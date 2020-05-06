---
title: RGPD de uso compartido de archivos local
description: Aprenda a cumplir con los requisitos de la Reglamento general de protección de datos (GDPR) en los archivos compartidos de Windows Server.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e9d45c86b2838acef9966b10806e589d1bb42ff9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036253"
---
# <a name="gdpr-for-on-premises-windows-server-file-shares"></a><span data-ttu-id="e4ef0-103">RGPD para uso compartido de archivos de Windows Server local.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-103">GDPR for on-premises Windows Server file shares</span></span>

<span data-ttu-id="e4ef0-104">El método recomendado básico para el uso compartido de archivos es:</span><span class="sxs-lookup"><span data-stu-id="e4ef0-104">The basic recommended approach for file shares is:</span></span>

-   <span data-ttu-id="e4ef0-105">Use Azure Information Protection para etiquetar los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-105">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="e4ef0-106">Use el escáner de Azure Information Protection para buscar datos.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-106">Use Azure Information Protection scanner to find data.</span></span>

<span data-ttu-id="e4ef0-107">El enfoque recomendado para el uso compartido de archivos incluye estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e4ef0-107">The recommended approach for files shares includes these steps:</span></span>

1.  <span data-ttu-id="e4ef0-108">**Instale y configure el escáner de Azure Information Protection.**</span><span class="sxs-lookup"><span data-stu-id="e4ef0-108">**Install and configure Azure Information Protection scanner.**</span></span>

    -   <span data-ttu-id="e4ef0-109">Decida qué tipos de datos confidenciales quiere usar.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-109">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="e4ef0-110">Especifique las carpetas locales y los recursos compartidos de red que se van a usar.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-110">Specify local folders and network shares to use.</span></span>

2.  <span data-ttu-id="e4ef0-111">**Complete un ciclo de detección.**</span><span class="sxs-lookup"><span data-stu-id="e4ef0-111">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="e4ef0-112">Ejecute el escáner en el modo de detección y valide los resultados.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-112">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="e4ef0-113">Si es necesario, optimice las condiciones y los tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-113">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="e4ef0-114">Evalúe el impacto esperado de aplicar etiquetas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-114">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="e4ef0-115">**Ejecute el analizador de Azure Information Protection para aplicar etiquetas a los documentos necesarios**.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-115">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="e4ef0-116">**Para obtener protección:**</span><span class="sxs-lookup"><span data-stu-id="e4ef0-116">**For protection:**</span></span>

    -   <span data-ttu-id="e4ef0-117">Configure las reglas de prevención de pérdida de datos de Exchange para proteger los documentos con la etiqueta que desee.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-117">Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    -   <span data-ttu-id="e4ef0-118">Asegúrese de usar permisos para limitar quién puede obtener acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-118">Be sure to use permissions to limit who can access files.</span></span>

5.  <span data-ttu-id="e4ef0-119">**Para supervisar, integre los registros de Windows Server con una herramienta SIEM.**</span><span class="sxs-lookup"><span data-stu-id="e4ef0-119">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    -   <span data-ttu-id="e4ef0-p101">Para buscar datos personales para solicitudes de datos personales, utilice el escáner de Azure Information Protection. También puede configurar la búsqueda de SharePoint Server para rastrear el uso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-p101">To find personal data for data subject requests, use Azure Information Protection scanner. You can also configure SharePoint Server search to crawl file shares.</span></span>

<span data-ttu-id="e4ef0-122">Para obtener más información sobre cómo usar el escáner de Azure Information Protection para buscar y etiquetar datos personales, vea el Kit de herramientas de detección de datos de RGPD de Microsoft en [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>).</span><span class="sxs-lookup"><span data-stu-id="e4ef0-122">For more information on using Azure Information Protection scanner to find and label personal data, see the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>).</span></span>

<span data-ttu-id="e4ef0-p102">Para obtener información sobre cómo configurar el escáner para buscar condiciones y usar los tipos de información confidencial prevención de pérdida de datos (DLP) de Office 365, consulte [Configuración de las condiciones para la clasificación automática y recomendada en Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Tenga en cuenta que los nuevos tipos de información confidencial de Office 365 no estarán disponibles inmediatamente para su uso con el escáner y que los tipos de información confidencial personalizados no pueden usarse con este.</span><span class="sxs-lookup"><span data-stu-id="e4ef0-p102">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>
