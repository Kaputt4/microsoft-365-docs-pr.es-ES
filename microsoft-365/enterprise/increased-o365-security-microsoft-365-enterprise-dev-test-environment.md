---
title: Mayor seguridad de Office 365 para el entorno de pruebas de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de prueba para habilitar la configuración de seguridad adicionales de Office 365 su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871426"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="68b9b-103">Mayor seguridad de Office 365 para el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="68b9b-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="68b9b-104">Con las instrucciones de este artículo, configura opciones adicionales de Office 365 para aumentar la seguridad en su entorno de prueba de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="68b9b-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="68b9b-106">Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="68b9b-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="68b9b-107">Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="68b9b-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="68b9b-108">Si desea configurar la seguridad de Office 365 mayor en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="68b9b-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="68b9b-109">Si desea configurar una mayor seguridad de Office 365 en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="68b9b-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="68b9b-p101">Pruebas de mayor seguridad de Office 365 no requieren que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="68b9b-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="68b9b-112">Fase 2: Configuración de mayor seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="68b9b-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="68b9b-p102">En esta fase, se habilita una mayor seguridad de Office 365 para el entorno de prueba de Microsoft 365 Enterprise. Para obtener más información y la configuración, vea [Configure el inquilino de Office 365 para aumentar la seguridad](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="68b9b-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="68b9b-115">Configurar SharePoint Online para bloquear las aplicaciones que no admiten la autenticación moderna</span><span class="sxs-lookup"><span data-stu-id="68b9b-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="68b9b-116">Aplicaciones que no admiten la autenticación moderna no pueden tener una [identidad y dispositivo de acceso a las configuraciones de](microsoft-365-policies-configurations.md) aplica a ellos, que es un elemento importante de la seguridad de su suscripción de 365 de Microsoft y a sus activos digitales.</span><span class="sxs-lookup"><span data-stu-id="68b9b-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="68b9b-117">Vaya al portal de Office ([https://office.com](https://office.com)) e inicie sesión en su suscripción de prueba de Office 365 con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="68b9b-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="68b9b-118">Si está utilizando el entorno de prueba de Microsoft 365 ligero, inicie sesión desde el equipo local.</span><span class="sxs-lookup"><span data-stu-id="68b9b-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="68b9b-119">Si está utilizando el entorno de prueba de enterprise simulado 365 de Microsoft, use el [portal de Azure](https://portal.azure.com) para conectarse a la máquina virtual CLIENT1 y, a continuación, iniciar sesión en desde CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="68b9b-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="68b9b-120">En la ficha del **Centro de administración de Microsoft 365** , haga clic en **Admin**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="68b9b-121">En la ficha del **Centro de administración de Microsoft 365** nuevo, haga clic en **centros de administración > SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="68b9b-122">En la nueva ficha del **Centro de administración de SharePoint** , haga clic en **control de acceso**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="68b9b-123">En **aplicaciones que no admiten la autenticación moderna**, haga clic en **Bloquear**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="68b9b-124">Habilitar una protección avanzada) para SharePoint, OneDrive para la empresa y los equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="68b9b-124">Enable Advanced Threat Protection) for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="68b9b-p103">Protección de amenaza avanzada de Office 365 (ATP) es una característica de Exchange Online Protection (EOP) que ayuda a mantener el malware fuera de su correo electrónico. Con ATP, crear directivas en el centro de administración de Exchange (EAC) o la seguridad & Centro de cumplimiento que ayudan a garantizar a los usuarios obtener acceso sólo vínculos o datos adjuntos en mensajes de correo electrónico que se identifican como no malintencionado. Para obtener más información, consulte [protección contra amenazas avanzadas para los datos adjuntos seguros y vínculos seguros](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="68b9b-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange Admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="68b9b-128">En la ficha del **Centro de administración de Microsoft 365** del explorador, haga clic en **centros de administración > seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="68b9b-129">En la ficha nuevo de **seguridad y cumplimiento** , haga clic en **administración de amenazas > directiva**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="68b9b-130">Haga clic en **datos adjuntos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="68b9b-131">En el panel **datos adjuntos seguros** , seleccione **Activar ATP para SharePoint, OneDrive y los equipos de Microsoft**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="68b9b-132">Habilitar anti-malware</span><span class="sxs-lookup"><span data-stu-id="68b9b-132">Enable anti-malware</span></span>

<span data-ttu-id="68b9b-p104">Malware se compone de virus y spyware. Virus infectan otros programas y datos, y se propagan a lo largo de su equipo buscando programas a infectan. Spyware hace referencia al código malintencionado que recopila su información personal, como información de inicio de sesión y los datos personales y lo envía a su autor de malware.</span><span class="sxs-lookup"><span data-stu-id="68b9b-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="68b9b-p105">Office 365 tiene capacidades que ayudan a proteger los mensajes entrantes y salientes de software malintencionado y ayudar a protegerle contra correo no deseado de filtrado de spam y malware incorporadas. Para obtener más información, consulte [protección contra correo no deseado y antimalware en Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="68b9b-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="68b9b-138">Para asegurarse de que se lleva a cabo el procesamiento de anti-malware en archivos con tipos de archivo de datos adjuntos comunes:</span><span class="sxs-lookup"><span data-stu-id="68b9b-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="68b9b-139">Haga clic en el botón Atrás del explorador para volver a la página de **Directiva** .</span><span class="sxs-lookup"><span data-stu-id="68b9b-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="68b9b-140">Haga clic en **Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="68b9b-141">Haga doble clic en la directiva de llamada **predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="68b9b-142">En la ventana **Directiva de Anti-malware** , haga clic en **configuración**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="68b9b-143">En **el filtro de tipos comunes de los datos adjuntos**, haga clic en **en > Guardar**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="68b9b-144">Fase 3: Examinar los registros y las herramientas de seguridad de Office 365</span><span class="sxs-lookup"><span data-stu-id="68b9b-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="68b9b-145">En esta fase, examine los servicios integrados que informan acerca de los eventos de seguridad y medir su posición de seguridad general.</span><span class="sxs-lookup"><span data-stu-id="68b9b-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="68b9b-146">Panel de administración de amenaza</span><span class="sxs-lookup"><span data-stu-id="68b9b-146">Threat management dashboard</span></span>

<span data-ttu-id="68b9b-p106">Administración de Office 365 amenaza puede ayudarle a controlar y administrar el acceso de dispositivo móvil a los datos de la organización, ayudar a proteger su organización contra la pérdida de datos y ayudar a proteger los mensajes entrantes y salientes de correo no deseado y otro software malintencionado. También use cuentas de administración para proteger la reputación de su dominio y para determinar si los remitentes se suplantación de identidad malintencionada desde su dominio de amenaza. Para obtener más información, vea [administración de amenaza en el centro de cumplimiento y seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span><span class="sxs-lookup"><span data-stu-id="68b9b-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="68b9b-150">Siga estos pasos para ver el panel de administración de Office 365 amenaza:</span><span class="sxs-lookup"><span data-stu-id="68b9b-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="68b9b-151">En la ficha del **Centro de administración de Microsoft 365** del explorador, haga clic en **centros de administración > seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="68b9b-152">En la ficha nuevo de **seguridad y cumplimiento** , haga clic en **administración de amenazas > panel**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="68b9b-153">En la ficha de **panel de** nuevo en el explorador, tenga en cuenta las tendencias de malware, conocimientos y otras secciones del panel.</span><span class="sxs-lookup"><span data-stu-id="68b9b-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="68b9b-154">Panel de seguridad de la aplicación en la nube de Office 365</span><span class="sxs-lookup"><span data-stu-id="68b9b-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="68b9b-p107">Office 365 en la nube seguridad de la aplicación, anteriormente conocido como Office 365 administración avanzada de seguridad, le permite crear directivas que supervisión e informan de las actividades sospechosas en su suscripción de Office 365, para que pueda investigar y tomar posibles acción de corrección. Para obtener más información, vea [Información general de Office 365 en la nube seguridad de la aplicación](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span><span class="sxs-lookup"><span data-stu-id="68b9b-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="68b9b-157">En la ficha del **Centro de administración de Microsoft 365** del explorador, haga clic en **centros de administración > seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="68b9b-158">En la ficha nuevo de **seguridad y cumplimiento** , haga clic en **alertas > Administrar avanzada alertas > Ir a la seguridad de la aplicación de nube de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="68b9b-159">En la ficha **Seguridad de la aplicación en la nube** de nuevo, tenga en cuenta la vista de panel y la lista de directivas predeterminadas que supervisar diversas actividades en su suscripción de Office 365.</span><span class="sxs-lookup"><span data-stu-id="68b9b-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="68b9b-160">Haga clic en el icono de panel para ver un resumen de las actividades de seguridad de la aplicación en la nube que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="68b9b-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="68b9b-161">Haga clic en **investigar** (el icono de anteojos) y, a continuación, en **el registro de actividad** para ver la lista de inicios de sesión recientes y otras actividades.</span><span class="sxs-lookup"><span data-stu-id="68b9b-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="68b9b-162">Puntuación de seguro</span><span class="sxs-lookup"><span data-stu-id="68b9b-162">Secure Score</span></span>

1. <span data-ttu-id="68b9b-163">Crear una ficha nueva en el explorador y vaya a **securescore.office.com**.</span><span class="sxs-lookup"><span data-stu-id="68b9b-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="68b9b-164">En la **ficha de panel**, tenga en cuenta la puntuación seguro actual y la lista de acciones en la cola para aumentar la puntuación.</span><span class="sxs-lookup"><span data-stu-id="68b9b-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="68b9b-165">Vea el paso [Configure mayor seguridad para Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) en la fase de **protección de la información** para obtener información y vínculos para configurar estas opciones de configuración de producción.</span><span class="sxs-lookup"><span data-stu-id="68b9b-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="68b9b-166">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="68b9b-166">Next step</span></span>

<span data-ttu-id="68b9b-167">Explorar las características adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="68b9b-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="68b9b-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="68b9b-168">See also</span></span>

[<span data-ttu-id="68b9b-169">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="68b9b-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="68b9b-170">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="68b9b-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="68b9b-171">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="68b9b-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

