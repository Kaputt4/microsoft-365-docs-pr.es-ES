---
title: Permitir que los dispositivos de Windows 10 unidos a un dominio se puedan administrar Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Obtenga información sobre cómo habilitar Microsoft 365 proteger los dispositivos locales unidos a Active-Directory Windows 10 en unos pocos pasos.
ms.openlocfilehash: eb95c437030ae13a44f5e8043b3544d5846001c2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287703"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="63e77-103">Habilitar dispositivos de Windows 10 unidos a un dominio para que los pueda administrar Microsoft 365 Empresa Premium</span><span class="sxs-lookup"><span data-stu-id="63e77-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="63e77-104">Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Empresa Premium para proteger los dispositivos Windows 10, al mismo tiempo que mantiene el acceso a los recursos locales que requieren autenticación local.</span><span class="sxs-lookup"><span data-stu-id="63e77-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="63e77-105">Para configurar esta protección, puede implementar **dispositivos híbridos unidos a Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="63e77-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="63e77-106">Estos dispositivos se unen a su Active Directory local y a su Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="63e77-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

## <a name="watch-configure-hybrid-azure-active-directory-join"></a><span data-ttu-id="63e77-107">Watch: Configure Hybrid Azure Active Directory join</span><span class="sxs-lookup"><span data-stu-id="63e77-107">Watch: Configure Hybrid Azure Active Directory join</span></span>

<span data-ttu-id="63e77-108">En este vídeo se describen los pasos para configurar esto para el escenario más común, que también se detalla en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="63e77-108">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a><span data-ttu-id="63e77-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="63e77-109">Before you begin</span></span>

- <span data-ttu-id="63e77-110">Sincronizar usuarios con Azure AD con Azure AD Conectar.</span><span class="sxs-lookup"><span data-stu-id="63e77-110">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="63e77-111">Complete la sincronización Conectar unidad organizativa (OU) de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="63e77-111">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="63e77-112">Asegúrese de que todos los usuarios de dominio que sincronice tengan licencias para Microsoft 365 Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="63e77-112">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="63e77-113">Consulta [Sincronizar usuarios de dominio con Microsoft](manage-domain-users.md) para ver los pasos.</span><span class="sxs-lookup"><span data-stu-id="63e77-113">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="63e77-114">1. Comprobar la entidad MDM en Intune</span><span class="sxs-lookup"><span data-stu-id="63e77-114">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="63e77-115">Vaya [a Endpoint Manager y,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en la página Microsoft Intune, seleccione Inscripción  de dispositivos **y,** a continuación, en la página Información general, asegúrese de que la entidad de **MDM** es **Intune**.</span><span class="sxs-lookup"><span data-stu-id="63e77-115">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="63e77-116">Si **la entidad MDM** es **None,** haz clic en la **entidad MDM** para establecerla en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="63e77-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="63e77-117">Si  la entidad MDM es **Microsoft Office 365,** ve a Dispositivos Inscribir dispositivos y usa el cuadro de diálogo Agregar entidad mdma a la derecha para agregar la autoridad MDM de Intune (el cuadro de diálogo Agregar entidad mdma solo está disponible si la entidad mdma está establecida en   >   Microsoft Office 365).    </span><span class="sxs-lookup"><span data-stu-id="63e77-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="63e77-118">2. Comprobar que Azure AD está habilitado para unir equipos</span><span class="sxs-lookup"><span data-stu-id="63e77-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="63e77-119">Vaya al Centro de administración en y seleccione Azure Active Directory (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Centros de** administración. </span><span class="sxs-lookup"><span data-stu-id="63e77-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="63e77-120">En el **Azure Active Directory de administración,** vaya **a Azure Active Directory** , elija **Dispositivos** y, a continuación, **Configuración del dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="63e77-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="63e77-121">Comprobar **que los usuarios pueden unir dispositivos a Azure AD** está habilitado</span><span class="sxs-lookup"><span data-stu-id="63e77-121">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="63e77-122">Para habilitar todos los usuarios, establezca en **Todos**.</span><span class="sxs-lookup"><span data-stu-id="63e77-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="63e77-123">Para habilitar usuarios específicos, establezca en **Seleccionado** para habilitar un grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="63e77-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="63e77-124">Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="63e77-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="63e77-125">Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="63e77-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="63e77-126">3. Comprobar que Azure AD está habilitado para MDM</span><span class="sxs-lookup"><span data-stu-id="63e77-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="63e77-127">Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione **Administradores de puntos** de conexión t (seleccione **Mostrar** todo si **Endpoint Manager** no está visible)</span><span class="sxs-lookup"><span data-stu-id="63e77-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="63e77-128">En el **Centro Microsoft Endpoint Manager administración,** vaya a **Dispositivos**  >  **Windows**  >  **Windows Inscripción**  >  **automática**.</span><span class="sxs-lookup"><span data-stu-id="63e77-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="63e77-129">Compruebe que el ámbito de usuario MDM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="63e77-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="63e77-130">Para inscribir todos los  equipos, establezca en Todos para inscribir automáticamente todos los equipos de usuario unidos a Azure AD y los equipos nuevos cuando los usuarios agreguen una cuenta de trabajo a Windows.</span><span class="sxs-lookup"><span data-stu-id="63e77-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="63e77-131">Se establece **en Algunos** para inscribir los equipos de un grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="63e77-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="63e77-132">Agregue los usuarios de dominio deseados sincronizados en Azure AD a un [grupo de seguridad.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="63e77-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="63e77-133">Elige **Seleccionar grupos para** habilitar el ámbito de usuario MDM para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="63e77-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="63e77-134">4. Crear los recursos necesarios</span><span class="sxs-lookup"><span data-stu-id="63e77-134">4. Create the required resources</span></span> 

<span data-ttu-id="63e77-135">La realización de las tareas necesarias para configurar la combinación híbrida de [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) se ha simplificado mediante el uso del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) que se encuentra en el módulo [De PowerShell de SecMgmt.](https://www.powershellgallery.com/packages/SecMgmt)</span><span class="sxs-lookup"><span data-stu-id="63e77-135">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="63e77-136">Al invocar este cmdlet, creará y configurará el punto de conexión de servicio y la directiva de grupo necesarios.</span><span class="sxs-lookup"><span data-stu-id="63e77-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="63e77-137">Puede instalar este módulo invocando lo siguiente desde una instancia de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="63e77-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="63e77-138">Se recomienda instalar este módulo en el servidor Windows que ejecuta Azure AD Conectar.</span><span class="sxs-lookup"><span data-stu-id="63e77-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="63e77-139">Para crear el punto de conexión de servicio y la directiva de grupo necesarios, invocará el cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="63e77-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="63e77-140">Necesitará sus credenciales de Microsoft 365 Empresa Premium de administración global al realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="63e77-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="63e77-141">Cuando esté listo para crear los recursos, invoque lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="63e77-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="63e77-142">El primer comando establecerá una conexión con la nube de Microsoft y, cuando se le solicite, especifique sus Microsoft 365 Empresa Premium de administración global.</span><span class="sxs-lookup"><span data-stu-id="63e77-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="63e77-143">5. Vincular la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="63e77-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="63e77-144">En la Consola de administración de directivas de grupo (GPMC), haga clic con el botón secundario en la ubicación donde desea vincular la directiva y seleccione Vincular un *GPO existente...* en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="63e77-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="63e77-145">Seleccione la directiva creada en el paso anterior y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="63e77-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="63e77-146">Obtener las plantillas administrativas más recientes</span><span class="sxs-lookup"><span data-stu-id="63e77-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="63e77-147">Si no ve la directiva Habilitar la inscripción automática de MDM con credenciales predeterminadas de **Azure AD,** puede deberse a que no tiene el ADMX instalado para Windows 10, versión 1803 o posterior.</span><span class="sxs-lookup"><span data-stu-id="63e77-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="63e77-148">Para solucionar el problema, siga estos pasos (Nota: la mdm.admx más reciente es compatible con versiones anteriores):</span><span class="sxs-lookup"><span data-stu-id="63e77-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1. <span data-ttu-id="63e77-149">Descargar: [Plantillas administrativas (.admx) para Windows 10 actualización de octubre de 2020 (20H2).](https://www.microsoft.com/download/102157)</span><span class="sxs-lookup"><span data-stu-id="63e77-149">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2. <span data-ttu-id="63e77-150">Instale el paquete en un controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="63e77-150">Install the package on a Domain Controller.</span></span>
3. <span data-ttu-id="63e77-151">Navegue, según la versión de plantillas administrativas a la carpeta: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span><span class="sxs-lookup"><span data-stu-id="63e77-151">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4. <span data-ttu-id="63e77-152">Cambie el nombre de la carpeta **Definiciones de** directiva de la ruta de acceso anterior **a PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="63e77-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5. <span data-ttu-id="63e77-153">Copie la **carpeta PolicyDefinitions** en el recurso compartido SYSVOL, ubicado de forma predeterminada en **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="63e77-153">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span>
   - <span data-ttu-id="63e77-154">Si planea usar un almacén de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="63e77-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6. <span data-ttu-id="63e77-155">En caso de que tenga varios controladores de dominio, espere a que SYSVOL se replique para que las directivas estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="63e77-155">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="63e77-156">Este procedimiento también funcionará para cualquier versión futura de las plantillas administrativas.</span><span class="sxs-lookup"><span data-stu-id="63e77-156">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="63e77-157">En este punto, debería poder ver la directiva Habilitar la inscripción **automática de MDM con las credenciales predeterminadas de Azure AD** disponibles.</span><span class="sxs-lookup"><span data-stu-id="63e77-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="63e77-158">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="63e77-158">Related content</span></span>

<span data-ttu-id="63e77-159">[Sincronizar usuarios de dominio Microsoft 365](manage-domain-users.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="63e77-159">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>\
<span data-ttu-id="63e77-160">[Crear un grupo en el Centro de administración](../admin/create-groups/create-groups.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="63e77-160">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="63e77-161">[Tutorial: Configurar la combinación Azure Active Directory híbrida para dominios administrados](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="63e77-161">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>