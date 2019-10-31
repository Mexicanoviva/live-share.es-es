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
ms.openlocfilehash: 8091a7ba5cf1f57f192ecea18da4473c8fdd99f7
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179954"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->
# <a name="live-share-features-and-concepts"></a>Live Share características y conceptos 

Live Share se crea con la arquitectura y los conceptos revolucionarios que se manifiestan como características eficaces para nuestros usuarios. A continuación encontrará todas las características distintivas de Live Share y lo convierte en líder en el espacio de colaboración. 

### <a name="collaboration-sessions"></a>Sesiones de colaboración

Todas las actividades de colaboración en Visual Studio Live Share implican un único **anfitrión de la sesión de colaboración** y uno o varios **invitados**. El anfitrión es la persona que inicia la sesión de colaboración, mientras que las personas que participan en ella son invitados.

Los anfitriones de las sesiones de colaboración pueden usar todas sus herramientas y servicios, pero a los invitados solo se les concede acceso a los elementos específicos que el anfitrión ha compartido con ellos. Esto incluye el código, los servidores en ejecución, la depuración de sesiones, los terminales y mucho más. Actualmente todo el contenido que se comparte se mantiene en la máquina del anfitrión y no se sincroniza con la nube ni el equipo del invitado, lo que permite el _acceso instantáneo_ y _mayor seguridad_. La ventaja es que toda la solución está disponible en el momento en el que un invitado se une y, cuando un anfitrión finaliza una sesión de colaboración, el contenido deja de estar disponible. Además, los archivos temporales creados por el IDE o el editor para mejorar el rendimiento para el invitado se limpian automáticamente cuando finaliza la sesión.

#### <a name="sharing"></a>Uso compartido de recursos

Al "compartir" como anfitrión, inicia una sesión de colaboración que comparte el contenido de un proyecto, una solución o una carpeta. Los invitados obtienen acceso a este contenido mediante el vínculo de invitación que les envía. Mientras que "compartir" es una abreviatura de "compartir un proyecto", también abre la puerta a compartir otras funcionalidades como la depuración.

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project) a

#### <a name="joining"></a>Combinación

Al hacer clic en un vínculo de invitación enviado por un anfitrión, puede "unirse" a una sesión de colaboración como invitado y acceder a cualquier contenido o funcionalidad que el anfitrión haya optado por compartir. El vínculo web proporciona una forma rápida de entrar a una sesión de colaboración, si ya tiene instalada la extensión, y una forma rápida de configurar la información, si no la tiene.

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#join-a-collaboration-session) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#join-a-collaboration-session) a

### <a name="features"></a>Características

#### <a name="co-editing"></a>Edición conjunta

Cuando abre el mismo archivo que otro colaborador, es posible "editar en colaboración" o "coeditar" al instante el contenido del archivo. Puede ver las modificaciones de cada colaborador, sus cursores y selecciones, y mucho más. Es más, no es necesario editar el mismo archivo en todo momento, por lo que puede colaborar cuando considere y actuar con independencia, como prefiera.

> [!NOTE]
> La coedición tiene algunas limitaciones. Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características por lenguaje.

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-editing) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-editing) a

#### <a name="following-and-focusing"></a>Seguimiento y atención

En ocasiones necesitará explicar un problema o diseño que abarque varios archivos o ubicaciones en el código. En estos casos, puede ser útil seguir temporalmente a un compañero de trabajo mientras se mueve por el proyecto al coeditar. Por este motivo, como invitado, cuando se une a una sesión de colaboración, automáticamente "sigue" la ubicación de edición del anfitrión. Los anfitriones e invitados pueden empezar o dejar de seguirse con un simple clic. Además, puede que quiera pedir a todos los participantes que le sigan. Live Share le permite solicitar que todo el mundo "centre" su atención en usted con una notificación que les facilita la tarea de seguirle.

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#following) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#following) a

#### <a name="co-debugging"></a>Depuración conjunta

Al depurar problemas o errores de codificación difíciles, puede ser muy útil tener un par de ojos adicional. Como anfitrión, Live Share habilita automáticamente la "depuración colaborativa" o la "depuración conjunta" al compartir la sesión de depuración con todos los invitados. Cada uno puede obtener las características de coedición junto con la capacidad de investigar por separado mientras avanzan juntos.

> [!NOTE]
> Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características de depuración por lenguaje o plataforma.

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging) a

#### <a name="share-server--share-port"></a>Uso compartido de servidores y puertos

Al depurar conjuntamente, puede ser muy útil obtener acceso a diferentes partes de la aplicación ofrecidas por el anfitrión para la sesión de depuración. Puede que quiera acceder a la aplicación en un explorador, acceder a una base de datos local o alcanzar un punto de conexión REST desde sus herramientas. Live Share le permite "compartir un servidor", lo cual asigna un puerto local en la máquina del anfitrión en exactamente el mismo puerto de la máquina de cada invitado. Luego, como invitado, puede interactuar con la aplicación como si se estuviera ejecutando localmente en su máquina (por ejemplo, tanto el anfitrión como el invitado pueden acceder a una aplicación web que se ejecute en http://localhost:3000).

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server) a

#### <a name="share-terminals"></a>Uso compartido de terminales

El desarrollo moderno hace un uso frecuente de una amplia gama de herramientas de línea de comandos. Afortunadamente, como anfitrión, Live Share le permite, de forma opcional, "compartir un terminal" con los invitados. El terminal compartido puede ser de solo lectura o totalmente colaborativo, para que tanto usted como sus invitados puedan ejecutar comandos y ver los resultados. Como anfitrión, siempre tiene el control y puede decidir si los otros colaboradores pueden ejecutar comandos o solo ver la salida del comando. De hecho, puede ejecutar cualquier cosa que quiera mantener privada en un terminal no compartido.

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal) a

#### <a name="access-controls"></a>Controles de acceso

Visual Studio Live Share proporciona a los participantes excelentes maneras de colaborar. Pero con la cantidad de opciones y la flexibilidad que se proporciona a los invitados para interactuar con los anfitriones, es posible que quiera aprobar explícitamente a los invitados que se unen o bloquear el acceso a determinados archivos o carpetas. Live Share tiene una serie de opciones de configuración que pueden serle útiles, como el valor de solo lectura y requerir la aceptación de los invitados.

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../reference/security.md) [![frente](../media/vs-icon-15x15.png)](../reference/security.md) a

#### <a name="flexible-connection-modes"></a>Modos de conexión flexibles

Para garantizar un rendimiento óptimo, Visual Studio Live Share admite dos "modos de conexión" básicos: "directo" y "retransmisión". En el modo directo, los invitados se conectan directamente al anfitrión sin pasar por la red. El modo de retransmisión permite que los invitados que se encuentren en una red completamente diferente se conecten al anfitrión a través de una retransmisión de Internet. En todos los casos, las conexiones son SSH o SSL cifradas para garantizar que solo los colaboradores tengan acceso a lo que está pasando a través de la conexión. De forma predeterminada, Live Share está en modo "automático", que primero intenta una conexión directa y, después, conmuta por error la retransmisión. En cualquier caso, si lo prefiere, puede dejarlo en un modo único.

Más **información:** [![vs Code](../media/vscode-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode) [![frente](../media/vs-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode) a
