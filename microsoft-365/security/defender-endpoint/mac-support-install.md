---
title: Solucionar problemas de instalación de Microsoft Defender para Endpoint en Mac
description: Solucionar problemas de instalación en Microsoft Defender para Endpoint en Mac.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, instalar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5166de3a7c7017979a93ac7026636ba24671892e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935154"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solucionar problemas de instalación de Microsoft Defender para Endpoint en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Error en la instalación

Para la instalación manual, la página Resumen del asistente de instalación dice: "Se produjo un error durante la instalación. El instalador encontró un error que provocó un error en la instalación. Póngase en contacto con el fabricante del software para obtener ayuda." Para las implementaciones de MDM, también se muestra como un error de instalación genérica.

Aunque no se muestra un error exacto al usuario final, se mantiene un archivo de registro con el progreso de la instalación en `/Library/Logs/Microsoft/mdatp/install.log` . Cada sesión de instalación se anexa a este archivo de registro. Solo puede usar `sed` para generar la última sesión de instalación:

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

En este ejemplo, el motivo real tiene el prefijo `[ERROR]` .
Error en la instalación porque no se admite una degradación entre estas versiones.

## <a name="mdatp-install-log-missing-or-not-updated"></a>Falta o no se actualiza el registro de instalación de MDATP

En raras ocasiones, la instalación no deja ningún seguimiento en el archivo /Library/Logs/Microsoft/mdatp/install.log de MDATP.
Puedes comprobar que se ha producido una instalación y analizar posibles errores consultando registros de macOS (esto resulta útil en la implementación de MDM, cuando no hay ninguna interfaz de usuario de cliente). Se recomienda usar una ventana de tiempo limitado para ejecutar una consulta y filtrar por el nombre del proceso de registro, ya que habrá una gran cantidad de información.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
