---
title: Mayor seguridad de Microsoft 365 para su entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta Guía del laboratorio de pruebas para habilitar la configuración de seguridad adicional de Microsoft 365 en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: d1bff8b736e5074f621a173d206f7c5f77841b25
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198356"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a3cb8-103">Mayor seguridad de Microsoft 365 para su entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a3cb8-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a3cb8-104">*Esta Guía del laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*</span><span class="sxs-lookup"><span data-stu-id="a3cb8-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a3cb8-105">Con las instrucciones de este artículo, se configuran configuraciones adicionales de Microsoft 365 para aumentar la seguridad en el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a3cb8-107">Haga clic [aquí](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a3cb8-108">Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a3cb8-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a3cb8-109">Si solo desea configurar una mayor seguridad de Microsoft 365 de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="a3cb8-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a3cb8-110">Si desea configurar una mayor seguridad de Microsoft 365 en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a3cb8-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3cb8-111">El aumento de la seguridad de Microsoft 365 no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a3cb8-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a3cb8-112">Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="a3cb8-113">Fase 2: Configurar mayor seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3cb8-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="a3cb8-114">En esta fase, se habilita una mayor seguridad de Microsoft 365 para el entorno de prueba de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="a3cb8-115">Para obtener más detalles y opciones de configuración, consulte [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="a3cb8-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="a3cb8-116">Configurar SharePoint Online para bloquear aplicaciones que no admiten la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="a3cb8-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="a3cb8-117">Las aplicaciones que no admiten la autenticación moderna no pueden tener configuraciones de identidad y acceso a [dispositivos aplicadas,](../security/office-365-security/microsoft-365-policies-configurations.md) lo que es un elemento importante para proteger la suscripción a Microsoft 365 y sus activos digitales.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="a3cb8-118">Vaya al Centro de administración de Microsoft 365 ( ) e inicie sesión en su suscripción al laboratorio de pruebas de [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="a3cb8-119">Si usa el entorno de prueba ligero de Microsoft 365, inicie sesión desde el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="a3cb8-120">Si usa el entorno de prueba de Microsoft 365 de empresa simulada, use [Azure Portal](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 y, a continuación, inicie sesión desde CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="a3cb8-121">En la nueva pestaña Centro de **administración de Microsoft 365,** en Centros de **administración** en el panel de navegación izquierdo, haga clic **en SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="a3cb8-122">En la nueva **pestaña Centro de administración de SharePoint,** haga clic en Directivas > control de **acceso**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="a3cb8-123">Haga **clic en Aplicaciones que no admiten la autenticación moderna,** seleccione Bloquear **acceso** y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="a3cb8-124">Habilitar Defender para Office 365 para SharePoint, OneDrive para la Empresa y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a3cb8-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="a3cb8-125">Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege su organización contra el uso compartido involuntario de archivos malintencionados.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="a3cb8-126">Vaya al [Centro de seguridad & cumplimiento e](https://protection.office.com) inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="a3cb8-127">En el panel de navegación izquierdo, en **Administración de** amenazas, haga clic en **Directiva** y, a continuación, haga clic en **Datos adjuntos seguros.**</span><span class="sxs-lookup"><span data-stu-id="a3cb8-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="a3cb8-128">En **Proteger archivos en SharePoint, OneDrive y Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="a3cb8-129">seleccione **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="a3cb8-130">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="a3cb8-131">Habilitar antimalware</span><span class="sxs-lookup"><span data-stu-id="a3cb8-131">Enable anti-malware</span></span>

<span data-ttu-id="a3cb8-132">El malware se compone de virus y spyware.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="a3cb8-133">Los virus infectan otros programas y datos, y se propagan en todo el equipo en busca de programas que infectar.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="a3cb8-134">El spyware se refiere a malware que recopila información de carácter personal, como información de inicio de sesión y datos de carácter personal, y la envía al autor del malware.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="a3cb8-135">Microsoft 365 tiene capacidades integradas de filtrado de correo no deseado y malware que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y le ayudan a protegerse del correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="a3cb8-136">Para obtener más información, vea [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="a3cb8-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="a3cb8-137">Para asegurarse de que el procesamiento antimalware se realiza en archivos con tipos de archivos adjuntos comunes:</span><span class="sxs-lookup"><span data-stu-id="a3cb8-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="a3cb8-138">Haga clic en el botón Atrás del explorador para volver a la **página** Directiva.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="a3cb8-139">Haga **clic en Antimalware**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="a3cb8-140">Haga doble clic en la directiva denominada **Default**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="a3cb8-141">En la ventana **Directiva antimalware,** haga clic en **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="a3cb8-142">En **Filtro de tipos comunes de datos adjuntos,** seleccione **Activar** y, a continuación, haga clic **en Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="a3cb8-143">Fase 3: Examinar el panel de seguridad</span><span class="sxs-lookup"><span data-stu-id="a3cb8-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="a3cb8-144">La administración de amenazas en Microsoft 365 puede ayudarle a controlar y administrar el acceso de dispositivos móviles a los datos de su organización, ayudar a proteger su organización de la pérdida de datos y ayudar a proteger los mensajes entrantes y salientes de software malintencionado y correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="a3cb8-145">También usa la administración de amenazas para proteger la reputación de su dominio y determinar si los remitentes suplanta de forma malintencionada cuentas de su dominio.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="a3cb8-146">Para ver el panel de seguridad:</span><span class="sxs-lookup"><span data-stu-id="a3cb8-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="a3cb8-147">Si es necesario, vaya al Centro de [seguridad & cumplimiento e](https://protection.office.com) inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="a3cb8-148">En el panel de navegación izquierdo, en **Administración de amenazas,** haga clic en **Panel**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="a3cb8-149">Echa un vistazo de cerca a todas las tarjetas del panel para familiarizarte con la información proporcionada.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="a3cb8-150">Para obtener más información, vea [Panel de seguridad](../security/office-365-security/security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="a3cb8-150">For more information, see [Security Dashboard](../security/office-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="a3cb8-151">Fase 4: Examinar la puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a3cb8-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="a3cb8-152">Puntuación segura de Microsoft muestra su posición de seguridad como un número, que indica el nivel actual con respecto a las características que están disponibles en su suscripción.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="a3cb8-153">También te ofrece una lista de acciones de mejora que puedes realizar para mejorar tu puntuación.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="a3cb8-154">Cree una nueva pestaña en el explorador, vaya al Centro de seguridad de [Microsoft 365](https://security.microsoft.com/)y, a continuación, haga clic **en Puntuación segura**.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="a3cb8-155">En la **pestaña Información**  general, anote su puntuación segura actual y cómo se compara con el promedio global y las suscripciones con un número similar de licencias.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="a3cb8-156">En la **pestaña Acciones de** mejora, lee la lista de acciones que puedes realizar para aumentar la puntuación.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="a3cb8-157">Para obtener más información, vea [Puntuación segura de Microsoft](../security/defender/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="a3cb8-157">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a3cb8-158">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="a3cb8-158">Next steps</span></span>

<span data-ttu-id="a3cb8-159">Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#information-protection) de protección de la información en el entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3cb8-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3cb8-160">See also</span></span>

[<span data-ttu-id="a3cb8-161">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a3cb8-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a3cb8-162">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a3cb8-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a3cb8-163">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a3cb8-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)