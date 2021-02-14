---
title: Habilitar dispositivos Windows 10 unidos a un dominio para que sean administrados por Microsoft 365 para empresas
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
description: Aprende a habilitar Microsoft 365 para proteger los dispositivos Windows 10 locales unidos a Active Directory en tan solo unos pasos.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560851"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="225fc-103">Habilitar dispositivos Windows 10 unidos a un dominio para que sean administrados por Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="225fc-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="225fc-104">Si tu organización usa Windows Server Active Directory local, puedes configurar Microsoft 365 Empresa Premium para proteger los dispositivos Windows 10, a la vez que mantienes el acceso a los recursos locales que requieren autenticación local.</span><span class="sxs-lookup"><span data-stu-id="225fc-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="225fc-105">Para configurar esta protección, puede implementar dispositivos unidos **a Azure AD híbrido.**</span><span class="sxs-lookup"><span data-stu-id="225fc-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="225fc-106">Estos dispositivos se unen a active directory local y a Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="225fc-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="225fc-107">En este vídeo se describen los pasos para configurarlo para el escenario más común, que también se detalla en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="225fc-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="225fc-108">Antes de empezar, asegúrese de completar estos pasos:</span><span class="sxs-lookup"><span data-stu-id="225fc-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="225fc-109">Sincronizar usuarios con Azure AD con Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="225fc-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="225fc-110">Complete la sincronización de la unidad organizativa (OU) de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="225fc-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="225fc-111">Asegúrese de que todos los usuarios de dominio que sincronice tengan licencias para Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="225fc-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="225fc-112">Consulte [Sincronizar usuarios de dominio con Microsoft](manage-domain-users.md) para ver los pasos.</span><span class="sxs-lookup"><span data-stu-id="225fc-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="225fc-113">1. Comprobar la autoridad MDM en Intune</span><span class="sxs-lookup"><span data-stu-id="225fc-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="225fc-114">Ve a [Endpoint Manager y,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en la página de  Microsoft Intune, selecciona **Inscripción** de dispositivos y, a continuación, en la página Información general, asegúrate de que la entidad **de MDM** sea **Intune.**</span><span class="sxs-lookup"><span data-stu-id="225fc-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="225fc-115">Si **la entidad de MDM** es **Ninguna,** haz clic en la autoridad **MDM** para establecerla en **Intune.**</span><span class="sxs-lookup"><span data-stu-id="225fc-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="225fc-116">Si  la entidad de MDM es Microsoft Office  **365,** ve a Dispositivos Inscribir dispositivos y usa el cuadro de diálogo Agregar entidad de mdma de la derecha para agregar la autoridad MDM de Intune (el cuadro de diálogo Agregar entidad de mdma solo está disponible si la entidad de MDM está establecida en  >   Microsoft Office 365).    </span><span class="sxs-lookup"><span data-stu-id="225fc-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="225fc-117">2. Comprobar que Azure AD está habilitado para unirse a equipos</span><span class="sxs-lookup"><span data-stu-id="225fc-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="225fc-118">Vaya al centro de administración y seleccione Azure Active Directory (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Centros de** administración. </span><span class="sxs-lookup"><span data-stu-id="225fc-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="225fc-119">En el **Centro de administración de Azure Active Directory,** vaya a Azure Active **Directory,** elija **Dispositivos** y, a continuación, Configuración **de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="225fc-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="225fc-120">Comprobar **que los usuarios pueden unir dispositivos a Azure AD** está habilitado</span><span class="sxs-lookup"><span data-stu-id="225fc-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="225fc-121">Para habilitar todos los usuarios, establezca en **Todos**.</span><span class="sxs-lookup"><span data-stu-id="225fc-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="225fc-122">Para habilitar usuarios específicos, establezca el valor **seleccionado** para habilitar un grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="225fc-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="225fc-123">Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="225fc-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="225fc-124">Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="225fc-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="225fc-125">3. Comprobar que Azure AD está habilitado para MDM</span><span class="sxs-lookup"><span data-stu-id="225fc-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="225fc-126">Ve al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  y selecciona **Endpoint Managemen** t (selecciona **Mostrar** todo si **Endpoint Manager** no está visible)</span><span class="sxs-lookup"><span data-stu-id="225fc-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="225fc-127">En el Centro **de administración de Microsoft Endpoint Manager,** vaya a **Dispositivos** windows inscripción automática  >    >  **de Windows**  >  .</span><span class="sxs-lookup"><span data-stu-id="225fc-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="225fc-128">Comprueba que el ámbito de usuario MDM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="225fc-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="225fc-129">Para inscribir todos los  equipos, esta establece en Todos para inscribir automáticamente todos los equipos de usuario que están unidos a Azure AD y los equipos nuevos cuando los usuarios agregan una cuenta de trabajo a Windows.</span><span class="sxs-lookup"><span data-stu-id="225fc-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="225fc-130">Se establece **en Algunos** para inscribir los equipos de un grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="225fc-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="225fc-131">Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="225fc-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="225fc-132">Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="225fc-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="225fc-133">4. Crear los recursos necesarios</span><span class="sxs-lookup"><span data-stu-id="225fc-133">4. Create the required resources</span></span> 

<span data-ttu-id="225fc-134">La realización de las tareas necesarias para configurar la unión híbrida de [Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) se ha simplificado mediante el uso del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) que se encuentra en el módulo [de PowerShell SecMgmt.](https://www.powershellgallery.com/packages/SecMgmt)</span><span class="sxs-lookup"><span data-stu-id="225fc-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="225fc-135">Al invocar este cmdlet, se creará y configurará el punto de conexión de servicio y la directiva de grupo necesarios.</span><span class="sxs-lookup"><span data-stu-id="225fc-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="225fc-136">Puede instalar este módulo invocando lo siguiente desde una instancia de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="225fc-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="225fc-137">Se recomienda instalar este módulo en Windows Server que ejecuta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="225fc-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="225fc-138">Para crear el punto de conexión de servicio y la directiva de grupo necesarios, invocará el cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="225fc-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="225fc-139">Necesitará sus credenciales de administrador global de Microsoft 365 Empresa Premium al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="225fc-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="225fc-140">Cuando esté listo para crear los recursos, invoque lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="225fc-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="225fc-141">El primer comando establecerá una conexión con la nube de Microsoft y, cuando se le solicite, especifique sus credenciales de administrador global de Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="225fc-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="225fc-142">5. Vincular la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="225fc-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="225fc-143">En la Consola de administración de directivas de grupo (GPMC), haz clic con el botón derecho en la ubicación donde quieres vincular la directiva y selecciona Vincular un *GPO existente...* en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="225fc-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="225fc-144">Seleccione la directiva creada en el paso anterior y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="225fc-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="225fc-145">Obtener las plantillas administrativas más recientes</span><span class="sxs-lookup"><span data-stu-id="225fc-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="225fc-146">Si no ves la directiva Habilitar la inscripción automática de MDM con credenciales predeterminadas de **Azure AD,** puede deberse a que no tienes el ADMX instalado para Windows 10, versión 1803, versión 1809 o versión 1903.</span><span class="sxs-lookup"><span data-stu-id="225fc-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="225fc-147">Para solucionar el problema, sigue estos pasos (Nota: el mdm.admx más reciente es compatible con versiones anteriores):</span><span class="sxs-lookup"><span data-stu-id="225fc-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="225fc-148">Descarga: [Plantillas administrativas (.admx) para Windows 10 May 2019 Update (1903).](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)</span><span class="sxs-lookup"><span data-stu-id="225fc-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="225fc-149">Instale el paquete en el controlador de dominio principal (PDC).</span><span class="sxs-lookup"><span data-stu-id="225fc-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="225fc-150">Navegue, según la versión a la carpeta: C:\Archivos de programa **(x86)\Directiva de grupo de Microsoft\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="225fc-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="225fc-151">Cambie el nombre **de la carpeta Definiciones de** directiva de la ruta de acceso anterior a **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="225fc-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="225fc-152">Copie **la carpeta PolicyDefinitions** en **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="225fc-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="225fc-153">Si planea usar un almacén de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="225fc-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="225fc-154">Reinicie el controlador de dominio principal para que la directiva esté disponible.</span><span class="sxs-lookup"><span data-stu-id="225fc-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="225fc-155">Este procedimiento también funcionará para cualquier versión futura.</span><span class="sxs-lookup"><span data-stu-id="225fc-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="225fc-156">En este punto, deberías poder ver la directiva Habilitar la inscripción automática de MDM con las credenciales predeterminadas **de Azure AD disponibles.**</span><span class="sxs-lookup"><span data-stu-id="225fc-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
