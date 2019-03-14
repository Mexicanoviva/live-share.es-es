---
title: Colaborar mediante Visual Studio, Visual Studio Live Share | Microsoft Docs
description: Un conjunto de procedimientos de colaboración para Visual Studio y Live Share.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 995c9e16d24328bb2680deb99cd7e7d421af945c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256431"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>Cómo: Colaborar mediante Visual Studio

¿Listo para empezar a colaborar con Live Share en Visual Studio? Si es así, está en el punto adecuado. En este artículo le guiaré a través de cómo usar algunas de las características específicas de la extensión de Visual Studio Live Share para Visual Studio.

Tenga en cuenta que todas las actividades de colaboración en se describen aquí implican una sola **host de sesión de colaboración** y uno o varios **invitados**. El anfitrión es la persona que inicia la sesión de colaboración, mientras que las personas que participan en ella son invitados.

*¿Busca un resumen resumido? Consulte la [compartir](../quickstart/share.md) o [combinación](../quickstart/join.md) inicios rápidos en su lugar.*

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

## <a name="installation"></a>Instalación

Antes de comenzar, deberá instalar **Visual Studio 2017 versión 15.6 o posterior** en Windows 7, 8.1 o 10. *Sin embargo, se recomienda Visual Studio 15.7 + como esto habilita la compatibilidad de deshacer y rehacer local.*

Para avanzar es muy sencillo:

1. Instale cualquier edición de la de [Visual Studio 2017](https://visualstudio.microsoft.com/vs/) 15.6 +.
2. Instalar un [admite la carga de trabajo](../reference/platform-support.md). (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).
3. [Descargar](https://aka.ms/vsls-dl/vs) e instalar la extensión de Visual Studio Live Share en marketplace.

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](../troubleshooting.md).

[![Descargar](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>Inicio de sesión

Para colaborar, necesitará inicio de sesión en Visual Studio Live Share para que todo el mundo sepa quién es usted. Esto es puramente una medida de seguridad y **no** optar cualquier marketing u otras actividades de investigación. Puede iniciar sesión con una cuenta personal de Microsoft (por ejemplo, @outlook.com), respaldado por Microsoft cuenta profesional o educativa (AAD) o una cuenta de GitHub. Es fácil iniciar sesión.

De forma predeterminada, Visual Studio usa el su [cuenta de personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) por lo que si ya ha iniciado sesión en Visual Studio, puede omitir este paso. En caso contrario, inicie sesión como lo haría normalmente.

![Botón de inicio de VS](../media/vs-sign-in-button.png)

Si desea utilizar un inicio de sesión diferente en que Visual Studio [cuenta de personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), vaya a **herramientas &gt; opciones &gt; Live Share &gt; cuenta de usuario** cambiar credenciales.

![Opciones de herramientas de VS Live Share](../media/vs-tools-options.png)

Seleccionar **cuenta externa** le permite seleccionar una cuenta que no se admite mediante la característica de personalización de Visual Studio, como GitHub. Un explorador aparecerá automáticamente la primera vez que se usa una característica de Live Share, por lo que puede completar el inicio de sesión.

Si surgen problemas, consulte [solución de problemas](../troubleshooting.md#sign-in) para obtener más sugerencias.

## <a name="share-a-project"></a>Compartir un proyecto

Después de descargar e instalar Visual Studio Live Share, siga estos pasos para iniciar una sesión de colaboración e invitar a un compañero de trabajo para trabajar con usted.

1. **Inicia sesión**

    Después de instalar la extensión Live Share, desea iniciar sesión para que otros colaboradores sepa quién es usted. De manera predeterminada Visual Studio usa la cuenta de personalización, por lo que es posible que pueda omitir este paso completamente.

    Consulte [inicie sesión en](#sign-in) para obtener más detalles.

2. **Abrir una carpeta, proyecto o solución**

    Para abrir una carpeta, proyecto o solución que le gustaría compartir con sus invitados, use el flujo de trabajo normal.

3. **[Opcional] Actualizar archivos ocultos o excluidos**

    De forma predeterminada, Live Share **oculta** los archivos o carpetas que se hace referencia en los archivos .gitignore en el proyecto de los invitados. **Ocultar** un archivo evita que aparezca en el árbol de archivos mientras **excepto** impide que se transmiten incluso durante las operaciones como la depuración. Si desea ocultar o excluir archivos diferentes, una **. vsls.json** archivo se puede agregar al proyecto con esta configuración. Consulte [controlar el acceso de archivo y visibilidad](../reference/security.md#controlling-file-access-and-visibility) para obtener más información.

4. **Iniciar una sesión de colaboración**

    Ahora, simplemente haga clic en el botón "Compartir" en la esquina superior derecha.

    ![Botón de recurso compartido de VS](../media/vs-share-button.png)

    > [!NOTE]
    > Se le pedirá el software de firewall de escritorio para que el agente de compartir en directo abrir un puerto de la primera vez que se comparte. Aceptar esto es totalmente opcional pero permite que un seguro "modo directo" para mejorar el rendimiento cuando es la persona que trabaja en la misma red que sea. Consulte [cambiar el modo de conexión](../reference/connectivity.md#changing-the-connection-mode) para obtener más información.

    Un vínculo de la invitación se copiará automáticamente en el Portapapeles. Cuando se abre en un explorador, este vínculo permite a otros a unirse a una nueva sesión de colaboración que comparte el contenido de estas carpetas con ellos.

    También verá la transición del botón "Compartir" para transmitir un "estado de sesión". Consulte [estado de sesión](#session-states) siguiente información sobre este aspecto.

    Tenga en cuenta que si tiene que obtener el vínculo de la invitación a intentarlo después de haber iniciado el uso compartido, puede acceder haciendo clic en el recurso compartido / estado de sesión de botón y seleccione "Copiar vínculo".

5. **[Opcional] Habilitar el modo de solo lectura**

    Una vez que inicie una sesión de colaboración, puede establecer la sesión sea de solo lectura para evitar que los invitados realiza modificaciones en el código que se comparte.

    Después de compartir, obtendrá una notificación de que el vínculo de la invitación se ha copiado en el Portapapeles. A continuación, puede seleccionar la opción para que la sesión de solo lectura.

    ![Modo de solo lectura de VS](../media/vs-read-only-notification.png)

6. **Enviar a alguien el vínculo**

    Envíe el vínculo por correo electrónico, Slack, Skype, etc. a los que desea invitar. Tenga en cuenta que, dado el nivel de acceso a Live compartir sesiones pueden proporcionar a los invitados, **solo se debe compartir con usuarios de confianza** y piense detenidamente las implicaciones de lo que va a compartir.

    > **Sugerencia de seguridad:** ¿Desea comprender las implicaciones de seguridad de algunas de las características de Live del recurso compartido? Consulte la [seguridad](../reference/security.md) artículo.

    Si el invitado le invitó tiene preguntas, el "[inicio rápido: Únase a la primera sesión](../quickstart/join.md)"artículo proporciona información adicional sobre entre en funcionamiento como invitado.

7. **[Opcional] Aprobar el invitado**

    De forma predeterminada, los invitados se unirán automáticamente a la sesión de colaboración y se le notificará cuando porque han preparado para trabajar con usted. Aunque esta notificación le proporciona la opción de quitarlos de la sesión, también puede optar en su lugar, requieren una "aprobación" explícita para todo aquel que unir.

    Basta con cambiar **Herramientas > Opciones > Live Share > solicitar aprobación del invitado** en True para habilitar la característica. Una vez activada esta opción, le solicitará una notificación que aprobar al invitado para que pueden unirse.

    ![Solicitud de aprobación de combinación de Visual Studio](../media/vs-join-approval.png)

    Consulte [invitaciones y acceso de combinación](../reference/security.md#invitations-and-join-access) para obtener más detalles sobre las consideraciones de seguridad de invitación.

¡¡Eso es todo!!

### <a name="ending-the-collaboration-session"></a>Finalizar la sesión de colaboración

Como un host, puede dejar de compartir completamente y finalizar la sesión de colaboración, haga clic en el recurso compartido / estado de sesión de botón (en la esquina superior derecha) y seleccione "sesión de colaboración final".

![Dejar de compartir](../media/vs-stop-sharing.png)

Todos los invitados le notificará que la sesión ha finalizado. Una vez que ha finalizado la sesión, los invitados ya no podrán acceder al contenido y los archivos temporales se limpian automáticamente.

¿Tiene problemas con el uso compartido? Desproteger [solución de problemas](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Participar en una sesión de colaboración

Después de descargar e instalar Visual Studio Live Share, los invitados sólo necesitan realizar unos pasos para participar en una sesión de colaboración de alojamiento. Hay dos maneras de combinar: [a través del explorador](#join-via-the-browser) y [manualmente](#join-manually).

> **Sugerencia de seguridad:** Como invitado participar en una sesión de colaboración, es importante comprender que los hosts pueden limitar su acceso a determinados archivos o las características. ¿Desea comprender las implicaciones de seguridad de algunas de las características y la configuración de Live Share? Consulte la [seguridad](../reference/security.md) artículo.

### <a name="join-via-the-browser"></a>Unirse a través del explorador

Para participar en una sesión de colaboración más sencillo es simplemente abrir el vínculo de invitación en un explorador web. Aquí es lo que puede esperar al seguir este flujo.

1. **Inicia sesión**

    Después de instalar la extensión Live Share, desea iniciar sesión para que otros colaboradores sepa quién es usted. De manera predeterminada Visual Studio usa la cuenta de personalización, por lo que es posible que pueda omitir este paso completamente.

    Consulte [inicie sesión en](#sign-in) para obtener más detalles.

2. **Haga clic en el vínculo de la invitación y abrir la invitación en el explorador**

    Ahora, basta con abrir (o volver a abrir) el vínculo de invitación en un explorador.

    > **Nota**: Si aún no ha instalado la extensión Live Share, se mostrarán con vínculos a marketplace de extensión. Instalar la extensión y reinicie la herramienta y vuelva a intentar.

    Debería recibir una notificación que desea que el explorador iniciar una herramienta de Live Share habilitado. Si se permite que inicie la herramienta seleccionada, se conectará a la sesión de colaboración, una vez que se inicia.

    ![Únase a la página](../media/join-page.png)

    Si el host está sin conexión, se le notificará en este momento en su lugar. A continuación, puede ponerse en contacto con el host y pídale que vuelva a compartir.

    > [!NOTE]
    > ¿Sigue teniendo problemas? Consulte [combinar manualmente](#join-manually).

3. **Collaborate**

    ¡¡Eso es todo!! En unos instantes se conectará y empezar a colaborar.

    Verá la transición del botón "Compartir" para transmitir un "estado de sesión". Consulte [estado de sesión](#session-states) información siguiente para este aspecto.

    A continuación, automáticamente pasará al archivo es que el host se está editando una vez completada la combinación.

### <a name="join-manually"></a>Combinar manualmente

Puede combinar manualmente sin usar un explorador web que puede ser útil en situaciones donde ya se está ejecutando la herramienta que desea usar, que desea usar otra herramienta que suela hacerlo, o si tiene problemas con la obtención de invitar a vínculos a trabajar por algún motivo. El proceso es sencillo:

1. **Inicia sesión**

    Después de instalar la extensión Live Share, desea iniciar sesión para que otros colaboradores sepa quién es usted. De manera predeterminada Visual Studio usa la cuenta de personalización, por lo que es posible que pueda omitir este paso completamente.

    Consulte [inicie sesión en](#sign-in) para obtener más detalles.

2. **Use el comando de combinación**

    Simplemente vaya a **archivo > unirse a la sesión de colaboración**

    ![Menú de la combinación de VS](../media/vs-join.png)

3. **Pegue el vínculo de invitación**

    Pegue la dirección URL de invitación que se enviaron y confirme.

4. **¡Colaborar!**

    Ya está. Debe estar conectado a la sesión de colaboración momentáneamente.

    Verá la transición del botón "Compartir" para transmitir un "estado de sesión". Consulte [estado de sesión](#session-states) información siguiente para este aspecto.

    A continuación, automáticamente pasará a donde el host se está editando una vez completada la combinación.

### <a name="leave-the-collaboration-session"></a>Deje la sesión de colaboración

Como invitado, puede dejar la sesión de colaboración sin tener que finalizar, para que otros usuarios simplemente cierre la herramienta o haciendo clic en el recurso compartido / estado de sesión de botón y seleccionando "Abandonar la sesión de colaboración".

![Menú de la combinación de VS](../media/vs-leave-session.png)

Los archivos temporales se limpian automáticamente por lo que no es necesario realizar ninguna otra acción.

¿Tiene problemas con la combinación? Desproteger [solución de problemas](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Edición conjunta

Una vez que un invitado ha unido a una sesión de colaboración, todos los colaboradores podrán inmediatamente ver los demás modificaciones y las selecciones en tiempo real. Todo lo que necesita hacer es seleccionar un archivo desde el Explorador de archivos y empiece a editar. Hosts e invitados ver ediciones incluirlas y puede contribuir a sí mismos lo que iterar fácil y rápidamente clavo hacia abajo tanto soluciones.

> [!NOTE]
> Unirse a una sesión de colaboración de solo lectura impide que los invitados se pueden realizar modificaciones a los archivos. Un host puede [habilitar el modo de solo lectura cuando comparten](#share-a-project). Como un invitado, puede indicar si se ha unido a una sesión de solo lectura examinando su [estado de sesión](#session-states).

![Pantalla que muestra edición conjunta](../media/vs-coedit.png)

> [!NOTE]
> Comparte la edición tiene algunas limitaciones para determinados idiomas. Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características por lenguaje.

Más allá de los cursores y las modificaciones, las opciones seleccionadas también son visibles para todos los participantes en ese mismo archivo. Esto facilita la resalte donde podrían existir o transmitir ideas problemas.

![Pantalla que muestra resaltado](../media/vs-highlight.png)

Mejor aún, usted y otros participantes pueden navegar a cualquier archivo en el proyecto compartido. Puede modificar conjuntamente o por separado, lo que significa que puede cambiar sin problemas entre la investigación, realizar pequeños ajustes y editarlo en colaboración completa.

> [!NOTE]
> De forma predeterminada los recursos compartidos de Live Share abren archivos externos a la solución de compartido. Si desea deshabilitar esta característica, actualice el recurso compartido de archivos externos en herramientas &gt; opciones &gt; Live Share en False.

Las ediciones resultantes se almacenan en la máquina del host en Guardar por lo que no es necesario sincronizar, inserte o enviar archivos alrededor de una vez que haya terminado edición. Las modificaciones son "simplemente there".

> **Sugerencia de seguridad:** Dado que todos los participantes pueden independientemente navegar y editar archivos, como un host, es posible que desee restringir los archivos que los invitados pueden tener acceso a su proyecto a través de un. archivo vsls.json. Como invitado, también es importante tener en cuenta que no vea determinados archivos como resultado de esta configuración. Consulte [controlar el acceso de archivo y visibilidad](../reference/security.md#controlling-file-access-and-visibility) para obtener más información.

### <a name="changing-participant-flag-behaviors"></a>Cambiar los comportamientos de la marca de participante

De forma predeterminada, Visual Studio Live Share muestra automáticamente una "marca" junto al cursor de un participante al mantener el mouse, o cuando edita, resalte o mover el cursor. En algunos casos es posible que prefiera cambiar este comportamiento. Para ello:

1. Vaya a **Herramientas > Opciones > Live Share**
2. Cambiar el **marca visibilidad** opción a uno de los siguientes:

| Opción | Comportamiento |
|--------|----------|
| OnHoverOnly | La marca solo está visible cuando mantenga el mouse sobre el cursor. |
| OnHoverOrActivity | Este es el valor predeterminado. La marca está visible al mantener el mouse o si edita el participante, se resaltan o se mueve el cursor. |
| Siempre | La marca está siempre visible.

## <a name="following"></a>Siguiente

Siempre que esté en una sesión de colaboración, podrá puede ver las iniciales de cada participante en la esquina superior derecha del editor junto al botón el inicio de sesión. Mantener el mouse sobre las iniciales muestra toda la información del participante.

![Captura de pantalla que muestra usuario](../media/vs-person.png)

A veces deberá explicar un problema o diseño que abarca varios archivos o ubicaciones del código. En estas situaciones, puede útil seguir temporalmente un compañero de trabajo cuando se mueven a lo largo del proyecto. Por este motivo, como un invitado, cuando se une a una sesión de colaboración automáticamente "seguirá" el host. Al seguir un participante, el editor se mantendrá sincronizado con sus archivos abiertos actualmente, el cursor y la posición de desplazamiento.

> [!NOTE]
> De forma predeterminada los recursos compartidos de Live Share abren archivos externos a la solución de compartido. Si desea deshabilitar esta característica, actualice el recurso compartido de archivos externos en herramientas &gt; opciones &gt; Live Share en False.

Para facilitar la desactivar "modo de seguimiento" y empiece a editar por su cuenta, detendrá los siguientes si se produce cualquiera de las siguientes acciones:

1. Editar, mueva el cursor o realizar una selección
2. Seleccione otro archivo

También puede dejar de seguir en cualquier momento haciendo clic en las iniciales de la persona que está siguiendo en la esquina superior derecha. A continuación, desaparecerá el círculo alrededor de las iniciales del participante que indica que está siguiendo ellos.

![Participante en Visual Studio se sigue](../media/vs-pinned.png) ![Participante en Visual Studio no se sigue](../media/vs-pin-hover.png)

Puede hacer clic en cualquier iniciales en esta misma ubicación que seguir cualquier host o invitado en la sesión de colaboración. Tenga en cuenta que si desea pasar a una persona ubicación en lugar de seguir, simplemente haga doble clic en el sus iniciales.

## <a name="focusing"></a>Centrado

En ocasiones puede que desee todos los usuarios en una sesión de colaboración para llegar y eche un vistazo a algo que está haciendo. Live Share le permite hacer que todo el mundo "Centrar" su atención en una notificación que facilita la tarea para que puedan disponer de vuelta.

Simplemente haga clic en el estado de sesión / compartir situado en la esquina superior derecha y seleccione a "Participantes del enfoque".

![Opción de menú de foco](../media/vs-focus.png)

Todos los usuarios de la sesión de colaboración, a continuación, obtendrá una notificación de que ha solicitado su atención

![Notificación del sistema de foco](../media/vs-focus-toast.png)

Puede, a continuación, haga clic en "Seguir" directamente desde la notificación cuando haya terminado poner su enfoque en el.

## <a name="co-debugging"></a>Depuración conjunta

Característica de depuración de Visual Studio Live Share colaboración es una manera eficaz y única para depurar un problema. Más allá de lo que permite una experiencia de colaboración solucionar problemas, también y otros participantes en la sesión de la capacidad para investigar los problemas que pueden ser específica del entorno proporcionando una sesión de depuración compartida en la máquina del host.

> **Sugerencia de seguridad:** Dado que todos los participantes pueden independientemente navegar y editar archivos, como un host, es posible que desee restringir los archivos que los invitados pueden tener acceso a su proyecto a través de un. archivo vsls.json. También debe tener en cuenta que el acceso de consola/REPL significa que los participantes pueden ejecutar comandos en el equipo de forma que solo debe depurar conjuntamente con los que confíe. Como invitado, también es importante tener en cuenta que no es posible que pueda seguir el depurador lo paso en algunos archivos restringidos de archivos como resultado de esta configuración. Consulte [controlar el acceso de archivo y visibilidad](../reference/security.md#controlling-file-access-and-visibility) para obtener más información.

Usando simple. El host de sesión de colaboración solo tiene que iniciar la depuración a través de los medios habituales en Visual Studio.

![Botón de depuración de VS](../media/vs-debug-button.png)

Una vez que el depurador se adjunta en el lado del host, todos los invitados se adjuntan también también automáticamente. Aunque hay una "sesión de depuración" que se ejecuta en la máquina del host, todos los participantes están conectados a él y tienen su propia vista.

> [!TIP]
> Si desea cambiar cuándo y cómo se realiza la depuración conjunta, puede cambiar los comportamientos predeterminados a través de la configuración en **Herramientas > Opciones > Live Share**.

![Adjuntadas el depurador de VS](../media/vs-debugger.png)

Cualquier persona puede avanzar por el proceso de depuración que permite cambiar sin problemas entre colaboradores sin tener que negociar el control.

> [!NOTE]
> Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características de depuración por lenguaje o plataforma.

Cada colaborador puede investigar distintas variables, saltar a distintos archivos de la pila de llamadas, inspeccionar variables e incluso agregar o quitar puntos de interrupción. Características de edición conjunta, a continuación, permitir que cada participante oradores realizar un seguimiento en los demás se encuentran para proporcionar la capacidad única de cambiar sin problemas al mismo tiempo investigando distintos aspectos del problema y depuración en colaboración.

> [!NOTE]
> Mientras está en una sesión de colaboración de solo lectura, un invitado no pueda recorrer el proceso de depuración. Pueden, sin embargo, todavía agregar o quitar puntos de interrupción e inspeccionar variables.

> [!TIP]
> También puede participar en las sesiones de Visual Studio y viceversa de depuración de VS Code. Consulte la [instrucciones en Visual Studio](vscode.md#co-debugging) en depuración conjuntamente para obtener más información.

### <a name="automatic-web-app-sharing"></a>Uso compartido de aplicaciones web automática

Aún mejor, para los proyectos de aplicación Web ASP.NET, de forma predeterminada si el proyecto del host está configurado para iniciarse automáticamente un explorador web para conectarse a la aplicación web en ejecución durante la depuración, Live Share hará automáticamente lo mismo en la máquina de cada invitado! Esto se realiza de forma segura y la aplicación web remota solo está disponible para los invitados durante la sesión de depuración de forma predeterminada.

Consulte [compartir un servidor](#share-a-server) para obtener información sobre cómo compartir el acceso al servidor para otros tipos de proyecto o para la duración de la sesión.

> [!TIP]
> Si no, como el explorador automatizado comportamiento de uso compartido y quiere cambiarla, puede actualizar la configuración en **Herramientas > Opciones > Live Share**.

![Animación de depuración simultáneas](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Al cambiar las combinaciones de las sesiones de depuración de Visual Studio

De forma predeterminada, como invitado, deberá se adjunta automáticamente a cuando se comparten por el host de sesiones de depuración. Sin embargo, en algunos casos es posible este comportamiento perjudiciales. Afortunadamente, puede cambiarlo como sigue:

1. Vaya a **Herramientas > Opciones > Live Share**
2. Cambiar el **opción de sesión de depuración de combinación** a uno de los siguientes:

| Opción | Comportamiento |
|--------|----------|
| Automático | El valor predeterminado. Como invitado, deberá unirse automáticamente a cualquier sesión de depuración compartido se inicia el host. |
| Se le pida | Como invitado, se le preguntará si desea participar en una sesión de depuración compartida cuando se inicie el host. |
| Manual | Como invitado, necesita combinar manualmente las sesiones de depuración. Consulte [separar y volver a adjuntar](#detaching-and-reattaching).|

### <a name="detaching-and-reattaching"></a>Separar y volver a adjuntar

Un invitado, puede desear detener temporalmente la depuración. Afortunadamente, basta con hacer clic en el icono "Detener" en la barra de herramientas de depuración para desasociar al depurador sin que afecte a otros invitados o el host.

Si ha actualizado la configuración por lo que ya no la asociación automática, o si desea volver a adjuntar más adelante, puede seleccionar simplemente la ejecución deseada sesión desde el "... Seleccione elemento de inicio" de depuración lista desplegable...

![Botón de depuración de VS](../media/vs-select-reattach.png)

... y, a continuación, haga clic en él para asociarlo.

![Botón de depuración de VS](../media/vs-reattach.png)

## <a name="share-a-server"></a>Compartir un servidor

Desde la hora a hora, como un host de sesión de colaboración es posible que desea compartir los servidores locales adicionales o servicios con los invitados. Esto puede variar desde otros puntos de conexión RESTful a las bases de datos u otros servidores. Compartir Live de Visual Studio le permite especificar un número de puerto local, opcionalmente, asignarle un nombre y, después, compartirlo con todos los invitados.

Los invitados, a continuación, podrá tener acceso al servidor que ha compartido en ese puerto desde su propio equipo local en el mismo puerto exacto. Por ejemplo, si comparte un servidor web **que se ejecuta en el puerto 3000**, el invitado puede tener acceso a ese mismo servidor web en ejecución en sus **propia máquina** en http://localhost:3000! Esto se logra a través de un túnel SSH o SSL seguro entre el host y los invitados y autenticado a través del servicio, por lo que puede estar seguro de que sólo los de la sesión de colaboración tienen acceso.

> **Sugerencia de seguridad:** Como un host, debe ser muy selectivo con los puertos que comparte con los invitados y ajustarse a los puertos aplicación (en lugar de compartir un puerto del sistema). Para los invitados, los puertos compartidos se comportarán exactamente como lo harían si se estaba ejecutando el servicio de servidor en su propio equipo. Esto es muy útil, pero si se comparte un puerto incorrecto también puede ser arriesgado.

Por motivos de seguridad, solo los servidores que se ejecutan en los puertos que especifique están disponibles para otros invitados. Afortunadamente, resulta muy sencillo agregar uno de ellos como la sesión de colaboración **host**. Esta es la manera de hacerlo:

1. Haga clic en el recurso compartido / estado de sesión en la esquina superior derecha y seleccione "Administrar servidores locales compartidos"

    ![Administrar servidores locales compartidos](../media/vs-share-local-servers.png)

2. En el cuadro de diálogo que aparece, haga clic en "Agregar" y escriba el número de puerto que se está ejecutando el servidor en forma local, escriba un nombre, presione ENTRAR, a continuación, Aceptar.

    ![Administrar servidores locales compartidos](../media/vs-manage-local-shared-servers.png)

Ya está. El servidor en el puerto que especificó se asignarán al host local de cada invitado en el mismo puerto (a menos que ese puerto ya estaba ocupado).

Si el puerto ya está en uso en la máquina del invitado, automáticamente se selecciona uno diferente. Afortunadamente, como un invitado puede ver una lista de actualmente comparten puertos (por nombre si se especifica) haciendo clic en el recurso compartido / estado de sesión de botón en la esquina superior derecha y seleccione "ver Shared servidores locales."

![Viw compartido servidores locales](../media/vs-view-shared-servers.png)

Tenga en cuenta que *invitados no* controlar qué puertos en la máquina del host se comparten por motivos de seguridad.

Para **detener** uso compartido de un servidor local, el host simplemente debe hacer clic en el recurso compartido / estado de sesión de botón en la esquina superior derecha como anteriormente, seleccione "Administrar compartido servidores locales" y seleccione el puerto adecuado y haga clic en "Quitar".

## <a name="share-a-terminal"></a>Compartir un terminal

El desarrollo moderno hace un uso frecuente de una amplia gama de herramientas de línea de comandos. Afortunadamente, compartir Live le permite, como un host, para "compartir opcionalmente un terminal" con los invitados. El terminal compartido puede ser de solo lectura o de colaboración totalmente por lo que usted y los invitados pueden ejecutar comandos y ver los resultados. Puede dar visibilidad de los invitados a la salida de terminal o dejarlos comience a usar y ejecutar pruebas, compilaciones o problemas específicos de evaluación de prioridades incluso entorno que se producen sólo en el equipo.

Sin embargo, los elementos terminales son **no** comparten de forma predeterminada ya que proporcionan los invitados acceso de solo lectura al menos a la salida de comandos que ejecute (si no la capacidad de ejecutar comandos ellos mismos). Este modo, puede ejecutar comandos en terminales locales sin riesgo libremente y sólo compartir cuando en realidad debe hacerlo. Además, solo los hosts pueden iniciar terminales compartidos para evitar que los invitados de iniciarse una y hacer algo que no espera ni viendo.

Como un host, puede compartir un terminal, haga clic en el estado de sesión o compartir el botón en la esquina superior derecha y seleccione uno de los elementos de menú "Compartir Terminal".

![Menú Terminal](../media/vs-terminal-menu.png)

En este momento, puede seleccionar sólo lectura o lectura/escritura terminal en el menú. Si el terminal es lectura/escritura, todo el mundo puede escribir en el terminal incluido el host, lo que facilita la intervenir si un invitado está haciendo algo que no le gusta. Sin embargo, para estar seguros, debería **únicamente conceda acceso de lectura/escritura a los invitados cuando se sabe que necesitan realmente** y sígala terminales de solo lectura para escenarios donde desea que el invitado para ver la salida de los comandos que ejecute.

> [!NOTE]
> Si la sesión de colaboración está en modo de solo lectura, los terminales de sólo lectura pueden compartirse por el host.

Una vez que haya seleccionado el tipo de terminal compartida que desee iniciar, aparecerá un nuevo terminal compartido para todos los participantes con los permisos correctos. Mientras que Visual Studio Code tiene una compatibilidad integrada de terminal Visual Studio no tiene una fábrica. Por lo tanto, de forma predeterminada, se mostrará nueva ventana que contiene el terminal. Sin embargo, si la [extensión ataca ataca Terminal](https://marketplace.visualstudio.com/items?itemName=DanielGriffen.WhackWhackTerminal), Live Share creará un terminal integrado en su lugar. Visual Studio le proporcionará un vínculo para instalarlo en la primera vez que inicia o unen a un terminal compartido.

![Notificación del sistema de instalación de Terminal](../media/vs-terminal-install.png)

Para finalizar la sesión de terminal, simplemente escriba exit o cerrar la ventana de terminal y todos los usuarios se desconectarán.

## <a name="session-states"></a>Estados de sesión

Una vez que se iniciaron o unido a la sesión de colaboración y dispone de acceso al contenido compartido, el botón "Compartir" en la esquina superior derecha actualiza su aspecto para reflejar el estado de la sesión de colaboración activos.

Estos son los Estados que normalmente solo verá:

| Estado | Botón | Descripción |
|-------|--------|-------------|
| inactivo | ![Estado de VS: inactivo](../media/vs-status-share.png) | No hay ninguna sesión de colaboración active y nada se comparte. |
| Host: Uso compartido en curso | ![Estado de VS: compartir en curso](../media/vs-status-sharing.png) | Se está iniciando una sesión de colaboración y uso compartido de contenido comenzará en breve. |
| Host: Uso compartido de recursos | ![Estado de VS: uso compartido de activos ](../media/vs-status-active.png) | Se activa una sesión de colaboración y contenido se comparte. |
| Host: Uso compartido de solo lectura | ![Estado de VS: uso compartido de solo lectura](../media/vs-status-sharing-read-only.png)| Uso compartido de una sesión de colaboración de solo lectura. |
| Invitado: Unirse a la sesión | ![Estado del código de VS: unirse a](../media/vs-status-joining.png) | Unirse a una sesión de colaboración existente. |
| Invitado: Unirse | ![Estado de VS: unido](../media/vs-status-joined.png) | Unido y conectado a una sesión de colaboración active y recepción de contenido compartido. |
| Invitado: Unido a solo lectura | ![Estado de VS: Unido de solo lectura](../media/vs-status-joined-read-only.png) | Unido y conectado a una sesión de colaboración activa de solo lectura. |

## <a name="guest-limitations"></a>Limitaciones de invitado

Aunque actualmente hay algunos puntos débiles invitados experimentará al usar las características que se ha descrito anteriormente, los hosts de sesión de colaboración conservan toda la funcionalidad de su herramienta preferida. Para obtener más información, vea las secciones siguientes:

- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Compatibilidad con extensiones](../reference/extensions.md)
- [Todos los errores principales, las solicitudes de características y limitaciones](https://aka.ms/vsls-issues)
- [Todas las solicitudes de características y limitaciones](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>Pasos siguientes

Consulte estos artículos adicionales para obtener más información.

- [Inicio rápido: Comparta su primer proyecto](../quickstart/share.md)
- [Inicio rápido: Únase a la primera sesión](../quickstart/join.md)
- [Cómo: Colaborar mediante Visual Studio Code](vscode.md)
- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
