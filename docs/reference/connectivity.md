---
title: Visual Studio Live Share de conectividad | Microsoft Docs
description: Información sobre los modos de conexión y conectividad para Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c1d537ac80daddcf83d18942c8d837f3c0ce370b
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73169992"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Requisitos de conectividad de Live Share

En este artículo se resumen los requisitos de conectividad de Visual Studio Live Share, las opciones de conectividad disponibles y las soluciones conocidas cuando proceda.

## <a name="sign-in"></a>Inicio de sesión

Puede iniciar sesión en Live Share con una cuenta profesional o educativa respaldada [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) , un [cuenta de Microsoft](https://account.microsoft.com/account)o un [Perfil de github](https://github.com/). Normalmente, las direcciones URL de inicio de sesión de estas están abiertas en la mayoría de las organizaciones dado el número de productos de acceso público que los usan, pero si no es así, póngase en contacto con el administrador de red para abrir `login.microsoftonline.com` o `github.com` además de los dominios que se [enumeran a continuación](#requirements-for-connection-modes).

> [!NOTE]
> Actualmente no se admiten cuentas de AD locales (ADFS) ni cuentas empresariales de GitHub locales [(👍de votos)](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>Modos de conexión

Para garantizar un rendimiento óptimo, Visual Studio Live Share detecta automáticamente si un equipo host de sesión de colaboración y un equipo invitado pueden comunicarse directamente a través de una red y solo retransmisiones a través de la nube si no hay ninguna ruta entre ellos. Este modo "automático" mixto es flexible e incluso permite a algunos invitados retransmitir a través de la nube mientras que otros se conectan directamente a la misma sesión.

Las conexiones directas se autentican a través de un mecanismo basado en la nube para garantizar la seguridad pero es necesario abrir un puerto entre 5990 y 5999 para habilitar la conectividad. Como resultado, al compartir por primera vez, es posible que el Firewall de escritorio le pida que abra un puerto. Aceptar esto es opcional, ya que si se omite, simplemente Live Share usar siempre la retransmisión en el modo auto.

Todas las conexiones en Visual Studio Live Share son SSH o SSL cifradas y autenticadas con un servicio central para asegurarse de que solo las de la sesión de colaboración puedan obtener acceso a su contenido. Además, la retransmisión en la nube de Live Share no conserva ningún tráfico enrutado a través de ella y no "Snoop" el tráfico de ningún modo.

## <a name="changing-the-connection-mode"></a>Cambiar el modo de conexión

Si prefiere deshabilitar las conexiones directas o retransmitidas o simplemente solucionar problemas de conectividad, puede forzar otros modos de conexión.

| Modo | Comportamiento del host | Comportamiento de invitado |
|------|----------------|----------------------|
| Auto | La sesión de colaboración del host acepta conexiones directas autenticadas y seguras o conexiones retransmitidas en la nube. | Intenta usar una conexión directa y recurre a la retransmisión a través de la nube si se produce un error. |
| Directa | La sesión de colaboración del host solo acepta conexiones directas autenticadas y seguras. | Intenta usar una conexión directa y se detiene si no se puede conectar. |
| Relé | La sesión de colaboración del host no permite conexiones directas. No hay ningún puerto abierto en el equipo del host. | Siempre se conecta a través de la nube. |

Para cambiar el modo:

**VIRTUAL**

1. Vaya a herramientas > Opciones > Live Share.
2. Seleccione el modo en la lista desplegable "modo de conexión".
3. Reinicie VS.

**VS Code:**

1. Edite Settings. JSON (archivos > Preferencias > configuración).
2. Establezca `"liveshare.connectionMode"` en `"auto"`, `"direct"`o `"relay"` en función de sus preferencias.
3. Reinicie VS Code.

## <a name="requirements-for-connection-modes"></a>Requisitos para los modos de conexión

El modo de conexión en el que se encuentra determinará los puertos y direcciones URL específicos que deben estar disponibles para que Live Share funcione.

| Modo | Requisitos de acceso de cliente | Solución de problemas |
|------|--------------|-----------------|
| Cualquiera | Acceso de salida a `*.liveshare.vsengsaas.visualstudio.com:443` | Asegúrese de que el Firewall de la red corporativa o personal le permite conectarse a este dominio. Escriba https://insiders.liveshare.vsengsaas.visualstudio.com en un explorador y compruébelo en la Página principal de Visual Studio Live Share. También puede encontrarse con [problemas de proxy](#proxies) que deben resolverse.|
| Any (VS Code) | Acceso de salida a `download.microsoft.com:443` | Asegúrese de que el Firewall de la red corporativa o personal le permite conectarse a este dominio. También puede encontrarse con [problemas de proxy](#proxies) que deben resolverse. |
| Auto | Modificadores automáticos. Consulte modos directo y de retransmisión. | Cambie al modo directo o de retransmisión para solucionar los problemas. |
| Directa | Hosts: es necesario abrir un puerto en el intervalo 5990-5999 para aceptar las conexiones de red locales entrantes.<br /><br />Invitados: ruta de red y acceso saliente al host en este mismo puerto. | Compruebe que el software de Firewall de escritorio no bloquee "vsls-Agent" para este intervalo de puertos y que pueda hacer ping entre sí. Mientras que Windows y otro software de escritorio deberían pedirle la primera vez que se inicia el agente, hemos encontrado instancias en las que las directivas de grupo impiden que esto suceda y tendrá que [Agregar manualmente la entrada](#manually-adding-a-firewall-entry). También puede encontrarse con [problemas de proxy](#proxies) que deben resolverse. |
| Relé | Acceso de salida a `*.servicebus.windows.net:443`. | Asegúrese de que el Firewall de la red corporativa o personal le permite conectarse a este dominio. También puede encontrarse con [problemas de proxy](#proxies) que deben resolverse.|

## <a name="manually-adding-a-firewall-entry"></a>Agregar manualmente una entrada de Firewall

Tal y como se ha descrito anteriormente, el modo Direct requiere que el firewall personal permita que **vsls-Agent** acepte las conexiones en el intervalo de puertos 5990-5999. Si desea usar el modo directo pero ha detectado que el Firewall no tiene vsls-Agent, puede agregarlo manualmente. La forma de hacerlo variará en función del software de firewall, pero puede encontrar información acerca de cómo **[configurar el Firewall de Windows aquí](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)** .

Si no ve una entrada para vsls-Agent, puede encontrar el ejecutable del agente en una de las siguientes ubicaciones.

### <a name="vs-code-agent-location"></a>VS Code Ubicación del agente

Reemplace **version** por el número de versión de la extensión en una de las siguientes rutas de acceso:

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Ubicación del agente de Visual Studio

La ubicación de Visual Studio es más dinámica, pero puede seguir estos pasos para encontrar el archivo ejecutable:

1. Vaya a la ubicación de instalación de Visual Studio. Normalmente se `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` donde **edición** es Community, Enterprise, etc.

2. Ejecute una búsqueda de `vsls-agent.exe` en la subcarpeta **IDE\Extensions** .

Desafortunadamente, es posible que tenga que realizar este paso **cada vez que actualice Visual Studio Live share.**

## <a name="proxies"></a>Servidores proxy

Actualmente, Visual Studio Live Share tiene algunas limitaciones en relación con el uso del proxy. Mientras que la configuración de proxy automática debe funcionar en Windows, al usar macOS o Linux (y con ciertas configuraciones de proxy en Windows) las variables de entorno **http_proxy** y **HTTPS_PROXY** deben establecerse de forma *global*.

Si el proxy no lo configura automáticamente, puede establecer manualmente las variables de la siguiente forma:

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

Si tiene un proxy de autenticación, puede Agregar el usuario y la contraseña de la siguiente manera:

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

Si estas opciones no solucionan el problema, indíquenos los detalles [de la configuración](https://github.com/MicrosoftDocs/live-share/issues/86) del proxy para que podamos echar un vistazo a la mejora del soporte técnico.

## <a name="see-also"></a>Vea también

- [Cómo colaborar con Visual Studio Code](../how-to-guides/vscode.md)
- [Colaborar con Visual Studio](../how-to-guides/vs.md)
- [Características de seguridad de Live Share](security.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
