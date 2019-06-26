---
title: 'Inicio rápido de uso compartido: Visual Studio Live Share | Microsoft Docs'
description: Un tutorial resumido sobre cómo compartir el primer proyecto mediante una sesión de colaboración de Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: e65656c604a9dbc479a03a503fe01d7e2d938072
ms.sourcegitcommit: c702aafb65b0fc43cb210e1bb7340cef48b57f35
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67322801"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>Inicio rápido: Uso compartido de un primer proyecto

Le damos la bienvenida a Visual Studio Live Share. Live Share le permite editar y depurar en colaboración con otros usuarios en tiempo real, independientemente del lenguaje de programación que use o los tipos de aplicaciones que compile. Asimismo, permite compartir al instante y de forma segura su proyecto actual y, después, según sea necesario, compartir las sesiones de depuración, las instancias del terminal, las aplicaciones web de host local, las llamadas de voz y mucho más.

¿A punto para comenzar?  La colaboración en equipo debería ser tan rápida y natural que resulta difícil no hacerlo. Por este motivo, Visual Studio Live Share simplifica los primeros pasos, para que pueda empezar a compartir sus ideas y su trabajo sin problemas.

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

Siga estos pasos para empezar a compartir.
<!--
Change the instructions to Install extension for VS Code and in-tool for VS?
-->
## <a name="1-install-the-extension"></a>1. Instalación de la extensión

La instalación de la extensión es sencilla. Tan solo tiene que seguir estos pasos:

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
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Instale <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Instale una <a href="../reference/platform-support.md">carga de trabajo compatible</a> (por ejemplo, ASP.NET, .NET Core, C++, Python o Node.js).<br />
        3. Visual Studio Live Share se instala de forma predeterminada con esas cargas de trabajo. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017, versión 15.6 o posterior</strong><br />
        1. Instale la versión más reciente de <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6 y versiones posteriores) en Windows (7, 8.1 o 10).<br/>
        2. Instale una <a href="../reference/platform-support.md">carga de trabajo compatible</a> (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).<br />
        3. Descargue e instale la extensión de Visual Studio Live Share desde Marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](../troubleshooting.md).

## <a name="2-sign-in"></a>2. Inicio de sesión

<!--
Re-write the grammar here- run on sentence does not make sense. Change screen shots. There is another way of signing in as well- what if a user goes directly to the start collaboration. 
-->
Después de instalar la extensión Live Share, reiniciar y esperar a que se terminen de instalar las dependencias (VS Code), le recomendamos que inicie sesión para que otros participantes sepan quién es. Haga clic en el elemento "Live Share" de la barra de estado (VS Code) o en el botón "Iniciar sesión" (VS) para empezar.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button-new.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

En **VS Code**, se iniciará el explorador mientras aparece una notificación en la que se le pide que inicie sesión. Complete el proceso de inicio de sesión en el explorador, y después ciérrelo cuando haya terminado.

![Notificación del sistema en la que solicita el inicio de sesión con un explorador web](../media/vscode-sign-in-toast.png)

> **Usuarios de Linux:** Se le pedirá que escriba un código de usuario si usa una versión antigua de Live Share (versión 0.3.295 o inferior). Actualice a la versión más reciente de la extensión o haga clic en el vínculo "¿Tiene problemas?" después de iniciar sesión para ver el código. Vea [esto para obtener más detalles](../use/vscode.md#sign-in-using-a-user-code).

En **Visual Studio**, Live Share usa la [cuenta de personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) de forma automática. Como resultado, solo tiene que iniciar sesión como lo haría normalmente. Pero si prefiere usar un inicio de sesión diferente al de la cuenta de personalización de Visual Studio, vaya a **Herramientas &gt; Opciones &gt; Live Share &gt; Cuenta de usuario** y seleccione otras credenciales.

Vea [Solución de problemas](../troubleshooting.md#sign-in) si se sigue teniendo problemas.

## <a name="3-open-a-folder-project-or-solution"></a>3. Apertura de una carpeta, proyecto o solución

Use el flujo de trabajo normal para abrir una carpeta, proyecto o solución que le gustaría compartir en Visual Studio o Visual Studio Code.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [Opcional] Actualización de archivos ocultos o excluidos

De forma predeterminada, Live Share **oculta** a los invitados los archivos o carpetas a los que se hace referencia en los archivos .gitignore de las carpetas compartidas. **Ocultar** un archivo evita que aparezca en el árbol de archivos del invitado. **Excluir** un archivo aplica una regla más estricta que impide que Live Share lo abra para el invitado en situaciones como Ir a la definición o cuando el archivo se depura paso a paso por instrucciones mientras depura o se "sigue". Si quiere ocultar o excluir otros archivos, puede agregar un archivo **.vsls.json** al proyecto con esta configuración. Vea [Control de la visibilidad y el acceso de archivos](../reference/security.md#controlling-file-access-and-visibility) para obtener más información.

## <a name="5-start-a-collaboration-session"></a>5. Inicio de una sesión de colaboración

<!--
-->
A continuación, simplemente haga clic en "Live Share" dentro de la herramienta y un vínculo de invitación se copiará de forma automática en el Portapapeles.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button-new.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> La primera vez que comparta, es posible que el software de firewall de escritorio le pida que permita que el agente de Live Share abra un puerto. Aceptar esto es totalmente opcional, pero habilita un "modo directo" seguro para mejorar el rendimiento cuando la persona con la que trabaja se encuentra en la misma red que usted. Vea [Cambiar el modo de conexión](../reference/connectivity.md#changing-the-connection-mode) para obtener más información.

## <a name="6-optional-enable-read-only-mode"></a>6. [Opcional] Habilitación del modo de solo lectura

Una vez iniciada la sesión de colaboración, puede establecerla para que sea de solo lectura a fin de evitar que los invitados realicen cambios en el código que se comparte.

Después de compartir, recibirá una notificación en la que se indica que el vínculo de invitación se ha copiado en el Portapapeles. Después, puede seleccionar la opción para hacer que la sesión sea de solo lectura.

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

En **VS Code**, también puede iniciar una sesión de solo lectura desde la pestaña del viewlet de Live Share.

![Notificación del sistema en la que solicita el inicio de sesión con un explorador web](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. Envío del vínculo de invitación a alguien

Envíe el vínculo por correo electrónico, Slack, Skype, etc., a los usuarios que quiera invitar. Abrir el vínculo en un explorador les permite unirse a la sesión de colaboración en la que se comparte el contenido de la carpeta, proyecto o solución que haya abierto. Tenga en cuenta que, dado el nivel de acceso que las sesiones de Live Share pueden proporcionar a los invitados, **solo se debe compartir con usuarios de confianza**, y piense detenidamente en las implicaciones de lo que va a compartir.

> **Sugerencia de seguridad:** ¿Quiere conocer las implicaciones de seguridad de algunas de las características de Live Share? Consulte el artículo sobre [seguridad](../reference/security.md).

Si el invitado al que ha invitado tiene preguntas, en el artículo [Inicio rápido: Unirse a la primera sesión de colaboración](join.md) se proporciona información adicional sobre cómo prepararlo todo para participar como invitado.

## <a name="8-optional-approve-the-guest"></a>8. [Opcional] Aprobación del invitado

De forma predeterminada, los invitados se unen automáticamente a la sesión de colaboración y se le notificará cuando estén listos para trabajar con usted.

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

En su lugar, puede optar por requerir una "aprobación" explícita para todo el que se una. Si tiene esta opción activada, una notificación le pedirá que apruebe a los invitados cuando intenten unirse a la sesión.

Vea [Requerir la aprobación de invitado](../reference/security.md#requiring-guest-approval) para obtener más información sobre cómo activar esta característica.

## <a name="9-collaborate"></a>9. Colaboración

Ya está. Estas son algunas operaciones que se pueden probar después de que se haya unido un invitado:

1. Desplazarse por diferentes archivos del proyecto de forma independiente y realizar algunas modificaciones.
1. Seguir al invitado y observar cómo se desplaza, realiza modificaciones y navega a otros archivos.
1. Iniciar una sesión de depuración conjunta con el invitado.
1. Compartir un servidor para que pueda extraer del repositorio algo como una aplicación web que se ejecute en su equipo.
1. Compartir un terminal y ejecutar algún comando.

Consulte la documentación de las extensiones [Visual Studio Code](../use/vscode.md) y [Visual Studio](../use/vs.md) para obtener información sobre cómo realizar estas acciones y muchas más.

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).

## <a name="next-steps"></a>Pasos siguientes

Consulte estos artículos adicionales para obtener más información.

- [Inicio rápido: Unirse a la primera sesión de colaboración](join.md)
- [Procedimientos para colaborar mediante Visual Studio Code](../use/vscode.md)
- [Procedimientos para colaborar mediante Visual Studio](../use/vs.md)

Referencia

- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)
- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Compatibilidad con extensiones](../reference/extensions.md)
