---
title: Recopilar datos de diagnóstico para actualizar el cumplimiento y Windows Defender Antivirus de Microsoft Defender
description: Usar una herramienta para recopilar datos para solucionar problemas de cumplimiento de actualizaciones al usar el complemento evaluación antivirus de Microsoft Defender
keywords: troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f2b3060d7f0d9daf0f923c674f2fe45ba976fdfc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764740"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="cb0cb-104">Recopilar datos de diagnóstico de cumplimiento de actualizaciones para la evaluación antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cb0cb-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cb0cb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cb0cb-105">**Applies to:**</span></span>

- [<span data-ttu-id="cb0cb-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="cb0cb-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cb0cb-107">En este artículo se describe cómo recopilar datos de diagnóstico que pueden usar los equipos de soporte técnico e ingeniería de Microsoft para ayudar a solucionar problemas que se pueden encontrar al usar la sección Evaluación de antivirus de Microsoft Defender en el complemento Actualizar cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="cb0cb-108">Antes de intentar este proceso, asegúrese de que ha leído Solucionar problemas de informes de Antivirus de [Microsoft Defender,](troubleshoot-reporting.md)cumple todos los requisitos previos y ha realizado otros pasos de solución de problemas sugeridos.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="cb0cb-109">En al menos dos dispositivos que no se informen o se muestren en Update Compliance, obtenga el archivo de diagnóstico .cab siguiendo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb0cb-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="cb0cb-110">Abra una versión de nivel de administrador del símbolo del sistema de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="cb0cb-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="cb0cb-111">a.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-111">a.</span></span> <span data-ttu-id="cb0cb-112">Abra el **menú** Inicio.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="cb0cb-113">b.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-113">b.</span></span> <span data-ttu-id="cb0cb-114">Escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-114">Type **cmd**.</span></span> <span data-ttu-id="cb0cb-115">Haga clic con el botón secundario en **el símbolo del sistema** y haga clic en Ejecutar como **administrador.**</span><span class="sxs-lookup"><span data-stu-id="cb0cb-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="cb0cb-116">c.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-116">c.</span></span> <span data-ttu-id="cb0cb-117">Escriba las credenciales de administrador o apruebe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="cb0cb-118">Navegue hasta el Windows Defender directorio.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="cb0cb-119">El valor predeterminado es `C:\Program Files\Windows Defender`</span><span class="sxs-lookup"><span data-stu-id="cb0cb-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="cb0cb-120">Escriba el siguiente comando y, a continuación, presione **ENTRAR**</span><span class="sxs-lookup"><span data-stu-id="cb0cb-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="cb0cb-121">Se generará un archivo .cab que contenga varios registros de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="cb0cb-122">La ubicación del archivo se especificará en la salida del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="cb0cb-123">De forma predeterminada, la ubicación es `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="cb0cb-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="cb0cb-124">Copie estos archivos .cab en una ubicación a la que pueda tener acceso el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="cb0cb-125">Un ejemplo podría ser una carpeta de OneDrive protegida con contraseña que puede compartir con nosotros.</span><span class="sxs-lookup"><span data-stu-id="cb0cb-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="cb0cb-126">Envíe un correo electrónico con la <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">plantilla de</a>correo electrónico de compatibilidad de actualización y rellene la plantilla con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="cb0cb-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="cb0cb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb0cb-127">See also</span></span>

- [<span data-ttu-id="cb0cb-128">Solucionar Windows Defender informes de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="cb0cb-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)