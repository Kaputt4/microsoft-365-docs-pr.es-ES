---
title: Reglas de aplicación o prueba
description: Reglas que se deben seguir al cargar una aplicación o prueba
search.appverid: MET150
author: andreicsibi-msft
ms.author: ancsibi
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: 6a3878e0326fdcfe1ea9d35997e6a605457fcbf7
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316498"
---
# <a name="applicationtest-rules"></a>Reglas de aplicación o prueba

Todas las aplicaciones o pruebas de Test Base deben cumplir las reglas siguientes:

## <a name="test-base-folders"></a>Carpetas base de prueba 

La infraestructura base de pruebas usa las siguientes carpetas:
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
> * Bloquear la ejecución de cualquier proceso desde estas carpetas. Si la aplicación es software antimalware, configure la instalación de la aplicación para permitir la ejecución sin obstáculos de todos los procesos de estas carpetas.
> * Manipulación de cualquiera de estas carpetas.

## <a name="test-base-registry-keys"></a>Probar claves del Registro base

Las aplicaciones o pruebas no deben eliminar ni modificar ninguna clave del Registro relacionada con:
* Nivel de telemetría de Windows
* Eliminación de TLS 1.2
