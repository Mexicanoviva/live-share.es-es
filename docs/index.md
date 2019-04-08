---
title: 'Información general: Visual Studio Live Share | Microsoft Docs'
description: Información general sobre Visual Studio Live Share y sus funcionalidades.
ms.custom: ''
ms.date: 04/26/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5f67086e9040a477e082cbd3ef27a1789c6406c5
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58853591"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>¿Qué es Visual Studio Live Share?

Le damos la bienvenida a Visual Studio Live Share. Live Share le permite editar y depurar en colaboración con otros usuarios en tiempo real, independientemente del lenguaje de programación que use o los tipos de aplicaciones que compile. Asimismo, permite compartir al instante y de forma segura su proyecto actual y, después, según sea necesario, compartir las sesiones de depuración, las instancias del terminal, las aplicaciones web de host local, las llamadas de voz y mucho más.

A diferencia de la programación en pareja tradicional, Visual Studio Live Share permite a los desarrolladores trabajar de forma conjunta conservando sus preferencias personales del editor (por ejemplo, el tema o los enlaces de teclado) y tener su propio cursor. Esto le permite realizar la transición sin problemas entre una y otra, y ofrece la posibilidad de explorar las ideas y las tareas por su cuenta. En la práctica, esta capacidad para trabajar de forma conjunta _e_ independiente proporciona una experiencia de colaboración que es potencialmente más natural para muchos casos de uso comunes.

¿A punto para comenzar? En este artículo veremos algunos conceptos y cómo instalar las extensiones necesarias. Si está buscando una versión resumida, consulte las guías de inicio rápido sobre [uso compartido](quickstart/share.md) y [combinación](quickstart/join.md).

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

## <a name="install-visual-studio-live-share"></a>Instalación de Visual Studio Live Share

Antes de comenzar, deberá asegurarse de tener instalada una versión de Visual Studio o Visual Studio Code que cumpla los requisitos principales de Live Share.

- **Visual Studio Code versión 1.22.0 o una versión posterior** - Windows 7, 8.1 o 10, macOS *(Sierra 10.12 y versiones posteriores únicamente)*, Linux de 64 bits *(se recomienda Ubuntu Desktop 16.04 de 64 bits y Fedora 27 o versiones posteriores - [ver detalles](use/vscode.md#installation))*.
- **Visual Studio 2019** (cualquier edición) - Windows 7, 8.1 o 10.
- **Visual Studio 2017 15.6 o una versión posterior** (cualquier edición) - Windows 7, 8.1 o 10.

Después, descargar e instalar la extensión de Visual Studio Live Share es muy sencillo:

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0 y versiones posteriores)</strong><br />
        1. Instale <a href="https://code.visualstudio.com/">Visual Studio Code</a> para Windows (7, 8.1 o 10), macOS <b>(Sierra y versiones posteriores)</b> o Linux de 64 bits <b>(<a href="use/vscode.md#installation">detalles</a>)</b>.<br />
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
        2. Instale una <a href="reference/platform-support.md">carga de trabajo compatible</a>. (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).<br />
        3. Visual Studio Live Share se instala de forma predeterminada con esas cargas de trabajo. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017, versión 15.6 o posterior</strong><br />
        1. Instale la versión más reciente de <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6 y versiones posteriores) en Windows (7, 8.1 o 10).<br/>
        2. Instale una <a href="reference/platform-support.md">carga de trabajo compatible</a>. (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).<br />
        3. Descargue e instale la extensión de Visual Studio Live Share desde Marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](troubleshooting.md).

Así de simple. Ahora debería ver una barra de estado de inicio de sesión en la parte inferior izquierda en VS Code y un botón Compartir en la esquina superior derecha de Visual Studio. Eche un vistazo al resto de la documentación para saber qué hacer a continuación.

## <a name="concepts-and-features"></a>Conceptos y características

Al igual que con cualquier producto, Visual Studio Live Share proporciona un conjunto de características muy útiles creadas a partir de algunos conceptos básicos. Esta sección le ofrece algunos conceptos y un breve paseo por las características.

### <a name="collaboration-sessions"></a>Sesiones de colaboración

Todas las actividades de colaboración en Visual Studio Live Share implican un único **anfitrión de la sesión de colaboración** y uno o varios **invitados**. El anfitrión es la persona que inicia la sesión de colaboración, mientras que las personas que participan en ella son invitados.

Los anfitriones de las sesiones de colaboración pueden usar todas sus herramientas y servicios, pero a los invitados solo se les concede acceso a los elementos específicos que el anfitrión ha compartido con ellos. Esto incluye el código, los servidores en ejecución, la depuración de sesiones, los terminales y mucho más. Actualmente todo el contenido que se comparte se mantiene en la máquina del anfitrión y no se sincroniza con la nube ni el equipo del invitado, lo que permite el _acceso instantáneo_ y _mayor seguridad_. La ventaja es que toda la solución está disponible en el momento en el que un invitado se une y, cuando un anfitrión finaliza una sesión de colaboración, el contenido deja de estar disponible. Además, los archivos temporales creados por el IDE o el editor para mejorar el rendimiento para el invitado se limpian automáticamente cuando finaliza la sesión.

#### <a name="sharing"></a>Uso compartido de recursos

Al "compartir" como anfitrión, inicia una sesión de colaboración que comparte el contenido de un proyecto, una solución o una carpeta. Los invitados obtienen acceso a este contenido mediante el vínculo de invitación que les envía. Mientras que "compartir" es una abreviatura de "compartir un proyecto", también abre la puerta a compartir otras funcionalidades como la depuración.

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-project) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-project)

#### <a name="joining"></a>Combinación

Al hacer clic en un vínculo de invitación enviado por un anfitrión, puede "unirse" a una sesión de colaboración como invitado y acceder a cualquier contenido o funcionalidad que el anfitrión haya optado por compartir. El vínculo web proporciona una forma rápida de entrar a una sesión de colaboración, si ya tiene instalada la extensión, y una forma rápida de configurar la información, si no la tiene.

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#join-a-collaboration-session) [![VS](media/vs-icon-15x15.png)](use/vs.md#join-a-collaboration-session)

### <a name="features"></a>Características

#### <a name="co-editing"></a>Edición conjunta

Cuando abre el mismo archivo que otro colaborador, es posible "editar en colaboración" o "coeditar" al instante el contenido del archivo. Puede ver las modificaciones de cada colaborador, sus cursores y selecciones, y mucho más. Es más, no es necesario editar el mismo archivo en todo momento, por lo que puede colaborar cuando considere y actuar con independencia, como prefiera.

> [!NOTE]
> La coedición tiene algunas limitaciones. Consulte la [información sobre compatibilidad con la plataforma](reference/platform-support.md) para ver el estado de las características por lenguaje.

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-editing) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-editing)

#### <a name="following-and-focusing"></a>Seguimiento y atención

En ocasiones necesitará explicar un problema o diseño que abarque varios archivos o ubicaciones en el código. En estos casos, puede ser útil seguir temporalmente a un compañero de trabajo mientras se mueve por el proyecto al coeditar. Por este motivo, como invitado, cuando se une a una sesión de colaboración, automáticamente "sigue" la ubicación de edición del anfitrión. Los anfitriones e invitados pueden empezar o dejar de seguirse con un simple clic. Además, puede que quiera pedir a todos los participantes que le sigan. Live Share le permite solicitar que todo el mundo "centre" su atención en usted con una notificación que les facilita la tarea de seguirle.

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#following) [![VS](media/vs-icon-15x15.png)](use/vs.md#following)

#### <a name="co-debugging"></a>Depuración conjunta

Al depurar problemas o errores de codificación difíciles, puede ser muy útil tener un par de ojos adicional. Como anfitrión, Live Share habilita automáticamente la "depuración colaborativa" o la "depuración conjunta" al compartir la sesión de depuración con todos los invitados. Cada uno puede obtener las características de coedición junto con la capacidad de investigar por separado mientras avanzan juntos.

> [!NOTE]
> Consulte la [información sobre compatibilidad con la plataforma](reference/platform-support.md) para ver el estado de las características de depuración por lenguaje o plataforma.

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-debugging) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>Uso compartido de servidores y puertos

Al depurar conjuntamente, puede ser muy útil obtener acceso a diferentes partes de la aplicación ofrecidas por el anfitrión para la sesión de depuración. Puede que quiera acceder a la aplicación en un explorador, acceder a una base de datos local o alcanzar un punto de conexión REST desde sus herramientas. Live Share le permite "compartir un servidor", lo cual asigna un puerto local en la máquina del anfitrión en exactamente el mismo puerto de la máquina de cada invitado. Luego, como invitado, puede interactuar con la aplicación como si se estuviera ejecutando localmente en su máquina (por ejemplo, tanto el anfitrión como el invitado pueden acceder a una aplicación web que se ejecute en http://localhost:3000).

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-server) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-server)

#### <a name="share-terminals"></a>Uso compartido de terminales

El desarrollo moderno hace un uso frecuente de una amplia gama de herramientas de línea de comandos. Afortunadamente, como anfitrión, Live Share le permite, de forma opcional, "compartir un terminal" con los invitados. El terminal compartido puede ser de solo lectura o totalmente colaborativo, para que tanto usted como sus invitados puedan ejecutar comandos y ver los resultados. Como anfitrión, siempre tiene el control y puede decidir si los otros colaboradores pueden ejecutar comandos o solo ver la salida del comando. De hecho, puede ejecutar cualquier cosa que quiera mantener privada en un terminal no compartido.

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-terminal) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-terminal)

#### <a name="access-controls"></a>Controles de acceso

Visual Studio Live Share proporciona a los participantes excelentes maneras de colaborar. Pero con la cantidad de opciones y la flexibilidad que se proporciona a los invitados para interactuar con los anfitriones, es posible que quiera aprobar explícitamente a los invitados que se unen o bloquear el acceso a determinados archivos o carpetas. Live Share tiene una serie de opciones de configuración que pueden serle útiles, como el valor de solo lectura y requerir la aceptación de los invitados.

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](reference/security.md) [![VS](media/vs-icon-15x15.png)](reference/security.md)

#### <a name="flexible-connection-modes"></a>Modos de conexión flexibles

Para garantizar un rendimiento óptimo, Visual Studio Live Share admite dos "modos de conexión" básicos: "directo" y "retransmisión". En el modo directo, los invitados se conectan directamente al anfitrión sin pasar por la red. El modo de retransmisión permite que los invitados que se encuentren en una red completamente diferente se conecten al anfitrión a través de una retransmisión de Internet. En todos los casos, las conexiones son SSH o SSL cifradas para garantizar que solo los colaboradores tengan acceso a lo que está pasando a través de la conexión. De forma predeterminada, Live Share está en modo "automático", que primero intenta una conexión directa y, después, conmuta por error la retransmisión. En cualquier caso, si lo prefiere, puede dejarlo en un modo único.

**Más información:** [![VS Code](media/vscode-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode) [![VS](media/vs-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode)

## <a name="see-also"></a>Vea también

Guías de inicio rápido

- [Uso compartido de un primer proyecto](quickstart/share.md)
- [Participación en una primera sesión](quickstart/join.md)

Temas procedimentales

- [mediante Visual Studio Code](use/vscode.md)
- [mediante Visual Studio](use/vs.md)

Referencia

- [Requisitos de conectividad de Live Share](reference/connectivity.md)
- [Características de seguridad de Live Share](reference/security.md)
- [Compatibilidad con lenguajes y plataformas](reference/platform-support.md)
- [Compatibilidad con extensiones](reference/extensions.md)
- [Notas de la versión](https://aka.ms/vsls-releases)

¿Tiene algún problema? Consulte la [solución de problemas](troubleshooting.md) o [envíe sus comentarios](support.md).
