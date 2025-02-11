---
title: Solución de problemas de instalación de Microsoft Defender para punto de conexión en Mac
description: Solución de problemas de instalación en Microsoft Defender para punto de conexión en Mac.
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mac, install, catalina, big sur, monterey, ventura, mde for mac
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 1ac3f82c713673a236816a5279e0e5cb772cfbff
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68769156"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solución de problemas de instalación de Microsoft Defender para punto de conexión en macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión en macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Error de instalación

Para la instalación manual, en la página Resumen del asistente para la instalación se indica: "Se produjo un error durante la instalación. El instalador encontró un error que provocó un error en la instalación. Póngase en contacto con el editor de software para obtener ayuda." En el caso de las implementaciones de MDM, también se muestra como un error de instalación genérico.

Aunque no se muestra un error exacto al usuario final, conservamos un archivo de registro con el progreso de la instalación en `/Library/Logs/Microsoft/mdatp/install.log`. Cada sesión de instalación se anexa a este archivo de registro. Solo puede usar para generar `sed` la última sesión de instalación:

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

En este ejemplo, el motivo real tiene el `[ERROR]`prefijo .
Error en la instalación porque no se admite una degradación entre estas versiones.

## <a name="mdatp-install-log-missing-or-not-updated"></a>Falta o no se actualiza el registro de instalación de MDATP

En raras ocasiones, la instalación no deja ningún seguimiento en el archivo /Library/Logs/Microsoft/mdatp/install.log de MDATP.
En primer lugar, compruebe que se ha producido una instalación. A continuación, analice los posibles errores consultando los registros de macOS. Es útil hacerlo en las implementaciones de MDM, cuando no hay ninguna interfaz de usuario de cliente. Se recomienda usar un período de tiempo reducido para ejecutar una consulta y filtrar por el nombre del proceso de registro, ya que habrá una gran cantidad de información.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
