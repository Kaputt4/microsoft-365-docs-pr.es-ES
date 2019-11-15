---
title: Aumentó la seguridad de Microsoft 365 para su entorno de prueba empresarial de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del entorno de pruebas para habilitar la configuración adicional de seguridad de Microsoft 365 su entorno de prueba empresarial de Microsoft 365.
ms.openlocfilehash: f430acb4a7fd1842a4ae26025ad5a63cccf8392f
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640372"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1e76c-103">Aumentó la seguridad de Microsoft 365 para su entorno de prueba empresarial de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e76c-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1e76c-104">Con las instrucciones de este artículo, se configuran opciones adicionales de configuración de Microsoft 365 para aumentar la seguridad en el entorno de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1e76c-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1e76c-106">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1e76c-106">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1e76c-107">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e76c-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1e76c-108">Si solo quiere configurar la seguridad mejorada de Microsoft 365 de forma ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1e76c-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1e76c-109">Si desea configurar una seguridad mejorada de Microsoft 365 en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1e76c-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e76c-110">La prueba de la seguridad mejorada de Microsoft 365 no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1e76c-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1e76c-111">Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="1e76c-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="1e76c-112">Fase 2: configurar una mayor seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e76c-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="1e76c-113">En esta fase, se habilita una mayor seguridad de Microsoft 365 para su entorno de prueba empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e76c-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="1e76c-114">Para obtener más detalles y opciones de configuración, consulte [configurar el inquilino de Office 365 para aumentar la seguridad](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="1e76c-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="1e76c-115">Configurar SharePoint Online para bloquear aplicaciones que no son compatibles con la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="1e76c-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="1e76c-116">Las aplicaciones que no admiten la autenticación moderna no pueden tener aplicadas [configuraciones de identidad y acceso a dispositivos](microsoft-365-policies-configurations.md) , que es un elemento importante de la protección de la suscripción de Microsoft 365 y sus activos digitales.</span><span class="sxs-lookup"><span data-stu-id="1e76c-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="1e76c-117">Vaya al centro de administración de 365 de[https://portal.microsoft.com](https://portal.microsoft.com)Microsoft () e inicie sesión en su suscripción de laboratorio de pruebas de Office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1e76c-117">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="1e76c-118">Si usa el entorno de prueba ligero de Microsoft 365, inicie sesión desde el equipo local.</span><span class="sxs-lookup"><span data-stu-id="1e76c-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="1e76c-119">Si usa el entorno de prueba de Enterprise de Microsoft 365 simulado, use [Azure portal](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 y, a continuación, inicie sesión desde cliente1.</span><span class="sxs-lookup"><span data-stu-id="1e76c-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="1e76c-120">En la nueva pestaña **centro de administración de 365 de Microsoft** , haga clic en centros de **Administración > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-120">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
3. <span data-ttu-id="1e76c-121">En la nueva pestaña **centro de administración de SharePoint** , haga clic en control de **acceso**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-121">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="1e76c-122">En **aplicaciones que no admiten la autenticación moderna**, haga clic en **bloquear**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-122">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="1e76c-123">Habilitación de la protección contra amenazas avanzada para SharePoint, OneDrive para la empresa y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e76c-123">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="1e76c-124">Office 365 Advanced Threat Protection (ATP) para SharePoint, OneDrive y Microsoft Teams protege su organización de archivos malintencionados que se comparten de forma inadvertida.</span><span class="sxs-lookup"><span data-stu-id="1e76c-124">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="1e76c-125">Vaya al [centro de cumplimiento de & de seguridad de Office 365](https://protection.office.com) e inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="1e76c-125">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="1e76c-126">En el panel de navegación izquierdo, en **Administración de amenazas**, elija **Directiva > datos adjuntos seguros**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-126">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="1e76c-127">Seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-127">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="1e76c-128">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="1e76c-128">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="1e76c-129">Habilitar anti-malware</span><span class="sxs-lookup"><span data-stu-id="1e76c-129">Enable anti-malware</span></span>

<span data-ttu-id="1e76c-130">El malware se compone de virus y spyware.</span><span class="sxs-lookup"><span data-stu-id="1e76c-130">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="1e76c-131">Los virus infectan otros programas y datos, y se propagan en todo el equipo en busca de programas que infectar.</span><span class="sxs-lookup"><span data-stu-id="1e76c-131">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="1e76c-132">El spyware se refiere a malware que recopila información de carácter personal, como información de inicio de sesión y datos de carácter personal, y la envía al autor del malware.</span><span class="sxs-lookup"><span data-stu-id="1e76c-132">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="1e76c-133">Office 365 tiene capacidades integradas de filtrado de correo no deseado y malware que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y ayudan a protegerse del correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1e76c-133">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="1e76c-134">Para obtener más información, consulte [protección antimalware & contra el correo no deseado en Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="1e76c-134">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="1e76c-135">Para asegurarse de que el procesamiento antimalware se realice en archivos con tipos de archivos adjuntos comunes:</span><span class="sxs-lookup"><span data-stu-id="1e76c-135">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="1e76c-136">Haga clic en el botón atrás del explorador para volver a la página de la **Directiva** .</span><span class="sxs-lookup"><span data-stu-id="1e76c-136">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="1e76c-137">Haga clic en **anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-137">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="1e76c-138">Haga doble clic en la Directiva denominada **default**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-138">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="1e76c-139">En la ventana **Directiva contra malware** , haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-139">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="1e76c-140">En **filtro de tipos de datos adjuntos comunes**, haga clic **en > guardar**.</span><span class="sxs-lookup"><span data-stu-id="1e76c-140">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-the-threat-management-dashboard"></a><span data-ttu-id="1e76c-141">Fase 3: examinar el panel de administración de amenazas</span><span class="sxs-lookup"><span data-stu-id="1e76c-141">Phase 3: Examine the threat management dashboard</span></span>

<span data-ttu-id="1e76c-142">La administración de amenazas de Office 365 puede ayudarle a controlar y administrar el acceso de dispositivos móviles a los datos de su organización, a proteger su organización de la pérdida de datos y a proteger los mensajes entrantes y salientes del software malintencionado y el correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="1e76c-142">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="1e76c-143">También se usa la administración de amenazas para proteger la reputación del dominio y para determinar si los remitentes se falsifican de su dominio de una mala parte de las cuentas.</span><span class="sxs-lookup"><span data-stu-id="1e76c-143">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="1e76c-144">Para obtener más información, vea [Threat Management en el centro de seguridad de Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="1e76c-144">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="1e76c-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1e76c-145">Next steps</span></span>

<span data-ttu-id="1e76c-146">Consulte el paso [configurar mayor seguridad para Microsoft 365](infoprotect-configure-increased-security-office-365.md) en la fase de protección de la **información** para obtener información y vínculos para configurar estas opciones en producción.</span><span class="sxs-lookup"><span data-stu-id="1e76c-146">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="1e76c-147">Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="1e76c-147">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e76c-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e76c-148">See also</span></span>

[<span data-ttu-id="1e76c-149">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e76c-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1e76c-150">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e76c-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1e76c-151">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1e76c-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

