---
title: Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 para la empresa
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo habilitar Microsoft 365 para proteger dispositivos Windows 10 locales Unidos a directorio activo en tan solo unos pocos pasos.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560851"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="59064-103">Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 empresa Premium</span><span class="sxs-lookup"><span data-stu-id="59064-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="59064-104">Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business Premium para proteger sus dispositivos con Windows 10, a la vez que mantiene el acceso a los recursos locales que requieren autenticación local.</span><span class="sxs-lookup"><span data-stu-id="59064-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="59064-105">Para configurar esta protección, puede implementar dispositivos de **Azure ad Unidos híbridos**.</span><span class="sxs-lookup"><span data-stu-id="59064-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="59064-106">Estos dispositivos se unen a su Active Directory local y a su Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="59064-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="59064-107">Este vídeo describe los pasos para configurar esta configuración para el escenario más común, que también se detalla en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="59064-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="59064-108">Antes de empezar, asegúrese de completar estos pasos:</span><span class="sxs-lookup"><span data-stu-id="59064-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="59064-109">Sincronice los usuarios a Azure AD con Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="59064-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="59064-110">Complete la sincronización de la unidad organizativa (OU) de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="59064-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="59064-111">Asegúrese de que todos los usuarios de dominio que sincronice tienen licencias para Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="59064-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="59064-112">Consulte [sincronizar usuarios de dominio a Microsoft](manage-domain-users.md) para conocer los pasos.</span><span class="sxs-lookup"><span data-stu-id="59064-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="59064-113">1. comprobar la autoridad de MDM en Intune</span><span class="sxs-lookup"><span data-stu-id="59064-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="59064-114">Vaya a [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) y, en la página de Microsoft Intune, seleccione **inscripción de dispositivos**y, a continuación, en la página **información general** , asegúrese de que la **autoridad de MDM** es **Intune**.</span><span class="sxs-lookup"><span data-stu-id="59064-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="59064-115">Si la **entidad de MDM** es **ninguna**, haga clic en la **entidad de MDM** para establecerla en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="59064-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="59064-116">Si **la entidad de MDM** es **Microsoft Office 365**, vaya a dispositivos de inscripción de **dispositivos**  >  **Enroll devices** y use el cuadro de diálogo **Agregar autoridad de MDM** que se encuentra a la derecha para agregar la autoridad de **Intune MDM** (el cuadro de diálogo **Agregar autoridad de MDM** solo está disponible si la autoridad de **MDM** está establecida en Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="59064-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="59064-117">2. Compruebe que Azure AD esté habilitado para unirse a los equipos</span><span class="sxs-lookup"><span data-stu-id="59064-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="59064-118">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione **Azure Active Directory** (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista **centros de administración** .</span><span class="sxs-lookup"><span data-stu-id="59064-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="59064-119">En el **centro de administración de Azure Active**Directory, vaya a **Azure Active Directory** , elija **dispositivos** y, a continuación, **configuración de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="59064-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="59064-120">Comprobar**que los usuarios pueden unirse a dispositivos a Azure ad** está habilitado</span><span class="sxs-lookup"><span data-stu-id="59064-120">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="59064-121">Para habilitar todos los usuarios, establezca en **todos**.</span><span class="sxs-lookup"><span data-stu-id="59064-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="59064-122">Para habilitar usuarios específicos, defina como **seleccionado** para habilitar un grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="59064-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="59064-123">Agregue los usuarios de dominio que desee sincronizar en Azure AD a un [grupo de seguridad](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="59064-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="59064-124">Elija **seleccionar grupos** para habilitar el ámbito de usuario de MDM para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="59064-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="59064-125">3. comprobar que Azure AD está habilitado para MDM</span><span class="sxs-lookup"><span data-stu-id="59064-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="59064-126">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione seleccionar **extremo** **administradora** t (seleccionar **Mostrar todo** si el administrador de puntos de conexión no está visible).</span><span class="sxs-lookup"><span data-stu-id="59064-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="59064-127">En el **centro de administración de Microsoft Endpoint Manager**, vaya a **dispositivos**  >  **Windows**inscripción automática de  >  **inscripción**  >  **Automatic Enrollment**.</span><span class="sxs-lookup"><span data-stu-id="59064-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="59064-128">Compruebe que el ámbito de usuario de MDM esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="59064-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="59064-129">Para inscribir todos los equipos, establezca en **todos** para inscribir de forma automática a todos los equipos de los usuarios que se unen a Azure ad y a los nuevos equipos cuando los usuarios agregan una cuenta profesional a Windows.</span><span class="sxs-lookup"><span data-stu-id="59064-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="59064-130">Establezca en **some** para inscribir los equipos de un grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="59064-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="59064-131">Agregue los usuarios de dominio que desee sincronizar en Azure AD a un [grupo de seguridad](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="59064-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="59064-132">Elija **seleccionar grupos** para habilitar el ámbito de usuario de MDM para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="59064-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="59064-133">4. crear los recursos necesarios</span><span class="sxs-lookup"><span data-stu-id="59064-133">4. Create the required resources</span></span> 

<span data-ttu-id="59064-134">La realización de las tareas necesarias para [configurar la Unión híbrida de Azure ad](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) se ha simplificado mediante el uso del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) que se encuentra en el módulo de PowerShell [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) .</span><span class="sxs-lookup"><span data-stu-id="59064-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="59064-135">Al invocar este cmdlet, creará y configurará el punto de conexión de servicio y la Directiva de grupo necesarios.</span><span class="sxs-lookup"><span data-stu-id="59064-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="59064-136">Puede instalar este módulo invocando lo siguiente desde una instancia de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="59064-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="59064-137">Se recomienda instalar este módulo en el servidor Windows que ejecuta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="59064-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="59064-138">Para crear el punto de conexión de servicio y la Directiva de grupo necesarios, deberá invocar el cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) .</span><span class="sxs-lookup"><span data-stu-id="59064-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="59064-139">Para llevar a cabo esta tarea, necesitará sus credenciales de administrador global de Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="59064-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="59064-140">Cuando esté listo para crear los recursos, invoque lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59064-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="59064-141">El primer comando establecerá una conexión con la nube de Microsoft y, cuando se le solicite, especifique sus credenciales de administrador global de Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="59064-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="59064-142">5. vincular la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="59064-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="59064-143">En la consola de administración de directivas de grupo (GPMC), haga clic con el botón secundario en la ubicación en la que desea vincular la Directiva y seleccione *vincular un GPO existente...* en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="59064-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="59064-144">Seleccione la directiva creada en el paso anterior y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="59064-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="59064-145">Obtener las plantillas administrativas más recientes</span><span class="sxs-lookup"><span data-stu-id="59064-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="59064-146">Si no ve la Directiva habilitar la **inscripción automática de MDM con credenciales de Azure ad predeterminadas**, puede deberse a que no tiene instalado ADMX para Windows 10, versión 1803, versión 1809 o versión 1903.</span><span class="sxs-lookup"><span data-stu-id="59064-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="59064-147">Para solucionar el problema, siga estos pasos (Nota: la versión más reciente de MDM. ADMX es compatible con versiones anteriores):</span><span class="sxs-lookup"><span data-stu-id="59064-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="59064-148">Descargar: [plantillas administrativas (. admx) para Windows 10 May 2019 actualización (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="59064-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="59064-149">Instale el paquete en el controlador de dominio principal (PDC).</span><span class="sxs-lookup"><span data-stu-id="59064-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="59064-150">Navegue, en función de la versión de la carpeta: **c:\Archivos de programa (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="59064-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="59064-151">Cambie el nombre de la carpeta de **definiciones de directiva** en la ruta de acceso anterior a **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="59064-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="59064-152">Copie la carpeta **PolicyDefinitions** en **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="59064-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="59064-153">Si tiene previsto usar una tienda de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="59064-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="59064-154">Reinicie el controlador de dominio principal para que la Directiva esté disponible.</span><span class="sxs-lookup"><span data-stu-id="59064-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="59064-155">Este procedimiento también funcionará para versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="59064-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="59064-156">En este momento, podrá ver la directiva **Habilitar la inscripción automática de MDM con credenciales de Azure ad predeterminadas** disponibles.</span><span class="sxs-lookup"><span data-stu-id="59064-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
