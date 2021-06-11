---
title: Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: información adicional del dispositivo sobre los servicios al pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 servicios en la nueva región del centro de datos alemán.'
ms.openlocfilehash: cdb3278e1d96b2ebdced122ab53db716c3195d8c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903890"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="be5e6-103">Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="be5e6-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="be5e6-104">Los dispositivos unidos y registrados de Azure AD conectados a Microsoft Cloud Deutschland deben migrarse después de la fase 9 y antes de la fase 10.</span><span class="sxs-lookup"><span data-stu-id="be5e6-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="be5e6-105">La migración de un dispositivo depende del tipo de dispositivo, el sistema operativo y la relación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be5e6-105">The migration of a device depends on the devices type, operating system and Azure AD relation.</span></span> 

## <a name="azure-ad-joined-windows-10-devices"></a><span data-ttu-id="be5e6-106">Dispositivos unidos Windows 10 Azure AD</span><span class="sxs-lookup"><span data-stu-id="be5e6-106">Azure AD Joined Windows 10 devices</span></span>
<span data-ttu-id="be5e6-107">Si un Windows 10 está unido a Azure AD, debe desconectarse de Azure AD y debe conectarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-107">If a Windows 10 device is Azure AD joined, it must be disconnected from Azure AD and must be connected again.</span></span> 

<span data-ttu-id="be5e6-108">[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="be5e6-108">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="be5e6-109">Si el usuario es un administrador en el dispositivo Windows 10, el usuario puede anular el registro del dispositivo de Azure AD y volver a unirlo en tres pasos.</span><span class="sxs-lookup"><span data-stu-id="be5e6-109">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again in three steps.</span></span> 

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="be5e6-110">Paso 1: Determinar si el dispositivo está unido a Azure ID.</span><span class="sxs-lookup"><span data-stu-id="be5e6-110">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="be5e6-111">Inicie sesión con su cuenta profesional.</span><span class="sxs-lookup"><span data-stu-id="be5e6-111">Sign in with your work account.</span></span>
2.  <span data-ttu-id="be5e6-112">Vaya a **Configuración**  >  **cuentas acceso** a trabajo o  >  **escuela**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-112">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span> 
3.  <span data-ttu-id="be5e6-113">Buscar una cuenta en la lista con **conectado a [...]' s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-113">Look for an account in the list with **connected to […]‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="be5e6-114">Si existe una cuenta conectada, continúe con el paso 2.</span><span class="sxs-lookup"><span data-stu-id="be5e6-114">If a connected account exists, proceed with Step 2.</span></span> 
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="be5e6-115">Paso 2: Desconectar el dispositivo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="be5e6-115">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="be5e6-116">Haga **clic en** Desconectar en el trabajo conectado o cuenta educativa.</span><span class="sxs-lookup"><span data-stu-id="be5e6-116">Click **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="be5e6-117">Confirme la desconexión dos veces.</span><span class="sxs-lookup"><span data-stu-id="be5e6-117">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="be5e6-118">Escriba un nombre de usuario y una contraseña de administrador local.</span><span class="sxs-lookup"><span data-stu-id="be5e6-118">Enter a local administrator username and password.</span></span> <span data-ttu-id="be5e6-119">El dispositivo está desconectado.</span><span class="sxs-lookup"><span data-stu-id="be5e6-119">The device is disconnected.</span></span>
4.  <span data-ttu-id="be5e6-120">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-120">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="be5e6-121">Paso 3: Unir el dispositivo a Azure AD</span><span class="sxs-lookup"><span data-stu-id="be5e6-121">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="be5e6-122">Inicie sesión con las credenciales del administrador local.</span><span class="sxs-lookup"><span data-stu-id="be5e6-122">Sign in with the credentials of the local administrator.</span></span>
2.  <span data-ttu-id="be5e6-123">Vaya a **Configuración**  >  **cuentas acceso** a trabajo o  >  **escuela**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-123">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3.  <span data-ttu-id="be5e6-124">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-124">Click **Connect**.</span></span>
4.  <span data-ttu-id="be5e6-125">**IMPORTANTE:** Haga clic **en Unirse a Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-125">**IMPORTANT**: Click **Join to Azure AD**.</span></span>
5.  <span data-ttu-id="be5e6-126">Escriba la dirección de correo electrónico y la contraseña de su cuenta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-126">Enter the e-mail address and password of your work account.</span></span> <span data-ttu-id="be5e6-127">El dispositivo está conectado.</span><span class="sxs-lookup"><span data-stu-id="be5e6-127">The device is connected.</span></span>
6.  <span data-ttu-id="be5e6-128">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-128">Restart the device.</span></span>
7.  <span data-ttu-id="be5e6-129">Inicie sesión con la dirección de correo electrónico y la contraseña de su cuenta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-129">Sign in with the email address and password of your work account.</span></span>

<span data-ttu-id="be5e6-130">Si el usuario no es un administrador del dispositivo, un administrador global de Azure AD puede crear la cuenta de administrador local en el dispositivo siguiendo esta ruta de configuración y deshacer la conexión del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="be5e6-130">If the user is not an administrator of the device, an Azure AD global administrator can create the local administrator account on the device following this configuration path and unjoin the device:</span></span>

<span data-ttu-id="be5e6-131">*Configuración > cuentas > otras cuentas > credenciales desconocidas > Agregar usuario sin Microsoft-Account*</span><span class="sxs-lookup"><span data-stu-id="be5e6-131">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

<span data-ttu-id="be5e6-132">Para volver a unirse, las credenciales de cualquier cuenta de trabajo de su organización se pueden usar en este paso.</span><span class="sxs-lookup"><span data-stu-id="be5e6-132">For re-joining, the credentials of any work account from your organization can be used in this step.</span></span> 

<span data-ttu-id="be5e6-133">Ten en cuenta que la cuenta de trabajo usada para unirse al dispositivo se promocionará automáticamente como administrador del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-133">Please consider that the work account used to join the device will be automatically promoted as an Administrator of the device.</span></span>
<span data-ttu-id="be5e6-134">Cualquier otra cuenta de trabajo de la organización puede iniciar sesión en el dispositivo, pero no tiene privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="be5e6-134">Any other work account from the organization can sign in to the device, but has no administrator privileges.</span></span>

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a><span data-ttu-id="be5e6-135">Azure AD registrado (unido al lugar de trabajo) Windows 10 dispositivos</span><span class="sxs-lookup"><span data-stu-id="be5e6-135">Azure AD registered (workplace-joined) Windows 10 devices</span></span>
<span data-ttu-id="be5e6-136">Si un Windows 10 está registrado en Azure AD, debe desconectarse de Azure AD y conectarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-136">If a Windows 10 device is Azure AD registered, it needs to be disconnected from the Azure AD and connected again.</span></span>

<span data-ttu-id="be5e6-137">[![Azure AD Device Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="be5e6-137">[ ![Azure AD Device Re-Registration Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a><span data-ttu-id="be5e6-138">Paso 1: Determinar si el dispositivo está registrado en Azure ID.</span><span class="sxs-lookup"><span data-stu-id="be5e6-138">Step 1: Determine if the device is Azure ID registered</span></span>
1.  <span data-ttu-id="be5e6-139">Inicie sesión con el usuario.</span><span class="sxs-lookup"><span data-stu-id="be5e6-139">Sign in with your user.</span></span>
2.  <span data-ttu-id="be5e6-140">Vaya a **Configuración**  >  **cuentas acceso** a trabajo o  >  **escuela**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-140">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span> 
3.  <span data-ttu-id="be5e6-141">Descubrir la cuenta de trabajo en la lista y comprobar si está **conectada a [...]' s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-141">Discover your work account in the list and check if it is **connected to […]‘s Azure AD**.</span></span>

    <span data-ttu-id="be5e6-142">Si la cuenta de trabajo está en la lista pero NO está conectada a azure AD, continúe con el paso 2.</span><span class="sxs-lookup"><span data-stu-id="be5e6-142">If your work account is in the list but NOT connected to an Azure AD, proceed with step 2.</span></span>

    <span data-ttu-id="be5e6-143">De lo contrario, el dispositivo es un dispositivo unido a Azure AD y tiene que hacer referencia a [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).</span><span class="sxs-lookup"><span data-stu-id="be5e6-143">Otherwise, your device is an Azure AD joined device and you have to refer to [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="be5e6-144">Paso 2: Desconectar el dispositivo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="be5e6-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="be5e6-145">Haz clic en tu cuenta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-145">Click on your work account.</span></span> <span data-ttu-id="be5e6-146">Aparecen los botones *Información* *y* Desconectar.</span><span class="sxs-lookup"><span data-stu-id="be5e6-146">The buttons *Info* and *Disconnect* appear.</span></span>
2.  <span data-ttu-id="be5e6-147">Haga clic **en Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-147">Click **Disconnect**.</span></span> 
3.  <span data-ttu-id="be5e6-148">Para confirmar la eliminación de la cuenta del dispositivo, haga clic **en Sí**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-148">Confirm account removal from the device by clicking **Yes**.</span></span>
### <a name="step-3-connect-the-device-to-azure-ad"></a><span data-ttu-id="be5e6-149">Paso 3: Conectar el dispositivo a Azure AD</span><span class="sxs-lookup"><span data-stu-id="be5e6-149">Step 3: Connect the device to Azure AD</span></span>
1.  <span data-ttu-id="be5e6-150">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-150">Click **Connect**.</span></span>
2.  <span data-ttu-id="be5e6-151">Escriba la dirección de correo electrónico de su cuenta de trabajo y haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-151">Enter the email address of your work account and click **Next**.</span></span>
3.  <span data-ttu-id="be5e6-152">Escriba la contraseña de su cuenta de trabajo y haga clic **en Iniciar sesión.**</span><span class="sxs-lookup"><span data-stu-id="be5e6-152">Enter the password of your work account and click **Sign in**.</span></span>
4.  <span data-ttu-id="be5e6-153">Confirme haciendo clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-153">Confirm by clicking **Done**.</span></span> <span data-ttu-id="be5e6-154">La cuenta de trabajo aparece de nuevo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-154">Your work account is listed again.</span></span>

## <a name="android"></a><span data-ttu-id="be5e6-155">Android</span><span class="sxs-lookup"><span data-stu-id="be5e6-155">Android</span></span>

<span data-ttu-id="be5e6-156">Para Android, los usuarios tendrán que anular el registro y volver a registrar sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="be5e6-156">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="be5e6-157">Esto se puede hacer a través de la Microsoft Authenticator o la Portal de empresa aplicación.</span><span class="sxs-lookup"><span data-stu-id="be5e6-157">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="be5e6-158">Desde la Microsoft Authenticator, los usuarios pueden ir a **Configuración > Registro de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="be5e6-158">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="be5e6-159">Desde allí, los usuarios pueden anular el registro y volver a registrar su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-159">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="be5e6-160">Desde el Portal de empresa, los usuarios pueden ir a la **pestaña Dispositivos** y quitar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-160">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="be5e6-161">Después, vuelva a inscribir el dispositivo mediante Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="be5e6-161">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="be5e6-162">Los usuarios también pueden anular el registro y volver a registrarse quitando la cuenta de la página de configuración de la cuenta y, a continuación, agregando de nuevo la cuenta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-162">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="be5e6-163">Para anular el registro y volver a registrar el dispositivo en Android mediante la Microsoft Authenticator aplicación:</span><span class="sxs-lookup"><span data-stu-id="be5e6-163">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="be5e6-164">Abre la Microsoft Authenticator y ve **a Configuración**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-164">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="be5e6-165">Seleccione **Registro de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-165">Select **Device registration**.</span></span>
3.  <span data-ttu-id="be5e6-166">Anula el registro del dispositivo **seleccionando Anular registro**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-166">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="be5e6-167">Para **registro de dispositivos,** vuelva a registrar el dispositivo escribiendo la dirección de correo electrónico y, a continuación, **seleccione Registrar**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-167">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="be5e6-168">Para anular el registro y volver a registrar un dispositivo Android con la Configuración Android:</span><span class="sxs-lookup"><span data-stu-id="be5e6-168">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="be5e6-169">Abra **Device Configuración** y vaya a **Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-169">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="be5e6-170">Seleccione la cuenta de trabajo que desea volver a registrar y seleccione **Quitar cuenta**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-170">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="be5e6-171">Después de quitar la cuenta, en la **página Cuentas,** seleccione **Agregar cuenta > cuenta de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-171">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="be5e6-172">En **Workplace Join**, escriba su dirección de correo electrónico y seleccione **Unirse** para completar el registro del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-172">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="be5e6-173">Para anular el registro y volver a registrar el dispositivo en Android desde Portal de empresa:</span><span class="sxs-lookup"><span data-stu-id="be5e6-173">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="be5e6-174">Inicie Portal de empresa y vaya a **la pestaña Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="be5e6-174">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="be5e6-175">Selecciona el dispositivo para ver los detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-175">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="be5e6-176">En el menú puntos suspensivos (tres puntos), selecciona **Quitar** dispositivo y completa la eliminación confirmando en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-176">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="be5e6-177">Ahora debes haber cerrado sesión en la Portal de empresa aplicación.</span><span class="sxs-lookup"><span data-stu-id="be5e6-177">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="be5e6-178">Selecciona **Iniciar sesión** para volver a registrar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-178">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="be5e6-179">Para obtener más información sobre las acciones necesarias durante la fase de migración de esta carga de trabajo, o el impacto en la administración o el uso, revise la información sobre Azure Active Directory (Azure AD) en Información adicional de Azure AD para la migración desde [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="be5e6-179">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="be5e6-180">iOS</span><span class="sxs-lookup"><span data-stu-id="be5e6-180">iOS</span></span>

<span data-ttu-id="be5e6-181">En dispositivos iOS, un usuario tendrá que quitar manualmente las cuentas almacenadas en caché del Microsoft Authenticator, anular el registro del dispositivo y cerrar sesión de cualquier aplicación nativa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-181">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="be5e6-182">Paso 1: Si está presente, quite la cuenta de la Microsoft Authenticator aplicación</span><span class="sxs-lookup"><span data-stu-id="be5e6-182">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="be5e6-183">Pulsa la cuenta en la Microsoft Authenticator aplicación.</span><span class="sxs-lookup"><span data-stu-id="be5e6-183">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="be5e6-184">Pulsa el **Configuración** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="be5e6-184">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="be5e6-185">Si no ve el  icono Configuración, es posible que no esté usando la versión más reciente de Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="be5e6-185">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="be5e6-186">Pulsa el **botón Quitar cuenta.**</span><span class="sxs-lookup"><span data-stu-id="be5e6-186">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="be5e6-187">Pulsa **Todas las aplicaciones en este dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-187">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="be5e6-188">Paso 2: Anular el registro del dispositivo desde la Microsoft Authenticator aplicación</span><span class="sxs-lookup"><span data-stu-id="be5e6-188">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="be5e6-189">Pulsa el icono del menú en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="be5e6-189">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="be5e6-190">Pulsa **Configuración** y, a continuación, **Registro de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="be5e6-190">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="be5e6-191">Si se muestra tu cuenta, pulsa **Anular registro del dispositivo** y **Continuar** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-191">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="be5e6-192">No debería ver ninguna cuenta después de eso.</span><span class="sxs-lookup"><span data-stu-id="be5e6-192">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="be5e6-193">Paso 3: Cerrar sesión de aplicaciones individuales si es necesario</span><span class="sxs-lookup"><span data-stu-id="be5e6-193">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="be5e6-194">Los usuarios pueden ir a aplicaciones individuales como Outlook, Teams y OneDrive y quitar cuentas de esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="be5e6-194">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="be5e6-195">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="be5e6-195">Frequently asked questions</span></span>

<span data-ttu-id="be5e6-196">**¿Cómo puedo saber si mi organización está afectada?**</span><span class="sxs-lookup"><span data-stu-id="be5e6-196">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="be5e6-197">Los administradores deben comprobar si tienen dispositivos de Azure AD registrados o unidos `https://portal.microsoftazure.de` a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be5e6-197">Administrators should check `https://portal.microsoftazure.de` to determine if they have any Azure AD registered or Azure AD joined devices.</span></span> <span data-ttu-id="be5e6-198">Si su organización tiene dispositivos de Azure AD registrados o unidos a Azure AD, la organización debe seguir las instrucciones de esta página.</span><span class="sxs-lookup"><span data-stu-id="be5e6-198">If your organization has Azure AD registered or Azure AD joined devices, your organization has to follow the instructions on this page.</span></span>

<span data-ttu-id="be5e6-199">**¿Cuándo los usuarios vuelvan a registrar sus dispositivos?**</span><span class="sxs-lookup"><span data-stu-id="be5e6-199">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="be5e6-200">Es fundamental para el éxito que solo desinscriba y vuelva a registrar los dispositivos una vez completada la [fase 9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)</span><span class="sxs-lookup"><span data-stu-id="be5e6-200">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="be5e6-201">Debes finalizar el nuevo registro antes de que se inicie la fase 10, de lo contrario podrías perder el acceso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-201">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="be5e6-202">**¿Cómo sé que todos mis dispositivos están registrados en la nube pública?**</span><span class="sxs-lookup"><span data-stu-id="be5e6-202">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="be5e6-203">Para comprobar si los dispositivos están registrados en la nube pública, debe exportar y descargar la lista de dispositivos del portal de Azure AD a una Excel de cálculo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-203">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="be5e6-204">A continuación, filtre los dispositivos registrados (mediante la columna _registeredTime)_ después de la fecha en que la organización ha pasado la [fase 9 del proceso de migración](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).</span><span class="sxs-lookup"><span data-stu-id="be5e6-204">Then, filter the devices that are registered (by using the _registeredTime_ column) after the date when your organization has passed [phase 9 of the migration process](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="be5e6-205">Consideraciones adicionales</span><span class="sxs-lookup"><span data-stu-id="be5e6-205">Additional considerations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be5e6-206">La entidad de servicio de Intune se habilitará después de la [fase 3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)del proceso de migración, lo que implica la activación del registro de dispositivos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be5e6-206">The Intune service principal will be enabled after [phase 3 of the migration process](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer), which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="be5e6-207">Si bloqueó el registro de dispositivos de Azure AD antes de la migración, debe deshabilitar la entidad de servicio de Intune con PowerShell para deshabilitar de nuevo el registro de dispositivos de Azure AD con el portal de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be5e6-207">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="be5e6-208">Puede deshabilitar la entidad de servicio de Intune con este comando en el Azure Active Directory PowerShell para Graph módulo.</span><span class="sxs-lookup"><span data-stu-id="be5e6-208">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a><span data-ttu-id="be5e6-209">Más información</span><span class="sxs-lookup"><span data-stu-id="be5e6-209">More information</span></span>

<span data-ttu-id="be5e6-210">Introducción:</span><span class="sxs-lookup"><span data-stu-id="be5e6-210">Getting started:</span></span>

- [<span data-ttu-id="be5e6-211">Migración de Microsoft Cloud Deutschland a Office 365 servicios en las nuevas regiones del centro de datos alemán</span><span class="sxs-lookup"><span data-stu-id="be5e6-211">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="be5e6-212">Asistencia para la migración a Microsoft Cloud Alemania</span><span class="sxs-lookup"><span data-stu-id="be5e6-212">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="be5e6-213">Cómo participar en la migración</span><span class="sxs-lookup"><span data-stu-id="be5e6-213">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="be5e6-214">Experiencia del cliente durante la migración</span><span class="sxs-lookup"><span data-stu-id="be5e6-214">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="be5e6-215">Pasar a través de la transición:</span><span class="sxs-lookup"><span data-stu-id="be5e6-215">Moving through the transition:</span></span>

- [<span data-ttu-id="be5e6-216">Impactos y acciones de las fases de migración</span><span class="sxs-lookup"><span data-stu-id="be5e6-216">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="be5e6-217">Pre-work adicional</span><span class="sxs-lookup"><span data-stu-id="be5e6-217">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="be5e6-218">Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="be5e6-218">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="be5e6-219">Aplicaciones en la nube:</span><span class="sxs-lookup"><span data-stu-id="be5e6-219">Cloud apps:</span></span>

- [<span data-ttu-id="be5e6-220">Información del programa de migración de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="be5e6-220">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="be5e6-221">Información del programa de migración de Power BI</span><span class="sxs-lookup"><span data-stu-id="be5e6-221">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="be5e6-222">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be5e6-222">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)