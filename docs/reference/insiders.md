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
ms.openlocfilehash: 04bfb314ebae711566a8bab8b0ada8f2fbd2e940
ms.sourcegitcommit: 6b46e300d76eda661ab34c67a3b909d5c162cd9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062282"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Participantes

El equipo de Visual Studio Live Share es todo sobre la iteración rápida, la prueba de nuevas ideas y la escucha de nuestros clientes. Los Insiders ofrecen a nuestros usuarios la oportunidad de probar todas las características nuevas primero y ofrecer sus comentarios valiosos. Aprenda a [ser un](#BecomeanInsider) Insider más abajo y ayúdenos a dar forma al futuro de la colaboración del desarrollador. 

## <a name="new-to-insiders"></a>✨ Nuevo a Insiders ✨


### <a name="reusable-sessions-vs-code"></a>**Sesiones reutilizables (VS Code)**

Live Share ahora pueden hospedar sesiones reutilizables. Las sesiones reutilizables proporcionan la capacidad de reutilizar una sesión de Live Share para varios escenarios. Esto significa que puede programar una sesión de Live Share de antemano para las entrevistas técnicas, la sesión semanal de programación de Mob, usar la misma sesión mientras se mentora a un amigo, y mucho más.

Para crear una sesión reutilizable, haga lo siguiente:
1. Vaya a `Command Palette` mediante`Ctrl+Shift+P`
1. Escriba "Live Sha..." y haga clic en**el_Live Share: Crear el vínculo_** de sesión reutilizable '.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Esto creará una sesión reutilizable y se copiará un vínculo a ella en el portapapeles. Verá un mensaje emergente de notificación en la esquina inferior derecha del editor.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Se ha creado la sesión reutilizable. Comparta el vínculo con su sesión y úselo cada vez para acceder a la sesión.

> [!TIP] 
>Un vínculo de sesión reutilizable es persistente y se mantiene durante 30 días a partir de la fecha de creación o la fecha del último uso. Esto significa que si sigue usando su sesión al menos una vez cada 30 días, no tendrá que preocuparse de que expire. Solo tiene que guardar el vínculo en un lugar seguro donde pueda acceder a él fácilmente.
 

### <a name="direct-user-invitations"></a>**Invitaciones directas de usuarios**

Actualmente, tanto Visual Studio como Visual Studio Code proporcionan un `Contacts` panel, lo que permite dos funciones clave:

1. Mostrar una lista de `Suggested Contacts`, que son desarrolladores que han contribuido al proyecto actualmente abierto en los últimos 30 días. En la práctica, se trata de las personas con las que es probable que desee colaborar y, por lo tanto, se recomiendan para facilitar la introducción.

2. Proporcionar la lista de `Recent Contacts`, que son desarrolladores con los que ha colaborado previamente mediante Live share. En la práctica, la mayoría de los desarrolladores suelen colaborar con las mismas personas y, por lo tanto, la lista reciente permite un medio más repetible de trabajar con su equipo o aula, etc.

Sin embargo, `Contacts` la lista solo permite invitar a los contactos recientes o sugeridos por correo electrónico, lo que hemos aprendido no es tan eficaz como podría ser. Si instala la actualización más reciente de Live share y habilita `Insiders` (como se describió anteriormente), ahora podrá invitar a **los desarrolladores a una sesión de colaboración directamente desde el IDE**. Tenga en cuenta que si está usando Visual Studio Code, deberá instalar la [compilación](https://code.visualstudio.com/insiders/) de Insiders para que esta característica funcione.

![Invitatiosn directo](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Un host de Live Share (izquierda) que invita directamente a un elemento del mismo nivel (derecho) a una sesión</em>

Una vez que los desarrolladores inician sesión con Live Share, su estado de disponibilidad se publicará en sus equipos del mismo nivel. Como resultado, puede ver que alguien de su equipo está en línea y, a continuación, empezar a colaborar con ellos inmediatamente. Obtendrán una notificación del sistema que les ofrece la opción de unirse a la sesión o no. Esto elimina la necesidad de intercambiar las direcciones URL de sesión por completo.

Después de 5 minutos de inactividad, el estado cambiará automáticamente `Away`a, y cuando se encuentre en una sesión de Live Share, el estado cambiará `Do not disturb` automáticamente a (que notificaciones del sistema de invitación a suprresses). Una vez que vuelva a estar activo y/o deje una sesión Live Share, el estado cambiará automáticamente `Available`a. Con este comportamiento, no es necesario administrar realmente el estado de Live Share. Simplemente está disponible para habilitar invitaciones directas y comunicarse con sus compañeros, tanto si está disponible para la colaboración como si no. Sin embargo, siempre puede establecer manualmente el estado si lo prefiere.

Si quiere dejar de participar en esta característica, simplemente puede deshabilitar la `Presence` configuración en la Live share configuración de Visual Studio y Visual Studio Code. Una vez deshabilitado, podrá ver el estado de la otra e invitarla, pero su estado no se publicará y otros no podrán invitarle directamente.

 

## Convertirse en Insider <a name="BecomeanInsider"></a>

De forma predeterminada, después de instalar la extensión de Visual Studio Live Share, se `Stable` usa el conjunto de características, que incluye todas las funcionalidades listas para producción (por ejemplo, edición conjunta, depuración compartida, terminales). Sin embargo, si desea obtener un acceso anticipado a la característica en la que estamos trabajando, puede participar en el `Insiders` conjunto de características cambiando la siguiente configuración en el IDE:

* Visual Studio

    ![conjunto de características-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![Feature-Set-vscode](../media/feature-set-vscode.png)

En las secciones siguientes se describe el conjunto de funcionalidades que se encuentran `Insiders` actualmente en el conjunto de características y, por lo tanto, están listas para su evaluación una vez que se cambia la configuración mencionada anteriormente:



## <a name="see-also"></a>Vea también

- [Compatibilidad con lenguajes y plataformas](platform-support.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
