---
title: Conectividad - Visual Studio Live Share | Microsoft Docs
description: Información sobre los modos de conectividad y conexión para Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 6edc5bcf18dde6f84a4972a1efd755592cbef18c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256425"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Requisitos de conectividad para Live Share

En este artículo se resume los requisitos de conectividad para Visual Studio Live Share, opciones de conectividad disponibles y soluciones conocidas cuando sea aplicable.

## <a name="sign-in"></a>Inicio de sesión

Puede iniciar sesión en Live Share mediante cualquiera [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) copia cuenta profesional o educativa, un [cuenta Microsoft](https://account.microsoft.com/account), o un [perfil de GitHub](https://github.com/). Normalmente, inicio de sesión de las direcciones URL de estos están abiertos en la mayoría de las organizaciones dada el número de productos orientados al públicos que usarlos, pero si no, póngase en contacto con el Administrador de red sobre la apertura de `login.microsoftonline.com` o `github.com` además de los dominios [enumerados a continuación](#requirements-for-connection-modes).

> [!NOTE]
> Local, cuentas de AD (AD FS) y las cuentas de GitHub Enterprise local, no se admiten actualmente [(enviar su voto a 👍)](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>Modos de conexión

Para garantizar un óptimo rendimiento, de forma predeterminada, Visual Studio Live Share detecta automáticamente si un equipo de host de sesión de colaboración y la máquina invitada pueden comunicarse directamente a través de una red y solo se retransmite a través de la nube si no hay ninguna ruta entre ellos. Este modo mixto "auto" es flexible y permite incluso que algunos los invitados retransmisión a través de la nube mientras que otros usuarios conexión directamente para la misma sesión.

Las conexiones directas se autentican a través de un mecanismo basado en la nube para garantizar la seguridad pero se requieren para habilitar la conectividad se puede abrir un puerto entre 5990 y 5999. Como resultado, cuando el uso compartido por primera vez el firewall de escritorio puede pedirle abrir un puerto. Aceptar que es opcional, ya que se les ignora Esto hará que simplemente Live Share usar siempre la retransmisión en el modo auto.

Todas las conexiones en Visual Studio Live Share son SSH o SSL cifradas y autenticadas contra un servicio central para asegurarse de que sólo los de la sesión de colaboración pueden tener acceso a su contenido. Además, retransmisión de la nube en vivo del recurso compartido no conserva todo el tráfico que se enruta a través de él y no "consultar" el tráfico de ninguna manera.

## <a name="changing-the-connection-mode"></a>Cambiar el modo de conexión

Si prefiere deshabilitar conexiones directas o retransmitidas o simplemente se esté solucionando problemas de conectividad, puede forzar otros modos de conexión.

| Modo | Comportamiento de host | Comportamiento de invitado |
|------|----------------|----------------------|
| Automático | Sesión de colaboración del host acepta conexiones directas segura y autenticadas o conexiones retransmitida en la nube. | Intenta utilizar una conexión directa y vuelve a la retransmisión a través de la nube si se produce un error. |
| Directa | Sesión de colaboración del host solo acepta conexiones directas autenticadas y seguras. | Intenta utilizar una conexión directa y se detiene si no puede conectarse. |
| Relé | Sesión de colaboración del host no permite conexiones directas. Ningún puerto se abre en la máquina del host. | Siempre se conecta a través de la nube. |

Para cambiar el modo:

**VS:**

1. Vaya a Herramientas > Opciones > Live Share.
2. Seleccione el modo en la lista desplegable de "Modo de conexión".
3. Reinicie VS.

**Código de VS:**

1. Editar settings.json (archivo > Opciones > configuración).
2. Establecer `"liveshare.connectionMode"` a `"auto"`, `"direct"`, o `"relay"` según sus preferencias.
3. Reinicie VS Code.

## <a name="requirements-for-connection-modes"></a>Requisitos para los modos de conexión

Se encuentra en el modo de conexión determinará el determinados puertos y direcciones URL que deben estar disponibles para Live Share a función.

| Modo | Requisitos de acceso de cliente | Solución de problemas |
|------|--------------|-----------------|
| Cualquiera | Acceso de salida a `*.liveshare.vsengsaas.visualstudio.com:443` | Asegúrese de que su empresa o firewall de red personal le permite conectarse a este dominio. Escriba https://insiders.liveshare.vsengsaas.visualstudio.com en un explorador y compruebe que lleguen en la página principal de Visual Studio Live Share. Puede que también esté ejecutando en [problemas de proxy](#proxies) que deben resolverse.|
| Cualquier (VS Code) | Acceso de salida a `download.microsoft.com:443` | Asegúrese de que su empresa o firewall de red personal le permite conectarse a este dominio. Puede que también esté ejecutando en [problemas de proxy](#proxies) que deben resolverse. |
| Automático | Modificadores de automático. Vea en directo y modos de retransmisión. | Cambiar a dirigir o modo de solucionar problemas de retransmisión. |
| Directa | Hosts: Un puerto en el intervalo 5990 5999 debe abrirse para aceptar conexiones entrantes de red local.<br /><br />Invitados: Una ruta de red y el acceso al host en este mismo puerto de salida. | Compruebe "VSL-agent" no está bloqueado por el software de firewall de escritorio para este intervalo de puertos y que puede hacer ping entre sí. Aunque Windows y otro software de escritorio puede solicitarle que la primera vez que se inicia el agente, hemos visto las instancias donde las directivas de grupo evitar que esto ocurra y deberá [agregue manualmente la entrada](#manually-adding-a-firewall-entry). Puede que también esté ejecutando en [problemas de proxy](#proxies) que deben resolverse. |
| Relé | Acceso de salida a `*.servicebus.windows.net:443`. | Asegúrese de que su empresa o firewall de red personal le permite conectarse a este dominio. Puede que también esté ejecutando en [problemas de proxy](#proxies) que deben resolverse.|

## <a name="manually-adding-a-firewall-entry"></a>Cómo agregar manualmente una entrada de firewall

Tal como se describió anteriormente, el modo direct requiere que el firewall personal permita **vsls como agente** para aceptar las conexiones en el puerto de intervalo 5990 5999. Si desea usar el modo directo pero ha encontrado que el firewall no tiene entrada VSL-agent, puede agregarlo manualmente. Cómo hacer esto variará según el software de firewall, pero puede encontrar información sobre  **[configurar el Firewall de Windows aquí](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)**.

Si no ve una entrada para VSL-agent, puede encontrar al agente ejecutable en una de las siguientes ubicaciones.

### <a name="vs-code-agent-location"></a>Ubicación del agente de código de VS

Sustituya **versión** para el número de versión de extensión en una de las rutas de acceso siguiente:

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Ubicación del agente de Visual Studio

La ubicación de Visual Studio es más dinámica, pero puede seguir estos pasos para encontrar el archivo ejecutable:

1. Vaya a la ubicación de instalación de Visual Studio. Este suele ser `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` donde **EDITION** es Community, Enterprise, etcetera

2. Ejecutar una búsqueda de `vsls-agent.exe` en bajo el **IDE\Extensions** subcarpeta.

Por desgracia es posible que deba realizar este paso **cada vez actualice Visual Studio Live Share.**

## <a name="proxies"></a>Servidores proxy

Visual Studio Live Share actualmente tiene algunas limitaciones en cuanto a uso del proxy. Aunque la configuración automática de proxy debería funcionar en Windows, cuando se usa en macOS o Linux (y con determinadas configuraciones de proxy en Windows) la **HTTP_PROXY** y **HTTPS_PROXY** deben variables de entorno se puede establecer *globalmente*.

Si no establece automáticamente el proxy de éstos para usted, puede establecer manualmente las variables de la forma siguiente:

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

Si tiene un proxy de autenticación, puede agregar el usuario y la contraseña como sigue:

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

Si estas opciones no resuelven el problema, [, comuníquenoslo](https://github.com/MicrosoftDocs/live-share/issues/86) por lo que podemos echamos un vistazo a mejorar el soporte técnico de instalación de los detalles del proxy.

## <a name="see-also"></a>Vea también

- [Cómo: Colaborar mediante Visual Studio Code](../use/vscode.md)
- [Cómo: Colaborar mediante Visual Studio](../use/vs.md)
- [Características de seguridad de Live Share](security.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
