---
title: Insider - Visual Studio Live Share | Microsoft Docs
description: Una descripción del canal dentro de Visual Studio Live Share 'Insiders'.
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
ms.openlocfilehash: a79effc25c09851301bb2231511a8a9d8a9f549b
ms.sourcegitcommit: 6e84bf17eedd616417f474551344c2161700c4d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67192723"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Participantes

El equipo de Visual Studio Live Share intenta iterar rápidamente en orden a los comentarios de usuario de dirección y, como parte de eso, se ofrecen dos características independientes "canales" que le permiten decidir rápidamente cómo recibirá nuevas características. De forma predeterminada, después de instalar la extensión de Visual Studio Live Share, está usando el `Stable` conjunto, que incluye todas las funcionalidades de entornos de producción (p. ej. conjuntamente edición compartido depuración terminales) de características. Sin embargo, si desea obtener acceso anticipado a la característica que estamos trabajando, puede participar en el `Insiders` cambiando la configuración siguiente en el IDE de conjunto de características:

* Programa para la mejora

    ![característica-set-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![feature-set-vscode](../media/feature-set-vscode.png)

Las secciones siguientes describen el conjunto de funcionalidades que están actualmente en el `Insiders` conjunto de características y, por lo tanto, está preparado para evaluar una vez que cambie la configuración mencionada anteriormente:

## <a name="direct-user-invitations"></a>Invitaciones de usuarios directo

Actualmente, Visual Studio y Visual Studio Code proporcionan un `Contacts` panel, lo que permite dos funciones principales:

1. Muestra una lista de `Suggested Contacts`, que son los desarrolladores que han contribuido a su proyecto que está abierto en los últimos 30 días. En la práctica, son las personas que es probable que quiera colaborar con y, por lo tanto, se recomienda para que resulte más fácil empezar a trabajar.

2. Proporcionar una lista de `Recent Contacts`, que son los desarrolladores que ha colaborado anteriormente con el uso de Live Share. En la práctica, la mayoría de los desarrolladores con frecuencia colaboran con las mismas personas y, por lo tanto, la lista de recientes permite un medio más repetible para trabajar con su equipo, aula/etcetera.

Sin embargo, el `Contacts` lista actualmente sólo le permite invitar a contactos recientes o sugeridos por correo electrónico, lo que hemos aprendido que no es tan eficaz como podría ser. Si instala la actualización más reciente de Live Share y habilitar `Insiders` (como se ha descrito anteriormente), ahora podrá **invitar a los desarrolladores a una sesión de colaboración directamente desde el IDE**! Tenga en cuenta que si usa Visual Studio Code, deberá instalar el [Insider](https://code.visualstudio.com/insiders/) en orden para esta característica funcione.

![Invitatiosn directo](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Un host de Live Share (izquierdo) directamente invitar a un elemento del mismo nivel (derecha) en una sesión</em>

Una vez que inicie sesión a los desarrolladores con Live Share, se publicará su estado de disponibilidad a sus colegas. Como resultado, puede ver que alguien del equipo está conectado y, a continuación, inmediatamente empezar a colaborar con ellos. Obtendrá una notificación que les da la opción de unirse a la sesión o no. Esto elimina la necesidad de intercambiar direcciones URL de la sesión completamente.

Después de 5 minutos de inactividad, el estado cambia automáticamente a `Away`, y cuando esté dentro de una sesión de Live Share, su estado cambiará automáticamente a `Do not disturb` (qué notificaciones suprresses invitación del sistema). Una vez volverán a estar activo o salir de una sesión de Live Share, su estado cambiará automáticamente a `Available`. Con este comportamiento, no es necesario administrar el estado de Live Share. Es simplemente permitir invitaciones directas y comunicarse con sus compañeros, si está disponible para la colaboración o no. Sin embargo, puede establecer el estado siempre manualmente si lo prefiere.

Si desea participar en esta característica, simplemente puede deshabilitar el `Presence` configuración dentro de la configuración de Live Share en Visual Studio y Visual Studio Code. Una vez deshabilitado, todavía podrá ver el estado de los demás e invitar a ellos, pero no publicará su estado y otros no directamente invitamos.

## <a name="see-also"></a>Vea también

- [Compatibilidad con lenguajes y plataformas](platform-support.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
