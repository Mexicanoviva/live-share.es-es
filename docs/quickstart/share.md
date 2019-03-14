---
title: Compartir la Guía de inicio rápido - Visual Studio Live Share | Microsoft Docs
description: Un tutorial resumido sobre el uso compartido de su primer proyecto mediante una sesión de colaboración de Visual Studio Live Share.
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
ms.openlocfilehash: 3596b25dc0d08962d7813f52549dbe6fef4f00a0
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256267"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>Inicio rápido: Comparta su primer proyecto

> **Nota: Visual Studio Live Share está actualmente en versión preliminar. Las características y la experiencia de usuario no son finales.**

Le damos la bienvenida a Visual Studio Live Share. Live Share le permite editar y depurar en colaboración con otros usuarios en tiempo real, independientemente del lenguaje de programación que use o los tipos de aplicaciones que compile. Asimismo, permite compartir al instante y de forma segura su proyecto actual y, después, según sea necesario, compartir las sesiones de depuración, las instancias del terminal, las aplicaciones web de host local, las llamadas de voz y mucho más.

¿A punto para comenzar?  Colaboración en equipo debería ser tan rápido y natural, que resulta difícil para no hacerlo! Por este motivo, Visual Studio Live Share simplifica la introducción, para que puede empezar a compartir su trabajo y las ideas sin problemas.

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

Siga estos pasos para empezar a compartir.

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
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
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

## <a name="2-sign-in"></a>2. Inicio de sesión

Después de instalar la extensión Live Share, reiniciando y esperando las dependencias finalizar la instalación (VS Code), desea iniciar sesión para que otros participantes sepa quién es usted. Simplemente haga clic en el elemento de barra de estado de "Live Share" (VS Code) o "Inicio de sesión" botón (VS) para empezar a trabajar.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
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

## <a name="3-open-a-folder-project-or-solution"></a>3. Abrir una carpeta, proyecto o solución

Use el flujo de trabajo normal para abrir una carpeta, proyecto o solución que le gustaría compartir en Visual Studio o Visual Studio Code.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [Update opcional] oculto o archivos excluidos

De forma predeterminada, Live Share **oculta** los archivos o carpetas que se hace referencia en los archivos .gitignore en las carpetas compartidas de los invitados. **Ocultar** un archivo evita que aparezca en el árbol de archivos de invitado. **Excluir** un archivo aplica una regla más estricta que impide que si lo abre para el invitado en situaciones como ir a definición o si entra en el archivo mientras depura o se "sigue" Live Share. Si desea ocultar o excluir archivos diferentes, una **. vsls.json** archivo se puede agregar al proyecto con esta configuración. Consulte [controlar el acceso de archivo y visibilidad](../reference/security.md#controlling-file-access-and-visibility) para obtener más información.

## <a name="5-start-a-collaboration-session"></a>5. Iniciar una sesión de colaboración

A continuación, simplemente haga clic en "Live Share" dentro de la herramienta y un vínculo de la invitación se copia automáticamente en el Portapapeles.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> Se le pedirá el software de firewall de escritorio para que el agente de compartir en directo abrir un puerto de la primera vez que se comparte. Aceptar esto es totalmente opcional pero permite que un seguro "modo directo" para mejorar el rendimiento cuando es la persona que trabaja en la misma red que sea. Consulte [cambiar el modo de conexión](../reference/connectivity.md#changing-the-connection-mode) para obtener más información.

## <a name="6-optional-enable-read-only-mode"></a>6. [opcional] Activar modo de solo lectura

Una vez que inicie una sesión de colaboración, puede establecer la sesión sea de solo lectura para evitar que los invitados realiza modificaciones en el código que se comparte.

Después de compartir, obtendrá una notificación de que el vínculo de la invitación se ha copiado en el Portapapeles. A continuación, puede seleccionar la opción para que la sesión de solo lectura.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-read-only-toast.png" width="100%" alt="Visual Studio Code read-only option" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-read-only-notification.png" width="100%" alt="Visual Studio read-only option"/>
    </td>
</tr>
</table>

En **VS Code**, también puede iniciar una sesión de solo lectura desde la pestaña de viewlet Live Share.

![Notificación del sistema que pide que inicie sesión con un explorador web](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. Enviar a alguien el vínculo de la invitación

Envíe el vínculo por correo electrónico, Slack, Skype, etc. a los que desea invitar. Abrir el vínculo en un explorador les permite unirse a la sesión de colaboración que comparte el contenido de la carpeta, proyecto o solución que abrió. Tenga en cuenta que, dado el nivel de acceso a Live compartir sesiones pueden proporcionar a los invitados, **solo se debe compartir con usuarios de confianza** y piense detenidamente las implicaciones de lo que va a compartir.

> **Sugerencia de seguridad:** ¿Desea comprender las implicaciones de seguridad de algunas de las características de Live del recurso compartido? Consulte la [seguridad](../reference/security.md) artículo.

Si el invitado le invitó tiene preguntas, el [inicio rápido: Únase a la primera sesión](join.md) artículo proporciona información adicional sobre entre en funcionamiento como invitado.

## <a name="8-optional-approve-the-guest"></a>8. [opcional] aprobar el invitado

De forma predeterminada, los invitados unirse automáticamente join la sesión de colaboración y se le notificará cuando está listos para trabajar con usted.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

Puede optar por requerir una "aprobación" explícita para todo aquel que unirse en su lugar. Si tiene esta opción activada, una notificación le pide que apruebe al invitado cuando intenten unirse a la sesión.

Consulte [que requieren aprobación invitado](../reference/security.md#requiring-guest-approval) para obtener más información sobre cómo activar esta característica.

## <a name="9-collaborate"></a>9. ¡Colaborar!

Ya está. Estas son algunas cosas para probar una vez que ha unido a un invitado:

1. Mover a distintos archivos en el proyecto de forma independiente y realizar algunas modificaciones
1. Siga al invitado y observe como desplazarse, realizar modificaciones y navegar a archivos diferentes
1. Iniciar una sesión de depuración conjunta con ellas
1. Compartir un servidor para que pueda buscar algo como una aplicación web que se ejecutan en su equipo
1. Compartir un terminal y ejecute algunos comandos

Consulte la [Visual Studio Code](../use/vscode.md) y [Visual Studio](../use/vs.md) docs de extensión para obtener información sobre cómo realizar estas acciones y mucho más.

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).

## <a name="next-steps"></a>Pasos siguientes

Consulte estos artículos adicionales para obtener más información.

- [Inicio rápido: Únase a la primera sesión de colaboración](join.md)
- [Cómo: Colaborar mediante Visual Studio Code](../use/vscode.md)
- [Cómo: Colaborar mediante Visual Studio](../use/vs.md)

Referencia

- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)
- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Compatibilidad con extensiones](../reference/extensions.md)
