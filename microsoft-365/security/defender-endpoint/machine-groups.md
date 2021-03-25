---
title: Crear y administrar grupos de dispositivos en ATP de Microsoft Defender
description: Crear grupos de dispositivos y establecer niveles de corrección automatizados en ellos mediante la confidción de las reglas que se aplican en el grupo
keywords: grupos de dispositivos, grupos, corrección, nivel, reglas, grupo de aad, rol, asignación, clasificación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dfc7c04bbde2b7061c92f5a25115b75a2f5b47b5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074339"
---
# <a name="create-and-manage-device-groups"></a><span data-ttu-id="1eea8-104">Crear y administrar grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="1eea8-104">Create and manage device groups</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1eea8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1eea8-105">**Applies to:**</span></span>
- <span data-ttu-id="1eea8-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1eea8-106">Azure Active Directory</span></span>
- <span data-ttu-id="1eea8-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="1eea8-107">Office 365</span></span>

> <span data-ttu-id="1eea8-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="1eea8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1eea8-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1eea8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="1eea8-110">En un escenario de empresa, los equipos de operaciones de seguridad suelen tener asignado un conjunto de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1eea8-110">In an enterprise scenario, security operation teams are typically assigned a set of devices.</span></span> <span data-ttu-id="1eea8-111">Estos dispositivos se agrupan en función de un conjunto de atributos, como sus dominios, nombres de equipo o etiquetas designadas.</span><span class="sxs-lookup"><span data-stu-id="1eea8-111">These devices are grouped together based on a set of attributes such as their domains, computer names, or designated tags.</span></span>

<span data-ttu-id="1eea8-112">En Microsoft Defender para endpoint, puedes crear grupos de dispositivos y usarlos para:</span><span class="sxs-lookup"><span data-stu-id="1eea8-112">In Microsoft Defender for Endpoint, you can create device groups and use them to:</span></span>
- <span data-ttu-id="1eea8-113">Limitar el acceso a alertas y datos relacionados a grupos de usuarios específicos de Azure AD con [roles RBAC asignados](rbac.md)</span><span class="sxs-lookup"><span data-stu-id="1eea8-113">Limit access to related alerts and data to specific Azure AD user groups with [assigned RBAC roles](rbac.md)</span></span> 
- <span data-ttu-id="1eea8-114">Configurar diferentes opciones de corrección automática para distintos conjuntos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="1eea8-114">Configure different auto-remediation settings for different sets of devices</span></span>
- <span data-ttu-id="1eea8-115">Asignar niveles de corrección específicos para aplicar durante investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="1eea8-115">Assign specific remediation levels to apply during automated investigations</span></span>
- <span data-ttu-id="1eea8-116">En una investigación, filtre la lista **Dispositivos** a grupos de dispositivos específicos mediante el **filtro** Grupo.</span><span class="sxs-lookup"><span data-stu-id="1eea8-116">In an investigation, filter the **Devices list** to just specific device groups by using the **Group** filter.</span></span>

<span data-ttu-id="1eea8-117">Puedes crear grupos de dispositivos en el contexto del acceso basado en roles (RBAC) para controlar quién puede realizar acciones específicas o ver información asignando los grupos de dispositivos a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1eea8-117">You can create device groups in the context of role-based access (RBAC) to control who can take specific action or see information by assigning the device group(s) to a user group.</span></span> <span data-ttu-id="1eea8-118">Para obtener más información, vea [Manage portal access using role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="1eea8-118">For more information, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="1eea8-119">Para obtener una visión completa de la aplicación RBAC, lea: [¿Su SOC se ejecuta sin formato con RBAC.](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)</span><span class="sxs-lookup"><span data-stu-id="1eea8-119">For a comprehensive look into RBAC application, read: [Is your SOC running flat with RBAC](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015).</span></span>

<span data-ttu-id="1eea8-120">Como parte del proceso de creación de un grupo de dispositivos, podrás:</span><span class="sxs-lookup"><span data-stu-id="1eea8-120">As part of the process of creating a device group, you'll:</span></span>
- <span data-ttu-id="1eea8-121">Establezca el nivel de corrección automatizado para ese grupo.</span><span class="sxs-lookup"><span data-stu-id="1eea8-121">Set the automated remediation level for that group.</span></span> <span data-ttu-id="1eea8-122">Para obtener más información sobre los niveles de corrección, vea [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="1eea8-122">For more information on remediation levels, see [Use Automated investigation to investigate and remediate threats](automated-investigations.md).</span></span>
- <span data-ttu-id="1eea8-123">Especifica la regla de coincidencia que determina qué grupo de dispositivos pertenece al grupo en función del nombre del dispositivo, el dominio, las etiquetas y la plataforma del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1eea8-123">Specify the matching rule that determines which device group belongs to the group based on the device name, domain, tags, and OS platform.</span></span> <span data-ttu-id="1eea8-124">Si un dispositivo también coincide con otros grupos, se agrega solo al grupo de dispositivos clasificado más alto.</span><span class="sxs-lookup"><span data-stu-id="1eea8-124">If a device is also matched to other groups, it is added only to the highest ranked device group.</span></span>
- <span data-ttu-id="1eea8-125">Seleccione el grupo de usuarios de Azure AD que debe tener acceso al grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1eea8-125">Select the Azure AD user group that should have access to the device group.</span></span>
- <span data-ttu-id="1eea8-126">Clasifice el grupo de dispositivos con respecto a otros grupos después de crearlo.</span><span class="sxs-lookup"><span data-stu-id="1eea8-126">Rank the device group relative to other groups after it is created.</span></span>

>[!NOTE]
><span data-ttu-id="1eea8-127">Un grupo de dispositivos es accesible para todos los usuarios si no le asigna ningún grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1eea8-127">A device group is accessible to all users if you don’t assign any Azure AD groups to it.</span></span>

## <a name="create-a-device-group"></a><span data-ttu-id="1eea8-128">Crear un grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="1eea8-128">Create a device group</span></span>

1. <span data-ttu-id="1eea8-129">En el panel de navegación, seleccione **Configuración Grupos**  >  **de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1eea8-129">In the navigation pane, select **Settings** > **Device groups**.</span></span>

2. <span data-ttu-id="1eea8-130">Haga clic **en Agregar grupo de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1eea8-130">Click **Add device group**.</span></span>

3. <span data-ttu-id="1eea8-131">Escriba el nombre del grupo y la configuración de automatización y especifique la regla de coincidencia que determina qué dispositivos pertenecen al grupo.</span><span class="sxs-lookup"><span data-stu-id="1eea8-131">Enter the group name and automation settings and specify the matching rule that determines which devices belong to the group.</span></span> <span data-ttu-id="1eea8-132">Vea [Cómo se inicia la investigación automatizada](automated-investigations.md#how-the-automated-investigation-starts).</span><span class="sxs-lookup"><span data-stu-id="1eea8-132">See [How the automated investigation starts](automated-investigations.md#how-the-automated-investigation-starts).</span></span>

    >[!TIP]
    ><span data-ttu-id="1eea8-133">Si desea agrupar dispositivos por unidad organizativa, puede configurar la clave del Registro para la afiliación de grupo.</span><span class="sxs-lookup"><span data-stu-id="1eea8-133">If you want to group devices by organizational unit, you can configure the registry key for the group affiliation.</span></span> <span data-ttu-id="1eea8-134">Para obtener más información sobre el etiquetado de dispositivos, consulta [Crear y administrar etiquetas de dispositivo.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="1eea8-134">For more information on device tagging, see [Create and manage device tags](machine-tags.md).</span></span>

4. <span data-ttu-id="1eea8-135">Obtenga una vista previa de varios dispositivos que coincidirán con esta regla.</span><span class="sxs-lookup"><span data-stu-id="1eea8-135">Preview several devices that will be matched by this rule.</span></span> <span data-ttu-id="1eea8-136">Si está satisfecho con la regla, haga clic en la **pestaña Acceso de** usuario.</span><span class="sxs-lookup"><span data-stu-id="1eea8-136">If you are satisfied with the rule, click the **User access** tab.</span></span>

5. <span data-ttu-id="1eea8-137">Asigna los grupos de usuarios que pueden tener acceso al grupo de dispositivos que creaste.</span><span class="sxs-lookup"><span data-stu-id="1eea8-137">Assign the user groups that can access the device group you created.</span></span>

    >[!NOTE]
    ><span data-ttu-id="1eea8-138">Solo puede conceder acceso a grupos de usuarios de Azure AD que se hayan asignado a roles RBAC.</span><span class="sxs-lookup"><span data-stu-id="1eea8-138">You can only grant access to Azure AD user groups that have been assigned to RBAC roles.</span></span>

6. <span data-ttu-id="1eea8-139">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="1eea8-139">Click **Close**.</span></span> <span data-ttu-id="1eea8-140">Se aplican los cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="1eea8-140">The configuration changes are applied.</span></span>

## <a name="manage-device-groups"></a><span data-ttu-id="1eea8-141">Administrar grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="1eea8-141">Manage device groups</span></span>

<span data-ttu-id="1eea8-142">Puedes promover o disminuir la clasificación de un grupo de dispositivos para que se le de mayor o menor prioridad durante la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="1eea8-142">You can promote or demote the rank of a device group so that it is given higher or lower priority during matching.</span></span> <span data-ttu-id="1eea8-143">Cuando un dispositivo coincide con más de un grupo, se agrega solo al grupo clasificado más alto.</span><span class="sxs-lookup"><span data-stu-id="1eea8-143">When a device is matched to more than one group, it is added only to the highest ranked group.</span></span> <span data-ttu-id="1eea8-144">También puede editar y eliminar grupos.</span><span class="sxs-lookup"><span data-stu-id="1eea8-144">You can also edit and delete groups.</span></span>

>[!WARNING]
><span data-ttu-id="1eea8-145">Eliminar un grupo de dispositivos puede afectar a las reglas de notificación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="1eea8-145">Deleting a device group may affect email notification rules.</span></span> <span data-ttu-id="1eea8-146">Si un grupo de dispositivos está configurado en una regla de notificación de correo electrónico, se quitará de esa regla.</span><span class="sxs-lookup"><span data-stu-id="1eea8-146">If a device group is configured under an email notification rule, it will be removed from that rule.</span></span> <span data-ttu-id="1eea8-147">Si el grupo de dispositivos es el único grupo configurado para una notificación de correo electrónico, esa regla de notificación de correo electrónico se eliminará junto con el grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1eea8-147">If the device group is the only group configured for an email notification, that email notification rule will be deleted along with the device group.</span></span>

<span data-ttu-id="1eea8-148">De forma predeterminada, los grupos de dispositivos son accesibles para todos los usuarios con acceso al portal.</span><span class="sxs-lookup"><span data-stu-id="1eea8-148">By default, device groups are accessible to all users with portal access.</span></span> <span data-ttu-id="1eea8-149">Puede cambiar el comportamiento predeterminado asignando grupos de usuarios de Azure AD al grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1eea8-149">You can change the default behavior by assigning Azure AD user groups to the device group.</span></span>

<span data-ttu-id="1eea8-150">Los dispositivos que no coinciden con ningún grupo se agregan al grupo Dispositivos desagrupados (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="1eea8-150">Devices that are not matched to any groups are added to Ungrouped devices (default) group.</span></span> <span data-ttu-id="1eea8-151">No puede cambiar la clasificación de este grupo ni eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="1eea8-151">You cannot change the rank of this group or delete it.</span></span> <span data-ttu-id="1eea8-152">Sin embargo, puede cambiar el nivel de corrección de este grupo y definir los grupos de usuarios de Azure AD que pueden tener acceso a este grupo.</span><span class="sxs-lookup"><span data-stu-id="1eea8-152">However, you can change the remediation level of this group, and define the Azure AD user groups that can access this group.</span></span>

>[!NOTE]
> <span data-ttu-id="1eea8-153">La aplicación de cambios en la configuración del grupo de dispositivos puede tardar hasta varios minutos.</span><span class="sxs-lookup"><span data-stu-id="1eea8-153">Applying changes to device group configuration may take up to several minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1eea8-154">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1eea8-154">Related topics</span></span>

- [<span data-ttu-id="1eea8-155">Administrar el acceso al portal mediante el control de acceso basado en roles</span><span class="sxs-lookup"><span data-stu-id="1eea8-155">Manage portal access using role-based based access control</span></span>](rbac.md)
- [<span data-ttu-id="1eea8-156">Crear y administrar etiquetas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="1eea8-156">Create and manage device tags</span></span>](machine-tags.md)
- [<span data-ttu-id="1eea8-157">Obtener una lista de grupos de dispositivos de inquilino con la API de Graph</span><span class="sxs-lookup"><span data-stu-id="1eea8-157">Get list of tenant device groups using Graph API</span></span>](https://docs.microsoft.com/graph/api/device-list-memberof)
