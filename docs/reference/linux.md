---
title: Detalles de la instalación de Linux - Visual Studio Live Share | Microsoft Docs
description: Información detallada acerca de cómo instalar Visual Studio Live Share en Linux.
ms.custom: ''
ms.date: 10/6/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 9ac16b0e598fb07446c2b682397684b7e2e4709a
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640138"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Detalles de la instalación de Linux

Linux es un entorno altamente variable y con el gran número de distribuciones y entornos de escritorio puede ser complicado hacerlo funcionar. Si se limita a las versiones compatibles de **escritorio Ubuntu** (16.04 +), **CentOS 7**, o **Fedora Workstation** (27 +) y usar solo **distribuciones oficiales de VS Código**, debe buscar el proceso sencillo. Sin embargo, en caso de que use una configuración no estándar o una configuración de nivel inferior, es posible que se encuentre (o no) con algunas interrupciones. Este documento proporciona información sobre los requisitos y algunos detalles de solución de problemas que puedan ayudar a ponerse en marcha y admite la ejecución incluso si la configuración es única Comunidad. Tenga en cuenta que solo admite Live Share **Linux de 64 bits**.

## <a name="install-linux-prerequisites"></a>Instalación de los requisitos previos de Linux

En algunas distribuciones de Linux faltan bibliotecas que Live Share necesita para funcionar. De manera predeterminada, Live Share intenta detectar e instalar los requisitos previos de Linux. Verá una notificación del sistema cuando Live Share encuentre un problema que pueda provenir de la falta de bibliotecas en la que se le pedirá permiso para instalarlas.

![Mensaje de notificación del sistema notificación que muestra que faltan requisitos previos de Linux](../media/vscode-linux-prereq-missing.png)

Al hacer clic en "Instalar", aparecerá una ventana de terminal en su sistema operativo le pedirá que escriba su administrador o raíz (sudo) contraseña para continuar. Suponiendo que el script se complete correctamente, volver a cargar Visual Studio Code cuando se le solicite debería ser todo listo! También puede consultar las **[sugerencias de distribución](#tips-by-distribution)** para ver otras indicaciones y soluciones alternativas que puedan existir.

Si ve un mensaje que indica que el script no es compatible con la distribución, consulte las **[sugerencias para las distribuciones compatibles con la comunidad](#tips-for-unsupported-distros)** para ver la información que la comunidad nos ha compartido.

Si se **no prefieren tener VS Code, ejecute el comando de**, también puede para volver a ejecutar la versión más reciente de este script en cualquier momento manualmente mediante el comando siguiente en una ventana de Terminal:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>Sugerencias de distribución

Durante la instalación de los requisitos previos script anterior abarca una variedad de distribuciones, quizás se pregunte lo que normalmente no está en las instalaciones de vainilla. La siguiente lista muestra las bibliotecas principales que no estaban presentes en una instalación nueva de una distribución dada. La lista también proporciona algunas sugerencias que pueden ayudarle a ponerse en marcha si se produce un problema.

| Distribución | Vainilla instalar las bibliotecas que faltan | Pasos adicionales |
|--------|-------------------|----|
| Escritorio Ubuntu 18.04 (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Escritorio Ubuntu 16.04 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 (64 bits) |&lt;none&gt;  | <ul><li>Asegúrese de "iniciar servicios GNOME al inicio" está activada en la pestaña "Advanced" de "E inicio de sesión".</li><li>Si experimenta problemas de inicio de sesión, instale `seahorse`, iniciarlo "Contraseñas y claves", compruebe que dispone de conjunto de claves "Login" y que se puede desbloquear.</li></ul> |
| Xubuntu 16.04 (64 bits) | &lt;none&gt; | <ul><li>Asegúrese de "iniciar servicios GNOME al inicio" está activada en la pestaña "Advanced" de "E inicio de sesión".</li><li>Si experimenta problemas de inicio de sesión, instale `seahorse`, iniciarlo "Contraseñas y claves", compruebe que dispone de conjunto de claves "Login" y que se puede desbloquear.</li></ul> |
| Canela 19 Mint (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Canela 18,3 Mint (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| 10 de Debian (validador) las pruebas (64 bits) | Versión no estable, por lo tanto desconocida. | <ul><li>Pruebas de Debian y Unstable (Sid) no se admiten oficialmente.</li><li>Hay un [problema conocido](https://github.com/dotnet/corefx/issues/33179) en .NET Core que afecta a Live Share. </li><li>Consulte [aquí para encontrar una solución](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249).</li></ul> |
| Escritorio GNOME 9 Debian (64 bits) | &lt;none&gt; | <ul><li>Es posible que deba instalar `sudo` y agregue el usuario al grupo de sudo para usar el script de instalación automatizada.</li>  |
| Estación de trabajo de Fedora (64 bits) de 29 | `openssl-compat10` | &lt;none&gt; |
| Estación de trabajo Fedora 28 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Estación de trabajo Fedora 27 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Escritorio GNOME centOS 7 (64 bits) | &lt;none&gt; | &lt;none&gt; |

Consulte **[sugerencias para las distribuciones compatible con la Comunidad](#tips-for-community-supported-distros)** para obtener información acerca de otro no-Debian / distribuciones basadas en Ubuntu o RHL.

También puede encontrar detalles adicionales [debajo](#detailed-library-requirements) en las bibliotecas específicas de Live Share necesita.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>Sugerencias para las distribuciones compatible con la Comunidad

Distribuciones fuera el Debian / Ubuntu o RHL árboles no son compatibles oficialmente con Visual Studio Code o .NET Core. Por lo tanto, por extensión, no se oficialmente admiten por Visual Studio Live Share bien. Sin embargo, la Comunidad ha contribuido información útil acerca de Live Share entre en funcionamiento en un número de distribuciones adicionales.

> **Incorporación de cambios de bienvenida:** Si está interesado en actualizar esta información con la distribución de favoritos, envíe un PR para [este archivo](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) en nuestro repositorio de documentos de GitHub. Mejor aún, si desea obtener el instalador de dependencia que admiten la distribución de favoritos, puede enviar un PR [para este archivo](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh).

| Distribución | ¿Funciona? | Vainilla instalar las bibliotecas que faltan | Pasos adicionales |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 bits) | Sí | Varía. Bibliotecas posibles: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>Compatible con la [script de instalación de requisitos previos](#install-linux-prerequisites).</li><li>Use la [visual studio código bin](https://aur.archlinux.org/packages/visual-studio-code-bin) paquete AUR para VS Code.</li><li>`sudo` debe instalarse para utilizar el requisito previo automatizado instalará script.</li><li>`gnome-keyring` puede requerir adicionales [pasos de configuración](https://wiki.archlinux.org/index.php/GNOME/Keyring) en algunos entornos de escritorio.</ul> |
| Manjaro 17.1 (64 bits) | Sí | `xorg-xprop liburcu` | <ul><li>Compatible con la [script de instalación de requisitos previos](#install-linux-prerequisites).</li><li>Use la [visual studio código bin](https://aur.archlinux.org/packages/visual-studio-code-bin) paquete AUR para VS Code.</li></ul> |
| openSuSE LEAP 15 KDE (64 bits) | Sí | `libopenssl1_0_0 gnome-keyring` | <ul><li>Compatible con el script de instalación de requisitos previos.</li></ul> |
| 3 solus (64 bits) | Sí | `xprop` | <ul><li>Compatible con la [script de instalación de requisitos previos](#install-linux-prerequisites).</li><li>Las versiones de la `vscode` product.json requiere valores no tenían el paquete antes de la versión 57 ([vea más abajo](#vs-code-oss-issues)). Actualizar el `vscode` paquete para resolver este problema.</li></ul> |
| Gentoo (64 bits) | Sí | Muy variable. Paquetes que falten posibles: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>El `visual-studio-code` del paquete en el **jorgicio** superposición está comprobada que funciona.</li></ul>

## <a name="install-prerequisites-manually"></a>Instalar manualmente los requisitos previos

 Aunque se recomienda utilizar Live Share **script de instalación de la dependencia**, esta sección proporciona más detalles sobre los requisitos de la biblioteca en caso de que desea realizar estos pasos usted mismo o está usando una distribución que no admite la Guión.

Típicas bibliotecas que faltan en las instalaciones de vainilla pueden encontrarse en el [sugerencias según la distribución](#tips-by-distribution) y [sugerencias para las distribuciones compatible con la Comunidad](#tips-for-unsupported-distros) secciones.

### <a name="detailed-library-requirements"></a>Requisitos de la biblioteca detallada

Requisitos de la biblioteca nativa del Visual Studio Live Share proceden de su uso de .NET Core 2.1, libsecret para conservar las credenciales y su integración con el explorador. En la tabla siguiente se resume estos requisitos para las distribuciones oficialmente compatibles con .NET Core.

| Distribución | Req de .NET core. | Requisitos de almacenamiento de credenciales| Requisitos de integración de explorador |
|--------------|-----------|--------------------|------------|
| Ubuntu y distribuciones de nivel inferiores | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (para Ubuntu 16.04, menta 18,3) o `libicu57` (para Ubuntu con 17.10) o `libicu60` (para Ubuntu 18.04, menta 19) | `libsecret-1-0 gnome-keyring` (o Kwallet no admite libsecret - libsecret admite el conjunto de claves) | `desktop-file-utils x11-utils` |
| Debian distribuciones 9 y descendentes | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (o Kwallet no admite libsecret - libsecret admite el conjunto de claves) | `desktop-file-utils x11-utils` |
| RHL / CentOS/ Fedora | `openssl-libs krb5-libs zlib libicu` Fedora también requiere `compat-openssl10`| `libsecret gnome-keyring` (o Kwallet no admite libsecret - libsecret admite el conjunto de claves) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (o Kwallet no admite libsecret - libsecret admite el conjunto de claves) | `desktop-file-utils xprop`

Mientras que otras distribuciones requieren las mismas bibliotecas, sus nombres de paquete pueden variar. Puede encontrar algunas de ellas en el [sugerencias para las distribuciones compatible con la Comunidad](#tips-for-unsupported-distros) sección.

### <a name="debian--ubuntu"></a>Debian / Ubuntu

Las bibliotecas pueden instalarse en distribuciones basadas en Debian/Ubuntu ejecutando `sudo apt install <library-name>` en un terminal.

Para las distribuciones de Ubuntu basada incluidos Mint, ejecute:

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Debian 9 y no Ubuntu descendentes distribuciones, ejecute:

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora / CentOS / RHL

Las bibliotecas pueden instalarse en las distribuciones de CentOS y Fedora/RHL basado mediante la ejecución de `sudo yum install <library-name>` en un terminal. Por ejemplo, se instalará todo:

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>Problemas de OSS de código de VS

> **Arch Linux/Manjaro usuarios:** Use la [visual-studio-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) paquete AUR para evitar este problema.

Paquetes de Visual Studio Code cualquier vainilla o modificación las versiones de sistemas operativos de código de VS pueden que falte un valor crítico de `product.json` archivo que impide que Visual Studio Live Share de activación.

Una forma rápida de ver que es posible que se produzca este problema es ir a Ayuda > "Alternar herramientas de desarrollo" y vea si encuentra un seguimiento de pila que indica la extensión Live Share no activó porque estaba usando "API propuesta".

Para comprobar que éste es el problema, compruebe el contenido de `product.json`. La ubicación del archivo varían según el paquete, pero normalmente resulta en una de las siguientes ubicaciones:

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

Si el `extensionAllowedProposedApi` propiedad está ausente o no ve "ms-vsliveshare.vsliveshare" al que hace referencia, utiliza una versión de OSS con este problema.

Como un **solución**, puede agregar lo siguiente en el product.json:

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

Consulte [anteriormente](#tips-for-community-supported-distros) para obtener más detalles sobre si se conoce la distribución que se use para que funcione.

## <a name="linux-browser-integration"></a>Integración del explorador de Linux

Por lo general, Visual Studio Live Share **no necesita pasos de instalación adicionales** para habilitar la integración del explorador en Linux.

Para ello, coloca automáticamente un archivo de escritorio en Live Share `~/.local/share/applications` y el iniciador necesario en `~/.local/share/vsliveshare` cuando inicializa primero la extensión. Si esto se realiza correctamente, se requiere ninguna acción por parte del usuario.

En algunos casos, las distribuciones no admite esta ubicación o requerir ajustes para conseguir que funcione con sus instalaciones de vainilla. En estos casos, Live Share vuelve a utilizar `/usr/local/share` en su lugar. Como resultado, **puedan recibir notificaciones que se requiere la contraseña de administrador (sudo)** para completar el proceso de instalación. Aparecerá una ventana de terminal en la que se le indicará que se instalará el iniciador del explorador. Para cerrar la ventana de terminal, solo debe escribir la contraseña cuando se le solicite y presionar ENTRAR una vez que la instalación termine.

Si prefiere ejecutar el comando usted mismo en su lugar, haga clic en "Copiar en su lugar" que copiará el comando terminal en el Portapapeles en su lugar.

Por último, si decide para omitir este paso completamente, todavía puede [combinar manualmente sesiones de colaboración](../use/vscode.md#join-manually), pero no se puede unir al abrir un vínculo de invitación en el explorador. Tenga en cuenta que siempre puede acceder a los comandos a intentarlo más tarde, presionando **Ctrl + Mayús + P / Cmd + Mayús + P** y seleccionando el "recurso compartido en vivo: Comando de instalación de iniciador".

## <a name="see-also"></a>Vea también

- [Colaboración mediante Visual Studio Code](../use/vscode.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
