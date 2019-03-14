---
title: 'Colaborar mediante Visual Studio Code: Visual Studio Live Share | Microsoft Docs'
description: Un conjunto de procedimientos de colaboración de Visual Studio Code y Live Share.
ms.custom: ''
ms.date: 04/27/2018
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
ms.openlocfilehash: 9285fef38fea9bb164892775521ed2a28fe9ef1b
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256324"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>Cómo: Colaborar mediante Visual Studio Code

¿Listo para empezar a colaborar con Live Share en VS Code?  Si es así, está en el punto adecuado. En este artículo, le guiaré a través de cómo usar algunas de las características específicas de la extensión de Visual Studio Live Share para Visual Studio Code.

Tenga en cuenta que todas las actividades de colaboración que se describen aquí implican una sola **host de sesión de colaboración** y uno o varios **invitados**. El anfitrión es la persona que inicia la sesión de colaboración, mientras que las personas que participan en ella son invitados.

*¿Busca un resumen resumido? Consulte la [compartir](../quickstart/share.md) o [combinación](../quickstart/join.md) inicios rápidos en su lugar.*

> [!TIP]
> ¿Sabía que puede *participar en su propia sesión de colaboración*? Esto le permite probar Live Share por su cuenta o poner en marcha una instancia de Visual Studio o VS Code y conectarse a ella de forma remota. Incluso puede usar la misma identidad en ambas instancias. ¡Compruébelo!

## <a name="installation"></a>Instalación

Antes de comenzar, necesitará para asegurarse de que tiene una versión de Visual Studio Code instalado que cumpla los requisitos principales de Live del recurso compartido. Necesitará **Visual Studio Code (1.22.0 o superior)** que se ejecuta en:

- **Windows**: 7, 8.1 o 10

- **macOS**: Sierra (10.12) y versiones posteriores únicamente.
    - _El capitán (10.11) y versiones anteriores no son compatibles actualmente debido a [los requisitos de .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872315)._

- **Linux**: Escritorio de 64 bits Ubuntu 16.04 +, estación de trabajo Fedora 27 + y CentOS 7

    - Recurso compartido en vivo requiere un número de [requisitos previos de Linux](#linux-install-steps) se le pedirá que instale.
    - _no se admite Linux de 32 bits debido a [los requisitos de .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872314)._
    - ARM también actualmente no se admite.
    - Consulte la [detalles de la instalación de Linux](../reference/linux.md) artículo para obtener más información sobre el uso de nivel inferiores y otras distribuciones.

Después, descargar e instalar la extensión de Visual Studio Live Share es muy sencillo:

1. Instalar <a href="https://code.visualstudio.com/">código de Visual Studio</a>
2. [Descargar](https://aka.ms/vsls-dl/vscode) e instalar la extensión de Visual Studio Live Share en marketplace.
3. Vuelva a cargar Visual Studio Code
4. Espere a que las dependencias descargar e instalar (consulte la barra de estado).<br/>
    ![Finalizar instalación](../media/vscode-finishing-install.png)
5. **Linux**: Si ve una notificación acerca de cómo instalar las bibliotecas que faltan:
    1. Haga clic en "Instalar" en la notificación.
    2. Escriba la contraseña de administrador (sudo) cuando se le solicite.
    3. Reinicie VS Code cuando haya terminado.

Al descargar y usar Visual Studio Live Share, acepta los [términos de licencia](https://aka.ms/vsls-license) y la [declaración de privacidad](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si surge algún problema, consulte la [solución de problemas](../troubleshooting.md).

[![Descargar](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Pasos de instalación de Linux

Linux es un entorno muy variable y con el gran número de entornos de escritorio y distribuciones puede ser complicado ponerlo en funcionamiento. Si se limita a las versiones compatibles de **escritorio Ubuntu** (16.04 +) o **Fedora Workstation** (27 o superior), **CentOS 7** y usar solo **distribuciones oficiales de VS Código**, debe buscar el proceso sencillo. Sin embargo, en caso de que usa una configuración no estándar o una distribución de nivel inferior, puede o no se puede ejecutar en algunas interrupciones. Consulte [detalles de la instalación de Linux](../reference/linux.md) para obtener más información.

#### <a name="install-linux-prerequisites"></a>Instalar requisitos previos de Linux

Algunas distribuciones de Linux faltan las bibliotecas de que Live Share necesite para funcionar. De forma predeterminada, Live Share intenta detectar e instalar los requisitos previos de Linux para usted. Verá una notificación cuando Live Share encuentra un problema que puede originarse en el que faltan las bibliotecas que le pide permiso instalarlos.

![Faltan notificación del sistema que se muestra el mensaje que requisitos previos de Linux](../media/vscode-linux-prereq-missing.png)

Al hacer clic en "Instalar", aparecerá una ventana de terminal donde deberá escribir la contraseña de administrador (sudo) para continuar. ¡Suponiendo que se complete correctamente, reinicie el código de Visual Studio ya debería estar listo! También puede consultar **[sugerencias según la distribución](../reference/linux.md#tips-by-distribution)** otras sugerencias y soluciones alternativas si existe alguno.

Si ve un mensaje que indica la secuencia de comandos no es compatible con la distribución, consulte **[sugerencias para las distribuciones compatible con la Comunidad](../reference/linux.md#tips-for-community-supported-distros)** para la información de la Comunidad ha compartido con nosotros.

Si se **no prefieren tener VS Code, ejecute el comando de**, también puede para volver a ejecutar la versión más reciente de este script en cualquier momento manualmente ejecutando el siguiente comando desde una ventana de Terminal:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Integración del explorador de Linux

Live Visual Studio comparten normalmente **no requiere pasos de instalación adicionales** para habilitar la integración con el explorador en Linux.

Poco habitual, en ciertas distribuciones **puede recibir una notificación que se requiere la contraseña de administrador (sudo)** para completar el proceso de instalación. Aparecerá una ventana de terminal que le indica dónde se instalará el iniciador del explorador. Simplemente escriba la contraseña cuando se le solicite y presione ENTRAR una vez finalizada la instalación para cerrar la ventana de terminal.

Puede leer más información sobre por qué esto es necesario y que comparten Live coloca archivos  **[aquí](../reference/linux.md#linux-browser-integration)**. Tenga en cuenta incluso si no puede obtener el trabajo de integración del explorador todavía puede  **[combinar manualmente sesiones de colaboración](../use/vscode.md#join-manually)**.

## <a name="sign-in"></a>Inicio de sesión

Con el fin de colaborar, necesitará iniciar sesión en Visual Studio Live Share, por lo que todo el mundo sabe quién es usted. Esto es puramente una medida de seguridad y **no** optar cualquier marketing u otras actividades de investigación. Puede iniciar sesión con una cuenta personal de Microsoft (por ejemplo, @outlook.com), respaldado por Microsoft cuenta profesional o educativa (AAD) o una cuenta de GitHub. Es fácil iniciar sesión.

**Haga clic en** en el estado "Compartir" elemento o presione la barra **Ctrl + Mayús + P / Cmd + Mayús + P** y seleccione el "recurso compartido en vivo: Comando iniciar sesión con el explorador".

![En el botón de la firma de código de VS](../media/vscode-sign-in-button.png)

Aparecerá una notificación que le pide que inicie sesión con su explorador web. Al hacer clic en "iniciar sesión en" se abrirá un explorador para que pueda usar para completar el proceso de inicio de sesión. Simplemente cierre el explorador cuando haya terminado.

![Notificación del sistema que pide que inicie sesión con un explorador web](../media/vscode-sign-in-toast.png)

> **Usuarios de Linux:** Se le pedirá que escriba un código de usuario si usa una versión anterior de Live Share (v0.3.295 o por debajo). Actualizar a la versión más reciente de la extensión o haga clic en el "teniendo problemas?" vincular después del inicio de sesión para ver el código. Consulte [a continuación para obtener más información](#sign-in-using-a-user-code).

Si el código de Visual Studio no se recoge el inicio de sesión después de completar el proceso de inicio de sesión en el explorador, vea [inicie sesión con un código de usuario](#sign-in-using-a-user-code). En caso contrario, consulte [solución de problemas](../troubleshooting.md#sign-in) para obtener más sugerencias.

### <a name="sign-in-using-a-user-code"></a>Inicie sesión con un código de usuario

Si está experimentando problemas con el código de VS no recoger un inicio de sesión completado, puede escribir un código de"usuario" en su lugar.

1. Presione **Ctrl + Mayús + P / Cmd + Mayús + P** y ejecute el "recurso compartido en vivo: Comando iniciar sesión con el código de usuario".

2. Un explorador debe aparecer para que use para completar el proceso de inicio de sesión.

    > [!NOTE]
    > Si no aparece automáticamente un explorador, abra [esta ubicación](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) en un explorador e inicie sesión.

3. ¿Cuando haya terminado, haga clic en "teniendo problemas? Haga clic aquí para obtener instrucciones de código de usuario"para ver el código de usuario.

    ![Imagen del código de usuario en el explorador](../media/vscode-user-code-browser.png)

4. Copie el código de usuario.

5. Por último, pegue el código de usuario en el campo de entrada que aparecía cuando ejecutó el comando y presione ENTRAR para completar el proceso de inicio de sesión.

    ![Imagen del campo de entrada de código de usuario](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Utilizando el viewlet Live Share

Después de instalar Visual Studio Live Share, se agregará una pestaña personalizada a la barra de actividad de VS Code. En esta pestaña, puede tener acceso a todas las funciones de Live Share para colaborar. Además, al compartir o participar en una sesión de colaboración, una vista también aparecerá en la pestaña de explorador para tener acceso a todas estas funciones.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

Con estas vistas, puede ver la ubicación de un participante en el código compartido, haga clic en un participante de seguirlos, céntrese participantes, tener acceso a servidores compartidos y los terminales y mucho más.

## <a name="using-the-scoped-command-menu"></a>Mediante el menú de comandos con ámbito

Además, todas las funciones de Visual Studio Live Share están disponibles desde el código de Visual Studio "Paleta de comandos" que se puede tener acceso presionando Ctrl + Mayús + P / Cmd + Mayús + P o F1. Puede encontrar una lista completa de comandos escribiendo "live share".

Puesto que esta lista puede ser muy larga, le resultará más fácil aprovechar las ventajas de un menú de comandos con ámbito disponible en la barra de estado. Al hacer clic en el inicio de sesión / icono de estado de sesión en la barra de estado inmediatamente, aparecerá una lista contextualizada de comandos que están disponibles para su uso.

![Icono de estado de sesión de código de VS](../media/vscode-share-state.png)

## <a name="share-a-project"></a>Compartir un proyecto

Después de descargar e instalar Visual Studio Live Share, siga estos pasos para iniciar una sesión de colaboración e invitar a un compañero de trabajo para trabajar con usted.

1. **Inicia sesión**

    Después de instalar la extensión Live Share, volver a cargar y esperando las dependencias finalizar la instalación, desea iniciar sesión para que otros colaboradores sepa quién es usted. Consulte [inicie sesión en](#sign-in) para obtener más detalles.

2. **Abrir una carpeta**

    Para abrir una carpeta, proyecto o solución que le gustaría compartir con sus invitados, use el flujo de trabajo normal.

3. **[Opcional] Actualizar archivos ocultos o excluidos**

    De forma predeterminada, Live Share **oculta** los archivos o carpetas que se hace referencia en los archivos .gitignore en las carpetas compartidas de los invitados. **Ocultar** un archivo evita que aparezca en el árbol de archivos de invitado. **Excluir** un archivo aplica una regla más estricta que impidan que Live Share abrirlo para el invitado en situaciones como ir a una definición o si el paso en el archivo mientras depura o se "sigue". Si desea ocultar o excluir archivos diferentes, una **. vsls.json** archivo se puede agregar al proyecto con esta configuración. Consulte [controlar el acceso de archivo y visibilidad](../reference/security.md#controlling-file-access-and-visibility) para obtener más información.

4. **Iniciar una sesión de colaboración**

    Ahora, simplemente **haga clic en** el estado de "Compartir" elemento o presione la barra **Ctrl + Mayús + P / Cmd + Mayús + P** y seleccione "recurso compartido en vivo: Iniciar una sesión de colaboración (recurso compartido) ".

    ![Botón Compartir](../media/vscode-share-button.png)

    > [!NOTE]
    > Se le pedirá el software de firewall de escritorio para que el agente de compartir en directo abrir un puerto de la primera vez que se comparte. Aceptar esto es totalmente opcional pero permite que un seguro "modo directo" para mejorar el rendimiento cuando es la persona que trabaja en la misma red que sea. Consulte [cambiar el modo de conexión](../reference/connectivity.md#changing-the-connection-mode) para obtener más información.

    Un vínculo de la invitación se copiará automáticamente en el Portapapeles. Cuando se abre en un explorador, este vínculo permite a otros a unirse a una nueva sesión de colaboración que comparte el contenido de estas carpetas con ellos.

    También verá la transición de elemento de barra de estado "Compartir" para representar el estado de sesión. Consulte [estado de sesión](#session-states) información siguiente para este aspecto.

    Tenga en cuenta que si necesita obtener el vínculo de invitación a intentarlo después de haber iniciado el uso compartido, acceder a ella nuevamente haciendo clic en el icono de barra de estado de estado de sesión y seleccione "Invitar a otros usuarios (Copiar vínculo)".

5. **[Opcional] Habilitar el modo de solo lectura**

    Una vez que inicie una sesión de colaboración, puede establecer la sesión sea de solo lectura para evitar que los invitados realiza modificaciones en el código que se comparte.

    Después de compartir, obtendrá una notificación de que el vínculo de la invitación se ha copiado en el Portapapeles. A continuación, puede seleccionar la opción para que la sesión de solo lectura.

    ![Modo de solo lectura del código de VS](../media/vscode-read-only-toast.png)

6. **Enviar a alguien el vínculo**

    Envíe el vínculo por correo electrónico, Slack, Skype, etc. a los que desea invitar. Tenga en cuenta que, dado el nivel de acceso a Live compartir sesiones pueden proporcionar a los invitados, **solo se debe compartir con usuarios de confianza** y piense detenidamente las implicaciones de lo que va a compartir.

    > **Sugerencia de seguridad:** ¿Desea comprender las implicaciones de seguridad de algunas de las características de Live del recurso compartido? Consulte la [seguridad](../reference/security.md) artículo.

    Si el invitado le invitó tiene preguntas, el "[inicio rápido: Únase a la primera sesión](../quickstart/join.md)"artículo proporciona información adicional sobre entre en funcionamiento como invitado.

7. **[Opcional] Aprobar el invitado**

    De forma predeterminada, los invitados se unirán automáticamente a la sesión de colaboración y se le notificará cuando haya terminado de trabajar con usted. Aunque esta notificación le proporciona la opción de quitarlos de la sesión, también puede optar en su lugar, requieren una "aprobación" explícita para todo aquel que unir.

    Para habilitar esta característica, simplemente agregue lo siguiente al settings.json:

         "liveshare.guestApprovalRequired": true

    Una vez activada esta opción, le solicitará una notificación que aprobar al invitado para que pueden unirse.

    ![Solicitud de aprobación de combinación de Visual Studio Code](../media/vscode-join-approval.png)

    Consulte [invitaciones y acceso de combinación](../reference/security.md#invitations-and-join-access) para obtener más detalles sobre las consideraciones de seguridad de invitación.

¡¡Eso es todo!!

### <a name="stop-the-collaboration-session"></a>Detener la sesión de colaboración

Como un host, puede dejar de compartir completamente y finalizar la sesión de colaboración en cualquier momento, abra la vista de Live Share en el explorador o en la pestaña personalizada de Live Share y seleccione el icono "Detener la sesión de colaboración".

![Detener la sesión de colaboración](../media/vscode-end-collaboration-viewlet.png)

Todos los invitados le notificará que la sesión ha finalizado.  Una vez que ha finalizado la sesión, los invitados ya no podrán acceder al contenido y los archivos temporales se limpian automáticamente.

¿Tiene problemas con el uso compartido? Desproteger [solución de problemas](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Participar en una sesión de colaboración

Después de descargar e instalar Visual Studio Live Share, los invitados sólo necesitan realizar un par de pasos para participar en una sesión de colaboración de alojamiento. Hay dos maneras de combinar: [a través del explorador](#join-via-the-browser) y [manualmente](#join-manually).

> **Sugerencia de seguridad:** Como invitado participar en una sesión de colaboración, es importante comprender que los hosts pueden limitar su acceso a determinados archivos o las características. ¿Desea comprender las implicaciones de seguridad de algunas de las características y la configuración de Live Share? Consulte la [seguridad](../reference/security.md) artículo.

### <a name="join-via-the-browser"></a>Unirse a través del explorador

Para participar en una sesión de colaboración más sencillo es simplemente abrir el vínculo de invitación en un explorador web. Aquí es lo que puede esperar al seguir este flujo.

1. **Inicia sesión**

    Después de instalar la extensión Live Share, volver a cargar y esperando las dependencias finalizar la instalación, desea iniciar sesión para que otros colaboradores sepa quién es usted. Consulte [inicie sesión en](#sign-in) para obtener más detalles.

2. **Haga clic en el vínculo de la invitación y abrir la invitación en el explorador**

    Ahora, basta con abrir (o volver a abrir) el vínculo de invitación en un explorador.

    > **Nota**: Si aún no ha instalado la extensión Live Share, se mostrarán con vínculos a marketplace de extensión. Instalar la extensión y reinicie la herramienta y vuelva a intentar.

    Debería recibir una notificación que desea que el explorador iniciar una herramienta de Live Share habilitado. Si se permite que inicie la herramienta seleccionada, se conectará a la sesión de colaboración, una vez que se inicia.

    ![Únase a la página](../media/join-page.png)

    Si el host está sin conexión, se le notificará en este momento en su lugar. A continuación, puede ponerse en contacto con el host y pídale que vuelva a compartir.

    > [!NOTE]
    > Asegúrese de haber **inicia la herramienta de al menos una vez** después de instalar la extensión de Visual Studio Live Share y permite la instalación finalice antes de apertura/volver-opening la página de invitación. ¿Sigue teniendo problemas? Consulte [combinar manualmente](#join-manually).

3. **Collaborate**

    Ya está. En unos instantes se conectará y empezar a colaborar.

    Verá la transición del botón "Compartir" para transmitir un "estado de sesión". Consulte [estado de sesión](#session-states) información siguiente para este aspecto.

    A continuación, automáticamente pasará al archivo es que el host se está editando una vez completada la combinación.

### <a name="join-manually"></a>Combinar manualmente

Puede combinar manualmente sin usar un explorador web que puede ser útil en situaciones donde ya se está ejecutando la herramienta que desea usar, que desea usar otra herramienta que suela hacerlo, o si tiene problemas con la obtención de invitar a vínculos a trabajar por algún motivo. El proceso es sencillo:

1. **Inicia sesión**

    Después de instalar la extensión Live Share, volver a cargar y esperando las dependencias finalizar la instalación, desea iniciar sesión para que otros colaboradores sepa quién es usted. Consulte [inicie sesión en](#sign-in) para obtener más detalles.

2. **Use el comando de combinación**

    Abra la pestaña personalizada de Live Share en la barra de actividad de VS Code y seleccione la "combinación sesión de colaboración..." icono o entrada.

    ![Icono viewlet de combinación](../media/vscode-join-viewlet.png)

3. **Pegue el vínculo de invitación**

    Pegue la dirección URL de invitación se envió y presione ENTRAR para confirmar.

4. **¡Colaborar!**

    Ya está. Debe estar conectado a la sesión de colaboración momentáneamente.

    Verá la transición del botón "Compartir" para transmitir un "estado de sesión". Consulte [estado de sesión](#session-states) información siguiente para este aspecto.

    A continuación, automáticamente pasará al archivo es que el host se está editando una vez completada la combinación.

### <a name="leave-the-collaboration-session"></a>Deje la sesión de colaboración

Como invitado, puede dejar la sesión de colaboración sin tener que finalizar para que otros usuarios simplemente cierre la ventana de VS Code. Si prefiere mantener abierta la ventana, puede abrir la vista del explorador de recursos compartidos en vivo o la pestaña personalizada de Live Share y seleccione el icono "Dejar la sesión de colaboración".

![Icono de la sesión de hojas](../media/vscode-leave-session-viewlet.png)

Los archivos temporales se limpian automáticamente por lo que no es necesario realizar ninguna otra acción.

¿Tiene problemas con la combinación? Desproteger [solución de problemas](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Edición conjunta

Una vez que un invitado ha unido a una sesión de colaboración, todos los colaboradores podrán inmediatamente ver las modificaciones y las selecciones en tiempo real entre sí. Todo lo que necesita hacer es seleccionar un archivo desde el Explorador de archivos y empiece a editar. Hosts e invitados ver ediciones incluirlas y puede contribuir a sí mismos lo que iterar fácil y rápidamente clavo hacia abajo tanto soluciones.

> [!NOTE]
> Unirse a una sesión de colaboración de solo lectura impide que los invitados se pueden realizar modificaciones a los archivos. Un host puede [habilitar el modo de solo lectura cuando comparten](#share-a-project). Como un invitado, puede indicar si se ha unido a una sesión de solo lectura examinando su [estado de sesión](#session-states).

![Pantalla que muestra edición conjunta](../media/vscode-coedit.png)

> [!NOTE]
> Comparte la edición tiene limitaciones para determinados idiomas. Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características por lenguaje.

Más allá de los cursores y las modificaciones, las opciones seleccionadas también son visibles para todos los participantes en ese mismo archivo. Esto facilita la resalte donde podrían existir o transmitir ideas problemas.

![Pantalla que muestra resaltado](../media/vscode-highlight.png)

Mejor aún, usted y otros participantes pueden navegar a cualquier archivo en el proyecto compartido. Puede modificar conjuntamente o por separado, lo que significa que puede cambiar sin problemas entre la investigación, realizar pequeños ajustes y editarlo en colaboración completa.

Las ediciones resultantes se almacenan en la máquina del host en Guardar por lo que no es necesario sincronizar, inserte o enviar archivos alrededor de una vez que haya terminado edición. Las modificaciones son "simplemente there".

> **Sugerencia de seguridad:** Dado que todos los participantes pueden independientemente navegar y editar archivos, como un host, es posible que desee restringir los archivos que los invitados pueden tener acceso a su proyecto a través de un. archivo vsls.json. Como invitado, también es importante tener en cuenta que no vea determinados archivos como resultado de esta configuración. Consulte [controlar el acceso de archivo y visibilidad](../reference/security.md#controlling-file-access-and-visibility) para obtener más información.

### <a name="changing-participant-flag-behaviors"></a>Cambiar los comportamientos de la marca de participante

De forma predeterminada, Visual Studio Live Share muestra automáticamente una "marca" junto al cursor de un participante al mantener el mouse, o cuando edita, resalte o mover el cursor. En algunos casos, es posible que prefiera cambiar este comportamiento.

Simplemente **editar settings.json** (archivo > Opciones > configuración), agregue una de las líneas siguientes y, a continuación, reinicie VS Code:

| Parámetro | Comportamiento |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | La marca solo está visible cuando mantenga el mouse sobre el cursor. |
| ``"liveshare.nameTagVisibility":"Activity"`` | Este es el valor predeterminado. La marca está visible al mantener el mouse o si edita el participante, se resaltan o se mueve el cursor. |
| ``"liveshare.nameTagVisibility":"Always"`` | La marca está siempre visible. |

## <a name="following"></a>Siguiente

En ocasiones necesitará explicar un problema o diseño que abarque varios archivos o ubicaciones en el código. En estas situaciones, puede ser útil seguir temporalmente un compañero de trabajo cuando se mueven a lo largo del proyecto. Por este motivo, cuando se une a una sesión de colaboración automáticamente "seguirá" el host. Al seguir un usuario, el editor permanecerá sincronizado con su posición de desplazamiento y de archivo abierto actualmente.

> [!NOTE]
> De forma predeterminada, los recursos compartidos de Live Share abren archivos externos a la carpeta compartida también. Si desea deshabilitar esta característica, actualice `liveshare.shareExternalFiles` Live Share a `false` en settings.json.

Para empezar a seguir un participante (como un host o invitado), haga clic en su nombre en la lista de los participantes en la vista del explorador de recursos compartidos en vivo o la pestaña personalizada. Rellene el círculo situado junto a su nombre para indicar que está siguiendo ellos.

![VS Code siga desde viewlet](../media/vscode-follow-multiple-viewlet.png)

Como alternativa, puede hacer clic en el icono de anclaje en la esquina superior derecha del grupo de editor o presione **Ctrl + Alt + F / Cmd + Alt + F**.

![Pin de código de VS](../media/vscode-pin.png)

> [!NOTE]
> Si se encuentra más de una persona en la sesión de colaboración, le pedirá que seleccione al participante que desea seguir.
>
>![Captura de pantalla con una lista de colaboradores](../media/vscode-list-collaborators.png)

Puesto que la siguiente está asociado a un grupo de editor, puede usar la vista dividida (o diseño de cuadrícula) para que tenga un grupo que está siguiendo a un participante y un grupo que no es. Esto le permite seguir pasivamente alguien mientras también trabaja en un elemento por separado. Con un editor grupo seleccionado, puede seleccionar un participante en la lista de los participantes que ese grupo seguirlos.

![Pin de código de VS en vista dividida](../media/vscode-follow-split.png)

Para facilitar la "modo de seguimiento" y empiece a editar en su propio, también detendrá automáticamente los siguientes si se produce alguno de estos:

1. Empiece a editar el archivo activo
1. Abrir un archivo diferente
1. Cierre el archivo activo

Además, puede detener explícitamente después de que alguien haciendo clic en el icono de anclaje nuevo o presionar **Ctrl + Alt + F / Cmd + Alt + F**.

## <a name="listing-participants"></a>Lista de participantes

Una forma rápida de ver quién está en la sesión de colaboración es mirar la lista de participantes en la vista del explorador de recursos compartidos en vivo o la pestaña personalizada. Las vistas mostrará a todos los participantes en la sesión.

![Icono de la barra de estado de usuario de captura de pantalla que muestra](../media/vscode-explorer-view.png)

Al hacer clic en cualquier participante en esta lista seguirá a éstos en el grupo editor activo.

Como alternativa, puede presionar **Ctrl + Mayús + P / Cmd + Mayús + P** y seleccione el "recurso compartido en vivo: Comando de la lista de participantes"o **haga clic en** en el elemento de la barra de estado que muestra el número de participantes en la sesión.

![Icono de la barra de estado de usuario de captura de pantalla que muestra](../media/vscode-user-status.png)

A continuación, aparecerá una lista de todos los participantes en la sesión. A diferencia de hacer clic en el icono de anclaje, esta lista aparece incluso si hay solo una persona en la sesión con usted para que pueda ver rápidamente siempre que alguien se encuentra. Para fines de comodidad, al igual que el icono de anclaje, a continuación, puede elegir uno de los participantes en la lista mantengan con ellos. Si desea salir en su lugar, presione ESC.

## <a name="focusing"></a>Centrado

En ocasiones puede que desee todos los usuarios en una sesión de colaboración para llegar y eche un vistazo a algo que está haciendo. Live Share le permite hacer que todo el mundo "Centrar" su atención en una notificación que facilita la tarea para que puedan disponer de vuelta.

Abra la pestaña personalizada de Live Share en la barra de actividad de VS Code o la vista del explorador de recursos compartidos de Live y seleccione el icono "Centrarse participantes".

![Icono de enfoque viewlet](../media/vscode-focus-viewlet.png)

Una vez que ejecute el comando, todos los usuarios de la sesión de colaboración, a continuación, recibirá una notificación que ha solicitado su atención.

![Notificación del sistema de foco](../media/vscode-focus-toast.png)

Puede, a continuación, haga clic en "Seguir" directamente desde la notificación cuando haya terminado poner su enfoque en el.

## <a name="co-debugging"></a>Depuración conjunta

Característica de depuración de Visual Studio Live Share colaboración es una manera eficaz y única para depurar un problema. Más allá de lo que permite una experiencia de colaboración solucionar problemas, también y otros participantes en la sesión de la capacidad para investigar los problemas que pueden ser específica del entorno proporcionando una sesión de depuración compartida en la máquina del host.

> **Sugerencia de seguridad:** Dado que todos los participantes pueden independientemente navegar y editar archivos, como un host, es posible que desee restringir los archivos que los invitados pueden tener acceso a su proyecto a través de un. archivo vsls.json. También debe tener en cuenta que el acceso de consola/REPL significa que los participantes pueden ejecutar comandos en el equipo de forma que solo debe depurar conjuntamente con los que confíe. Como invitado, también es importante tener en cuenta que no es posible que pueda seguir el depurador avanza hasta algunos archivos restringidos de archivos como resultado de esta configuración. Consulte [controlar el acceso de archivo y visibilidad](../reference/security.md#controlling-file-access-and-visibility) para obtener más información.

Usando simple.

1. Asegúrese de que el host y todos los invitados tengan instalada la extensión de depuración adecuada. (Técnicamente esto no siempre es necesario, pero suele ser una buena idea).

2. Como el host, si aún no está configurado para el proyecto, debe [configurar launch.json](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) para depurar la aplicación desde VS Code como lo haría normalmente. No se requiere ninguna configuración especial.

3. A continuación, el host puede iniciar la depuración con el botón de la pestaña depurar de forma habitual.

    ![Botón de depuración de VS Code](../media/vscode-debug-button.png)

    > [!TIP]
    > También puede participar en sesiones de VS Code y viceversa de depuración de Visual Studio! Consulte la [instrucciones en Visual Studio](vs.md#co-debugging) en depuración conjuntamente para obtener más información.

Una vez que el depurador se adjunta en el lado del host, se adjuntan también automáticamente todos los invitados. Aunque hay una "sesión de depuración" que se ejecuta en la máquina del host, todos los participantes están conectados a él y tienen su propia vista.

![Adjuntadas el depurador de VS Code](../media/vscode-debugger.png)

Cualquier persona puede avanzar por el proceso de depuración que permite cambiar sin problemas entre colaboradores sin tener que negociar el control.

> [!NOTE]
> Consulte la [información sobre compatibilidad con la plataforma](../reference/platform-support.md) para ver el estado de las características de depuración por lenguaje o plataforma.

Cada colaborador puede investigar distintas variables, saltar a distintos archivos de la pila de llamadas, inspeccionar variables e incluso agregar o quitar puntos de interrupción. Características de edición conjunta, a continuación, permitir que cada participante oradores realizar un seguimiento en los demás se encuentran para proporcionar la capacidad única de cambiar sin problemas al mismo tiempo investigando distintos aspectos del problema y depuración en colaboración.

> [!NOTE]
> Mientras está en una sesión de colaboración de solo lectura, un invitado no pueda recorrer el proceso de depuración. Pueden, sin embargo, todavía agregar o quitar puntos de interrupción e inspeccionar variables.

![Animación de depuración simultáneas](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>Al cambiar las combinaciones de las sesiones de depuración de VS Code

De forma predeterminada, como invitado, deberá se adjunta automáticamente a cuando se comparten por el host de sesiones de depuración. Sin embargo, en algunos casos, se puede encontrar este comportamiento perjudiciales. Afortunadamente, puede cambiarlo como sigue:

Simplemente **editar settings.json** (archivo > Opciones > configuración), agregue una de las líneas siguientes y, a continuación, reinicie VS Code:

| Parámetro | Comportamiento |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | El valor predeterminado. Como invitado, deberá unirse automáticamente a cualquier sesión de depuración compartido se inicia el host. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | Como invitado, se le preguntará si desea participar en una sesión de depuración compartida cuando se inicie el host. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | Como invitado, necesita combinar manualmente las sesiones de depuración. Consulte [separar y volver a adjuntar](#detaching-and-reattaching). |

### <a name="detaching-and-reattaching"></a>Separar y volver a adjuntar

Un invitado, puede desear detener temporalmente la depuración. Afortunadamente, basta con hacer clic en el icono "Detener" en la barra de herramientas de depuración para desasociar al depurador sin que afecte a otros invitados o el host.

![Botón de detención de depurador de código de VS](../media/vscode-debug-stop.png)

Si ha actualizado la configuración por lo que ya no la asociación automática o si simplemente desea volver a adjuntar más adelante, puede hacerlo presionando **Ctrl + Mayús + P / Cmd + Mayús + P** o **al hacer clic en** en el elemento de barra de estado de estado de sesión y al seleccionar "Conectar a unos depuración sesión compartida".

![VS Code adjuntar depurador](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>Uso compartido de la aplicación en ejecución en un explorador

Código de Visual Studio no tiene el concepto de un conocido "puerto de aplicación web", como Visual Studio para tipos de proyecto, como ASP.NET. Sin embargo, si va a unir a una sesión de colaboración de un host de Visual Studio, es posible que automáticamente aparece el explorador predeterminado al iniciar, es decir, a continuación, automáticamente se conecta a las aplicaciones en ejecución del host la depuración. Consulte [características de Visual Studio](vs.md#automatic-web-app-sharing) para obtener más detalles.

Como un host, puede conseguir algo similar al compartir manualmente la aplicación u otros extremos, como los servicios RESTful mediante la característica de "Servidor Local de recursos compartidos". Los invitados de Visual Studio y VS Code, a continuación, pueden abrir un explorador en el mismo puerto localhost para ver la aplicación en ejecución.  Consulte [compartir un servidor](#share-a-server) para obtener más detalles.

## <a name="share-a-server"></a>Compartir un servidor

De vez en cuando, como un host de sesión de colaboración, es posible que desee compartir una aplicación web u otros localmente que ejecutan servidores o servicios con los invitados. Esto puede variar desde otros puntos de conexión RESTful a las bases de datos y otros servidores. Compartir Live de Visual Studio le permite especificar un número de puerto local, opcionalmente, asignarle un nombre y, después, compartirlo con todos los invitados.

Los invitados, a continuación, podrá tener acceso al servidor que ha compartido en ese puerto desde su propio equipo local en el mismo puerto exacto. Por ejemplo, si comparte un servidor web **que se ejecuta en el puerto 3000**, el invitado puede tener acceso a ese mismo servidor web en ejecución en sus **propia máquina** en http://localhost:3000! Esto se logra a través de un túnel SSH o SSL seguro entre el host y los invitados y autenticado a través del servicio, por lo que puede estar seguro de que sólo los de la sesión de colaboración tienen acceso.

> **Sugerencia de seguridad:** Como un host, debe ser muy selectivo con los puertos que comparte con los invitados y ajustarse a los puertos aplicación (en lugar de compartir un puerto del sistema). Para los invitados, los puertos compartidos se comportarán exactamente como lo harían si se estaba ejecutando el servicio de servidor en su propio equipo. Esto es muy útil, pero si se comparte un puerto incorrecto también puede ser arriesgado.

Por motivos de seguridad, solo los servidores que se ejecutan en los puertos que especifique están disponibles para otros invitados. Afortunadamente, resulta fácil agregar uno de ellos como la sesión de colaboración **host**. Esta es la manera de hacerlo:

1. Abra la pestaña personalizada de Live Share en la barra de actividad de VS Code o la vista del explorador de recursos compartidos de Live y seleccione "recurso compartido servidor..." entrada o haga clic en el icono.

    ![Servidor local de recurso compartido de código de VS](../media/vscode-share-local-server-viewlet.png)<br />

1. Escriba el número de puerto que se ejecuta en el servidor y, opcionalmente, un nombre.

    ![Captura de pantalla de símbolo del sistema del número de puerto](../media/vscode-enter-port.png)<br />

Ya está. El servidor en el puerto que especificó se asignarán al host local de cada invitado en el mismo puerto (a menos que ese puerto ya estaba ocupado).

Si el puerto ya está en uso en el equipo de invitado, automáticamente se selecciona uno diferente. Afortunadamente, como un invitado, puede ver una lista de puertos compartidos actualmente (por nombre si se especifica) en la vista de explorador Live de recurso compartido o una pestaña personalizada en la barra de actividades de VS Code y buscar en la lista de servidores compartidos. Al seleccionar una entrada, abre ese servidor en el explorador. También puede haga clic y seleccione la opción para copiar el vínculo en el servidor en el Portapapeles.

![Servidor local de acceso de código de VS](../media/vscode-access-shared-server-viewlet.png)<br />

Tenga en cuenta que *invitados no* controlar qué puertos en la máquina del host se comparten por motivos de seguridad.

Para **detener** uso compartido de un servidor local como el host, mantenga el mouse sobre la entrada del servidor en la lista de servidores compartidos en la vista del explorador de recursos compartidos en vivo o la pestaña personalizada y haga clic en el icono de "Servidor de dejar de compartir".

![Frente a código Detener uso compartido de servidor](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>Compartir un terminal

El desarrollo moderno hace un uso frecuente de una amplia gama de herramientas de línea de comandos. Afortunadamente, compartir Live le permite, como un host, para "compartir opcionalmente un terminal" con los invitados. El terminal compartido puede ser de solo lectura o de colaboración totalmente por lo que usted y los invitados pueden ejecutar comandos y ver los resultados. Puede dar visibilidad de los invitados a la salida de terminal o bien permitirles obtener prácticas y ejecución de pruebas, compilaciones o problemas de específicas del entorno incluso de evaluación de errores que se producen sólo en el equipo.

Sin embargo, los elementos terminales son **no** comparten de forma predeterminada ya que proporcionan los invitados acceso de solo lectura al menos a la salida de comandos que ejecute (si no la capacidad de ejecutar comandos ellos mismos). Este modo, puede ejecutar comandos en terminales locales sin riesgo libremente y sólo compartir cuando en realidad debe hacerlo. Además, solo los hosts pueden iniciar terminales compartidos para evitar que los invitados de iniciarse una y hacer algo que no espera ni viendo.

Como un host, puede compartir un terminal, abre la pestaña personalizada de Live compartir en la barra de actividad de VS Code o la vista del explorador de compartir en vivo y seleccione "recurso compartido de servidor..." entrada o al hacer clic en el icono.

![Recurso compartido de terminal de VS Code](../media/vscode-share-terminal-viewlet.png)<br />

En este momento, puede seleccionar sólo lectura o lectura/escritura terminal en el menú. Si el terminal es lectura/escritura, todo el mundo puede escribir en el terminal incluido el host, lo que facilita la intervenir si un invitado está haciendo algo que no le gusta. Sin embargo, para estar seguros, debería **únicamente conceda acceso de lectura/escritura a los invitados cuando se sabe que necesitan realmente** y sígala terminales de solo lectura para escenarios donde desea que el invitado para ver la salida de los comandos que ejecute.

> [!NOTE]
> Si la sesión de colaboración está en modo de solo lectura, los terminales de sólo lectura pueden compartirse por el host.

![Solo lectura o lectura/escritura selección](../media/vscode-share-terminal-ro-rw.png)<br />

Una vez que haya seleccionado el tipo de terminal compartida que desee iniciar, aparecerá un nuevo terminal compartido en la ficha de terminales de VS Code.

![Ejecución de terminal compartida](../media/vscode-share-terminal-up.png)<br />

Si se comparten varios terminales, o el foco está en una ficha diferente, puede llevar el foco a un terminal específico mediante la selección de la entrada en la lista de los terminales compartido.

![Terminal compartida llevar el foco](../media/vscode-shared-terminal-focus.png)<br />

Para finalizar la sesión de terminal, simplemente escriba exit, cierre la ventana del terminal o haga clic en el icono "Terminal de dejar de compartir" en la vista del explorador de recursos compartidos en vivo o pestaña personalizada y todos los usuarios se desconectarán.

## <a name="session-states"></a>Estados de sesión

Una vez que se iniciaron o unido a la sesión de colaboración y dispone de acceso al contenido compartido, los elementos de barra de estado de Visual Studio Live Share actualizan su aspecto para reflejar el estado de la sesión de colaboración activos.

Estos son los Estados que normalmente solo verá:

| Estado | Barra de estado | Descripción |
|-------|--------------------|-------------|
| inactivo | ![Estado del código de VS: inactivo](../media/vscode-status-share.png) | No hay ninguna sesión de colaboración active y nada se comparte. |
| Host: Uso compartido en curso | ![Estado del código de VS: compartir en curso](../media/vscode-status-sharing.png)| Se está iniciando una sesión de colaboración y uso compartido de contenido comenzará en breve. |
| Host: Uso compartido de recursos | ![Estado del código de VS: uso compartido de activos ](../media/vscode-status-active.png)| Se activa una sesión de colaboración y contenido se comparte. |
| Host: Uso compartido de solo lectura | ![Estado del código de VS: uso compartido de solo lectura](../media/vscode-status-sharing-read-only.png)| Uso compartido de una sesión de colaboración de solo lectura. |
| Invitado: Unirse a la sesión | ![Estado del código de VS: unirse a](../media/vscode-status-joining.png)| Unirse a una sesión de colaboración existente. |
| Invitado: Unirse | ![Estado del código de VS: unido](../media/vscode-status-active.png) | Unido y conectado a una sesión de colaboración active y recepción de contenido compartido. |
| Invitado: Unido a solo lectura | ![Estado del código de VS: Unido de solo lectura](../media/vscode-status-joined-read-only.png) | Unido y conectado a una sesión de colaboración activa de solo lectura. |

## <a name="guest-limitations"></a>Limitaciones de invitado

Aunque actualmente hay algunos puntos débiles invitados experimentará al usar las características que se ha descrito anteriormente, los hosts de sesión de colaboración conservan toda la funcionalidad de su herramienta preferida. Para obtener más información, vea las secciones siguientes:

- [Compatibilidad con lenguajes y plataformas](../reference/platform-support.md)
- [Compatibilidad con extensiones](../reference/extensions.md)
- [Todos los errores principales, las solicitudes de características y limitaciones](https://aka.ms/vsls-issues)
- [Todas las solicitudes de características y limitaciones](https://aka.ms/vsls-feature-requests)
- [Solución de problemas](../troubleshooting.md)

## <a name="next-steps"></a>Pasos siguientes

Consulte estos artículos adicionales para obtener más información.

- [Inicio rápido: Comparta su primer proyecto](../quickstart/share.md)
- [Inicio rápido: Únase a la primera sesión](../quickstart/share.md)
- [Cómo: Colaborar mediante Visual Studio](vs.md)
- [Requisitos de conectividad de Live Share](../reference/connectivity.md)
- [Características de seguridad de Live Share](../reference/security.md)
- [Detalles de la instalación de Linux](../reference/linux.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
