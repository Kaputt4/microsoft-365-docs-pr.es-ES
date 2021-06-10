---
title: Configurar Azure Rights Management para la versión anterior del cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: La versión anterior de Cifrado de mensajes de Office 365 depende de Microsoft Azure Rights Management (anteriormente conocido como Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919496"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="c85cc-103">Configurar Azure Rights Management para la versión anterior del cifrado de mensajes</span><span class="sxs-lookup"><span data-stu-id="c85cc-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="c85cc-104">En este tema se describen los pasos que debe seguir para activar y, a continuación, configurar Azure Rights Management (RMS), parte de Azure Information Protection, para su uso con la versión anterior de Cifrado de mensajes de Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="c85cc-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="c85cc-105">Este artículo solo se aplica a la versión anterior de OME</span><span class="sxs-lookup"><span data-stu-id="c85cc-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="c85cc-106">Si aún no ha movido la organización a las nuevas funcionalidades de OME, pero ya ha implementado OME, la información de este artículo se aplica a su organización.</span><span class="sxs-lookup"><span data-stu-id="c85cc-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="c85cc-107">Microsoft recomienda realizar un plan para pasar a las nuevas funcionalidades de OME tan pronto como sea razonable para su organización.</span><span class="sxs-lookup"><span data-stu-id="c85cc-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="c85cc-108">Para obtener instrucciones, vea [Set up new Cifrado de mensajes de Office 365 capabilities](set-up-new-message-encryption-capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="c85cc-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="c85cc-109">Si desea obtener más información sobre cómo funcionan primero las nuevas funcionalidades, [vea Cifrado de mensajes de Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="c85cc-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="c85cc-110">El resto de este artículo hace referencia al comportamiento de OME antes del lanzamiento de las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="c85cc-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="c85cc-111">Requisitos previos para usar la versión anterior de Cifrado de mensajes de Office 365</span><span class="sxs-lookup"><span data-stu-id="c85cc-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="c85cc-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="c85cc-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="c85cc-113">Cifrado de mensajes de Office 365 (OME), incluido IRM, depende de Azure Rights Management (Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="c85cc-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="c85cc-114">Azure RMS es la tecnología de protección usada por Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="c85cc-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="c85cc-115">Para usar OME, la organización debe incluir una Exchange Online o una Exchange Online Protection que, a su vez, incluya una Azure Rights Management suscripción.</span><span class="sxs-lookup"><span data-stu-id="c85cc-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="c85cc-116">Si no está seguro de lo que incluye la suscripción, consulte las descripciones de Exchange Online de servicio de [Message Policy, Recovery y Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span><span class="sxs-lookup"><span data-stu-id="c85cc-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

- <span data-ttu-id="c85cc-117">Si tiene Azure Rights Management pero no está configurado para Exchange Online o Exchange Online Protection, en este artículo se explica cómo activar Azure Rights Management y, a continuación, se describe la mejor manera de configurar OME para que funcione con Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="c85cc-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="c85cc-118">Si ya ha configurado OME para que funcione con Azure Rights Management para Exchange Online o Exchange Online Protection, según cómo lo configure, puede que esté listo para empezar a usar OME y sus nuevas funcionalidades de inmediato.</span><span class="sxs-lookup"><span data-stu-id="c85cc-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="c85cc-119">En este artículo se explica cómo determinar si ha configurado OME correctamente, qué hacer si necesita cambiar la configuración y qué sucede si decide no cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="c85cc-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="c85cc-120">Por ejemplo, para usar las nuevas funcionalidades, debe usar Azure RMS con OME.</span><span class="sxs-lookup"><span data-stu-id="c85cc-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="c85cc-121">No puede usar las nuevas funcionalidades con un RMS de Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="c85cc-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="c85cc-122">Activar Azure Rights Management para la versión anterior de OME en Office 365</span><span class="sxs-lookup"><span data-stu-id="c85cc-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="c85cc-123">Debe activar Azure Rights Management para que los usuarios de la organización puedan aplicar protección de la información a los mensajes que envían y abrir mensajes y archivos protegidos por el servicio de Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="c85cc-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="c85cc-124">Para obtener instrucciones, vea [Activating Azure Rights Management](/azure/information-protection/activate-service).</span><span class="sxs-lookup"><span data-stu-id="c85cc-124">For instructions, see [Activating Azure Rights Management](/azure/information-protection/activate-service).</span></span> <span data-ttu-id="c85cc-125">Una vez completada la activación, vuelva aquí y continúe con las tareas de este artículo.</span><span class="sxs-lookup"><span data-stu-id="c85cc-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="c85cc-126">Configurar la versión anterior de OME para usar Azure RMS mediante la importación de dominios de publicación de confianza (TPD)</span><span class="sxs-lookup"><span data-stu-id="c85cc-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="c85cc-127">Un TPD es un archivo XML que contiene información sobre la configuración de administración de derechos de su organización.</span><span class="sxs-lookup"><span data-stu-id="c85cc-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="c85cc-128">Por ejemplo, el TPD contiene información sobre el certificado de licencia del servidor (SLC) usado para firmar y cifrar certificados y licencias, las direcciones URL usadas para licencias y publicación, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="c85cc-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="c85cc-129">El TPD se importa en la organización mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c85cc-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c85cc-130">Anteriormente, podía elegir importar los TPD del servicio de Administración de derechos de Active Directory (AD RMS) a su organización.</span><span class="sxs-lookup"><span data-stu-id="c85cc-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="c85cc-131">Sin embargo, esto le impedirá usar las nuevas funcionalidades de OME y no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="c85cc-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="c85cc-132">Si su organización está configurada actualmente de esta manera, Microsoft recomienda crear un plan para migrar desde el RMS de Active Directory local a Azure Information Protection basado en la nube.</span><span class="sxs-lookup"><span data-stu-id="c85cc-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="c85cc-133">Para obtener más información, [vea Migración de AD RMS a Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span><span class="sxs-lookup"><span data-stu-id="c85cc-133">For more information, see [Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="c85cc-134">No podrá usar las nuevas funcionalidades de OME hasta que haya completado la migración a Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="c85cc-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="c85cc-135">**Para importar TPD desde Azure RMS**</span><span class="sxs-lookup"><span data-stu-id="c85cc-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="c85cc-136">[Conectar para Exchange Online con PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c85cc-136">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="c85cc-137">Elija la dirección URL de uso compartido de claves que corresponda a la ubicación geográfica de su organización:</span><span class="sxs-lookup"><span data-stu-id="c85cc-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="c85cc-138">**Location**</span><span class="sxs-lookup"><span data-stu-id="c85cc-138">**Location**</span></span>|<span data-ttu-id="c85cc-139">**Url de ubicación de uso compartido de claves**</span><span class="sxs-lookup"><span data-stu-id="c85cc-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c85cc-140">Norteamérica</span><span class="sxs-lookup"><span data-stu-id="c85cc-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="c85cc-141">Unión Europea</span><span class="sxs-lookup"><span data-stu-id="c85cc-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="c85cc-142">Asia</span><span class="sxs-lookup"><span data-stu-id="c85cc-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="c85cc-143">Sudamérica</span><span class="sxs-lookup"><span data-stu-id="c85cc-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="c85cc-144">Office 365 Administración Pública (nube de la comunidad de administración pública)</span><span class="sxs-lookup"><span data-stu-id="c85cc-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="c85cc-145">Esta ubicación de uso compartido de claves de RMS está reservada para los clientes que han comprado Office 365 para SKU gubernamentales.</span><span class="sxs-lookup"><span data-stu-id="c85cc-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="c85cc-146">Configure la ubicación de uso compartido de claves ejecutando el cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c85cc-146">Configure the key-sharing location by running the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="c85cc-147">Por ejemplo, para configurar la ubicación de uso compartido de claves si su organización se encuentra en Norteamérica:</span><span class="sxs-lookup"><span data-stu-id="c85cc-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="c85cc-148">Ejecute el cmdlet [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) con el modificador -RMSOnline para importar el TPD desde Azure Rights Management:</span><span class="sxs-lookup"><span data-stu-id="c85cc-148">Run the [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="c85cc-149">Donde  *TPDName*  es el nombre que desea usar para el TPD.</span><span class="sxs-lookup"><span data-stu-id="c85cc-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="c85cc-150">Por ejemplo, "Contoso North American TPD".</span><span class="sxs-lookup"><span data-stu-id="c85cc-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="c85cc-151">Para comprobar que la organización configuró correctamente el servicio Azure Rights Management, ejecute el cmdlet [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) con el modificador -RMSOnline de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c85cc-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="c85cc-152">Entre otras cosas, este cmdlet comprueba la conectividad con el servicio Azure Rights Management, descarga el TPD y comprueba su validez.</span><span class="sxs-lookup"><span data-stu-id="c85cc-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="c85cc-153">Ejecute el cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) de la siguiente manera para deshabilitar que las plantillas Azure Rights Management estén disponibles en Outlook web y Outlook:</span><span class="sxs-lookup"><span data-stu-id="c85cc-153">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="c85cc-154">Ejecute el cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) de la siguiente manera para habilitar Azure Rights Management para la organización de correo electrónico basada en la nube y configurarlo para que use Azure Rights Management para Cifrado de mensajes de Office 365:</span><span class="sxs-lookup"><span data-stu-id="c85cc-154">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="c85cc-155">Para comprobar que ha importado correctamente el TPD y ha Azure Rights Management, use el cmdlet Test-IRMConfiguration para probar Azure Rights Management funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="c85cc-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="c85cc-156">Para obtener más información, vea "Ejemplo 1" en [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span><span class="sxs-lookup"><span data-stu-id="c85cc-156">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="c85cc-157">Tengo la versión anterior de OME configurada con Active Directory Rights Management no con Azure Information Protection, ¿qué debo hacer?</span><span class="sxs-lookup"><span data-stu-id="c85cc-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="c85cc-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="c85cc-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="c85cc-159">Puede seguir usando las reglas de flujo de correo Cifrado de mensajes de Office 365 existentes con Active Directory Rights Management, pero no puede configurar ni usar las nuevas funcionalidades de OME.</span><span class="sxs-lookup"><span data-stu-id="c85cc-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="c85cc-160">En su lugar, debe migrar a Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="c85cc-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="c85cc-161">Para obtener información sobre la migración y lo que esto significa para su organización, vea Migración de [AD RMS a Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span><span class="sxs-lookup"><span data-stu-id="c85cc-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c85cc-162">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c85cc-162">Next steps</span></span>
<span data-ttu-id="c85cc-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="c85cc-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="c85cc-164">Una vez que haya completado Azure Rights Management configuración, si desea habilitar las nuevas funcionalidades de OME, consulte Configurar nuevas funcionalidades de Cifrado de mensajes de Office 365 integradas en [Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="c85cc-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span></span>
  
<span data-ttu-id="c85cc-165">Después de configurar la organización para que use las nuevas funcionalidades de OME, estará listo para definir reglas de flujo de correo para proteger los mensajes de correo electrónico con nuevas [funcionalidades de OME.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="c85cc-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c85cc-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c85cc-166">Related topics</span></span>
<span data-ttu-id="c85cc-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="c85cc-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="c85cc-168">Cifrado en Office 365</span><span class="sxs-lookup"><span data-stu-id="c85cc-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="c85cc-169">Información de referencia técnica sobre el cifrado en Office 365</span><span class="sxs-lookup"><span data-stu-id="c85cc-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="c85cc-170">¿Qué es Azure Rights Management?</span><span class="sxs-lookup"><span data-stu-id="c85cc-170">What is Azure Rights Management?</span></span>](/information-protection/understand-explore/what-is-azure-rms)