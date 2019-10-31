---
title: 'Colaboración mediante Visual Studio Code: Visual Studio Live Share | Microsoft Docs'
description: Un conjunto de procedimientos de colaboración para Visual Studio Code y Live Share.
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: a720a93f0e98b28400a62874c26f3f4cdda57ef7
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179984"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>Cómo colaborar con Visual Studio Code

¿Está listo para empezar a colaborar con Live Share en VS Code?  Si es así, está en el lugar correcto. En este artículo, lo guiaremos para que aprenda a usar algunas de las características específicas de la extensión Visual Studio Live Share para Visual Studio Code.

Tenga en cuenta que todas las actividades de colaboración que se describen aquí implica un único **anfitrión de la sesión de colaboración** y uno o varios **invitados**. El anfitrión es la persona que inicia la sesión de colaboración, mientras que las personas que participan en ella son invitados.

*¿Busca un resumen abreviado? En su lugar, consulte las guías de inicio rápido de [compartir](../quickstart/share.md) o [unirse](../quickstart/join.md) .*

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

## <a name="installation"></a>Instalación

Antes de empezar, deberá asegurarse de tener instalada una versión de Visual Studio Code que cumpla los requisitos principales de Live Share. Necesitará **Visual Studio Code (1.22.0 superior)** que se ejecute en:

- **Windows**: 7, 8,1 o 10

- **MacOS**: Sierra (10,12) y versiones posteriores.
    - _El Capitan (10.11) y versiones anteriores no son compatibles actualmente debido a los [requisitos de .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872315)._

- **Linux**: 64 de Ubuntu Desktop 16.04 +, Fedora Workstation 27 +, 8 a 7

    - Live Share requiere varios [requisitos previos de Linux](#linux-install-steps) que quizás se le pida instalar.
    - _Linux de 32 bits no es compatible debido a los [requisitos de .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872314)._
    - ARM tampoco se admite actualmente.
    - Consulte el artículo [Detalles de la instalación de Linux](../reference/linux.md) para ver los detalles sobre cómo usar las distribuciones de nivel inferior y otras.

Después, descargar e instalar la extensión de Visual Studio Live Share es muy sencillo:

1. Instalación de <a href="https://code.visualstudio.com/">Visual Studio Code</a>
2. [Descargue](https://aka.ms/vsls-dl/vscode) e instale la extensión Visual Studio Live Share desde Marketplace.
3. Recarga de Visual Studio Code
4. Espere que las dependencias se descarguen e instalen (consulte la barra de estado).<br/>
    ![Finalización de la instalación](../media/vscode-finishing-install.png)
5. **Linux**: Si ve una notificación sobre la instalación de bibliotecas que faltan:
    1. Haga clic en "Instalar" en la notificación.
    2. Escriba la contraseña de administrador (sudo) cuando se le solicite.
    3. Cuando termine, reinicie VS Code.

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](../troubleshooting.md).

[![Descarga](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Pasos de instalación de Linux

Linux es un entorno altamente variable y con el gran número de distribuciones y entornos de escritorio puede ser complicado hacerlo funcionar. Si se limita a las versiones compatibles de **Ubuntu Desktop** (16.04 o posteriores) o de **Fedora Workstation** (27 o posteriores), **CentOS 7** y solo usa **distribuciones oficiales de VS Code**, debería encontrar que el proceso es sencillo. Sin embargo, en caso de que use una configuración no estándar o una configuración de nivel inferior, es posible que se encuentre (o no) con algunas interrupciones. Consulte [Detalles de la instalación de Linux](../reference/linux.md) para obtener más información.

#### <a name="install-linux-prerequisites"></a>Instalación de los requisitos previos de Linux

En algunas distribuciones de Linux faltan bibliotecas que Live Share necesita para funcionar. De manera predeterminada, Live Share intenta detectar e instalar los requisitos previos de Linux. Verá una notificación del sistema cuando Live Share encuentre un problema que pueda provenir de la falta de bibliotecas en la que se le pedirá permiso para instalarlas.

![Notificación del sistema que muestra el mensaje de que faltan algunos requisitos previos de Linux](../media/vscode-linux-prereq-missing.png)

Al hacer clic en "Instalar", aparecerá una ventana de terminal en la que tendrá que escribir la contraseña de administrador (sudo) para continuar. Si todo se completa correctamente, todo debería estar listo una vez que reinicie Visual Studio Code. También puede consultar las **[sugerencias de distribución](../reference/linux.md#tips-by-distribution)** para ver otras indicaciones y soluciones alternativas que puedan existir.

Si ve un mensaje que indica que el script no es compatible con la distribución, consulte las **[sugerencias para las distribuciones compatibles con la comunidad](../reference/linux.md#tips-for-community-supported-distros)** para ver la información que la comunidad nos ha compartido.

Si **prefiere que VS Code no ejecute el comando por usted**, también puede optar por volver a ejecutar la versión más reciente de este script en cualquier momento de manera manual mediante la ejecución del comando siguiente desde una ventana del terminal:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Integración del explorador de Linux

Por lo general, Visual Studio Live Share **no necesita pasos de instalación adicionales** para habilitar la integración del explorador en Linux.

Si bien es poco habitual, en ciertas distribuciones **es posible que reciba una notificación de que se necesita su contraseña de administración (sudo)** para completar el proceso de instalación. Aparecerá una ventana de terminal en la que se le indicará que se instalará el iniciador del explorador. Para cerrar la ventana de terminal, solo debe escribir la contraseña cuando se le solicite y presionar ENTRAR una vez que la instalación termine.

**[Aquí](../reference/linux.md#linux-browser-integration)** puede leer más sobre por qué es necesario este paso y dónde coloca los archivos Live Share. Observe que, incluso si no puede hacer funcionar la integración del explorador, de todos modos puede **[participar manualmente en las sesiones de colaboración](../how-to-guides/vscode.md#join-manually)** .

## <a name="sign-in"></a>Inicio de sesión

Para poder colaborar, deberá iniciar sesión en Visual Studio Live Share de manera que todos sepan quién es usted. Esto no es más que una medida de seguridad y **no** significa que se inscriba en ninguna actividad de marketing u otro tipo de investigación. Puede iniciar sesión con una cuenta personal de Microsoft (por ejemplo, @outlook.com), una cuenta profesional o educativa (AAD) con el respaldo de Microsoft, o bien una cuenta de GitHub. Es fácil iniciar sesión.

**Haga clic** en el elemento de barra de estado "Live share" o presione **Ctrl + Mayús + P/Cmd + Mayús + P** y seleccione el comando "Live Share: iniciar sesión con el explorador".

![Botón de inicio de sesión de VS Code](../media/vscode-sign-in-button.png)

Aparecerá una notificación para pedirle que inicie sesión con el explorador web. Si hace clic en "launch sign in" (Iniciar inicio de sesión) se abrirá un explorador que puede usar para completar el proceso de inicio de sesión. Cuando termine, simplemente cierre el explorador.

![Notificación del sistema en la que solicita el inicio de sesión con un explorador web](../media/vscode-sign-in-toast.png)

> **Usuarios de Linux:** Es posible que se le pida que escriba un código de usuario si usa una versión anterior de Live Share (v 0.3.295 o posterior). Actualice a la versión más reciente de la extensión o haga clic en el vínculo "¿Tiene problemas?" después de iniciar sesión para ver el código. Para información más detallada, [consulte a continuación](#sign-in-using-a-user-code).

#

> **Sugerencia avanzada:** La configuración de `liveshare.account` y `liveshare.accountProvider` permite seleccionar la cuenta que se debe usar para el inicio de sesión automático en caso de que haya credenciales almacenadas en caché para varias cuentas disponibles.
> Por ejemplo, imagine que trabaja en dos proyectos en los que quiere iniciar sesión con identidades distintas. En la configuración del área de trabajo de VSCode, puede configurar la opción `liveshare.account` para distintas direcciones de correo electrónico en cada directorio de proyecto. De este modo, se asegurará de que la sesión de cada una de ellas se inicia automáticamente con la cuenta adecuada. La opción `liveshare.accountProvider` se puede establecer tanto en `"microsoft"` como `"github"` si usa la misma dirección de correo electrónico con varios proveedores.

Si Visual Studio Code no acepta su inicio de sesión una vez que completa el proceso en el explorador, consulte [Inicio de sesión con un código de usuario](#sign-in-using-a-user-code). En caso contrario, revise la [solución de problemas](../troubleshooting.md#sign-in) para ver más sugerencias.

### <a name="sign-in-using-a-user-code"></a>Inicio de sesión con un código de usuario

Si tiene problemas para que VS Code acepte un inicio de sesión completado, puede escribir un "código de usuario" en su lugar.

1. Presione **Ctrl + Mayús + P/Cmd + Mayús + P** y ejecute el comando "Live Share: iniciar sesión con código de usuario".

2. Debería aparecer un explorador donde completar el proceso de inicio de sesión.

    > [!NOTE]
    > Si no aparece automáticamente, abra [esta ubicación](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) en un explorador e inicie sesión.

3. Una vez que termine, haga clic en "Having trouble? Click here for user code directions" (¿Problemas? Haga clic aquí para instrucciones sobre el código de usuario) para ver el código de usuario.

    ![Imagen del código de usuario en un explorador](../media/vscode-user-code-browser.png)

4. Copie el código de usuario.

5. Por último, péguelo en el campo de entrada que apareció cuando ejecutó el comando y presione ENTRAR para completar el proceso de inicio de sesión.

    ![Imagen del campo de entrada de código de usuario](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Uso del viewlet de Live Share

Después de instalar Visual Studio Live Share, se agregará una pestaña personalizada a la barra de actividades de VS Code. En esta pestaña, podrá acceder a todas las funciones de Live Share para colaborar. Además, cuando se une a una sesión de colaboración o la comparte, también aparecerá una vista en la pestaña Explorador para que acceda a todas esas funciones.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

Con estas vistas, puede ver la ubicación de un participante en el código compartido, hacer clic en un participante para seguirlo, atraer la atención de los participantes, acceder a terminales y servidores compartidos, etc.

## <a name="using-the-scoped-command-menu"></a>Uso del menú de comandos con ámbito

Además, todas las funciones de Visual Studio Live Share están disponibles desde la "paleta de comandos" de Visual Studio Code a la que se puede acceder con Ctrl+Mayús+P o Cmd+Mayús+P o F1. Para encontrar una lista completa de los comandos, escriba "live share".

Como esta lista puede ser larga, quizás le resulte más fácil usar un menú de comandos con ámbito que está disponible en la barra de estado. Si hace clic en el icono de inicio de sesión/estado de sesión de la barra de estado se abrirá una lista contextualizada de los comandos disponibles para su uso.

![Icono de estado de sesión de VS Code](../media/vscode-share-state.png)

## <a name="share-a-project"></a>Uso compartido de un proyecto

Después de descargar e instalar Visual Studio Live Share, siga estos pasos para iniciar una sesión de colaboración e invitar a un compañero de trabajo a trabajar con usted.

1. **Iniciar sesión**

    Después de instalar la extensión Live Share, recargar y esperar a que se terminen de instalar las dependencias, querrá iniciar sesión para que otros colaboradores sepan quién es. Consulte [Inicio de sesión](#sign-in) para más detalles.

2. **Abrir una carpeta**

    Use el flujo de trabajo normal para abrir una carpeta, un proyecto o una solución que quisiera compartir con los invitados.

3. **[Opcional] Actualizar los archivos ocultos o excluidos**

    De manera predeterminada, Live Share **oculta** a los invitados los archivos o carpetas a los que se hace referencia en los archivos .gitignore de las carpetas compartidas. **Ocultar** un archivo evita que aparezca en el árbol de archivos del invitado. **Excluir** un archivo aplica una regla más estricta que impedirá que Live Share lo abra para el invitado en situaciones como ir a una definición o cuando el archivo se depura paso a paso por instrucciones mientras depura o se "sigue". Si quiere ocultar o excluir otros archivos, puede agregar un archivo **.vsls.json** al proyecto con esta configuración. Consulte [Control de la visibilidad y el acceso de archivos](../reference/security.md#controlling-file-access-and-visibility) para más información.

4. **Iniciar una sesión de colaboración**

    Ahora, solo tiene que **hacer clic en** el elemento de barra de estado "Live share" o presionar **Ctrl + Mayús + P/Cmd + Mayús + P** y seleccionar "Live Share: iniciar una sesión de colaboración (recurso compartido)".

    ![Botón Compartir](../media/vscode-share-button-new.png)

    > [!NOTE]
    > La primera vez que comparta, es posible que el software de firewall de escritorio le pida que permita que el agente de Live Share abra un puerto. Aceptar esto es totalmente opcional, pero habilita un "modo directo" seguro para mejorar el rendimiento cuando la persona con la que trabaja se encuentra en la misma red que usted. Consulte [Cambiar el modo de conexión](../reference/connectivity.md#changing-the-connection-mode) para más detalles.

    Un vínculo a la invitación se copiará automáticamente en el Portapapeles. Cuando se abre en un explorador, este vínculo permite que otros usuarios se unan a una sesión de colaboración donde se les comparte contenido de estas carpetas.

    También verá la transición del elemento de la barra de estado "Live Share" para representar el estado de sesión. Consulte la información sobre el [estado de sesión](#session-states) que aparece a continuación para saber cuál es el aspecto.

    Tenga en cuenta que si necesita obtener nuevamente el vínculo de la invitación una vez que haya empezado a compartir los recursos, puede acceder a él otra vez si hace clic en el icono de estado de sesión de la barra de estado y selecciona "Invite Others (Copy Link)" (Invitar a otros [copiar vínculo]).

5. **[Opcional] Habilitar el modo de solo lectura**

    Una vez iniciada la sesión de colaboración, puede establecerla para que sea de solo lectura a fin de evitar que los invitados realicen cambios en el código que se comparte.

    Después de compartir, recibirá una notificación en la que se indica que el vínculo de invitación se ha copiado en el Portapapeles. Después, puede seleccionar la opción para hacer que la sesión sea de solo lectura.

    ![Modo de solo lectura de VS](../media/vscode-read-only-toast.png)

6. **Enviar el vínculo a alguien**

    Envíe el vínculo por correo electrónico, Slack, Skype, etc., a los usuarios que quiera invitar. Tenga en cuenta que, dado el nivel de acceso que las sesiones de Live Share pueden proporcionar a los invitados, **solo se debe compartir con usuarios de confianza**, y piense detenidamente en las implicaciones de lo que va a compartir.

    > **Sugerencia de seguridad:** ¿Quiere comprender las implicaciones de seguridad de algunas de las características de Live Share? Consulte el artículo sobre [seguridad](../reference/security.md).

    Si el invitado al que ha invitado tiene preguntas, el artículo "[Inicio rápido: unirse a su primera sesión](../quickstart/join.md)" proporciona más información sobre cómo ponerse en marcha como invitado.

7. **[Opcional] Aprobar al invitado**

    De manera predeterminada, los invitados participarán automáticamente en la sesión de colaboración y se le notificará cuando estén listos para trabajar con usted. Si bien esta notificación le da la opción de quitarlos de la sesión, también puede optar por requerir una "aprobación" explícita para todo aquel que se una.

    Para habilitar esta característica, simplemente agregue lo siguiente a settings.json:

         "liveshare.guestApprovalRequired": true

    Una vez que active esta configuración, recibirá una notificación que le pedirá aprobar al invitado antes de que pueda participar.

    ![Solicitud de aprobación de participación en Visual Studio Code](../media/vscode-join-approval.png)

    Consulte [Invitations and join access](../reference/security.md#invitations-and-join-access) (Invitaciones y acceso de participación) para más detalles sobre las consideraciones de seguridad en la invitación.

¡Y listo!

### <a name="stop-the-collaboration-session"></a>Detención de la sesión de colaboración

Como anfitrión, puede dejar de compartir completamente y finalizar la sesión de colaboración en cualquier momento si abre la vista de Live Share en el Explorador o en la pestaña personalizada Live Share y selecciona el icono "Stop collaboration session" (Detener sesión de colaboración).

![Detener sesión de colaboración](../media/vscode-end-collaboration-viewlet.png)

Todos los invitados recibirán una notificación de que finalizó la sesión.  Una vez finalizada la sesión, los invitados ya no podrán acceder al contenido y los archivos temporales se borrarán automáticamente.

¿Tiene problemas para compartir recursos? Revise la [solución de problemas](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Participación en una sesión de colaboración

Después de descargar e instalar Visual Studio Live Share, los invitados solo deben realizar un par de pasos para participar en una sesión de colaboración hospedada. Hay dos maneras de participar: [a través del explorador](#join-via-the-browser) y [manualmente](#join-manually).

> **Sugerencia de seguridad:** Como invitado que se une a una sesión de colaboración, es importante comprender que los hosts pueden restringir el acceso a determinados archivos o características. ¿Quiere conocer las implicaciones de seguridad de algunas de las características y configuraciones de Live Share? Consulte el artículo sobre [seguridad](../reference/security.md).

### <a name="join-via-the-browser"></a>Participar a través del explorador

La manera más sencilla de participar en una sesión de colaboración es abrir el vínculo de la invitación en un explorador web. Esto es lo que puede esperar si sigue este flujo.

1. **Iniciar sesión**

    Después de instalar la extensión Live Share, recargar y esperar a que se terminen de instalar las dependencias, querrá iniciar sesión para que otros colaboradores sepan quién es. Consulte [Inicio de sesión](#sign-in) para más detalles.

2. **Haga clic en el vínculo de la invitación o abra la invitación en el explorador**

    Ahora, basta con abrir (o volver a abrir) el vínculo de invitación en un explorador.

    > **Nota**: Si aún no ha instalado la extensión de Live Share, se le mostrarán vínculos a la extensión Marketplace. Instale la extensión, reinicie la herramienta e inténtelo de nuevo.

    Debería recibir una notificación en la que se indica que el explorador quiere iniciar una herramienta habilitada para Live Share. Si permite que inicie la herramienta seleccionada, se conectará a la sesión de colaboración una vez que se inicie.

    ![Página para participar](../media/join-page.png)

    Si el host está sin conexión, se le notificará en este momento. Después, puede ponerse en contacto con el anfitrión y pedirle que vuelva a compartir.

    > [!NOTE]
    > Asegúrese de haber **iniciado la herramienta al menos una vez** después de instalar la extensión Visual Studio Live Share y permitido que la instalación se realice completamente antes de abrir o volver a abrir la página de invitación. ¿Sigue teniendo problemas? Consulte [Participar manualmente](#join-manually).

3. **Colabore**

    Ya está. En unos instantes se conectará y podrá empezar a colaborar.

    Verá la transición del botón "Live Share" a convertirse en un "Estado de sesión". Consulte la información sobre el [estado de sesión](#session-states) que aparece a continuación para saber cuál es el aspecto.

    Luego pasará automáticamente al archivo que actualmente está editando el anfitrión una vez que se una por completo.

### <a name="join-manually"></a>Participar manualmente

También puede participar manualmente sin usar un explorador web, lo que puede ser útil cuando la herramienta que quiere usar ya está en ejecución, si quiere una herramienta distinta a la que usa con frecuencia o si, por alguna razón, tiene problemas para que los vínculos de invitación funcionen. El proceso es sencillo:

1. **Iniciar sesión**

    Después de instalar la extensión Live Share, recargar y esperar a que se terminen de instalar las dependencias, querrá iniciar sesión para que otros colaboradores sepan quién es. Consulte [Inicio de sesión](#sign-in) para más detalles.

2. **Use el comando para participar**

    Abra la pestaña personalizada Live Share en la barra de actividades de VS Code y seleccione la entrada o el icono "Join collaboration session…" (Participar en la sesión de colaboración).

    ![Icono para participar del viewlet](../media/vscode-join-viewlet.png)

3. **Pegue el vínculo de invitación**

    Pegue la dirección URL de la invitación que le enviamos y presione ENTRAR para confirmar.

4. **¡Colabore!**

    Ya está. Debería estar conectado momentáneamente a la sesión de colaboración.

    Verá la transición del botón "Live Share" a convertirse en un "Estado de sesión". Consulte la información sobre el [estado de sesión](#session-states) que aparece a continuación para saber cuál es el aspecto.

    Luego pasará automáticamente al archivo que actualmente está editando el anfitrión una vez que se una por completo.

### <a name="leave-the-collaboration-session"></a>Salida de la sesión de colaboración

Como invitado, puede salir de la sesión de colaboración sin finalizarla para los demás invitados. Para ello, simplemente cierre la ventana de VS Code. Si prefiere mantener abierta la ventana, puede abrir la vista Explorador de Live Share o la pestaña personalizada Live Share y seleccionar el icono "Leave collaboration session" (Salir de la sesión de colaboración).

![Icono para salir de la sesión](../media/vscode-leave-session-viewlet.png)

Los archivos temporales se eliminar automáticamente, por lo que no es necesario hacer nada más.

¿Tiene problemas para participar en la sesión? Revise la [solución de problemas](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Edición conjunta

Una vez que un invitado se une a una sesión de colaboración, todos los colaboradores podrán, de manera inmediata, ver las ediciones y selecciones de los demás en tiempo real. Solo tiene que tomar un archivo del explorador de archivos y empezar a editarlo. Tanto los anfitriones como los invitados verán cuando esté haciendo las ediciones y podrán contribuir, con lo que será más sencillo iterar y llegar a las soluciones.

> [!NOTE]
> Participar en una sesión de colaboración de solo lectura impide que los invitados puedan editar los archivos. Un anfitrión puede [habilitar el modo de solo lectura cuando comparten la sesión](#share-a-project). Para saber si está participando en una sesión de solo lectura, un invitado debe mirar el [estado de sesión](#session-states).

![Captura de pantalla de una edición conjunta](../media/vscode-coedit.png)

> [!NOTE]
> La edición conjunta tiene limitaciones en ciertos lenguajes. Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características por lenguaje.

Más allá de los cursores y las ediciones, las selecciones que hace también son visibles para todos quienes participan en el mismo archivo. Esto facilita resaltar dónde puede haber problemas o transmitir ideas.

![Captura de pantalla que muestra elementos resaltados](../media/vscode-highlight.png)

Mejor aún: usted y otros participantes pueden ir a cualquier archivo en el proyecto compartido. Puede editar en conjunto o de manera independiente, lo que significa que puede cambiar sin problemas entre la investigación, hacer pequeños ajustes y la edición totalmente colaborativa.

Las ediciones resultantes se conservan en la máquina del anfitrión al guardar la sesión, por lo que no es necesario sincronizar, enviar cambios ni enviar archivos una vez que termine de editar. Las ediciones simplemente "están ahí".

> **Sugerencia de seguridad:** Dado que todos los participantes pueden navegar y editar archivos de forma independiente, como un host, puede que desee restringir los archivos a los que los invitados pueden acceder en el proyecto a través de un archivo. vsls. JSON. Como invitado, también es importante tener en cuenta que es posible que no vea determinados archivos como resultado de esta configuración. Consulte [Control de la visibilidad y el acceso de archivos](../reference/security.md#controlling-file-access-and-visibility) para más información.

### <a name="changing-participant-flag-behaviors"></a>Cambio de los comportamientos de las marcas de los participantes

De manera predeterminada, Visual Studio Live Share muestra automáticamente una "marca" junto al cursor de un participante si mantiene el puntero sobre él, o cuando edite, resalte o mueva el cursor. En algunos casos, quizás prefiera cambiar este comportamiento.

Simplemente debe **editar settings.json** (Archivo > Preferencias > Configuración), agregar una de las líneas siguientes y, luego, reiniciar VS Code:

| Parámetro | Comportamiento |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | La marca solo es visible cuando mantiene el puntero sobre el cursor. |
| ``"liveshare.nameTagVisibility":"Activity"`` | Este es el valor predeterminado. La marca es visible cuando mantiene el puntero sobre el cursor o si el participante edita, resalta o mueve el cursor. |
| ``"liveshare.nameTagVisibility":"Always"`` | La marca siempre está visible. |

## <a name="following"></a>Seguimiento

En ocasiones necesitará explicar un problema o diseño que abarque varios archivos o ubicaciones en el código. En estos casos, puede ser útil seguir temporalmente a un compañero de trabajo mientras se mueve por el proyecto. Es por esto que, cuando se una a una sesión de colaboración, "seguirá" automáticamente al anfitrión. Cuando siga a alguien, el editor se mantendrá sincronizado con el archivo abierto actualmente de ese usuario y su posición de desplazamiento.

> [!NOTE]
> De manera predeterminada, Live Share también comparte los archivos abiertos externos a la carpeta compartida. Si quiere deshabilitar esta característica, actualice Live Share `liveshare.shareExternalFiles` a `false` en settings.json.

Para empezar a seguir un participante (ya sea un host o invitado), haga clic en su nombre en la lista de participantes en la vista del explorador de Live Share o en la pestaña personalizada. El círculo situado junto a su nombre se rellenará para indicar que está siguiendo.

![Opción de seguir en el viewlet de VS Code](../media/vscode-follow-multiple-viewlet.png)

De manera alternativa, puede hacer clic en el icono de anclaje que se encuentra en la esquina superior derecha del grupo de editores o presione **Ctrl+Alt+F / Cmd+Alt+F**.

![Anclaje de VS Code](../media/vscode-pin.png)

> [!NOTE]
> Si hay más de una persona en la sesión de colaboración, tendrá que seleccionar al participante al que quiere seguir.
>
>![Captura de pantalla de la lista de colaboradores](../media/vscode-list-collaborators.png)

Como el seguimiento está asociado a un grupo de editores, puede usar la vista dividida (o diseño de cuadrícula) para tener un grupo que siga a un participante y un grupo que no lo haga. Esto le permite seguir de manera pasiva a alguien mientras trabaja también en otra cosa. Con un grupo de editores seleccionado, puede seleccionar a un participante en la lista de participantes para hacer que ese grupo lo siga.

![Anclaje de VS Code en la vista dividida](../media/vscode-follow-split.png)

Para facilitar salir del "modo de seguimiento" y empezar a editar por su cuenta, dejará automáticamente de seguir participantes si ocurre alguna de estas situaciones:

1. Empieza a editar el archivo actualmente activo
1. Abre un archivo distinto
1. Cierra el archivo actualmente activo

Además, puede dejar de seguir a alguien de manera explícita si hace clic en el icono de anclaje o presiona **Ctrl+Alt+F / Cmd+Alt+F**.

## <a name="listing-participants"></a>Lista de participantes

Una forma rápida de ver quién está en la sesión de colaboración es examinar la lista de participantes en la vista del explorador de Live Share o en la pestaña personalizada. Las vistas mostrarán todos los participantes de la sesión.

![Captura de pantalla que muestra el icono de la barra de estado del usuario](../media/vscode-explorer-view.png)

Si hace clic en cualquiera de los participantes de esta lista, lo seguirá en el grupo de editores activo.

Como alternativa, puede presionar **Ctrl + Mayús + P/Cmd + Mayús + P** y seleccionar el comando "Live Share: List participante" o **hacer clic** en el elemento de la barra de estado que muestra el número de participantes de la sesión.

![Captura de pantalla que muestra el icono de la barra de estado del usuario](../media/vscode-user-status.png)

De ese modo, aparecerá una lista de todos los participantes de la sesión. A diferencia de lo que ocurre cuando se hace clic en el icono de anclaje, esta lista aparece incluso si hay solo una persona más en la sesión junto con usted, por lo que siempre podrá ver rápidamente dónde se ubica alguien más. Para su comodidad, del mismo modo que con el icono de anclaje, puede elegir uno de los participantes de la lista para seguirlo. Si prefiere salir, presione Escape.

## <a name="focusing"></a>Atracción de la atención de los participantes

En algunas ocasiones puede que quiera que todos quienes participan en una sesión de colaboración vean lo que está haciendo. Live Share le pide solicitar que todo el mundo "centre" su atención en usted con una notificación que les facilita la tarea de seguirle.

Abra la pestaña personalizada Live Share en la barra de actividades de VS Code o la vista Explorador de Live Share y seleccione el icono "Atraer la atención de los participantes".

![Icono para atraer la atención de los participantes del viewlet](../media/vscode-focus-viewlet.png)

Una vez que ejecute el comando, todos los participantes de la sesión de colaboración recibirán una notificación de que solicita su atención.

![Notificación del sistema sobre atraer la atención de los participantes](../media/vscode-focus-toast.png)

De ese modo, ellos pueden simplemente hacer clic en "Seguir" directo en la notificación cuando estén listos para centrar su atención en usted.

## <a name="co-debugging"></a>Depuración conjunta

La característica de depuración colaborativa de Visual Studio Live Share es una manera única y eficaz de depurar un problema. Más allá de permitir una experiencia de colaboración para solucionar problemas, también le brinda a usted y a otros participantes de la sesión la capacidad de investigar los problemas que puedan ser específicos del entorno al proporcionar una sesión de depuración compartida en la máquina del anfitrión.

> **Sugerencia de seguridad:** Dado que todos los participantes pueden navegar y editar archivos de forma independiente, como un host, puede que desee restringir los archivos a los que los invitados pueden acceder en el proyecto a través de un archivo. vsls. JSON. También debe tener en cuenta que el acceso a la consola/REPL significa que los participantes pueden ejecutar comandos en su máquina, por lo que solo debe depurar en conjunto con personas de confianza. Como invitado, también es importante tener en cuenta que es posible que no pueda seguir al depurador, porque entra en ciertos archivos restringidos como resultado de esta configuración. Consulte [Control de la visibilidad y el acceso de archivos](../reference/security.md#controlling-file-access-and-visibility) para más información.

Usarlo es simple.

1. Asegúrese de que tanto el anfitrión como todos los invitados tengan instalada la extensión de depuración correspondiente. (No siempre es técnicamente necesaria, pero es una buena idea hacerlo).

2. Como anfitrión, si todavía no está configurado para el proyecto, debe [configurar launch.json](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) para depurar la aplicación desde VS Code como lo haría normalmente. No se requiere ninguna configuración especial.

3. A continuación, el anfitrión puede empezar a depurar con el botón de la pestaña de depuración, tal como lo haría normalmente.

    ![Botón de depuración de VS Code](../media/vscode-debug-button.png)

    > [!TIP]
    > También puede participar en las sesiones de depuración de Visual Studio desde VS Code y viceversa. Consulte las [instrucciones de Visual Studio](vs.md#co-debugging) para más información sobre la depuración conjunta.

Una vez que el depurador se asocia en el lado del anfitrión, también se ajustan automáticamente todos los invitados. Mientras hay una "sesión" de depuración ejecutándose en la máquina del anfitrión, todos los participantes se conectan a ella y tienen su propia vista.

![Depurador de VS Code asociado](../media/vscode-debugger.png)

Cualquier persona puede desplazarse por el proceso de depuración, lo que permite cambiar sin problemas entre los colaboradores sin tener que negociar el control.

> [!NOTE]
> Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características de depuración por lenguaje o plataforma.

Cada colaborador puede investigar distintas variables, saltar a distintos archivos en la pila de llamadas, inspeccionar las variables e incluso agregar o quitar puntos de interrupción. Luego, las características de edición conjunta permiten que cada orador participante haga un seguimiento de dónde se encuentran ubicados los demás para brindar la capacidad única de cambiar sin complicaciones entre los distintos aspectos del problema que se investigan en simultáneo y la depuración colaborativa.

> [!NOTE]
> Mientras esté en una sesión de colaboración de solo lectura, un invitado no podrá desplazarse por el proceso de depuración. Sin embargo, sí puede agregar o quitar puntos de interrupción e inspeccionar variables.

![Animación de la depuración simultánea](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>Cambio cuando VS Code se une a las sesiones de depuración

De manera predeterminada, como invitado, se lo asociará automáticamente a las sesiones de depuración cuando el anfitrión las comparta. Sin embargo, en algunos casos, puede considerar que este comportamiento es problemático. Afortunadamente, puede cambiarlo de la siguiente manera:

Simplemente debe **editar settings.json** (Archivo > Preferencias > Configuración), agregar una de las líneas siguientes y, luego, reiniciar VS Code:

| Parámetro | Comportamiento |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | El valor predeterminado. Como invitado, participará automáticamente en cualquier sesión de depuración que inicie el anfitrión. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | Como invitado, se le preguntará si quiere participar en una sesión de depuración compartida cuando la inicie el anfitrión. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | Como invitado, deberá participar manualmente en cualquier sesión de depuración. Consulte [Desasociación y nueva asociación](#detaching-and-reattaching). |

### <a name="detaching-and-reattaching"></a>Desasociación y nueva asociación

Es posible que un invitado quiera detener temporalmente la depuración. Afortunadamente, puede simplemente hacer clic en el icono "Detener" de la barra de herramientas de depuración para desasociar el depurador sin afectar al anfitrión ni a otros invitados.

![Botón de detención del depurador de VS](../media/vscode-debug-stop.png)

Si actualizó la configuración y ya no se asocia de manera automática o si simplemente quiere volver a asociarse más adelante, puede presionar **Ctrl+Mayús+P / Cmd+Mayús+P** o **hacer clic** en el elemento de estado de la barra de estado y seleccionar "Attach to a Shared Debugging Session"(Asociar a una sesión de depuración compartida).

![Asociar depurador de VS Code](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>Uso compartido de la aplicación en ejecución en un explorador

Visual Studio Code no tiene el concepto de un "puerto de aplicación web" conocido como Visual Studio para tipos de proyecto como ASP.NET. Sin embargo, si va a participar en una sesión de colaboración desde un anfitrión de Visual Studio, puede ver automáticamente que el explorador predeterminado aparece cuando se inicia la depuración y que luego se conecta automáticamente a las aplicaciones en ejecución del anfitrión. Consulte [Características de Visual Studio](vs.md#automatic-web-app-sharing) para más detalles.

Como anfitrión, puede lograr algo similar si comparte manualmente la aplicación u otros puntos de conexión, como los servicios RESTful, a través de la característica "Share Local Server" (Compartir servidor local). Los invitados de Visual Studio y VS Code entonces pueden abrir un explorador en el mismo puerto localhost para ver la aplicación en ejecución.  Consulte [Uso compartido de un servidor](#share-a-server) para más detalles.

## <a name="share-a-server"></a>Uso compartido de un servidor

De vez en cuando, como anfitrión de la sesión de colaboración, puede darse el caso de que quiera compartir una aplicación web u otro servicio o servidor en ejecución local con los invitados. Esto puede ir desde otros puntos de conexión de RESTful a bases de datos y otros servidores. Visual Studio Live Share le permite especificar un número de puerto local, darle un nombre si así lo quiere y compartirlo con todos los invitados.

A continuación, los usuarios podrán acceder al servidor que compartió en ese puerto desde su propia máquina local exactamente en el mismo puerto. Por ejemplo, si compartió un servidor web **en ejecución en el puerto 3000**, el invitado puede acceder a ese mismo servidor web en ejecución en su **propia máquina** en http://localhost:3000. Esto se logra a través de un túnel SSH o SSL entre el anfitrión y los invitados y se autentica a través del servicio, por lo que puede estar seguro de que solo quienes participen de la sesión de colaboración tienen acceso.

> **Sugerencia de seguridad:** Como host, debe ser muy selectivo con los puertos que comparte con los invitados y se adhiere a los puertos de la aplicación (en lugar de compartir un puerto del sistema). En el caso de los invitados, los puertos compartidos se comportarán exactamente igual que si el servidor o servicio se estuviese ejecutando en su propia máquina. Esto es muy útil, pero podría ser también arriesgado si es que se comparte el puerto incorrecto.

Por motivos de seguridad, solo los servidores que se ejecutan en los puertos que especifica estarán disponibles a los demás invitados. Afortunadamente, es fácil agregar uno como el **anfitrión** de la sesión de colaboración. Esta es la manera de hacerlo:

1. Abra la pestaña personalizada Live Share en la barra de actividades de VS Code o la vista Explorador de Live Share y seleccione la entrada "Share server…" (Compartir servidor) o haga clic en el icono.

    ![Compartir servidor local de VS Code](../media/vscode-share-local-server-viewlet.png)<br />

1. Escriba el número de puerto en el que se ejecuta el servidor y, si quiere, un nombre.

    ![Captura de pantalla de la solicitud del número de puerto](../media/vscode-enter-port.png)<br />

Ya está. El servidor en el puerto que especificó ahora se asignará al localhost de cada invitado en el mismo puerto (a menos que ya esté ocupado).

Si el puerto ya está en uso en la máquina del invitado, se seleccionará otro automáticamente. Por fortuna, como invitado puede ver una lista de los puertos actualmente compartidos (por nombre si se especificó) en la pestaña personalizada o la vista Explorador de Live Share en la barra de actividades de VS Code y ver debajo de la lista de servidores compartidos. Si se selecciona una entrada, ese servidor se abre en el explorador. También puede hacer clic con el botón derecho y seleccionar la opción para copiar el vínculo al servidor en el Portapapeles.

![Servidor local de acceso de VS Code](../media/vscode-access-shared-server-viewlet.png)<br />

Tenga en cuenta que *los invitados no pueden* controlar qué puertos de la máquina del anfitrión se comparten por motivos de seguridad.

Para **dejar** de compartir un servidor local como el anfitrión, mantenga el puntero sobre la entrada del servidor en la lista de los servidores compartidos en la pestaña personalizada o la vista Explorador de Live Share y haga clic en el icono "Unshare server" (Dejar de compartir el servidor).

![Dejar de compartir el servidor en VS Code](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>Uso compartido de un terminal

El desarrollo moderno hace un uso frecuente de una amplia gama de herramientas de línea de comandos. Afortunadamente, como anfitrión, Live Share le permite, de forma opcional, "compartir un terminal" con los invitados. El terminal compartido puede ser de solo lectura o totalmente colaborativo, para que tanto usted como los invitados puedan ejecutar comandos y ver los resultados. Puede dar a los invitados visibilidad sobre la salida del terminal o permitirles obtener experiencias prácticas y ejecutar pruebas, compilaciones o incluso evaluar la prioridades de los problemas específicos del entorno que solo aparecen en su máquina.

Sin embargo, los terminales **no** se comparten de manera predeterminada, porque dan a los invitados al menos acceso de solo lectura a la salida de los comandos que usted ejecuta (si es que no la capacidad de ejecutar los comandos mismos). De este modo, puede ejecutar libremente los comandos en los terminales locales sin riesgo y solo compartirlos cuando de verdad tenga que hacerlo. Además, solo los anfitriones pueden iniciar los terminales compartidos para impedir que los invitados inicien uno y hagan algo inesperado o sin supervisión.

Como anfitrión, para compartir un terminal puede abrir la pestaña personalizada Live Share en la barra de actividades de VS Code o la vista Explorador de Live Share y seleccionar la entrada "Share server…" (Compartir servidor) o hacer clic en el icono.

![Uso compartido del terminal en VS Code](../media/vscode-share-terminal-viewlet.png)<br />

En este momento, puede seleccionar un terminal de solo lectura o de lectura y escritura en el menú. Si el terminal es de lectura/escritura, todos los participantes pueden escribir en el terminal, incluido el anfitrión, lo que permite intervenir fácilmente si un invitado hace algo que no le gusta. Sin embargo, para estar seguros, debería **darle acceso de lectura/escritura a los invitados solo cuando sabe que realmente lo necesitan**  y limitarse a los terminales de solo lectura en escenarios donde quiere que un invitado solo vea la salida de los comandos que ejecuta.

> [!NOTE]
> Si la sesión de colaboración está en modo de solo lectura, el anfitrión solo puede compartir los terminales de solo lectura.

![Selección de solo lectura o de lectura/escritura](../media/vscode-share-terminal-ro-rw.png)<br />

Una vez que haya seleccionado el tipo de terminal compartido que quiere iniciar, aparecerá un terminal compartido nuevo en la pestaña de terminales de VS Code.

![Terminal compartido en ejecución](../media/vscode-share-terminal-up.png)<br />

Si se comparten varios terminales o si su atención está en otra pestaña, puede atraer la atención a un terminal específico si selecciona la entrada en la lista de terminales compartidos.

![Centrar la atención en un terminal compartido](../media/vscode-shared-terminal-focus.png)<br />

Para finalizar la sesión del terminal, solo debe escribir exit (salir), cerrar la ventana del terminal o hacer clic en el icono "Unshare terminal" (Dejar de compartir el terminal) en la pestaña personalizada o la vista Explorador de Live Share y se desconectará a cada uno de los participantes.

## <a name="session-states"></a>Estados de sesión

Una vez que inicie una sesión de colaboración o que se una a ella y tenga acceso al contenido compartido, los elementos de la barra de estado de Visual Studio Live Share actualizarán su apariencia para reflejar el estado de la sesión de colaboración activa.

Estos son los estados que verá habitualmente:

| Estado | Barra de estado | Descripción |
|-------|--------------------|-------------|
| Inactivo | ![Estado de VS Code: inactivo](../media/vscode-status-share.png) | No hay ninguna sesión de colaboración activa y no se comparte nada. |
| Host: uso compartido en curso | ![Estado de VS Code: uso compartido en curso](../media/vscode-status-sharing.png)| Se inicia una sesión de colaboración y pronto se empezará a compartir contenido. |
| Host: uso compartido | ![Estado de VS Code: uso compartido activo ](../media/vscode-status-active.png)| Hay una sesión de colaboración activa y se comparte contenido. |
| Host: uso compartido de solo lectura | ![Estado de VS Code: uso compartido de solo lectura](../media/vscode-status-sharing-read-only.png)| Se comparte una sesión de colaboración de solo lectura. |
| Invitado: unirse a sesión | ![Estado de VS: participación](../media/vscode-status-joining.png)| Participación en una sesión de colaboración existente. |
| Invitado: Unido | ![Estado de VS Code: participando](../media/vscode-status-active.png) | Se conectó y está participando en una sesión de colaboración activa y recibe contenido compartido. |
| Invitado: solo lectura combinada | ![Estado de VS Code: participando en solo lectura](../media/vscode-status-joined-read-only.png) | Se conectó y está participando en una sesión de colaboración de solo lectura activa. |

## <a name="guest-limitations"></a>Limitaciones de los invitados

Si bien actualmente los invitados pueden encontrarse con algunas limitaciones al usar las características ya descritas, los anfitriones de la sesión de colaboración conservan toda la funcionalidad de su herramienta preferida. Para obtener más información, vea las secciones siguientes:

- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Compatibilidad con extensiones](../reference/extensions.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)
- [Solución de problemas](../troubleshooting.md)

## <a name="next-steps"></a>Pasos siguientes

Consulte estos artículos adicionales para obtener más información.

- [Inicio rápido: compartir el primer proyecto](../quickstart/share.md)
- [Inicio rápido: Únase a su primera sesión](../quickstart/share.md)
- [Colaborar con Visual Studio](vs.md)
- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)
- [Detalles de la instalación de Linux](../reference/linux.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
