---
title: Menores de edad y adquisición de complementos de la Tienda
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Obtenga información sobre las regulaciones del Reglamento general de protección de datos (RGPD) que rigen los datos personales de los menores.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306556"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a><span data-ttu-id="ff650-103">Menores de edad y adquisición de complementos de la Tienda</span><span class="sxs-lookup"><span data-stu-id="ff650-103">Minors and acquiring add-ins from the Store</span></span>

<span data-ttu-id="ff650-104">El Reglamento general de protección de datos (RGPD) es un reglamento de la Unión Europea que se hace efectivo el 25 de mayo de 2018.</span><span class="sxs-lookup"><span data-stu-id="ff650-104">The General Data Protection Regulation (GDPR) is a European Union regulation that becomes effective May 25, 2018.</span></span> <span data-ttu-id="ff650-105">Concede a los usuarios derechos y protección de sus datos.</span><span class="sxs-lookup"><span data-stu-id="ff650-105">It gives users rights to and protection of their data.</span></span> <span data-ttu-id="ff650-106">Uno de los aspectos del RGPD es que los menores no pueden enviar sus datos personales a las partes que sus padres o tutores no han aprobado.</span><span class="sxs-lookup"><span data-stu-id="ff650-106">One of the aspects of the GDPR is that minors cannot have their personal data sent to parties that their parent or guardian hasn't approved.</span></span> <span data-ttu-id="ff650-107">La edad específica definida como menor depende de la región donde se encuentra la persona.</span><span class="sxs-lookup"><span data-stu-id="ff650-107">The specific age defined as a minor depends on the region where the individual is located.</span></span>
  
<span data-ttu-id="ff650-108">Las regiones que tienen normativas legales sobre el consentimiento parental incluyen Los Estados Unidos, Corea del Sur, Reino Unido y la Unión Europea.</span><span class="sxs-lookup"><span data-stu-id="ff650-108">Regions that have statutory regulations about parental consent include the United States, South Korea, the United Kingdom, and the European Union.</span></span> <span data-ttu-id="ff650-109">Para esas regiones, se bloqueará a un menor (a través de Azure Active Directory) para que no pueda obtener nuevos complementos de Office de la Tienda y ejecutar complementos que se adquirieron anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ff650-109">For those regions, a minor will be blocked (via Azure Active Directory) from getting any new Office add-ins from the Store and running add-ins that were previously acquired.</span></span> <span data-ttu-id="ff650-110">Para los países sin normativas legales, no habrá restricciones de descarga.</span><span class="sxs-lookup"><span data-stu-id="ff650-110">For countries without statutory regulations, there will be no download restrictions.</span></span>
  
<span data-ttu-id="ff650-111">Se determina que un usuario es un menor en función de los datos especificados en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff650-111">A user is determined to be a minor based on data specified in Azure Active Directory.</span></span> <span data-ttu-id="ff650-112">El administrador de la organización es responsable de declarar el grupo de edad legal y el consentimiento parental para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="ff650-112">The organization admin is responsible for declaring the legal age group and the parental consent for that user.</span></span>
  
<span data-ttu-id="ff650-113">Si el elemento primario/tutor da su consentimiento a un menor mediante un complemento específico, el administrador de la organización puede usar la implementación centralizada para implementar ese complemento para todos los menores que tengan consentimiento.</span><span class="sxs-lookup"><span data-stu-id="ff650-113">If the parent/guardian consents to a minor using a specific add-In, then the organization admin can use centralized deployment to deploy that add-In to all minors who have consent.</span></span>
  
<span data-ttu-id="ff650-114">Para cumplir con el RGPD para menores, debe asegurarse de que se implemente una de las siguientes compilaciones de Office en su escuela u organización.</span><span class="sxs-lookup"><span data-stu-id="ff650-114">To be GDPR compliant for minors you need to ensure that one of following builds of Office is deployed in your school/organization.</span></span>
 
 <span data-ttu-id="ff650-115">**Para Word, Excel, PowerPoint y Project:**</span><span class="sxs-lookup"><span data-stu-id="ff650-115">**For Word, Excel, PowerPoint, and Project**:</span></span> 

|<span data-ttu-id="ff650-116">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="ff650-116">**Platform**</span></span> <br/> |<span data-ttu-id="ff650-117">**Número de compilación**</span><span class="sxs-lookup"><span data-stu-id="ff650-117">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="ff650-118">Aplicaciones de Microsoft 365 para empresas (Canal actual)</span><span class="sxs-lookup"><span data-stu-id="ff650-118">Microsoft 365 Apps for enterprise (Current Channel)</span></span>  <br/> |<span data-ttu-id="ff650-119">9001.2138</span><span class="sxs-lookup"><span data-stu-id="ff650-119">9001.2138</span></span>   <br/> |
|<span data-ttu-id="ff650-120">Aplicaciones de Microsoft 365 para empresas (Canal empresarial semianual)</span><span class="sxs-lookup"><span data-stu-id="ff650-120">Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)</span></span>  <br/> |<span data-ttu-id="ff650-121">8431.2159</span><span class="sxs-lookup"><span data-stu-id="ff650-121">8431.2159</span></span>  <br/> |
|<span data-ttu-id="ff650-122">Office 2016 para Windows</span><span class="sxs-lookup"><span data-stu-id="ff650-122">Office 2016 for Windows</span></span>  <br/> |<span data-ttu-id="ff650-123">16.0.4672.1000</span><span class="sxs-lookup"><span data-stu-id="ff650-123">16.0.4672.1000</span></span>  <br/> |
|<span data-ttu-id="ff650-124">Office 2013 para Windows</span><span class="sxs-lookup"><span data-stu-id="ff650-124">Office 2013 for Windows</span></span>  <br/> |<span data-ttu-id="ff650-125">15.0.5023.1000</span><span class="sxs-lookup"><span data-stu-id="ff650-125">15.0.5023.1000</span></span>  <br/> |
|<span data-ttu-id="ff650-126">Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="ff650-126">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="ff650-127">16.11.18020200</span><span class="sxs-lookup"><span data-stu-id="ff650-127">16.11.18020200</span></span>  <br/> |
|<span data-ttu-id="ff650-128">Office para la web</span><span class="sxs-lookup"><span data-stu-id="ff650-128">Office for the web</span></span>  <br/> |<span data-ttu-id="ff650-129">N/D</span><span class="sxs-lookup"><span data-stu-id="ff650-129">N/A</span></span>  <br/> |
   
 <span data-ttu-id="ff650-130">**Para Outlook:**</span><span class="sxs-lookup"><span data-stu-id="ff650-130">**For Outlook**:</span></span> 
  
|<span data-ttu-id="ff650-131">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="ff650-131">**Platform**</span></span> <br/> |<span data-ttu-id="ff650-132">**Número de compilación**</span><span class="sxs-lookup"><span data-stu-id="ff650-132">**Build number**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="ff650-133">Outlook 2016 para Windows (MSI)</span><span class="sxs-lookup"><span data-stu-id="ff650-133">Outlook 2016 for Windows (MSI)</span></span>  <br/> |<span data-ttu-id="ff650-134">Compilación sin TBD</span><span class="sxs-lookup"><span data-stu-id="ff650-134">Build No TBD</span></span>  <br/> |
|<span data-ttu-id="ff650-135">Outlook 2016 para Windows (C2R)</span><span class="sxs-lookup"><span data-stu-id="ff650-135">Outlook 2016 for Windows (C2R)</span></span>  <br/> |<span data-ttu-id="ff650-136">16.0.9323.1000</span><span class="sxs-lookup"><span data-stu-id="ff650-136">16.0.9323.1000</span></span>  <br/> |
|<span data-ttu-id="ff650-137">Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="ff650-137">Office 2016 for Mac</span></span>  <br/> |<span data-ttu-id="ff650-138">16.0.9318.1000</span><span class="sxs-lookup"><span data-stu-id="ff650-138">16.0.9318.1000</span></span>  <br/> |
|<span data-ttu-id="ff650-139">Outlook Mobile para iOS</span><span class="sxs-lookup"><span data-stu-id="ff650-139">Outlook mobile for iOS</span></span>  <br/> |<span data-ttu-id="ff650-140">2.75.0</span><span class="sxs-lookup"><span data-stu-id="ff650-140">2.75.0</span></span>  <br/> |
|<span data-ttu-id="ff650-141">Outlook Mobile para Android</span><span class="sxs-lookup"><span data-stu-id="ff650-141">Outlook mobile for Android</span></span>  <br/> |<span data-ttu-id="ff650-142">2.2.145</span><span class="sxs-lookup"><span data-stu-id="ff650-142">2.2.145</span></span>  <br/> |
|<span data-ttu-id="ff650-143">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="ff650-143">Outlook.com</span></span>  <br/> |<span data-ttu-id="ff650-144">N/D</span><span class="sxs-lookup"><span data-stu-id="ff650-144">N/A</span></span>  <br/> |

 <span data-ttu-id="ff650-145">**Requisitos de Office 2013**</span><span class="sxs-lookup"><span data-stu-id="ff650-145">**Office 2013 requirements**</span></span>
  
<span data-ttu-id="ff650-146">Word, Excel y PowerPoint 2013 para Windows admitirán las mismas comprobaciones secundarias si la Biblioteca de autenticación de Active Directory (ADAL) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ff650-146">Word, Excel, and PowerPoint 2013 for Windows will support the same minors checks if Active Directory Authentication Library (ADAL) is enabled.</span></span> <span data-ttu-id="ff650-147">Hay dos opciones de cumplimiento, como se explica a continuación.</span><span class="sxs-lookup"><span data-stu-id="ff650-147">There are two options for compliance, as explained next.</span></span>
  
- <span data-ttu-id="ff650-148">**Habilitar ADAL**.</span><span class="sxs-lookup"><span data-stu-id="ff650-148">**Enable ADAL**.</span></span> <span data-ttu-id="ff650-149">En este artículo se explica cómo habilitar ADAL para Office 2013: Usar la autenticación moderna de [Microsoft 365 con clientes de Office.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="ff650-149">This article explains how to enable ADAL for Office 2013: [Using Microsoft 365 modern authentication with Office clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).</span></span><br/><span data-ttu-id="ff650-150">También debe establecer las claves del Registro para habilitar ADAL, como se explica en Habilitar la autenticación moderna para [Office 2013 en dispositivos Windows.](../security-and-compliance/enable-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="ff650-150">You also need to set the registry keys to enable ADAL as explained in [Enable Modern Authentication for Office 2013 on Windows devices](../security-and-compliance/enable-modern-authentication.md).</span></span><br/><span data-ttu-id="ff650-151">Además, debe instalar las siguientes actualizaciones de abril para Office 2013:</span><span class="sxs-lookup"><span data-stu-id="ff650-151">Additionally, you need to install the following April updates for Office 2013:</span></span>
    
  - [<span data-ttu-id="ff650-152">Descripción de la actualización de seguridad de Office 2013: 10 de abril de 2018</span><span class="sxs-lookup"><span data-stu-id="ff650-152">Description of the security update for Office 2013: April 10, 2018</span></span>](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [<span data-ttu-id="ff650-153">3 de abril de 2018, actualización de Office 2013 (KB4018333)</span><span class="sxs-lookup"><span data-stu-id="ff650-153">April 3, 2018, update for Office 2013 (KB4018333)</span></span>](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- <span data-ttu-id="ff650-154">**No habilite ADAL**.</span><span class="sxs-lookup"><span data-stu-id="ff650-154">**Don't enable ADAL**.</span></span> <span data-ttu-id="ff650-155">Si no puede habilitar ADAL en Office 2013, le recomendamos que use la directiva de grupo para desactivar la Tienda para los clientes de Office.</span><span class="sxs-lookup"><span data-stu-id="ff650-155">If you're unable to enable ADAL in Office 2013, then our recommendation is to use Group Policy to turn off the Store for the Office clients.</span></span> <span data-ttu-id="ff650-156">Aquí encontrará información sobre cómo desactivar la configuración de la aplicación para [Office.](https://technet.microsoft.com/library/cc178992.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff650-156">Information on how to turn off the app for Office settings is located [here](https://technet.microsoft.com/library/cc178992.aspx).</span></span>

## <a name="related-articles"></a><span data-ttu-id="ff650-157">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="ff650-157">Related articles</span></span>

[<span data-ttu-id="ff650-158">Implementar complementos en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="ff650-158">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[<span data-ttu-id="ff650-159">Administrar complementos en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="ff650-159">Manage add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
