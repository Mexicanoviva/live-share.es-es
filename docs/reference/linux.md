---
title: 'Detalles de la instalación de Linux: Visual Studio Live Share | Microsoft Docs'
description: Información detallada sobre la instalación de Visual Studio Live Share en Linux.
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
ms.openlocfilehash: 27a3d76f14cd3c8df312abe7ab36185109ac7e89
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170132"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Detalles de la instalación de Linux

Linux es un entorno altamente variable y con el gran número de distribuciones y entornos de escritorio puede ser complicado hacerlo funcionar. Si se dirige a las versiones admitidas de **Ubuntu Desktop** (16.04 +), versión **7**o **Fedora Workstation** (27 +) y solo usa **distribuciones oficiales de vs Code**, debería encontrar el proceso directo. Sin embargo, en caso de que use una configuración no estándar o una configuración de nivel inferior, es posible que se encuentre (o no) con algunas interrupciones. En este documento se proporciona información sobre los requisitos y algunos detalles de solución de problemas que pueden ayudarle a ponerse en marcha incluso si la configuración solo es compatible con la comunidad. Tenga en cuenta que Live Share solo admite **Linux de 64 bits**.

## <a name="install-linux-prerequisites"></a>Instalación de los requisitos previos de Linux

En algunas distribuciones de Linux faltan bibliotecas que Live Share necesita para funcionar. De manera predeterminada, Live Share intenta detectar e instalar los requisitos previos de Linux. Verá una notificación del sistema cuando Live Share encuentre un problema que pueda provenir de la falta de bibliotecas en la que se le pedirá permiso para instalarlas.

![Notificación del sistema que muestra el mensaje que faltan los requisitos previos de Linux](../media/vscode-linux-prereq-missing.png)

Al hacer clic en "instalar", aparecerá una ventana de terminal en la que el sistema operativo le pedirá que escriba su contraseña de administrador o raíz (sudo) para continuar. Suponiendo que el script se complete correctamente, vuelva a cargar Visual Studio Code cuando se le pida que se establezca. También puede consultar las **[sugerencias de distribución](#tips-by-distribution)** para ver otras indicaciones y soluciones alternativas que puedan existir.

Si ve un mensaje que indica que el script no es compatible con la distribución, consulte las **[sugerencias para las distribuciones compatibles con la comunidad](#tips-for-unsupported-distros)** para ver la información que la comunidad nos ha compartido.

Si **prefiere no tener vs Code ejecutar el comando automáticamente**, puede optar por volver a ejecutar manualmente la versión más reciente de este script en cualquier momento mediante el comando siguiente en una ventana de terminal:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>Sugerencias por distribución

Aunque el script de instalación de requisitos previos anterior cubre una variedad de distribuciones, es posible que se pregunte qué falta normalmente en las instalaciones de vainilla. En la siguiente lista se muestran las bibliotecas de claves que faltaban en una instalación nueva de una distribución determinada. La lista también proporciona algunas sugerencias que pueden ayudarle a ponerse en marcha si se produce un problema.

| Distribución | Instalación de vainilla faltan bibliotecas | Pasos adicionales |
|--------|-------------------|----|
| Ubuntu Desktop 18,04 (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16,04 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18,04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16,04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18,04 (64 bits) |&lt;none&gt;  | <ul><li>Asegúrese de que "iniciar los servicios de GNOME al iniciar" está activado en la pestaña "Opciones avanzadas" de "sesión e inicio".</li><li>Si tiene problemas de inicio de sesión, instale `seahorse`, inicie "contraseñas y claves", compruebe que dispone de un "Inicio de sesión" y que puede desbloquearlo.</li></ul> |
| Xubuntu 16,04 (64 bits) | &lt;none&gt; | <ul><li>Asegúrese de que "iniciar los servicios de GNOME al iniciar" está activado en la pestaña "Opciones avanzadas" de "sesión e inicio".</li><li>Si tiene problemas de inicio de sesión, instale `seahorse`, inicie "contraseñas y claves", compruebe que dispone de un "Inicio de sesión" y que puede desbloquearlo.</li></ul> |
| Menta 19 Cinnamon (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Menta 18,3 Cinnamon (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Pruebas de Debian 10 (validador) (64 bits) | Versión no estable, desconocidos. | <ul><li>Las pruebas de Debian e inestables (SID) no se admiten oficialmente.</li><li>Existe un [problema conocido](https://github.com/dotnet/corefx/issues/33179) en .net Core que afecta a Live share. </li><li>[Aquí encontrará una solución alternativa](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249).</li></ul> |
| Debian 9 GNOME Desktop (64 bits) | &lt;none&gt; | <ul><li>Es posible que tenga que instalar `sudo` y agregar el usuario al grupo sudo para usar el script de instalación automatizada.</li>  |
| Fedora Workstation 29 (64 bits) | `openssl-compat10` | &lt;none&gt; |
| Fedora Workstation 28 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Fedora Workstation 27 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Edición 7 GNOME Desktop (64 bits) | &lt;none&gt; | &lt;none&gt; |

Consulte las **[sugerencias para las distribuciones admitidas](#tips-for-community-supported-distros)** por la comunidad para obtener información sobre otras distribuciones basadas en no Debian/Ubuntu o RHL.

También se pueden encontrar detalles adicionales [a continuación](#detailed-library-requirements) en las bibliotecas específicas Live share necesidades.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>Sugerencias para distribuciones admitidas por la comunidad

Las distribuciones fuera de los árboles Debian/Ubuntu o RHL no se admiten oficialmente en Visual Studio Code o .NET Core. Por lo tanto, por extensión, no se admite oficialmente en Visual Studio Live Share ninguno de ellos. Sin embargo, la comunidad ha contribuido a la obtención de información útil acerca de la puesta en marcha de Live Share en una serie de distribuciones adicionales.

> **Página principal del PR:** Si está interesado en actualizar esta información con su distribución favorita, envíe una solicitud de incorporación de [este archivo](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) en nuestro repositorio de github de documentos. Incluso mejor, si desea obtener el instalador de dependencias que admite su distribución favorita, puede enviar una solicitud [de incorporación de este archivo](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh).

| Distribución | Horarios? | Instalación de vainilla faltan bibliotecas | Pasos adicionales |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 bits) | Sí | Varía. Bibliotecas posibles: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>Compatible con el [script de instalación de requisitos previos](#install-linux-prerequisites).</li><li>Use el paquete [Visual-Studio-Code-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) AUR para vs Code.</li><li>`sudo` tendrá que instalarse para usar el script de instalación de requisitos previos automatizados.</li><li>`gnome-keyring` pueden requerir [pasos de configuración](https://wiki.archlinux.org/index.php/GNOME/Keyring) adicionales en algunos entornos de escritorio.</ul> |
| Manjaro 17,1 (64 bits) | Sí | `xorg-xprop liburcu` | <ul><li>Compatible con el [script de instalación de requisitos previos](#install-linux-prerequisites).</li><li>Use el paquete [Visual-Studio-Code-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) AUR para vs Code.</li></ul> |
| openSuSE LEAP 15 KDE (64 bits) | Sí | `libopenssl1_0_0 gnome-keyring` | <ul><li>Compatible con el script de instalación de requisitos previos.</li></ul> |
| Solus 3 (64 bits) | Sí | `xprop` | <ul><li>Compatible con el [script de instalación de requisitos previos](#install-linux-prerequisites).</li><li>Las versiones del paquete `vscode` anteriores a la versión 57 no tenían los valores product. JSON necesarios ([consulte a continuación](#vs-code-oss-issues)). Actualice el paquete de `vscode` para resolver este problema.</li></ul> |
| Gentoo (64 bits) | Sí | Alta variable. Posibles paquetes que faltan: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>El paquete de `visual-studio-code` en la superposición **jorgicio** se sabe que funciona.</li></ul>

## <a name="install-prerequisites-manually"></a>Instalación manual de los requisitos previos

 Aunque se recomienda usar el **script de instalación de dependencias**de Live Share, en esta sección se proporcionan más detalles sobre los requisitos de la biblioteca en caso de que se realicen estos pasos usted mismo o estén usando una distribución no compatible con el script.

Las bibliotecas que faltan normalmente en las instalaciones de vainilla se pueden encontrar en las secciones [sugerencias por distribución](#tips-by-distribution) y [sugerencias para distribuciones admitidas](#tips-for-unsupported-distros) por la comunidad.

### <a name="detailed-library-requirements"></a>Requisitos de biblioteca detallados

Los requisitos de la biblioteca nativa de Visual Studio Live Share proceden de su uso de .NET Core 2,1, libsecret para conservar las credenciales y su integración con el explorador. En la tabla siguiente se resumen estos requisitos para las distribuciones oficialmente compatibles con .NET Core.

| Distribución | Requisitos de .NET Core | Requisitos de almacenamiento de credenciales| Requisitos de integración del explorador |
|--------------|-----------|--------------------|------------|
| Distribuciones de Ubuntu y downstream | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (para Ubuntu 16,04, menta 18,3) o `libicu57` (para Ubuntu 17,10) o `libicu60` (para Ubuntu 18,04, menta 19) | `libsecret-1-0 gnome-keyring` (o libsecret de claves admitidas: KWallet no admite libsecret) | `desktop-file-utils x11-utils` |
| Distribuciones de Debian 9 y downstream | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (o libsecret de claves admitidas: KWallet no admite libsecret) | `desktop-file-utils x11-utils` |
| RHL/AC/Fedora | `openssl-libs krb5-libs zlib libicu` Fedora también requiere `compat-openssl10`| `libsecret gnome-keyring` (o libsecret de claves admitidas: KWallet no admite libsecret) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (o libsecret de claves admitidas: KWallet no admite libsecret) | `desktop-file-utils xprop`

Aunque otras distribuciones requieren las mismas bibliotecas, los nombres de los paquetes pueden variar. Puede encontrar algunas de ellas en la sección [sugerencias para distribuciones admitidas por la comunidad](#tips-for-unsupported-distros) .

### <a name="debian--ubuntu"></a>Debian/Ubuntu

Las bibliotecas se pueden instalar en las distribuciones basadas en Debian/Ubuntu mediante la ejecución de `sudo apt install <library-name>` en un terminal.

Para distribuciones basadas en Ubuntu, como menta, ejecute:

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

En el caso de las distribuciones de bajada de Debian 9 y no de Ubuntu, ejecute:

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora/AC/RHL

Las bibliotecas se pueden instalar en distribuciones basadas en Fedora/Allocation/RHL mediante la ejecución de `sudo yum install <library-name>` en un terminal. Por ejemplo, se instalará todo:

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>Problemas de VS Code OSS

> **Usuarios de Arch Linux/Manjaro:** Use el paquete [Visual-Studio-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) AUR para evitar este problema.

Los paquetes de Visual Studio Code que son versiones de vainilla o modificadas de VS Code OSS pueden carecer de un valor crítico en `product.json` archivo que impide que Visual Studio Live Share se active.

Una forma rápida de ver que podría estar llegando a este problema es ir a ayuda > "alternar Herramientas de desarrollo" y ver si encuentra un seguimiento de la pila que indica que la extensión de Live Share no se activó porque estaba usando una "API propuesta".

Para comprobar que este es el problema, compruebe el contenido de `product.json`. La ubicación del archivo varía según el paquete, pero normalmente se encuentra en una de las siguientes ubicaciones:

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

Si falta la propiedad `extensionAllowedProposedApi` o no ve "MS-vsliveshare. vsliveshare" a la que se hace referencia, se usa una versión de OSS con este problema.

Como **solución alternativa**, puede agregar lo siguiente al archivo product. JSON:

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

Consulte más [arriba](#tips-for-community-supported-distros) para obtener más información sobre si la distribución que está usando se sabe que funciona.

## <a name="linux-browser-integration"></a>Integración del explorador de Linux

Por lo general, Visual Studio Live Share **no necesita pasos de instalación adicionales** para habilitar la integración del explorador en Linux.

Para ello, Live Share coloca automáticamente un archivo de escritorio en `~/.local/share/applications` y el iniciador necesario en `~/.local/share/vsliveshare` cuando la extensión se inicializa por primera vez. No se requiere ninguna acción por su parte si esto se realiza correctamente.

En algunos casos, las distribuciones no admiten esta ubicación o requieren ajustes para que funcione con sus instalaciones de vainilla. En estos casos, Live Share recurre al uso de `/usr/local/share` en su lugar. Como resultado, es **posible que se le notifique que la contraseña de administrador (sudo) es necesaria** para completar el proceso de instalación. Aparecerá una ventana de terminal en la que se le indicará que se instalará el iniciador del explorador. Para cerrar la ventana de terminal, solo debe escribir la contraseña cuando se le solicite y presionar ENTRAR una vez que la instalación termine.

Si prefiere ejecutar el comando usted mismo, puede hacer clic en "copiar en su lugar", que copiará en su lugar el comando de terminal en el portapapeles.

Por último, si opta por omitir este paso por completo, todavía puede [unirse a sesiones de colaboración manualmente](../how-to-guides/vscode.md#join-manually), pero no podrá unirse abriendo un vínculo de invitación en el explorador. Tenga en cuenta que siempre puede acceder al comando de nuevo más adelante, presionando **Ctrl + Mayús + P/Cmd + Mayús + P** y seleccionando el comando "Live Share: instalación del iniciador".

## <a name="see-also"></a>Vea también

- [Cómo colaborar con Visual Studio Code](../how-to-guides/vscode.md)
- [Requisitos de conectividad de Live Share](connectivity.md)
- [Características de seguridad de Live Share](security.md)

¿Tiene algún problema? Consulte la [solución de problemas](../troubleshooting.md) o [envíe sus comentarios](../support.md).
