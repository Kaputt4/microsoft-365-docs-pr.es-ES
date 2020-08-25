---
title: Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Usar etiquetas de confidencialidad para proteger el contenido en los sitios de SharePoint y Microsoft Teams, y los grupos de Microsoft 365.
ms.openlocfilehash: 849eae1c2c3153d8f17e561aa82312c95672ec04
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845748"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="c9868-103">Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9868-103">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

><span data-ttu-id="c9868-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c9868-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c9868-105">Además de usar [etiquetas de confidencialidad](sensitivity-labels.md) para clasificar y proteger documentos y mensajes de correo electrónico, también puede usarlas para proteger el contenido en los siguientes contenedores: sitios de Microsoft Teams, grupos de Microsoft 365 ([anteriormente grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), y sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9868-105">In addition to using [sensitivity labels](sensitivity-labels.md) to classify and protect documents and emails, you can also use sensitivity labels to protect content in the following containers: Microsoft Teams sites, Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), and SharePoint sites.</span></span> <span data-ttu-id="c9868-106">Para esta clasificación y protección de nivel de contenedor, utilice la siguiente configuración de etiquetas:</span><span class="sxs-lookup"><span data-stu-id="c9868-106">For this container-level classification and protection, use the following label settings:</span></span>

- <span data-ttu-id="c9868-107">Privacidad (pública o privada) de los sitios de equipos conectados a grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9868-107">Privacy (public or private) of Microsoft 365 group-connected teams sites</span></span>
- <span data-ttu-id="c9868-108">Acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="c9868-108">External users access</span></span>
- <span data-ttu-id="c9868-109">Acceso desde dispositivos no administrados</span><span class="sxs-lookup"><span data-stu-id="c9868-109">Access from unmanaged devices</span></span>

<span data-ttu-id="c9868-110">Cuando aplica esta etiqueta de confidencialidad a un contenedor compatible, la etiqueta aplica automáticamente la configuración de protección y clasificación al grupo o sitio conectado.</span><span class="sxs-lookup"><span data-stu-id="c9868-110">When you apply this sensitivity label to a supported container, the label automatically applies the classification and protection settings to the connected site or group.</span></span>

<span data-ttu-id="c9868-111">Sin embargo, el contenido de estos contenedores no hereda las etiquetas para la clasificación y configuración, como las marcas visuales o el cifrado.</span><span class="sxs-lookup"><span data-stu-id="c9868-111">Content in these containers however, do not inherit the labels for the classification and settings such as visual markings, or encryption.</span></span> <span data-ttu-id="c9868-112">Para que los usuarios puedan etiquetar sus documentos en los sitios de SharePoint o de grupos, asegúrese de [habilitar las etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="c9868-112">So that users can label their documents in SharePoint sites or team sites, make sure you've [enabled sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c9868-113">Las etiquetas de sensibilidad para contenedores no son compatibles con las Redes de entrega de contenido (CDNs) de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9868-113">Sensitivity labels for containers aren't supported with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a><span data-ttu-id="c9868-114">Uso de etiquetas de confidencialidad para Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9868-114">Using sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="c9868-115">Antes de habilitar etiquetas de confidencialidad para contenedores y establecerlas para la nueva configuración, los usuarios pueden ver y aplicar etiquetas de confidencialidad en sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c9868-115">Before you enable sensitivity labels for containers and configure sensitivity labels for the new settings, users can see and apply sensitivity labels in their apps.</span></span> <span data-ttu-id="c9868-116">Por ejemplo, en Word:</span><span class="sxs-lookup"><span data-stu-id="c9868-116">For example, from Word:</span></span>

![Una etiqueta de sensibilidad que se muestra en la aplicación de escritorio de Word](../media/sensitivity-label-word.png)

<span data-ttu-id="c9868-118">Después de habilitar y configurar etiquetas de confidencialidad para contenedores, los usuarios también pueden ver y aplicar etiquetas de confidencialidad en sitios de equipos de Microsoft, grupos de Microsoft 365 y sitios de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9868-118">After you enable and configure sensitivity labels for containers, users can additionally see and apply sensitivity labels to Microsoft team sites, Microsoft 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="c9868-119">Por ejemplo, al crear un sitio de grupo de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="c9868-119">For example, when you create a new team site from SharePoint:</span></span>

![Una etiqueta de sensibilidad al crear un sitio de equipo desde SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a><span data-ttu-id="c9868-121">Cómo habilitar etiquetas de confidencialidad para contenedores y sincronizarlas</span><span class="sxs-lookup"><span data-stu-id="c9868-121">How to enable sensitivity labels for containers and synchronize labels</span></span>

1. <span data-ttu-id="c9868-122">Dado que esta característica usa la funcionalidad de Azure AD, siga las instrucciones de la documentación de Azure AD para habilitar la compatibilidad con etiquetas de confidencialidad: [Asignar etiquetas de confidencialidad a grupos de Microsoft 365 en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="c9868-122">Because this feature uses Azure AD functionality, follow the instructions from the Azure AD documentation to enable sensitivity label support: [Assign sensitivity labels to Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).</span></span>

2. <span data-ttu-id="c9868-123">Ahora tiene que sincronizar sus etiquetas de confidencialidad en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c9868-123">You now need to synchronize your sensitivity labels to Azure AD.</span></span> <span data-ttu-id="c9868-124">En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9868-124">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="c9868-125">Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:</span><span class="sxs-lookup"><span data-stu-id="c9868-125">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account.</span></span>

3. <span data-ttu-id="c9868-126">Después, ejecute el siguiente comando para asegurarse de que sus etiquetas de confidencialidad se pueden usar con los grupos de Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="c9868-126">Then run the following command to ensure your sensitivity labels can be used with Microsoft 365 groups:</span></span>

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings"></a><span data-ttu-id="c9868-127">Cómo establecer la configuración de sitio y grupo</span><span class="sxs-lookup"><span data-stu-id="c9868-127">How to configure site and group settings</span></span>

<span data-ttu-id="c9868-128">Ya está listo para crear o editar las etiquetas de confidencialidad que quiera y que estén disponibles para sitios y grupos.</span><span class="sxs-lookup"><span data-stu-id="c9868-128">You're now ready to create or edit sensitivity labels that you want to be available for sites and groups.</span></span> <span data-ttu-id="c9868-129">Al habilitar etiquetas de confidencialidad para contenedores, se hace visible una nueva página en los asistentes de etiquetas de confidencialidad: **Configuración de sitio y grupo**</span><span class="sxs-lookup"><span data-stu-id="c9868-129">Enabling sensitivity labels for containers makes a new page visible in the sensitivity labeling wizards: **Site and group settings**</span></span>

<span data-ttu-id="c9868-130">Si necesita ayuda para crear o editar una etiquetas de confidencialidad, vea las instrucciones en [Crear y configurar etiquetas de confidencialidad](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="c9868-130">If you need help with creating or editing a sensitivity label, see the instructions from [Create and configure sensitivity labels](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).</span></span>

<span data-ttu-id="c9868-131">En la nueva página **Configuración de sitio y grupo**, configure las opciones:</span><span class="sxs-lookup"><span data-stu-id="c9868-131">On this new **Site and group settings** page, configure the settings:</span></span>

- <span data-ttu-id="c9868-132">**Privacidad de los sitios de equipos conectados a grupos de Office 365**: mantenga el valor predeterminado de \*\*Público: cualquier persona de la organización puede acceder al sitio \*\* si quiere que todos en su organización accedan al sitio de grupo o grupo donde se aplica esta etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c9868-132">**Privacy of Office 365 group-connected teams sites**: Keep the default of **Public - anyone in the organization can access the site** if you want anyone in your organization to access the team site or group where this label is applied.</span></span>

  <span data-ttu-id="c9868-133">Seleccione **Privado** si quiere que el acceso esté restringido solo a miembros aprobados de su organización.</span><span class="sxs-lookup"><span data-stu-id="c9868-133">Select **Private** if you want access to be restricted to only approved members in your organization.</span></span>

  <span data-ttu-id="c9868-134">Seleccione **Ninguno: permitir al usuario elegir quién puede acceder al sitio** cuando quiera proteger el contenido del contenedor mediante el uso de la etiqueta de confidencialidad, pero permitir que los usuarios configuren la configuración de privacidad ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="c9868-134">Select **None - let user chose who can access the site** when you want to protect content in the container by using the sensitivity label, but still let users configure the privacy setting themselves.</span></span>

  <span data-ttu-id="c9868-135">Las opciones **Pública** o **Privada** para establecen y bloquean la configuración de privacidad cuando aplica esta etiqueta al contenedor.</span><span class="sxs-lookup"><span data-stu-id="c9868-135">The settings of **Public** or **Private** set and lock the privacy setting when you apply this label to the container.</span></span> <span data-ttu-id="c9868-136">La configuración elegida reemplaza cualquier configuración de privacidad anterior establecida para el equipo o grupo, y bloquea el valor de privacidad para que solo se pueda cambiar quitando primero la etiqueta de confidencialidad del contenedor.</span><span class="sxs-lookup"><span data-stu-id="c9868-136">Your chosen setting replaces any previous privacy setting that might be configured for the team or group, and locks the privacy value so it can be changed only by first removing the sensitivity label from the container.</span></span> <span data-ttu-id="c9868-137">Después de quitar la etiqueta de confidencialidad, la configuración de privacidad de la etiqueta permanece y los usuarios ya pueden cambiarla de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c9868-137">After you remove the sensitivity label, the privacy setting from the label remains and users can now change it again.</span></span>

- <span data-ttu-id="c9868-138">**Acceso de usuarios externos**: controla si el propietario del grupo puede [agregar invitados al grupo](/office365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="c9868-138">**External users access**: Control whether the group owner can [add guests to the group](/office365/admin/create-groups/manage-guest-access-in-groups).</span></span>

- <span data-ttu-id="c9868-139">**Dispositivos no administrados**: para [dispositivos sin administrar](/sharepoint/control-access-from-unmanaged-devices), permite acceso total, acceso de solo Web, o bloquear el acceso completamente.</span><span class="sxs-lookup"><span data-stu-id="c9868-139">**Unmanaged devices**: For [unmanaged devices](/sharepoint/control-access-from-unmanaged-devices), allow full access, web only access, or block access completely.</span></span> <span data-ttu-id="c9868-140">Si ha configurado este parámetro a nivel de espacio empresarial o para sitio específico, la configuración que especifique aquí solo se aplicará si es más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="c9868-140">If you have configured this setting at the tenant level or for a specific site, the setting you specify here will be applied only if it's more restrictive.</span></span>

![La pestaña de configuración del sitio y del grupo](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> <span data-ttu-id="c9868-142">La configuración de sitio y grupo solo surte efecto al aplicar la etiqueta a un equipo, grupo o sitio.</span><span class="sxs-lookup"><span data-stu-id="c9868-142">Only these site and group settings take effect when you apply the label to a team, group, or site.</span></span> <span data-ttu-id="c9868-143">El resto de opciones de configuración de etiqueta, como el cifrado y la marcación de contenido, no se aplican a todo el contenido del equipo, grupo o sitio.</span><span class="sxs-lookup"><span data-stu-id="c9868-143">Other label settings, such as encryption and content marking, aren't applied to the content within the team, group, or site.</span></span>
>
> <span data-ttu-id="c9868-144">Implementación gradual en espacios empresariales: solo las etiquetas con la configuración de sitio y de grupo estarán disponibles para seleccionarlas cuando los usuarios creen equipos, grupos y sitios.</span><span class="sxs-lookup"><span data-stu-id="c9868-144">Gradually rolling out to tenants: Only labels with the site and group settings will be available to select when users create teams, groups, and sites.</span></span> <span data-ttu-id="c9868-145">Si actualmente puede aplicar una etiqueta a un contenedor cuando la etiqueta no tiene habilitadas las configuraciones de sitio y grupo, solo se aplica el nombre de la etiqueta al contenedor.</span><span class="sxs-lookup"><span data-stu-id="c9868-145">If you can currently apply a label to a container when the label doesn't have the site and group settings enabled, only the label name is applied to the container.</span></span>

<span data-ttu-id="c9868-146">Si la etiqueta de confidencialidad aún no se ha publicado, publíquela [agregándola a una directiva de etiqueta de confidencialidad](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="c9868-146">If your sensitivity label isn't already published, now publish it by [adding it to a sensitivity label policy](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span> <span data-ttu-id="c9868-147">Los usuarios que tienen asignada una directiva de etiqueta de confidencialidad que incluye esta etiqueta podrán seleccionarla para sitios y grupos.</span><span class="sxs-lookup"><span data-stu-id="c9868-147">The users who are assigned a sensitivity label policy that includes this label will be able to select it for sites and groups.</span></span>

<span data-ttu-id="c9868-148">En la Directiva de etiqueta, solo la configuración de directiva **aplicar esta etiqueta de forma predeterminada a los documentos y el correo electrónico** es aplicable cuando se aplica esta etiqueta a contenedores.</span><span class="sxs-lookup"><span data-stu-id="c9868-148">From the label policy, only the policy setting **Apply this label by default to documents and email** is applicable when you apply this label to containers.</span></span> <span data-ttu-id="c9868-149">No se aplican otras opciones de configuración de Directiva, como la etiqueta obligatoria, que requiere la justificación del usuario y un vínculo a la página de ayuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="c9868-149">Other policy settings are not applied, which include mandatory labeling, requiring user justification, and a link to the custom help page.</span></span>

## <a name="sensitivity-label-management"></a><span data-ttu-id="c9868-150">Administración de etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="c9868-150">Sensitivity label management</span></span>

<span data-ttu-id="c9868-151">Use las siguientes instrucciones para crear, modificar o eliminar las etiquetas de confidencialidad configuradas para sitios y grupos.</span><span class="sxs-lookup"><span data-stu-id="c9868-151">Use the following guidance for when you create, modify, or delete sensitivity labels that are configured for sites and groups.</span></span>

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="c9868-152">Crear y publicar etiquetas configuradas para sitios y grupos</span><span class="sxs-lookup"><span data-stu-id="c9868-152">Creating and publishing labels that are configured for sites and groups</span></span>

<span data-ttu-id="c9868-153">Cuando se crea y se publica una nueva etiqueta de confidencialidad, los usuarios en los equipos, grupos y sitios pueden verla en un plazo de una hora.</span><span class="sxs-lookup"><span data-stu-id="c9868-153">When a new sensitivity label is created and published, it's visible for users in teams, groups, and sites within one hour.</span></span> <span data-ttu-id="c9868-154">Sin embargo, si modifica una etiqueta existente, permita que pasen hasta 24 horas.</span><span class="sxs-lookup"><span data-stu-id="c9868-154">However, if you modify an existing label, allow up to 24 hours.</span></span> <span data-ttu-id="c9868-155">Use las siguientes instrucciones para publicar una etiqueta para los usuarios establecida para la configuración de sitio y grupo:</span><span class="sxs-lookup"><span data-stu-id="c9868-155">Use the following guidance to publish a label for your users when that label is configured for site and group settings:</span></span>

1. <span data-ttu-id="c9868-156">Después de crear y configurar la etiqueta de confidencialidad, agréguela a una directiva de etiqueta que solo se aplique a algunos usuarios de prueba.</span><span class="sxs-lookup"><span data-stu-id="c9868-156">After you create and configure the sensitivity label, add this label to a label policy that applies to just a few test users.</span></span>

2. <span data-ttu-id="c9868-157">Espere a que se replique el cambio:</span><span class="sxs-lookup"><span data-stu-id="c9868-157">Wait for the change to replicate:</span></span>

   - <span data-ttu-id="c9868-158">Nueva etiqueta: espere una hora.</span><span class="sxs-lookup"><span data-stu-id="c9868-158">New label: Wait for one hour.</span></span>
   - <span data-ttu-id="c9868-159">Etiqueta existente: espere 24 horas.</span><span class="sxs-lookup"><span data-stu-id="c9868-159">Existing label: Wait for 24 hours.</span></span>

3. <span data-ttu-id="c9868-160">Después de este período, utilice una de las cuentas de usuario de prueba para crear un equipo, un grupo de Microsoft 365 o un sitio de SharePoint con la etiqueta creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c9868-160">After this wait period, use one of the test user accounts to create a team, Microsoft 365 group, or SharePoint site with the label that you created in step 1.</span></span>

4. <span data-ttu-id="c9868-161">Si no se producen errores durante el proceso de creación, significa que es seguro publicar la etiqueta en todos los usuarios de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="c9868-161">If there are no errors during this creation operation, you know it's safe to publish the label to all users in your tenant.</span></span>

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="c9868-162">Modificar las etiquetas publicadas que están configuradas para sitios y grupos</span><span class="sxs-lookup"><span data-stu-id="c9868-162">Modifying published labels that are configured for sites and groups</span></span>

<span data-ttu-id="c9868-163">Como práctica recomendada, no cambie la configuración de sitio y grupo para una etiqueta de confidencialidad cuando se haya aplicado a equipos, grupos o sitios.</span><span class="sxs-lookup"><span data-stu-id="c9868-163">As a best practice, don't change the site and group settings for a sensitivity label after the label has been applied to teams, groups, or sites.</span></span> <span data-ttu-id="c9868-164">Si lo hace, espere hasta 24 horas para que los cambios se repliquen en todos los contenedores que tienen la etiqueta aplicada.</span><span class="sxs-lookup"><span data-stu-id="c9868-164">If you do, remember to wait for 24 hours for the changes to replicate to all containers that have the label applied.</span></span>

<span data-ttu-id="c9868-165">Además, si los cambios incluyen la configuración **Acceso de usuarios externos**:</span><span class="sxs-lookup"><span data-stu-id="c9868-165">In addition, if your changes include the **External users access** setting:</span></span>

- <span data-ttu-id="c9868-166">La nueva configuración se aplica a los usuarios nuevos, pero no a los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="c9868-166">The new setting applies to new users but not to existing users.</span></span> <span data-ttu-id="c9868-167">Por ejemplo, si esta configuración se seleccionó previamente y, como resultado, los usuarios invitados entraron el sitio, estos aún podrán tener acceso al sitio después de que la opción esté desactivada en la configuración de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c9868-167">For example, if this setting was previously selected and as a result, guest users accessed the site, these guest users can still access the site after this setting is cleared in the label configuration.</span></span>

- <span data-ttu-id="c9868-168">La configuración de privacidad de las propiedades de grupo hiddenMembership y roleEnabled no se actualiza.</span><span class="sxs-lookup"><span data-stu-id="c9868-168">The privacy settings for the group properties hiddenMembership and roleEnabled aren't updated.</span></span>

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a><span data-ttu-id="c9868-169">Eliminar etiquetas publicadas que están configuradas para sitios y grupos</span><span class="sxs-lookup"><span data-stu-id="c9868-169">Deleting published labels that are configured for sites and groups</span></span>

<span data-ttu-id="c9868-170">Si elimina una etiqueta de confidencialidad con la configuración de sitio y grupo habilitada, y esa etiqueta se incluye en una o más directivas de etiquetas, esta acción pueden provocar fallas de creación para nuevos equipos, grupos y sitios.</span><span class="sxs-lookup"><span data-stu-id="c9868-170">If you delete a sensitivity label that has the site and group settings enabled, and that label is included in one or more label policies, this action can result in creation failures for new teams, groups, and sites.</span></span> <span data-ttu-id="c9868-171">Para evitarlo, siga las instrucciones que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="c9868-171">To avoid this situation, use the following guidance:</span></span>

1. <span data-ttu-id="c9868-172">Elimine la etiqueta de confidencialidad de todas las directivas de etiqueta que la incluyan.</span><span class="sxs-lookup"><span data-stu-id="c9868-172">Remove the sensitivity label from all label policies that include the label.</span></span>

2. <span data-ttu-id="c9868-173">Espere una hora.</span><span class="sxs-lookup"><span data-stu-id="c9868-173">Wait for one hour.</span></span>

3. <span data-ttu-id="c9868-174">Después de este período, pruebe a crear un equipo, grupo o sitio y compruebe que la etiqueta ya no es visible.</span><span class="sxs-lookup"><span data-stu-id="c9868-174">After this wait period, try creating a team, group, or site and confirm that the label is no longer visible.</span></span>

4. <span data-ttu-id="c9868-175">Si la etiqueta de confidencialidad no es visible, ya puede eliminarla de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c9868-175">If the sensitivity label isn't visible, you can now safely delete the label.</span></span>

## <a name="how-to-apply-sensitivity-labels-to-containers"></a><span data-ttu-id="c9868-176">Cómo aplicar etiquetas de confidencialidad a contenedores</span><span class="sxs-lookup"><span data-stu-id="c9868-176">How to apply sensitivity labels to containers</span></span>

<span data-ttu-id="c9868-177">Ya está listo para aplicar la etiqueta o las etiquetas de confidencialidad a los siguientes contenedores:</span><span class="sxs-lookup"><span data-stu-id="c9868-177">You're now ready to apply the sensitivity label or labels to the following containers:</span></span>

- [<span data-ttu-id="c9868-178">Grupo de Microsoft 365 en Azure AD</span><span class="sxs-lookup"><span data-stu-id="c9868-178">Microsoft 365 group in Azure AD</span></span>](#apply-sensitivity-labels-to-microsoft-365-groups)
- [<span data-ttu-id="c9868-179">Sitio de grupo de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9868-179">Microsoft Teams team site</span></span>](#apply-a-sensitivity-label-to-a-new-team)
- [<span data-ttu-id="c9868-180">Grupo de Microsoft 365 en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="c9868-180">Microsoft 365 group in Outlook on the web</span></span>](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [<span data-ttu-id="c9868-181">Sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9868-181">SharePoint site</span></span>](#apply-a-sensitivity-label-to-a-new-site)

<span data-ttu-id="c9868-182">Puede usar PowerShell si necesita [aplicar una etiqueta de sensibilidad a varios sitios](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span><span class="sxs-lookup"><span data-stu-id="c9868-182">You can use PowerShell if you need to [apply a sensitivity label to multiple sites](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).</span></span>

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a><span data-ttu-id="c9868-183">Aplicar etiquetas de confidencialidad a grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9868-183">Apply sensitivity labels to Microsoft 365 groups</span></span>

<span data-ttu-id="c9868-184">Ya está listo para aplicar la etiqueta o las etiquetas de confidencialidad a los grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9868-184">You're now ready to apply the sensitivity label or labels to Microsoft 365 groups.</span></span> <span data-ttu-id="c9868-185">Regrese a la documentación de Azure AD para obtener instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c9868-185">Return to the Azure AD documentation for instructions:</span></span>

- [<span data-ttu-id="c9868-186">Asignar una etiqueta a un grupo nuevo en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="c9868-186">Assign a label to a new group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

- [<span data-ttu-id="c9868-187">Asignar una etiqueta a un grupo existente en Azure Portal</span><span class="sxs-lookup"><span data-stu-id="c9868-187">Assign a label to an existing group in Azure portal</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- <span data-ttu-id="c9868-188">[Quitar una etiqueta a un grupo existente en Azure Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="c9868-188">[Remove a label from an existing group in Azure portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal).</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="c9868-189">Aplicar una etiqueta de confidencialidad a un nuevo equipo</span><span class="sxs-lookup"><span data-stu-id="c9868-189">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="c9868-190">Los usuarios pueden seleccionar etiquetas de confidencialidad al crear nuevos equipos en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c9868-190">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="c9868-191">Al seleccionar la etiqueta en la lista desplegable **confidencialidad**, es posible que la configuración de privacidad cambie para reflejar la configuración de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c9868-191">When they select the label from the **Sensitivity** dropdown, the privacy setting might change to reflect the label configuration.</span></span> <span data-ttu-id="c9868-192">En función de la configuración de acceso de usuarios externos que haya seleccionado para la etiqueta, los usuarios pueden o no, agregar al equipo personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="c9868-192">Depending on the external users access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

[<span data-ttu-id="c9868-193">Más información sobre las etiquetas de confidencialidad para Teams</span><span class="sxs-lookup"><span data-stu-id="c9868-193">Learn more about sensitivity labels for Teams</span></span>](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![La configuración de privacidad al crear un nuevo equipo](../media/privacy-setting-new-team.png)

<span data-ttu-id="c9868-195">Después de crear el equipo, se muestra la etiqueta de confidencialidad en la esquina superior derecha de todos los canales.</span><span class="sxs-lookup"><span data-stu-id="c9868-195">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![La etiqueta de confidencialidad se muestra en el equipo](../media/privacy-setting-teams.png)

<span data-ttu-id="c9868-197">El servicio aplica automáticamente la misma etiqueta de confidencialidad al grupo de Microsoft 365 y al sitio de grupo de SharePoint conectado.</span><span class="sxs-lookup"><span data-stu-id="c9868-197">The service automatically applies the same sensitivity label to the Microsoft 365 group and the connected SharePoint team site.</span></span>

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a><span data-ttu-id="c9868-198">Aplicar una etiqueta de confidencialidad a un nuevo grupo en Outlook en la Web</span><span class="sxs-lookup"><span data-stu-id="c9868-198">Apply a sensitivity label to a new group in Outlook on the web</span></span>

<span data-ttu-id="c9868-199">En Outlook en la Web, al crear un grupo, puede seleccionar o cambiar la opción **confidencialidad** para las etiquetas publicadas:</span><span class="sxs-lookup"><span data-stu-id="c9868-199">In Outlook on the web, when you create a new group, you can select or change the **Sensitivity** option for published labels:</span></span>

![Crear un grupo y seleccionar una opción en Confidencialidad](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="c9868-201">Aplicar una etiqueta de confidencialidad a un nuevo sitio</span><span class="sxs-lookup"><span data-stu-id="c9868-201">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="c9868-202">Los administradores y los usuarios finales pueden seleccionar las etiquetas de confidencialidad cuando [crean sitios de grupo y de comunicación modernos](/sharepoint/create-site-collection) y expandir la **configuración avanzada**:</span><span class="sxs-lookup"><span data-stu-id="c9868-202">Admins and end users can select sensitivity labels when they [create modern team sites and communication sites](/sharepoint/create-site-collection), and expand **Advanced settings**:</span></span>

![Crear un sitio y seleccionar una opción en Confidencialidad](../media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="c9868-204">En el cuadro desplegable se mostrarán los nombres de etiqueta de la selección, y en el icono de ayuda se mostrarán todos los nombres de etiqueta con la información sobre herramientas, que puede ayudar a los usuarios a determinar la etiqueta correcta que debe aplicar.</span><span class="sxs-lookup"><span data-stu-id="c9868-204">The dropdown box displays the label names for the selection, and the help icon displays all the label names with their tooltip, which can help users determine the correct label to apply.</span></span>

<span data-ttu-id="c9868-205">Cuando los usuarios exploren el sitio, podrán ver el nombre de la etiqueta y las directivas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="c9868-205">When the label is applied, and users browse to the site, they see the name of the label and applied policies.</span></span> <span data-ttu-id="c9868-206">Por ejemplo, este sitio se ha etiquetado como **confidencial** y la configuración de privacidad se ha establecido en **privada**:</span><span class="sxs-lookup"><span data-stu-id="c9868-206">For example, this site has been labeled as **Confidential**, and the privacy setting is set to **Private**:</span></span>

![Un sitio en el que se ha aplicado una etiqueta de confidencialidad](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a><span data-ttu-id="c9868-208">Usar PowerShell para aplicar una etiqueta de confidencialidad a varios sitios</span><span class="sxs-lookup"><span data-stu-id="c9868-208">Use PowerShell to apply a sensitivity label to multiple sites</span></span>

<span data-ttu-id="c9868-209">Puede usar los cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) y [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) con el parámetro *SensitivityLabel* desde el [Shell de SharePoint Online Management](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) actual para aplicar una etiqueta de confidencialidad a muchos sitios.</span><span class="sxs-lookup"><span data-stu-id="c9868-209">You can use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) and [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) cmdlet with the *SensitivityLabel* parameter from the current [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) to apply a sensitivity label to many sites.</span></span> <span data-ttu-id="c9868-210">Los sitios pueden ser cualquiera de los pertenecientes a la colección de sitios de SharePoint o un sitio de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c9868-210">The sites can be any SharePoint site collection, or a OneDrive site.</span></span>

<span data-ttu-id="c9868-211">Asegúrese de que tiene la versión 16.0.19418.12000 o posterior del Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c9868-211">Make sure you have version 16.0.19418.12000 or later of the SharePoint Online Management Shell.</span></span>

1. <span data-ttu-id="c9868-212">Abra una sesión de PowerShell con la opción **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="c9868-212">Open a PowerShell session with the **Run as Administrator** option.</span></span>

2. <span data-ttu-id="c9868-213">Si no conoce el GUID de la etiqueta, vaya a: [Conectarse al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) y obtenga la lista de etiquetas de confidencialidad y sus GUID.</span><span class="sxs-lookup"><span data-stu-id="c9868-213">If you don't know your label GUID: [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and get the list of sensitivity labels and their GUIDs.</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="c9868-214">Ahora, [conéctese a SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) y almacene el GUID de etiqueta como una variable.</span><span class="sxs-lookup"><span data-stu-id="c9868-214">Now [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and store your label GUID as a variable.</span></span> <span data-ttu-id="c9868-215">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9868-215">For example:</span></span>

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. <span data-ttu-id="c9868-216">Cree una nueva variable que identifique varios sitios con una cadena de identificación en común en su URL.</span><span class="sxs-lookup"><span data-stu-id="c9868-216">Create a new variable that identifies multiple sites that have an identifying string in common in their URL.</span></span> <span data-ttu-id="c9868-217">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9868-217">For example:</span></span>

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. <span data-ttu-id="c9868-218">Ejecute el siguiente comando para aplicar la etiqueta a estos sitios.</span><span class="sxs-lookup"><span data-stu-id="c9868-218">Run the following command to apply the label to these sites.</span></span> <span data-ttu-id="c9868-219">Utilice nuestros ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c9868-219">Using our examples:</span></span>

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

<span data-ttu-id="c9868-220">Para aplicar distintas etiquetas a otros sitios, repita el siguiente comando para cada sitio: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span><span class="sxs-lookup"><span data-stu-id="c9868-220">To apply different labels to different sites, repeat the following command for each site: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`</span></span>

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="c9868-221">Ver y administrar etiquetas de confidencialidad en el centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9868-221">View and manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="c9868-222">Para ver, ordenar y buscar las etiquetas de confidencialidad aplicadas, use la página **Sitios activos** en el nuevo Centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c9868-222">To view, sort, and search the applied sensitivity labels, use the **Active sites** page in the new SharePoint admin center.</span></span> <span data-ttu-id="c9868-223">Es posible que primero tenga que agregar la columna **confidencialidad**:</span><span class="sxs-lookup"><span data-stu-id="c9868-223">You might need to first add the **Sensitivity** column:</span></span>

![La columna Confidencialidad en la página Sitios activos](../media/manage-site-sensitivity-labels.png)

<span data-ttu-id="c9868-225">Para obtener más información sobre la administración de sitios desde la página Sitios activos, incluido cómo agregar una columna, vea [Administrar sitios en el nuevo centro de administración de SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c9868-225">For more information about managing sites from the Active sites page, including how to add a column, see [Manage sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

<span data-ttu-id="c9868-226">También puede cambiar y aplicar una etiqueta desde esta página:</span><span class="sxs-lookup"><span data-stu-id="c9868-226">You can also change and apply a label from this page:</span></span>

1. <span data-ttu-id="c9868-227">Seleccione el nombre del sitio para abrir el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="c9868-227">Select the site name to open the details pane.</span></span>

2. <span data-ttu-id="c9868-228">Seleccione la pestaña **Directivas** y después, elija **Editar** para la configuración **Confidencialidad**.</span><span class="sxs-lookup"><span data-stu-id="c9868-228">Select the **Policies** tab, and then select **Edit** for the **Sensitivity** setting.</span></span>

3. <span data-ttu-id="c9868-229">En el panel **Editar configuración de confidencialidad**, seleccione la etiqueta de confidencialidad que desea aplicar al sitio y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c9868-229">From the **Edit sensitivity setting** pane, select the sensitivity label you want to apply to the site, and then select **Save**.</span></span>

## <a name="support-for-sensitivity-labels"></a><span data-ttu-id="c9868-230">Compatibilidad con etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="c9868-230">Support for sensitivity labels</span></span>

<span data-ttu-id="c9868-231">Las siguientes aplicaciones y servicios son compatibles con etiquetas de confidencialidad establecidas para la configuración de sitio y grupo:</span><span class="sxs-lookup"><span data-stu-id="c9868-231">The following apps and services support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="c9868-232">Centros de administración:</span><span class="sxs-lookup"><span data-stu-id="c9868-232">Admin centers:</span></span>

  - <span data-ttu-id="c9868-233">Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9868-233">SharePoint admin center</span></span>
  - <span data-ttu-id="c9868-234">Portal de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c9868-234">Azure Active Directory portal</span></span>
  - <span data-ttu-id="c9868-235">Centro de cumplimiento de Microsoft 365, Centro de seguridad de Microsoft 365 y Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="c9868-235">Microsoft 365 compliance center, Microsoft 365 security center, Security & Compliance Center</span></span>

- <span data-ttu-id="c9868-236">Servicios y aplicaciones de usuario:</span><span class="sxs-lookup"><span data-stu-id="c9868-236">User apps and services:</span></span>

  - <span data-ttu-id="c9868-237">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9868-237">SharePoint</span></span>
  - <span data-ttu-id="c9868-238">Teams</span><span class="sxs-lookup"><span data-stu-id="c9868-238">Teams</span></span>
  - <span data-ttu-id="c9868-239">Outlook en la Web y para Windows, Mac OS, iOS y Android</span><span class="sxs-lookup"><span data-stu-id="c9868-239">Outlook on the web and for Windows, MacOS, iOS, and Android</span></span>
  - <span data-ttu-id="c9868-240">Forms</span><span class="sxs-lookup"><span data-stu-id="c9868-240">Forms</span></span>
  - <span data-ttu-id="c9868-241">Stream</span><span class="sxs-lookup"><span data-stu-id="c9868-241">Stream</span></span>

<span data-ttu-id="c9868-242">Las siguientes aplicaciones y servicios actualmente no son compatibles con las etiquetas de confidencialidad establecidas para la configuración de sitios y grupos:</span><span class="sxs-lookup"><span data-stu-id="c9868-242">The following apps and services don't currently support sensitivity labels configured for sites and group settings:</span></span>

- <span data-ttu-id="c9868-243">Centros de administración:</span><span class="sxs-lookup"><span data-stu-id="c9868-243">Admin centers:</span></span>

  - <span data-ttu-id="c9868-244">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9868-244">Microsoft 365 admin center</span></span>
  - <span data-ttu-id="c9868-245">Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="c9868-245">Teams admin center</span></span>
  - <span data-ttu-id="c9868-246">Centro de administración de Exchange</span><span class="sxs-lookup"><span data-stu-id="c9868-246">Exchange admin center</span></span>

- <span data-ttu-id="c9868-247">Servicios y aplicaciones de usuario:</span><span class="sxs-lookup"><span data-stu-id="c9868-247">User apps and services:</span></span>

  - <span data-ttu-id="c9868-248">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c9868-248">Dynamics 365</span></span>
  - <span data-ttu-id="c9868-249">Yammer</span><span class="sxs-lookup"><span data-stu-id="c9868-249">Yammer</span></span>
  - <span data-ttu-id="c9868-250">Planner</span><span class="sxs-lookup"><span data-stu-id="c9868-250">Planner</span></span>
  - <span data-ttu-id="c9868-251">Proyecto</span><span class="sxs-lookup"><span data-stu-id="c9868-251">Project</span></span>
  - <span data-ttu-id="c9868-252">PowerBI</span><span class="sxs-lookup"><span data-stu-id="c9868-252">PowerBI</span></span>

## <a name="classic-azure-ad-group-classification"></a><span data-ttu-id="c9868-253">Clasificación de grupos de Azure AD clásica</span><span class="sxs-lookup"><span data-stu-id="c9868-253">Classic Azure AD group classification</span></span>

<span data-ttu-id="c9868-254">Microsoft 365 ya no admitirá las antiguas clasificaciones para los nuevos grupos de Microsoft 365 y sitios de SharePoint después de que habilite etiquetas de confidencialidad para contenedores.</span><span class="sxs-lookup"><span data-stu-id="c9868-254">Microsoft 365 no longer supports the old classifications for new Microsoft 365 groups and SharePoint sites after you enable sensitivity labels for containers.</span></span> <span data-ttu-id="c9868-255">Sin embargo, los grupos y sitios existentes que son compatibles con etiquetas de confidencialidad aún mostrarán los valores de clasificación antiguos hasta que los convierta para usar etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="c9868-255">However, existing groups and sites that support sensitivity labels still display the old classification values until you convert them to use sensitivity labels.</span></span>

<span data-ttu-id="c9868-256">Como ejemplo de cómo podría haber utilizado la antigua clasificación de grupos para SharePoint, consulte [Clasificación de sitios "modernos" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="c9868-256">As an example of how you might have used the old group classification for SharePoint, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="c9868-257">Estas clasificaciones se configuraron con Azure AD PowerShell o la biblioteca principal de PnP y definiendo valores para la configuración de `ClassificationList`.</span><span class="sxs-lookup"><span data-stu-id="c9868-257">These classifications were configured by using Azure AD PowerShell or the PnP Core library and defining values for the `ClassificationList` setting.</span></span> <span data-ttu-id="c9868-258">Si su espacio empresarial tiene valores de clasificación definidos, se muestran al ejecutar el siguiente comando desde el módulo de [PowerShell de AzureADPreview](https://www.powershellgallery.com/packages/AzureADPreview):</span><span class="sxs-lookup"><span data-stu-id="c9868-258">If your tenant has classification values defined, they are shown when you run the following command from the [AzureADPreview PowerShell module](https://www.powershellgallery.com/packages/AzureADPreview):</span></span>

```powershell
($setting["ClassificationList"])
```

<span data-ttu-id="c9868-259">Para convertir las clasificaciones antiguas en etiquetas de confidencialidad, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="c9868-259">To convert your old classifications to sensitivity labels, do one of the following:</span></span>

- <span data-ttu-id="c9868-260">Usar etiquetas existentes: especifique la configuración de la etiqueta que desee para los sitios y grupos al editar las etiquetas de confidencialidad existentes que ya están publicadas.</span><span class="sxs-lookup"><span data-stu-id="c9868-260">Use existing labels: Specify the label settings you want for sites and groups by editing existing sensitivity labels that are already published.</span></span>

- <span data-ttu-id="c9868-261">Crear etiquetas nuevas: especifique la configuración de la etiqueta que desee para los sitios y grupos creando y publicando nuevas etiquetas de confidencialidad que tengan los mismos nombres que las de las clasificaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="c9868-261">Create new labels: Specify the label settings you want for sites and groups by creating and publishing new sensitivity labels that have the same names as your existing classifications.</span></span>

<span data-ttu-id="c9868-262">Luego:</span><span class="sxs-lookup"><span data-stu-id="c9868-262">Then:</span></span>

1. <span data-ttu-id="c9868-263">Use PowerShell para aplicar las etiquetas de confidencialidad a los grupos de Microsoft 365 y a los sitios de SharePoint mediante la asignación de nombres.</span><span class="sxs-lookup"><span data-stu-id="c9868-263">Use PowerShell to apply the sensitivity labels to existing Microsoft 365 groups and SharePoint sites by using name mapping.</span></span> <span data-ttu-id="c9868-264">Vea la siguiente sección para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c9868-264">See the next section for instructions.</span></span>

2. <span data-ttu-id="c9868-265">Quitar las clasificaciones antiguas de los grupos y sitios existentes.</span><span class="sxs-lookup"><span data-stu-id="c9868-265">Remove the old classifications from the existing groups and sites.</span></span>

<span data-ttu-id="c9868-266">Aunque no se puede impedir que los usuarios creen grupos nuevos en aplicaciones y servicios que aún no admiten las etiquetas de confidencialidad, puede ejecutar un script de PowerShell periódico para buscar grupos nuevos que los usuarios han creado con las clasificaciones anteriores y convertirlos para usar etiquetas de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="c9868-266">Although you can't prevent users from creating new groups in apps and services that don't yet support sensitivity labels, you can run a recurring PowerShell script to look for new groups that users have created with the old classifications, and convert these to use sensitivity labels.</span></span>

<span data-ttu-id="c9868-267">Para ayudarle a administrar la coexistencia de etiquetas de confidencialidad y clasificaciones de Azure AD para sitios y grupos, consulte [Clasificación y etiquetas de confidencialidad de Azure Active Directory para grupos de Microsoft 365](migrate-aad-classification-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="c9868-267">To help you manage the coexistence of sensitivity labels and Azure AD classifications for sites and groups, see [Azure Active Directory classification and sensitivity labels for Microsoft 365 groups](migrate-aad-classification-sensitivity-labels.md).</span></span>

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a><span data-ttu-id="c9868-268">Usar PowerShell para convertir clasificaciones de grupos de Microsoft 365 a etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="c9868-268">Use PowerShell to convert classifications for Microsoft 365 groups to sensitivity labels</span></span>

1. <span data-ttu-id="c9868-269">En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9868-269">First, [connect to Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

   <span data-ttu-id="c9868-270">Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:</span><span class="sxs-lookup"><span data-stu-id="c9868-270">For example, in a PowerShell session that you run as administrator, sign in with a global administrator account:</span></span>

2. <span data-ttu-id="c9868-271">Consiga la lista de etiquetas de sensibilidad y sus GUIDs usando el cmdlet[Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps):</span><span class="sxs-lookup"><span data-stu-id="c9868-271">Get the list of sensitivity labels and their GUIDs by using the [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) cmdlet:</span></span>

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. <span data-ttu-id="c9868-272">Tome nota de los GUID para las etiquetas de confidencialidad que quiere aplicar a los grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9868-272">Make a note of the GUIDs for the sensitivity labels you want to apply to your Microsoft 365 groups.</span></span>

4. <span data-ttu-id="c9868-273">Ahora [conéctese a PowerShell en línea de Exchange](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) en una ventana independiente de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9868-273">Now [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) in a separate Windows PowerShell window.</span></span>

5. <span data-ttu-id="c9868-274">Use el comando siguiente como ejemplo para obtener la lista de grupos que actualmente tienen la clasificación de "general":</span><span class="sxs-lookup"><span data-stu-id="c9868-274">Use the following command as an example to get the list of groups that currently have the classification of "General":</span></span>

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. <span data-ttu-id="c9868-275">Para cada grupo, agregue la nueva etiqueta de sensibilidad GUID.</span><span class="sxs-lookup"><span data-stu-id="c9868-275">For each group, add the new sensitivity label GUID.</span></span> <span data-ttu-id="c9868-276">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9868-276">For example:</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. <span data-ttu-id="c9868-277">Repita los pasos 5 y 6 para el resto de sus clasificaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="c9868-277">Repeat steps 5 and 6 for your remaining group classifications.</span></span>

## <a name="auditing-sensitivity-label-activities"></a><span data-ttu-id="c9868-278">Auditar actividades de etiqueta de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="c9868-278">Auditing sensitivity label activities</span></span>

<span data-ttu-id="c9868-279">Si alguien carga un documento en un sitio protegido con una etiqueta de confidencialidad y el documento tiene una etiqueta de confidencialidad de [mayor prioridad](sensitivity-labels.md#label-priority-order-matters) que la etiqueta de confidencialidad que se aplica al sitio, esta acción no está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="c9868-279">If somebody uploads a document to a site that's protected with a sensitivity label and their document has a [higher priority](sensitivity-labels.md#label-priority-order-matters) sensitivity label than the sensitivity label applied to the site, this action isn't blocked.</span></span> <span data-ttu-id="c9868-280">Por ejemplo, aplicó la etiqueta **general** a un sitio de SharePoint y alguien carga en este sitio un documento etiquetado como **confidencial**.</span><span class="sxs-lookup"><span data-stu-id="c9868-280">For example, you've applied the **General** label to a SharePoint site, and somebody uploads to this site a document labeled **Confidential**.</span></span> <span data-ttu-id="c9868-281">Debido a que una etiqueta de confidencialidad con mayor prioridad identifica el contenido que es más confidencial que el contenido que tiene un orden de menor prioridad, esta situación podría ser un problema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c9868-281">Because a sensitivity label with a higher priority identifies content that is more sensitivity than content that has a lower priority order, this situation could be a security concern.</span></span>

<span data-ttu-id="c9868-282">Aunque la acción no está bloqueada, se audita y genera automáticamente un correo electrónico a la persona que cargó el documento y el administrador del sitio.</span><span class="sxs-lookup"><span data-stu-id="c9868-282">Although the action isn't blocked, it is audited and automatically generates an email to the person who uploaded the document and the site administrator.</span></span> <span data-ttu-id="c9868-283">Como resultado, tanto el usuario como los administradores pueden identificar los documentos que no están alineados con la prioridad de las etiquetas y tomar las medidas necesarias.</span><span class="sxs-lookup"><span data-stu-id="c9868-283">As a result, both the user and administrators can identify documents that have this misalignment of label priority and take action if needed.</span></span> <span data-ttu-id="c9868-284">Por ejemplo, eliminar o mover el documento cargado del sitio.</span><span class="sxs-lookup"><span data-stu-id="c9868-284">For example, delete or move the uploaded document from the site.</span></span>

<span data-ttu-id="c9868-285">No sería un problema de seguridad si el documento tiene una etiqueta de confidencialidad de menor prioridad que la etiqueta de confidencialidad aplicada al sitio.</span><span class="sxs-lookup"><span data-stu-id="c9868-285">It wouldn't be a security concern if the document has a lower priority sensitivity label than the sensitivity label applied to the site.</span></span> <span data-ttu-id="c9868-286">Por ejemplo, un documento con la etiqueta **general** se carga en un sitio con la etiqueta **confidencial**.</span><span class="sxs-lookup"><span data-stu-id="c9868-286">For example, a document labeled **General** is uploaded to a site labeled **Confidential**.</span></span> <span data-ttu-id="c9868-287">En este escenario, no se generarán ni un evento de auditoría, ni un correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c9868-287">In this scenario, an auditing event and email aren't generated.</span></span>

<span data-ttu-id="c9868-288">Para buscar el registro de auditoría para este evento, busque **Desfase detectado de la confidencialidad del documento** en la categoría de las **actividades de archivos y páginas**.</span><span class="sxs-lookup"><span data-stu-id="c9868-288">To search the audit log for this event, look for **Detected document sensitivity mismatch** from the **File and page activities** category.</span></span>

<span data-ttu-id="c9868-289">El correo electrónico generado automáticamente tiene el asunto **Etiqueta de confidencialidad no compatible detectado** y el mensaje de correo electrónico explica que la etiqueta no coincide con un vínculo al documento cargado y al sitio.</span><span class="sxs-lookup"><span data-stu-id="c9868-289">The automatically generated email has the subject **Incompatible sensitivity label detected** and the email message explains the labeling mismatch with a link to the uploaded document and site.</span></span> <span data-ttu-id="c9868-290">También contiene un vínculo a la documentación en el que se explica cómo los usuarios pueden cambiar la etiqueta de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="c9868-290">It also contains a documentation link that explains how users can change the sensitivity label.</span></span> <span data-ttu-id="c9868-291">Actualmente, estos correos electrónicos automatizados no se pueden deshabilitar o personalizar.</span><span class="sxs-lookup"><span data-stu-id="c9868-291">Currently, these automated emails cannot be disabled or customized.</span></span>

<span data-ttu-id="c9868-292">Cuando alguien agrega o quita una etiqueta de confidencialidad a un sitio o grupo, estas actividades también se auditan, pero sin generar un correo electrónico automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c9868-292">When somebody adds or removes a sensitivity label to or from a site or group, these activities are also audited but without automatically generating an email.</span></span>

<span data-ttu-id="c9868-293">Todos estos eventos de auditoría se pueden encontrar en la categoría [Actividades de etiqueta de confidencialidad](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities).</span><span class="sxs-lookup"><span data-stu-id="c9868-293">All these auditing events can be found in the [Sensitivity label activities](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) category.</span></span> <span data-ttu-id="c9868-294">Para obtener instrucciones sobre cómo buscar el registro de auditoría, vea [buscar el registro de auditoría en el Centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="c9868-294">For instructions to search the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="how-to-disable-sensitivity-labels-for-containers"></a><span data-ttu-id="c9868-295">Cómo deshabilitar etiquetas de confidencialidad para contenedores</span><span class="sxs-lookup"><span data-stu-id="c9868-295">How to disable sensitivity labels for containers</span></span>

<span data-ttu-id="c9868-296">Puede desactivar las etiquetas de confidencialidad para Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint siguiendo las mismas instrucciones que se indican en [Habilitar la compatibilidad con etiquetas de confidencialidad en PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9868-296">You can turn off sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites by using the same instructions from [Enable sensitivity label support in PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell).</span></span> <span data-ttu-id="c9868-297">Sin embargo, para deshabilitar la característica, en el paso 5, especifique `$setting["EnableMIPLabels"] = "False"`.</span><span class="sxs-lookup"><span data-stu-id="c9868-297">However, to disable the feature, in step 5, specify `$setting["EnableMIPLabels"] = "False"`.</span></span>

<span data-ttu-id="c9868-298">Además de ocultar la página **Configuración de sitios y grupos** cuando cree o edite etiquetas de confidencialidad, esta acción revierte la propiedad que usan los contenedores para su configuración.</span><span class="sxs-lookup"><span data-stu-id="c9868-298">In addition to hiding the **Sites and group settings** page when you create or edit sensitivity labels, this action reverts which property the containers use for their configuration.</span></span> <span data-ttu-id="c9868-299">Al habilitar las etiquetas de confidencialidad para Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint se cambia la propiedad **Clasificación** (usada para la [clasificación de grupos de Azure AD](#classic-azure-ad-group-classification)) a **Confidencialidad**.</span><span class="sxs-lookup"><span data-stu-id="c9868-299">Enabling sensitivity labels for Microsoft Teams, Microsoft 365 groups, and SharePoint sites switches the property used from **Classification** (used for [Azure AD group classification](#classic-azure-ad-group-classification)) to **Sensitivity**.</span></span> <span data-ttu-id="c9868-300">Cuando deshabilita las etiquetas de confidencialidad para contenedores, estos ignoran la propiedad Confidencialidad y vuelven a usar la propiedad Clasificación.</span><span class="sxs-lookup"><span data-stu-id="c9868-300">When you disable sensitivity labels for containers, the containers ignore the Sensitivity property and use the Classification property again.</span></span>

<span data-ttu-id="c9868-301">Esto quiere decir que no se exigirá la configuración de etiquetas para sitios y grupos que se aplicó previamente a los contenedores, y los contenedores ya no mostrarán las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="c9868-301">This means that any label settings from sites and groups previously applied to containers won't be enforced, and containers no longer display the labels.</span></span>

<span data-ttu-id="c9868-302">Si dichos contenedores tienen valores de clasificación de Azure AD aplicados, estos volverán a usar las clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="c9868-302">If these containers have Azure AD classification values applied to them, the containers revert to using the classifications again.</span></span> <span data-ttu-id="c9868-303">Tenga en cuenta que cualquier nuevo sitio o grupo creado después de habilitar la característica no mostrará una etiqueta ni tendrá una clasificación.</span><span class="sxs-lookup"><span data-stu-id="c9868-303">Be aware that any new sites or groups that were created after enabling the feature won't display a label or have a classification.</span></span> <span data-ttu-id="c9868-304">Ahora puede aplicar valores de clasificación tanto a estos como a los nuevos contenedores.</span><span class="sxs-lookup"><span data-stu-id="c9868-304">For these containers, and any new containers, you can now apply classification values.</span></span> <span data-ttu-id="c9868-305">Para obtener más información, consulte [Clasificación de sitios "moderna" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) y [Crear clasificaciones para grupos de Office en su organización](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span><span class="sxs-lookup"><span data-stu-id="c9868-305">For more information, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) and [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c9868-306">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c9868-306">Additional resources</span></span>

<span data-ttu-id="c9868-307">Consulte la grabación y las preguntas contestadas sobre el [Uso de etiquetas de sensibilidad con Microsoft Teams, grupos de O365 y sitios de SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span><span class="sxs-lookup"><span data-stu-id="c9868-307">See the webinar recording and answered questions for [Using Sensitivity labels with Microsoft Teams, O365 Groups and SharePoint Online sites](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).</span></span>

<span data-ttu-id="c9868-308">Este seminario web se grabó cuando la característica aún estaba en la versión preliminar, por lo que es posible que observe algunas discrepancias en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c9868-308">This webinar was recorded when the feature was still in preview, so you might notice some discrepancies in the UI.</span></span> <span data-ttu-id="c9868-309">Sin embargo, la información de esta característica aún es precisa, con las nuevas funciones que se documentan en esta página.</span><span class="sxs-lookup"><span data-stu-id="c9868-309">However, the information for this feature is still accurate, with any new capabilities documented on this page.</span></span>
