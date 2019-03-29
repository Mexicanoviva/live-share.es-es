---
title: 'Solución de problemas: Visual Studio Live Share | Microsoft Docs'
description: Solución de problemas de sugerencias y trucos para Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5fc611714d148a9ba1d5a6848e0399af753d1a37
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640216"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Solución de problemas de Visual Studio Live Share

Este artículo trata las sugerencias para solucionar problemas, soluciones y respuestas para preguntas y problemas comunes. También puede echar un vistazo a la [preguntas más frecuentes sobre](faq.md). 

## <a name="installation--tool-requirements"></a>Instalación y la herramienta de requisitos

Los siguientes son sugerencias para solucionar problemas relacionados con la instalación de Visual Studio Live Share.

| Herramienta | Problema | Resolución o solución alternativa |
|------|---------|------------|
| VS | El instalador de extensión <strong>no se puede encontrar una versión de Visual Studio</strong> que se utilizará al intentar instalar la extensión de Visual Studio Live Share. | Requiere Visual Studio Live Share **Visual Studio 2017 versión 15.6** o superior para hosts e invitados. Instalar el estable más reciente [actualización de Visual Studio 2017](https://visualstudio.com/vs/) e intente de nuevo.|
| VS Code | Aparece un error al intentar usar Visual Studio Live Share con VS Code en macOS <strong>El capitán o por debajo</strong>. | Compatibilidad del Visual Studio Live Share sistema operativo depende de .NET Core que actualmente [solo admite macOS Sierra y superiores.]((https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).) |
| VS Code | Un "**no se puede instalar las dependencias**" aparece un error mientras extensión es **Finalizando instalación** en el primer inicio, o bien obtener errores sobre **que faltan o están presentes archivos**. | Compruebe que está en un **buena conexión de red**. Si es así, puede que esté ejecutando en un **proxy o firewall** problema. Consulte [solucionar problemas de conectividad](#connectivity). <br /><br />|
| VS Code | Instalar la extensión de Visual Studio Live Share desde marketplace <strong>lo instala en la versión de stable/insiders de VS Code</strong> en lugar de la versión desee. | Iniciar estable de VS Code o insiders según sus preferencias, haga clic en la pestaña "extensiones", busque "Visual Studio Live Share" e instalar desde allí. |
| Código de VS (**Linux**) | No se activa la extensión Live Share y **no aparece ningún elemento de barra de estado** después de instalar la extensión en **Linux**. | Visual Studio Live Share depende de .NET Core 2.0 que tiene un número de requisitos previos de Linux que no pueden cumplirse en algunas distribuciones de Linux de forma predeterminada. Consulte [aquí para obtener detalles](reference/linux.md#install-linux-prerequisites) en lo que debe estar instalado. |

## <a name="sign-in"></a>Inicio de sesión

Los siguientes son sugerencias para solucionar problemas para los problemas de inicio de sesión.

| Herramienta | Problema | Resolución o solución alternativa |
|------|---------|------------|
| VS | Se debe iniciar sesión en Visual Studio Live Share con un <strong>otra identidad</strong> que usas para iniciar sesión en Visual Studio. | Vaya a Herramientas > Opciones > Live Share > cuenta de usuario para seleccionar una cuenta alternativa. |
| VS Code | Mientras que una ventana de explorador emergente durante el inicio de sesión y el proceso <strong>aparece correctamente en la página web</strong>, la barra de estado <strong>todavía se dice, "Iniciar sesión"</strong> después de cerrar el explorador. | Después de iniciar sesión, haga clic en "Teniendo problemas?" y siga las instrucciones para escribir un código de usuario temporales en la herramienta.<br /><br />Nos encantaría ver lo que podría estar ocurriendo, lo póngase [registra un error](https://aka.ms/vsls-problem). |
| Todas | Obtiene un <strong>error de conexión o el tiempo de espera</strong>. | Consulte [solucionar problemas de conectividad](#connectivity). |
| Todas | Al inicio de sesión con un Microsoft seguridad **profesional o educativa de la dirección de correo electrónico** verá un mensaje que dice, **"Necesita la aprobación del administrador"**. | El principio básico de Azure AD está configurada para solicitar "consentimiento del administrador" para tener acceso al contenido del directorio de aplicaciones nuevas. Consulte [aquí](reference/security.md) para obtener más detalles. |
| VS Code (**macOS**) | Al iniciar sesión en el vea un error que indica **SecKeychainAddGenericPassword() no se pudo**. | Esto es casi siempre debido a un problema común con macOS donde los cambios de contraseña no se reflejan en la cadena de claves de inicio de sesión. Intente ir a "Acceso a llaves", el bloqueo de la cadena de claves de inicio de sesión y, a continuación, desbloquear. Esto puede ser suficiente para resolver el problema, pero si no se puede desbloquear con su contraseña actual, pruebe su uno anterior. Si eso funciona, cambie la contraseña de la cadena de claves de inicio de sesión con su contraseña actual. Consulte [aquí](https://support.apple.com/en-us/HT201609) para obtener más información. |
| Código de VS (**Linux**) | Al escribir en el código de usuario después de iniciar sesión a través del explorador verá un error que indica **secret_password_store_sync() error con el código XX**. | Esto suele ser debido a `gnome-keyring` o `libsecret-1-0` /  `libsecret` no se está instalando. Puede validar gnome keyring está configurado correctamente mediante la instalación de `seahorse` y, a continuación, usar la aplicación de "Contraseñas y claves" en su entorno de escritorio. Obtenga más información sobre [requisitos previos de Linux aquí](reference/linux.md#install-linux-prerequisites). |
| Código de VS (**Linux**) | Está <strong>le pedirá que escriba un código de usuario</strong> con Live Share v0.3.295 o una versión inferior, pero ningún explorador aparecerá para permitirle obtener uno. | Estamos trabajando para eliminar el requisito de código de usuario en Linux. En el tiempo medio, debe aparecer una ventana del explorador para que pueda usar para iniciar sesión. Si no es así, la ventana del explorador puede estar oculto bajo VS Code. Si esto no es así, consulte la siguiente sugerencia.  |
| VS Code | Tras hacer clic en "Iniciar sesión" (o mediante el "recurso compartido en vivo: Iniciar sesión"comando), <strong>no aparecerá ninguna ventana del explorador para que pueda escribir sus credenciales</strong>. | 1. [Iniciar sesión aquí](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. Después de iniciar sesión, haga clic en "Teniendo problemas?"<br /> 3. Siga las instrucciones para escribir un código de usuario temporales en la herramienta. |
| Todas | Le gustaría <strong>combinación</strong> una sesión de colaboración</strong> pero <strong>no lo ha hecho o no desea recibir actualizaciones por correo electrónico</strong>. | Inicio de sesión en la extensión Live Share en VS/VS Code <strong>no</strong> optar por recibir actualizaciones por correo electrónico.<br /><br />Recurso compartido en vivo requiere los invitados que inicie sesión como una medida de seguridad, por lo que el host tiene visibilidad a la identidad de los usuarios que se hayan unido. [Votar a favor de esta característica](https://github.com/MicrosoftDocs/live-share/issues/3) si desea que la opción para permitir que los usuarios anónimos unir (por ejemplo, los usuarios sin nombre / nombre definido por el usuario). |

## <a name="share-and-join"></a>Recurso compartido y combinación

Los siguientes son sugerencias para solucionar problemas para los problemas de inicio de sesión.

| Herramienta | Problema | Resolución o solución alternativa |
|------|----------------|------------|
| Todas | <strong>Recurso compartido/combinación:</strong> Recibe un error sobre la imposibilidad de conectarse o tiempo de espera. | Consulte [solucionar problemas de conectividad](#connectivity). |
| VS Code | <strong>Combinación:</strong> Estaba <strong>no solicitadas / capaces de lanzar VS Code</strong> después de abrir la página de combinación en un explorador. |  Sugerencias: <ul><li>Asegúrese de haber <i>iniciado al menos una vez el código de VS y esperado durante la instalación se complete en la barra de estado.</i></li><li>Si esto no funciona, intente ejecutar el "recurso compartido en vivo: Comando de instalación de iniciador".</li><li>**Los usuarios de Linux**: Si se le pide que escriba la contraseña de administrador (sudo) cuando se ejecuta el comando anterior, hágalo.</li><li>Por último, consulte [combinar manualmente](reference/manual-join.md) como solución alternativa.</li></ul> Si se produce este problema, nos gustaría ver lo que podría estar ocurriendo, lo póngase [registra un error](https://aka.ms/vsls-new-issue). |
| VS | <strong>Combinación:</strong> Estaba <strong>no solicitadas / capaz de iniciar VS</strong>  después de abrir la página de combinación en un explorador. |  Consulte [Participar manualmente](reference/manual-join.md).<br /><br /> Nos encantaría ver los registros, por lo tanto, [registra un error](https://aka.ms/vsls-problem) mediante Visual Studio "informe de un problema..." característica. |
| Todas | <strong>Combinación:</strong> Sería preferible <strong>pegue el vínculo de unión directamente en Visual Studio o VS Code</strong> en lugar de hacer clic en el vínculo web. | Consulte [Participar manualmente](reference/manual-join.md). |
| Todas | <strong>Combinación:</strong> Vea un mensaje que dice, "**el propietario del área de trabajo parece estar sin conexión**," al unirse a través del explorador. | Posibles soluciones:<br /><ul><li>Pruebe [combinar manualmente](reference/manual-join.md). Hemos visto problemas entre regiones (p. ej., Asia y oeste de EE. UU.) combinaciones debido a problemas de servicio que no afectan a las combinaciones manuales.</li><li>Recurso compartido en vivo puede ser no se puede enrutar directamente al host cuando se ejecuta en modo de conexión de "auto". Pruebe [modo retransmisión](reference/connectivity.md).</li></ul>Consulte [solucionar problemas de conectividad](#connectivity) para obtener más posibilidades |
| VS Code | <strong>Combinación:</strong> Se unió a través del explorador <strong>antes de iniciar sesión</strong>, no se pide que inicie sesión</strong>y la combinación nunca se ha completado. |  Se trata de un [problema conocido](https://github.com/MicrosoftDocs/live-share/issues/167). Haga clic en el inicio de sesión en el elemento de la barra de estado para iniciar sesión y, a continuación, unir de nuevo. |

## <a name="connectivity"></a>Conectividad

La siguiente información puede ayudarle a solucionar problemas si tiene problemas relacionados con la conectividad o los tiempos de espera al iniciar sesión, uso compartido, o la combinación.

Como se describe en el [los requisitos de conectividad para Live Share](reference/connectivity.md) artículo, modos de conexión diferentes tienen requisitos diferentes para funcionar, por lo que hay algunos problemas posibles diferentes en.

| Herramienta | Problema | Causa probable |
|------|------|----------------|
| Todas | Usa un <strong>proxy</strong> y está viendo un número de problemas de conectividad | Configuración de proxy puede ser complicada.  Pruebe a establecer el **HTTP_PROXY** y **HTTPS_PROXY** variables de entorno **globalmente** y, a continuación, reiniciar la herramienta. Consulte [configuración de proxy](reference/connectivity.md#proxies) para obtener más detalles. Es probable que hay algunas configuraciones que no admite aún, por lo que [háganoslo saber](https://github.com/MicrosoftDocs/live-share/issues/86) si esto no funciona para usted. |
| VS Code | Después de instalar la extensión y VS Code inicia por primera vez obtenga un <strong>un error cuando "Finalización de la instalación" aparece en la barra de estado</strong>. |  No se puede obtener acceso a internet o acceso a download.visualstudio.microsoft.com o download.microsoft.com en el puerto 443 está bloqueado por el firewall personal o corporativo. Consulte [aquí](https://github.com/MicrosoftDocs/live-share/issues/58) para obtener información sobre por qué Live Share necesita descargar algo en este momento. |
| Todas | Está <strong>no se puede iniciar sesión en Visual Studio Live Share</strong> | No se puede acceder a internet o tener acceso a *. liveshare.vsengsaas.visualstudio.com en el puerto 80/443 está bloqueado por el firewall personal o corporativo. Escriba https://insiders.liveshare.vsengsaas.visualstudio.com en un explorador y compruebe que lleguen en la página principal de Visual Studio Live Share. |
| Todas | Se encuentra en <strong>modo auto</strong> (valor predeterminado), pueden iniciar sesión, pero vea un <strong>error de conexión o el tiempo de espera</strong> al uso compartido o la combinación. | O bien, tanto directa y se producen errores en los modos de conectarse o hay un error con el modo auto de retransmisión. Si puede conectarse después [conmutación para dirigir o modo de retransmisión](reference/connectivity.md#changing-the-connection-mode), por favor, [genere un error](https://aka.ms/vsls-problem). |
| Todas | Se encuentra en <strong>modo directo</strong>, pueden iniciar sesión, pero vea un <strong>error de conexión o el tiempo de espera</strong> al uso compartido o la combinación. | El invitado y el host no se pueden conectar directamente. Pruebe [modo auto o retransmisión](reference/connectivity.md#changing-the-connection-mode) para ver si el problema desaparece. Es posible que deba [permitir Live Share manualmente a través del firewall personal](reference/connectivity.md#manually-adding-a-firewall-entry) o simplemente usar el modo de retransmisión. |
| Todas | Se encuentra en <strong>modo retransmisión</strong>, pueden iniciar sesión, pero se le notificará una <strong>error de conexión o el tiempo de espera</strong> al uso compartido o la combinación. | El acceso a *. servicebus.windows.net en el puerto 80 y 443 se bloquea está bloqueado por el firewall personal o corporativo. Pruebe [modo directo](reference/connectivity.md#changing-the-connection-mode). |

Consulte la [los requisitos de conectividad para Live Share](reference/connectivity.md) artículo para obtener más información sobre los requisitos de conectividad.

## <a name="see-also"></a>Vea también

Guías de inicio rápido

- [Uso compartido de un primer proyecto](quickstart/share.md)
- [Participación en una primera sesión](quickstart/join.md)

Temas procedimentales

- [Colaboración mediante Visual Studio Code](use/vscode.md)
- [Colaboración mediante Visual Studio](use/vs.md)

Referencia

- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)
- [Requisitos de conectividad de Live Share](reference/connectivity.md)
- [Detalles de la instalación de Linux](reference/linux.md)
- [Compatibilidad con lenguajes y plataformas](reference/platform-support.md)
- [Compatibilidad con extensiones](reference/extensions.md)

¿Sigue teniendo problemas? También puede [proporcionar comentarios](support.md).
