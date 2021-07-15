---
title: Crear directivas de aplicación
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Crear directivas de aplicación.
ms.openlocfilehash: 17417d7fac80f2763edbbaa8dbb2c8be16e47371
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420427"
---
# <a name="create-app-policies"></a><span data-ttu-id="429c0-103">Crear directivas de aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-103">Create app policies</span></span>

><span data-ttu-id="429c0-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="429c0-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="429c0-105">Además de un conjunto de funciones integradas para detectar comportamientos anómalos de las aplicaciones y generar alertas, las directivas de aplicaciones en el gobierno de aplicaciones de Microsoft son una forma de:</span><span class="sxs-lookup"><span data-stu-id="429c0-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="429c0-106">Especifique las condiciones por las que el gobierno de la aplicación puede alertarle del comportamiento de la aplicación para su corrección automática o manual.</span><span class="sxs-lookup"><span data-stu-id="429c0-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="429c0-107">Implemente las directivas de cumplimiento de aplicaciones para su organización.</span><span class="sxs-lookup"><span data-stu-id="429c0-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="429c0-108">Puede crear directivas de aplicación a partir de plantillas proporcionadas que pueden ser personalizadas, o puede crear su propia directiva de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="429c0-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="429c0-109">Para crear una nueva directiva de aplicaciones, vaya al **Centro de cumplimiento de Microsoft 365 > Protección y gobierno de aplicaciones > Página de descripción general > Directivas**:</span><span class="sxs-lookup"><span data-stu-id="429c0-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App protection & governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="429c0-110">Para crear una nueva directiva de aplicaciones con plantillas diseñadas para el uso de aplicaciones, seleccione **Crear directiva** en **Crear una política de uso de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="429c0-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="429c0-111">Para crear una nueva directiva de aplicaciones con plantillas diseñadas para permisos de aplicaciones, seleccione **Crear directiva** en **Crear una directiva de permisos**.</span><span class="sxs-lookup"><span data-stu-id="429c0-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="429c0-112">Para crear una nueva directiva de aplicación para la certificación de aplicaciones o para una directiva personalizada, seleccione **Crear nuevo**.</span><span class="sxs-lookup"><span data-stu-id="429c0-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="429c0-113">Plantillas de directiva de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="429c0-113">App policy templates</span></span>

<span data-ttu-id="429c0-114">Para crear una nueva directiva de aplicación basada en una plantilla de directiva de aplicación, en la **página Elegir plantilla de directiva de aplicación**, seleccione una categoría de plantilla de aplicación, seleccione el nombre de la plantilla y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429c0-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="429c0-115">El gobierno de las aplicaciones tiene tres categorías de plantillas de directivas de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="429c0-116">Usuarios de la aplicación y acceso a los datos</span><span class="sxs-lookup"><span data-stu-id="429c0-116">App users and data access</span></span>

<span data-ttu-id="429c0-117">El gobierno de las aplicaciones incluye estas plantillas para generar alertas sobre el uso de las mismas.</span><span class="sxs-lookup"><span data-stu-id="429c0-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="429c0-118">Nombre de la plantilla</span><span class="sxs-lookup"><span data-stu-id="429c0-118">Template name</span></span> | <span data-ttu-id="429c0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="429c0-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="429c0-120">Nueva aplicación con un alto volumen de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="429c0-120">New app with a high volume of data access</span></span> | <span data-ttu-id="429c0-121">Destaca las aplicaciones registradas recientemente con un alto volumen de acceso a los datos para asegurarse de que esos patrones de datos son los esperados.</span><span class="sxs-lookup"><span data-stu-id="429c0-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="429c0-122">De forma predeterminada, esta directiva marcará todas las aplicaciones que se hayan registrado en los últimos 7 días y que hayan tenido más de 1 GB de acceso a datos durante ese periodo.</span><span class="sxs-lookup"><span data-stu-id="429c0-122">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period.</span></span> <span data-ttu-id="429c0-123">Esta directiva se puede personalizar con más condiciones y acciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-123">This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="429c0-124">Permisos de aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-124">App Permissions</span></span>

<span data-ttu-id="429c0-125">El gobierno de las aplicaciones incluye estas plantillas para generar alertas sobre los permisos de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="429c0-126">Nombre de la plantilla</span><span class="sxs-lookup"><span data-stu-id="429c0-126">Template name</span></span> | <span data-ttu-id="429c0-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="429c0-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="429c0-128">Aplicaciones con exceso de privilegios</span><span class="sxs-lookup"><span data-stu-id="429c0-128">Overprivileged apps</span></span> | <span data-ttu-id="429c0-129">Destaca cualquier aplicación con más permisos concedidos de los que están siendo utilizados por esas aplicaciones para identificar oportunidades de reducción potencial de permisos.</span><span class="sxs-lookup"><span data-stu-id="429c0-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="429c0-130">Por defecto, esta directiva marcará todas las aplicaciones que estén marcadas como con exceso de privilegios si no se utilizan durante 90 días.</span><span class="sxs-lookup"><span data-stu-id="429c0-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="429c0-131">Este filtro de periodo de tiempo se puede personalizar con más condiciones y acciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="429c0-132">Nueva aplicación con permisos de alto privilegio</span><span class="sxs-lookup"><span data-stu-id="429c0-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="429c0-133">Destaca todas las nuevas aplicaciones con permisos de alto privilegio para identificar las posibles aplicaciones de alto impacto que pueden necesitar una mayor investigación.</span><span class="sxs-lookup"><span data-stu-id="429c0-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="429c0-134">De forma predeterminada, esta directiva marcará todas las aplicaciones registradas en los últimos 7 días que tengan permisos de alto alcance.</span><span class="sxs-lookup"><span data-stu-id="429c0-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="429c0-135">Certificación de aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-135">App certification</span></span>

<span data-ttu-id="429c0-136">El gobierno de las aplicaciones incluye estas plantillas para generar alertas para la certificación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="429c0-137">Nombre de la plantilla</span><span class="sxs-lookup"><span data-stu-id="429c0-137">Template name</span></span> | <span data-ttu-id="429c0-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="429c0-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="429c0-139">Nueva aplicación no certificada</span><span class="sxs-lookup"><span data-stu-id="429c0-139">New uncertified app</span></span> | <span data-ttu-id="429c0-140">Destaca las nuevas aplicaciones que no han pasado por el proceso de certificación de aplicaciones para garantizar que son esperadas en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="429c0-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="429c0-141">De forma predeterminada, esta directiva marcará todas las aplicaciones que se hayan registrado en los últimos 7 días y que no estén certificadas.</span><span class="sxs-lookup"><span data-stu-id="429c0-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="429c0-142">Directivas de aplicación personalizadas</span><span class="sxs-lookup"><span data-stu-id="429c0-142">Custom app policies</span></span>

<span data-ttu-id="429c0-143">Utilice una directiva de aplicación personalizada cuando necesite hacer algo que no esté hecho por una de las plantillas incorporadas.</span><span class="sxs-lookup"><span data-stu-id="429c0-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="429c0-144">Para crear una nueva directiva de aplicación personalizada, primero seleccione **Crear nueva** en la página de **Directivas**.</span><span class="sxs-lookup"><span data-stu-id="429c0-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="429c0-145">En la **página Elegir plantilla de directiva de aplicación**, seleccione la categoría **Personalizada**, la plantilla de **Directiva personalizada**, y luego, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429c0-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="429c0-146">En la página **Nombre y descripción**, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="429c0-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="429c0-147">Nombre de directiva</span><span class="sxs-lookup"><span data-stu-id="429c0-147">Policy Name</span></span>

- <span data-ttu-id="429c0-148">Descripción de directiva</span><span class="sxs-lookup"><span data-stu-id="429c0-148">Policy Description</span></span>

- <span data-ttu-id="429c0-149">Seleccione la gravedad de la directiva, que establece la gravedad de las alertas generadas por esta directiva.</span><span class="sxs-lookup"><span data-stu-id="429c0-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="429c0-150">Alto</span><span class="sxs-lookup"><span data-stu-id="429c0-150">High</span></span>
  - <span data-ttu-id="429c0-151">Medio</span><span class="sxs-lookup"><span data-stu-id="429c0-151">Medium</span></span>
  - <span data-ttu-id="429c0-152">Bajo</span><span class="sxs-lookup"><span data-stu-id="429c0-152">Low</span></span>

<span data-ttu-id="429c0-153">En la página **Elegir la configuración y las condiciones de la directiva**, para **Elegir las aplicaciones a las que se aplica esta directiva**, seleccione:</span><span class="sxs-lookup"><span data-stu-id="429c0-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="429c0-154">Todas las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="429c0-154">All Apps</span></span>
- <span data-ttu-id="429c0-155">Elija aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="429c0-155">Choose specific apps</span></span>

  <span data-ttu-id="429c0-156">Un panel permite seleccionar una o varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="429c0-157">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="429c0-157">Select **Add**.</span></span>

<span data-ttu-id="429c0-158">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429c0-158">Select **Next**.</span></span>

<span data-ttu-id="429c0-159">En la página **Elegir configuración y condiciones de la directiva**, seleccione **Establecer nuevas condiciones para la directiva**, y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429c0-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="429c0-160">El panel **Crear regla** permite seleccionar las condiciones para una nueva regla.</span><span class="sxs-lookup"><span data-stu-id="429c0-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="429c0-161">Seleccione **Agregar condición** y seleccione de la lista de condiciones, y luego especifique el valor de la condición.</span><span class="sxs-lookup"><span data-stu-id="429c0-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="429c0-162">Puede agregar varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-162">You can add multiple conditions.</span></span>

<span data-ttu-id="429c0-163">Estas son las condiciones disponibles para una directiva de aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="429c0-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="429c0-164">Condición</span><span class="sxs-lookup"><span data-stu-id="429c0-164">Condition</span></span> | <span data-ttu-id="429c0-165">Valores de condición aceptados</span><span class="sxs-lookup"><span data-stu-id="429c0-165">Condition values accepted</span></span> | <span data-ttu-id="429c0-166">Más información</span><span class="sxs-lookup"><span data-stu-id="429c0-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="429c0-167">Edad de registro de la aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-167">App registration age</span></span> | <span data-ttu-id="429c0-168">En los últimos X días</span><span class="sxs-lookup"><span data-stu-id="429c0-168">Within last X days</span></span> |  |
| <span data-ttu-id="429c0-169">Certificación de aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-169">App certification</span></span> | <span data-ttu-id="429c0-170">Cumplimiento básico, cumplimiento del MCAS o N/A</span><span class="sxs-lookup"><span data-stu-id="429c0-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="429c0-171">Certificación Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="429c0-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="429c0-172">Verificación del editor</span><span class="sxs-lookup"><span data-stu-id="429c0-172">Publisher verification</span></span> | <span data-ttu-id="429c0-173">Sí o no</span><span class="sxs-lookup"><span data-stu-id="429c0-173">Yes or No</span></span> | [<span data-ttu-id="429c0-174">Verificación del editor</span><span class="sxs-lookup"><span data-stu-id="429c0-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="429c0-175">Permiso de aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-175">Application Permission</span></span> | <span data-ttu-id="429c0-176">Seleccione uno o más permisos de API de la lista</span><span class="sxs-lookup"><span data-stu-id="429c0-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="429c0-177">Referencia de permisos de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="429c0-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="429c0-178">Permiso delegado</span><span class="sxs-lookup"><span data-stu-id="429c0-178">Delegated Permission</span></span> | <span data-ttu-id="429c0-179">Seleccione uno o más permisos de API de la lista</span><span class="sxs-lookup"><span data-stu-id="429c0-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="429c0-180">Referencia de permisos de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="429c0-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="429c0-181">Privilegio alto</span><span class="sxs-lookup"><span data-stu-id="429c0-181">High privilege</span></span> | <span data-ttu-id="429c0-182">Sí o no</span><span class="sxs-lookup"><span data-stu-id="429c0-182">Yes or No</span></span> | <span data-ttu-id="429c0-183">Se trata de una designación interna basada en la misma lógica utilizada por el MCAS.</span><span class="sxs-lookup"><span data-stu-id="429c0-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="429c0-184">Aplicación sobre privilegiada</span><span class="sxs-lookup"><span data-stu-id="429c0-184">Overprivileged app</span></span> | <span data-ttu-id="429c0-185">Sí o no</span><span class="sxs-lookup"><span data-stu-id="429c0-185">Yes or No</span></span> | <span data-ttu-id="429c0-186">Aplicaciones con más permisos concedidos de los que están siendo utilizados por esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="429c0-187">Acceso a los datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-187">App data access</span></span> | <span data-ttu-id="429c0-188">Más de X GB de acceso a datos por hora</span><span class="sxs-lookup"><span data-stu-id="429c0-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="429c0-189">Tendencia de acceso a los datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-189">App data access trend</span></span> | <span data-ttu-id="429c0-190">X% de aumento en el uso de datos en los últimos 7 días</span><span class="sxs-lookup"><span data-stu-id="429c0-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="429c0-191">Acceso a la API de la aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-191">App API Access</span></span> | <span data-ttu-id="429c0-192">Más de X llamadas a la API por hora</span><span class="sxs-lookup"><span data-stu-id="429c0-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="429c0-193">Tendencia de acceso a la API de la aplicación</span><span class="sxs-lookup"><span data-stu-id="429c0-193">App API Access trend</span></span> | <span data-ttu-id="429c0-194">X% de aumento en las llamadas a la API en los últimos 7 días</span><span class="sxs-lookup"><span data-stu-id="429c0-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="429c0-195">Consentimiento del usuario</span><span class="sxs-lookup"><span data-stu-id="429c0-195">Users consented</span></span> | <span data-ttu-id="429c0-196">(mayor o menor que) X usuarios con consentimiento</span><span class="sxs-lookup"><span data-stu-id="429c0-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="429c0-197">El usuario con prioridad ha dado su consentimiento</span><span class="sxs-lookup"><span data-stu-id="429c0-197">Priority user consented</span></span> | <span data-ttu-id="429c0-198">Sí o no</span><span class="sxs-lookup"><span data-stu-id="429c0-198">Yes or No</span></span> | <span data-ttu-id="429c0-199">Un usuario con una [cuenta prioritaria](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="429c0-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="429c0-200">Consentimiento de la aplicación concedido por</span><span class="sxs-lookup"><span data-stu-id="429c0-200">App consented by</span></span> | <span data-ttu-id="429c0-201">Seleccionar usuario(s) de la lista</span><span class="sxs-lookup"><span data-stu-id="429c0-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="429c0-202">Rol del usuario que da su consentimiento</span><span class="sxs-lookup"><span data-stu-id="429c0-202">Consenting user’s role</span></span> | <span data-ttu-id="429c0-203">Seleccione uno o más: Administrador de equipos, Lector de directorios, Lector de seguridad, Administrador de cumplimiento, Administrador de seguridad, Administrador de Helpdesk, Administrador de SharePoint, Administrador de Exchange, Lector global, Administrador global, Administrador de datos de cumplimiento, Administrador de usuarios, Administrador de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="429c0-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="429c0-204">La selección múltiple está permitida.</span><span class="sxs-lookup"><span data-stu-id="429c0-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="429c0-205">Cualquier rol de Azure AD con miembro asignado debe estar disponible en esta lista.</span><span class="sxs-lookup"><span data-stu-id="429c0-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="429c0-206">Carga de trabajo a la que se accede</span><span class="sxs-lookup"><span data-stu-id="429c0-206">Workload accessed</span></span> | <span data-ttu-id="429c0-207">OneDrive y/o SharePoint y/o Exchange</span><span class="sxs-lookup"><span data-stu-id="429c0-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="429c0-208">La selección múltiple está permitida.</span><span class="sxs-lookup"><span data-stu-id="429c0-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="429c0-209">Tasa de errores</span><span class="sxs-lookup"><span data-stu-id="429c0-209">Error rate</span></span> | <span data-ttu-id="429c0-210">La tasa de error es superior al X% en los últimos 7 días, donde X es un valor definido por el administrador</span><span class="sxs-lookup"><span data-stu-id="429c0-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="429c0-211">Se deben cumplir todas las condiciones especificadas para que se aplique esta directiva de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="429c0-212">Cuando haya terminado de especificar las condiciones, seleccione **Guardar**, y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429c0-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="429c0-213">En la página **Definir acciones de directiva**, seleccione **Desactivar aplicación** si desea que el gobierno de la aplicación desactive la aplicación cuando se genere una alerta basada en esta directiva, y luego, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="429c0-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="429c0-214">En la página **Definir el estado de la directiva**, seleccione una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="429c0-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="429c0-215">**Modo de auditoría**: las directivas son evaluadas pero las acciones configuradas no ocurrirán.</span><span class="sxs-lookup"><span data-stu-id="429c0-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="429c0-216">Las directivas en modo de auditoría aparecen con el estado de **Auditoría** en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="429c0-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="429c0-217">**Activo**: las directivas son evaluadas y las acciones configuradas se llevarán a cabo.</span><span class="sxs-lookup"><span data-stu-id="429c0-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="429c0-218">**Inactivo**: las directivas no son evaluadas y las acciones configuradas no tendrán lugar.</span><span class="sxs-lookup"><span data-stu-id="429c0-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="429c0-219">Pruebe y supervise su nueva directiva de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="429c0-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="429c0-220">Ahora que su directiva de aplicación está creada, debe supervisarla en la página de **Directivas** para asegurarse de que está registrando un número esperado de alertas activas y alertas totales durante las pruebas.</span><span class="sxs-lookup"><span data-stu-id="429c0-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![La página de resumen de las directivas de MAPG en el Centro de cumplimiento de Microsoft 365 con una directiva resaltada](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="429c0-222">Si el número de alertas es un valor inesperadamente bajo, edite la configuración de la directiva de la aplicación para asegurarse de que la ha configurado correctamente antes de establecer su estado.</span><span class="sxs-lookup"><span data-stu-id="429c0-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="429c0-223">Este es un ejemplo de un proceso para crear una nueva directiva, probarla y luego activarla:</span><span class="sxs-lookup"><span data-stu-id="429c0-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="429c0-224">Cree la nueva directiva con la gravedad, las aplicaciones, las condiciones y las acciones establecidas en el **Modo de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="429c0-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="429c0-225">Compruebe el comportamiento esperado, como las alertas generadas.</span><span class="sxs-lookup"><span data-stu-id="429c0-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="429c0-226">Si el comportamiento no es el esperado, edite las aplicaciones de la directiva, las condiciones y la configuración de la acción según sea necesario y vuelva al paso 2.</span><span class="sxs-lookup"><span data-stu-id="429c0-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="429c0-227">Si el comportamiento es el esperado, edite la directiva y cambie su estado a **Activo**.</span><span class="sxs-lookup"><span data-stu-id="429c0-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![El flujo de trabajo para crear una directiva de aplicación](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="429c0-229">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="429c0-229">Next step</span></span>

[<span data-ttu-id="429c0-230">Administre las directivas de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="429c0-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
