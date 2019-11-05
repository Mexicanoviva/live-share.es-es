---
title: 'Información general: Visual Studio Live Share | Microsoft Docs'
description: Información general sobre Visual Studio Live Share y sus funcionalidades.
ms.custom: ''
ms.date: 10/30/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 6f46f65a362d4fff46e21a647e4b677a7d45b3e7
ms.sourcegitcommit: ab8a49a163cc89f69ed9f117fb34e25bf0f00ae1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73190680"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>¿Qué es Visual Studio Live Share?

Le damos la bienvenida a Visual Studio Live Share. Live Share le permite editar y depurar en colaboración con otros usuarios en tiempo real, con independencia de los lenguajes de programación que use o los tipos de aplicaciones que compile. Puede compartir al instante y de forma segura el proyecto actual, iniciar una sesión de depuración conjunta, compartir instancias del terminal, reenviar aplicaciones web de host local, realizar llamadas de voz y mucho más.

 A diferencia de la programación en pareja tradicional, Visual Studio Live Share permite a los desarrolladores trabajar de forma conjunta, al tiempo que conservan sus preferencias personales del editor (por ejemplo, el tema o los enlaces de teclado) y tienen su propio cursor. Esto le permite realizar la transición sin problemas entre una y otra, y ofrece la posibilidad de explorar las ideas y las tareas por su cuenta. Esta capacidad de trabajar de forma conjunta e independiente proporciona una experiencia de colaboración que se parece mucho a la colaboración _en persona_.

¿A punto para comenzar? En este artículo veremos algunos conceptos y cómo instalar las extensiones necesarias. Si está buscando una versión resumida, consulte las guías de inicio rápido sobre [uso compartido](quickstart/share.md) y [combinación](quickstart/join.md).

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

## <a name="install-visual-studio-live-share"></a>Instalación de Visual Studio Live Share

Antes de comenzar, deberá asegurarse de tener instalada una versión de Visual Studio o Visual Studio Code que cumpla los requisitos principales de Live Share.

- **Visual Studio Code versión 1.22.0 o una versión posterior** - Windows 7, 8.1 o 10, macOS *(Sierra 10.12 y versiones posteriores únicamente)* , Linux de 64 bits *(se recomienda Ubuntu Desktop 16.04 de 64 bits y Fedora 27 o versiones posteriores - [ver detalles](how-to-guides/vscode.md#installation))* .
- **Visual Studio 2019** (cualquier edición) - Windows 7, 8.1 o 10.
- **Visual Studio 2017 15.6 o una versión posterior** (cualquier edición) - Windows 7, 8.1 o 10.

Después, descargar e instalar la extensión de Visual Studio Live Share es muy sencillo:

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0 y versiones posteriores)</strong><br />
        1. Instale <a href="https://code.visualstudio.com/">Visual Studio Code</a> para Windows (7, 8.1 o 10), macOS <b>(Sierra y versiones posteriores)</b> o Linux de 64 bits <b>(<a href="how-to-guides/vscode.md#installation">detalles</a>)</b>.<br />
        2. Descargue e instale la extensión de Visual Studio Live Share desde Marketplace. <br />
        3. Vuelva a cargar y espere a que las dependencias se descarguen e instalen (consulte la barra de estado).<br />
        4. <strong>Linux</strong>: Si se le pide que <a href="reference/linux.md#install-linux-prerequisites">instale bibliotecas</a>, haga clic en Instalar, escriba la contraseña y reinicie VS Code cuando haya terminado.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Instale <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Instale una <a href="reference/platform-support.md">carga de trabajo compatible</a> (por ejemplo, ASP.NET, .NET Core, C++, Python o Node.js).<br />
        3. Visual Studio Live Share se instala de forma predeterminada con esas cargas de trabajo. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017, versión 15.6 o posterior</strong><br />
        1. Instale la versión más reciente de <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6 y versiones posteriores) en Windows (7, 8.1 o 10).<br/>
        2. Instale una <a href="reference/platform-support.md">carga de trabajo compatible</a> (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).<br />
        3. Descargue e instale la extensión de Visual Studio Live Share desde Marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](troubleshooting.md).

Así de simple. Ahora debería ver una barra de estado de inicio de sesión en la parte inferior izquierda en VS Code y un botón Compartir en la esquina superior derecha de Visual Studio. Eche un vistazo al resto de la documentación para saber qué hacer a continuación.


## <a name="see-also"></a>Vea también

Guías de inicio rápido

- [Uso compartido de un primer proyecto](quickstart/share.md)
- [Participación en una primera sesión](quickstart/join.md)

Temas procedimentales

- [Colaboración mediante Visual Studio Code](how-to-guides/vscode.md)
- [Colaboración mediante Visual Studio](how-to-guides/vs.md)

referencia

- [Requisitos de conectividad de Live Share](reference/connectivity.md)
- [Características de seguridad de Live Share](reference/security.md)
- [Compatibilidad con lenguajes y plataformas](reference/platform-support.md)
- [Compatibilidad con extensiones](reference/extensions.md)
- [Notas de la versión](https://aka.ms/vsls-releases)

¿Tiene algún problema? Consulte la [solución de problemas](troubleshooting.md) o [envíe sus comentarios](support.md).
