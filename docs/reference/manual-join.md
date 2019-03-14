---
title: Combinación manual - Visual Studio Live Share | Microsoft Docs
description: Compartir información sobre cómo combinar manualmente una sesión de colaboración en Visual Studio Live.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 57d26c2c63bd5b92e62a72368f97bb8aee63313c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256311"
---
# <a name="join-a-session-manually"></a>Participar en una sesión manualmente

Además de abrir un vínculo en un explorador para participar en una sesión de colaboración, puede combinar manualmente si pega el vínculo en una herramienta que ya se está ejecutando. Esto puede ser útil si desea usar una herramienta diferente a como lo hace normalmente o si tiene problemas con la obtención de vínculos de invitación a trabajar por algún motivo.

Las instrucciones exactas varían entre [Visual Studio](#join-from-visual-studio) y [Visual Studio Code](#join-from-visual-studio-code), así que elija la herramienta que se va a utilizar para obtener más información.

## <a name="join-from-visual-studio-code"></a>Combinar desde Visual Studio Code

### <a name="1-sign-in"></a>1. Inicio de sesión

>**Nota:** Si desea participar en una sesión de colaboración como invitado de solo lectura, puede omitir la firma. Se tiene acceso para ver y navegar por el código que se comparte pero no podrá realizar modificaciones.

![Notificación del sistema que pide que inicie sesión con un explorador web](../media/vscode-sign-in-toast.png)

Para colaborar, necesitará inicio de sesión en Visual Studio Live Share para que todo el mundo sepa quién es usted. **Haga clic en** en el estado de "Live Share" elemento o presione la barra **Ctrl + Mayús + P / Cmd + Mayús + P** y seleccione el "recurso compartido en vivo: Comando iniciar sesión con el explorador".

![En el botón de la firma de código de VS](../media/vscode-sign-in-button.png)

Se iniciará el explorador mientras aparecerá una notificación que le pide que inicie sesión en el inicio. Completar el inicio de sesión en proceso en el explorador, a continuación, simplemente cierre el explorador cuando haya terminado.

Si está experimentando problemas con el código de VS no recoger un inicio de sesión correcto, haga clic en el vínculo "Problemas" en la pantalla de éxito en el explorador y siga las instrucciones. Desproteger [solución de problemas](../troubleshooting.md#sign-in) para obtener más sugerencias.

### <a name="2-use-the-join-command"></a>2. Use el comando de combinación

Abra el viewlet Live Share en la barra de actividad de VS Code y seleccione la "combinación sesión de colaboración..." icono o entrada.

![Icono viewlet de combinación](../media/vscode-join-viewlet.png)

>**Nota:** Si se va a unir como invitado de solo lectura, a continuación, se le pedirá que escriba un nombre para mostrar para ayudar a los participantes a identificar al usuario en la sesión.

### <a name="3-paste-the-invite-link"></a>3. Pegue el vínculo de invitación

Pegue la dirección URL de invitación se enviaron y presione 'ENTRAR' para confirmar.

Ya está. Debe estar conectado a la sesión de colaboración momentáneamente.

## <a name="join-from-visual-studio"></a>Combinar desde Visual Studio

### <a name="1-sign-in"></a>1. Inicio de sesión

Una vez instalado, inicie Visual Studio e inicie sesión si aún no lo hizo. Si necesita usar un inicio de sesión en diferentes para Visual Studio que su [cuenta de personalización](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), vaya a **herramientas &gt; opciones &gt; Live Share &gt; cuenta de usuario**.

![Frente a iniciar sesión](../media/vs-sign-in-button.png)

¿Sigue teniendo problemas? Consulte [solución de problemas](../troubleshooting.md#sign-in).

### <a name="2-use-the-join-command"></a>2. Use el comando de combinación

Simplemente vaya a **archivo > unirse a la sesión de colaboración**.

![Menú de la combinación de VS](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. Pegue el vínculo de invitación

Pegue la dirección URL de invitación se enviaron y presione 'ENTRAR' para confirmar.

Ya está. Debe estar conectado a la sesión de colaboración momentáneamente.

## <a name="see-also"></a>Vea también

Guías de inicio rápido

- [Inicio rápido: Comparta su primer proyecto](../quickstart/share.md)
- [Inicio rápido: Únase a la primera sesión](../quickstart/join.md)

Temas procedimentales

- [Cómo: Colaborar mediante Visual Studio Code](../use/vscode.md)
- [Cómo: Colaborar mediante Visual Studio](../use/vs.md)
- [Cómo: Proporcionar comentarios](../support.md)

Referencia

- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Detalles de la instalación de Linux](linux.md)
- [Compatibilidad con lenguajes y plataformas](platform-support.md)
- [Compatibilidad con extensiones](extensions.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
