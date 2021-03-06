---
title: Visual Studio Live Share de presencia | Microsoft Docs
description: Información sobre el servicio de presencia para los contactos de Visual Studio Live Share.
ms.custom: ''
ms.date: 10/08/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: b95e5f837d044b2b069f73478da40461268bdf3d
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170001"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="contacts-in-live-share"></a>Contactos en Live Share 

Por lo tanto, ha estado usando Live Share y tenga en cuenta que el envío de vínculos a través de una aplicación externa (como chat o correo electrónico) puede llegar a ser muy rápido. Sabemos que, si queremos fomentar la colaboración, debe ser la cantidad mínima de fricción posible para que le guste. Este es el motivo por el que Live Share ahora tiene **contactos** con el **Estado** .

>Los contactos se habilitarán automáticamente para todas las versiones de **Live share v 1.0.950** .

Los contactos aparecerán en la ventana de Live Share como un panel independiente, tal como se muestra en la imagen siguiente: 

![Contactos](../media/vscode-contacts-intro.png)

<em>Mostrar el panel de contactos en la ventana de Live Share</em>
## <a name="who-shows-up-in-my-contacts"></a>¿Quién aparece en mis contactos?

El panel contactos muestra dos tipos de contactos que admiten los flujos de trabajo naturales de los desarrolladores mientras trabajan.
### <a name="1-recent-contacts"></a>1. contactos recientes  
 Se trata de desarrolladores con los que ha colaborado anteriormente mediante Live Share. En la práctica, la mayoría de los desarrolladores suelen colaborar con las mismas personas y, por lo tanto, la lista reciente permite un medio más repetible de trabajar con su equipo o aula, etc.
### <a name="2-suggested-contacts"></a>2. contactos sugeridos
Se trata de desarrolladores que han contribuido al proyecto actualmente abierto en los últimos 30 días. En la práctica, se trata de las personas con las que es probable que desee colaborar y, por lo tanto, se recomiendan para facilitar la introducción.

## <a name="direct-user-invitations"></a>Invitaciones directas de usuarios 
Todos los contactos pueden ser invitados directamente a una sesión de Live Share desde el editor. Obtendrán una notificación del sistema que les ofrece la opción de unirse a la sesión o no. Esto elimina la necesidad de intercambiar las direcciones URL de sesión por completo.
![DirectInvitationVSCode](https://user-images.githubusercontent.com/51928518/66443914-e59c5d00-e9f5-11e9-957a-b1a92949d660.gif)
<em>un host de Live Share (izquierda) que invita directamente a un elemento del mismo nivel (derecho) a una sesión</em>

## <a name="how-does-status-for-contacts-work"></a>¿Cómo funciona el estado de los contactos?
Una vez que los desarrolladores inician sesión con Live Share, **su estado de disponibilidad se publicará en sus equipos del mismo nivel.** Como resultado, puede ver que alguien de su equipo está en línea y, a continuación, empezar a colaborar con ellos inmediatamente, mediante una invitación directa como se ha mencionado anteriormente.
Su estado puede establecerse directamente desde el editor para que pueda indicar la disponibilidad para su equipo, sin necesidad de cambiar el contexto. Actualmente, Live Share contactos tienen 4 Estados:

**1. disponible:** el estado predeterminado será `Available` si tiene la extensión Live share y utiliza activamente el editor, mientras no está en una sesión.

**2. no molestar:** su estado se establece en `Do not disturb` si actualmente está en una sesión de Live share activa y se suprimen todas las notificaciones de invitación.

**3. fuera:** después de 5 minutos de inactividad, el estado cambiará automáticamente a `Away`.

**4. sin conexión:** estará sin conexión una vez que esté fuera de un período de tiempo prolongado, o si decide no participar en el [Estado de uso compartido](##ManagingPresence)


## Administrar contactos y el estado<a name="ManagingPresence"> </a> de uso compartido

Si desea no participar en esta característica, puede hacerlo de dos maneras.
1. Puede deshabilitar la configuración de estado si elige que se `offline`. Una vez deshabilitado, podrá ver el estado de la otra e invitarla, pero su estado no se publicará y otros no podrán invitarle directamente.
Puede dejar sin conexión haciendo clic en el círculo de estado que abrirá el siguiente menú desplegable:

![dropdownstatus](../media/vscode-presence-opt-out.png)
<em>que muestra la lista desplegable de Estados de presencia</em>

2. Puede abrir `user settings` y ir a *extensiones > Visual Studio Live Share > Live Share: presencia* y deshabilitar el servicio de presencia. Una vez deshabilitado, podrá ver el estado de la otra e invitarla, pero su estado no se publicará y otros no podrán invitarle directamente.

![presencesettings](../media/vscode-presence-setting.png)

## <a name="faqs"></a>Preguntas más frecuentes 

###### <a name="1-will-i-be-automatically-opting-into-sharing-status-when-i-use-live-share-v10950-and-above"></a>1. ¿voy a participar automáticamente en el estado de uso compartido cuando utilizo Live Share v 1.0.950 y versiones posteriores?

La primera vez que vea contactos se le notificará con una notificación del sistema y una opción para rechazar su estado. Después, el estado se compartirá automáticamente con los contactos, a menos que decida no participar como se mostró anteriormente.

###### <a name="2-can-i-add-my-own-contacts"></a>2. ¿puedo agregar mis propios contactos?

Actualmente, nuestro servicio de contactos detecta automáticamente a los colaboradores con los que suele compartir código o que trabajan en paralelo, y no le ofrece la opción de agregar sus propios contactos. 


>¿Cree que la posibilidad de agregar contactos manualmente será útil? Ayúdenos a priorizar esto abriendo una solicitud de característica de GitHub [aquí.](https://github.com/MicrosoftDocs/live-share/issues/new?template=feature_request.md)
 

 