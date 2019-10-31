---
title: 'Compatibilidad con plataformas y lenguajes: Visual Studio Live Share | Microsoft Docs'
description: Información general sobre la compatibilidad de plataformas y idiomas para el uso compartido de Visual Studio Live.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 386a8204787ed378413e1b35b7c2a80e0de678ce
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170094"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>Compatibilidad con lenguajes y plataformas

Las características de Visual Studio Live Share están diseñadas para funcionar en un panorama diverso de lenguajes y plataformas de aplicaciones. Sin embargo, dado el gran número de variaciones, algunas plataformas y lenguajes son más completos que otros. En este documento se trata el estado conocido actual de varios lenguajes y plataformas populares para las características admitidas actualmente.

¿Ve el idioma o la plataforma que necesita? ¿Desea agregar uno que no ve? [Vote aquí.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

Todos los lenguajes y plataformas tienen el mismo archivo IntelliSense (cuando se instala la extensión respectiva), así como la compatibilidad con la característica de coloración y edición conjunta. En las listas siguientes se tratan las características avanzadas actualmente sin soporte universal completo:

### <a name="languages"></a>Lenguajes

| Lenguaje | Servicios de lenguaje compartido | Depuración compartida |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *N/A* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *N/A* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *N/A* <sup>4</sup> |
| [Decision](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *N/A* <sup>4</sup> |
| CSHTML | *N/A* <sup>1</sup> | ✅ |
| CSS | *N/A* | *N/A* |
| DART | ✅ | ✅ |
| Docker | ✅ | *N/A* |
| Elixir | ✅ | ✅ |
| Elm | ✅ |  *N/A* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *N/A* <sup>4</sup> |
| Flujo | ✅ |  *N/A* <sup>4</sup> |
| Fortran | ✅ | *N/A* |
| Ir | ✅ | ✅ |
| Gradle | ✅ | *N/A* <sup>4</sup> |
| GraphQL | ✅ | *N/A* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *N/A* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript/TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *N/A* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *N/A* | *N/A* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *N/A* |
| MATLAB |  ✅ | *N/A* <sup>4</sup> |
| Objective-C | ✅ | *N/A* <sup>4</sup> |
| Nomenclatura | ✅ | *N/A* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *N/A* | ✅ |
| Plantillas de |  ✅ | ✅ |
| PureScript | ✅ | *N/A* <sup>4</sup> |
| R |  ✅ | *N/A* <sup>4</sup> |
| [Motivo/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/A* <sup>4</sup> |
| reStructuredText | ✅ | *N/A* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/A* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *N/A* |
| Scala | ✅ | *N/A* <sup>4</sup> |
| Solidity | ✅ | *N/A* <sup>4</sup> |
| SQL/T-SQL | *N/A* | *N/A* <sup>4</sup> |
| [Puntero](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *N/A* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/A* <sup>4</sup> |
| Swift | ✅ | *N/A* <sup>4</sup> |
| Terraform | ✅ | *N/A* <sup>4</sup> |
| XML | ✅ | *N/A* <sup>4</sup> |
| YAML | ✅ | *N/A* <sup>4</sup> |

<sup>1</sup> no se admite CSHTML C# en la extensión.<br />
<sup>2</sup> JavaScript incrustado en HTML se admite cuando se realiza la depuración de cliente.<br />
<sup>3</sup> depuración de JavaScript/TypeScript para un nodo o explorador.<br />
<sup>4</sup> la extensión respectiva de vs Code no admite actualmente la depuración. En cuanto lo hace, se investigará la incorporación de compatibilidad con la depuración. <br />

### <a name="platforms"></a>Plataformas

| Tipo de aplicación o plataforma | Depuración compartida | Uso compartido de aplicaciones |
|-------------------|--------------|-------------|
| Arduino | ✅ | *N/A* |
| Azure App Service | ✅ | *N/A* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure Functions (local y remoto) | ✅ | ✅ <sup>1</sup> |
| Blockchain (Ethereum) | ✅ | ✅ <sup>1</sup> |
| Consola/CLI | ✅ | ✅ <sup>4</sup> |
| Bases de datos | <sup>5</sup> | ✅ <sup>1</sup> |
| Escritorio (electrones/nativo) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| Juegos (Unity) | ✅ | <sup>9</sup> |
| Juegos (no real) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *N/A* | ✅ <sup>6</sup> |
| Móvil (Cordova) | ✅ | ✅ <sup>1, 7</sup> |
| Móvil (nativo) | ✅ | <sup>9</sup> |
| Móvil (reAct nativo) | ✅ | ✅ <sup>1, 8</sup> |
| Aplicación web/API (back-end) | ✅ | ✅ <sup>1</sup> |
| Aplicación web (front-end) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Extensiones de VS Code | | <sup>9</sup> |

<sup>1</sup> a través del [servidor local de recursos compartidos](../how-to-guides/vscode.md#share-a-server).<br />
<sup>2</sup> la depuración se produce en el explorador del host en lugar de en el invitado.<br />
<sup>3</sup> compartiendo el back-end.<br />
<sup>4</sup> se admite a través de terminales compartidos.<br />
<sup>5</sup> actualmente no se admiten procedimientos almacenados de base de datos de depuración <br />
<sup>6</sup> a través de "vista previa". Sin embargo, las imágenes no aparecen debido a un problema conocido. [Vote (👍) aquí.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> las aplicaciones de Cordova se pueden compartir a través de la plataforma de "explorador"<br />
<sup>8</sup> las aplicaciones nativas de reAct se pueden compartir a través de los servidores de exposición y [compartidos](../how-to-guides/vscode.md#share-a-server).<br />
<sup>9</sup> Live Share no admite actualmente el uso compartido de ventanas o pantallas. [Vote (👍) aquí.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Programa para la mejora

Aunque la mayoría de los lenguajes tienen cierta compatibilidad con IntelliSense de un solo archivo, hay algunas advertencias que se describen a continuación. Todos los lenguajes y plataformas admiten la edición conjunta. En el resto de la lista se incluyen características avanzadas actualmente sin soporte técnico universal completo:

### <a name="languages"></a>Lenguajes

| Lenguaje | Servicios de lenguaje de un solo archivo | Servicios de lenguaje para todo el proyecto | Depuración conjunta |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅<sup>1</sup> | | ✅ |
| ASCX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *N/A* | <sup>2</sup> |
| CSS | ✅ | *N/A* | *N/A* |
| JavaScript/TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Plantillas de | ✅ | | ✅ |
| Markdown | ✅ | *N/A* | *N/A* |
| PowerShell | ✅ | *N/A* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *N/A* | <sup>4</sup> |
| SQL/T-SQL | ✅ | *N/A* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *N/A* | ✅ |

<sup>1</sup> intervalo: CSHTML, VBHTML y aspx tienen problemas conocidos relacionados con la compatibilidad C#de/VB incrustada, dado C#que los archivos/VB de código subyacente no se resuelven debido a que no se implementa IntelliSense completo. [Vote (👍) aquí en CSHTML/VBHTML.](https://github.com/MicrosoftDocs/live-share/issues/59) [Vote (👍) aquí en ASPX.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> JavaScript incrustado en HTML se admite cuando se realiza la depuración de cliente.<br />
<sup>3</sup> depuración de JavaScript/TypeScript para un nodo o explorador.<br />
<sup>4</sup> aunque la depuración de XAML es técnicamente N/A, se admite la depuración de código subyacente.<br />
<sup>5</sup> brecha: errores del servicio de lenguaje R en el lado invitado en la combinación y después de cada nueva línea. No se admite. [Vote (👍) aquí.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>Plataformas

| Tipo de aplicación o plataforma | Depuración conjunta | Uso compartido de aplicaciones |
|-------------------|--------------|-------------|
| Aplicación web/API (back-end) | ✅ | ✅ <sup>1</sup> |
| Aplicación web (front-end) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Comprobación de | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure Dev Spaces](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Bases de datos | <sup>4</sup> | ✅ <sup>5</sup> |
| Consola/CLI | ✅ | ✅ <sup>6</sup> |
| Escritorio (WinForms) | ✅ | |
| Escritorio (WPF) | ✅ | |
| Plataforma universal de Windows | ✅ |  |
| Extensiones de VS | ✅ |  |

<sup>1</sup> a través del [servidor local de recursos compartidos](../how-to-guides/vs.md#share-a-server). ASP.NET Web Apps también puede usar el [uso compartido automático de aplicaciones web](../how-to-guides/vs.md#automatic-web-app-sharing).<br />
<sup>2</sup> la depuración se produce en el explorador del host en lugar de en el invitado.<br />
<sup>3</sup> compartiendo el back-end.<br />
<sup>4</sup> actualmente no se admiten procedimientos almacenados de base de datos de depuración <br />
<sup>5</sup> a través del [servidor local de recursos compartidos](../how-to-guides/vs.md#share-a-server). <br />
<sup>6</sup> parcialmente compatible mediante terminales compartidos.<br />
<sup>?</sup> Todavía no se ha validado.

## <a name="see-also"></a>Vea también

- [Compatibilidad con extensiones](extensions.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Todos los errores importantes, limitaciones y solicitudes de características](https://aka.ms/vsls-issues)
- [Todas las limitaciones y solicitudes de características](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
