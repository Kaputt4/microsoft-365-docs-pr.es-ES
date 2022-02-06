---
title: Reglas de aplicación y prueba
description: Reglas que se deben seguir al cargar una aplicación/prueba
search.appverid: MET150
author: andreicsibi-msft
ms.author: ancsibi
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: null
ms.reviewer: mapatel
f1.keywords: NOCSH
---
# <a name="applicationtest-rules"></a>Reglas de aplicación y prueba

Todas las aplicaciones o pruebas de Test Base deben cumplir las siguientes reglas:

## <a name="test-base-folders"></a>Carpetas base de prueba 

La infraestructura base de prueba usa las siguientes carpetas:
* %SYSTEMDRIVE%\USL
* %SYSTEMDRIVE%\EtlExport
* %SYSTEMDRIVE%\Ffmpeg
* %SYSTEMDRIVE%\Monitoring
* %SYSTEMDRIVE%\powershell-yaml
* %SYSTEMDRIVE%\ProcMon
* %SYSTEMDRIVE%\PSTools
* %SYSTEMDRIVE%\TokenProviderTool
* %SYSTEMDRIVE%\USLPowershellModules
* %SYSTEMDRIVE%\UtcUtil
* %SYSTEMDRIVE%\WPT
* %SYSTEMDRIVE%\WULogs

> [!IMPORTANT]
> **Evite lo siguiente**:
> * Bloquear la ejecución de cualquier proceso de estas carpetas. Si la aplicación es un software antimalware, configure la instalación de la aplicación para permitir la ejecución sin intervención de todos los procesos de estas carpetas.
> * Manipulación de cualquiera de estas carpetas.

## <a name="test-base-registry-keys"></a>Claves del Registro base de prueba

Las aplicaciones/pruebas no deben eliminar ni modificar ninguna clave del Registro relacionada con:
* Windows de telemetría
* Eliminación de TLS 1.2
