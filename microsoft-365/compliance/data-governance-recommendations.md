---
title: Cómo se identifica el contenido para las recomendaciones de gobierno de datos
ms.author: brendonb
author: laurawi
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: El Centro de seguridad y cumplimiento de Office 365 ofrece recomendaciones para el gobierno de datos según la configuración actual de su organización y le permite realizar configuraciones con un par de clics. Algunas de estas recomendaciones detectan el contenido específico de su organización y, luego, proporcionan pasos recomendados para administrarlo. Por ejemplo, una recomendación puede detectar los elementos que contienen contenido crítico para la empresa (como privilegios abogado-cliente o información NDA) y hacer que pueda aplicar automáticamente una etiqueta de retención a dichos elementos para asegurarse de que están clasificados y se conservan según sea necesario. En este tema se enumeran las recomendaciones de gobierno de datos que puede ver y se describe el contenido que se detecta para desencadenar cada uno.
ms.openlocfilehash: e860a41b616be2265904775a63454aba1a6040c1
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "38708232"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="52c38-106">Cómo se identifica el contenido para las recomendaciones de gobierno de datos</span><span class="sxs-lookup"><span data-stu-id="52c38-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="52c38-p102">El Centro de seguridad y cumplimiento de Office 365 ofrece recomendaciones para el gobierno de datos según la configuración actual de su organización y le permite realizar configuraciones con un par de clics. Algunas de estas recomendaciones detectan el contenido específico de su organización y, luego, proporcionan pasos recomendados para administrarlo. Por ejemplo, una recomendación puede detectar los elementos que contienen contenido crítico para la empresa (como privilegios abogado-cliente o información NDA) y hacer que pueda aplicar automáticamente una etiqueta de retención a dichos elementos para asegurarse de que están clasificados y se conservan según sea necesario. </span><span class="sxs-lookup"><span data-stu-id="52c38-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="52c38-110">En este tema se enumeran las recomendaciones de gobierno de datos que es posible que vea y se describe el contenido que se detecte para desencadenar cada uno.</span><span class="sxs-lookup"><span data-stu-id="52c38-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="52c38-111">Limpiar el correo de voz</span><span class="sxs-lookup"><span data-stu-id="52c38-111">Clean up voicemail</span></span>

<span data-ttu-id="52c38-p103">Esta recomendación aparece cuando se detectan mensajes de correo identificados como tipo de mensaje "correo de voz" en los buzones de usuarios. Obtenga más información sobre las [propiedades de mensajes en Exchange](https://docs.microsoft.com/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="52c38-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="52c38-114">Etiquetar contenido de privilegios abogado-cliente </span><span class="sxs-lookup"><span data-stu-id="52c38-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="52c38-115">Esta recomendación aparece cuando se cumple uno de los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="52c38-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="52c38-116">Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="52c38-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="52c38-117">ACP</span><span class="sxs-lookup"><span data-stu-id="52c38-117">ACP</span></span>
    - <span data-ttu-id="52c38-118">Privilegio de abogado cliente</span><span class="sxs-lookup"><span data-stu-id="52c38-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="52c38-119">Privilegio de abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="52c38-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="52c38-120">Confidencialidad abogado-cliente</span><span class="sxs-lookup"><span data-stu-id="52c38-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="52c38-121">Cualquier combinación de estas palabras clave se detectan en archivos de SharePoint o OneDrive:</span><span class="sxs-lookup"><span data-stu-id="52c38-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="52c38-122">ACP</span><span class="sxs-lookup"><span data-stu-id="52c38-122">ACP</span></span>
    - <span data-ttu-id="52c38-123">Privilegio de abogado cliente\*</span><span class="sxs-lookup"><span data-stu-id="52c38-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="52c38-124">Privilegio AC</span><span class="sxs-lookup"><span data-stu-id="52c38-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="52c38-125">Conservar archivos de audio</span><span class="sxs-lookup"><span data-stu-id="52c38-125">Retain audio files</span></span>

<span data-ttu-id="52c38-126">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="52c38-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="52c38-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="52c38-127">.MP3</span></span>
- <span data-ttu-id="52c38-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="52c38-128">.WMA</span></span>
- <span data-ttu-id="52c38-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="52c38-129">.WAV</span></span>
- <span data-ttu-id="52c38-130">.RA</span><span class="sxs-lookup"><span data-stu-id="52c38-130">.RA</span></span>
- <span data-ttu-id="52c38-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="52c38-131">.RAM</span></span>
- <span data-ttu-id="52c38-132">.RM</span><span class="sxs-lookup"><span data-stu-id="52c38-132">.RM</span></span>
- <span data-ttu-id="52c38-133">.MID</span><span class="sxs-lookup"><span data-stu-id="52c38-133">.MID</span></span>
- <span data-ttu-id="52c38-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="52c38-134">.OGG</span></span>
- <span data-ttu-id="52c38-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="52c38-135">.AIFF</span></span>
- <span data-ttu-id="52c38-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="52c38-136">.PCM</span></span>
- <span data-ttu-id="52c38-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="52c38-137">.AAC</span></span>
- <span data-ttu-id="52c38-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="52c38-138">.FLAC</span></span>
- <span data-ttu-id="52c38-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="52c38-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="52c38-140">Conservar archivos CAD</span><span class="sxs-lookup"><span data-stu-id="52c38-140">Retain CAD files</span></span>

<span data-ttu-id="52c38-141">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="52c38-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="52c38-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="52c38-142">.3DXML</span></span>
- <span data-ttu-id="52c38-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="52c38-143">.ACIS</span></span>
- <span data-ttu-id="52c38-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="52c38-144">.ARC</span></span>
- <span data-ttu-id="52c38-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="52c38-145">.ASM</span></span>
- <span data-ttu-id="52c38-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="52c38-146">.CAT\*</span></span>
- <span data-ttu-id="52c38-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="52c38-147">.CGR</span></span>
- <span data-ttu-id="52c38-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="52c38-148">.DW\*</span></span>
- <span data-ttu-id="52c38-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="52c38-149">.DX\*</span></span>
- <span data-ttu-id="52c38-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="52c38-150">.EDRW</span></span>
- <span data-ttu-id="52c38-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="52c38-151">.IAM</span></span>
- <span data-ttu-id="52c38-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="52c38-152">.IGES</span></span>
- <span data-ttu-id="52c38-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="52c38-153">.IGS</span></span>
- <span data-ttu-id="52c38-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="52c38-154">.IPT</span></span>
- <span data-ttu-id="52c38-155">.JT</span><span class="sxs-lookup"><span data-stu-id="52c38-155">.JT</span></span>
- <span data-ttu-id="52c38-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="52c38-156">.MF1</span></span>
- <span data-ttu-id="52c38-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="52c38-157">.NEU</span></span>
- <span data-ttu-id="52c38-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="52c38-158">.PAR</span></span>
- <span data-ttu-id="52c38-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="52c38-159">.PKG</span></span>
- <span data-ttu-id="52c38-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="52c38-160">.PRC</span></span>
- <span data-ttu-id="52c38-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="52c38-161">.PRT</span></span>
- <span data-ttu-id="52c38-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="52c38-162">.PSM</span></span>
- <span data-ttu-id="52c38-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="52c38-163">.PWD</span></span>
- <span data-ttu-id="52c38-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="52c38-164">.SLD\*</span></span>
- <span data-ttu-id="52c38-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="52c38-165">.STEP</span></span>
- <span data-ttu-id="52c38-166">.STL</span><span class="sxs-lookup"><span data-stu-id="52c38-166">.STL</span></span>
- <span data-ttu-id="52c38-167">.STP</span><span class="sxs-lookup"><span data-stu-id="52c38-167">.STP</span></span>
- <span data-ttu-id="52c38-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="52c38-168">.U3D</span></span>
- <span data-ttu-id="52c38-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="52c38-169">.UNV</span></span>
- <span data-ttu-id="52c38-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="52c38-170">.VRML</span></span>
- <span data-ttu-id="52c38-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="52c38-171">.WRL</span></span>
- <span data-ttu-id="52c38-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="52c38-172">.X_\*</span></span>
- <span data-ttu-id="52c38-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="52c38-173">.XAS</span></span>
- <span data-ttu-id="52c38-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="52c38-174">.XMT\*</span></span>
- <span data-ttu-id="52c38-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="52c38-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="52c38-176">Conservar archivos de imagen</span><span class="sxs-lookup"><span data-stu-id="52c38-176">Retain image files</span></span>

<span data-ttu-id="52c38-177">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="52c38-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="52c38-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="52c38-178">.JPEG</span></span>
- <span data-ttu-id="52c38-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="52c38-179">.GIF</span></span>
- <span data-ttu-id="52c38-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="52c38-180">.TIF\*</span></span>
- <span data-ttu-id="52c38-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="52c38-181">.BMP</span></span>
- <span data-ttu-id="52c38-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="52c38-182">.PNG</span></span>
- <span data-ttu-id="52c38-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="52c38-183">.RAW</span></span>
- <span data-ttu-id="52c38-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="52c38-184">.PSD</span></span>
- <span data-ttu-id="52c38-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="52c38-185">.PSP</span></span>
- <span data-ttu-id="52c38-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="52c38-186">.JPG</span></span>
- <span data-ttu-id="52c38-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="52c38-187">.EXIF</span></span>
- <span data-ttu-id="52c38-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="52c38-188">.PPM</span></span>
- <span data-ttu-id="52c38-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="52c38-189">.PGM</span></span>
- <span data-ttu-id="52c38-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="52c38-190">.PBM</span></span>
- <span data-ttu-id="52c38-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="52c38-191">.PNM</span></span>
- <span data-ttu-id="52c38-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="52c38-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="52c38-193">Conservar contenido NDA</span><span class="sxs-lookup"><span data-stu-id="52c38-193">Retain NDA content</span></span> 

<span data-ttu-id="52c38-194">Esta recomendación aparece cuando se cumple uno de los siguientes criterios.</span><span class="sxs-lookup"><span data-stu-id="52c38-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="52c38-195">Cualquier combinación de estas palabras clave se detecta en el cuerpo de un mensaje de correo electrónico:</span><span class="sxs-lookup"><span data-stu-id="52c38-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="52c38-196">NDA</span><span class="sxs-lookup"><span data-stu-id="52c38-196">NDA</span></span>
    - <span data-ttu-id="52c38-197">“Acuerdo de confidencialidad”</span><span class="sxs-lookup"><span data-stu-id="52c38-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="52c38-198">“Acuerdo de confidencialidad”</span><span class="sxs-lookup"><span data-stu-id="52c38-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="52c38-199">Cualquier combinación de estas palabras clave se detectan en archivos .PDF o .DOC en SharePoint o OneDrive:</span><span class="sxs-lookup"><span data-stu-id="52c38-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="52c38-200">NDA</span><span class="sxs-lookup"><span data-stu-id="52c38-200">NDA</span></span>
    - <span data-ttu-id="52c38-201">Acuerdo de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="52c38-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="52c38-202">Conservar archivos de desarrollo de software </span><span class="sxs-lookup"><span data-stu-id="52c38-202">Retain software development files</span></span>

<span data-ttu-id="52c38-203">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="52c38-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="52c38-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="52c38-204">.ASAX</span></span>
- <span data-ttu-id="52c38-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="52c38-205">.ASM</span></span>
- <span data-ttu-id="52c38-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="52c38-206">.ASP\*</span></span>
- <span data-ttu-id="52c38-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="52c38-207">.BAT</span></span>
- <span data-ttu-id="52c38-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="52c38-208">.CONFIG</span></span>
- <span data-ttu-id="52c38-209">.CS</span><span class="sxs-lookup"><span data-stu-id="52c38-209">.CS</span></span>
- <span data-ttu-id="52c38-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="52c38-210">.CSS</span></span>
- <span data-ttu-id="52c38-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="52c38-211">.DISCO</span></span>
- <span data-ttu-id="52c38-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="52c38-212">.HTM\*</span></span>
- <span data-ttu-id="52c38-213">.INC</span><span class="sxs-lookup"><span data-stu-id="52c38-213">.INC</span></span>
- <span data-ttu-id="52c38-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="52c38-214">.JAD</span></span>
- <span data-ttu-id="52c38-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="52c38-215">.JAVA</span></span>
- <span data-ttu-id="52c38-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="52c38-216">.JS\*</span></span>
- <span data-ttu-id="52c38-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="52c38-217">.LIB</span></span>
- <span data-ttu-id="52c38-218">.O</span><span class="sxs-lookup"><span data-stu-id="52c38-218">.O</span></span>
- <span data-ttu-id="52c38-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="52c38-219">.PHP</span></span>
- <span data-ttu-id="52c38-220">.RC</span><span class="sxs-lookup"><span data-stu-id="52c38-220">.RC</span></span>
- <span data-ttu-id="52c38-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="52c38-221">.RESX</span></span>
- <span data-ttu-id="52c38-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="52c38-222">.RPT</span></span>
- <span data-ttu-id="52c38-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="52c38-223">.RSS</span></span>
- <span data-ttu-id="52c38-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="52c38-224">.SCPT</span></span>
- <span data-ttu-id="52c38-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="52c38-225">.SRC</span></span>
- <span data-ttu-id="52c38-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="52c38-226">.VB\*</span></span>
- <span data-ttu-id="52c38-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="52c38-227">.WSF</span></span>
- <span data-ttu-id="52c38-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="52c38-228">.XCODEPROJ</span></span>
- <span data-ttu-id="52c38-229">.XML</span><span class="sxs-lookup"><span data-stu-id="52c38-229">.XML</span></span>
- <span data-ttu-id="52c38-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="52c38-230">.XSD</span></span>
- <span data-ttu-id="52c38-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="52c38-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="52c38-232">Conservar archivos de vídeo</span><span class="sxs-lookup"><span data-stu-id="52c38-232">Retain video files</span></span>

<span data-ttu-id="52c38-233">Esta recomendación aparece cuando se detecta cualquiera de los siguientes tipos de archivo en SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="52c38-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="52c38-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="52c38-234">.AVCHD</span></span>
- <span data-ttu-id="52c38-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="52c38-235">.AVI</span></span>
- <span data-ttu-id="52c38-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="52c38-236">.FLV</span></span>
- <span data-ttu-id="52c38-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="52c38-237">.MOV</span></span>
- <span data-ttu-id="52c38-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="52c38-238">.MP2V</span></span>
- <span data-ttu-id="52c38-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="52c38-239">.MP4</span></span>
- <span data-ttu-id="52c38-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="52c38-240">.MP4V</span></span>
- <span data-ttu-id="52c38-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="52c38-241">.MPE</span></span>
- <span data-ttu-id="52c38-242">MPEG</span><span class="sxs-lookup"><span data-stu-id="52c38-242">.MPEG</span></span>
- <span data-ttu-id="52c38-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="52c38-243">.MPEG1</span></span>
- <span data-ttu-id="52c38-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="52c38-244">.MPEG2</span></span>
- <span data-ttu-id="52c38-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="52c38-245">.MPEG4</span></span>
- <span data-ttu-id="52c38-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="52c38-246">.MPG</span></span>
- <span data-ttu-id="52c38-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="52c38-247">.MPG2</span></span>
- <span data-ttu-id="52c38-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="52c38-248">.MPG4</span></span>
- <span data-ttu-id="52c38-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="52c38-249">.WMV</span></span>
- <span data-ttu-id="52c38-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="52c38-250">.XMV</span></span>
