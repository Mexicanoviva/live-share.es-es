---
title: 'Preguntas más frecuentes: Visual Studio Live Share | Microsoft Docs'
description: Preguntas más frecuentes sobre Visual Studio Live Share.
ms.custom: ''
ms.date: 05/05/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 1b68dc90f4bac5e21c04c555ab2d8fc7f59aad55
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58853604"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>Preguntas más frecuentes

## <a name="what-is-live-share"></a>¿Qué es Live Share?
Live Share le permite editar y depurar en colaboración con otros usuarios en tiempo real, independientemente del lenguaje de programación que use o los tipos de aplicaciones que compile. Permite al instante (y segura) comparta su proyecto actual y, luego, según sea necesario, comparta las sesiones de depuración, terminales instancias, las aplicaciones web de host local y mucho más! Los desarrolladores que se unen a las sesiones de reciben toda su contexto del editor de su entorno (por ejemplo, servicios de lenguaje, depuración), lo que garantiza que puedan empezar a productiva colaborar inmediatamente, sin necesidad de clonar los repositorios o instale los SDK.

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>¿Cuáles son los requisitos de las herramientas para usar Live Share?
El [capacidades básicas de](#what-are-the-core-capabilities-of-live-share) de Live Share son totalmente compatibles con las siguientes herramientas:

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [Visual Studio 2017 (versión 15.6 y versiones posteriores)](https://visualstudio.microsoft.com/vs/older-downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

Nos iterar rápidamente para responder a los comentarios de usuario. Esto nos obliga a aprovechar las características de Visual Studio y Visual Studio Code que sólo esté disponible en sus versiones de vista previa/insider respectivos. Le indicará qué características requieren las versiones más recientes de VS o VS Code en la documentación. Por ejemplo, soporte técnico de deshacer y rehacer local requiere Visual Studio 2017 15.7 +.

## <a name="what-are-the-core-capabilities-of-live-share"></a>¿Cuáles son las capacidades básicas de Live Share?
Recurso compartido en directo le permite compartir su código base con los miembros del equipo a través de una conexión segura. Con Live Share, puede editar en colaboración de varios archivos en un área de trabajo y más importante de depurar la aplicación con sus compañeros de equipo. Durante la edición conjunta de las modificaciones se ven inmediatamente por sus compañeros de equipo. Durante la depuración conjunta comparten la misma sesión de depuración de la aplicación. Esto significa y sus compañeros de equipo pueden controlar la ejecución del programa con los puntos de interrupción y pasos, pero independiente puede inspeccionar las variables, las inspecciones, variables locales y REPL (por ejemplo, la ventana Inmediato de Visual Studio).

Recurso compartido en vivo presenta una amplia variedad de casos de uso, como: investigando un error en conjunto, que muestra un problema que no la reproducción en el equipo de otra persona, resolver diseño emite, par de programación, la realización de una entrevista de codificación, otros miembros de un equipo de asesoría o realizar revisiones de código ad hoc.

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>¿Mediante el uso de Live Share, es mi código almacenado en un servidor de Microsoft?
No, el código compartido reside únicamente en el equipo del desarrollador que inició el recurso compartido. No se almacena ni cargado en la nube de ninguna manera. En su lugar, Live Share simplemente establece una conexión segura entre usted y sus compañeros de equipo (que es cifrada-to-end) y no inspeccionar o recopilar los datos en el código que se comparte.

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>¿Este modelo basado en remoto funciona en cualquier lugar? ¿Es igual a igual?
Requisito único del recurso compartido en vivo es que la persona que comparte y su compañero de equipo tienen acceso a internet. Una retransmisión de Azure que se facilita una comunicación segura entre los miembros del equipo durante una sesión de colaboración. El área de trabajo (es decir, los archivos de origen) no se almacena en la nube. Ninguna conexión de punto a punto especial es necesaria aunque uno podría utilizarse para reducir la latencia. Consulte [cambiar el modo de conexión](https://aka.ms/vsls-docs/connection-mode) en nuestra documentación para obtener más detalles.

## <a name="what-is-shared-during-a-live-share-session"></a>¿Qué se comparte durante una sesión de Live Share?
Recurso compartido en vivo no transfiere todas las entradas de teclado y mouse. Solo se comunica los datos necesarios para cada actividad de colaboración a las máquinas de sus compañeros de equipo. Por ejemplo, cuando se comparte el área de trabajo, se comparte la estructura de carpetas. Cuando se edita conjuntamente un archivo, se comparte el contenido de ese archivo. Cuando se depura en colaboración, se comparten las acciones de depuración (por ejemplo, paso a paso) y estado (por ejemplo, la pila de llamadas y variables locales).

## <a name="when-will-live-share-be-released"></a>¿Cuándo se lanzará Live Share?
Recurso compartido en vivo ya está disponible con carácter general. También puede [Introducción a Live Share](https://aka.ms/vsls-start) hoy mismo.

## <a name="how-much-will-it-cost"></a>¿Cuánto costará?
Estamos comprometidos con un nivel gratis sustancial de Visual Studio Live Share para los desarrolladores pueden usar de forma continuada. Se evaluará la introducción de los niveles de pago con características avanzadas como podamos comprender mejor las necesidades de la Comunidad.

## <a name="how-is-my-code-shared-with-other-teammates"></a>¿Cómo se comparte mi código con otros compañeros de equipo?
Cuando se usa Live Share, que está realizando el código que está trabajando disponibles que sus compañeros de equipo pueden acceder a él a través de un servicio de nube segura que los comandos remotos desde el editor. Sus compañeros de equipo pueden abrir y editar los archivos sin necesidad de almacenarlas en la nube o almacena permanentemente en la máquina de su compañero.

Recurso compartido en vivo permite acceso instantáneo a funcionalidades, como el árbol del proyecto, la navegación de código y búsqueda. También permite que sus compañeros de equipo para beneficiarse de mejoras del editor como IntelliSense.

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>¿Qué ocurre si un usuario se desconecta o deja de compartir?
El modelo remoto requiere que el desarrollador de uso compartido a través de Live Share y su compañero de equipo debe estar en línea se conecten. Si su compañero de equipo intenta usar Live Share cuando esté sin conexión, no podrá unirse a la sesión hasta que vuelven a estar en línea. Además, inmediatamente se deshabilitan cuando se detiene (p. ej. Cierre el editor, poner sin conexión o deja de compartir) de colaboración, otras acciones o acceso a archivos por sus compañeros de equipo.

## <a name="what-about-screen-sharing"></a>¿Qué sucede con uso compartido de pantalla?
Recurso compartido en directo le permite compartir el código del proyecto y su contexto. Significa que su compañero de equipo puede ir a la base de código y trabajar fácilmente con usted mediante su herramienta que ya conoce. El editor o en otras aplicaciones no son compartidos o visible por su compañero de equipo, y no debe cambiar su estilo de trabajo o usar una aplicación basada en web.

Recurso compartido en vivo no sustituye a uso compartido de pantalla donde desea mostrar un elemento de menú o tratar aspectos visuales de la aplicación o su editor. En su lugar, tiene la opción de usar Live Share, además de chat, voz, vídeo y pantalla compartida.

## <a name="what-about-other-collaboration-tools"></a>¿Qué sucede con otras herramientas de colaboración?
Recurso compartido en directo puede utilizarse con las tecnologías de correo electrónico, chat o mensajería instantánea. Hemos detectado que muchas interacciones de colaboración entre desarrolladores se inician en estas herramientas. Sin embargo, cuando se la discusión sobre el código, a menudo obtienen a un punto donde simplemente es demasiado difícil de explicar un problema con el texto, fragmentos de código o archivos individuales - es necesario más contexto.

Recurso compartido en directo puede usarse para muchas cosas, como: buscar ayuda sobre un problema, resolver un error, par de programación, llevar a cabo una entrevista de codificación o realizar un ad-hoc revise antes de una confirmación de código o una solicitud de extracción.

## <a name="what-about-other-web-editors"></a>¿Qué sucede con otros editores web?
Con editores basados en web, los compañeros de equipo deben usar la misma aplicación web para obtener las ventajas de colaboración, que no pueden ser su editor cotidiana y principal. Muchos editores basados en web, se suponen que compila e implementa en una máquina Virtual a menudo hospedada en un entorno de nube.

Aunque esto puede ser deseable para muchos escenarios, los desarrolladores a menudo desean colaborar en las aplicaciones que no se hospedan en una máquina virtual o en la nube.  Con Live Share, usted y su compañero de equipo pueden usar las funcionalidades del ecosistema de herramientas además de las mismas funcionalidades disponibles en editores basados en web.

Recurso compartido en vivo va un paso más allá y le permite compartir una sesión de depuración.  Esto resulta especialmente útil en dar de alta otros para ayudarle a localizar problemas que se producen sólo en el equipo sin modificar su flujo de trabajo de desarrollo o la necesidad de modificar el diseño de la aplicación.

## <a name="which-languages-and-platforms-will-be-supported"></a>¿Se admitirán qué lenguajes y plataformas?
Nuestro objetivo es admitir la amplia variedad de lenguajes y plataformas, para asegurarse de que podemos permiten una colaboración enriquecedora, independientemente del tipo de aplicación que se desarrolla. Consulte la [idioma y la compatibilidad con la plataforma](reference/platform-support.md) para obtener información sobre lo que funciona hoy en día.

## <a name="how-many-developers-can-join-a-collaboration-session"></a>¿Cuántos desarrolladores pueden unirse a una sesión de colaboración?
Actualmente admitimos 30 invitados simultáneos, el desarrollador que está compartiendo ("hospedaje"), además de su proyecto. De forma predeterminada, se habilitan a hasta 5 invitados en una sesión. 

Para habilitar el límite de aumento de invitado: 
- **Código de VS:** Agregue "liveshare.increasedGuestLimit":"true" a settings.json.
- **VS:** Conjunto de herramientas > Opciones > Live Share > mayor límite de invitado en "True"

## <a name="what-is-the-roadmap"></a>¿Qué es el mapa de ruta?
Puede ver el conjunto de problemas conocidos y los elementos de mapa de ruta [aquí](https://aka.ms/vsls-issues). Si desea ver solo las solicitudes de la característica en lugar de todos los problemas, consulte [aquí](https://aka.ms/vsls-feature-requests). Le animamos a enviar su voto a los elementos existentes, solicitar nuevas características y los informes de errores de registro para ayudarnos a forma la dirección del producto más adelante.

## <a name="see-also"></a>Vea también

- [Compatibilidad con lenguajes y plataformas](platform-support.md)
- [Requisitos de conectividad de Live Share](reference/connectivity.md)
- [Características de seguridad de Live Share](reference/security.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](troubleshooting.md) o [envíe sus comentarios](support.md).
