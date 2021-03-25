---
title: Solucionar problemas de instalación de ATP de Microsoft Defender para Mac
description: Solucionar problemas de instalación en ATP de Microsoft Defender para Mac.
keywords: microsoft, defender, atp, mac, install
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
ms.openlocfilehash: 888bffdb85adeb7af58504439c1c31c7232cd73b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187630"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="96fef-104">Solucionar problemas de instalación de Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="96fef-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="96fef-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="96fef-105">**Applies to:**</span></span>

- [<span data-ttu-id="96fef-106">Microsoft Defender para endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="96fef-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="96fef-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="96fef-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="96fef-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96fef-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="96fef-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="96fef-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="96fef-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="96fef-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="96fef-111">Error en la instalación</span><span class="sxs-lookup"><span data-stu-id="96fef-111">Installation failed</span></span>

<span data-ttu-id="96fef-112">Para la instalación manual, la página Resumen del asistente de instalación dice: "Se produjo un error durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="96fef-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="96fef-113">El instalador encontró un error que provocó un error en la instalación.</span><span class="sxs-lookup"><span data-stu-id="96fef-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="96fef-114">Póngase en contacto con el fabricante del software para obtener ayuda."</span><span class="sxs-lookup"><span data-stu-id="96fef-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="96fef-115">Para las implementaciones de MDM, también se muestra como un error de instalación genérica.</span><span class="sxs-lookup"><span data-stu-id="96fef-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="96fef-116">Aunque no se muestra un error exacto al usuario final, se mantiene un archivo de registro con el progreso de la instalación en `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="96fef-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="96fef-117">Cada sesión de instalación se anexa a este archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="96fef-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="96fef-118">Solo puede usar `sed` para generar la última sesión de instalación:</span><span class="sxs-lookup"><span data-stu-id="96fef-118">You can use `sed` to output the last installation session only:</span></span>

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

<span data-ttu-id="96fef-119">En este ejemplo, el motivo real tiene el prefijo `[ERROR]` .</span><span class="sxs-lookup"><span data-stu-id="96fef-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="96fef-120">Error en la instalación porque no se admite una degradación entre estas versiones.</span><span class="sxs-lookup"><span data-stu-id="96fef-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="96fef-121">Falta o no se actualiza el registro de instalación de MDATP</span><span class="sxs-lookup"><span data-stu-id="96fef-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="96fef-122">En raras ocasiones, la instalación no deja ningún seguimiento en el archivo /Library/Logs/Microsoft/mdatp/install.log de MDATP.</span><span class="sxs-lookup"><span data-stu-id="96fef-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="96fef-123">Puedes comprobar que se ha producido una instalación y analizar posibles errores consultando registros de macOS (esto resulta útil en la implementación de MDM, cuando no hay ninguna interfaz de usuario de cliente).</span><span class="sxs-lookup"><span data-stu-id="96fef-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="96fef-124">Se recomienda usar una ventana de tiempo limitado para ejecutar una consulta y filtrar por el nombre del proceso de registro, ya que habrá una gran cantidad de información.</span><span class="sxs-lookup"><span data-stu-id="96fef-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
