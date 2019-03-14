---
title: 'Extensiones y el ecosistema de soporte técnico: Visual Studio Live Share | Microsoft Docs'
description: Información general de compatibilidad con las extensiones para Visual Studio Live share.
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
ms.openlocfilehash: 5a9787643643c22ca7302528dc794480d09df902
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256359"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="extensions-and-ecosystem-support"></a>Extensiones y soporte técnico del ecosistema

Uno de los objetivos principales de Visual Studio Live Share es que los desarrolladores puedan colaborar entre sí, desde la comodidad de sus favoritos, y [ **muy personalizable** ](https://marketplace.visualstudio.com/) herramientas. De este modo, ad-hoc interacciones pueden producirse con frecuencia, sin dejar de familiares y ergonómico visualmente, independientemente qué ayudan a con. Para lograr esto, es fundamental que los participantes en una sesión de colaboración son capaces de seguir usando las extensiones que admiten sus [flujos de trabajo y preferencias personales](#user-specific-extensions) (por ejemplo, los temas de color o icono, los enlaces de teclado, editor de potenciadores de productividad).

Además, para realizar la acción de unirse a una sesión de colaboración como instantánea como sea posible, mientras sigue siendo altamente productivo, el objetivo de Visual Studio Live Share es habilitar los invitados puedan aprovechar automáticamente las herramientas específicas del proyecto que ha compartido su host. De este modo, puede simplemente haga clic en un vínculo, inicie la herramienta de elección y comience a colaborar, sin ninguna configuración adicional. Para lograr esto, es fundamental que extensiones, que el núcleo de energía [editar, compilar y depurar el flujo de trabajo](#project-specific-extensions), son de forma transparente "remotos" desde el host al invitado, para que las cosas como la finalización automática, ir a definición y la depuración " simplemente funcionan".

Este documento abarca el actual que se conoce el estado para el ecosistema de gran extensión, así como el "scorecard" para los objetivos mencionados anteriormente. Si se produce una extensión que no cumple este criterio y es fundamental para el flujo de trabajo personal, a continuación, inicie [háganoslo saber!](https://github.com/MicrosoftDocs/live-share/issues/new)

## <a name="user-specific-extensions"></a>Extensiones específicas del usuario

Las extensiones que admiten las personalizaciones específicas del usuario **debe** profesional para el host, y **debe** profesional para todos los invitados. Si una extensión no funciona correctamente para el host, que sería una regresión y es probable que un error en Visual Studio Live Share (por favor, [registre un problema](https://github.com/MicrosoftDocs/live-share/issues/new) si ve alguno!). Si una extensión no se comporta según lo esperado para un invitado, puede requerir [los cambios en la propia extensión](#known-issues), y vamos a trabajar con el ecosistema de dirección/mejorar estos escenarios.

### <a name="visual-studio-code"></a>Visual Studio Code

| Categoría | Ejemplos | ¿Compatible con el invitado? | ¿Colaboración? |
|-|-|-|-|
| Temas de color | [Pro oscuro uno](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme), [salida Coloreador](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer), [arco iris cadena](https://marketplace.visualstudio.com/items?itemName=wk-j.vscode-rainbow-string), [coloreados regiones](https://github.com/jmihelcic/colored-regions), [sangría bloque resaltado](https://marketplace.visualstudio.com/items?itemName=byi8220.indented-block-highlighting), [ Resaltado de la lista de tareas](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight), [Coloreador par corchete angular de cierre](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) | ✅ | *N/A* |
| Conjuntos de iconos | [iconos de vscode](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons), [Visual Studio iconos en vista clásica](https://marketplace.visualstudio.com/items?itemName=jez9999.vsclassic-icon-theme) | ✅ | *N/A* |
| Enlaces de teclado | [VIM](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim), [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings), [mapa de teclas Emacs compatible](https://marketplace.visualstudio.com/items?itemName=lfs.vscode-emacs-friendly) | ✅ | *N/A* |
| Fragmentos de código | [Fragmentos de código de angular v5](https://marketplace.visualstudio.com/items?itemName=johnpapa.Angular2), [fragmentos de código HTML](https://marketplace.visualstudio.com/items?itemName=abusaidm.html-snippets), [SVG iconos](https://marketplace.visualstudio.com/items?itemName=idleberg.svg-icons), [encabezado de archivo](https://marketplace.visualstudio.com/items?itemName=mikey.vscode-fileheader) | ✅ | *N/A* <sup>1</sup> |
| Organización | [Sincronización de configuración](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync), [jefe de proyecto](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager), [Timeit](https://marketplace.visualstudio.com/items?itemName=smulyono.timeit), [puntos de control](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints), [analizador TODO](https://marketplace.visualstudio.com/items?itemName=minhthai.vscode-todo-parser), [favoritos ](https://marketplace.visualstudio.com/items?itemName=kdcro101.favorites) (❌), [marcadores](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) (❌) | ✅ <sup>2</sup> | *N/A* <sup>3</sup> |
| Productividad | [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens), [etiqueta automático Rename](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag), [código esquema](https://github.com/patrys/vscode-code-outline), [resaltado de Color](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight), [incrementar selección](https://marketplace.visualstudio.com/items?itemName=albymor.increment-selection), [ Bracketeer](https://marketplace.visualstudio.com/items?itemName=pustelto.bracketeer), [vista previa de imagen](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview), [JSON auxiliar](https://marketplace.visualstudio.com/items?itemName=zhoufeng.json-helper) (mantenga el mouse), [selector de Color](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color), [copiar Word cursor](https://marketplace.visualstudio.com/items?itemName=alefragnani.copy-word), [CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) (CodeLens), [Git coautores](https://github.com/rjimenezda/vscode-coauthor), [JavaScript ajuste](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster) (CodeActions), [registro de la consola de Turbo](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log), [ Ir a siguiente/anterior miembro](https://marketplace.visualstudio.com/items?itemName=mishkinf.goto-next-previous-member), [desplazamiento automático](https://github.com/PejmanNik/vscode-autoScroll?files=1), [NPM importación versión](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-npm-import-package-version) (❌), [importar costo](https://github.com/wix/import-cost) (❌) | ✅ <sup>2</sup> | ❌ <sup>3</sup> |
| REPL | [Cliente REST](https://marketplace.visualstudio.com/items?itemName=humao.rest-client), [código ejecutor](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner), [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode), [R](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) | ✅ <sup>4</sup> | ❌ <sup>3</sup>  |
| Administradores de recursos | [MSSQL](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql), [ftp simple](https://marketplace.visualstudio.com/items?itemName=humy2833.ftp-simple), [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [Docker](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker), [Brew servicios](https://marketplace.visualstudio.com/items?itemName=beauallison.brew-services) | ✅ <sup>5</sup> | ❌ <sup>3</sup>  |

<sup>1</sup> *a menos que un usuario ya estaba familiarizado con un fragmento de código, no esperaría que esté disponible y, por lo tanto, hacerlos compartido no necesariamente tiene sentido.*

<sup>2</sup> *estas categorías de extensión son tan diversas, que es imposible que decir funcionan. Sin embargo, en teoría, debe y realizaremos un seguimiento de la clave de las que no.*

<sup>3</sup> *estas categorías de extensión pueden beneficiarse de las experiencias de colaboración y, por lo que necesitamos comentarios del usuario final que saber!*

<sup>4</sup> *requieren el invitado tiene instaladas las herramientas de tiempo de ejecución (por ejemplo, Node.js), y trabajar mediante la ejecución de código localmente.*

<sup>5</sup> *estas funcionan mediante la conexión a un servidor de algún tipo y puede trabajar con ambos servidores centralizados, los servidores que ha compartido el invitado.*

### <a name="visual-studio"></a>Programa para la mejora

Próximamente.

## <a name="project-specific-extensions"></a>Extensiones específicas del proyecto

Extensiones de host instalado, que admiten el núcleo de edición, compilación y depuración de una aplicación y son específicos de un lenguaje o plataforma/biblioteca/SDK, deben ser disponibles automáticamente para los invitados, sin necesidad de instalar nada. De este modo, hosts pueden configurar su entorno para admitir desarrollo productivo de un proyecto y permitir que sus invitados al instante a unirse a ellos, sin requisitos previos adicionales. Dado que no son extensiones específicas del proyecto subjetiva o personal de cualquier manera, que pueden determinista compartirse de host a invitado, sin afectar al entorno familiar de cualquier persona.

Además, con el fin de admitir extensiones específicas del proyecto que tenga instalado un invitado, pero el host no, sería lo ideal es que proporcionan una experiencia degradada, todavía funcional (por ejemplo, intellisense de archivo único de introducción, poder dar formato a un documento).

| Categoría | Ejemplos | ¿Compartido? | ¿Compatible con el invitado? |
|-------|----------|--------|-----|
| Gramáticas / resaltado de sintaxis | [Shell de peces](https://marketplace.visualstudio.com/items?itemName=TeddyDD.fish), [Nginx](https://marketplace.visualstudio.com/items?itemName=shanoor.vscode-nginx), [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur), [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv), [ES6 cadena HTML](https://marketplace.visualstudio.com/items?itemName=hjb2012.vscode-es6-string-html), [Todo +](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus), [Arco iris CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv) | ❌ | ✅ |
| Servicios de lenguaje | [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml), [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [ARM](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) | ✅ <sup>1</sup>| ✅ <sup>2</sup> |
| JSON Schemas | [Funciones de Azure](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions) | ✅ | ✅ |
| Linter | [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint), [Markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint), [código corrector ortográfico](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker), [PHPCS](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs) | ✅ | ✅ <sup>2</sup>  |
| Formateadores | [Más agradable](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode), [de presentación](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) | ✅ | ✅ <sup>2</sup> |
| Depuradores | [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python), [depurador para Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) | ✅ <sup>3</sup> | ❌ <sup>4</sup> |
| Ejecutores de pruebas | [Ejecutor de pruebas de Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test), [Mocha Sidebar](https://marketplace.visualstudio.com/items?itemName=maty.vscode-mocha-sidebar), [Postman ejecutor](https://marketplace.visualstudio.com/items?itemName=eridem.vscode-postman), [Jest ejecutor](https://marketplace.visualstudio.com/items?itemName=firsttris.vscode-jest-runner), [Neptune](https://marketplace.visualstudio.com/items?itemName=LambdaFactory.neptune) | ❌ <sup>5</sup> | ✅ <sup>2</sup> |
| Controladores de vista previa de archivo personalizado | [Vista previa SVG](https://marketplace.visualstudio.com/items?itemName=cssho.vscode-svgviewer), [GraphViz](https://marketplace.visualstudio.com/items?itemName=joaompinto.vscode-graphviz), [tamaño de la imagen de Markdown](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-image-size) | ❌ |  ✅ |
| Los generadores de archivo o proyecto | [Las funciones de Azure](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [generador de proyectos de C o C++](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-project-generator) | ❌ | ❌<sup>6</sup> |
| Proveedores de control de código fuente | [SVN](https://marketplace.visualstudio.com/items?itemName=johnstoncode.svn-scm), [Hg](https://marketplace.visualstudio.com/items?itemName=mrcrowl.hg) | ❌ | ❌ |

<sup>1</sup> *actualmente solo C# y JavaScript/TypeScript, con soporte técnico más próximamente.*

<sup>2</sup> *solo admiten el documento activo actual, puesto que los invitados no tienen acceso al archivo local.*

<sup>3</sup> *se comparte la experiencia de depuración de núcleo, sin embargo, no se reenvían automáticamente todos los servidores iniciados.*

<sup>4</sup> *invitados no tienen una copia local de la aplicación y, por lo tanto, deben empezar en la máquina del host de la aplicación en ejecución y las sesiones de depuración.*

<sup>5</sup> *la salida de una serie de pruebas requiere que los terminales resultantes, paneles de salida y los errores también se han compartido con los invitados.*

<sup>6</sup> *casi todos estos utilizaría el Node.js `fs` módulo directamente para crear archivos, lo que podría no funcionarían.*

### <a name="visual-studio"></a>Programa para la mejora

Próximamente.

## <a name="known-issues"></a>Problemas conocidos

Los siguientes son problemas conocidos actualmente extensión, que podrían impedir que el trabajo de los invitados en el contexto de una sesión de colaboración (junto con sus soluciones alternativas) y, por lo tanto, podrían afectar a su flujo de trabajo:

### <a name="visual-studio-code"></a>Visual Studio Code

| Problema | Motivo | Solución |
|-|-|-|
| Mediante el Node.js `fs` módulo para detectar o leer archivos (por ejemplo, un archivo de configuración), o enumerar directorios (y no es un servicio de lenguaje). | Los invitados no tienen acceso al archivo local. | 1. Degradar de forma correcta la experiencia del usuario *(si es posible).*<br /><br />2. Use la `openTextDocument` y `findFiles` API para leer y enumerar los archivos del área de trabajo. |
| Mediante el Node.js `fs` módulo para crear o escribir archivos | *Igual que el anterior* | *N/D* puede usar el `openTextDocument(Uri)` API para crear un `untitled` archivo, pero no puede guardarlo directamente en el sistema de archivos en una ruta específica. |
| Según un agrupados por el proyecto de biblioteca o una herramienta | *Igual que el anterior* | 1. Agrupación de una versión de la dependencia con la extensión de reserva<br><br> 2. Admite la instalación global para desbloquear a los invitados si desean instalarlo explícitamente.<br><br> 3. El estado/acción si es posible, ya que el host tendría las dependencias derechos disponibles remoto. |
| Mediante el Node.js `fs` módulo para crear un directorio | *Igual que el anterior* | *N/A* |
| Restringir la funcionalidad a documentos que usan el `file` esquema. | Archivos en uso del invitado la `vsls` esquema. | Agregar compatibilidad para `vsls` documentos ([ejemplo](https://github.com/CoenraadS/BracketPair/pull/73)) |
| Mediante el `Uri.file` método y/o `Uri.fsPath` / `TextDocument.fileName` miembros para serializar y analizar los URI | *Igual que el anterior* | Use `Uri.parse` y `Url.toString()` en su lugar, lo que mantener y respetar los esquemas de archivo ([ejemplo](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| Mediante el `workspace.openTextDocument` método con una ruta de acceso de archivo en lugar de un `Uri` | *Igual que el anterior* | Proporcione un `Uri` instancia en lugar de una cadena de ruta de acceso de archivo sin formato ([ejemplo](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| Mediante el `workspace.rootPath` propiedad para detectar la presencia de un área de trabajo | El `workspace.rootPath` propiedad llamadas `Uri.fsPath` en la primera `workspaceFolder` en el `workspace`, que tiene el mismo problema se ha mencionado anteriormente | Use la `workspace.workspaceFolders` propiedad para detectar la presencia de un área de trabajo en su lugar y si es necesario, examine cada `workspaceFolder`del `Uri.scheme` para determinar si es local o no |
| No se especifica un esquema de documento al registrar los servicios de lenguaje (ya sea a través de un `LanguageClient`, o el `languages.register*` métodos) | Invitados recepción los resultados del servicio de lenguaje desde sus extensiones locales y el host y, por lo tanto, si ambos participantes tienen la misma extensión de servicio de lenguaje instalada, los invitados verá entradas duplicadas para ciertas cosas (por ejemplo, Autocompletar, código acciones) | Restringir los servicios de lenguaje solo `file` y `untitled` esquemas ([ejemplo](https://github.com/vuejs/vetur/pull/756/files)) |
| Si no activa un documento `Uri.scheme` antes de rellenar un `DiagnosticCollection` para él | *Igual que el anterior* | Generar solo `Diagnostics` para `documents` cuyo `Uri.scheme`  ===  `file` ([ejemplo](https://github.com/Huachao/vscode-restclient/pull/196)) |
| No comprobar para el esquema de área de trabajo al devolver `Tasks` desde un personalizado `TaskProvider`  | Mostrar todas las tareas remotas y locales invitados y, por lo tanto, mostraría duplicados si ambos participantes tenían instalada la extensión del misma  | Devolver solo `Tasks` para `WorkspaceFolder`s cuyo `Uri.scheme`  ===  `file` ([ejemplo](https://github.com/Microsoft/vscode-eslint/blob/0fdb7c74b093cae9dc08355e7235582a254f24c2/client/src/tasks.ts#L42)) |

### <a name="visual-studio"></a>Programa para la mejora

Próximamente.

<!--

## Extensibility API

In addition to the core goals outlined in the beginning of this document, Live Share also wants to enable extension authors to enhance the default sharing experience in the following ways:

1. Contributing to the core collaborative feature set, based on behavior that only the extension would know about. In these scenarios, the host could have an extension installed, and potentially allow guests to benefit from it without also needing to have it installed

2. Enhancing their own experiences to be collaborative (e.g. syncing bookmarks between participants), by synchronizing any custom state and UI interactions. In these scenarios, only participants that had the custom extension installed would be able to take advantage of the added collaboratively.

This will require some form of API/SDK, which extensions can use to determine if/when the end-user is within a Live Share session, and if so, light up additional capabilities. The following represents a high-level overview of some of the extension points we've identified, and look forward to getting further feedback on:

| Shared Resource | Extensibility Point(s) |
|------------------|---------------------|
| User status | 1. Retrieving the list of participants within the current Live Share session (e.g. the [Git Co-Authors](https://marketplace.visualstudio.com/items?itemName=drrouman.git-coauthors) extension could use that to populate the host's commit message with)<br /><br /> 2. Updating a participant's location (outside of just editors), as well as allowing other participant's to jump to/pin to them as they move into custom extension UI (e.g. a participant is navigating a MongoDB database using the [Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) extension). |
| Workspace | *N/A* - Live Share can transparently share all files, edits, cursors and highlights, without requiring an extension to do anything extra if it modified the file system and/or cursor/highlight position. |
| Language Services | *N/A* - Long-term, Live Share can transparently remote all language services (e.g. go to definition, document formatting, CodeLens) to the guest, including those that are contributed via extensions (e.g. [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)) |
| Debugging Sessions | *N/A* - Live Share can transparently remote all debugging sessions, including those that are enabled by custom extensions (e.g. [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)) |
| Servers | 1. Sharing a server that an extension was responsible for starting, and then optionally specifying whether a browser should be launched on the guest's machine as well (e.g. a debug adapter that launched a web server).  |
| Custom | 1. Synchronizing arbitrary state and/or user interactions (e.g. the [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) extension syncing CRUD operations across participants, the [Maven for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven) extension exposing the project-wide view to guests) |

-->

## <a name="see-also"></a>Vea también

- [Compatibilidad con lenguajes y plataformas](platform-support.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)
- [Todos los errores principales, las solicitudes de características y limitaciones](https://aka.ms/vsls-issues)
- [Todas las solicitudes de características y limitaciones](https://aka.ms/vsls-feature-requests)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
