---
title: Unirse desde el explorador-Visual Studio Live Share | Microsoft Docs
description: Introducción a la Unión desde el explorador de mismos
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 741292a3df8b86a8f7a9484875b352ebe6e8ec10
ms.sourcegitcommit: 382f069abbd81ed258d497a974b30379be36b4f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "79510640"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [Versión preliminar] ✨ unirse a una sesión de Live Share desde el explorador

Todas las sesiones de colaboración Live Share ahora tienen la capacidad de unirse al explorador. Esto significa que un invitado a la sesión ya no necesita instalar VS Code o Visual Studio para unirse a la sesión. Esto es especialmente útil para todas esas instancias si desea que alguien llegue a su sesión rápidamente, o para estudiantes que no suelen tener instalados los clientes de escritorio.

> [!TIP]
> Consulte nuestra sección de preguntas más frecuentes para obtener más información sobre cómo unirse desde el explorador.

# <a name="how-to-join-a-live-share-session-from-the-browser"></a>Cómo unirse a una sesión de Live Share desde el explorador 

### <a name="1-host-starts-session"></a>1. host: inicia la sesión 
Para empezar, el host debe ir a Visual Studio o VS Code para iniciar una sesión de colaboración. Cuando el host comparte una carpeta o un proyecto.

![Animación de inicio de sesión](https://user-images.githubusercontent.com/51928518/76938928-b814e300-68b4-11ea-923e-cefabd4688c6.gif)

### <a name="2-guest-uses-shared-link-to-join-from-browser"></a>2. invitado: usa el vínculo compartido para unirse desde el explorador 
Live Share generará un vínculo de Unión que se puede compartir con el invitado. Ahora, el invitado puede usar este vínculo para navegar a una página web, que ahora le proporciona una opción para continuar con el explorador.

![Animación de unirse a una sesión](https://user-images.githubusercontent.com/51928518/76941137-b8af7880-68b8-11ea-8228-41fdf4afd3ef.gif)

### <a name="3-guest-enjoys-full-fidelity-collaboration-experience-from-browser"></a>3. invitado: disfruta de una experiencia de colaboración de plena fidelidad desde el explorador 
Una vez que el invitado se ha unido a la sesión, puede llevar a cabo tal como lo haría si colaborara desde los clientes de escritorio.

![Animación de fidelidad completa](https://user-images.githubusercontent.com/51928518/76942009-40e24d80-68ba-11ea-885c-6eb1069ed550.gif)
# <a name="frequently-asked-questions"></a>Preguntas más frecuentes 

##### <a name="1-is-there-an-environment-running-in-the-background-that-is-hosting-my-session-in-the-browser"></a>1. ¿hay un entorno que se ejecute en segundo plano, que hospeda la sesión en el explorador?
Al unirse a una sesión de Live Share desde el explorador, no hay ningún nuevo entorno activo. Es un servicio sin servidor. 
##### <a name="2-do-i-have-to-pay-for-the-service-of-joining-from-the-browser"></a>2. ¿tengo que pagar por el servicio de unirse desde el explorador?
La combinación del explorador es gratuita, de forma muy parecida a la de Live Share.

##### <a name="3-how-is-this-different-from-visual-studio-online"></a>3. ¿Cómo es diferente en Visual Studio online?
Al unirse desde el explorador, solo tiene acceso al cliente de VS Code desde el explorador durante la sesión. Una vez finalizada la sesión, se cerrarán todos los archivos y carpetas junto con las capacidades del editor. Para usar un editor en el explorador, respaldado con su propio entorno para editar sus propios archivos, debe usar [Visual Studio online.](aka.ms/vso)

##### <a name="4-does-this-work-for-all-browsers"></a>4. ¿esto funciona para todos los exploradores?
Sí. Esto funciona en todos los exploradores. 
##### <a name="5-is-there-a-vs-client-that-i-can-use-in-the-browser"></a>5. ¿hay un cliente de VS que se puede usar en el explorador?
Todavía no tenemos esto disponible. 

# <a name="feedback-and-issues"></a>Comentarios y problemas 
Se trata de una característica de vista previa y esperamos obtener comentarios de los usuarios para mejorar la experiencia. Rellene aquí cualquier comentario o problema que vea en nuestro repositorio de GitHub [.](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)