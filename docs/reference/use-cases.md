---
title: Casos de uso comunes - Visual Studio Live Share | Microsoft Docs
description: Información general de los casos de uso que los desarrolladores normalmente saca provecho de Visual Studio Live Share para.
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2ef982a00a06cb312cd0270ba65abd308518d99e
ms.sourcegitcommit: c20a6ddef4f184678a2d6cf1a2493d42ea3a4356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2019
ms.locfileid: "57725706"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>Casos de uso comunes

El objetivo principal de Visual Studio Live Share es que los desarrolladores puedan colaborar entre sí con mayor facilidad, sin introducir cualquier opinión sobre cuándo y cómo hacerlo (por ejemplo, la comunicación herramienta, la metodología de software "derecha" o el flujo de trabajo SCM). De este modo, sus herramientas pueden admitir las interacciones que se producen **naturalmente**y como **con frecuencia*según sea necesario, pero de manera que **cortesía*cómo ya prefiere trabajar.

Esta información destacada de documento algunos que ya está en uso para Visual Studio Live Share y describe también cómo actualmente admitimos ellos y las formas de tenemos previsto optimizarlas aún más (en función de los comentarios.) de casos de uso. Si está usando Live Share para algo que ya no está cubierto por debajo, o si piensa que podamos mejorar para admitir un caso de uso específicos, por favor, [háganoslo saber](https://github.com/MicrosoftDocs/live-share/issues/new).

- [Ayuda rápida](#quick-assistance)
    - [Horario de oficina](#office-hours)
- [Programación en pareja](#pair-programming)
    - [Programación Mob](#mob-programming)
    - [Las competiciones de codificación / Hack-A-Thons](#coding-competitions--hack-a-thons)
    - [Proyectos del grupo de School](#school-group-projects)
    - [Desarrollador de transmisión por secuencias](#developer-streaming)
    - [Creación de prototipos / concepción del proyecto](#prototyping--project-inception)
- [Formación interactiva](#interactive-education)
    - [Elemento del mismo nivel tutorías / incorporación](#peer-mentoring--onboarding)
    - [Bolsas marrones del equipo](#team-brown-bags)
    - [Conferencias de aula](#classroom-lectures)
- [Revisiones de código](#code-reviews)
- [Entrevistas técnicas](#technical-interviews)

## <a name="quick-assistance"></a>Ayuda rápida

Cuando surge un problema (por ejemplo, al intentar resolver un error, la configuración del entorno), puede usar Visual Studio Live Share al instante buscar ayuda de otra del mismo nivel. En muchos casos, no está inmediatamente claro qué contexto de la persona que proporciona ayuda necesitará y, por lo tanto, ayuda a compartir Live realizando simple proporcionar acceso a todo el proyecto y if/como sea necesario, incrementalmente comparte más (por ejemplo, un servidor local, de solo lectura Terminal). No es necesario enviar fragmentos de código o a mensajes de error atrás y adelante!

Además, dado que Live compartir le permite compartir la sesión de depuración activa, sin necesidad de utilizar "invitados" instalar cualquiera de los SDK de las plataformas necesarias (p. ej., Node.js, Go, .NET Core), las extensiones de herramientas puede ayudarle obtener resolución más rápida y evitar que "no situaciones de reproducción en mi equipo". Recurso compartido en directo le permite compartir el estado de depuración con otros usuarios, para cualquier entorno de lenguaje o tiempo de ejecución de programación (por ejemplo, Kubernetes, React Native app) e independientemente que qué necesita ayuda, puede compartirlo!

### <a name="office-hours"></a>Horario de oficina

Muchas empresas y a las instituciones educativas (p. ej., escuelas, cursos de aprendizaje en línea) proporcionan soporte técnico para los clientes o empleados o estudiantes en determinar previamente veces y, por lo general en una frecuencia de repetición (por ejemplo, cada viernes de 3-5 P.M.). De este modo, "horario de oficina" es simplemente una forma programada de "rápido asistencia", en lugar de ser completamente ad hoc. Recurso compartido de Live facilita la obtener ayuda rápidamente, ya que la Ayuda que proporciona "experta" inmediatamente puede participar en una sesión de colaboración y responder sus preguntas, sin necesidad de configurar su máquina en absoluto.

## <a name="pair-programming"></a>Programación en pareja

Una de las más usadas escenarios para Visual Studio Live Share es "programación en pareja": dos o más desarrolladores trabajen juntos en una tarea compartida, con el fin de compartir conocimientos, aumentar la cohesión del equipo y, potencialmente, la calidad del producto. El exacto apariencia y el funcionamiento de la programación en pareja puede diferir considerablemente entre los equipos y situaciones, dependiendo de lo siguiente (entre otros):

1. El ámbito de la tarea"" que se han colaborado en (por ejemplo, un error, un caso de usuario)

1. La duración prevista de la sesión de colaboración (por ejemplo, dos minutos, una hora, a tiempo completo, una vez por semana, TBD)

1. El número de personas implicadas (por ejemplo, dos, todo el equipo)

1. El rol de cada participante (p. ej., "controlador", observador/revisor, experto en la materia)

1. La proximidad de los participantes (por ejemplo, ubicado en el mismo edificio, en todo el mundo)

Recurso compartido en vivo se ha diseñado para ser independiente respecto a todos los problemas mencionados anteriormente y en su lugar, se esfuerza por compatibilidad con programación en pareja dirigido a su situación y completamente "oportunista". Dicho esto, a diferencia de los dos desarrolladores compartir un único teclado y pantalla, Live Share permite una forma de par programación que permite a los desarrolladores trabajar en un objetivo compartido, sin quitar su autonomía individual o preferencias de entorno. Puede trabajar de forma independiente o juntos, permitir que cada participante poner su propio proceso de elaboración de para la colaboración.

Para más compatibilidad con programación en pareja y permitir que cada "Invitado" realizar acciones requieren habitualmente, tenemos trabajo en nuestra guía para seguir aumentando el contexto y capacidades que se comparten en una sesión de Live Share: tareas ([40 #](https://github.com/MicrosoftDocs/live-share/issues/40)), salida de la compilación ([#48](https://github.com/MicrosoftDocs/live-share/issues/48)), depuración controlada por el invitado ([#32](https://github.com/MicrosoftDocs/live-share/issues/32)) y mucho más. Háganoslo saber cuáles de estas experiencias son importantes para usted.

Para desglosar en este caso de uso aún más, los elementos siguientes representan formas de par de programación que hemos detectado gente con Live Share para:

### <a name="mob-programming"></a>Programación Mob

[Mob programación](https://en.wikipedia.org/wiki/Mob_programming) (o swarm programación) es esencialmente el par de programación, pero con más de dos personas. Por lo tanto, todas las ventajas de Live Share de programación en pareja se aplican igualmente también. Además, algunos equipos hacer "swarming" según sea necesario (por ejemplo, el equipo rallying alrededor de un simulacro de incendio) en lugar de a tiempo completo.

Actualmente, Live Share admite hasta cinco de los invitados dentro de una sesión, lo que puede o no puede adaptarse a su tamaño del equipo. Sin embargo, esto es algo que pensar en aumentar (para varios casos de uso) y buscan comentarios ([voto 👍 aquí](https://github.com/MicrosoftDocs/live-share/issues/229))

### <a name="coding-competitions--hack-a-thons"></a>Las competiciones de codificación / Hack-A-Thons

Codificación competiciones y hack un thons son variaciones eficazmente a corto plazo, la única tarea de programación mob. Los miembros del equipo y su rol actual, también son potencialmente dinámicos. Puesto que este caso de uso normalmente también está sujeto a limitación temporal, la capacidad de colaborar en tiempo real sin necesidad de adoptar una herramienta completamente nueva y la capacidad de trabajar juntos, sin limitarse a una única pantalla o el teclado, puede ir un modo de registro en aumento velocidad.

Puesto que los participantes en este entorno podrían no ser siempre plena "confianza", hemos oído solicitudes para permitir quitar (y bloqueo) invitado desde una sesión en cualquier momento, que es algo que tenemos previsto habilitar ([#398](https://github.com/MicrosoftDocs/live-share/issues/398)) y es compatible con el objetivo de proporcionar "hosts" con un control completo sobre su entorno.

### <a name="school-group-projects"></a>Proyectos del grupo de School

Agrupar los proyectos ralo parece mucho a la programación mob, donde varios alumnos están trabajando juntos y puede realizar la transición sin problemas entre centrándose en una sola tarea o trabajando en tareas independientes al mismo tiempo. En lugar de depender únicamente de control de versiones para colaborar de forma asincrónica, puede usar Live de Share a colaborar tiempo real, que pueden ayudar a las ventajas de trabajar en un grupo de redes sociales y educativas.

### <a name="developer-streaming"></a>Desarrollador de transmisión por secuencias

Desarrollador de transmisión por secuencias (mediante Twitch o Mixer) se ha convertido en una nueva forma atractiva de educación. Aunque Live Share no está pensado para reemplazar sus plataformas de difusión (aunque hemos oído la solicitud!), proporciona un medio para el host a la par con uno o más invitados del programa y, después, transmita esa interacción. De este modo, los visores pueden potencialmente más viendo la interacción natural y el proceso de pensamiento de dos o más desarrolladores, que incluso podría estar funcionando juntas en el IDE y completamente independiente de los sistemas operativos!

### <a name="prototyping--project-inception"></a>Creación de prototipos / concepción del proyecto

Cuando un equipo inicia un nuevo proyecto o microservicio o una nueva característica de creación de prototipos/picos, a menudo puede ser útil al colaborar con el fin de avanzar rápido y explorar nuevas ideas. Puesto que recién que forman la base de código es posible que no se confirmen en un repositorio compartido, Live Share permite que todo el mundo participar en el proceso iterativo, sin importar si están en la misma oficina o no.

## <a name="interactive-education"></a>Formación interactiva

Por lo general, Live Share pretende ayudar a los desarrolladores en el uso compartido de conocimientos entre su equipo. Educación es un caso de uso fundamental para Live Share, y esto admite especialmente bien al permitir que cada participante interactuar con la base de código que se han colaborado en, en lugar de simplemente ve una pantalla. Cada persona aprende de maneras diferentes de sutileza y, por lo tanto, al proporcionar independencia a un elemento "student", se les permite aprovechar las ventajas de la instrucción dada, sin necesidad de sacrificar su capacidad para explorar sus propias ideas en el camino.

### <a name="peer-mentoring--onboarding"></a>Elemento del mismo nivel tutorías / incorporación

Al introducir un desarrollador a una nueva base de código, características área, tecnología, etc., puede usar Live Share a les guiará a través del proyecto (mediante `Follow Mode`), de modo que puede seguir con usted, pero dentro de su propio IDE personal. Dado que Live Share permite "invitados" navegar de forma independiente el proyecto (por ejemplo, al abrir un archivo, realizar un `Peek Definition`), pueden seguir permiten, pero también, realizar exploraciones rápidas según sea necesario (por ejemplo, "Hmm, ¿qué hace esta función?").

### <a name="team-brown-bags"></a>Bolsas marrones del equipo

Bolsas marrones del equipo son eficazmente como del mismo nivel de asesoría, pero presenta a todo un equipo y, potencialmente, mucho más centrado en comunicar conocimiento útil con carácter general, en lugar de incorporar admiten o ayuda con una tarea específica.

### <a name="classroom-lectures"></a>Conferencias de aula

Cuando los instructores enseña una lección, pueden usar Live compartir para compartir su proyecto con los estudiantes, en lugar de simplemente presentar su pantalla. Esto permite que toda la clase seguir el profesor, al tiempo que es capaz de interactuar con el proyecto por sí solos. Además, el profesor puede pedir a los estudiantes individuales para ayudar a resolver (por ejemplo, una parte determinada de la lección "El método deberíamos llamamos aquí?"), que pueden ayudar a los aspectos sociales de la clase, sin necesidad de estudiantes acercarse a la parte delantera de la sala de reuniones, o incluso estar presente físicamente en la misma sala (por ejemplo, cursos en línea).

Para ayudar en la configuración de aula, Live Share habilita el uso compartido en modo de solo lectura. Instructores pueden usar el modo de solo lectura para que puedan compartir sus proyectos con los estudiantes sin tener que preocuparse acerca de modificaciones accidentales o innecesarias realizadas.

Además, Live Share tiene compatibilidad experimental con para habilitar a hasta 30 invitados unir en una sesión de colaboración. De este modo, instructores pueden tener su toda clase unirse a una sesión y ver código de forma conjunta.

Para habilitar esta característica experimental:

- **Código de VS:** Agregue "liveshare.features":"experimental" a settings.json.
- **VS:** Conjunto de herramientas > Opciones > Live Share > características en "Experimental"

Para optimizar totalmente Live Share en este escenario, se necesita aumentar aún más el límite actual de invitado ([#229](https://github.com/MicrosoftDocs/live-share/issues/229)) y simplificar la forma en que se inician las sesiones ([422 #](https://github.com/MicrosoftDocs/live-share/issues/422)).

## <a name="code-reviews"></a>Revisiones de código

Incorporación de cambios es una forma eficaz de colaborar con otras personas, pero suelen representar la finalización de una tarea (excepto PR "WIP") y el deseo lo combinó en. Muchas veces, los comentarios que se proporciona en un PR podrían fácilmente haberle proporcionado anteriormente y, por lo tanto, merece la pena potencialmente para que los equipos con facilidad y continua buscar consejos de sus colegas, en lugar de esperar hasta que "completar" una tarea para pedir.

Dado que Live compartir le permite compartir instantáneamente su proyecto con otros usuarios, se puede usar para habilitar "informal" / ad-hoc revisiones de código, donde en lugar de pedir ayuda, simplemente busca la entrada para asegurarse de su dirección o el enfoque se alinea con otros usuarios. Esto podría contribuir posteriores pr completarse más rápido y sin duda ayuda a relacionarse conocimiento en el equipo.

Además, dado que Live compartir le permite compartir un directorio arbitrario, sirve para realizar revisiones de código, incluso si actualmente no usa control de versiones (aunque debería!), o si el equipo no utiliza PRs (p. ej. hace desarrollo basado en el tronco).

Recurso compartido de activo actualmente no comparte las diferencias de control de código fuente, que es una parte crítica del contexto al uso de las revisiones de código. Se trata en nuestra guía básica y se agradece enormemente cualquier comentario sobre la prioridad ([voto 👍 aquí](https://github.com/MicrosoftDocs/live-share/issues/36)).

## <a name="technical-interviews"></a>Entrevistas técnicas

Cuando las entrevistas a los candidatos para la posición de un desarrollador, suele ser útil ir más allá de las discusiones de pizarra y, en su lugar, observarlas para resolver un problema de codificación de un IDE real (especialmente si su equipo u organización ha "estandarizado" en una herramienta que gustaría ver ellos usar). Esto no sólo le otorga la ventaja de trabajar de manera que es potencialmente más natural y cómoda (la mayoría de los desarrolladores no codificar en pizarras!), pero además, proporciona comentarios/asistencia inmediata mientras trabaja (por ejemplo, errores, intellisense de compilación). Muchas veces, es más importante comprender el proceso de pensamiento del candidato, en lugar de su capacidad para memorizar la sintaxis exacta o nombres de API. De esta manera, Live Share proporciona una experiencia que es similar a hacer un par de programación de la sesión, pero permite que el participante en su propio entorno (incluida la configuración del sistema operativo, como la accesibilidad) y funcionaría igualmente, así como para las entrevistas locales o remotas.

Además, el desarrollo del mundo real más que simplemente es escribir código. Dado que Live Share también admite la depuración compartido, las tareas y los terminales, permite los entrevistadores observar a candidatos al diagnosticar un problema, y le proporciona las herramientas adecuadas necesarios para resolverlo (p. ej. paso depurar, ejecutar pruebas). Puesto que todo el contexto es enviar de forma remota desde el equipo del host, pueden saltar rápidamente candidatos en el entorno de entrevista"" sin necesidad de configurar su máquina (más allá de instalar Live Share). Los equipos, a continuación, podrían mantener un repositorio compartido entrevistar a las aplicaciones (o use su base de código de producto real), que podría clona y compartido con los candidatos, basta con enviar la dirección URL de sesión antes de cada entrevista.

## <a name="see-also"></a>Vea también

- [Compatibilidad con lenguajes y plataformas](platform-support.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Todos los errores principales, las solicitudes de características y limitaciones](https://aka.ms/vsls-issues)
- [Todas las solicitudes de características y limitaciones](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
