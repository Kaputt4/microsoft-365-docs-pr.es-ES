---
title: Administrar la configuración de los Scripts de Office
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración Office scripts para los usuarios de su organización.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572314"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="09955-103">Administrar la configuración de los Scripts de Office</span><span class="sxs-lookup"><span data-stu-id="09955-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="09955-104">[Office Scripts permite](/office/dev/scripts)a los usuarios automatizar las tareas grabando, editando y ejecutando scripts en Excel en la web.</span><span class="sxs-lookup"><span data-stu-id="09955-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="09955-105">Office Los scripts funcionan Power Automate y los usuarios ejecutan scripts en libros mediante el conector Excel Online (empresa).</span><span class="sxs-lookup"><span data-stu-id="09955-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="09955-106">Microsoft 365 administradores pueden administrar la configuración Office scripts desde el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="09955-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="09955-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="09955-107">Before you begin</span></span>

- <span data-ttu-id="09955-108">Para administrar Office de scripts, debe ser un administrador global. Para obtener más información, vea [About admin roles](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="09955-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="09955-109">Asegúrese de que los usuarios de su organización tienen una licencia válida para un plan Microsoft 365 o Office 365 comercial o EDU que incluya acceso Office aplicaciones de escritorio, como uno de los siguientes planes:</span><span class="sxs-lookup"><span data-stu-id="09955-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="09955-110">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="09955-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="09955-111">Aplicaciones de Microsoft 365 para negocios</span><span class="sxs-lookup"><span data-stu-id="09955-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="09955-112">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="09955-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="09955-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="09955-113">Office 365 E3</span></span>
    - <span data-ttu-id="09955-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="09955-114">Office 365 E5</span></span>
    - <span data-ttu-id="09955-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="09955-115">Office 365 A3</span></span>
    - <span data-ttu-id="09955-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="09955-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="09955-117">Administrar la disponibilidad de Office scripts y el uso compartido de scripts</span><span class="sxs-lookup"><span data-stu-id="09955-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="09955-118">En el centro Microsoft 365 administración, vaya a la **pestaña Servicios** Configuración configuración de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a> la organización.</span><span class="sxs-lookup"><span data-stu-id="09955-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="09955-119">Seleccione **Office scripts**.</span><span class="sxs-lookup"><span data-stu-id="09955-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="09955-120">Office Los scripts están activados de forma predeterminada y todos los usuarios de la organización pueden acceder y usar la característica y compartir scripts.</span><span class="sxs-lookup"><span data-stu-id="09955-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="09955-121">Para desactivar Office scripts de la organización, desactive la casilla Permitir a los usuarios automatizar sus tareas **en Excel en la Web.**</span><span class="sxs-lookup"><span data-stu-id="09955-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="09955-122">Si ha desactivado anteriormente Office Scripts para su organización y desea volver **a** activarlo, seleccione Permitir que los usuarios automaticen sus tareas en Excel en la Web y, a continuación, especifique quién puede acceder y usar la característica:</span><span class="sxs-lookup"><span data-stu-id="09955-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="09955-123">Para permitir que todos los usuarios de la organización accedan y usen Office scripts, **deje** todos (el valor predeterminado) seleccionado.</span><span class="sxs-lookup"><span data-stu-id="09955-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="09955-124">Para permitir que solo los miembros de un grupo específico accedan y usen scripts de Office, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="09955-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="09955-125">Puede agregar solo un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="09955-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="09955-126">Microsoft 365 grupo</span><span class="sxs-lookup"><span data-stu-id="09955-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="09955-127">Grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="09955-127">Distribution group</span></span>
        - <span data-ttu-id="09955-128">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="09955-128">Security group</span></span>
        - <span data-ttu-id="09955-129">Grupo de seguridad habilitado para correo</span><span class="sxs-lookup"><span data-stu-id="09955-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="09955-130">Para obtener más información sobre los diferentes tipos de grupos, vea [Comparar grupos](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="09955-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="09955-131">Para permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de la organización, seleccione Permitir que los usuarios con acceso **a Office Scripts** compartan sus scripts con otros usuarios de la organización .</span><span class="sxs-lookup"><span data-stu-id="09955-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="09955-132">No se permite el uso compartido de scripts fuera de una organización.</span><span class="sxs-lookup"><span data-stu-id="09955-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="09955-133">Si más adelante desactiva el uso compartido de scripts para su organización, los usuarios podrán ejecutar scripts compartidos previamente.</span><span class="sxs-lookup"><span data-stu-id="09955-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="09955-134">Especifica qué usuarios con acceso a Office scripts pueden compartir sus scripts:</span><span class="sxs-lookup"><span data-stu-id="09955-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="09955-135">Para permitir que todos los usuarios con acceso a Office scripts compartan sus scripts, deje **todos** (el valor predeterminado) seleccionado.</span><span class="sxs-lookup"><span data-stu-id="09955-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="09955-136">Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office compartan sus scripts, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="09955-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="09955-137">Puede agregar solo un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="09955-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="09955-138">Microsoft 365 grupo</span><span class="sxs-lookup"><span data-stu-id="09955-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="09955-139">Grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="09955-139">Distribution group</span></span>
        - <span data-ttu-id="09955-140">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="09955-140">Security group</span></span>
        - <span data-ttu-id="09955-141">Grupo de seguridad habilitado para correo</span><span class="sxs-lookup"><span data-stu-id="09955-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="09955-142">Para obtener más información sobre los diferentes tipos de grupos, vea [Comparar grupos](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="09955-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="09955-143">Para permitir que los usuarios ejecuten sus scripts Office dentro de los flujos de Power Automate, seleccione Permitir que los usuarios con acceso a Office Scripts ejecuten sus **scripts con Power Automate**.</span><span class="sxs-lookup"><span data-stu-id="09955-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="09955-144">Esto permite a los usuarios agregar pasos de flujo con la opción ejecutar del conector Excel línea [(empresa).](/connectors/excelonlinebusiness) </span><span class="sxs-lookup"><span data-stu-id="09955-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="09955-145">Para permitir que todos los usuarios con acceso a Office scripts usen sus scripts en flujos, **deje** todos (el valor predeterminado) seleccionado.</span><span class="sxs-lookup"><span data-stu-id="09955-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="09955-146">Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office usen sus scripts en flujos, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="09955-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="09955-147">Puede agregar solo un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="09955-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="09955-148">Microsoft 365 grupo</span><span class="sxs-lookup"><span data-stu-id="09955-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="09955-149">Grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="09955-149">Distribution group</span></span>
        - <span data-ttu-id="09955-150">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="09955-150">Security group</span></span>
        - <span data-ttu-id="09955-151">Grupo de seguridad habilitado para correo</span><span class="sxs-lookup"><span data-stu-id="09955-151">Mail-enabled security group</span></span>

        <span data-ttu-id="09955-152">Para obtener más información sobre los diferentes tipos de grupos, vea [Comparar grupos](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="09955-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="09955-153">Para obtener más información sobre cómo usar Office scripts con Power Automate, vea [Ejecutar Office scripts con Power Automate](/office/dev/scripts/develop/power-automate-integration).</span><span class="sxs-lookup"><span data-stu-id="09955-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="09955-154">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="09955-154">Select **Save**.</span></span>

    <span data-ttu-id="09955-155">Los cambios realizados en la configuración de scripts Office pueden tardar hasta 48 horas en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="09955-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="09955-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="09955-156">Next steps</span></span>

<span data-ttu-id="09955-157">Dado que Office Scripts funciona con Power Automate, se recomienda revisar las directivas de prevención de pérdida de datos (DLP) existentes para garantizar que los datos de la organización permanecen protegidos mientras los usuarios usan Office scripts.</span><span class="sxs-lookup"><span data-stu-id="09955-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="09955-158">Para obtener más información, vea [Directivas de prevención de pérdida de datos (DLP).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="09955-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="09955-159">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="09955-159">Related content</span></span>

<span data-ttu-id="09955-160">[Office documentación técnica de scripts (página](/office/dev/scripts/) de vínculos)</span><span class="sxs-lookup"><span data-stu-id="09955-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="09955-161">[Introducción a Office scripts en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo)</span><span class="sxs-lookup"><span data-stu-id="09955-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="09955-162">[Compartir Office scripts en Excel para web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo)</span><span class="sxs-lookup"><span data-stu-id="09955-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="09955-163">[Grabar, editar y crear scripts Office en Excel en la Web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)</span><span class="sxs-lookup"><span data-stu-id="09955-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
