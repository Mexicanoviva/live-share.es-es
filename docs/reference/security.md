---
title: Security - Visual Studio Live Share | Microsoft Docs
description: Información sobre las características de seguridad de Visual Studio Live Share.
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 754a740118ef9e6de2463fb3bb0537af350409aa
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640203"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Características de seguridad de Live Share

Sesiones de colaboración en Visual Studio Live Share son eficaces en que permiten a cualquier número de personas a unirse en una sesión y en colaboración editar, depurar y mucho más. Sin embargo, dado este nivel de acceso, sin duda estará interesado en las características de seguridad que proporciona Live Share. En este artículo, le presentaremos algunas recomendaciones y opciones para proteger su entorno según sea necesario.

**Al igual que con cualquier herramienta de colaboración, recuerde que solo debe compartir su código, contenido y aplicaciones con usuarios de que confianza.**

## <a name="connectivity"></a>Conectividad

Todas las conexiones en Visual Studio Live Share son SSH o SSL cifradas y autenticadas contra un servicio central para asegurarse de que sólo los de la sesión de colaboración pueden tener acceso a su contenido. De forma predeterminada, Live Share intenta una conexión directa y recurre a una retransmisión en la nube si no se puede establecer una conexión entre el invitado y el host. Observe que la retransmisión de la nube en vivo del recurso compartido no conserva todo el tráfico que se enruta a través de él y no "consultar" el tráfico de ninguna manera. Sin embargo, si prefiere no se debe utilizar la retransmisión puede cambiar la configuración siempre se conecte directamente.

Para obtener más información acerca de la modificación de estos comportamientos y requisitos de conectividad de la vida del recurso compartido, consulte  **[los requisitos de conectividad para Live Share](connectivity.md)**.

## <a name="invitations-and-join-access"></a>Invitaciones y acceso de combinación

Cada vez que inicie una nueva sesión de colaboración, Live Share genera un **nuevo identificador único** que se coloca en el vínculo de invitación. Estos vínculos proporcionan una base sólida y segura para invitar a los que confía ya que el identificador del vínculo es "no adivinar" y es _solo es válido para la duración de una sesión de colaboración único_.

### <a name="removing-an-unexpected-guest"></a>Eliminación de un invitado inesperado

Como un host, se le notificará automáticamente siempre que la sesión de colaboración une a un invitado.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

Aún mejor, la notificación le ofrece la capacidad para quitar a un invitado que se ha unido si por alguna razón no sabe que ellos. (Por ejemplo, si por accidente registró su vínculo en un sistema de chat en toda la empresa y Unidos un empleado). Simplemente haga clic en el botón "Quitar" en la notificación que aparece y se expulsará desde la sesión de colaboración.

En **VS Code**, incluso aunque haya descartado una notificación de combinación, también tiene la capacidad para quitar un participante después de eso. Al abrir la vista de Live Share en el explorador o en la ficha personalizada en la barra de actividad de VS Code, mantenga el mouse sobre o haga clic en nombre de un participante y seleccione el icono "Remove participante" o la opción.

![Quitar a participante en VS Code](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>Requerir la aprobación de invitado

Normalmente, los participantes que se unen a una sesión de colaboración serán **ha iniciado sesión en Live Share** con un profesional de Microsoft o cuenta educativa (AAD), cuenta Microsoft personal o cuenta de GitHub. Mientras que "notificación + remove" predeterminada para que inicien sesión en los usuarios proporciona una buena combinación de velocidad y control de estos invitados, puede desear **bloquear las cosas** un poco más si se esté haciendo algo confidenciales.

Además, en determinadas circunstancias forzar todos los invitados para iniciar sesión en unirse a una colaboración sesión puede ser problemática. Algunos ejemplos son pedir a alguien familiarizado con Live Share a unirse como un invitado, escenarios de aprendizaje en clase, o al colaborar con alguien que no tiene uno de los tipos de cuenta compatibles. Por estos motivos, Live Share puede permitir que los usuarios que son **no ha iniciado sesión** unirse a sesiones de colaboración como **de sólo lectura** invitados. Mientras que el host debe **aprobar** estos invitados antes de que pueden unirse de forma predeterminada, puede aprobarlas siempre en su lugar o no permitir estos invitados "anonymous".

#### <a name="requiring-guest-approval-for-signed-in-users"></a>Que requiere aprobación de invitado para que inicien sesión en los usuarios

Si desea evitar que inicien sesión en los invitados de unirse a la colaboración sesiones hasta que se han "aprobado" que, cambie la configuración siguiente:

* En **VS Code**, agregue lo siguiente al settings.json (archivo > Opciones > configuración):

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* En **Visual Studio**, conjunto de herramientas > Opciones > Live Share > "Requerir aprobación de invitado" en True.

    ![Ventana de configuración de Visual Studio con la configuración de invitado aprobación, resaltado](../media/vs-setting-guestapproval.png)

Desde este punto, se le pedirá que apruebe a cada invitado que se une.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-approval.png" width="100%" alt="Visual Studio Code join approval request" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-approval.png" width="100%" alt="Visual Studio join approval request"/>
    </td>
</tr>
</table>

Como invitado, si se une a una sesión en el host tiene esta opción habilitada, se le notificará en la barra de estado o únase a cuadro de diálogo que está esperando Live Share en el host para aprobar.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>Aceptación o rechazo de automática a los usuarios que no haya iniciado sesión (anónimo)

Como se describió anteriormente, Live Share puede configurarse para permitir **a los usuarios que no han iniciado sesión** unirse a una sesión de colaboración como **de sólo lectura** invitados.  Aunque todos éstos **invitados "anónimos" deben especificar un nombre** cuando se unen, un nombre simple no proporciona el mismo nivel de seguridad como un inicio de sesión real. Por lo tanto, **de forma predeterminada, el host se le solicita que apruebe** cualquier invitado anónimo independientemente de la opción "Requerir aprobación de invitado" establecimiento se ha descrito anteriormente.

También puede **rechazar siempre** (deshabilitar los visitantes anónimos) o **Aceptar siempre** los usuarios anónimos en su lugar, como se indica a continuación:

* En **VS Code**, establezca `liveshare.anonymousGuestApproval` en settings.json (archivo > Preferencias > configuración) para `accept`, `reject`, o `prompt` (valor predeterminado) según corresponda.

* En **Visual Studio**, conjunto de herramientas > Opciones > Live Share > "aprobación de invitado anónimo" para aceptar, rechazar o símbolo del sistema (predeterminado) como corresponda.

 **No obstante, recuerde que sólo se debe enviar Live Share vínculos de invitación a las personas de confianza.**

## <a name="controlling-file-access-and-visibility"></a>Visibilidad y control de acceso de archivo

Como invitado, remoto modelo Live del recurso compartido le acceso de lectura/escritura rápida a archivos y carpetas que el host ha compartido con usted sin tener que sincronizar todo el contenido de un proyecto. Puede, por tanto, por separado navegar y editar archivos en el árbol de todo archivo compartido. **Sin embargo, esta libertad suponer ciertos riesgos al host.** Conceptualmente, un desarrollador podría optar por ir y modificar código fuente sin su conocimiento o ver código fuente confidenciales o "secretos" ubicados en algún lugar en el árbol de archivos compartidos. Por lo tanto, como un host, es posible que no desea que siempre del invitado para tener acceso a la totalidad de un proyecto que se va a compartir. Afortunadamente, una ventaja adicional de este modelo remoto es que puede optar por "excluir" que no desea compartir con nadie sin sacrificar la funcionalidad de archivos. Los invitados todavía pueden participar en cosas como las sesiones que normalmente necesitaría tener acceso a estos archivos si alguien desea hacerlo en sus propias de depuración.

Puede hacerlo agregando una **. vsls.json** archivo a la carpeta o proyecto que se va a compartir. Cualquier configuración que agregue a este archivo con formato json cambia cómo Live Share procesa los archivos. Además de proporcionar un control directo, estos archivos también se pueden confirmados al control de código fuente para cualquier persona la clonación de un proyecto podrá aprovechar las ventajas de estas reglas con ningún esfuerzo adicional por su parte.

Este es un ejemplo. archivo vsls.json:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"none",
    "excludeFiles":[
        "*.p12",
        "*.cer",
        "token",
        ".gitignore"
    ],
    "hideFiles": [
        "bin",
        "obj"
    ]
}
```

> [!NOTE]
> También puede hacer los todos los archivos o carpetas que comparte **de sólo lectura** al iniciar una sesión de colaboración. Consulte [debajo](#read-only-mode) para obtener más información.

Veamos cómo estas propiedades cambian a lo que pueden hacer los invitados.

### <a name="properties"></a>Propiedades

El **excludeFiles** propiedad le permite especificar una lista de patrones de archivo globales (muy similar a los que encuentra los archivos .gitignore muy) que evitan que Live Share abrir determinados archivos o carpetas para los invitados. Tenga en cuenta que esto incluye escenarios como un invitado _siguiendo o saltar a la ubicación de la edición, ejecución paso a paso en un archivo durante la depuración colaborativa, las características de navegación de código, como ir a definición y mucho más._ Se está diseñado para archivos que no desea compartir bajo ninguna circunstancia, como aquellas que contienen secretos, certificados o las contraseñas nunca. Por ejemplo, dado que controlar la seguridad,. vsls.json archivos siempre quedan excluidos.

El **hideFiles** propiedad es similar, pero no tan estricta. Estos archivos simplemente se ocultan en el árbol de archivos. Por ejemplo, si se ha ocurrido paso a paso por uno de estos archivos durante la depuración, todavía está abierto en el editor. Esta propiedad es especialmente útil si no tiene un programa de instalación del archivo .gitignore (como sería el caso si usa un sistema de control de código fuente diferente) o si desea aumentar lo que está ahí evitar el desorden o confusión.

El **gitignore** configuración establece cómo Live Share debería procesar el contenido de los archivos .gitignore en las carpetas compartidas. De forma predeterminada, cualquier globs que se encuentra en los archivos .gitignore se tratan como si se especificaron en la propiedad "hideFiles". Sin embargo, puede elegir un comportamiento diferente mediante uno de los siguientes valores:

| Opción    | Resultado                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | contenido del archivo .gitignore es visible para los invitados en el árbol de archivos (suponiendo que no se filtran por un editor invitado establecer). |
| `hide`    | **El valor predeterminado.** Globs dentro .gitignore se procesan como si estuvieran en la propiedad "hideFiles".                   |
| `exclude` | Globs dentro .gitignore se procesan como si estuvieran en la propiedad "excludeFiles".                                 |

Una desventaja de la `exclude` configuración es que el contenido de carpetas como node_modules es a menudo en .gitignore, pero puede ser útil para depurar paso a paso durante la depuración. Por lo tanto, Live Share admite la capacidad para invertir una regla mediante "!" en la propiedad excludeFiles. Por ejemplo, esto. archivo vsls.json podría excluir todo el contenido de ".gitignore" excepto node_modules:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

Las reglas de ocultar y excluir se procesan por separado, por lo que si desea ocultar node_modules para reducir el desorden sin realmente excluyéndola, simplemente puede editar el archivo como sigue:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ],
    "hideFiles":[
        "node_modules"
    ]
}
```

### <a name="vslsjson-files-in-sub-folders"></a>. vsls.json archivos en subcarpetas

Por último, al igual que .gitignore,. vsls.json archivos se pueden colocar en las subcarpetas. Ocultar o excluir reglas se determinan a partir de la. archivo vsls.json en la carpeta raíz que han compartido (si existe) y, a continuación, entrando en cada subcarpeta provoque allí a un archivo dado que se busca. vsls.json archivos al proceso. El contenido de. vsls.json archivos en carpetas aparece más abajo en el árbol de archivos, a continuación, complementar (o invalidar) las reglas establecidas en niveles superiores.

### <a name="disabling-external-file-sharing"></a>Deshabilitar el uso compartido de archivos externos

De forma predeterminada, Live compartir también compartirán los archivos que se abre el host que son externos a la carpeta compartida / solución. Esto facilita abrir rápidamente otros archivos relacionados sin tener que volver a compartir.

Si prefiere deshabilitar esta característica:

* En **VS Code**, agregue lo siguiente al settings.json:

    ```json
    "liveshare.shareExternalFiles": false
    ```

* En **Visual Studio**, conjunto de herramientas &gt; opciones &gt; Live Share &gt; "Recurso compartido de archivos externos" en False

## <a name="read-only-mode"></a>Modo de solo lectura

En ocasiones, al compartir su código como un host, no desea que los invitados para realizar modificaciones. Puede necesitar su invitado echar un vistazo a algunos del código, o se muestran el proyecto a un gran número de invitados y no desea que se realicen cualquier modificaciones accidentales o innecesarias. Recurso compartido de Live ofrece la capacidad de compartir proyectos en modo de solo lectura.

Como un host, cuando se comparte, tiene la opción para habilitar el modo de solo lectura para una sesión de colaboración. Cuando se une a un invitado, no podrá realizar modificaciones en el código, aunque pueden seguir viendo los cursores de la otra y se resaltan así como navegar por el proyecto.

Aún puede depurar conjuntamente con los invitados en el modo de solo lectura. Los invitados no tendrán la capacidad de paso a través del proceso de depuración, pero puede aún agregue o quite los puntos de interrupción e inspeccionar las variables. Además, todavía puede compartir terminales (es de solo lectura) y servidores con los invitados.

Puede aprender más acerca de cómo iniciar una sesión de colaboración de solo lectura: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>Depuración conjunta

Al que enfrenta a problemas de codificación complejos o errores, puede ser muy útil tener un par de ojos adicionales durante la depuración. Visual Studio Live Share permite "depuración colaboración" o "conjuntamente depurar" al compartir la sesión de depuración con todos los invitados cada vez que inicia el host de depuración.

Como un host, tiene control completo sobre cuando se inicia una sesión de depuración o se detiene, pero la depuración conjunta suponer ciertos riesgos si va a compartir con alguien que no es de confianza. Recurso compartido en vivo permite que los invitados invitar para ejecutar comandos de consola/REPL y, por tanto, hay **un riesgo de un individuo malintencionado ejecutar un comando no querría que se ejecuten**.

Por consiguiente, debería **solo depurar conjuntamente con los que confíe.**

Más información: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>Uso compartido de un servidor local

Al depurar conjuntamente, puede ser muy útil obtener acceso a diferentes partes de la aplicación ofrecidas por el anfitrión para la sesión de depuración. Puede acceder a la aplicación en un explorador, obtener acceso a una base de datos local o alcanza un punto de conexión REST desde sus herramientas. Live Share le permite "recurso compartido de un servidor" que se asigna un puerto local en la máquina del host en el mismo puerto exacto en la máquina del invitado. Como invitado, entonces puede interactuar con la aplicación exactamente como si se ejecutara localmente en su máquina (p. ej. el host e invitado pueden ambas tener acceso a una aplicación web que se ejecutan en http://localhost:3000).

Sin embargo, como un host, debe **sea muy selectivo con los puertos que comparte** con los invitados y recurso compartido de solo aplicación puertos en su lugar los puertos del sistema. En el caso de los invitados, los puertos compartidos se comportarán exactamente igual que si el servidor o servicio se estuviese ejecutando en su propia máquina. Esto es muy útil, pero podría ser también arriesgado si es que se comparte el puerto incorrecto. Por este motivo, Live Share no realizar ninguna suposición sobre qué se debe o no debe compartirse sin un valor de configuración y el host que realiza una acción.

En Visual Studio, el **puerto de la aplicación de web** especificados en los proyectos de ASP.NET es **compartido automáticamente durante la depuración solo** para facilitar el acceso de invitado a la aplicación web cuando se ejecuta. Sin embargo, puede desactivar esta automatización estableciendo Herramientas > Opciones > Live Share > "Recurso compartido de web app de depuración" en "False" Si lo prefiere.

En el código de Visual Studio, Live compartir intenta **detectar los puertos de aplicación adecuada** y compartirlos. Sin embargo, puede deshabilitar agregando la siguiente settings.json:

        liveshare.autoShareServers: false

En cualquier caso, tome precauciones cuando uso compartido de puertos adicionales.

Puede aprender más acerca de cómo configurar la característica aquí: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>Uso compartido de una ventana de terminal

El desarrollo moderno hace un uso frecuente de una amplia gama de herramientas de línea de comandos. Afortunadamente, como anfitrión, Live Share le permite, de forma opcional, "compartir un terminal" con los invitados. El terminal compartido puede ser de solo lectura o totalmente colaborativo, para que tanto usted como los invitados puedan ejecutar comandos y ver los resultados. Como el host, podrá permitir que otros colaboradores a uno solo verá la salida o para usar cualquier número de línea de comandos, herramientas para ejecutar pruebas, compilaciones, o incluso evaluar problemas específicos del entorno.

Solo los hosts pueden empezar a terminales compartidos para evitar que los invitados de iniciarse una y hacer algo que no espera ni viendo. Cuando se inicia un terminal compartido como un host, puede especificar si debe ser de solo lectura o lectura/escritura. Si el terminal es de lectura/escritura, todos los participantes pueden escribir en el terminal, incluido el anfitrión, lo que permite intervenir fácilmente si un invitado hace algo que no le gusta. Sin embargo, para estar seguros, debería **darle acceso de lectura/escritura a los invitados solo cuando sabe que realmente lo necesitan**  y limitarse a los terminales de solo lectura en escenarios donde quiere que un invitado solo vea la salida de los comandos que ejecuta.

En Visual Studio, los terminales no se comparten de forma predeterminada. En VS Code, se comparten automáticamente terminales **de sólo lectura** de forma predeterminada. Sin embargo, puede deshabilitar agregando la siguiente settings.json:

```json
"liveshare.autoShareTerminals": false
```

Más información: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>Consentimiento del administrador AAD

Al inicio de sesión con un Microsoft seguridad **profesional o educativa de la dirección de correo electrónico** verá un mensaje informando de **"Necesita la aprobación del administrador"** al iniciar sesión. Esto es porque Live Share requiere acceso de lectura a la información de usuario para sus características de seguridad y el inquilino de Azure AD está configurado para requerir "consentimiento del administrador" para tener acceso al contenido del directorio de aplicaciones nuevas.

El Administrador de AD necesita resolver este problema automáticamente mediante la siguiente información:

* **Nombre de la aplicación**: Visual Studio Live Share (Insider)
* **Tipo de aplicación**: Aplicación web
* **Estado de las aplicaciones**: Producción
* **Permisos delegados**: User.Read
* **Dirección URL de la aplicación**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **Dirección URL de respuesta**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Esto solo tendría que realizarse una vez para cualquier persona que use Live Share. Consulte [aquí](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) y [aquí](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) para obtener más información.

## <a name="see-also"></a>Vea también

* [Colaboración colaborar mediante Visual Studio Code](../use/vscode.md)
* [Procedimientos para mediante Visual Studio](../use/vs.md)
* [Requisitos de conectividad de Live Share](connectivity.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
