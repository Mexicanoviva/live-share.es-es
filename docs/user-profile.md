---
title: Perfil de usuario-Visual Studio Live Share | Microsoft Docs
description: Información general sobre cómo ver y quitar el perfil de usuario de Visual Studio Live Share.
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
ms.openlocfilehash: 2f9f496b47db7efe260c1f09a2906c68c07762d5
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80295943"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>Perfil de usuario

Cuando se autentica con Visual Studio Live Share, crea un perfil de usuario, que simplemente permite que los participantes con los que colaboren puedan ver quién es (por ejemplo, la dirección de correo electrónico, el Avatar). En un momento dado, puede ver la información del perfil que Live Share ha almacenado en su nombre; para ello, vaya a una de las siguientes páginas (dependiendo del proveedor de identidades que haya usado):

- [Cuenta Microsoft/Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

En esta página se le pedirá que inicie sesión (para comprobar su identidad) y, a continuación, se mostrará la salida JSON sin procesar para su perfil de usuario.

<img width="500px" src="media/user-profile.png" />

Si Visual Studio Live Share no tiene actualmente un perfil almacenado para la identidad con la que inició sesión, lo notificará también.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>Quitar el perfil

Si desea quitar su perfil de usuario, puede hacer clic en el botón `Delete your account` en la [página Perfil de usuario](#user-profile). De lo contrario, Visual Studio Live Share eliminará automáticamente el perfil 30 días desde el último inicio de sesión correcto. En este contexto, un "Inicio de sesión correcto" hace referencia a lo siguiente (en función de la herramienta que esté usando):

| IDE/editor | El perfil de usuario se eliminará 30 días después de la última hora... |
|-|-|
| Visual Studio | Inicie una nueva instancia del IDE. Con el fin de admitir el inicio de sesión único, Visual Studio Live Share actualiza la sesión de autenticación cada vez que se abre una nueva instancia de Visual Studio. |
| Visual Studio Code | Complete el flujo de trabajo de autenticación basada en explorador (por ejemplo, haga clic en el botón `Sign In` o ejecute el comando `Live Share: Sign in with browser`). Visual Studio Live Share recordará su sesión de autenticación en el cliente para evitar que tenga que iniciar sesión cada vez que comparta. Sin embargo, esa sesión expira después de 30 días y nunca se actualiza automáticamente, hasta que se vuelva a iniciar sesión explícitamente a través del explorador. |

## <a name="see-also"></a>Consulte también

- [Compatibilidad con lenguajes y plataformas](reference/platform-support.md)
- [Requisitos de conectividad de Live Share](reference/connectivity.md)
- [Características de seguridad de Live Share](reference/security.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](troubleshooting.md) o [envíe sus comentarios](support.md).
