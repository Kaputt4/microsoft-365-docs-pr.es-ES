---
title: Solucionar problemas de AzCopy en eDiscovery avanzada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Solucionar errores de Azure AzCopy al cargar datos que no son de Office 365 para la corrección de errores en eDiscovery avanzada.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919296"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Solucionar problemas de AzCopy en eDiscovery avanzada

Al cargar datos o documentos que no sean de Microsoft 365 para la corrección de errores en eDiscovery avanzada, la interfaz de usuario proporciona un comando de Azure AzCopy que contiene parámetros con la ubicación de dónde se almacenan los archivos que desea cargar y la ubicación de almacenamiento de Azure en la que se cargarán los archivos. Para cargar los documentos, copie este comando y, a continuación, ejecutarlo en un símbolo del sistema en el equipo local.  La captura de pantalla siguiente muestra un ejemplo de un comando AzCopy:

![Cargar archivos que no son de Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Normalmente, el comando que se proporciona funciona al ejecutarlo. Sin embargo, puede haber casos en los que el comando que se muestra no se ejecutará correctamente. Estos son algunos motivos posibles.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>La versión compatible de AzCopy no está instalada en el equipo local

En este momento, debe usar AzCopy v8.1 para cargar datos que no son de Microsoft 365 en eDiscovery avanzada. El comando AzCopy que se  muestra en la página Cargar archivos que se muestra en la captura de pantalla anterior devuelve un error si no usa AzCopy v8.1. Para instalar esta versión, consulta [Transferir datos con AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy no está instalado en el equipo local o no está instalado en la ubicación predeterminada

Si AzCopy no está instalado o está instalado en una ubicación que no sea la ubicación de instalación predeterminada (que es ), puede recibir el siguiente error al ejecutar el comando `%ProgramFiles(x86)%` AzCopy:

> El sistema no puede encontrar la ruta de acceso especificada.

Si AzCopy no está instalado en el equipo local, encontrará información de instalación en Transferir datos con [AzCopy v8.1 en Windows](/previous-versions/azure/storage/storage-use-azcopy). Asegúrese de instalarlo en la ubicación predeterminada.

Si AzCopy está instalado, pero está instalado en una ubicación diferente a la ubicación predeterminada, puede copiar el comando, pegarlo en un archivo de texto y, a continuación, cambiar la ruta de acceso a la ubicación donde está instalado AzCopy. Por ejemplo, si Azcopy se encuentra en , puede cambiar la primera parte `%ProgramFiles%` del comando de a `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . Después de realizar este cambio, cópielo desde el archivo de texto y, a continuación, ejecute un símbolo del sistema.

> [!TIP]
> Si AzCopy está instalado en otra ubicación, la ubicación de instalación predeterminada, considere la posibilidad de desinstalarla y, a continuación, volver a instalarla en la ubicación predeterminada. Esto ayudará a evitar este problema en el futuro.