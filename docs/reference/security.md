---
title: Visual Studio Live Share de seguridad | Microsoft Docs
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
ms.openlocfilehash: 2f3a2adf0be13071f22a8ea7e33800af6f9099b5
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170106"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Características de seguridad de Live Share

Las sesiones de colaboración en Visual Studio Live Share son eficaces, ya que permiten que cualquier número de personas se unan en una sesión y edición colaborativa, depuración, etc. Sin embargo, dado este nivel de acceso, indudablemente le interesarán las características de seguridad Live Share proporciona. En este artículo, proporcionaremos algunas recomendaciones y opciones para proteger su entorno según sea necesario.

**Como con cualquier herramienta de colaboración, recuerde que solo debe compartir el código, el contenido y las aplicaciones con personas de confianza.**

## <a name="connectivity"></a>Conectividad

Todas las conexiones en Visual Studio Live Share son SSH o SSL cifradas y autenticadas con un servicio central para asegurarse de que solo las de la sesión de colaboración puedan obtener acceso a su contenido. De forma predeterminada, Live Share intenta una conexión directa y recurre a una retransmisión en la nube si no se puede establecer una conexión entre el invitado y el host. Tenga en cuenta que la retransmisión en la nube de Live Share no conserva ningún tráfico enrutado a través de ella y no "Snoop" el tráfico de ningún modo. Sin embargo, si prefiere no usar la retransmisión, puede cambiar la configuración para conectar siempre directamente.

Para obtener más información sobre la modificación de estos comportamientos y los requisitos de conectividad de Live Share, consulte **[requisitos de conectividad para Live share](connectivity.md)** .

## <a name="invitations-and-join-access"></a>Invitaciones y unirse a Access

Cada vez que se inicia una nueva sesión de colaboración, Live Share genera un **nuevo identificador único** que se coloca en el vínculo de invitación. Estos vínculos proporcionan una base sólida y segura para invitar a los usuarios de confianza, ya que el identificador del vínculo es "no adivinable" y _solo es válido para la duración de una sola sesión de colaboración_.

### <a name="removing-an-unexpected-guest"></a>Quitar un invitado inesperado

Como host, se le notificará automáticamente cada vez que un invitado se una a la sesión de colaboración.

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

Mejor aún, la notificación le ofrece la posibilidad de quitar un invitado que se ha unido si por alguna razón no lo conoce. (Por ejemplo, si ha publicado accidentalmente el vínculo en un sistema de chat de toda la compañía y se ha unido un empleado aleatorio). Simplemente haga clic en el botón "quitar" en la notificación que aparece y se expulsarán de la sesión de colaboración.

En **vs Code**, incluso si ha descartado una notificación de combinación, también tiene la posibilidad de quitar un participante después. Al abrir la vista de Live Share en el explorador o en la pestaña personalizada de la barra de actividades VS Code, puede mantener el mouse sobre el nombre de un participante o hacer clic con el botón secundario en él y seleccionar el icono o la opción "quitar participante".

![Quitar participante en VS Code](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>Requerir aprobación de invitado

Normalmente, los participantes que se unen a una sesión de colaboración iniciarán **sesión en Live share** mediante una cuenta profesional o educativa de Microsoft (AAD), un cuenta de Microsoft personal o una cuenta de github. Aunque el valor predeterminado de "notificación + quitar" para los usuarios que han iniciado sesión proporciona una buena combinación de velocidad y control para estos invitados, puede que le interese **reducir** un poco más si está haciendo algo sensible.

Además, en determinadas circunstancias obliga a todos los invitados a iniciar sesión para unirse a una sesión de colaboración puede ser problemático. Entre los ejemplos se incluye pedir a alguien nuevo que Live Share unirse como invitado, escenarios de formación y aprendizaje, o al colaborar con alguien que no tiene uno de los tipos de cuenta admitidos. Por estos motivos, Live Share puede permitir que los usuarios que **no han iniciado sesión** se unan a sesiones de colaboración como invitados **de solo lectura** . Aunque el host necesita **aprobar** estos invitados antes de que se puedan unir de forma predeterminada, es posible que desee denegar estos invitados "anónimos" o bien aprobarlos siempre en su lugar.

#### <a name="requiring-guest-approval-for-signed-in-users"></a>Requerir aprobación de invitado para usuarios con sesión iniciada

Si desea evitar que los invitados con sesión iniciada se unan a sus sesiones de colaboración hasta que los haya "aprobado", cambie la configuración siguiente:

* En **vs Code**, agregue lo siguiente a Settings. JSON (preferencias de > de archivo > configuración):

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* En **Visual Studio**, establezca herramientas > opciones > Live share > "requerir aprobación de invitado" en true.

    ![Ventana de configuración de Visual Studio con la configuración de aprobación de invitado resaltada](../media/vs-setting-guestapproval.png)

A partir de este punto, se le pedirá que apruebe cada invitado que se combina.

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

Como invitado, si se une a una sesión en la que el host tiene esta configuración habilitada, se le notificará en la barra de estado o en el cuadro de diálogo de combinación que Live Share espera en el host para su aprobación.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>Rechazar o aceptar automáticamente usuarios que no han iniciado sesión (anónimo)

Como se describió anteriormente, Live Share se pueden configurar para permitir **que los usuarios que no han iniciado** sesión se unan a una sesión de colaboración como invitados **de solo lectura** .  Aunque estos **invitados "anónimos" deben escribir un nombre** al unirse, un nombre simple no proporciona el mismo nivel de confianza que un inicio de sesión real. Por lo tanto, de **forma predeterminada, se solicita al host que apruebe** cualquier invitado anónimo independientemente de la configuración de "requerir aprobación de invitado" que se ha descrito anteriormente.

Siempre puede **rechazar** (deshabilitar invitados anónimos) o **Aceptar siempre** usuarios anónimos, como se indica a continuación:

* En **vs Code**, establezca `liveshare.anonymousGuestApproval` en Settings. JSON (el archivo > Preferencias > configuración) en `accept`, `reject`o `prompt` (valor predeterminado) según corresponda.

* En **Visual Studio**, establezca herramientas > opciones > Live share > "aprobación de invitado anónimo" para aceptar, rechazar o preguntar (valor predeterminado) según corresponda.

 **Tenga en consideración que solo debe enviar vínculos de invitación Live Share a personas en las que confíe.**

## <a name="controlling-file-access-and-visibility"></a>Controlar el acceso y la visibilidad de los archivos

Como invitado, el modelo remoto de Live Share le proporciona acceso de lectura y escritura rápido a los archivos y carpetas que el host ha compartido con usted sin tener que sincronizar todo el contenido de un proyecto. Por tanto, puede navegar por los archivos y editarlos de forma independiente en todo el árbol de archivos compartidos. **Sin embargo, esta libertad plantea algunos riesgos para el host.** En concepto, un desarrollador podría optar por entrar y modificar el código fuente sin su conocimiento o ver el código fuente confidencial o "secretos" ubicado en algún lugar del árbol de archivos compartido. Por lo tanto, como un host, es posible que no siempre quiera que el invitado tenga acceso a todo el proyecto que está compartiendo. Afortunadamente, una ventaja adicional de este modelo remoto es que puede optar por "excluir" los archivos que no desea compartir con nadie sin sacrificar la funcionalidad. Los invitados todavía pueden participar en cosas como las sesiones de depuración que normalmente necesitarían acceder a estos archivos si quisiera hacerlo por sí solos.

Para ello, agregue un archivo **. vsls. JSON** a la carpeta o el proyecto que está compartiendo. Cualquier configuración que agregue a este archivo con formato JSON cambia el modo en que Live Share procesa los archivos. Además de proporcionar control directo, estos archivos también se pueden confirmar en el control de código fuente, por lo que cualquier persona que pueda clonar un proyecto podrá aprovechar estas reglas sin ningún esfuerzo adicional por su parte.

Este es un archivo de ejemplo. vsls. JSON:

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
> También puede hacer que todos los archivos o carpetas que comparte sea **de solo lectura** cuando se inicia una sesión de colaboración. Consulte [a continuación](#read-only-mode) para obtener más información.

Veamos cómo cambian estas propiedades qué pueden hacer los invitados.

### <a name="properties"></a>Propiedades

La propiedad **excludeFiles** permite especificar una lista de patrones de archivos Glob (muy parecidos a los archivos. gitignore) que evitan que Live share abra determinados archivos o carpetas para invitados. Tenga en cuenta que esto incluye escenarios como un invitado _que sigue o salta a la ubicación de edición, pasando a un archivo durante la depuración colaborativa, cualquier característica de navegación por el código como ir a definición, etc._ Está destinada a archivos que no desea compartir en ninguna circunstancia, como aquellos que contienen secretos, certificados o contraseñas. Por ejemplo, dado que controlan la seguridad, los archivos. vsls. JSON siempre se excluyen.

La propiedad **hideFiles** es similar, pero no es tan estricta. Estos archivos simplemente están ocultos en el árbol de archivos. Por ejemplo, si ha tenido que ir a uno de estos archivos durante la depuración, sigue abierto en el editor. Esta propiedad es principalmente útil si no tiene una configuración de archivos. gitignore (como sería el caso si utiliza un sistema de control de código fuente diferente) o si simplemente desea aumentar lo que ya existe para evitar el desorden o la confusión.

La configuración **gitignore** establece cómo debe procesar Live share el contenido de los archivos. gitignore en carpetas compartidas. De forma predeterminada, cualquier globs que se encuentre en los archivos. gitignore se trata como si se hubiera especificado en la propiedad "hideFiles". Sin embargo, puede elegir un comportamiento diferente con uno de los siguientes valores:

| Opción    | Resultado                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | el contenido de. gitignore es visible para los invitados en el árbol de archivos (suponiendo que no se filtre por una configuración de editor invitado). |
| `hide`    | **Valor predeterminado.** Globs Inside. gitignore se procesan como si estuvieran en la propiedad "hideFiles".                   |
| `exclude` | Globs Inside. gitignore se procesan como si estuvieran en la propiedad "excludeFiles".                                 |

Una desventaja de la configuración `exclude` es que el contenido de las carpetas como node_modules con frecuencia es. gitignore, pero puede ser útil para depurar durante la depuración. Por consiguiente, Live Share admite la posibilidad de invertir una regla mediante "!" en la propiedad excludeFiles. Por ejemplo, este archivo. vsls. JSON excluiría todo de ". gitignore", salvo node_modules:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

Las reglas de ocultación y exclusión se procesan por separado, por lo que si desea ocultar node_modules para reducir la aglomeración sin excluirla realmente, puede modificar el archivo de la siguiente manera:

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

### <a name="vslsjson-files-in-sub-folders"></a>archivos. vsls. JSON en subcarpetas

Por último, al igual que los archivos. gitignore,. vsls. JSON se pueden colocar en subcarpetas. Las reglas de ocultar o excluir se determinan mediante el archivo. vsls. JSON de la carpeta raíz que ha compartido (si está presente) y, a continuación, recorriendo en cada subcarpeta desde allí un archivo determinado para buscar los archivos. vsls. JSON que se van a procesar. El contenido de los archivos. vsls. JSON de las carpetas más abajo en el árbol de archivos y, a continuación, las reglas de suplemento (o invalidación) establecidas en niveles superiores.

### <a name="disabling-external-file-sharing"></a>Deshabilitar el uso compartido de archivos externo

De forma predeterminada, Live Share también compartirá los archivos que el host abre y que son externos a la solución o carpeta compartida. Esto permite abrir rápidamente otros archivos relacionados sin tener que volver a compartir.

Si prefiere deshabilitar esta característica:

* En **vs Code**, agregue lo siguiente a Settings. JSON:

    ```json
    "liveshare.shareExternalFiles": false
    ```

* En **Visual Studio**, establezca herramientas &gt; opciones &gt; Live share &gt; "compartir archivos externos" en false.

## <a name="read-only-mode"></a>Modo de solo lectura

A veces, cuando comparte el código como un host, no desea que los invitados realicen modificaciones. Es posible que necesite que el invitado eche un vistazo a parte del código, o que muestre el proyecto a un gran número de invitados y no desee que se realicen modificaciones innecesarias o accidentales. Live Share ofrece la posibilidad de compartir proyectos en modo de solo lectura.

Como host, al compartir, tiene la opción de habilitar el modo de solo lectura para una sesión de colaboración. Cuando un invitado se une, no podrá realizar modificaciones en el código, aunque todavía puede ver los cursores y resaltados de los demás, así como navegar por el proyecto.

Todavía puede depurar con invitados en modo de solo lectura. Los invitados no tendrán la capacidad de recorrer el proceso de depuración, pero todavía pueden agregar o quitar puntos de interrupción e inspeccionar las variables. Además, todavía puede compartir servidores y terminales (solo lectura) con invitados.

Puede obtener más información acerca de cómo iniciar una sesión de colaboración de solo lectura: [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project) a

## <a name="co-debugging"></a>Depuración conjunta

Cuando se trata de problemas de codificación difíciles o errores, tener un par de ojos adicional cuando la depuración puede ser realmente útil. Visual Studio Live Share habilita la "depuración colaborativa" o la "co-depuración" compartiendo la sesión de depuración con todos los invitados cada vez que el host inicia la depuración.

Como host, tiene un control total sobre cuándo se inicia o detiene una sesión de depuración, pero la depuración conlleva algunos riesgos si comparte con alguien en quien no confía. Live Share permite a los invitados invitar a ejecutar comandos console/REPL y, por tanto, hay **un riesgo de que un actor malintencionado ejecute un comando que no desea que se ejecute**.

Por lo tanto, **solo debe depurar con aquellos en los que confíe.**

Más información: [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging) a

## <a name="sharing-a-local-server"></a>Compartir un servidor local

Al depurar conjuntamente, puede ser muy útil obtener acceso a diferentes partes de la aplicación ofrecidas por el anfitrión para la sesión de depuración. Es posible que quiera acceder a la aplicación en un explorador, acceder a una base de datos local o visitar un punto de conexión de REST desde sus herramientas. Live Share le permite "compartir un servidor" que asigna un puerto local en el equipo del host al mismo puerto exacto en el equipo del invitado. Como invitado, puede interactuar con la aplicación exactamente como si se ejecutara localmente en el equipo (por ejemplo, el host y el invitado pueden acceder a una aplicación web que se ejecuta en http://localhost:3000).

Sin embargo, como un host, debe **ser muy selectivo con los puertos que comparte con los** invitados y compartir los puertos de la aplicación en lugar de los puertos del sistema. En el caso de los invitados, los puertos compartidos se comportarán exactamente igual que si el servidor o servicio se estuviese ejecutando en su propia máquina. Esto es muy útil, pero podría ser también arriesgado si es que se comparte el puerto incorrecto. Por esta razón, Live Share no realiza ninguna suposición sobre lo que se debe compartir o no sin un valor de configuración y el host que realiza una acción.

En Visual Studio, el **Puerto de la aplicación web** especificado en los proyectos de ASP.net se **comparte automáticamente durante la depuración solo** para facilitar el acceso de invitado a la aplicación web cuando se ejecuta. Sin embargo, puede desactivar esta automatización estableciendo herramientas > Opciones > Live Share > "compartir aplicación web al depurar" en "false" si lo prefiere.

En Visual Studio Code, Live Share intenta **detectar los puertos de aplicación adecuados** y compartirlos. Sin embargo, puede deshabilitarlo agregando lo siguiente a Settings. JSON:

        liveshare.autoShareServers: false

En cualquier caso, preste atención al compartir puertos adicionales.

Puede obtener más información sobre la configuración de la característica aquí: [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server) a

## <a name="sharing-a-terminal"></a>Compartir un terminal

El desarrollo moderno hace un uso frecuente de una amplia gama de herramientas de línea de comandos. Afortunadamente, como anfitrión, Live Share le permite, de forma opcional, "compartir un terminal" con los invitados. El terminal compartido puede ser de solo lectura o totalmente colaborativo, para que tanto usted como los invitados puedan ejecutar comandos y ver los resultados. Como host, puede permitir a otros colaboradores ver solo la salida o usar cualquier número de herramientas de línea de comandos para ejecutar pruebas, compilaciones o incluso evaluar problemas específicos del entorno.

Solo los hosts pueden iniciar terminales compartidos para impedir que los invitados inicien uno y hagan algo que no espere ni esté viendo. Al iniciar un terminal compartido como host, puede especificar si debe ser de solo lectura o de lectura y escritura. Si el terminal es de lectura/escritura, todos los participantes pueden escribir en el terminal, incluido el anfitrión, lo que permite intervenir fácilmente si un invitado hace algo que no le gusta. Sin embargo, para estar seguros, debería **darle acceso de lectura/escritura a los invitados solo cuando sabe que realmente lo necesitan**  y limitarse a los terminales de solo lectura en escenarios donde quiere que un invitado solo vea la salida de los comandos que ejecuta.

En Visual Studio, los terminales no se comparten de forma predeterminada. En VS Code, los terminales se comparten automáticamente de forma predeterminada como de **solo lectura** . Sin embargo, puede deshabilitarlo agregando lo siguiente a Settings. JSON:

```json
"liveshare.autoShareTerminals": false
```

Más información: [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![frente](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal) a

## <a name="aad-admin-consent"></a>Consentimiento de administrador de AAD

Al iniciar sesión con una **dirección de correo electrónico profesional o educativa** respaldada por Microsoft, es posible que vea un mensaje que indica **"requerir aprobación del administrador"** al iniciar sesión. Esto se debe a que Live Share requiere acceso de lectura a la información de usuario para sus características de seguridad y el inquilino de Azure AD está configurado para requerir "consentimiento del administrador" para las nuevas aplicaciones que acceden al contenido del directorio.

Es necesario que el administrador de AD lo resuelva por usted con la siguiente información:

* **Nombre de aplicación**: Visual Studio Live Share (Insider)
* **Tipo de aplicación**: aplicación Web
* **Estado de las aplicaciones**: producción
* **Permisos delegados**: User. Read
* **Dirección URL**de la aplicación: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **URL de respuesta**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Esto solo tendría que realizarse una vez para cualquier persona que use Live Share. Vea [aquí](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) y [aquí](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) para obtener más información.

## <a name="see-also"></a>Vea también

* [Cómo colaborar con Visual Studio Code](../how-to-guides/vscode.md)
* [Colaborar con Visual Studio](../how-to-guides/vs.md)
* [Requisitos de conectividad de Live Share](connectivity.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
