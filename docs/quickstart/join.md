---
title: 'Únase a Inicio rápido: Visual Studio Live Share | Microsoft Docs'
description: Un tutorial resumido acerca de cómo combinar la primera sesión de colaboración de Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: d4280484aaa3fd4ac204588bf4aefc4e3ac51871
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256376"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>Inicio rápido: Únase a la primera sesión de colaboración

> **Nota: Visual Studio Live Share está actualmente en versión preliminar. Las características y la experiencia de usuario no son finales.**

Le damos la bienvenida a Visual Studio Live Share. Live Share le permite editar y depurar en colaboración con otros usuarios en tiempo real, independientemente del lenguaje de programación que use o los tipos de aplicaciones que compile. Permite al instante y segura para unirse a proyecto actual de un compañero de equipo y, a continuación, según sea necesario, escriba en la depuración de las sesiones, ver y editar las instancias de terminales, vea aplicaciones web de host local, las llamadas de voz de combinación y mucho más!

¿A punto para comenzar? Colaboración en equipo debería ser tan rápido y natural, que resulta difícil para no hacerlo! Por este motivo, Visual Studio Live Share simplifica la introducción, para que puede empezar a compartir su trabajo y las ideas sin problemas.

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

Siga estos pasos para participar en una sesión de colaboración.

## <a name="1-install-the-extension"></a>1. Instalar la extensión

La extensión de la instalación es sencilla. Siga estos pasos:

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0 y versiones posteriores)</strong><br />
        1. Instale <a href="https://code.visualstudio.com/">Visual Studio Code</a> para Windows (7, 8.1 o 10), macOS <b>(Sierra y versiones posteriores)</b> o Linux de 64 bits <b>(<a href="../use/vscode.md#installation">detalles</a>)</b>.<br />
        2. Descargue e instale la extensión de Visual Studio Live Share desde Marketplace. <br />
        3. Vuelva a cargar y espere a que las dependencias se descarguen e instalen (consulte la barra de estado).<br />
        4. <strong>Linux</strong>: Si se le pide que <a href="../reference/linux.md#install-linux-prerequisites">instale bibliotecas</a>, haga clic en Instalar, escriba la contraseña y reinicie VS Code cuando haya terminado.<br />
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td style="border:none;">
        <strong>Visual Studio 2017, versión 15.6 o posterior</strong><br />
        1. Instale la versión más reciente de <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a> (15.6 y versiones posteriores) en Windows (7, 8.1 o 10).<br/>
        2. Instale una <a href="../reference/platform-support.md">carga de trabajo compatible</a> (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).<br />
        3. Descargue e instale la extensión de Visual Studio Live Share desde Marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button"></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Instale la versión preliminar de <a href="https://aka.ms/vs-preview">Visual Studio 2019</a>.<br/>
        2. Instale una <a href="../reference/platform-support.md">carga de trabajo compatible</a> (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).<br />
        3. Visual Studio Live Share se instala de forma predeterminada con esas cargas de trabajo. <br />
    </td>
</tr>
</table>

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](../troubleshooting.md).

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [combinación de opcional] como invitado de solo lectura en VS Code

En VS Code, después de instalar la extensión Live Share, reiniciando y esperando las dependencias para finalizar la instalación, puede dar el salto y participar en una sesión de colaboración como invitado de solo lectura.

> [!NOTE]
> Si desea realizar modificaciones en el código que se va a unir, deberá [inicie sesión en](../quickstart/join.md#3-Sign-in).

Abre (o volver a abre) el vínculo de invitación en un explorador y recibirá una notificación que desea que el explorador iniciar VS Code. Deje que se inicie y empezará a conectarse a la sesión de colaboración.

Cuando se inicia VS Code, obtendrá una notificación del sistema para iniciar sesión. Seleccione "Continuar como invitado de solo lectura" unirse a la sesión.

![Unir como sesión como una notificación del sistema de invitado de solo lectura](../media/vscode-read-only-guest.png)

Se le pedirá que escriba un nombre para mostrar para ayudar a los participantes a identificar al usuario en la sesión.

![Nombre de invitado de solo lectura](../media/vscode-read-only-guest-name.png)

Después, les unirán en la sesión como de solo lectura. Podrá ver y navegar por el código, depuración conjunta y los servidores compartida la vista y terminales (es de solo lectura).

> [!NOTE]
> Si desea obtener acceso de lectura/escritura para el código de más adelante, puede iniciar sesión. Haga clic en su nombre para mostrar en el estado, barra y seleccione la opción "iniciar sesión".
![Inicio de sesión de solo lectura invitado](../media/vscode-read-only-guest-signin.png) se iniciará el explorador, y se puede iniciar sesión con una cuenta de Microsoft o GitHub.

## <a name="3-sign-in"></a>3. Inicio de sesión

Después de instalar la extensión Live Share, reiniciando y esperando las dependencias finalizar la instalación (VS Code), desea iniciar sesión para que otros participantes sepa quién es usted. Si omite este paso, se le pide que inicie una sesión durante el proceso de unión, o puede unirse a la sesión como un invitado de solo lectura. Haga clic en el elemento de barra de estado "compartir" (VS Code) o "inicio de sesión" botón (VS) para empezar a trabajar.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

En **VS Code**, se iniciará el explorador mientras aparecerá una notificación que le pide que inicie sesión en el inicio. Completar el inicio de sesión en proceso en el explorador, a continuación, simplemente cierre el explorador cuando haya terminado.

![Notificación del sistema que pide que inicie sesión con un explorador web](../media/vscode-sign-in-toast.png)

> **Usuarios de Linux:** Se le pedirá que escriba un código de usuario si usa una versión anterior de Live Share (v0.3.295 o por debajo). Actualizar a la versión más reciente de la extensión o haga clic en el "teniendo problemas?" vincular después del inicio de sesión para ver el código. Consulte [aquí para obtener detalles](../use/vscode.md#sign-in-using-a-user-code).

En **Visual Studio**, Live Share usa automáticamente la [cuenta de personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Como resultado, simplemente puede iniciar sesión como lo haría normalmente. Sin embargo, si prefiere usar un inicio de sesión diferente en que la cuenta de personalización de Visual Studio, vaya a **herramientas &gt; opciones &gt; Live Share &gt; cuenta de usuario** y seleccione credenciales diferentes.

Consulte [solución de problemas](../troubleshooting.md#sign-in) si se sigue produciendo problemas.

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Abrir/volver-open vínculo de la invitación de un explorador

Ahora, basta con abrir (o volver a abrir) el vínculo de invitación en un explorador.

> **Nota**: Si aún no ha instalado la extensión Live Share, se mostrarán con vínculos a marketplace de extensión. Instalar la extensión y reinicie la herramienta y vuelva a intentar.

Debería recibir una notificación que desea que el explorador iniciar una herramienta de Live Share habilitado. Si se permite que inicie la herramienta seleccionada, se conectará a la sesión de colaboración, una vez que se inicia.

![Únase a la página](../media/join-page.png)

Si el host está sin conexión, se le notificará en este momento en su lugar. A continuación, puede ponerse en contacto con el host y pídale que vuelva a compartir.

> **Sugerencia de solución de problemas:** Al usar VS Code, asegúrese de haber **inicia la herramienta de al menos una vez** después de instalar la extensión y esperaron las dependencias finalizar la instalación (consulte la barra de estado) antes de abrir/volver-opening la página de invitación. ¿Sigue teniendo problemas? Consulte [combinar manualmente](../reference/manual-join.md) para obtener más información.

## <a name="5-collaborate"></a>5. ¡Colaborar!

Ya está. En unos instantes, se conectará a la sesión de colaboración de su colega. De forma predeterminada, el host de aceptación automática las personas que unirse, pero si el host está configurado para [requieren la aprobación de invitado](../reference/security.md#requiring-guest-approval) se ve la barra de estado / unir mención del cuadro de diálogo que está esperando Live Share en el host para aprobar su solicitud para unirse.

> **Sugerencia de seguridad:** Como invitado participar en una sesión de colaboración, es importante comprender que los hosts pueden limitar su acceso a determinados archivos o las características. ¿Desea comprender las implicaciones de seguridad de algunas de las características y la configuración de Live Share? Consulte la [seguridad](../reference/security.md) artículo.

Estos son algunos aspectos que debe probar:

1. Moverse por el proyecto de forma independiente y realizar algunas modificaciones
2. Consulte trabajo intellisense para JavaScript, TypeScript, o C# código
3. Editar algo junto con el host
4. Siga el host y para desplazarse por con ellos, ya que navegan y realizar modificaciones en archivos diferentes
5. Iniciar una sesión de depuración conjuntamente con el host
6. Solicite al host que comparten un servidor para que pueda buscar algo como una aplicación web que se ejecutan en su equipo
7. Solicite al host que comparten un terminal y ejecutar algunos comandos

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).

## <a name="next-steps"></a>Pasos siguientes

Consulte estos artículos adicionales para obtener más información.

- [Inicio rápido: Comparta su primer proyecto](share.md)
- [Cómo: Colaborar mediante Visual Studio Code](../use/vscode.md)
- [Cómo: Colaborar mediante Visual Studio](../use/vs.md)

Referencia

- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)
- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Compatibilidad con extensiones](../reference/extensions.md)
