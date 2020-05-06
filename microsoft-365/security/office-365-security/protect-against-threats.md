---
title: Protección contra amenazas
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Obtenga información sobre la protección contra amenazas de Office 365 y cómo usarla para su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bdc7d619f3c48318572116fbc52647a0858ec5e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033895"
---
# <a name="protect-against-threats"></a><span data-ttu-id="b9513-103">Protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="b9513-103">Protect against threats</span></span>

<span data-ttu-id="b9513-104">Microsoft 365 incluye una variedad de características de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="b9513-104">Microsoft 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="b9513-105">Esta es una guía de inicio rápido que puede usar como una lista de comprobación para asegurarse de que las características de protección contra amenazas se configuran para su organización.</span><span class="sxs-lookup"><span data-stu-id="b9513-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="b9513-106">Si no está familiarizado con las características de protección contra amenazas de Office 365 o no está seguro de dónde empezar, use las siguientes instrucciones como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="b9513-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9513-107">**Se incluye la configuración recomendada inicial para cada tipo de directiva; sin embargo, hay muchas opciones disponibles y puede ajustar la configuración para satisfacer las necesidades específicas de su organización**.</span><span class="sxs-lookup"><span data-stu-id="b9513-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="b9513-108">Espere unos 30 minutos para que las directivas o los cambios funcionen a través del centro de proceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b9513-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9513-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9513-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="b9513-110">Suscripciones</span><span class="sxs-lookup"><span data-stu-id="b9513-110">Subscriptions</span></span>

<span data-ttu-id="b9513-111">Las características de protección contra amenazas se incluyen en todas las suscripciones de Microsoft 365; sin embargo, algunas suscripciones incluyen características más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="b9513-111">Threat protection features are included in all Microsoft 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="b9513-112">En la siguiente tabla se enumeran las características de protección que se incluyen en este artículo junto con los requisitos mínimos de suscripción.</span><span class="sxs-lookup"><span data-stu-id="b9513-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|||
|---|---|
|<span data-ttu-id="b9513-113">**Tipo de protección**</span><span class="sxs-lookup"><span data-stu-id="b9513-113">**Protection type**</span></span>|<span data-ttu-id="b9513-114">**Requisito de suscripción**</span><span class="sxs-lookup"><span data-stu-id="b9513-114">**Subscription requirement**</span></span>|
|<span data-ttu-id="b9513-115">Protección antimalware</span><span class="sxs-lookup"><span data-stu-id="b9513-115">Anti-malware protection</span></span>|<span data-ttu-id="b9513-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span><span class="sxs-lookup"><span data-stu-id="b9513-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>|
|<span data-ttu-id="b9513-117">Protección frente a direcciones URL y archivos malintencionados en correo electrónico y documentos de Office</span><span class="sxs-lookup"><span data-stu-id="b9513-117">Protection from malicious URLs and files in email and Office documents</span></span>|<span data-ttu-id="b9513-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span><span class="sxs-lookup"><span data-stu-id="b9513-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>|
|<span data-ttu-id="b9513-119">Protección contra phishing</span><span class="sxs-lookup"><span data-stu-id="b9513-119">Anti-phishing protection</span></span>|[<span data-ttu-id="b9513-120">EOP</span><span class="sxs-lookup"><span data-stu-id="b9513-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="b9513-121">Protección contra suplantación de identidad avanzada</span><span class="sxs-lookup"><span data-stu-id="b9513-121">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="b9513-122">ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="b9513-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="b9513-123">Protección contra correo no deseado</span><span class="sxs-lookup"><span data-stu-id="b9513-123">Anti-spam protection</span></span>|[<span data-ttu-id="b9513-124">EOP</span><span class="sxs-lookup"><span data-stu-id="b9513-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="b9513-125">Purgado automático de cero horas (para correo electrónico)</span><span class="sxs-lookup"><span data-stu-id="b9513-125">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="b9513-126">EOP</span><span class="sxs-lookup"><span data-stu-id="b9513-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|<span data-ttu-id="b9513-127">Registro de auditoría (se usa con fines de informes)</span><span class="sxs-lookup"><span data-stu-id="b9513-127">Audit logging (this is used for reporting purposes)</span></span>|[<span data-ttu-id="b9513-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b9513-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a><span data-ttu-id="b9513-129">Roles y permisos</span><span class="sxs-lookup"><span data-stu-id="b9513-129">Roles and permissions</span></span>

<span data-ttu-id="b9513-130">Debe tener asignado un rol apropiado para configurar directivas en el [centro de seguridad & cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="b9513-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="b9513-131">En la tabla siguiente se ofrecen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="b9513-131">The following table includes some examples:</span></span>

|<span data-ttu-id="b9513-132">Rol o grupo de roles</span><span class="sxs-lookup"><span data-stu-id="b9513-132">Role or role group</span></span>|<span data-ttu-id="b9513-133">Dónde obtener más información</span><span class="sxs-lookup"><span data-stu-id="b9513-133">Where to learn more</span></span>|
|---------|---------|
|<span data-ttu-id="b9513-134">administrador global</span><span class="sxs-lookup"><span data-stu-id="b9513-134">global administrator</span></span>|[<span data-ttu-id="b9513-135">Acerca de los roles de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b9513-135">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="b9513-136">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="b9513-136">Security Administrator</span></span>|[<span data-ttu-id="b9513-137">Permisos de roles de administrador en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b9513-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="b9513-138">Administración de la organización en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b9513-138">Exchange Online Organization Management</span></span>|[<span data-ttu-id="b9513-139">Permisos de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b9513-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="b9513-140">y</span><span class="sxs-lookup"><span data-stu-id="b9513-140">and</span></span><br> [<span data-ttu-id="b9513-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9513-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

<span data-ttu-id="b9513-142">Para obtener más información, consulte [permisos en el &amp; centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-142">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="b9513-143">Parte 1: protección contra malware</span><span class="sxs-lookup"><span data-stu-id="b9513-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="b9513-144">La [protección contra malware](anti-malware-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="b9513-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="b9513-145">En el [centro de seguridad & cumplimiento](https://protection.office.com), elija**Directiva** > de **Administración** > de amenazas**contra malware**.</span><span class="sxs-lookup"><span data-stu-id="b9513-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="b9513-146">Haga doble clic en la directiva **predeterminada** y, a continuación, elija **configuración**.</span><span class="sxs-lookup"><span data-stu-id="b9513-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="b9513-147">Especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="b9513-147">Specify the following settings:</span></span>

    - <span data-ttu-id="b9513-148">En la sección **respuesta de detección de malware** , mantenga el valor predeterminado de **no**.</span><span class="sxs-lookup"><span data-stu-id="b9513-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="b9513-149">En la sección **filtro de tipos de datos adjuntos comunes** , elija **activado**.</span><span class="sxs-lookup"><span data-stu-id="b9513-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="b9513-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-150">Click **Save**.</span></span>

<span data-ttu-id="b9513-151">Para obtener más información acerca de las opciones de directiva antimalware, vea [Configure anti-malware Policies](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="b9513-152">Parte 2: protección frente a direcciones URL y archivos malintencionados</span><span class="sxs-lookup"><span data-stu-id="b9513-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="b9513-153">La protección del tiempo de clic de los archivos y las direcciones URL malintencionadas está disponible en las suscripciones que incluyen [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) y se configuran mediante las directivas de [datos adjuntos seguros de ATP](atp-safe-attachments.md) y [vínculos seguros ATP](atp-safe-links.md) .</span><span class="sxs-lookup"><span data-stu-id="b9513-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="b9513-154">Directivas de datos adjuntos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="b9513-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="b9513-155">Para configurar los [datos adjuntos seguros de ATP](atp-safe-attachments.md), debe definir al menos una directiva de datos adjuntos seguros ATP.</span><span class="sxs-lookup"><span data-stu-id="b9513-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="b9513-156">En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione**Directiva** > de **Administración** > de amenazas:**datos adjuntos seguros ATP**.</span><span class="sxs-lookup"><span data-stu-id="b9513-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="b9513-157">Seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="b9513-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="b9513-158">En la sección **proteger archivos adjuntos de correo electrónico** , haga**+** clic en el signo más ().</span><span class="sxs-lookup"><span data-stu-id="b9513-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="b9513-159">Especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="b9513-159">Specify the following settings:</span></span>

   - <span data-ttu-id="b9513-160">En el cuadro **nombre** , escriba `Block malware`.</span><span class="sxs-lookup"><span data-stu-id="b9513-160">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="b9513-161">En la sección respuesta, elija **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="b9513-161">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="b9513-162">En la sección **redirigir datos adjuntos** , seleccione la opción **Habilitar redireccionamiento**y, a continuación, especifique la dirección de correo electrónico del administrador o operador de seguridad de la organización que va a revisar los archivos detectados.</span><span class="sxs-lookup"><span data-stu-id="b9513-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

   - <span data-ttu-id="b9513-163">En la sección **aplicado a** , elija **el dominio del destinatario es**.</span><span class="sxs-lookup"><span data-stu-id="b9513-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="b9513-164">A continuación, seleccione el dominio, elija **Agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="b9513-165">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-165">Click **Save**.</span></span>

6. <span data-ttu-id="b9513-166">(**Paso adicional recomendado**) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con el parámetro **DisallowInfectedFileDownload** establecido en *true* para su entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9513-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="b9513-167">(Esto impide que los usuarios abran, muevan, copien o compartan archivos que se detectan como malintencionados.)</span><span class="sxs-lookup"><span data-stu-id="b9513-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="b9513-168">Para obtener más información, consulte [configurar las directivas de datos adjuntos seguros de office 365 ATP](set-up-atp-safe-attachments-policies.md) y [activar Office 365 ATP para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="b9513-169">Directivas de vínculos seguros de ATP</span><span class="sxs-lookup"><span data-stu-id="b9513-169">ATP Safe Links policies</span></span>

<span data-ttu-id="b9513-170">Para configurar [vínculos seguros ATP](atp-safe-links.md), revise y edite su directiva predeterminada y agregue una directiva para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="b9513-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="b9513-171">En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione**Directiva** > de **Administración** > de amenazas de**ATP Safe links**.</span><span class="sxs-lookup"><span data-stu-id="b9513-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b9513-172">Haga doble clic en la directiva **predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="b9513-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="b9513-173">En la sección **usar vínculos seguros en** , seleccione la opción **Microsoft 365 apps for Enterprise, Office para iOS y Android**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-173">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="b9513-174">En la sección **directivas que se aplican a destinatarios específicos** , haga clic en**+** el signo más ().</span><span class="sxs-lookup"><span data-stu-id="b9513-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="b9513-175">Especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="b9513-175">Specify the following settings:</span></span>

   - <span data-ttu-id="b9513-176">En el cuadro **nombre** , escriba un nombre, como `Safe Links`.</span><span class="sxs-lookup"><span data-stu-id="b9513-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="b9513-177">En la sección **seleccionar la acción** , elija **activado**.</span><span class="sxs-lookup"><span data-stu-id="b9513-177">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="b9513-178">Seleccione estas opciones:</span><span class="sxs-lookup"><span data-stu-id="b9513-178">Select these options:</span></span>

     - <span data-ttu-id="b9513-179">**Usar datos adjuntos seguros para analizar contenido descargable**</span><span class="sxs-lookup"><span data-stu-id="b9513-179">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="b9513-180">**Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**</span><span class="sxs-lookup"><span data-stu-id="b9513-180">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="b9513-181">**No permitir que los usuarios hagan clic en los vínculos seguros a la dirección URL original**</span><span class="sxs-lookup"><span data-stu-id="b9513-181">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="b9513-182">En la sección **aplicado a** , elija **el dominio del destinatario es**.</span><span class="sxs-lookup"><span data-stu-id="b9513-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="b9513-183">A continuación, seleccione el dominio, elija **Agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="b9513-184">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-184">Click **Save**.</span></span>

<span data-ttu-id="b9513-185">Para obtener más información, consulte [Configurar directivas de vínculos seguros de ATP de Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="b9513-186">Parte 3: protección contra la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="b9513-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="b9513-187">[Anti-phishing]</span><span class="sxs-lookup"><span data-stu-id="b9513-187">[Anti-phishing]</span></span>

<span data-ttu-id="b9513-188">[La protección contra suplantación de identidad (phishing)](anti-phishing-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="b9513-188">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="b9513-189">La protección contra suplantación de identidad avanzada está disponible en [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="b9513-189">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="b9513-190">El siguiente procedimiento describe cómo configurar una directiva contra la suplantación de identidad ATP.</span><span class="sxs-lookup"><span data-stu-id="b9513-190">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="b9513-191">Los pasos son similares a la configuración de una directiva contra la suplantación de identidad (sin ATP).</span><span class="sxs-lookup"><span data-stu-id="b9513-191">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="b9513-192">En el [centro de seguridad & cumplimiento](https://protection.office.com), elija la**Directiva** > de **Administración** > de amenazas**ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b9513-192">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b9513-193">Haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="b9513-193">Click **Default policy**.</span></span>

3. <span data-ttu-id="b9513-194">En la sección **suplantación** , haga clic en **Editar**y, a continuación, especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="b9513-194">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="b9513-195">En la pestaña **Agregar usuarios a proteger** , desactive la protección.</span><span class="sxs-lookup"><span data-stu-id="b9513-195">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="b9513-196">A continuación, agregue usuarios, como los miembros del Consejo de su organización, su CEO, director financiero y otros líderes senior.</span><span class="sxs-lookup"><span data-stu-id="b9513-196">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="b9513-197">(Puede escribir una dirección de correo electrónico individual o hacer clic en para mostrar una lista).</span><span class="sxs-lookup"><span data-stu-id="b9513-197">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="b9513-198">En la pestaña **Agregar dominios para proteger** , Active **incluir automáticamente los dominios que posea**.</span><span class="sxs-lookup"><span data-stu-id="b9513-198">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="b9513-199">Si tiene dominios personalizados, agréguelos también.</span><span class="sxs-lookup"><span data-stu-id="b9513-199">If you have custom domains, add those as well.</span></span>

   - <span data-ttu-id="b9513-200">En la ficha **acciones** , seleccione **poner en cuarentena el mensaje** para las opciones **usuario** suplantado y **dominio suplantado** .</span><span class="sxs-lookup"><span data-stu-id="b9513-200">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="b9513-201">Además, active las sugerencias de seguridad de suplantación.</span><span class="sxs-lookup"><span data-stu-id="b9513-201">In addition, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="b9513-202">En la pestaña **inteligencia de buzones de correo** , asegúrese de que la inteligencia de buzones está activada.</span><span class="sxs-lookup"><span data-stu-id="b9513-202">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span> <span data-ttu-id="b9513-203">Además, active la protección de suplantación basada en la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="b9513-203">In addition, turn on mailbox intelligence based impersonation protection.</span></span> <span data-ttu-id="b9513-204">En la lista **si el correo electrónico se envía por un usuario suplantado** , elija **poner en cuarentena el mensaje**.</span><span class="sxs-lookup"><span data-stu-id="b9513-204">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="b9513-205">En la ficha **Agregar remitentes y dominios** de confianza, especifique los remitentes o dominios de confianza que desee agregar.</span><span class="sxs-lookup"><span data-stu-id="b9513-205">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="b9513-206">En la pestaña **revisar la configuración** , una vez que haya revisado la configuración, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-206">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="b9513-207">En la sección **suplantación** , haga clic en **Editar**y, a continuación, especifique las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="b9513-207">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="b9513-208">En la pestaña **configuración de filtro de suplantación de identidad** , asegúrese de que está activada la protección contra la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="b9513-208">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="b9513-209">En la ficha **acciones** , elija **poner en cuarentena el mensaje**.</span><span class="sxs-lookup"><span data-stu-id="b9513-209">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="b9513-210">En la pestaña **revisar la configuración** , una vez que haya revisado la configuración, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-210">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="b9513-211">(Si no realizó ningún cambio, haga clic en **Cancelar**).</span><span class="sxs-lookup"><span data-stu-id="b9513-211">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="b9513-212">Cierre la página Configuración de directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b9513-212">Close the default policy settings page.</span></span>

<span data-ttu-id="b9513-213">Para obtener más información sobre las opciones de la Directiva antiphishing, consulte [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-213">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="b9513-214">Parte 4: protección contra correo no deseado</span><span class="sxs-lookup"><span data-stu-id="b9513-214">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="b9513-215">[La protección contra correo no deseado](anti-spam-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="b9513-215">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="b9513-216">En el [centro de seguridad & cumplimiento](https://protection.office.com), elija**anti-spam**de la**Directiva** > de **Administración** > de amenazas.</span><span class="sxs-lookup"><span data-stu-id="b9513-216">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="b9513-217">En la ficha **personalizado** , active la **Configuración personalizada** .</span><span class="sxs-lookup"><span data-stu-id="b9513-217">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="b9513-218">Expanda **directiva predeterminada de filtro de correo no deseado**, haga clic en **Editar Directiva**y especifique la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="b9513-218">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="b9513-219">En la sección **correo electrónico no deseado y acciones en masa** , establezca el umbral en un valor de 5 o 6.</span><span class="sxs-lookup"><span data-stu-id="b9513-219">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="b9513-220">En la sección **listas de permitidos** , revise (y, si es necesario, Edit) los remitentes y dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="b9513-220">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="b9513-221">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b9513-221">Click **Save**.</span></span>

<span data-ttu-id="b9513-222">Para obtener más información sobre las opciones de la Directiva contra correo no deseado, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-222">To learn more about your anti-spam policy options, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="b9513-223">Parte 5: configuración adicional para configurar</span><span class="sxs-lookup"><span data-stu-id="b9513-223">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="b9513-224">Además de configurar la protección contra malware, archivos y direcciones URL malintencionadas, suplantación de identidad (phishing) y correo no deseado, le recomendamos que configure las opciones de configuración de registro de auditoría y de purga automática de cero horas.</span><span class="sxs-lookup"><span data-stu-id="b9513-224">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="b9513-225">Purgado automático de cero horas para correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b9513-225">Zero-hour auto purge for email</span></span>

<span data-ttu-id="b9513-226">[La purga automática de cero horas](zero-hour-auto-purge.md) (ZAP) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="b9513-226">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="b9513-227">Esta protección está activada de forma predeterminada; sin embargo, deben cumplirse las siguientes condiciones para que la protección esté en vigor:</span><span class="sxs-lookup"><span data-stu-id="b9513-227">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="b9513-228">Las acciones de correo no deseado se establecen para **mover el mensaje a la carpeta correo no deseado** en [las directivas contra correo no deseado](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-228">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="b9513-229">Los usuarios han mantenido su [configuración](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)predeterminada de correo no deseado y no han desactivado la protección contra correo electrónico no deseado.</span><span class="sxs-lookup"><span data-stu-id="b9513-229">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="b9513-230">Para obtener más información, consulte [depuración automática de cero horas-protección contra correo no deseado y malware](zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-230">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="b9513-231">Registro de auditoría para informes e investigación</span><span class="sxs-lookup"><span data-stu-id="b9513-231">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="b9513-232">El registro de auditoría está disponible en las suscripciones que incluyen [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span><span class="sxs-lookup"><span data-stu-id="b9513-232">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="b9513-233">Para poder ver los datos de los informes de protección contra amenazas, como el [Panel de seguridad](security-dashboard.md), los informes de [seguridad de correo electrónico](view-email-security-reports.md)y el [Explorador](threat-explorer.md), el registro de auditoría debe estar activado para su organización.</span><span class="sxs-lookup"><span data-stu-id="b9513-233">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="b9513-234">Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="b9513-234">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="b9513-235">Tareas posteriores a la instalación</span><span class="sxs-lookup"><span data-stu-id="b9513-235">Post-setup tasks</span></span>

<span data-ttu-id="b9513-236">Una vez que haya configurado las características de protección contra amenazas, asegúrese de supervisar cómo funcionan estas características, revise y revise las directivas según sea necesario, y vea las nuevas características y actualizaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="b9513-236">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|||
|---|---|
|<span data-ttu-id="b9513-237">**Qué hacer**</span><span class="sxs-lookup"><span data-stu-id="b9513-237">**What to do**</span></span>|<span data-ttu-id="b9513-238">**Recursos para obtener más información**</span><span class="sxs-lookup"><span data-stu-id="b9513-238">**Resources to learn more**</span></span>|
|<span data-ttu-id="b9513-239">Ver cómo funcionan las características de protección contra amenazas en su organización al ver los informes</span><span class="sxs-lookup"><span data-stu-id="b9513-239">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="b9513-240">Panel de seguridad</span><span class="sxs-lookup"><span data-stu-id="b9513-240">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="b9513-241">Informes de seguridad de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="b9513-241">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="b9513-242">Informes para Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b9513-242">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="b9513-243">Explorador de amenazas</span><span class="sxs-lookup"><span data-stu-id="b9513-243">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="b9513-244">Revisar y revisar periódicamente las directivas de protección contra amenazas según sea necesario</span><span class="sxs-lookup"><span data-stu-id="b9513-244">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="b9513-245">Puntuación de seguridad</span><span class="sxs-lookup"><span data-stu-id="b9513-245">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="b9513-246">Informes inteligentes y perspectivas</span><span class="sxs-lookup"><span data-stu-id="b9513-246">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="b9513-247">Características de respuesta y investigación de amenazas de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b9513-247">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="b9513-248">Vea las nuevas características y actualizaciones de servicio</span><span class="sxs-lookup"><span data-stu-id="b9513-248">Watch for new features and service updates</span></span>|[<span data-ttu-id="b9513-249">Opciones de versión estándar y de destino</span><span class="sxs-lookup"><span data-stu-id="b9513-249">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="b9513-250">Centro de mensajes</span><span class="sxs-lookup"><span data-stu-id="b9513-250">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="b9513-251">Plan de desarrollo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b9513-251">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="b9513-252">Descripciones de servicio</span><span class="sxs-lookup"><span data-stu-id="b9513-252">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
