---
title: Solución de problemas de AzCopy en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Solución de problemas de errores de Azure AzCopy al cargar datos que no son de Office 365 para la corrección de errores en eDiscovery (Premium).
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 85d51e7ecb59f8423f0a509725c6a1c1defd3adf
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092335"
---
# <a name="troubleshoot-azcopy-in-ediscovery-premium"></a>Solución de problemas de AzCopy en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Al cargar datos o documentos que no son de Microsoft 365 para la corrección de errores en microsoft Purview eDiscovery (Premium), la interfaz de usuario proporciona un comando de Azure AzCopy que contiene parámetros con la ubicación en la que se almacenan los archivos que desea cargar y la ubicación de almacenamiento de Azure en la que se cargarán los archivos. Para cargar los documentos, copie este comando y ejecútelo en un símbolo del sistema en el equipo local.  En la captura de pantalla siguiente se muestra un ejemplo de un comando azcopy:

![Upload archivos no Microsoft 365.](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Normalmente, el comando que se proporciona funciona cuando se ejecuta. Sin embargo, puede haber casos en los que el comando que se muestra no se ejecutará correctamente. Estas son algunas razones posibles.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>La versión compatible de AzCopy no está instalada en el equipo local.

En este momento, debe usar AzCopy v8.1 para cargar datos no Microsoft 365 en eDiscovery (Premium). El comando AzCopy que se muestra en la página **de archivos Upload** que se muestra en la captura de pantalla anterior devuelve un error si no usa AzCopy v8.1. Para instalar esta versión, consulte [Transferencia de datos con AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy no está instalado en el equipo local o no está instalado en la ubicación predeterminada.

Si AzCopy no está instalado o está instalado en una ubicación distinta de la ubicación de instalación predeterminada (que es `%ProgramFiles(x86)%`), puede recibir el siguiente error al ejecutar el comando AzCopy:

> El sistema no puede encontrar la ruta de acceso especificada.

Si AzCopy no está instalado en el equipo local, puede encontrar información de instalación en [Transferencia de datos con AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy). Asegúrese de instalarlo en la ubicación predeterminada.

Si AzCopy está instalado, pero está instalado en una ubicación diferente de la ubicación predeterminada, puede copiar el comando, pegarlo en un archivo de texto y, a continuación, cambiar la ruta de acceso a la ubicación donde está instalado AzCopy. Por ejemplo, si Azcopy se encuentra en `%ProgramFiles%`, puede cambiar la primera parte del comando de `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`. Después de realizar este cambio, cópielo desde el archivo de texto y, a continuación, ejecútelo en un símbolo del sistema.

> [!TIP]
> Si AzCopy está instalado en otra ubicación, la ubicación de instalación predeterminada, considere la posibilidad de desinstalarla y volver a instalarla en la ubicación predeterminada. Esto ayudará a evitar este problema en el futuro.