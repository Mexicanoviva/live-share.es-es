---
title: Compatibilidad de plataforma y lenguaje - Visual Studio Live Share | Microsoft Docs
description: Información general de compatibilidad de plataforma y lenguaje para Visual Studio Live share.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5c8429779bcfe39842ba298c3b6371daa1cf7fe4
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256312"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>Compatibilidad de lenguaje y plataforma

Características del Visual Studio Live Share están diseñadas para funcionar a través de una amplia variedad de lenguajes y plataformas de aplicaciones. Sin embargo, dada la enorme cantidad de variaciones, algunas plataformas y lenguajes son más completos que otros. Este documento describe el estado de un número de lenguajes y plataformas para las características admitidas actualmente conocido actual.

¿Vea un lenguaje o plataforma que necesita? ¿Desea agregar uno que no ve? [Votar aquí.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

Todos los lenguajes y plataformas tienen el mismo intellisense de archivo (cuando se instala la extensión correspondiente), así como la coloración y compatibilidad con la edición conjunta. Las listas de abajo abarca avanzada características actualmente sin soporte técnico completo, universal:

### <a name="languages"></a>Lenguajes

| Lenguaje | Servicios de lenguaje compartido | Depuración de compartidos |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *N/A* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *N/A* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *N/A* <sup>4</sup> |
| [Crystal](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *N/A* <sup>4</sup> |
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
| JavaScript / TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *N/A* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *N/A* | *N/A* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *N/A* |
| MATLAB |  ✅ | *N/A* <sup>4</sup> |
| Objective-C | ✅ | *N/A* <sup>4</sup> |
| Pascal | ✅ | *N/A* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *N/A* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *N/A* <sup>4</sup> |
| R |  ✅ | *N/A* <sup>4</sup> |
| [Motivo/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/A* <sup>4</sup> |
| reStructuredText | ✅ | *N/A* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/A* <sup>4</sup> |
| [SASS](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *N/A* |
| Scala | ✅ | *N/A* <sup>4</sup> |
| Solidez | ✅ | *N/A* <sup>4</sup> |
| SQL / T-SQL | *N/A* | *N/A* <sup>4</sup> |
| [Lápiz óptico](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *N/A* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/A* <sup>4</sup> |
| Swift | ✅ | *N/A* <sup>4</sup> |
| Terraform | ✅ | *N/A* <sup>4</sup> |
| XML | ✅ | *N/A* <sup>4</sup> |
| YAML | ✅ | *N/A* <sup>4</sup> |

<sup>1</sup> compatibilidad No CSHTML en C# extensión.<br />
<sup>2</sup> JavaScript incrustado en HTML es compatible cuando se realiza la depuración de cliente.<br />
<sup>3</sup> JavaScript / TypeScript depuración de nodo o el explorador.<br />
<sup>4</sup> la extensión correspondiente para VS Code no admite actualmente la depuración. Tan pronto como lo hace, investigaremos agregar compatibilidad con la depuración conjunta a él. <br />

### <a name="platforms"></a>Plataformas

| Tipo de aplicación/plataforma | Depuración de compartidos | Uso compartido de aplicaciones |
|-------------------|--------------|-------------|
| Arduino | ✅ | *N/A* |
| Azure App Service | ✅ | *N/A* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Funciones de Azure (local y remoto) | ✅ | ✅ <sup>1</sup> |
| Cadena de bloques (Ethereum) | ✅ | ✅ <sup>1</sup> |
| Consola / CLI | ✅ | ✅ <sup>4</sup> |
| Bases de datos | <sup>5</sup> | ✅ <sup>1</sup> |
| Escritorio (Electron/native) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| Juegos (Unity) | ✅ | <sup>9</sup> |
| Juegos (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *N/A* | ✅ <sup>6</sup> |
| Mobile (Cordova) | ✅ | ✅ <sup>1,7</sup> |
| Mobile (nativo) | ✅ | <sup>9</sup> |
| Mobile (React Native) | ✅ | ✅ <sup>1,8</sup> |
| Aplicación Web / API (Back-end) | ✅ | ✅ <sup>1</sup> |
| Aplicación Web (front-end) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Extensiones de VS Code | | <sup>9</sup> |

<sup>1</sup> a través de [recurso compartido de servidor local](../use/vscode.md#share-a-server).<br />
<sup>2</sup> depuración se realiza con del host explorador en lugar de invitado.<br />
<sup>3</sup> mediante el uso compartido de back-end.<br />
<sup>4</sup> compatible a través de los terminales compartidos.<br />
<sup>5</sup> depurar procedimientos almacenado de la base de datos no se admite actualmente <br />
<sup>6</sup> a través de "preview". Sin embargo, debido a un problema conocido no aparezcan las imágenes. [Voto (👍) aquí.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> aplicaciones de Cordova pueden compartirse a través de la plataforma "explorador"<br />
<sup>8</sup> react Native apps pueden compartirse a través de la exposición y [servidores compartidos](../use/vscode.md#share-a-server).<br />
<sup>9</sup> live Share no es compatible actualmente con windows y pantallas de uso compartidas. [Voto (👍) aquí.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Programa para la mejora

Aunque la mayoría de lenguajes tienen algunos archivos de solo compatibilidad con Intellisense, hay algunas advertencias que se describen a continuación. Todos los lenguajes y plataformas admiten la edición conjuntamente. El resto de la lista trata las características avanzadas actualmente sin soporte técnico completo, universal:

### <a name="languages"></a>Lenguajes

| Lenguaje | Servicios de lenguaje de único archivo | Servicios de lenguaje de todo el proyecto | Depuración conjunta |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅  <sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *N/A* | <sup>2</sup> |
| CSS | ✅ | *N/A* | *N/A* |
| JavaScript / TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *N/A* | *N/A* |
| PowerShell | ✅ | *N/A* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *N/A* | <sup>4</sup> |
| SQL / T-SQL | ✅ | *N/A* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *N/A* | ✅ |

<sup>1</sup> gap: ASPX, CSHTML y VBHTML tienen un conocido problemas aproximadamente incrustado C#/VB ayuda al código subyacente C#/VB archivos no se resuelven debido a la funcionalidad intellisense completa no está implementada. [Voto (👍) aquí, en CSHTML y VBHTML.](https://github.com/MicrosoftDocs/live-share/issues/59) [Voto (👍) aquí en ASPX.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> JavaScript incrustado en HTML es compatible cuando se realiza la depuración de cliente.<br />
<sup>3</sup> JavaScript / TypeScript depuración de nodo o el explorador.<br />
<sup>4</sup> aunque la depuración de XAML en sí mismo es técnicamente N/D, se admite la depuración de código subyacente.<br />
<sup>5</sup> gap: Errores de servicio de lenguaje R en el lado de invitado en combinación y después de cada línea nueva. No se admite. [Voto (👍) aquí.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>Plataformas

| Tipo de aplicación/plataforma | Depuración conjunta | Uso compartido de aplicaciones |
|-------------------|--------------|-------------|
| Aplicación Web / API (Back-End) | ✅ | ✅ <sup>1</sup> |
| Aplicación Web (front-end) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Comprobación de | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Espacios de desarrollo de Azure](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Bases de datos | <sup>4</sup> | ✅ <sup>5</sup> |
| Consola / CLI | ✅ | ✅ <sup>6</sup> |
| Escritorio (formularios Windows Forms) | ✅ | |
| Escritorio (WPF) | ✅ | |
| Plataforma universal de Windows | ✅ |  |
| Extensiones de VS | ✅ |  |

<sup>1</sup> a través de [recurso compartido de servidor local](../use/vs.md#share-a-server). También puede usar las aplicaciones Web ASP.NET [uso compartido de aplicaciones web automática](../use/vs.md#automatic-web-app-sharing).<br />
<sup>2</sup> depuración se realiza con del host explorador en lugar de invitado.<br />
<sup>3</sup> mediante el uso compartido de back-end.<br />
<sup>4</sup> depurar procedimientos almacenado de la base de datos no se admite actualmente <br />
<sup>5</sup> a través de [recurso compartido de servidor local](../use/vs.md#share-a-server). <br />
<sup>6</sup> parcialmente compatible a través de los terminales compartidos.<br />
<sup>?</sup> Aún no se ha validado.

## <a name="see-also"></a>Vea también

- [Compatibilidad con extensiones](extensions.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Todos los errores principales, las solicitudes de características y limitaciones](https://aka.ms/vsls-issues)
- [Todas las solicitudes de características y limitaciones](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
