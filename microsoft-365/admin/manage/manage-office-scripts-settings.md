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
description: Obtenga información sobre cómo administrar Office configuración de scripts para usuarios de su organización.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572314"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="7fdfc-103">Administrar la configuración de los Scripts de Office</span><span class="sxs-lookup"><span data-stu-id="7fdfc-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="7fdfc-104">[Office Scripts](/office/dev/scripts)permite a los usuarios automatizar tareas grabando, editando y ejecutando scripts en Excel en la web.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-104">[Office Scripts](/office/dev/scripts)‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="7fdfc-105">Office Scripts funciona con Power Automate y los usuarios ejecutan scripts en libros de trabajo mediante el conector Excel online (business).</span><span class="sxs-lookup"><span data-stu-id="7fdfc-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="7fdfc-106">Microsoft 365 administradores pueden administrar la configuración de scripts de Office desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7fdfc-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="7fdfc-107">Before you begin</span></span>

- <span data-ttu-id="7fdfc-108">Para administrar Office configuración de scripts, debe ser administrador global. Para obtener más información, consulte [Acerca de los roles de administrador.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="7fdfc-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="7fdfc-109">Asegúrese de que los usuarios de su organización tengan una licencia válida para un plan comercial o EDU Microsoft 365 o Office 365 que incluya acceso a aplicaciones de escritorio Office, como uno de los siguientes planes:</span><span class="sxs-lookup"><span data-stu-id="7fdfc-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="7fdfc-110">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="7fdfc-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="7fdfc-111">Aplicaciones de Microsoft 365 para negocios</span><span class="sxs-lookup"><span data-stu-id="7fdfc-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="7fdfc-112">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7fdfc-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="7fdfc-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="7fdfc-113">Office 365 E3</span></span>
    - <span data-ttu-id="7fdfc-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="7fdfc-114">Office 365 E5</span></span>
    - <span data-ttu-id="7fdfc-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="7fdfc-115">Office 365 A3</span></span>
    - <span data-ttu-id="7fdfc-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="7fdfc-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="7fdfc-117">Administrar la disponibilidad de scripts de Office y compartir scripts</span><span class="sxs-lookup"><span data-stu-id="7fdfc-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="7fdfc-118">En el Centro de administración de Microsoft 365, vaya a la pestaña Servicios de configuración **de Configuración** \> **org.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a></span><span class="sxs-lookup"><span data-stu-id="7fdfc-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="7fdfc-119">Seleccione **Office Scripts**.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="7fdfc-120">Office Los scripts están activados de forma predeterminada y todos los miembros de su organización pueden acceder y usar la característica y compartir scripts.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="7fdfc-121">Para desactivar Office scripts para su organización, desactive la casilla **Permitir que los usuarios automaticen sus tareas en Excel en la Web.**</span><span class="sxs-lookup"><span data-stu-id="7fdfc-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="7fdfc-122">Si previamente desactive Office Scripts para su organización y desea volver a activarlo, seleccione Permitir que **los usuarios automaticen sus tareas en Excel en la Web** y, a continuación, especifique quién puede acceder y usar la característica:</span><span class="sxs-lookup"><span data-stu-id="7fdfc-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="7fdfc-123">Para permitir que todos los usuarios de su organización tengan acceso y usen scripts Office, deje seleccionados **Todos** (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7fdfc-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7fdfc-124">Para permitir que solo los miembros de un grupo específico tengan acceso y utilicen scripts Office, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7fdfc-125">Puede agregar solo un grupo a la lista allow y debe ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="7fdfc-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7fdfc-126">grupo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7fdfc-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="7fdfc-127">Grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="7fdfc-127">Distribution group</span></span>
        - <span data-ttu-id="7fdfc-128">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="7fdfc-128">Security group</span></span>
        - <span data-ttu-id="7fdfc-129">Grupo de seguridad habilitado para correo</span><span class="sxs-lookup"><span data-stu-id="7fdfc-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="7fdfc-130">Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7fdfc-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="7fdfc-131">Para permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de la organización, seleccione **Permitir que los usuarios con acceso a scripts Office compartan sus scripts con otros usuarios de la organización.**</span><span class="sxs-lookup"><span data-stu-id="7fdfc-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="7fdfc-132">No se permite compartir scripts fuera de una organización.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="7fdfc-133">Si posteriormente desactiva el uso compartido de scripts para su organización, los usuarios podrán ejecutar scripts compartidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="7fdfc-134">Especifique qué usuarios con acceso a Office Scripts pueden compartir sus scripts:</span><span class="sxs-lookup"><span data-stu-id="7fdfc-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="7fdfc-135">Para permitir que todos los usuarios con acceso a scripts de Office compartan sus scripts, **deje** todos (el valor predeterminado) seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7fdfc-136">Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office compartan sus scripts, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7fdfc-137">Puede agregar solo un grupo a la lista allow y debe ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="7fdfc-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7fdfc-138">grupo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7fdfc-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="7fdfc-139">Grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="7fdfc-139">Distribution group</span></span>
        - <span data-ttu-id="7fdfc-140">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="7fdfc-140">Security group</span></span>
        - <span data-ttu-id="7fdfc-141">Grupo de seguridad habilitado para correo</span><span class="sxs-lookup"><span data-stu-id="7fdfc-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="7fdfc-142">Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7fdfc-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="7fdfc-143">Para permitir a los usuarios ejecutar sus scripts de Office dentro de flujos de Power Automate, seleccione **Permitir a los usuarios con acceso a Office Scripts ejecutar sus scripts con Power Automate**.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="7fdfc-144">Esto permite a los usuarios agregar pasos de flujo con la opción **ejecutar script** [del conector en línea (empresarial) de Excel.](/connectors/excelonlinebusiness)</span><span class="sxs-lookup"><span data-stu-id="7fdfc-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="7fdfc-145">Para permitir que todos los usuarios con acceso a scripts Office utilicen sus scripts en flujos, **deje** todos (el valor predeterminado) seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="7fdfc-146">Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office utilicen sus scripts en flujos, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="7fdfc-147">Puede agregar solo un grupo a la lista allow y debe ser uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="7fdfc-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="7fdfc-148">grupo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7fdfc-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="7fdfc-149">Grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="7fdfc-149">Distribution group</span></span>
        - <span data-ttu-id="7fdfc-150">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="7fdfc-150">Security group</span></span>
        - <span data-ttu-id="7fdfc-151">Grupo de seguridad habilitado para correo</span><span class="sxs-lookup"><span data-stu-id="7fdfc-151">Mail-enabled security group</span></span>

        <span data-ttu-id="7fdfc-152">Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7fdfc-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="7fdfc-153">Para obtener más información sobre el uso de scripts de Office con Power Automate, consulte [Ejecutar scripts de Office con Power Automate](/office/dev/scripts/develop/power-automate-integration).</span><span class="sxs-lookup"><span data-stu-id="7fdfc-153">To learn more about using Office Scripts with Power Automate, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="7fdfc-154">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-154">Select **Save**.</span></span>

    <span data-ttu-id="7fdfc-155">Los cambios realizados en Office configuración de scripts pueden tardar hasta 48 horas en surtirse efecto.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7fdfc-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7fdfc-156">Next steps</span></span>

<span data-ttu-id="7fdfc-157">Dado que Office scripts funciona con Power Automate, se recomienda revisar las directivas de prevención de pérdida de datos (DLP) existentes para asegurarse de que los datos de su organización permanecen protegidos mientras los usuarios usan scripts Office.</span><span class="sxs-lookup"><span data-stu-id="7fdfc-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="7fdfc-158">Para obtener más información, consulte [Directivas de prevención de pérdida de datos (DLP).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="7fdfc-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="7fdfc-159">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="7fdfc-159">Related content</span></span>

<span data-ttu-id="7fdfc-160">[Office Documentación técnica de scripts](/office/dev/scripts/) (página de enlace)</span><span class="sxs-lookup"><span data-stu-id="7fdfc-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="7fdfc-161">[Introducción a Office Scripts en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo)</span><span class="sxs-lookup"><span data-stu-id="7fdfc-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="7fdfc-162">[Compartir scripts de Office en Excel para la Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo)</span><span class="sxs-lookup"><span data-stu-id="7fdfc-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="7fdfc-163">[Grabar, editar y crear scripts Office en Excel en la Web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)</span><span class="sxs-lookup"><span data-stu-id="7fdfc-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
