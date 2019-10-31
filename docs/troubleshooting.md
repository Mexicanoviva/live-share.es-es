---
title: Solución de problemas-Visual Studio Live Share | Microsoft Docs
description: Sugerencias y trucos para la solución de problemas de Visual Studio Live Share.
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
ms.openlocfilehash: 087c3b209c8762e08b8d663f7c0a6fb3a40fee19
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170039"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Solución de problemas Visual Studio Live Share

En este artículo se describen las sugerencias, soluciones alternativas y respuestas para solucionar problemas comunes. También puede echar un vistazo a las [preguntas más frecuentes](faq.md). 

## <a name="installation--tool-requirements"></a>Requisitos de instalación y herramientas

A continuación se incluyen sugerencias para la solución de problemas relacionados con la instalación de Visual Studio Live Share.

| Herramienta | Problema | Solución/solución alternativa |
|------|---------|------------|
| VS | El instalador <strong>de extensión no puede encontrar una versión de Visual Studio</strong> para usar al intentar instalar la extensión de Visual Studio Live share. | Visual Studio Live Share requiere **Visual Studio 2017 versión 15,6** o superior para hosts e invitados. Instale la actualización estable más reciente [de Visual Studio 2017](https://visualstudio.com/vs/) e inténtelo de nuevo.|
| VS Code | Aparece un error al intentar usar Visual Studio Live Share con VS Code en macOS el <strong>Capitan o a continuación</strong>. | La compatibilidad del sistema operativo de Visual Studio Live Share depende de .NET Core, que actualmente [solo admite MacOS Sierra y up](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md). |
| VS Code | Aparece el error "**no se pudieron instalar las dependencias**" mientras la extensión está **finalizando la instalación** al iniciarse por primera vez o cuando se producen errores en **los archivos que faltan o que ya están presentes**. | Compruebe que está en una **conexión de red correcta**. Si es así, puede que se encuentre en un problema de **proxy o firewall** . Consulte [solución de problemas de conectividad](#connectivity). <br /><br />|
| VS Code | La instalación de la extensión de Visual Studio Live Share desde Marketplace la <strong>instala en la versión stable/Insider de vs Code</strong> en lugar de la versión que quiero. | Inicie VS Code estables o Insider en función de sus preferencias, haga clic en la pestaña "extensiones", busque "Visual Studio Live Share" e instálelo desde allí. |
| VS Code (**Linux**) | La extensión de Live Share no se activa y **no aparecen elementos de barra de estado** después de instalar la extensión en **Linux**. | Visual Studio Live Share depende de .NET Core 2,0, que tiene una serie de requisitos previos de Linux que no se pueden cumplir en determinadas distribuciones de Linux de forma predeterminada. Vea [aquí para obtener más información](reference/linux.md#install-linux-prerequisites) sobre lo que se debe instalar. |

## <a name="sign-in"></a>Inicio de sesión

A continuación se incluyen sugerencias para solucionar problemas de inicio de sesión.

| Herramienta | Problema | Solución/solución alternativa |
|------|---------|------------|
| VS | Debe iniciar sesión en Visual Studio Live Share con una <strong>identidad diferente</strong> a la que usa para iniciar sesión en Visual Studio. | Vaya a herramientas > Opciones > Live Share > cuenta de usuario para seleccionar una cuenta alternativa. |
| VS Code | Mientras se abre una ventana del explorador durante el inicio de sesión y <strong>parece que el proceso se realiza correctamente en la página web</strong>, la barra de estado <strong>sigue indicando "iniciar sesión"</strong> después de cerrar el explorador. | Después de iniciar sesión, haga clic en "¿tiene problemas?". y siga las instrucciones para especificar un código de usuario temporal en la herramienta.<br /><br />También nos encantaría ver lo que podría estar ocurriendo, por lo que debe [registrar un error](https://aka.ms/vsls-problem). |
| Todas | Recibe un error de <strong>tiempo de espera o de conexión</strong>. | Consulte [solución de problemas de conectividad](#connectivity). |
| Todas | Al iniciar sesión con una **dirección de correo electrónico profesional o educativa** respaldada por Microsoft, verá un mensaje que dice **"necesita aprobación de administrador"** . | El principio del Azure AD es configurar para requerir "consentimiento del administrador" para las nuevas aplicaciones que acceden al contenido del directorio. Vea [aquí](reference/security.md) para obtener más detalles. |
| VS Code (**MacOS**) | Al iniciar sesión, verá un error que indica que **SecKeychainAddGenericPassword () dio error**. | Esto casi siempre se debe a un problema común con macOS en el que los cambios de contraseña no se reflejan en la cadena de inicio de sesión. Intente entrar en "acceso a llaves", bloqueando la cadena de inicio de sesión y, a continuación, desbloquee de nuevo. Esto puede ser suficiente para resolver el problema, pero si no puede desbloquearlo con la contraseña actual, pruebe con el anterior. Si funciona, cambie la contraseña de la cadena de inicio de sesión a la contraseña actual. Vea [aquí](https://support.apple.com/en-us/HT201609) para obtener más información. |
| VS Code (**Linux**) | Al escribir en el código de usuario después de iniciar sesión a través del explorador, verá un error que indica que **secret_password_store_sync () produjo un error con el código de error XX**. | Esto suele deberse a `gnome-keyring` y/o `libsecret-1-0` /  `libsecret` no se instalan. Puede validar GNOME-el montaje de claves configurado correctamente instalando `seahorse` y, a continuación, usando la aplicación "contraseñas y claves" en el entorno de escritorio. Obtenga más información sobre los [requisitos previos de Linux aquí](reference/linux.md#install-linux-prerequisites). |
| VS Code (**Linux**) | Se <strong>le pedirá que escriba un código de usuario</strong> con Live share v 0.3.295 o una versión inferior, pero no aparecerá ningún explorador que le permita obtenerlo. | Estamos trabajando para eliminar el requisito de código de usuario en Linux. En el tiempo medio, debe aparecer una ventana del explorador para que pueda usar para iniciar sesión. Si no es así, puede que la ventana del explorador esté oculta en VS Code. Si no es así, consulte la siguiente sugerencia.  |
| VS Code | Después de hacer clic en "iniciar sesión" (o mediante el comando "Live Share: iniciar sesión"), <strong>no aparece ninguna ventana del explorador que le permita escribir sus credenciales</strong>. | 1. [inicie sesión aquí](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. después de iniciar sesión, haga clic en "¿tiene problemas?".<br /> 3. Siga las instrucciones para especificar un código de usuario temporal en la herramienta. |
| Todas | Le gustaría <strong>unirse</strong> a una sesión de colaboración </strong> pero <strong>no desea recibir actualizaciones de correo electrónico</strong>. | Iniciar sesión en la extensión de Live Share en VS/VS Code no le <strong>deja</strong> de recibir actualizaciones de correo electrónico.<br /><br />Live Share requiere que los invitados inicien sesión como medida de seguridad para que el host tenga visibilidad sobre la identidad de los que se han unido. [Subir votar esta característica](https://github.com/MicrosoftDocs/live-share/issues/3) si desea permitir que los usuarios anónimos se unan (por ejemplo, los usuarios sin nombre o un nombre definido por el usuario). |

## <a name="share-and-join"></a>Compartir y unirse

A continuación se incluyen sugerencias para solucionar problemas de inicio de sesión.

| Herramienta | Problema | Solución/solución alternativa |
|------|----------------|------------|
| Todas | <strong>Compartir/unirse:</strong> Está obteniendo un tiempo de espera o un error de no poder conectarse. | Consulte [solución de problemas de conectividad](#connectivity). |
| VS Code | <strong>Unirse:</strong> No se <strong>le solicitó o inició la vs Code</strong> después de abrir la página de combinación en un explorador. |  Sugerencias: <ul><li>Asegúrese <i>de haber iniciado el vs Code al menos una vez y ha esperado a que la instalación se complete en la barra de estado.</i></li><li>Si eso no funciona, pruebe a ejecutar el comando "Live Share: instalación del iniciador".</li><li>**Usuarios de Linux**: si se le solicita que escriba la contraseña de administrador (sudo) al ejecutar el comando anterior, hágalo.</li><li>Por último, consulte [combinación manual](reference/manual-join.md) como solución alternativa.</li></ul> Si alcanza este problema, nos encantaría ver lo que está ocurriendo, por lo que debe [registrar un error](https://aka.ms/vsls-new-issue). |
| VS | <strong>Unirse:</strong> No se <strong>le solicitó o no pudo iniciar vs</strong> después de abrir la página de combinación en un explorador. |  Consulte [Participar manualmente](reference/manual-join.md).<br /><br /> También nos encantaría ver los registros, por lo que debe [registrar un error](https://aka.ms/vsls-problem) con "Notificar un problema..." de Visual Studio. ofrecen. |
| Todas | <strong>Unirse:</strong> Preferiría <strong>pegar el vínculo de combinación directamente en Visual Studio/vs Code</strong> en lugar de hacer clic en el vínculo Web. | Consulte [Participar manualmente](reference/manual-join.md). |
| Todas | <strong>Unirse:</strong> Verá un mensaje que dice "**el propietario del área de trabajo parece estar sin conexión**" al unirse a través del explorador. | Posibles soluciones:<br /><ul><li>Intente [unirse manualmente](reference/manual-join.md). Hemos detectado problemas con las uniones entre regiones (por ejemplo, este y oeste de EE. UU.) debido a problemas de servicio que no afectan a las combinaciones manuales.</li><li>Es posible que Live Share no pueda enrutar directamente al host cuando se ejecute en el modo de conexión "automática". Pruebe el [modo de retransmisión](reference/connectivity.md).</li></ul>Consulte [solución de problemas de conectividad](#connectivity) para más posibilidades |
| VS Code | <strong>Unirse:</strong> Se unió a través del explorador <strong>antes de iniciar</strong>sesión, no se le solicitó que iniciara sesión </strong> y la combinación nunca se completaba. |  Se trata de un [error conocido](https://github.com/MicrosoftDocs/live-share/issues/167). Haga clic en el elemento de la barra de estado de inicio de sesión para iniciar sesión y volver a unirse. |

## <a name="connectivity"></a>Conectividad

La siguiente información puede ayudarle a solucionar problemas si tiene problemas relacionados con la conectividad o los tiempos de espera al iniciar sesión, compartir o unirse.

Tal y como se describe en los [requisitos de conectividad de Live share](reference/connectivity.md) artículo, los distintos modos de conexión tienen requisitos diferentes para funcionar, por lo que hay algunos problemas potenciales diferentes que se producen.

| Herramienta | Problema | Causa probable |
|------|------|----------------|
| Todas | Está usando un <strong>proxy</strong> y está viendo varios problemas de conectividad | La configuración de proxy puede resultar complicada.  Intente establecer las variables de entorno **http_proxy** y **HTTPS_PROXY** **globalmente** y, a continuación, reinicie la herramienta. Consulte [configuración de proxy](reference/connectivity.md#proxies) para obtener más detalles. Es probable que todavía no se admitan algunas configuraciones, por lo que [vamos a saber](https://github.com/MicrosoftDocs/live-share/issues/86) si esto no funciona en su caso. |
| VS Code | Después de instalar la extensión e iniciar VS Code por primera vez, <strong>aparecerá un error cuando aparezca el mensaje "finalizando la instalación" en la barra de estado</strong>. |  No se puede tener acceso a Internet o el acceso a download.visualstudio.microsoft.com y/o download.microsoft.com en el puerto 443 está bloqueado por el firewall personal o corporativo. Vea [aquí](https://github.com/MicrosoftDocs/live-share/issues/58) para obtener información sobre por qué Live share necesita descargar algo en este momento. |
| Todas | No puede <strong>iniciar sesión en Visual Studio Live share</strong> | No se puede acceder a Internet o a *. liveshare.vsengsaas.visualstudio.com en el puerto 80/443 está bloqueado por el firewall personal o corporativo. Escriba https://insiders.liveshare.vsengsaas.visualstudio.com en un explorador y compruébelo en la Página principal de Visual Studio Live Share. |
| Todas | Está en <strong>modo auto</strong> (valor predeterminado), puede iniciar sesión, pero puede ver un error de <strong>tiempo de espera o de conexión</strong> al compartir o unirse. | Tanto los modos directo como el de retransmisión no se pueden conectar o hay un error con el modo auto. Si puede conectarse después [de cambiar al modo directo o de retransmisión](reference/connectivity.md#changing-the-connection-mode), [genere un error](https://aka.ms/vsls-problem). |
| Todas | Está en <strong>modo directo</strong>, es capaz de iniciar sesión, pero ve un <strong>error de tiempo de espera o de conexión</strong> al compartir o unirse. | El invitado y el host no se pueden conectar directamente. Pruebe el [modo automático o de retransmisión](reference/connectivity.md#changing-the-connection-mode) para ver si el problema desaparece. Es posible que necesite [permitir manualmente Live share a través del firewall personal](reference/connectivity.md#manually-adding-a-firewall-entry) o simplemente usar el modo de retransmisión. |
| Todas | Está en <strong>modo de retransmisión</strong>, puede iniciar sesión, pero se le notifica un error de <strong>tiempo de espera o de conexión</strong> al compartir o unirse. | El acceso a *. servicebus.windows.net en el puerto 80/443 está bloqueado por el firewall personal o corporativo. Pruebe el [modo directo](reference/connectivity.md#changing-the-connection-mode). |

Consulte los [requisitos de conectividad de Live share](reference/connectivity.md) artículo para más información sobre los requisitos de conectividad.

## <a name="see-also"></a>Vea también

Tutoriales rápidos

- [Uso compartido de un primer proyecto](quickstart/share.md)
- [Participación en una primera sesión](quickstart/join.md)

Temas procedimentales

- [Colaboración mediante Visual Studio Code](how-to-guides/vscode.md)
- [Colaboración mediante Visual Studio](how-to-guides/vs.md)

Referencia

- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)
- [Requisitos de conectividad de Live Share](reference/connectivity.md)
- [Detalles de la instalación de Linux](reference/linux.md)
- [Compatibilidad con lenguajes y plataformas](reference/platform-support.md)
- [Compatibilidad con extensiones](reference/extensions.md)

¿Sigue teniendo problemas? Puede [proporcionar comentarios](support.md).
