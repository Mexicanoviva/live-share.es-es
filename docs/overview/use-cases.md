---
title: 'Casos de uso comunes: Visual Studio Live Share | Microsoft Docs'
description: Información general de los casos de uso a los que los desarrolladores se aprovechan normalmente Visual Studio Live Share para.
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 0d328ad39b35ae1c6338825848857342765418d9
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179960"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>Casos de uso comunes

El objetivo principal de Visual Studio Live Share consiste en permitir a los desarrolladores colaborar entre ellos más fácilmente, sin introducir ninguna opinión sobre cuándo y cómo hacerlo (por ejemplo, la herramienta de comunicación que se va a usar, la metodología de software "correcta" o el flujo de trabajo de SCM). De este modo, las herramientas pueden admitir interacciones que se producen de forma **natural**y con tanta **frecuencia** como sea necesario, pero de forma que se **complemente** cómo ya prefiere trabajar.

En este documento se resaltan algunos casos de uso en los que ya se está usando Visual Studio Live Share, y se describe cómo se admiten actualmente y las maneras en las que tenemos pensado optimizarlos (en función de los comentarios). Si usa Live Share para algo que todavía no se ha tratado, o piensa que podemos mejorar para admitir un caso de uso específico, [háganoslo saber](https://github.com/MicrosoftDocs/live-share/issues/new).

- [Asistencia rápida](#quick-assistance)
    - [Horas de oficina](#office-hours)
- [Programación de pares](#pair-programming)
    - [Programación de Mob](#mob-programming)
    - [Codificar competiciones/hack-A-thons](#coding-competitions--hack-a-thons)
    - [Proyectos de grupo School](#school-group-projects)
    - [Streaming para desarrolladores](#developer-streaming)
    - [Creación de prototipos/proyecto](#prototyping--project-inception)
- [Educación interactiva](#interactive-education)
    - [Aprendizaje/incorporación del mismo nivel](#peer-mentoring--onboarding)
    - [Bolsas de equipos Pardo](#team-brown-bags)
    - [Conferencias de Classroom](#classroom-lectures)
- [Revisiones de código](#code-reviews)
- [Entrevistas técnicas](#technical-interviews)

## <a name="quick-assistance"></a>Asistencia rápida

Cuando experimenta un problema (por ejemplo, al intentar resolver un error, al configurar su entorno), puede usar Visual Studio Live Share para buscar información de forma instantánea desde otro equipo del mismo nivel. En muchos casos, no se borra de inmediato el contexto que necesitará la persona que proporciona ayuda y, por lo tanto, Live Share ayuda a facilitar el acceso a todo el proyecto y, si es necesario, compartir incrementalmente más (por ejemplo, un servidor local, de solo lectura terminal). No es necesario enviar fragmentos de código ni mensajes de error en la parte posterior.

Además, como Live Share le permite compartir la sesión de depuración activa, sin requerir "invitados" para instalar cualquiera de los SDK de plataformas necesarios (por ejemplo, node. js, Go, .NET Core) o las extensiones de herramientas, puede ayudarle a obtener una resolución más rápida y a evitar que "no reproducción en mi equipo ". Live Share le permite compartir el estado de depuración con otros usuarios, para cualquier lenguaje de programación o entorno en tiempo de ejecución (por ejemplo, Kubernetes, reAct Native APP) y, con independencia de lo que necesite ayuda, puede compartir.

### <a name="office-hours"></a>Horas de oficina

Muchas empresas e instituciones educativas (por ejemplo, escuelas, cursos de aprendizaje en línea) proporcionan soporte técnico a sus clientes, empleados y estudiantes en momentos predeterminados y, por lo general, con una frecuencia periódica (por ejemplo, todos los viernes de 3-5 PM). De esta manera, las "horas de oficina" son simplemente una forma programada de "asistencia rápida", en lugar de ser completamente ad hoc. Live Share facilita la obtención de ayuda rápidamente, ya que el "experto" que proporciona ayuda puede unirse inmediatamente a una sesión de colaboración y responder a las preguntas, sin necesidad de configurar su equipo.

## <a name="pair-programming"></a>Programación de pares

Uno de los escenarios más usados para Visual Studio Live Share es "programación de pares": dos o más desarrolladores, que trabajan juntos en una tarea compartida, con el objetivo de compartir conocimiento, aumentar la cohesión del equipo y, potencialmente, la calidad del producto. La apariencia y el funcionamiento exactos de la programación de pares pueden diferir significativamente entre equipos y situaciones, en función de lo siguiente (entre otros):

1. El ámbito de la "tarea" en la que se está colaborando (por ejemplo, un error, un caso de usuario).

1. La duración esperada de la sesión de colaboración (por ejemplo, dos minutos, una hora, tiempo completo, una vez a la semana, TBD)

1. El número de personas implicadas (por ejemplo, dos, todo el equipo)

1. El rol de cada participante (por ejemplo, "controlador", observador/revisor, experto en la materia)

1. La proximidad de los participantes (por ejemplo, colocados en el mismo edificio, en todo el mundo)

Live Share se diseñó para ser independiente de todos los problemas mencionados anteriormente y, en su lugar, se esfuerza en admitir la programación de pares que es completamente "oportunista" y que se adapta a su situación. Dicho esto, a diferencia de dos desarrolladores que comparten un solo teclado y pantalla, Live Share habilita una forma de programación de pares que permite a los desarrolladores trabajar en un objetivo compartido sin quitar su autonomía o preferencias de entorno individuales. Puede trabajar de forma independiente o conjunta, lo que permite a cada participante llevar su propio proceso de pensamiento a la colaboración.

Para reducir aún más este caso de uso, los siguientes elementos representan formas de programación de pares que hemos observado que usan Live Share para:

### <a name="mob-programming"></a>Programación de Mob

[Mob Programming](https://en.wikipedia.org/wiki/Mob_programming) (o Swarm Programming) es esencialmente la programación en pares, pero con más de dos personas. Por lo tanto, todas las ventajas de Live Share para la programación de pares también se aplican igualmente. Además, algunos equipos "swarming" según sea necesario (por ejemplo, el equipo rallying en torno a un simulacro) en lugar de tiempo completo.

Actualmente, Live Share admite hasta 30 invitados dentro de una sesión.
> [!TIP]
> Para habilitar 30 invitados en una sesión:
> - **Vs Code:** agregue "LiveShare. increasedGuestLimit": "true" a Settings. JSON
> - **Vs:** Establecer herramientas > Opciones > Live Share > mayor límite de invitados a "true" 

### <a name="coding-competitions--hack-a-thons"></a>Codificar competiciones/hack-A-thons

La codificación de competiciones y hack-a-thons son en realidad variaciones de una sola tarea de la programación Mob. Los miembros del equipo y su rol actual también son potencialmente dinámicos. Puesto que este caso de uso suele ser también dependiente del tiempo, la capacidad de colaborar en tiempo real sin necesidad de adoptar una herramienta completamente nueva y la capacidad de trabajar de forma conjunta, sin tener que limitarse a una sola pantalla o un teclado, puede aumentar el modo de inicio de sesión. Velocity.

Dado que es posible que los participantes de este entorno no siempre sean totalmente "de confianza", puede quitar (y bloquear) un invitado de una sesión en cualquier momento. Esto proporciona "hosts" con control total sobre su entorno.

### <a name="school-group-projects"></a>Proyectos de grupo School

Los proyectos de grupo terminan en gran medida como la programación de Mob, donde varios alumnos trabajan juntos y pueden realizar la transición sin problemas entre centrarse en una sola tarea o trabajar en tareas independientes simultáneamente. En lugar de confiar simplemente en el control de versiones para colaborar de forma asincrónica, pueden usar Live Share para trabajar juntos en tiempo real, lo que puede ayudar a las ventajas sociales y educativas de trabajar en un grupo.

### <a name="developer-streaming"></a>Streaming para desarrolladores

La transmisión por secuencias del desarrollador (a través de Twitch o Mixer) se ha convertido en una nueva forma atractiva de educación. Aunque Live Share no está diseñado para reemplazar sus plataformas de difusión (aunque hemos escuchado la solicitud!), proporciona un medio para que el host empareje el programa con uno o más invitados y, después, transmite esa interacción. De este modo, los visores pueden obtener más información al ver el proceso natural de interacción y pensamiento de dos o más desarrolladores, que podrían incluso trabajar juntos en sistemas operativos e IDE completamente independientes.

### <a name="prototyping--project-inception"></a>Creación de prototipos/proyecto

Cuando un equipo está iniciando un nuevo proyecto o microservicio, o creando prototipos y picosndo una nueva característica, a menudo puede ser útil colaborar juntos para agilizar el progreso y explorar nuevas ideas. Dado que el código base recién creado podría no confirmarse todavía en un repositorio compartido, Live Share permite que todos participen en el proceso iterativo, independientemente de si están en la misma oficina o no.

## <a name="interactive-education"></a>Educación interactiva

Por lo general, Live Share pretende ayudar a los desarrolladores a compartir conocimientos entre su equipo. Education es un caso de uso fundamental para Live Share y lo admite especialmente bien al permitir que cada participante interactúe con el código base en el que se está colaborando, en lugar de simplemente ver una pantalla. Todo el mundo aprende de maneras diferentes y, por lo tanto, al proporcionar independencia a un "estudiante", puede aprovechar las ventajas de la instrucción que se proporciona, sin tener que sacrificar su capacidad de explorar sus propias ideas a lo largo del proceso.

### <a name="peer-mentoring--onboarding"></a>Aprendizaje/incorporación del mismo nivel

Al introducir un desarrollador en un nuevo código base, área de características, tecnología, etc. puede usar Live Share para guiarle a través del proyecto (con `Follow Mode`), de modo que puedan seguir con usted, pero desde su propio IDE personal. Como Live Share permite a "invitados" navegar de forma independiente por el proyecto (por ejemplo, abrir un archivo, realizar una `Peek Definition`), puede seguir permitir, pero también realizar exploraciones rápidas según sea necesario (por ejemplo, "Hmm, ¿qué hace esta función?").

### <a name="team-brown-bags"></a>Bolsas de equipos Pardo

En realidad, los sacos del equipo son similares a la mentorización del mismo nivel, pero se presentan a todo un equipo y, potencialmente, se centran en la información sobre la configuración de redes sociales en general, en contraposición a la compatibilidad con la incorporación o a la ayuda con una tarea específica.

### <a name="classroom-lectures"></a>Conferencias de Classroom

Cuando los instructores enseñan una lección, pueden usar Live Share para compartir su proyecto con estudiantes, en lugar de simplemente presentar su pantalla. Esto permite que la clase completa siga junto con el profesor, mientras que puede interactuar con el proyecto por sí mismo. Además, el profesor puede pedir a los estudiantes individuales que le ayuden a resolver una parte determinada de la lección (por ejemplo, "¿Qué método debería llamar aquí?"), que puede ayudar en los aspectos sociales de la clase, sin necesidad de que los estudiantes se recorran hasta el principio del salón. , o incluso estar presentes físicamente en la misma habitación (por ejemplo, cursos en línea).

Para ayudar en la configuración del aula, Live Share habilita el uso compartido en modo de solo lectura. Los instructores pueden utilizar el modo de solo lectura para permitirles compartir sus proyectos con estudiantes sin tener que preocuparse de las modificaciones innecesarias o accidentales que se realicen.

Además, Live Share tiene compatibilidad para permitir hasta 30 invitados que se unen a una sesión de colaboración. De esta manera, los instructores pueden tener su propia clase JOIN en una sesión y ver el código juntos.

Para habilitar esta característica:

- **Vs Code:** Agregue "LiveShare. increasedGuestLimit": "true" a Settings. JSON.
- **Vs:** Establecer herramientas > Opciones > Live Share > mayor límite de invitados a "true"

Para optimizar completamente Live Share para este escenario, es necesario simplificar la forma en que se inician las sesiones ([#422](https://github.com/MicrosoftDocs/live-share/issues/422)).

## <a name="code-reviews"></a>Revisiones de código

Los PR son una manera eficaz de colaborar con otras personas, pero normalmente representan la finalización de una tarea (excepto los PR "WIP") y el deseo de combinarla. Muchas veces, los comentarios que se proporcionan en una solicitud de incorporación de valor se pueden haber facilitado con facilidad y, por lo tanto, es posible que los equipos busquen fácilmente y continuamente consejos de sus compañeros, en lugar de esperar hasta que "completen" una tarea que se va a preguntar.

Puesto que Live Share le permite compartir el proyecto de forma instantánea con otros usuarios, se puede usar para habilitar las revisiones de código/ad-Hocs "informales", donde en lugar de solicitar ayuda, simplemente está buscando datos para asegurarse de que la dirección y el enfoque se alineen con otras personas. Esto puede ayudar a realizar más rápido las operaciones de personalización más rápidas y, de forma definitiva, ayuda a la información social en todo el equipo.

Además, como Live Share le permite compartir un directorio arbitrario, puede usarlo para realizar revisiones de código, incluso si no está usando el control de versiones actualmente (aunque debería hacerlo) o si el equipo no usa PR (por ejemplo, puede realizar el desarrollo basado en troncales).

Live Share no comparte actualmente las diferencias de control de código fuente, que es una parte crítica del contexto cuando se usa para las revisiones de código. Esto está en nuestro mapa de ruta y los comentarios sobre la prioridad se aprecian de forma significativa ([Vote 👍 aquí](https://github.com/MicrosoftDocs/live-share/issues/36)).

## <a name="technical-interviews"></a>Entrevistas técnicas

Al realizar la Intervista de candidatos para una posición del desarrollador, a menudo resulta útil ir más allá de las conversaciones de la pizarra y, en su lugar, observar la resolución de un problema de codificación desde dentro de un IDE real (especialmente si su equipo u organización tiene "estandarizado" en una herramienta que le gustaría verlas. Esto no solo les ofrece la ventaja de trabajar de forma más natural y cómoda (la mayoría de los desarrolladores no codifican en pizarras), sino que también les proporciona comentarios y asistencia inmediatos mientras trabajan (por ejemplo, errores de compilación, IntelliSense). Muchas veces, es más importante comprender el proceso de pensamiento de un candidato, en lugar de su capacidad de memorizar la sintaxis exacta y/o los nombres de API. De este modo, Live Share proporciona una experiencia similar a la de una sesión de programación de pares, pero permite que el participante esté en su propio entorno (incluida la configuración del sistema operativo, como la accesibilidad), y funcionaría igual para las entrevistas locales o remotas.

Además, el desarrollo real es algo más que simplemente escribir código. Dado que Live Share también admite la depuración, las tareas y los terminales compartidos, permite a los intervisores observar candidatos mientras se diagnostica un problema y proporcionarle las herramientas apropiadas necesarias para resolverlo (por ejemplo, paso de depuración, ejecutar pruebas). Puesto que todos los contextos se refieren de forma remota desde el equipo del host, los candidatos pueden pasar rápidamente al "entorno de entrevistas" sin necesidad de configurar su equipo (más allá de instalar Live Share). Después, los equipos pueden mantener un repositorio de aplicaciones de intervistas compartidas (o usar su código base real del producto), que podría clonarse y compartirse con los candidatos, simplemente enviándoles la dirección URL de la sesión antes de cada entrevista.

## <a name="see-also"></a>Vea también

- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
