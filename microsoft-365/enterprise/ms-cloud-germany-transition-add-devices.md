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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861311"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="edd9a-103">Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="edd9a-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="edd9a-104">Los dispositivos unidos y registrados de Azure AD conectados a Microsoft Cloud Deutschland deben migrarse después de la fase 9 y antes de la fase 10.</span><span class="sxs-lookup"><span data-stu-id="edd9a-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="edd9a-105">La migración de un dispositivo depende del tipo de dispositivo, el sistema operativo y la relación AAD.</span><span class="sxs-lookup"><span data-stu-id="edd9a-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="edd9a-106">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="edd9a-106">Frequently asked questions</span></span>

<span data-ttu-id="edd9a-107">**¿Cómo puedo saber si mi organización está afectada?**</span><span class="sxs-lookup"><span data-stu-id="edd9a-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="edd9a-108">Los administradores deben comprobar si tienen dispositivos registrados o unidos `https://portal.microsoftazure.de` a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="edd9a-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="edd9a-109">Si su organización tiene dispositivos registrados, se verá afectado.</span><span class="sxs-lookup"><span data-stu-id="edd9a-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="edd9a-110">**¿Cuál es el impacto en mis usuarios?**</span><span class="sxs-lookup"><span data-stu-id="edd9a-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="edd9a-111">Los usuarios de un dispositivo registrado ya no podrán iniciar sesión después de que se haya completado la fase de migración [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) y se hayan deshabilitado los puntos de conexión de Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="edd9a-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="edd9a-112">Asegúrese de que todos los dispositivos estén registrados en el punto de conexión mundial antes de que su organización se desconecte de Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="edd9a-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="edd9a-113">**¿Cuándo los usuarios vuelvan a registrar sus dispositivos?**</span><span class="sxs-lookup"><span data-stu-id="edd9a-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="edd9a-114">Es fundamental para el éxito que solo desinscriba y vuelva a registrar los dispositivos una vez completada la [fase 9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)</span><span class="sxs-lookup"><span data-stu-id="edd9a-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="edd9a-115">Debes finalizar el nuevo registro antes de que se inicie la fase 10, de lo contrario podrías perder el acceso al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="edd9a-116">**¿Cómo restaure el estado de mi dispositivo después de la migración?**</span><span class="sxs-lookup"><span data-stu-id="edd9a-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="edd9a-117">En el caso de los dispositivos Windows propiedad de la compañía que están registrados en Azure AD, los administradores podrán administrar la migración de estos dispositivos a través de flujos de trabajo desencadenados de forma remota que anularán el registro de los estados de dispositivo antiguos.</span><span class="sxs-lookup"><span data-stu-id="edd9a-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="edd9a-118">Para todos los demás dispositivos, incluidos los dispositivos Windows personales que están registrados en Azure AD, el usuario final debe realizar estos pasos manualmente.</span><span class="sxs-lookup"><span data-stu-id="edd9a-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="edd9a-119">Para los dispositivos unidos a Azure AD, los usuarios deben tener una cuenta de administrador local para anular el registro y volver a registrar sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edd9a-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="edd9a-120">Consulta instrucciones detalladas sobre cómo restaurar correctamente los estados del dispositivo a continuación.</span><span class="sxs-lookup"><span data-stu-id="edd9a-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="edd9a-121">**¿Cómo sé que todos mis dispositivos están registrados en la nube pública?**</span><span class="sxs-lookup"><span data-stu-id="edd9a-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="edd9a-122">Para comprobar si los dispositivos están registrados en la nube pública, debe exportar y descargar la lista de dispositivos del portal de Azure AD a una Excel de cálculo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="edd9a-123">A continuación, filtre los dispositivos registrados (mediante la columna _registeredTime)_ después de la fase de migración [Independiente de Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="edd9a-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="edd9a-124">Consideraciones adicionales</span><span class="sxs-lookup"><span data-stu-id="edd9a-124">Additional considerations</span></span>
<span data-ttu-id="edd9a-125">El registro del dispositivo se desactiva después de la migración del inquilino y no se puede habilitar ni deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="edd9a-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="edd9a-126">Si no se usa Intune, inicie sesión en la suscripción y ejecute este comando para volver a activar la opción:</span><span class="sxs-lookup"><span data-stu-id="edd9a-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="edd9a-127">**IMPORTANTE:** La entidad de servicio de Intune se habilitará después de la migración comercial, lo que implica la activación del registro de dispositivos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="edd9a-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="edd9a-128">Si bloqueó el registro de dispositivos de Azure AD antes de la migración, debe deshabilitar la entidad de servicio de Intune con PowerShell para deshabilitar de nuevo el registro de dispositivos de Azure AD con el portal de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="edd9a-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="edd9a-129">Puede deshabilitar la entidad de servicio de Intune con este comando en el Azure Active Directory PowerShell para Graph módulo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="edd9a-130">Unión a Azure AD</span><span class="sxs-lookup"><span data-stu-id="edd9a-130">Azure AD Join</span></span>
<span data-ttu-id="edd9a-131">Esto se aplica a Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edd9a-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="edd9a-132">Si un dispositivo está unido a Azure AD, debe desconectarse de Azure AD y volver a conectarse.</span><span class="sxs-lookup"><span data-stu-id="edd9a-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="edd9a-133">[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="edd9a-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="edd9a-134">Si el usuario es un administrador en el dispositivo Windows 10, el usuario puede anular el registro del dispositivo de Azure AD y volver a unirlo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="edd9a-135">Si no tiene privilegios de administrador, el usuario necesita credenciales de una cuenta de administrador local en este equipo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="edd9a-136">Un administrador puede crear una cuenta de administrador local en el dispositivo que sigue esta ruta de configuración:</span><span class="sxs-lookup"><span data-stu-id="edd9a-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="edd9a-137">*Configuración > cuentas > otras cuentas > credenciales desconocidas > Agregar usuario sin Microsoft-Account*</span><span class="sxs-lookup"><span data-stu-id="edd9a-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="edd9a-138">Paso 1: Determinar si el dispositivo está unido a Azure ID.</span><span class="sxs-lookup"><span data-stu-id="edd9a-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="edd9a-139">Inicie sesión con los usuarios Correo electrónico y contraseña.</span><span class="sxs-lookup"><span data-stu-id="edd9a-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="edd9a-140">Vaya a Configuración > cuentas > Access Work Or School.</span><span class="sxs-lookup"><span data-stu-id="edd9a-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="edd9a-141">Busque un usuario en la lista con **conectado a ... 's Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="edd9a-142">Si existe un usuario conectado, continúe con el paso 2.</span><span class="sxs-lookup"><span data-stu-id="edd9a-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="edd9a-143">Si no es así, no se requiere ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="edd9a-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="edd9a-144">Paso 2: Desconectar el dispositivo de Azure AD</span><span class="sxs-lookup"><span data-stu-id="edd9a-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="edd9a-145">Pulsa **Desconectar** en el trabajo conectado o cuenta educativa.</span><span class="sxs-lookup"><span data-stu-id="edd9a-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="edd9a-146">Confirme la desconexión dos veces.</span><span class="sxs-lookup"><span data-stu-id="edd9a-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="edd9a-147">Escriba el nombre de usuario y la contraseña del administrador local.</span><span class="sxs-lookup"><span data-stu-id="edd9a-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="edd9a-148">El dispositivo está desconectado.</span><span class="sxs-lookup"><span data-stu-id="edd9a-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="edd9a-149">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="edd9a-150">Paso 3: Unir el dispositivo a Azure AD</span><span class="sxs-lookup"><span data-stu-id="edd9a-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="edd9a-151">el usuario inicia sesión con las credenciales del administrador local</span><span class="sxs-lookup"><span data-stu-id="edd9a-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="edd9a-152">Vaya a **Configuración,** a **continuación, Cuentas** y **acceso a trabajo o escuela**</span><span class="sxs-lookup"><span data-stu-id="edd9a-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="edd9a-153">Pulsa **Conectar**</span><span class="sxs-lookup"><span data-stu-id="edd9a-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="edd9a-154">**IMPORTANTE:** Pulsa **Unirse a Azure AD**</span><span class="sxs-lookup"><span data-stu-id="edd9a-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="edd9a-155">Escriba la dirección de correo electrónico y la contraseña del usuario.</span><span class="sxs-lookup"><span data-stu-id="edd9a-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="edd9a-156">El dispositivo está conectado</span><span class="sxs-lookup"><span data-stu-id="edd9a-156">The device is connected</span></span>
6.  <span data-ttu-id="edd9a-157">Reiniciar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="edd9a-157">Restart the device</span></span> 
7.  <span data-ttu-id="edd9a-158">firmar con su dirección de correo electrónico y contraseña</span><span class="sxs-lookup"><span data-stu-id="edd9a-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="edd9a-159">Azure AD Registrado (propiedad de la compañía)</span><span class="sxs-lookup"><span data-stu-id="edd9a-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="edd9a-160">Para determinar si el Windows 10 está registrado en Azure AD, ejecute el siguiente comando en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="edd9a-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="edd9a-161">Si el dispositivo está registrado en Azure AD, verá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="edd9a-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="edd9a-162">Para quitar la cuenta registrada de Azure AD existente en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="edd9a-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="edd9a-163">Para quitar la cuenta registrada de Azure AD en el dispositivo, use CleanupWPJ, una herramienta que puede descargar desde aquí: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="edd9a-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="edd9a-164">Extraiga el archivo ZIP y ejecute **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="edd9a-165">Esta herramienta iniciará el ejecutable correcto en función de la versión de Windows en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="edd9a-166">Mediante un mecanismo como la directiva de grupo, el administrador puede ejecutar el comando en el dispositivo en el contexto de cualquier usuario que haya iniciado sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="edd9a-167">Para deshabilitar los mensajes del Administrador de cuentas web para registrar el dispositivo en Azure AD, agregue este valor del Registro:</span><span class="sxs-lookup"><span data-stu-id="edd9a-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="edd9a-168">Ubicación: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="edd9a-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="edd9a-169">Tipo: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="edd9a-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="edd9a-170">Nombre: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="edd9a-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="edd9a-171">Datos de valor: 1</span><span class="sxs-lookup"><span data-stu-id="edd9a-171">Value data: 1</span></span>

<span data-ttu-id="edd9a-172">La presencia de este valor del Registro debe bloquear la unión al lugar de trabajo e impedir que los usuarios vean mensajes para unirse al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="edd9a-173">Android</span><span class="sxs-lookup"><span data-stu-id="edd9a-173">Android</span></span>

<span data-ttu-id="edd9a-174">Para Android, los usuarios tendrán que anular el registro y volver a registrar sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="edd9a-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="edd9a-175">Esto se puede hacer a través de la Microsoft Authenticator o la Portal de empresa aplicación.</span><span class="sxs-lookup"><span data-stu-id="edd9a-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="edd9a-176">Desde la Microsoft Authenticator, los usuarios pueden ir a **Configuración > Registro de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="edd9a-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="edd9a-177">Desde allí, los usuarios pueden anular el registro y volver a registrar su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="edd9a-178">Desde el Portal de empresa, los usuarios pueden ir a la **pestaña Dispositivos** y quitar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="edd9a-179">Después, vuelva a inscribir el dispositivo mediante Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="edd9a-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="edd9a-180">Los usuarios también pueden anular el registro y volver a registrarse quitando la cuenta de la página de configuración de la cuenta y, a continuación, agregando de nuevo la cuenta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="edd9a-181">Para anular el registro y volver a registrar el dispositivo en Android mediante la Microsoft Authenticator aplicación:</span><span class="sxs-lookup"><span data-stu-id="edd9a-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="edd9a-182">Abre la Microsoft Authenticator y ve **a Configuración**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="edd9a-183">Seleccione **Registro de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="edd9a-184">Anula el registro del dispositivo **seleccionando Anular registro**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="edd9a-185">Para **registro de dispositivos,** vuelva a registrar el dispositivo escribiendo la dirección de correo electrónico y, a continuación, **seleccione Registrar**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="edd9a-186">Para anular el registro y volver a registrar un dispositivo Android con la Configuración Android:</span><span class="sxs-lookup"><span data-stu-id="edd9a-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="edd9a-187">Abra **Device Configuración** y vaya a **Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="edd9a-188">Seleccione la cuenta de trabajo que desea volver a registrar y seleccione **Quitar cuenta**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="edd9a-189">Después de quitar la cuenta, en la **página Cuentas,** seleccione **Agregar cuenta > cuenta de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="edd9a-190">En **Workplace Join**, escriba su dirección de correo electrónico y seleccione **Unirse** para completar el registro del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="edd9a-191">Para anular el registro y volver a registrar el dispositivo en Android desde Portal de empresa:</span><span class="sxs-lookup"><span data-stu-id="edd9a-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="edd9a-192">Inicie Portal de empresa y vaya a **la pestaña Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="edd9a-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="edd9a-193">Selecciona el dispositivo para ver los detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="edd9a-194">En el menú puntos suspensivos (tres puntos), selecciona **Quitar** dispositivo y completa la eliminación confirmando en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="edd9a-195">Ahora debes haber cerrado sesión en la Portal de empresa aplicación.</span><span class="sxs-lookup"><span data-stu-id="edd9a-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="edd9a-196">Selecciona **Iniciar sesión** para volver a registrar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="edd9a-197">Para obtener más información sobre las acciones necesarias durante la fase de migración de esta carga de trabajo, o el impacto en la administración o el uso, revise la información sobre Azure Active Directory (Azure AD) en Información adicional de Azure AD para la migración desde [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="edd9a-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="edd9a-198">iOS</span><span class="sxs-lookup"><span data-stu-id="edd9a-198">iOS</span></span>

<span data-ttu-id="edd9a-199">En dispositivos iOS, un usuario tendrá que quitar manualmente las cuentas almacenadas en caché del Microsoft Authenticator, anular el registro del dispositivo y cerrar sesión de cualquier aplicación nativa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="edd9a-200">Paso 1: Si está presente, quite la cuenta de la Microsoft Authenticator aplicación</span><span class="sxs-lookup"><span data-stu-id="edd9a-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="edd9a-201">Pulsa la cuenta en la Microsoft Authenticator aplicación.</span><span class="sxs-lookup"><span data-stu-id="edd9a-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="edd9a-202">Pulsa el **Configuración** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="edd9a-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="edd9a-203">Si no ve el  icono Configuración, es posible que no esté usando la versión más reciente de Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="edd9a-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="edd9a-204">Pulsa el **botón Quitar cuenta.**</span><span class="sxs-lookup"><span data-stu-id="edd9a-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="edd9a-205">Pulsa **Todas las aplicaciones en este dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="edd9a-206">Paso 2: Anular el registro del dispositivo desde la Microsoft Authenticator aplicación</span><span class="sxs-lookup"><span data-stu-id="edd9a-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="edd9a-207">Pulsa el icono del menú en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="edd9a-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="edd9a-208">Pulsa **Configuración** y, a continuación, **Registro de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="edd9a-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="edd9a-209">Si se muestra tu cuenta, pulsa **Anular registro del dispositivo** y **Continuar** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="edd9a-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="edd9a-210">No debería ver ninguna cuenta después de eso.</span><span class="sxs-lookup"><span data-stu-id="edd9a-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="edd9a-211">Paso 3: Cerrar sesión de aplicaciones individuales si es necesario</span><span class="sxs-lookup"><span data-stu-id="edd9a-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="edd9a-212">Los usuarios pueden ir a aplicaciones individuales como Outlook, Teams y OneDrive y quitar cuentas de esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="edd9a-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="edd9a-213">Más información</span><span class="sxs-lookup"><span data-stu-id="edd9a-213">More information</span></span>

<span data-ttu-id="edd9a-214">Introducción:</span><span class="sxs-lookup"><span data-stu-id="edd9a-214">Getting started:</span></span>

- [<span data-ttu-id="edd9a-215">Migración de Microsoft Cloud Deutschland a Office 365 servicios en las nuevas regiones del centro de datos alemán</span><span class="sxs-lookup"><span data-stu-id="edd9a-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="edd9a-216">Asistencia para la migración a Microsoft Cloud Alemania</span><span class="sxs-lookup"><span data-stu-id="edd9a-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="edd9a-217">Cómo participar en la migración</span><span class="sxs-lookup"><span data-stu-id="edd9a-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="edd9a-218">Experiencia del cliente durante la migración</span><span class="sxs-lookup"><span data-stu-id="edd9a-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="edd9a-219">Pasar a través de la transición:</span><span class="sxs-lookup"><span data-stu-id="edd9a-219">Moving through the transition:</span></span>

- [<span data-ttu-id="edd9a-220">Impactos y acciones de las fases de migración</span><span class="sxs-lookup"><span data-stu-id="edd9a-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="edd9a-221">Pre-work adicional</span><span class="sxs-lookup"><span data-stu-id="edd9a-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="edd9a-222">Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="edd9a-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="edd9a-223">Aplicaciones en la nube:</span><span class="sxs-lookup"><span data-stu-id="edd9a-223">Cloud apps:</span></span>

- [<span data-ttu-id="edd9a-224">Información del programa de migración de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="edd9a-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="edd9a-225">Información del programa de migración de Power BI</span><span class="sxs-lookup"><span data-stu-id="edd9a-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="edd9a-226">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="edd9a-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)