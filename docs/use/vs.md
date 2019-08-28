---
title: 'Colaboración mediante Visual Studio: Visual Studio Live Share | Microsoft Docs'
description: Un conjunto de procedimientos de colaboración para Visual Studio y Live Share.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 65c48d1a95cc94bc7505c185be353e437e3c5ba1
ms.sourcegitcommit: 6b46e300d76eda661ab34c67a3b909d5c162cd9a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062300"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>Colaboración mediante Visual Studio

¿Está listo para empezar a colaborar con Live Share en Visual Studio? Si es así, está en el lugar correcto. En este artículo, lo guiaremos para que aprenda a usar algunas de las características específicas de la extensión Visual Studio Live Share para Visual Studio.

Tenga en cuenta que todas las actividades de colaboración que se describen aquí implica un único **anfitrión de la sesión de colaboración** y uno o varios **invitados**. El anfitrión es la persona que inicia la sesión de colaboración, mientras que las personas que participan en ella son invitados.

*¿Busca un resumen abreviado? Consulte entonces los inicios rápidos sobre cómo [compartir](../quickstart/share.md) o [participar](../quickstart/join.md).*

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

## <a name="installation"></a>Instalación

Antes de comenzar, deberá instalar **Visual Studio 2019** o la versión **15.6 o superior de Visual Studio 2017** en Windows 7, 8.1 o 10. *Sin embargo, se recomienda Visual Studio 15.7 y versiones superiores porque está habilitada la compatibilidad con la acción de deshacer/rehacer*.

Empezar es muy sencillo:

Para Visual Studio 2019
1. Instale cualquier edición de [Visual Studio 2019](https://visualstudio.microsoft.com/vs/).
2. Instale una [carga de trabajo compatible](../reference/platform-support.md). (por ejemplo, ASP.NET, .NET Core, C++, Python o Node.js).
3. Visual Studio Live Share se instala de forma predeterminada con esas cargas de trabajo.

Para Visual Studio 2017
1. Instale cualquier edición de la versión 15.6 de [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/) o una versión posterior.
2. Instale una [carga de trabajo compatible](../reference/platform-support.md). (por ejemplo, ASP.NET, .NET Core, C++ o Node.js).
3. [Descargue](https://aka.ms/vsls-dl/vs) e instale la extensión de Visual Studio Live Share desde Marketplace.

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](../troubleshooting.md).

[![Descargar](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>Inicio de sesión

Para poder colaborar, deberá iniciar sesión en Visual Studio Live Share de manera que todos sepan quién es usted. Esto no es más que una medida de seguridad y **no** significa que se inscriba en ninguna actividad de marketing u otro tipo de investigación. Puede iniciar sesión con una cuenta personal de Microsoft (por ejemplo, @outlook.com), una cuenta profesional o educativa (AAD) con el respaldo de Microsoft, o bien una cuenta de GitHub. Es fácil iniciar sesión.

De manera predeterminada, Visual Studio usa su [cuenta de personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) por lo que, si ya inició sesión en Visual Studio, puede omitir este paso. En caso contrario, inicie sesión como lo haría normalmente.

![Botón de inicio de sesión de VS](../media/vs-sign-in-button.png)


Si quiere usar un inicio de sesión diferente al de la [cuenta de personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) de Visual Studio, vaya a **Herramientas &gt; Opciones &gt; Live Share &gt; Cuenta de usuario** y seleccione otras credenciales.

![Opciones de herramientas de VS para Live Share](../media/vs-tools-options-new.png)

Seleccionar **Cuenta externa** le permite seleccionar una cuenta no compatible con la característica de personalización de Visual Studio, como GitHub. Un explorador aparecerá automáticamente la primera vez que use una característica de Live Share para que pueda completar el inicio de sesión.
>[!Tip]
>¿Sabía que puede ir a **Herramientas &gt; Opciones &gt; Live Share &gt; General** para ver toda la configuración de Live Share predeterminada? Personalice la experiencia de colaboración para ajustarla a sus necesidades. También puede probar las nuevas características de Live Share eligiendo **Avanzadas &gt; Características &gt; Participantes**  desde la configuración general de Live Share.  

Si surgen problemas, consulte la [solución de problemas](../troubleshooting.md#sign-in) para obtener más sugerencias.

## <a name="share-a-project"></a>Uso compartido de un proyecto

Después de descargar e instalar Visual Studio Live Share, siga estos pasos para iniciar una sesión de colaboración e invitar a un compañero de trabajo a trabajar con usted.

1. **Inicio de sesión**

    Ahora que ha iniciado sesión, está listo para iniciar su sesión de colaboración.
    ¿No ha iniciado sesión? Consulte [Inicio de sesión](#sign-in) para obtener más detalles.

2. **Abrir una solución, un proyecto o una carpeta**

    Use el flujo de trabajo normal para abrir una carpeta, un proyecto o una solución que quisiera compartir con los invitados.

3. **[Opcional] Actualizar los archivos ocultos o excluidos**

    De manera predeterminada, Live Share **oculta** a los invitados los archivos o carpetas a los que se hace referencia en los archivos .gitignore. **Ocultar** un archivo impide que aparezca en el árbol de archivos, mientras que **excluirlo** impide que se transmita incluso durante operaciones como la depuración. Si quiere ocultar o excluir otros archivos, puede agregar un archivo **.vsls.json** al proyecto con esta configuración. Consulte [Control de la visibilidad y el acceso de archivos](../reference/security.md#controlling-file-access-and-visibility) para más información.

4. **Iniciar una sesión de colaboración**

    Ahora, haga clic en el botón "Live Share" que aparece en la esquina superior derecha para iniciar una sesión de Live Share.     Se copia automáticamente en el Portapapeles un vínculo a la sesión de colaboración que puede compartir. 

    ![Botón Compartir de VS](../media/vs-share-button.png)

    Cuando inicie una sesión de colaboración por primera vez, verá una ventana de herramientas de Live Share. Asegúrese de acoplar esta ventana para garantizar que aparezca la próxima vez que inicie una sesión de Live Share.

   ![Ventana de herramientas de VS Live Share](../media/vs-live-share-tool-window.png)

    > [!NOTE]
    > La primera vez que comparta, es posible que el software de firewall de escritorio le pida que permita que el agente de Live Share abra un puerto. Aceptar esto es totalmente opcional, pero habilita un "modo directo" seguro para mejorar el rendimiento cuando la persona con la que trabaja se encuentra en la misma red que usted. Consulte [Cambiar el modo de conexión](../reference/connectivity.md#changing-the-connection-mode) para más detalles.

5. **[Opcional] Habilitar el modo de solo lectura**

    Una vez iniciada la sesión de colaboración, puede establecerla para que sea de solo lectura a fin de evitar que los invitados realicen cambios en el código que se comparte.

    Después de compartir, recibirá una notificación en la que se indica que el vínculo de invitación se ha copiado en el Portapapeles. Después, puede seleccionar la opción para hacer que la sesión sea de solo lectura.

    ![Modo de solo lectura de VS](../media/vs-read-only-notification.png)

6. **Enviar el vínculo a alguien**

    Envíe el vínculo por correo electrónico, Slack, Skype, etc., a los usuarios que quiera invitar. Tenga en cuenta que, dado el nivel de acceso que las sesiones de Live Share pueden proporcionar a los invitados, **solo se debe compartir con usuarios de confianza**, y piense detenidamente en las implicaciones de lo que va a compartir.

    > **Sugerencia de seguridad:** ¿Quiere conocer las implicaciones de seguridad de algunas de las características de Live Share? Consulte el artículo sobre [seguridad](../reference/security.md).

    Si el invitado al que invitó tiene preguntas, en el artículo "[Quickstart: Join your first session](../quickstart/join.md)" (Inicio rápido: Participación en una primera sesión) se proporciona información adicional sobre cómo prepararlo todo para participar como invitado.

7. **[Opcional] Aprobar al invitado**

    De manera predeterminada, los invitados participarán automáticamente en la sesión de colaboración y se le notificará cuando estén listos para trabajar con usted. Si bien esta notificación le da la opción de quitarlos de la sesión, también puede optar por requerir una "aprobación" explícita para todo aquel que se una.

    Simplemente cambie **Herramientas > Opciones > Live Share > Requerir aprobación de invitados** a True para habilitar la característica. Una vez que active esta configuración, recibirá una notificación que le pedirá aprobar al invitado antes de que pueda participar.

    ![Solicitud de aprobación de participación en Visual Studio](../media/vs-join-approval.png)

    Consulte [Invitations and join access](../reference/security.md#invitations-and-join-access) (Invitaciones y acceso de participación) para más detalles sobre las consideraciones de seguridad en la invitación.

8. **Administrar la sesión de Live Share**
    
    Cuando el invitado haya abierto el vínculo a su sesión compartida en VS Code o Visual Studio, aparecerá en la lista de participantes en la ventana de herramientas de Live Share. Ahora puede ver en qué archivo se encuentra su invitado al lado de su nombre.  
    
    ![Ventana de herramientas de VS Live Share](../media/vs-live-share-tool-window-participant.png)

    La ventana de herramientas de Live Share le permite tener acceso a todas las características clave para administrar la sesión en un solo lugar. 

    > [!TIP]
    > ¿Ya no se puede ver la ventana de herramientas de Live Share durante las sesiones? Siempre puede ir a **Ver &gt; Otras ventanas &gt; Live Share** y buscarla.

### <a name="ending-the-collaboration-session"></a>Finalización de la sesión de colaboración

Como anfitrión, puede dejar de compartir completamente y finalizar la sesión de colaboración si hace clic en el botón de estado de sesión o de uso compartido (en la esquina superior derecha) y selecciona "End Collaboration Session" (Finalizar sesión de colaboración).

![Detener uso compartido](../media/vs-stop-sharing.png)

Todos los invitados recibirán una notificación de que finalizó la sesión. Una vez finalizada la sesión, los invitados ya no podrán acceder al contenido y los archivos temporales se borrarán automáticamente.

¿Tiene problemas para compartir recursos? Revise la [solución de problemas](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Participación en una sesión de colaboración

Después de descargar e instalar Visual Studio Live Share, los invitados solo deben realizar un par de pasos para participar en una sesión de colaboración hospedada. Hay dos maneras de participar: [a través del explorador](#join-via-the-browser) y [manualmente](#join-manually).

> **Sugerencia de seguridad:** Como invitado que participa en una sesión de colaboración, es importante comprender que los hosts pueden limitar el acceso a determinados archivos o características. ¿Quiere conocer las implicaciones de seguridad de algunas de las características y configuraciones de Live Share? Consulte el artículo sobre [seguridad](../reference/security.md).

### <a name="join-via-the-browser"></a>Participar a través del explorador

La manera más sencilla de participar en una sesión de colaboración es abrir el vínculo de la invitación en un explorador web. Esto es lo que puede esperar si sigue este flujo.

1. **Inicio de sesión**

    Después de instalar la extensión Live Share, querrá iniciar sesión para permitir que otros colaboradores sepan quién es usted. De manera predeterminada, Visual Studio usa su cuenta de personalización, por lo que puede omitir por completo este paso.

    Consulte [Inicio de sesión](#sign-in) para más detalles.

2. **Haga clic en el vínculo de la invitación o abra la invitación en el explorador**

    Ahora, basta con abrir (o volver a abrir) el vínculo de invitación en un explorador.

    > **Nota**: Si aún no ha instalado la extensión Live Share, se le mostrarán vínculos al Marketplace de la extensión. Instale la extensión, reinicie la herramienta e inténtelo de nuevo.

    Debería recibir una notificación en la que se indica que el explorador quiere iniciar una herramienta habilitada para Live Share. Si permite que inicie la herramienta seleccionada, se conectará a la sesión de colaboración una vez que se inicie.

    ![Página para participar](../media/join-page.png)

    Si el host está sin conexión, se le notificará en este momento. Después, puede ponerse en contacto con el host y pedirle que vuelva a compartir.

    > [!NOTE]
    > ¿Sigue teniendo problemas? Consulte [Participar manualmente](#join-manually).

3. **Colabore**

    Ya está. En unos instantes se conectará y podrá empezar a colaborar.

    Verá la transición del botón "Live Share" a convertirse en un "Estado de sesión". Consulte la información sobre el [estado de sesión](#session-states) que aparece a continuación para saber cuál es el aspecto.

    Luego pasará automáticamente al archivo que actualmente está editando el anfitrión una vez que se una por completo.

### <a name="join-manually"></a>Participar manualmente

También puede participar manualmente sin usar un explorador web, lo que puede ser útil cuando la herramienta que quiere usar ya está en ejecución, si quiere una herramienta distinta a la que usa con frecuencia o si, por alguna razón, tiene problemas para que los vínculos de invitación funcionen. El proceso es sencillo:

1. **Inicio de sesión**

    Después de instalar la extensión Live Share, querrá iniciar sesión para permitir que otros colaboradores sepan quién es usted. De manera predeterminada, Visual Studio usa su cuenta de personalización, por lo que puede omitir por completo este paso.

    Consulte [Inicio de sesión](#sign-in) para más detalles.

2. **Use el comando para participar**

    Simplemente vaya a **Archivo > Unirse a sesión de Live Share**

    ![Menú para participar de VS](../media/vs-join.png)

3. **Pegue el vínculo de invitación**

    Pegue la dirección URL de la invitación que le enviamos y confirme.

4. **¡Colabore!**

    Ya está. Debería estar conectado momentáneamente a la sesión de colaboración.

    Verá la transición del botón "Live Share" a convertirse en un "Estado de sesión". Consulte la información sobre el [estado de sesión](#session-states) que aparece a continuación para saber cuál es el aspecto.

    Luego pasará automáticamente al contenido que actualmente está editando el anfitrión una vez que se una por completo.

### <a name="leave-the-collaboration-session"></a>Salida de la sesión de colaboración

Como invitado, puede salir de la sesión de colaboración sin finalizarla para los demás invitados. Para ello, simplemente cierre la herramienta o haga clic en el botón de estado de sesión o de uso compartido y seleccione "Leave Collaboration Session" (Salir de la sesión de colaboración).

![Menú para participar de VS](../media/vs-leave-session.png)

Los archivos temporales se eliminar automáticamente, por lo que no es necesario hacer nada más.

¿Tiene problemas para participar en la sesión? Revise la [solución de problemas](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Edición conjunta

Una vez que un invitado se une a una sesión de colaboración, todos los colaboradores podrán, de manera inmediata, ver las ediciones y selecciones de los demás en tiempo real. Solo tiene que tomar un archivo del explorador de archivos y empezar a editarlo. Tanto los anfitriones como los invitados verán cuando esté haciendo las ediciones y podrán contribuir, con lo que será más sencillo iterar y llegar a las soluciones.

> [!NOTE]
> Participar en una sesión de colaboración de solo lectura impide que los invitados puedan editar los archivos. Un anfitrión puede [habilitar el modo de solo lectura cuando comparten la sesión](#share-a-project). Para saber si está participando en una sesión de solo lectura, un invitado debe mirar el [estado de sesión](#session-states).

![Captura de pantalla de una edición conjunta](../media/vs-coedit.png)

> [!NOTE]
> La edición conjunta tiene algunas limitaciones en ciertos lenguajes. Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características por lenguaje.

Más allá de los cursores y las ediciones, las selecciones que hace también son visibles para todos quienes participan en el mismo archivo. Esto facilita resaltar dónde puede haber problemas o transmitir ideas.

![Captura de pantalla que muestra elementos resaltados](../media/vs-highlight.png)

Mejor aún: usted y otros participantes pueden ir a cualquier archivo en el proyecto compartido. Puede editar en conjunto o de manera independiente, lo que significa que puede cambiar sin problemas entre la investigación, hacer pequeños ajustes y la edición totalmente colaborativa.

> [!NOTE]
> De manera predeterminada, Live Share también comparte los archivos abiertos externos a la solución compartida. Si quiere deshabilitar esta característica, actualice Compartir archivos externos en Herramientas &gt; Opciones &gt; Live Share a False.

Las ediciones resultantes se conservan en la máquina del anfitrión al guardar la sesión, por lo que no es necesario sincronizar, enviar cambios ni enviar archivos una vez que termine de editar. Las ediciones simplemente "están ahí".

> **Sugerencia de seguridad:** Como todos los participantes pueden navegar y editar archivos de manera independiente, como anfitrión, es posible que quiera restringir los archivos a los que pueden acceder los invitados en el proyecto a través de un archivo .vsls.json. Como invitado, también es importante tener en cuenta que es posible que no vea determinados archivos como resultado de esta configuración. Consulte [Control de la visibilidad y el acceso de archivos](../reference/security.md#controlling-file-access-and-visibility) para más información.

### <a name="changing-participant-flag-behaviors"></a>Cambio de los comportamientos de las marcas de los participantes

De manera predeterminada, Visual Studio Live Share muestra automáticamente una "marca" junto al cursor de un participante si mantiene el puntero sobre él, o cuando edite, resalte o mueva el cursor. En algunos casos, quizás prefiera cambiar este comportamiento. Para ello:

1. Vaya a **Herramientas > Opciones > Live Share**
2. Cambie la opción **Flag visibility** (Visibilidad de la marca) a una de las siguientes opciones:

| Opción | Comportamiento |
|--------|----------|
| OnHoverOnly | La marca solo es visible cuando mantiene el puntero sobre el cursor. |
| OnHoverOrActivity | Este es el valor predeterminado. La marca es visible cuando mantiene el puntero sobre el cursor o si el participante edita, resalta o mueve el cursor. |
| Siempre | La marca siempre está visible.

## <a name="following"></a>Seguimiento

Cada vez que esté en una sesión de colaboración, podrá ver las iniciales de cada participante en la esquina superior del editor, junto al botón de inicio de sesión. Mantenga el puntero sobre las iniciales para ver la información completa del participante.

![Captura de pantalla que muestra al usuario](../media/vs-person.png)

En ocasiones, puede que tenga que explicar un problema o diseño que abarque varios archivos o ubicaciones en el código. En estos casos, puede resultar útil seguir temporalmente a un compañero de trabajo mientras se mueve por el proyecto que se va a editar en conjunto. Es por esto que, como invitado, cuando participa en una sesión de colaboración, automáticamente "sigue" la ubicación de edición del anfitrión. Cuando siga a un participante, el editor se mantendrá sincronizado con el archivo abierto actualmente de ese usuario, su cursor y su posición de desplazamiento.

> [!NOTE]
> De manera predeterminada, Live Share también comparte los archivos abiertos externos a la solución compartida. Si quiere deshabilitar esta característica, actualice Compartir archivos externos en Herramientas &gt; Opciones &gt; Live Share a False.

Para facilitar salir del "modo de seguimiento" y empezar a editar por su cuenta, dejará de seguir participantes si ocurre alguna de estas situaciones:

1. Edita, mueve el cursor o hace alguna selección
2. Selecciona otro archivo

También puede dejar de seguir a alguien en cualquier momento si hace clic en las iniciales de la persona a la que sigue en la esquina superior derecha. Desaparecerá el círculo alrededor de las iniciales del participante que indica que lo sigue.

![Participante seguido en Visual Studio](../media/vs-pinned.png) ![Participante no seguido en Visual Studio](../media/vs-pin-hover.png)

Puede hacer clic en cualquier inicial en esta misma ubicación para seguir a cualquier anfitrión o invitado de la sesión de colaboración. Tenga en cuenta que si quiere ir a la ubicación de algún participante en lugar de seguirlo, solo debe hacer doble clic en sus iniciales.

## <a name="focusing"></a>Atracción de la atención de los participantes

En algunas ocasiones puede que quiera que todos quienes participan en una sesión de colaboración vean lo que está haciendo. Live Share le pide solicitar que todo el mundo "centre" su atención en usted con una notificación que les facilita la tarea de seguirle.

Solo basta con hacer clic en el botón de uso compartido o de estado de sesión en la esquina superior derecha y seleccionar "Atraer la atención de los participantes".

![Opción de menú para atraer la atención de los participantes](../media/vs-focus.png)

Todos los participantes de la sesión de colaboración recibirán una notificación de que solicita su atención.

![Notificación del sistema sobre atraer la atención de los participantes](../media/vs-focus-toast.png)

De ese modo, ellos pueden simplemente hacer clic en "Seguir" directo en la notificación cuando estén listos para centrar su atención en usted.

## <a name="co-debugging"></a>Depuración conjunta

La característica de depuración colaborativa de Visual Studio Live Share es una manera única y eficaz de depurar un problema. Más allá de permitir una experiencia de colaboración para solucionar problemas, también le brinda a usted y a otros participantes de la sesión la capacidad de investigar los problemas que puedan ser específicos del entorno al proporcionar una sesión de depuración compartida en la máquina del anfitrión.

> **Sugerencia de seguridad:** Como todos los participantes pueden navegar y editar archivos de manera independiente, como anfitrión, es posible que quiera restringir los archivos a los que pueden acceder los invitados en el proyecto a través de un archivo .vsls.json. También debe tener en cuenta que el acceso a la consola/REPL significa que los participantes pueden ejecutar comandos en su máquina, por lo que solo debe depurar en conjunto con personas de confianza. Como invitado, también es importante tener en cuenta que es posible que no pueda seguir al depurador, porque entra en ciertos archivos restringidos como resultado de esta configuración. Consulte [Control de la visibilidad y el acceso de archivos](../reference/security.md#controlling-file-access-and-visibility) para más información.

Usarlo es simple. El anfitrión de la sesión de colaboración simplemente necesita empezar a depurar a través de los medios usuales de Visual Studio.

![Botón de depuración de VS](../media/vs-debug-button.png)

Una vez que el depurador se asocia en el lado del anfitrión, también se ajustan automáticamente todos los invitados. Mientras hay una "sesión" de depuración ejecutándose en la máquina del anfitrión, todos los participantes se conectan a ella y tienen su propia vista.

> [!TIP]
> Si quiere modificar cómo y cuándo se realiza la depuración conjunta, puede cambiar los comportamientos predeterminados en la configuración en **Herramientas > Opciones > Live Share**.

![Depurador de VS asociado](../media/vs-debugger.png)

Cualquier persona puede desplazarse por el proceso de depuración, lo que permite cambiar sin problemas entre los colaboradores sin tener que negociar el control.

> [!NOTE]
> Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características de depuración por lenguaje o plataforma.

Cada colaborador puede investigar distintas variables, saltar a distintos archivos en la pila de llamadas, inspeccionar las variables e incluso agregar o quitar puntos de interrupción. Luego, las características de edición conjunta permiten que cada orador participante haga un seguimiento de dónde se encuentran ubicados los demás para brindar la capacidad única de cambiar sin complicaciones entre los distintos aspectos del problema que se investigan en simultáneo y la depuración colaborativa.

> [!NOTE]
> Mientras esté en una sesión de colaboración de solo lectura, un invitado no podrá desplazarse por el proceso de depuración. Sin embargo, sí puede agregar o quitar puntos de interrupción e inspeccionar variables.

> [!TIP]
> También puede participar en las sesiones de depuración de VS Code desde Visual Studio y viceversa. Consulte las [instrucciones de Visual Studio](vscode.md#co-debugging) para más información sobre la depuración conjunta.

### <a name="automatic-web-app-sharing"></a>Uso compartido automático de aplicaciones web

Mejor aún: de manera predeterminada para los proyectos de aplicación web de ASP.NET, si el proyecto del anfitrión está configurado para iniciar automáticamente un explorador web para conectarse a la aplicación web en ejecución cuando se realiza la depuración, Live Share hará lo mismo de manera automática en la máquina de cada invitado. Esto se hace de manera segura y la aplicación web remota solo está disponible para los invitados durante la sesión de depuración de forma predeterminada.

Consulte [Uso compartido de un servidor](#share-a-server) para información sobre cómo compartir el acceso a un servidor para otros tipos de proyectos o por lo que dure la sesión.

> [!TIP]
> Si no le gusta el comportamiento predeterminado de uso compartido del explorador y quiere cambiarlo, puede actualizar la información en **Herramientas > Opciones > Live Share**.

![Animación de la depuración simultánea](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Cambio cuando Visual Studio se une a las sesiones de depuración

De manera predeterminada, como invitado, se lo asociará automáticamente a las sesiones de depuración cuando el anfitrión las comparta. Sin embargo, en algunos casos, puede considerar que este comportamiento es problemático. Afortunadamente, puede cambiarlo de la siguiente manera:

1. Vaya a **Herramientas > Opciones > Live Share**
2. Cambie la opción **Join debug session** (Participar en la sesión de depuración) a una de las siguientes:

| Opción | Comportamiento |
|--------|----------|
| Automático | El valor predeterminado. Como invitado, participará automáticamente en cualquier sesión de depuración que inicie el anfitrión. |
| Solicitado | Como invitado, se le preguntará si quiere participar en una sesión de depuración compartida cuando la inicie el anfitrión. |
| Manual | Como invitado, deberá participar manualmente en cualquier sesión de depuración. Consulte [Desasociación y nueva asociación](#detaching-and-reattaching).|

### <a name="detaching-and-reattaching"></a>Desasociación y nueva asociación

Es posible que un invitado quiera detener temporalmente la depuración. Afortunadamente, puede simplemente hacer clic en el icono "Detener" de la barra de herramientas de depuración para desasociar el depurador sin afectar al anfitrión ni a otros invitados.

Si actualizó la configuración y ya no se asocia de manera automática o si simplemente quiere volver a asociarse más adelante, basta con seleccionar la sesión de depuración en ejecución que quiere en el menú desplegable "Select Startup Item" (Seleccionar elemento de inicio)

![Botón de depuración de VS](../media/vs-select-reattach.png)

y hacer clic en él para asociarse.

![Botón de depuración de VS](../media/vs-reattach.png)

## <a name="share-a-server"></a>Uso compartido de un servidor

De vez en cuando, como anfitrión de la sesión de colaboración, puede darse el caso de que quiera compartir con los invitados servidores o servicios locales adicionales. Esto puede ir desde otros puntos de conexión de RESTful a bases de datos u otros servidores. Visual Studio Live Share le permite especificar un número de puerto local, darle un nombre si así lo quiere y compartirlo con todos los invitados.

A continuación, los usuarios podrán acceder al servidor que compartió en ese puerto desde su propia máquina local exactamente en el mismo puerto. Por ejemplo, si compartió un servidor web **en ejecución en el puerto 3000**, el invitado puede acceder a ese mismo servidor web en ejecución en su **propia máquina** en http://localhost:3000. Esto se logra a través de un túnel SSH o SSL entre el anfitrión y los invitados y se autentica a través del servicio, por lo que puede estar seguro de que solo quienes participen de la sesión de colaboración tienen acceso.

> **Sugerencia de seguridad:** Como anfitrión, debe ser muy selectivo con los puertos que comparte con los invitados y limitarse a los puertos de aplicación (en lugar de compartir un puerto de sistema). En el caso de los invitados, los puertos compartidos se comportarán exactamente igual que si el servidor o servicio se estuviese ejecutando en su propia máquina. Esto es muy útil, pero podría ser también arriesgado si es que se comparte el puerto incorrecto.

Por motivos de seguridad, solo los servidores que se ejecutan en los puertos que especifica estarán disponibles a los demás invitados. Afortunadamente, es fácil agregar uno como el **anfitrión** de la sesión de colaboración. Esta es la manera de hacerlo:

1. Haga clic en el botón de estado de sesión o de uso compartido en la esquina superior derecha y seleccione "Manage Shared Local Serves" (Administrar servidores locales compartidos).

    ![Administrar servidores locales compartidos](../media/vs-share-local-servers.png)

2. En el cuadro de diálogo que aparece, haga clic en "Agregar" y escriba el número de puerto en que el servidor se ejecuta localmente, escriba un nombre, presione ENTRAR y luego Aceptar.

    ![Administrar servidores locales compartidos](../media/vs-manage-local-shared-servers.png)

Ya está. El servidor en el puerto que especificó ahora se asignará al localhost de cada invitado en el mismo puerto (a menos que ya esté ocupado).

Si el puerto ya está en uso en la máquina de un invitado, se seleccionará otro automáticamente. Por fortuna, como invitado puede ver una lista de los puertos actualmente compartidos (por nombre, si se especificó) si hace clic en el botón de estado de sesión o de uso compartido que se encuentra en la esquina superior derecha y selecciona "View Shared Local Servers" (Ver servidores locales compartidos).

![Ver servidores locales compartidos](../media/vs-view-shared-servers.png)

Tenga en cuenta que *los invitados no pueden* controlar qué puertos de la máquina del anfitrión se comparten por motivos de seguridad.

Para **dejar** de compartir un servidor local, basta con que el anfitrión haga clic en el botón de estado de sesión o de uso compartido en la esquina superior derecha como se indicó anteriormente, seleccione "Manage Shared Local Servers" (Administrar servidores locales compartidos), seleccione el puerto adecuado y haga clic en "Quitar".

## <a name="share-a-terminal"></a>Uso compartido de un terminal

El desarrollo moderno hace un uso frecuente de una amplia gama de herramientas de línea de comandos. Afortunadamente, como anfitrión, Live Share le permite, de forma opcional, "compartir un terminal" con los invitados. El terminal compartido puede ser de solo lectura o totalmente colaborativo, para que tanto usted como los invitados puedan ejecutar comandos y ver los resultados. Puede dar a los invitados visibilidad sobre la salida del terminal o permitirles obtener experiencias prácticas y ejecutar pruebas, compilaciones o incluso evaluar la prioridades de los problemas específicos del entorno que solo aparecen en su máquina.

Sin embargo, los terminales **no** se comparten de manera predeterminada, porque dan a los invitados al menos acceso de solo lectura a la salida de los comandos que usted ejecuta (si es que no la capacidad de ejecutar los comandos mismos). De este modo, puede ejecutar libremente los comandos en los terminales locales sin riesgo y solo compartirlos cuando de verdad tenga que hacerlo. Además, solo los anfitriones pueden iniciar los terminales compartidos para impedir que los invitados inicien uno y hagan algo inesperado o sin supervisión.

Como anfitrión, puede compartir un terminal si hace clic en el botón de uso compartido o de estado de sesión en la esquina superior derecha y selecciona uno de los elementos de menú "Share Terminal" (Compartir terminal).

![Menú del terminal](../media/vs-terminal-menu.png)

En este momento, puede seleccionar un terminal de solo lectura o de lectura y escritura en el menú. Si el terminal es de lectura/escritura, todos los participantes pueden escribir en el terminal, incluido el anfitrión, lo que permite intervenir fácilmente si un invitado hace algo que no le gusta. Sin embargo, para estar seguros, debería **darle acceso de lectura/escritura a los invitados solo cuando sabe que realmente lo necesitan**  y limitarse a los terminales de solo lectura en escenarios donde quiere que un invitado solo vea la salida de los comandos que ejecuta.

> [!NOTE]
> Si la sesión de colaboración está en modo de solo lectura, el anfitrión solo puede compartir los terminales de solo lectura.

Una vez que haya seleccionado el tipo de terminal compartido que quiere iniciar, aparecerá un terminal compartido nuevo para todos los participantes que tengan los permisos correctos. Si bien Visual Studio Code tiene integrada la compatibilidad con el terminal, Visual Studio no la tiene de manera predeterminada. Por lo tanto, de manera predeterminada, aparecerá una ventana nueva con el terminal. Sin embargo, si está instalada la [extensión Whack Whack](https://marketplace.visualstudio.com/items?itemName=DanielGriffen.WhackWhackTerminal), Live Share creará un terminal integrado. Visual Studio le entregará un vínculo para su instalación la primera vez que inicie o se una a un terminal compartido.

![Notificación del sistema sobre la instalación del terminal](../media/vs-terminal-install.png)

Para finalizar la sesión del terminal, solo debe escribir exit (salir) o cerrar la ventana del terminal y se desconectará a cada uno de los participantes.

## <a name="session-states"></a>Estados de sesión

Una vez que inicie una sesión de colaboración o que se una a ella y tenga acceso al contenido compartido, el botón "Live Share" que se encuentra en la esquina superior derecha actualizará su apariencia para reflejar el estado de la sesión de colaboración activa.

Estos son los estados que verá habitualmente:

| Estado | Botón | DESCRIPCIÓN |
|-------|--------|-------------|
| Inactivo | ![Estado de VS: inactivo](../media/vs-status-share.png) | No hay ninguna sesión de colaboración activa y no se comparte nada. |
| Anfitrión: Uso compartido en curso | ![Estado de VS: uso compartido en curso](../media/vs-status-sharing.png) | Se inicia una sesión de colaboración y pronto se empezará a compartir contenido. |
| Anfitrión: Uso compartido de recursos | ![Estado de VS: uso compartido activo ](../media/vs-status-active.png) | Hay una sesión de colaboración activa y se comparte contenido. |
| Anfitrión: Uso compartido de solo lectura | ![Estado de VS: uso compartido de solo lectura](../media/vs-status-sharing-read-only.png)| Se comparte una sesión de colaboración de solo lectura. |
| Invitado: Participación en la sesión | ![Estado de VS: participación](../media/vs-status-joining.png) | Participación en una sesión de colaboración existente. |
| Invitado: participando | ![Estado de VS: participando](../media/vs-status-joined.png) | Se conectó y está participando en una sesión de colaboración activa y recibe contenido compartido. |
| Invitado: Participando en solo lectura | ![Estado de VS: participando en solo lectura](../media/vs-status-joined-read-only.png) | Se conectó y está participando en una sesión de colaboración de solo lectura activa. |

## <a name="guest-limitations"></a>Limitaciones de los invitados

Si bien actualmente los invitados pueden encontrarse con algunas limitaciones al usar las características ya descritas, los anfitriones de la sesión de colaboración conservan toda la funcionalidad de su herramienta preferida. Para obtener más información, vea las secciones siguientes:

- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Compatibilidad con extensiones](../reference/extensions.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>Pasos siguientes

Consulte estos artículos adicionales para obtener más información.

- [Inicio rápido: Uso compartido de un primer proyecto](../quickstart/share.md)
- [Inicio rápido: Participación en una primera sesión](../quickstart/join.md)
- [Colaboración mediante Visual Studio Code](vscode.md)
- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
