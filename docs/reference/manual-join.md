---
title: 'Unión manual: Visual Studio Live Share | Microsoft Docs'
description: Información sobre cómo combinar una sesión de colaboración manualmente en el recurso compartido de Visual Studio Live.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 0d46cb53a28bfac1c088371ff5eecdb6af0c8420
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019791"
---
# <a name="join-a-session-manually"></a>Unirse a una sesión manualmente

Además de abrir un vínculo en un explorador para unirse a una sesión de colaboración, puede unirse manualmente pegando el vínculo en una herramienta que ya está en ejecución. Esto puede ser útil si desea usar una herramienta distinta de la que suele hacer o si tiene problemas para conseguir que los vínculos de invitación funcionen por algún motivo.

Las instrucciones exactas varían entre [Visual Studio](#join-from-visual-studio) y [Visual Studio Code](#join-from-visual-studio-code), por lo que debe elegir la herramienta que desea usar para obtener más información.

## <a name="join-from-visual-studio-code"></a>Unirse desde Visual Studio Code

### <a name="1-sign-in"></a>1. iniciar sesión

>**Nota:** Si desea unirse a una sesión de colaboración como guesasdsat de solo lectura, puede omitir el registro. Tendrá acceso para ver y navegar por el código que se comparte pero no puede realizar modificaciones.

![Notificación del sistema en la que solicita el inicio de sesión con un explorador web](../media/vscode-sign-in-toast.png)

Para poder colaborar, deberá iniciar sesión en Visual Studio Live Share de manera que todos sepan quién es usted. **Haga clic** en el elemento de barra de estado "Live share" o presione **Ctrl + Mayús + P/Cmd + Mayús + P** y seleccione el comando "Live Share: iniciar sesión con el explorador".

![Botón de inicio de sesión de VS Code](../media/vscode-sign-in-button.png)

El explorador se iniciará mientras se muestre una notificación que le pedirá que inicie sesión. Complete el proceso de inicio de sesión en el explorador, y después ciérrelo cuando haya terminado.

Si tiene problemas con VS Code no selecciona un inicio de sesión correcto, haga clic en el vínculo "problemas" en la pantalla de éxito del explorador y siga las instrucciones. Consulte [solución de problemas](../troubleshooting.md#sign-in) para obtener más sugerencias.

### <a name="2-use-the-join-command"></a>2. usar el comando join

Abra el Live Share Viewlet en la barra de actividades VS Code y seleccione la "unirse a la sesión de colaboración..." icono o entrada.

![Icono para participar del viewlet](../media/vscode-join-viewlet.png)

>**Nota:** Si se va a unir como invitado de solo lectura, se le pedirá que escriba un nombre para mostrar para ayudar a los participantes a identificarle en la sesión.

### <a name="3-paste-the-invite-link"></a>3. pegar el vínculo invitar

Pegue la dirección URL de invitación enviada y presione "entrar" para confirmarla.

Ya está. Debería estar conectado momentáneamente a la sesión de colaboración.

## <a name="join-from-visual-studio"></a>Unirse desde Visual Studio

### <a name="1-sign-in"></a>1. iniciar sesión

Una vez instalado, inicie Visual Studio e inicie sesión si aún no lo ha hecho. Si necesita usar un inicio de sesión diferente para Visual Studio que su cuenta de [Personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), vaya a **herramientas &gt; opciones &gt; Live share &gt; cuenta de usuario**.

![Inicio de sesión en VS](../media/vs-sign-in-button.png)

¿Sigue teniendo problemas? Consulte [solución de problemas](../troubleshooting.md#sign-in).

### <a name="2-use-the-join-command"></a>2. usar el comando join

Simplemente vaya a **archivo > unirse**a la sesión de colaboración.

![Menú para participar de VS](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. pegar el vínculo invitar

Pegue la dirección URL de invitación enviada y presione "entrar" para confirmarla.

Ya está. Debería estar conectado momentáneamente a la sesión de colaboración.

## <a name="see-also"></a>Vea también

Tutoriales rápidos

- [Inicio rápido: compartir el primer proyecto](../quickstart/share.md)
- [Inicio rápido: Únase a su primera sesión](../quickstart/join.md)

Temas procedimentales

- [Cómo colaborar con Visual Studio Code](../use/vscode.md)
- [Colaborar con Visual Studio](../use/vs.md)
- [Cómo: proporcionar comentarios](../support.md)

Referencia

- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Detalles de la instalación de Linux](linux.md)
- [Compatibilidad con lenguajes y plataformas](platform-support.md)
- [Compatibilidad con extensiones](extensions.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
