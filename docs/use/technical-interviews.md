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
ms.openlocfilehash: 0ac1ba213c59df2dc3b1d05d89e4186c823a250f
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80295960"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>Realizar entrevistas técnicas con Live Share

Con Live Share para las entrevistas, el entrevistador y el candidato pueden tener una sesión de entrevistas rápida y confiable, con un editor o un IDE de plena fidelidad. 


## <a name="setup-for-interviewer"></a>Configuración para el intervisor 
Para entrevistar a un candidato con Live Share primero debe elegir uno de los dos clientes de escritorio:

Instalación de [Visual Studio](../use/vs.md) que viene incorporado con la extensión de Live share

>[!TIP] 
> Asegúrese de activar los Live Share en las *herramientas > opciones > Live Share > características avanzadas >* . Esto le permitirá usar nuestra compatibilidad de llamada de audio integrada para las entrevistas.

O instale [Visual Studio Code](../.use/vscode.md) y descargue el [paquete de extensión de Live share]() desde Marketplace. El paquete de extensiones le proporcionará soporte técnico de audio para las entrevistas. 

## <a name="scheduling-an-interview"></a>Programar una entrevista 

**Live share en vs Code** le proporciona la capacidad de crear sesiones de Live share de antemano. Puede usar los pasos siguientes para crear una sesión de antemano:

1. Vaya a la `Command Palette` mediante `Ctrl+Shift+P`
1. Escriba "Live Sha..." y haga clic en el comando '_Live Share: crear vínculo de sesión reutilizable_'.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Esto creará una sesión reutilizable y se copiará un vínculo a ella en el portapapeles. Verá un mensaje emergente de notificación en la esquina inferior derecha del editor.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Envíe el vínculo.

Una vez que tenga este vínculo, solo debe compartirlo con el correo electrónico o el mecanismo de programación que prefiera. Todo lo que tienen que hacer es hacer clic en ese vínculo en el momento de la entrevista y se encontrarán en una sesión de Live Share. 
> [!TIP] 
>Un vínculo de sesión reutilizable es persistente y se mantiene durante 30 días a partir de la fecha de creación o la fecha del último uso. Al generar un vínculo de sesión reutilizable para la entrevista, asegúrese de que la entrevista se encuentra en un plazo de 30 días a partir de la fecha de creación del vínculo. Si el vínculo expira, solo tiene que crear una nueva sesión reutilizable. (Hay una manera de asegurarse de que el vínculo no expire nunca, pero esto es simplemente más fácil para las entrevistas).

**Nota:** Actualmente, Live Share en Visual Studio no tiene la capacidad de crear sesiones de antemano. En el caso de las entrevistas que realiza con Live Share en Visual Studio, puede seguir nuestra guía sobre cómo iniciar una sesión de Live Share instantánea [aquí](../quickstart/share.md)



## <a name="setup-for-candidate"></a>Configuración para candidato
Aunque un candidato siempre puede instalar Visual Studio o Visual Studio Code para unirse a la entrevista, no es necesario que lo haga. **Las sesiones de entrevistas Live Share pueden estar unidas por candidatos sin ninguna configuración previa.** Pueden hacer clic en el vínculo de la entrevista en el momento de la sesión y **unirse desde el explorador**. Obtenga más información [aquí.](../quickstart/browser-join.md)



<!--
### **What to do as an Interviewer?**

As an interviewer you will act as the host of the Live Share session. If you are not familiar with Live Share, we suggest you refer to the [share a project](../use/vscode.md) section of our how-to guide
### **What to do as the Interviewee?**

If you are expecting to do a Technical Interview using Live Share, you are in luck! We want to make sure you are familiar with the basic Live Share features so you feel comfortable during your interview.

1. Before the interview, take some time and look over the [How-to guide](../use/vscode.md) so you understand how Live Share works.

1. You may want to install Visual Studio Code beforehand so that you are not waiting for the installation to complete once you start your interview

1. If you don't have the time, no worries. All you need to have a full interview is the link to a Live Share session your interviewer sends you while scheduling the interview. Just clicking on the link will automatically take you through all the steps needed.

1. At the time of the interview, just click on the link and follow the steps it takes you through. If you are early or your interviewer is late to the interview, don't worry! You will just be in the 'lobby' waiting for your interviewer to join. No other steps are required, and once your interviewer joins the session will automatically start.

>[!NOTE]
>If you find that the session has disconnected before or after the interviewer joined, don't worry. Just exit out of that session if (it isn't already closed) and re-click on the same link!

You are now all set to go with using Live Share for your interview! 
-->