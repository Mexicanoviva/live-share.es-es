---
title: Visual Studio Live Share de Insider | Microsoft Docs
description: Descripción del canal de "Insiders" en Visual Studio Live Share.
ms.custom: ''
ms.date: 04/02/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 308f3746bfcdd1f2a428106c1d3e579f49df0cf3
ms.sourcegitcommit: 50069912a317f8685976013e80738bbaa403a3fe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72172001"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Participantes

El equipo de Visual Studio Live Share es todo sobre la iteración rápida, la prueba de nuevas ideas y la escucha de nuestros clientes. Los Insiders ofrecen a nuestros usuarios la oportunidad de probar todas las características nuevas primero y ofrecer sus comentarios valiosos. Aprenda a [ser un Insider](#BecomeanInsider) más abajo y ayúdenos a dar forma al futuro de la colaboración del desarrollador. 

## <a name="new-to-insiders"></a>✨ Nuevo a Insiders ✨


### <a name="reusable-sessions-vs-code"></a>**Sesiones reutilizables (VS Code)**

Live Share ahora pueden hospedar sesiones reutilizables. Las sesiones reutilizables proporcionan la capacidad de reutilizar una sesión de Live Share para varios escenarios. Esto significa que puede programar una sesión de Live Share de antemano para las entrevistas técnicas, la sesión semanal de programación de Mob, usar la misma sesión mientras se mentora a un amigo, y mucho más.

Para crear una sesión reutilizable, haga lo siguiente:
1. Vaya a la `Command Palette` mediante `Ctrl+Shift+P`
1. Escriba "Live Sha..." y haga clic en el comando ' **_Live Share: crear vínculo de sesión reutilizable_** '.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Esto creará una sesión reutilizable y se copiará un vínculo a ella en el portapapeles. Verá un mensaje emergente de notificación en la esquina inferior derecha del editor.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Se ha creado la sesión reutilizable. Comparta el vínculo con su sesión y úselo cada vez para acceder a la sesión.

> [!TIP] 
>Un vínculo de sesión reutilizable es persistente y se mantiene durante 30 días a partir de la fecha de creación o la fecha del último uso. Esto significa que si sigue usando su sesión al menos una vez cada 30 días, no tendrá que preocuparse de que expire. Solo tiene que guardar el vínculo en un lugar seguro donde pueda acceder a él fácilmente.
 


## Convertirse en Insider <a name="BecomeanInsider"></a>

De forma predeterminada, después de instalar la extensión de Visual Studio Live Share, se usa el conjunto de características `Stable`, que incluye todas las capacidades listas para producción (por ejemplo, edición conjunta, depuración compartida, terminales). Sin embargo, si desea obtener un acceso anticipado a la característica en la que estamos trabajando, puede participar en el conjunto de características de `Insiders` cambiando la siguiente configuración en el IDE:

* Visual Studio

    ![conjunto de características-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![Feature-Set-vscode](../media/feature-set-vscode.png)

En las secciones siguientes se describe el conjunto de funcionalidades que se encuentran actualmente en el conjunto de características `Insiders` y, por tanto, están listas para su evaluación una vez que se cambia la configuración mencionada anteriormente:



## <a name="see-also"></a>Vea también

- [Compatibilidad con lenguajes y plataformas](platform-support.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
