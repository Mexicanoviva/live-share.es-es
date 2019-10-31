---
title: 'Colaboración mediante Visual Studio Code: Visual Studio Live Share | Microsoft Docs'
description: Un conjunto de procedimientos de colaboración para Visual Studio Code y Live Share.
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: 2b2a92f656fdf95b72a70b484df53718c9306657
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179978"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>Realizar entrevistas técnicas con Live Share

Antes de empezar a usar Live Share para las entrevistas técnicas, debe completar un paso entero: **descargue Visual Studio Code y el paquete de extensión de Live share de su Marketplace** siguiendo [estos pasos.](../how-to-guides/vscode.md)

Live Share proporciona la capacidad de hospedar sesiones reutilizables. Todo esto significa que puede programar una sesión de Live Share de antemano para las entrevistas técnicas y no preocuparse por la expiración del vínculo.

> [!TIP] 
>Un vínculo de sesión reutilizable es persistente y se mantiene durante 30 días a partir de la fecha de creación o la fecha del último uso. Al generar un vínculo de sesión reutilizable para la entrevista, asegúrese de que la entrevista se encuentra en un plazo de 30 días a partir de la fecha de creación del vínculo. Si el vínculo expira, solo tiene que crear una nueva sesión reutilizable. (Hay una manera de asegurarse de que el vínculo no expire nunca, pero esto es simplemente más fácil para las entrevistas).

### <a name="what-to-do-as-an-interviewer"></a>**¿Qué se debe hacer como un intervisor?**

Como un intervisor, actuará como el host de la sesión de Live Share. Si no está familiarizado con Live Share, se recomienda que consulte la sección [compartir un proyecto](../how-to-guides/vscode.md) de nuestra guía de procedimientos.

Ahora, para crear una sesión de Live Share para su entrevista técnica, deberá crear una "sesión reutilizable" especial en lugar de la sesión de colaboración normal. Esto le permitirá tener una sesión de Live Share que se puede programar de antemano y usar en cualquier momento.

Para crear una sesión reutilizable, haga lo siguiente:

1. Vaya a la `Command Palette` mediante `Ctrl+Shift+P`
1. Escriba "Live Sha..." y haga clic en el comando ' **_Live Share: crear vínculo de sesión reutilizable_** '.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Esto creará una sesión reutilizable y se copiará un vínculo a ella en el portapapeles. Verá un mensaje emergente de notificación en la esquina inferior derecha del editor.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Se ha creado la sesión reutilizable. Comparta el vínculo con su sesión y úselo cada vez para acceder a la sesión.

Una vez que tenga este vínculo, solo debe compartirlo con el correo electrónico o el mecanismo de programación que prefiera. Todo lo que tienen que hacer es hacer clic en ese vínculo en el momento de la entrevista y se encontrarán en una sesión de Live Share. 

### <a name="what-to-do-as-the-interviewee"></a>**¿Qué se debe hacer como un elemento que se va a mostrar?**

Si espera realizar una entrevista técnica con Live Share, está de suerte. Queremos asegurarnos de que está familiarizado con las características básicas de Live Share para que se sienta cómodo durante la entrevista.

1. Antes de la entrevista, tómese un tiempo y examine la [Guía de procedimientos](../how-to-guides/vscode.md) para comprender cómo funciona Live share.

1. Puede que desee instalar Visual Studio Code de antemano para que no espere a que se complete la instalación una vez iniciada la entrevista.

1. Si no tiene tiempo, no tiene preocupaciones. Todo lo que necesita para realizar una entrevista completa es el vínculo a una sesión de Live Share que le envía el entrevistador mientras programa la entrevista. Al hacer clic en el vínculo, se le guiará automáticamente a través de todos los pasos necesarios.

1. En el momento de la entrevista, solo tiene que hacer clic en el vínculo y seguir los pasos que le guían. Si está pronto o el entrevistador está retrasado, no se preocupe. Solo tendrá que estar en el ' vestíbulo ' en espera para que se una su intervisor. No se requieren otros pasos y, una vez que el intervisor se une a la sesión, se iniciará automáticamente.

>[!NOTE]
>Si observa que la sesión se ha desconectado antes o después de que se haya Unido el intervisor, no se preocupe. Simplemente salga de esa sesión si (no está ya cerrada) y vuelva a hacer clic en el mismo vínculo.

Ya está todo listo para usar Live Share para su entrevista. 
