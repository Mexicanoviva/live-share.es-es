---
title: 'Inicio rápido de participación: Visual Studio Live Share | Microsoft Docs'
description: Un tutorial resumido sobre cómo unirse a la primera sesión de colaboración de Visual Studio Live Share.
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
ms.openlocfilehash: c5c86b158facfe1fe8fa7f5ae14a9511c55e0877
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58853552"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>Inicio rápido: Unirse a la primera sesión de colaboración

Le damos la bienvenida a Visual Studio Live Share. Live Share le permite editar y depurar en colaboración con otros usuarios en tiempo real, independientemente del lenguaje de programación que use o los tipos de aplicaciones que compile. Permite unirse al instante y de forma segura al proyecto actual de un compañero de equipo y, después, según sea necesario, entrar en sesiones de depuración, ver y modificar instancias del terminal, ver aplicaciones web de host local, participar en llamadas de voz y mucho más.

¿A punto para comenzar? La colaboración en equipo debería ser tan rápida y natural que resulta difícil no hacerlo. Por este motivo, Visual Studio Live Share simplifica los primeros pasos, para que pueda empezar a compartir sus ideas y su trabajo sin problemas.

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

Siga estos pasos para participar en una sesión de colaboración.

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
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Instale <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Instale una <a href="../reference/platform-support.md">carga de trabajo compatible</a>. (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).<br />
        3. Visual Studio Live Share se instala de forma predeterminada con esas cargas de trabajo. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017, versión 15.6 o posterior</strong><br />
        1. Instale la versión más reciente de <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6 y versiones posteriores) en Windows (7, 8.1 o 10).<br/>
        2. Instale una <a href="../reference/platform-support.md">carga de trabajo compatible</a>. (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).<br />
        3. Descargue e instale la extensión de Visual Studio Live Share desde Marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](../troubleshooting.md).

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [Opcional] Participación como invitado de solo lectura en VS Code

En VS Code, después de instalar la extensión Live Share, reiniciar y esperar a que se terminen de instalar las dependencias, puede participar en una sesión de colaboración como invitado de solo lectura.

> [!NOTE]
> Si quiere realizar modificaciones en el código al que se va a unir, tendrá que iniciar sesión.

Abra (o vuelva a abrir) el vínculo de invitación en un explorador, y recibirá una notificación en la que se indica que el explorador quiere iniciar VS Code. Deje que se inicie y empezará a conectarse a la sesión de colaboración.

Cuando se inicie VS Code, recibirá una notificación en la que se le solicita que inicie sesión. Haga clic en "Continuar como invitado de solo lectura" para unirse a la sesión.

![Notificación del sistema para unirse a la sesión como invitado de solo lectura](../media/vscode-read-only-guest.png)

Se le pedirá que escriba un nombre para mostrar para ayudar a los participantes a identificarle en la sesión.

![Nombre de invitado de solo lectura](../media/vscode-read-only-guest-name.png)

Después, se unirá a la sesión como invitado de solo lectura. Podrá ver y navegar por el código, depurarlo de forma conjunta y ver los servidores y terminales compartidos (solo lectura).

> [!NOTE]
> Si más adelante quiere obtener acceso de lectura o escritura al código, puede iniciar sesión. Haga clic en el nombre para mostrar en la barra de estado y seleccione la opción "Iniciar sesión".
![Inicio de sesión de invitado de solo lectura](../media/vscode-read-only-guest-signin.png) Esto iniciará el explorador, y podrá elegir una cuenta de Microsoft o GitHub con la que iniciar sesión.

## <a name="3-sign-in"></a>3. Inicio de sesión

Después de instalar la extensión Live Share, reiniciar y esperar a que se terminen de instalar las dependencias (VS Code), le recomendamos que inicie sesión para que otros participantes sepan quién es. Si omite este paso, se le pedirá que inicie sesión durante el proceso de unión, o puede unirse a la sesión como un invitado de solo lectura. Haga clic en el elemento "Live Share" de la barra de estado (VS Code) o en el botón "Iniciar sesión" (VS) para empezar.

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

En **VS Code**, se iniciará el explorador mientras aparece una notificación en la que se le pide que inicie sesión. Complete el proceso de inicio de sesión en el explorador, y después ciérrelo cuando haya terminado.

![Notificación del sistema en la que solicita el inicio de sesión con un explorador web](../media/vscode-sign-in-toast.png)

> **Usuarios de Linux:** Se le pedirá que escriba un código de usuario si usa una versión antigua de Live Share (versión 0.3.295 o inferior). Actualice a la versión más reciente de la extensión o haga clic en el vínculo "¿Tiene problemas?" después de iniciar sesión para ver el código. Vea [esto para obtener más detalles](../use/vscode.md#sign-in-using-a-user-code).

En **Visual Studio**, Live Share usa la [cuenta de personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) de forma automática. Como resultado, solo tiene que iniciar sesión como lo haría normalmente. Pero si prefiere usar un inicio de sesión diferente al de la cuenta de personalización de Visual Studio, vaya a **Herramientas &gt; Opciones &gt; Live Share &gt; Cuenta de usuario** y seleccione otras credenciales.

Vea [Solución de problemas](../troubleshooting.md#sign-in) si se sigue teniendo problemas.

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Apertura o reapertura del vínculo de invitación en un explorador

Ahora, basta con abrir (o volver a abrir) el vínculo de invitación en un explorador.

> **Nota**: Si aún no ha instalado la extensión Live Share, se le mostrarán vínculos al Marketplace de la extensión. Instale la extensión, reinicie la herramienta e inténtelo de nuevo.

Debería recibir una notificación en la que se indica que el explorador quiere iniciar una herramienta habilitada para Live Share. Si permite que inicie la herramienta seleccionada, se conectará a la sesión de colaboración una vez que se inicie.

![Página para participar](../media/join-page.png)

Si el host está sin conexión, se le notificará en este momento. Después, puede ponerse en contacto con el host y pedirle que vuelva a compartir.

> **Sugerencia de solución de problemas:** Cuando use VS Code, asegúrese de que ha **iniciado la herramienta al menos una vez** después de instalar la extensión y que ha esperado a que las dependencias terminen de instalarse (mire la barra de estado) antes de abrir o volver a abrir la página de la invitación. ¿Sigue teniendo problemas? Vea [Participar en una sesión manualmente](../reference/manual-join.md) para obtener más información.

## <a name="5-collaborate"></a>5. Colaboración

Ya está. En unos instantes, se conectará a la sesión de colaboración de su colega. De forma predeterminada, el host acepta automáticamente a los usuarios que se unen, pero si el host está configurado para [requerir la aprobación del invitado](../reference/security.md#requiring-guest-approval), verá que en la barra de estado o el cuadro de diálogo se menciona que Live Share está esperando a que el host apruebe su solicitud para unirse.

> **Sugerencia de seguridad:** Como invitado que participa en una sesión de colaboración, es importante comprender que los hosts pueden limitar el acceso a determinados archivos o características. ¿Quiere conocer las implicaciones de seguridad de algunas de las características y configuraciones de Live Share? Consulte el artículo sobre [seguridad](../reference/security.md).

Estas son algunas operaciones que puede probar:

1. Desplácese por el proyecto de forma independiente y realice algunas modificaciones.
2. Compruebe el funcionamiento de IntelliSense para código de JavaScript, TypeScript o C#.
3. Modifique algo junto con el host.
4. Siga al host y desplácese con él mientras navega y realiza cambios en diferentes archivos.
5. Inicie una sesión de depuración conjunta con el host.
6. Pídale al host que comparta un servidor para que pueda extraer del repositorio algo como una aplicación web que se ejecute en el equipo.
7. Pídale al host que comparta un terminal y ejecute algún comando.

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).

## <a name="next-steps"></a>Pasos siguientes

Consulte estos artículos adicionales para obtener más información.

- [Inicio rápido: Uso compartido de un primer proyecto](share.md)
- [Colaboración mediante Visual Studio Code](../use/vscode.md)
- [Colaboración mediante Visual Studio](../use/vs.md)

Referencia

- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)
- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Compatibilidad con extensiones](../reference/extensions.md)
