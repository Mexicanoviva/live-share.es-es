---
title: 'Perfil de usuario: Visual Studio Live Share | Microsoft Docs'
description: Información general sobre cómo ver y quitar su perfil de usuario de Visual Studio Live Share.
ms.custom: ''
ms.date: 05/222/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 1d3b4977745e33ba0ee1b599ea4257c4a49d970d
ms.sourcegitcommit: bfa1020882095fcc7d31cd71cf1f2e601e3bea06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2019
ms.locfileid: "66224701"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>Perfil de usuario

Cuando se autentica con Visual Studio Live Share, crea automáticamente un perfil de usuario, lo que permite a los participantes que colaboran para ver quién es usted (por ejemplo, su dirección de correo electrónico, el avatar). En un momento dado, puede ver la información de perfil que ha almacenado Live Share en su nombre, navegando a una de las páginas siguientes (según el proveedor de identidades usó):

- [Cuenta de Microsoft / Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

La página se pedirá que inicie sesión en verificar tu identidad y, a continuación, se mostrará la salida JSON sin procesar para su perfil de usuario.

<img width="500px" src="media/user-profile.png" />

Si Visual Studio Live Share actualmente no tiene un perfil almacenado para la identidad que inició sesión, a continuación, le permitirá saber que también.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>Quitar su perfil

Si desea quitar el perfil de usuario, haga clic en el vínculo titulado `Click here to get your data removed from our systems` en el [página de perfil de usuario](#user-profile). Como alternativa, puede visitar una de las siguientes páginas directamente (según el proveedor de identidades usó):

- [Cuenta de Microsoft / Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/deleteme)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/deleteme)

En caso contrario, Visual Studio Live Share eliminará automáticamente el perfil de 30 días después de su último inicio de sesión correcto. En este contexto, un "inicio de sesión correcto" se refiere a la siguiente (dependiendo de la herramienta que esté utilizando):

| Editor del IDE | 30 días después de la última vez que se eliminará su perfil de usuario... |
|-|-|
| Programa para la mejora | Inicie una nueva instancia del IDE. Para admitir el inicio de sesión único, Visual Studio Live Share actualiza su sesión de autenticación cada vez que abre una nueva instancia de Visual Studio. |
| Visual Studio Code | Completar el flujo de trabajo de autenticación basada en explorador (por ejemplo, al hacer clic en el `Sign In` botón o ejecutando el `Live Share: Sign in with browser` comando). Compartir Live de Visual Studio recordará la sesión de autenticación en el cliente, para evitar la necesidad de iniciar sesión cada vez que se comparte. Sin embargo, esa sesión expira después de 30 días y se actualiza automáticamente nunca, hasta explícita iniciar sesión a través del explorador nuevo. |

## <a name="see-also"></a>Vea también

- [Compatibilidad con lenguajes y plataformas](reference/platform-support.md)
- [Requisitos de conectividad de Live Share](reference/connectivity.md)
- [Características de seguridad de Live Share](reference/security.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](troubleshooting.md) o [envíe sus comentarios](support.md).
