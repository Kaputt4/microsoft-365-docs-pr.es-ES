---
title: Administrar la configuración de scripts de Office
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
description: Obtenga información sobre cómo administrar la configuración de scripts de Office para los usuarios de su organización.
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300843"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="6745b-103">Administrar la configuración de scripts de Office</span><span class="sxs-lookup"><span data-stu-id="6745b-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="6745b-104">Scripts de Office permite a los usuarios automatizar tareas mediante la grabación, la edición y la ejecución de scripts en Excel en la Web.</span><span class="sxs-lookup"><span data-stu-id="6745b-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="6745b-105">Los scripts de Office funcionan con Power Automates y los usuarios ejecutan scripts en libros mediante el conector de Excel online (Business).</span><span class="sxs-lookup"><span data-stu-id="6745b-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="6745b-106">Los administradores de Microsoft 365 pueden administrar la configuración de las secuencias de comandos de Office desde el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6745b-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6745b-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="6745b-107">Before you begin</span></span>

- <span data-ttu-id="6745b-108">Para administrar la configuración de las secuencias de comandos de Office, debe ser un administrador global. Para obtener más información, vea [acerca de los roles de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6745b-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="6745b-109">Asegúrese de que los usuarios de la organización tengan una licencia válida para un plan comercial o EDU de Microsoft 365 u Office 365 que incluya acceso a las aplicaciones de escritorio de Office, como uno de los siguientes planes:</span><span class="sxs-lookup"><span data-stu-id="6745b-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="6745b-110">Microsoft 365 Empresa Estándar</span><span class="sxs-lookup"><span data-stu-id="6745b-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="6745b-111">Aplicaciones de Microsoft 365 para negocios</span><span class="sxs-lookup"><span data-stu-id="6745b-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="6745b-112">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6745b-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="6745b-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="6745b-113">Office 365 E3</span></span>
    - <span data-ttu-id="6745b-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="6745b-114">Office 365 E5</span></span>
    - <span data-ttu-id="6745b-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="6745b-115">Office 365 A3</span></span>
    - <span data-ttu-id="6745b-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="6745b-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="6745b-117">Administrar la disponibilidad de scripts de Office y el uso compartido de scripts</span><span class="sxs-lookup"><span data-stu-id="6745b-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="6745b-118">En el centro de administración de Microsoft 365, vaya a la pestaña **configuración** \> **org Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .</span><span class="sxs-lookup"><span data-stu-id="6745b-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="6745b-119">Seleccione **scripts de Office**.</span><span class="sxs-lookup"><span data-stu-id="6745b-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="6745b-120">Los scripts de Office están activados de forma predeterminada y todos los usuarios de la organización pueden obtener acceso y usar la característica y compartir scripts.</span><span class="sxs-lookup"><span data-stu-id="6745b-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="6745b-121">Para desactivar los scripts de Office para su organización, desactive la casilla de verificación **permitir que los usuarios automaticen sus tareas en Excel en la web** .</span><span class="sxs-lookup"><span data-stu-id="6745b-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="6745b-122">Si ha desactivado anteriormente scripts de Office para su organización y desea volver a activarlo, seleccione **permitir a los usuarios automatizar sus tareas en Excel en la web**y, a continuación, especifique quién puede tener acceso a la característica y usarla:</span><span class="sxs-lookup"><span data-stu-id="6745b-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="6745b-123">Para permitir que todos los usuarios de su organización puedan tener acceso y usar scripts de Office, deje seleccionada la opción **todos** (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="6745b-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span> 

    - <span data-ttu-id="6745b-124">Para permitir que solo los miembros de un grupo específico tengan acceso y usen scripts de Office, seleccione **grupo específico**y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="6745b-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="6745b-125">Solo puede Agregar un grupo a la lista de permitidos y debe ser de uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="6745b-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="6745b-126">Grupo 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6745b-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="6745b-127">Grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="6745b-127">Distribution group</span></span>
        - <span data-ttu-id="6745b-128">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="6745b-128">Security group</span></span>
        - <span data-ttu-id="6745b-129">Grupo de seguridad habilitado para correo</span><span class="sxs-lookup"><span data-stu-id="6745b-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="6745b-130">Para obtener más información acerca de los distintos tipos de grupos, vea [comparar grupos](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6745b-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="6745b-131">Para permitir que los usuarios con acceso a los scripts de Office compartan sus scripts con otras personas de la organización, seleccione **permitir a los usuarios tener acceso a los scripts de Office que comparten sus scripts con otros miembros de la organización**.</span><span class="sxs-lookup"><span data-stu-id="6745b-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="6745b-132">No se permite compartir scripts fuera de una organización.</span><span class="sxs-lookup"><span data-stu-id="6745b-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="6745b-133">Si más tarde desactiva el uso compartido de scripts para su organización, los usuarios podrán seguir ejecutando scripts previamente compartidos.</span><span class="sxs-lookup"><span data-stu-id="6745b-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="6745b-134">Especifique qué usuarios con acceso a los scripts de Office pueden compartir sus scripts:</span><span class="sxs-lookup"><span data-stu-id="6745b-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="6745b-135">Para permitir que todos los usuarios con acceso a los scripts de Office compartan sus scripts, deje seleccionada la opción **todos** (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="6745b-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="6745b-136">Para permitir que solo los miembros de un grupo específico tengan acceso a los scripts de Office para compartir sus scripts, seleccione **grupo específico**y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos.</span><span class="sxs-lookup"><span data-stu-id="6745b-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="6745b-137">Solo puede Agregar un grupo a la lista de permitidos y debe ser de uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="6745b-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="6745b-138">Grupo 365 de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6745b-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="6745b-139">Grupo de distribución</span><span class="sxs-lookup"><span data-stu-id="6745b-139">Distribution group</span></span>
        - <span data-ttu-id="6745b-140">Grupo de seguridad</span><span class="sxs-lookup"><span data-stu-id="6745b-140">Security group</span></span>
        - <span data-ttu-id="6745b-141">Grupo de seguridad habilitado para correo</span><span class="sxs-lookup"><span data-stu-id="6745b-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="6745b-142">Para obtener más información acerca de los distintos tipos de grupos, vea [comparar grupos](../create-groups/compare-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6745b-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="6745b-143">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6745b-143">Select **Save**.</span></span>

    <span data-ttu-id="6745b-144">Los cambios en la configuración de script de Office pueden tardar hasta 48 horas en aplicarse.</span><span class="sxs-lookup"><span data-stu-id="6745b-144">It can take up to 48 hours for changes to Office Script settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6745b-145">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6745b-145">Next steps</span></span>

<span data-ttu-id="6745b-146">Como los scripts de Office funcionan con la automatización de la alimentación, le recomendamos que revise las directivas existentes de prevención de pérdida de datos (DLP) para asegurarse de que los datos de la organización sigan protegidos mientras los usuarios usan scripts de Office.</span><span class="sxs-lookup"><span data-stu-id="6745b-146">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="6745b-147">Para obtener más información, consulte [directivas de prevención de pérdida de datos (DLP)](/power-automate/prevent-data-loss).</span><span class="sxs-lookup"><span data-stu-id="6745b-147">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="6745b-148">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="6745b-148">Related content</span></span>

<span data-ttu-id="6745b-149">[Documentación técnica de scripts de Office](/office/dev/scripts/) (página vínculo) </span><span class="sxs-lookup"><span data-stu-id="6745b-149">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="6745b-150">[Introducción a los scripts de Office en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo) </span><span class="sxs-lookup"><span data-stu-id="6745b-150">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="6745b-151">[Uso compartido de scripts de Office en Excel para la web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo) </span><span class="sxs-lookup"><span data-stu-id="6745b-151">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="6745b-152">[Registro, edición y creación de scripts de Office en Excel en la web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)</span><span class="sxs-lookup"><span data-stu-id="6745b-152">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>