---
title: Crear y administrar roles para el control de acceso basado en roles
description: Cree roles y defina los permisos asignados al rol como parte de la implementación de control de acceso basada en roles en el Centro de seguridad de Microsoft Defender
keywords: roles de usuario, roles, acceso a rbac
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
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073987"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a><span data-ttu-id="a6d22-104">Crear y administrar roles para el control de acceso basado en roles</span><span class="sxs-lookup"><span data-stu-id="a6d22-104">Create and manage roles for role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a6d22-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a6d22-105">**Applies to:**</span></span>
- [<span data-ttu-id="a6d22-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a6d22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a6d22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6d22-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a6d22-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="a6d22-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a6d22-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="a6d22-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a><span data-ttu-id="a6d22-110">Crear roles y asignar el rol a un Azure Active Directory grupo</span><span class="sxs-lookup"><span data-stu-id="a6d22-110">Create roles and assign the role to an Azure Active Directory group</span></span>

<span data-ttu-id="a6d22-111">Los siguientes pasos le guían sobre cómo crear roles en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a6d22-111">The following steps guide you on how to create roles in Microsoft Defender Security Center.</span></span> <span data-ttu-id="a6d22-112">Se supone que ya ha creado Azure Active Directory grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a6d22-112">It assumes that you have already created Azure Active Directory user groups.</span></span>

1. <span data-ttu-id="a6d22-113">Inicie sesión en [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/) cuenta con un administrador de seguridad o un rol de administrador global asignado.</span><span class="sxs-lookup"><span data-stu-id="a6d22-113">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with a Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="a6d22-114">En el panel de navegación, **seleccione Configuración > Roles**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-114">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="a6d22-115">Seleccione **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-115">Select **Add item**.</span></span>

4. <span data-ttu-id="a6d22-116">Escriba el nombre, la descripción y los permisos del rol que desee asignar al rol.</span><span class="sxs-lookup"><span data-stu-id="a6d22-116">Enter the role name, description, and permissions you'd like to assign to the role.</span></span>

5. <span data-ttu-id="a6d22-117">Seleccione **Siguiente** para asignar el rol a un grupo de seguridad de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a6d22-117">Select **Next** to assign the role to an Azure AD Security group.</span></span>

6. <span data-ttu-id="a6d22-118">Use el filtro para seleccionar el grupo de Azure AD al que desea agregar a este rol.</span><span class="sxs-lookup"><span data-stu-id="a6d22-118">Use the filter to select the Azure AD group that you'd like to add to this role to.</span></span>

7. <span data-ttu-id="a6d22-119">**Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-119">**Save and close**.</span></span>

8. <span data-ttu-id="a6d22-120">Aplica las opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="a6d22-120">Apply the configuration settings.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6d22-121">Después de crear roles, tendrás que crear un grupo de dispositivos y proporcionar acceso al grupo de dispositivos al asignarlo a un rol que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="a6d22-121">After creating roles, you'll need to create a device group and provide access to the device group by assigning it to a role that you just created.</span></span>

### <a name="permission-options"></a><span data-ttu-id="a6d22-122">Opciones de permisos</span><span class="sxs-lookup"><span data-stu-id="a6d22-122">Permission options</span></span>

- <span data-ttu-id="a6d22-123">**Ver datos**</span><span class="sxs-lookup"><span data-stu-id="a6d22-123">**View data**</span></span>
    - <span data-ttu-id="a6d22-124">**Operaciones de seguridad:** ver todos los datos de operaciones de seguridad en el portal</span><span class="sxs-lookup"><span data-stu-id="a6d22-124">**Security operations** - View all security operations data in the portal</span></span>
    - <span data-ttu-id="a6d22-125">**Amenaza y administración de vulnerabilidades:** ver Administración de amenazas y vulnerabilidades datos en el portal</span><span class="sxs-lookup"><span data-stu-id="a6d22-125">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

- <span data-ttu-id="a6d22-126">**Acciones de corrección activas**</span><span class="sxs-lookup"><span data-stu-id="a6d22-126">**Active remediation actions**</span></span>
    - <span data-ttu-id="a6d22-127">**Operaciones de seguridad:** realizar acciones de respuesta, aprobar o descartar acciones de corrección pendientes, administrar listas permitidas o bloqueadas para automatización e indicadores</span><span class="sxs-lookup"><span data-stu-id="a6d22-127">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
    - <span data-ttu-id="a6d22-128">**Amenazas y administración de vulnerabilidades: control de excepciones:** crear nuevas excepciones y administrar excepciones activas</span><span class="sxs-lookup"><span data-stu-id="a6d22-128">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
    - <span data-ttu-id="a6d22-129">**Amenazas y administración de vulnerabilidades: control de** corrección: enviar nuevas solicitudes de corrección, crear vales y administrar las actividades de corrección existentes</span><span class="sxs-lookup"><span data-stu-id="a6d22-129">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

- <span data-ttu-id="a6d22-130">**Investigación de alertas:** administrar alertas, iniciar investigaciones automatizadas, ejecutar exámenes, recopilar paquetes de investigación, administrar etiquetas de dispositivo y descargar solo archivos ejecutables portátiles (PE)</span><span class="sxs-lookup"><span data-stu-id="a6d22-130">**Alerts investigation** - Manage alerts, initiate automated investigations, run scans, collect investigation packages, manage device tags, and download only portable executable (PE) files</span></span> 

- <span data-ttu-id="a6d22-131">**Administrar la configuración del** sistema del portal: configurar las opciones de almacenamiento, SIEM y la API intel de amenazas (se aplica globalmente), la configuración avanzada, las cargas automatizadas de archivos, los roles y los grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a6d22-131">**Manage portal system settings** - Configure storage settings, SIEM and threat intel API settings (applies globally), advanced settings, automated file uploads, roles and device groups</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6d22-132">Esta configuración solo está disponible en el rol Administrador de Microsoft Defender para puntos de conexión (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="a6d22-132">This setting is only available in the Microsoft Defender for Endpoint administrator (default) role.</span></span>

- <span data-ttu-id="a6d22-133">**Administrar la configuración** de seguridad en el Centro de seguridad: configure la configuración de supresión de alertas, administre las exclusiones de carpetas para la automatización, los dispositivos integrados y externos, y administre las notificaciones de correo electrónico, administre el laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="a6d22-133">**Manage security settings in Security Center** - Configure alert suppression settings, manage folder exclusions for automation, onboard and offboard devices, and manage email notifications, manage evaluation lab</span></span>

- <span data-ttu-id="a6d22-134">**Capacidades de respuesta en directo**</span><span class="sxs-lookup"><span data-stu-id="a6d22-134">**Live response capabilities**</span></span>
    - <span data-ttu-id="a6d22-135">**Comandos** básicos:</span><span class="sxs-lookup"><span data-stu-id="a6d22-135">**Basic** commands:</span></span>
        - <span data-ttu-id="a6d22-136">Iniciar una sesión de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="a6d22-136">Start a live response session</span></span>
        - <span data-ttu-id="a6d22-137">Realizar comandos de respuesta en directo de solo lectura en dispositivo remoto (excluyendo la copia y ejecución de archivos</span><span class="sxs-lookup"><span data-stu-id="a6d22-137">Perform read only live response commands on remote device (excluding file copy and execution</span></span>
    - <span data-ttu-id="a6d22-138">**Comandos** avanzados:</span><span class="sxs-lookup"><span data-stu-id="a6d22-138">**Advanced** commands:</span></span>
        - <span data-ttu-id="a6d22-139">Descargar un archivo desde el dispositivo remoto a través de una respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="a6d22-139">Download a file from the remote device via live response</span></span>
        - <span data-ttu-id="a6d22-140">Descargar archivos PE y que no son PE de la página de archivos</span><span class="sxs-lookup"><span data-stu-id="a6d22-140">Download PE and non-PE files from the file page</span></span>
        - <span data-ttu-id="a6d22-141">Upload un archivo al dispositivo remoto</span><span class="sxs-lookup"><span data-stu-id="a6d22-141">Upload a file to the remote device</span></span>
        - <span data-ttu-id="a6d22-142">Ver un script desde la biblioteca de archivos</span><span class="sxs-lookup"><span data-stu-id="a6d22-142">View a script from the files library</span></span>
        - <span data-ttu-id="a6d22-143">Ejecutar un script en el dispositivo remoto desde la biblioteca de archivos</span><span class="sxs-lookup"><span data-stu-id="a6d22-143">Execute a script on the remote device from the files library</span></span>

<span data-ttu-id="a6d22-144">Para obtener más información sobre los comandos disponibles, consulta [Investigar dispositivos con live response](live-response.md).</span><span class="sxs-lookup"><span data-stu-id="a6d22-144">For more information on the available commands, see [Investigate devices using Live response](live-response.md).</span></span>
  
## <a name="edit-roles"></a><span data-ttu-id="a6d22-145">Editar roles</span><span class="sxs-lookup"><span data-stu-id="a6d22-145">Edit roles</span></span>

1. <span data-ttu-id="a6d22-146">Inicie sesión [en](https://securitycenter.windows.com/) Centro de seguridad de Microsoft Defender cuenta con el rol Administrador de seguridad o Administrador global asignado.</span><span class="sxs-lookup"><span data-stu-id="a6d22-146">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="a6d22-147">En el panel de navegación, **seleccione Configuración > Roles**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-147">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="a6d22-148">Seleccione el rol que desea editar.</span><span class="sxs-lookup"><span data-stu-id="a6d22-148">Select the role you'd like to edit.</span></span>

4. <span data-ttu-id="a6d22-149">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-149">Click **Edit**.</span></span>

5. <span data-ttu-id="a6d22-150">Modifique los detalles o los grupos asignados al rol.</span><span class="sxs-lookup"><span data-stu-id="a6d22-150">Modify the details or the groups that are assigned to the role.</span></span> 

6. <span data-ttu-id="a6d22-151">Haga **clic en Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-151">Click **Save and close**.</span></span>

## <a name="delete-roles"></a><span data-ttu-id="a6d22-152">Eliminar roles</span><span class="sxs-lookup"><span data-stu-id="a6d22-152">Delete roles</span></span>

1. <span data-ttu-id="a6d22-153">Inicie sesión [en](https://securitycenter.windows.com/) Centro de seguridad de Microsoft Defender cuenta con el rol Administrador de seguridad o Administrador global asignado.</span><span class="sxs-lookup"><span data-stu-id="a6d22-153">Log in to [Microsoft Defender Security Center](https://securitycenter.windows.com/) using account with Security administrator or Global administrator role assigned.</span></span>

2. <span data-ttu-id="a6d22-154">En el panel de navegación, **seleccione Configuración > Roles**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-154">In the navigation pane, select **Settings > Roles**.</span></span>

3. <span data-ttu-id="a6d22-155">Seleccione el rol que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="a6d22-155">Select the role you'd like to delete.</span></span>

4. <span data-ttu-id="a6d22-156">Haga clic en el botón desplegable y seleccione **Eliminar rol**.</span><span class="sxs-lookup"><span data-stu-id="a6d22-156">Click the drop-down button and select **Delete role**.</span></span>

## <a name="related-topic"></a><span data-ttu-id="a6d22-157">Tema relacionado</span><span class="sxs-lookup"><span data-stu-id="a6d22-157">Related topic</span></span>

- [<span data-ttu-id="a6d22-158">Permisos básicos del usuario para acceder al portal</span><span class="sxs-lookup"><span data-stu-id="a6d22-158">User basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="a6d22-159">Crear y administrar grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a6d22-159">Create and manage device groups</span></span>](machine-groups.md)
