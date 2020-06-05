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
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564961"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="04028-103">Habilitar los dispositivos Windows 10 Unidos a un dominio para que los administre Microsoft 365 empresa Premium</span><span class="sxs-lookup"><span data-stu-id="04028-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="04028-104">Si su organización usa Windows Server Active Directory local, puede configurar Microsoft 365 Business Premium para proteger sus dispositivos con Windows 10, a la vez que mantiene el acceso a los recursos locales que requieren autenticación local.</span><span class="sxs-lookup"><span data-stu-id="04028-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="04028-105">Para configurar esta protección, puede implementar dispositivos de **Azure ad Unidos híbridos**.</span><span class="sxs-lookup"><span data-stu-id="04028-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="04028-106">Estos dispositivos se unen a su Active Directory local y a su Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="04028-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="04028-107">Este vídeo describe los pasos para configurar esta configuración para el escenario más común, que también se detalla en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="04028-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="04028-108">Antes de empezar, asegúrese de completar estos pasos:</span><span class="sxs-lookup"><span data-stu-id="04028-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="04028-109">Sincronice los usuarios a Azure AD con Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="04028-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="04028-110">Complete la sincronización de la unidad organizativa (OU) de Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="04028-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="04028-111">Asegúrese de que todos los usuarios de dominio que sincronice tienen licencias para Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="04028-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="04028-112">Consulte [sincronizar usuarios de dominio a Microsoft](manage-domain-users.md) para conocer los pasos.</span><span class="sxs-lookup"><span data-stu-id="04028-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="04028-113">1. comprobar la autoridad de MDM en Intune</span><span class="sxs-lookup"><span data-stu-id="04028-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="04028-114">Vaya a portal.azure.com y, en la parte superior de la página, busque Intune.</span><span class="sxs-lookup"><span data-stu-id="04028-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="04028-115">En la página Microsoft Intune, seleccione **inscripción de dispositivo** y, en la página **información general** , asegúrese de que la **autoridad de MDM** es **Intune**.</span><span class="sxs-lookup"><span data-stu-id="04028-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="04028-116">Si la **entidad de MDM** es **ninguna**, haga clic en la **entidad de MDM** para establecerla en **Intune**.</span><span class="sxs-lookup"><span data-stu-id="04028-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="04028-117">Si **la entidad de MDM** es **Microsoft Office 365**, vaya a dispositivos de inscripción de **dispositivos**  >  **Enroll devices** y use el cuadro de diálogo **Agregar autoridad de MDM** que se encuentra a la derecha para agregar la autoridad de **Intune MDM** (el cuadro de diálogo **Agregar autoridad de MDM** solo está disponible si la autoridad de **MDM** está establecida en Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="04028-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="04028-118">2. Compruebe que Azure AD esté habilitado para unirse a los equipos</span><span class="sxs-lookup"><span data-stu-id="04028-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="04028-119">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione **Azure Active Directory** (seleccione Mostrar todo si Azure Active Directory no está visible) en la lista **centros de administración** .</span><span class="sxs-lookup"><span data-stu-id="04028-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="04028-120">En el **centro de administración de Azure Active**Directory, vaya a **Azure Active Directory** , elija **dispositivos** y, a continuación, **configuración de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="04028-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="04028-121">Comprobar**que los usuarios pueden unirse a dispositivos a Azure ad** está habilitado</span><span class="sxs-lookup"><span data-stu-id="04028-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="04028-122">Para habilitar todos los usuarios, establezca en **todos**.</span><span class="sxs-lookup"><span data-stu-id="04028-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="04028-123">Para habilitar usuarios específicos, defina como **seleccionado** para habilitar un grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="04028-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="04028-124">Agregue los usuarios de dominio que desee sincronizar en Azure AD a un [grupo de seguridad](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="04028-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="04028-125">Elija **seleccionar grupos** para habilitar el ámbito de usuario de MDM para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04028-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="04028-126">3. comprobar que Azure AD está habilitado para MDM</span><span class="sxs-lookup"><span data-stu-id="04028-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="04028-127">Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> y seleccione seleccionar **extremo** **administradora** t (seleccionar **Mostrar todo** si el administrador de puntos de conexión no está visible).</span><span class="sxs-lookup"><span data-stu-id="04028-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="04028-128">En el **centro de administración de Microsoft Endpoint Manager**, vaya a **dispositivos**  >  **Windows**inscripción automática de  >  **inscripción**  >  **Automatic Enrollment**.</span><span class="sxs-lookup"><span data-stu-id="04028-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="04028-129">Compruebe que el ámbito de usuario de MDM esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="04028-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="04028-130">Para inscribir todos los equipos, establezca en **todos** para inscribir de forma automática a todos los equipos de los usuarios que se unen a Azure ad y a los nuevos equipos cuando los usuarios agregan una cuenta profesional a Windows.</span><span class="sxs-lookup"><span data-stu-id="04028-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="04028-131">Establezca en **some** para inscribir los equipos de un grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="04028-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="04028-132">Agregue los usuarios de dominio que desee sincronizar en Azure AD a un [grupo de seguridad](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="04028-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="04028-133">Elija **seleccionar grupos** para habilitar el ámbito de usuario de MDM para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04028-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="04028-134">4. configurar el punto de conexión de servicio (SCP)</span><span class="sxs-lookup"><span data-stu-id="04028-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="04028-135">Estos pasos se han simplificado desde [configurar la Unión híbrida de Azure ad](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="04028-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="04028-136">Para completar los pasos necesarios para usar Azure AD Connect y las contraseñas de administrador global y de administración de Active Directory de Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="04028-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="04028-137">Inicie Azure AD Connect y, a continuación, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="04028-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="04028-138">En la página **tareas adicionales** , seleccione **configurar opciones de dispositivo**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04028-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="04028-139">En la página **información general** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04028-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="04028-140">En la página **conectar con Azure ad** , escriba las credenciales de un administrador global para Microsoft 365 empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="04028-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="04028-141">En la página **Opciones de dispositivo** , seleccione configurar la **Unión híbrida de Azure ad**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04028-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="04028-142">En la página **SCP** , para cada bosque en el que desee que Azure ad Connect configure el SCP, complete los pasos siguientes y, a continuación, seleccione **siguiente**:</span><span class="sxs-lookup"><span data-stu-id="04028-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="04028-143">Active la casilla situada junto al nombre del bosque.</span><span class="sxs-lookup"><span data-stu-id="04028-143">Check the box beside the forest name.</span></span> <span data-ttu-id="04028-144">El bosque debe ser el nombre de dominio de AD.</span><span class="sxs-lookup"><span data-stu-id="04028-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="04028-145">En la columna **servicio de autenticación** , abra la lista desplegable y seleccione nombre de dominio coincidentes (solo debe haber una única opción).</span><span class="sxs-lookup"><span data-stu-id="04028-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="04028-146">Seleccione **Agregar** para especificar las credenciales de administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="04028-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="04028-147">En la página **sistemas operativos de dispositivos** , seleccione solo dispositivos Unidos a un dominio de Windows 10 o posterior.</span><span class="sxs-lookup"><span data-stu-id="04028-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="04028-148">En la página **listo para configurar** , seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="04028-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="04028-149">En la página **configuración completada** , seleccione **salir**.</span><span class="sxs-lookup"><span data-stu-id="04028-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="04028-150">5. crear un GPO para la inscripción de Intune: método ADMX</span><span class="sxs-lookup"><span data-stu-id="04028-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="04028-151">Utilizados. Archivo de plantilla ADMX.</span><span class="sxs-lookup"><span data-stu-id="04028-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="04028-152">Inicie sesión en el servidor de ad, busque y abra Administración de directivas de grupo de herramientas del **Administrador del servidor**  >  **Tools**  >  **Group Policy Management**.</span><span class="sxs-lookup"><span data-stu-id="04028-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="04028-153">Seleccione el nombre de dominio en **dominios** y haga clic con el botón secundario en **objetos de directiva de grupo** para seleccionar **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="04028-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="04028-154">Asigne un nombre al nuevo GPO, por ejemplo, "*Cloud_Enrollment*" y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="04028-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="04028-155">Haga clic con el botón derecho en el nuevo GPO en **objetos de directiva de grupo** y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="04028-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="04028-156">En el **Editor de administración de directivas de grupo**, vaya a directivas de **configuración del equipo**de  >  **Policies**  >  **plantillas administrativas**de  >  **Windows Components**  >  **MDM**.</span><span class="sxs-lookup"><span data-stu-id="04028-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="04028-157">Haga clic con el botón secundario en **Habilitar la inscripción automática de MDM con credenciales de Azure ad predeterminadas** y seleccione Aceptar **habilitado**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="04028-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="04028-158">Cierre la ventana del editor.</span><span class="sxs-lookup"><span data-stu-id="04028-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04028-159">Si no ve la Directiva habilitar la **inscripción automática de MDM con credenciales de Azure ad predeterminadas**, vea [obtener las últimas plantillas administrativas](#get-the-latest-administrative-templates).</span><span class="sxs-lookup"><span data-stu-id="04028-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="04028-160">6. implementar la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="04028-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="04028-161">En el administrador de servidores, en **dominios** > objetos de directiva de grupo, seleccione el GPO del paso 3 anterior, por ejemplo, "Cloud_Enrollment".</span><span class="sxs-lookup"><span data-stu-id="04028-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="04028-162">Seleccione la pestaña **ámbito** para el GPO.</span><span class="sxs-lookup"><span data-stu-id="04028-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="04028-163">En la pestaña ámbito del GPO, haga clic con el botón secundario en el vínculo al dominio en **vínculos**.</span><span class="sxs-lookup"><span data-stu-id="04028-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="04028-164">Seleccione **enforced** para implementar el GPO y, a continuación, haga clic en **Aceptar** en la pantalla de confirmación.</span><span class="sxs-lookup"><span data-stu-id="04028-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="04028-165">Obtener las plantillas administrativas más recientes</span><span class="sxs-lookup"><span data-stu-id="04028-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="04028-166">Si no ve la Directiva habilitar la **inscripción automática de MDM con credenciales de Azure ad predeterminadas**, puede deberse a que no tiene instalado ADMX para Windows 10, versión 1803, versión 1809 o versión 1903.</span><span class="sxs-lookup"><span data-stu-id="04028-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="04028-167">Para solucionar el problema, siga estos pasos (Nota: la versión más reciente de MDM. ADMX es compatible con versiones anteriores):</span><span class="sxs-lookup"><span data-stu-id="04028-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="04028-168">Descargar: [plantillas administrativas (. admx) para Windows 10 May 2019 actualización (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="04028-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="04028-169">Instale el paquete en el controlador de dominio principal (PDC).</span><span class="sxs-lookup"><span data-stu-id="04028-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="04028-170">Navegue, en función de la versión de la carpeta: **c:\Archivos de programa (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="04028-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="04028-171">Cambie el nombre de la carpeta de **definiciones de directiva** en la ruta de acceso anterior a **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="04028-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="04028-172">Copie la carpeta **PolicyDefinitions** en **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="04028-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="04028-173">Si tiene previsto usar una tienda de directivas central para todo el dominio, agregue allí el contenido de PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="04028-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="04028-174">Reinicie el controlador de dominio principal para que la Directiva esté disponible.</span><span class="sxs-lookup"><span data-stu-id="04028-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="04028-175">Este procedimiento también funcionará para versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="04028-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="04028-176">En este momento, podrá ver la directiva **Habilitar la inscripción automática de MDM con credenciales de Azure ad predeterminadas** disponibles.</span><span class="sxs-lookup"><span data-stu-id="04028-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

