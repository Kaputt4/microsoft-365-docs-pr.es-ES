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
description: 'Resumen: información adicional del dispositivo sobre los servicios al pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928161"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="3e523-103">Información adicional del dispositivo para la migración desde Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="3e523-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3e523-104">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="3e523-104">Frequently asked questions</span></span>

<span data-ttu-id="3e523-105">**¿Cómo puedo saber si mi organización está afectada?**</span><span class="sxs-lookup"><span data-stu-id="3e523-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="3e523-106">Los administradores deben `https://portal.microsoftazure.de` comprobar si tienen dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="3e523-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="3e523-107">Si su organización tiene dispositivos registrados, se verá afectado.</span><span class="sxs-lookup"><span data-stu-id="3e523-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="3e523-108">**¿Cuál es el impacto en mis usuarios?**</span><span class="sxs-lookup"><span data-stu-id="3e523-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="3e523-109">Los usuarios de un dispositivo registrado ya no podrán iniciar sesión después de que la migración entre en la fase [finalizar la migración de Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="3e523-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="3e523-110">Asegúrese de que todos los dispositivos estén registrados en el punto de conexión mundial antes de que su organización se desconecte de Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="3e523-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="3e523-111">**¿Cuándo los usuarios vuelvan a registrar sus dispositivos?**</span><span class="sxs-lookup"><span data-stu-id="3e523-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="3e523-112">Es fundamental para el éxito que solo desinscribas y vuelvas a registrar los dispositivos durante la fase de migración Independiente [de Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="3e523-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="3e523-113">**¿Cómo restaure el estado de mi dispositivo después de la migración?**</span><span class="sxs-lookup"><span data-stu-id="3e523-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="3e523-114">En el caso de los dispositivos Windows híbridos unidos a Azure AD y propiedad de la empresa que están registrados en Azure AD, los administradores podrán administrar la migración de estos dispositivos a través de flujos de trabajo desencadenados de forma remota que anularán el registro de los estados de dispositivo antiguos.</span><span class="sxs-lookup"><span data-stu-id="3e523-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="3e523-115">Para todos los demás dispositivos, incluidos los dispositivos Personales de Windows registrados en Azure AD, el usuario final debe realizar estos pasos manualmente.</span><span class="sxs-lookup"><span data-stu-id="3e523-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="3e523-116">Para los dispositivos unidos a Azure AD, los usuarios deben tener una cuenta de administrador local para anular el registro y volver a registrar sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3e523-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="3e523-117">Microsoft publicará instrucciones sobre cómo restaurar correctamente el estado del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="3e523-118">**¿Cómo sé que todos mis dispositivos están registrados en la nube pública?**</span><span class="sxs-lookup"><span data-stu-id="3e523-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="3e523-119">Para comprobar si los dispositivos están registrados en la nube pública, debe exportar y descargar la lista de dispositivos del portal de Azure AD a una hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="3e523-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="3e523-120">A continuación, filtre los dispositivos registrados (mediante la columna _registeredTime)_ después de la fase de migración [Independiente de Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="3e523-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="3e523-121">El registro del dispositivo se desactiva después de la migración del inquilino y no se puede habilitar ni deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="3e523-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="3e523-122">Si no se usa Intune, inicie sesión en la suscripción y ejecute este comando para volver a activar la opción:</span><span class="sxs-lookup"><span data-stu-id="3e523-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="3e523-123">Unión a Azure AD híbrido</span><span class="sxs-lookup"><span data-stu-id="3e523-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="3e523-124">Nivel inferior de Windows</span><span class="sxs-lookup"><span data-stu-id="3e523-124">Windows down-level</span></span>

<span data-ttu-id="3e523-125">Los dispositivos de nivel inferior de _Windows_ son dispositivos Windows que actualmente ejecutan versiones anteriores de Windows (como Windows 8.1 o Windows 7) o que ejecutan versiones de Windows Server anteriores a 2019 y 2016.</span><span class="sxs-lookup"><span data-stu-id="3e523-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="3e523-126">Si estos dispositivos se registraron antes, tendrás que anular el registro y volver a registrar esos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3e523-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="3e523-127">Para determinar si un dispositivo de nivel inferior de Windows se unió previamente a Azure AD, use el siguiente comando en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3e523-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="3e523-128">Si el dispositivo se unió previamente a Azure AD y si el dispositivo tiene conectividad de red con puntos de conexión globales de Azure AD, verá el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e523-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="3e523-129">Los dispositivos afectados tendrán el "Estado del dispositivo" con el valor "Desconocido".</span><span class="sxs-lookup"><span data-stu-id="3e523-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="3e523-130">Si el resultado es "Dispositivo no unido" o cuyo valor "Estado del dispositivo" es "Correcto", ignore las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="3e523-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="3e523-131">Solo para dispositivos que muestran que el dispositivo está unido (en virtud de deviceId, huella digital, entre otros) y cuyo valor "Estado del dispositivo" es "Desconocido", los administradores deben ejecutar el siguiente comando en el contexto de un usuario de dominio que inicie sesión en un dispositivo de nivel inferior:</span><span class="sxs-lookup"><span data-stu-id="3e523-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="3e523-132">El comando anterior solo debe ejecutarse una vez por usuario de dominio que inicie sesión en el dispositivo de nivel inferior de Windows.</span><span class="sxs-lookup"><span data-stu-id="3e523-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="3e523-133">Este comando debe ejecutarse en el contexto del inicio de sesión del usuario del dominio.</span><span class="sxs-lookup"><span data-stu-id="3e523-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="3e523-134">Debe tenerse suficiente cuidado para no ejecutar este comando cuando el usuario inicia sesión posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3e523-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="3e523-135">Cuando se ejecute el comando anterior, borrará el estado unido del equipo híbrido local unido a Azure AD para el usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="3e523-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="3e523-136">Y, si el equipo aún está configurado para que esté unido a Azure AD híbrido en el espacio empresarial, intentará unirse cuando el usuario vuelva a abrir sesión.</span><span class="sxs-lookup"><span data-stu-id="3e523-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="3e523-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="3e523-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="3e523-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="3e523-138">Unjoin</span></span>

<span data-ttu-id="3e523-139">Para determinar si el dispositivo Windows 10 se unió previamente a Azure AD, ejecute el siguiente comando en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3e523-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="3e523-140">Si el dispositivo está unido a Azure AD híbrido, el administrador vería el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="3e523-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="3e523-141">Si el resultado es "AzureAdJoined : No", ignore las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="3e523-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="3e523-142">Solo para dispositivos que muestran que el dispositivo está unido a Azure AD, ejecute el siguiente comando como administrador para quitar el estado unido del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="3e523-143">El comando anterior solo debe ejecutarse una vez en un contexto administrativo en el dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="3e523-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="3e523-144">Unión a AD híbrida\Nuevo registro</span><span class="sxs-lookup"><span data-stu-id="3e523-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="3e523-145">El dispositivo se une automáticamente a Azure AD sin intervención del usuario ni del administrador, siempre y cuando el dispositivo tenga conectividad de red con puntos de conexión globales de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e523-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="3e523-146">Unión a Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e523-146">Azure AD Join</span></span>

<span data-ttu-id="3e523-147">**IMPORTANTE:** La entidad de servicio de Intune se habilitará después de la migración comercial, lo que implica la activación del registro de dispositivos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e523-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="3e523-148">Si bloqueó el registro de dispositivos de Azure AD antes de la migración, debe deshabilitar la entidad de servicio de Intune con PowerShell para deshabilitar de nuevo el registro de dispositivos de Azure AD con el portal de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e523-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="3e523-149">Puede deshabilitar la entidad de servicio de Intune con este comando en el módulo Azure Active Directory PowerShell para Graph.</span><span class="sxs-lookup"><span data-stu-id="3e523-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="3e523-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="3e523-150">Unjoin</span></span>

<span data-ttu-id="3e523-151">Para determinar si el dispositivo Windows 10 se unió previamente a Azure AD, el usuario o administrador puede ejecutar el siguiente comando en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3e523-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="3e523-152">Si el dispositivo está unido a Azure AD, el usuario o administrador vería el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="3e523-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="3e523-153">Si el resultado es "AzureAdJoined : NO", ignore las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="3e523-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="3e523-154">Usuario: si el dispositivo está unido a Azure AD, un usuario puede unirse al dispositivo desde la configuración.</span><span class="sxs-lookup"><span data-stu-id="3e523-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="3e523-155">Compruebe que hay una cuenta de administrador local en el dispositivo antes de deshacer el dispositivo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e523-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="3e523-156">La cuenta de administrador local es necesaria para volver a iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="3e523-157">Administrador: si el administrador de la organización quiere unirse a los dispositivos de los usuarios unidos a Azure AD, puede hacerlo ejecutando el siguiente comando en cada uno de los dispositivos mediante un mecanismo como la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="3e523-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="3e523-158">El administrador debe comprobar que hay una cuenta de administrador local en el dispositivo antes de deshacer el dispositivo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e523-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="3e523-159">La cuenta de administrador local es necesaria para volver a iniciar sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="3e523-160">El comando anterior solo debe ejecutarse una vez en un contexto administrativo en el dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="3e523-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="3e523-161">Unirse o volver a registrarse de Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e523-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="3e523-162">El usuario puede unir el dispositivo a Azure AD desde la configuración de Windows: Configuración > Cuentas > **Access Work Or School > Connect**.</span><span class="sxs-lookup"><span data-stu-id="3e523-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="3e523-163">Azure AD Registrado (propiedad de la compañía)</span><span class="sxs-lookup"><span data-stu-id="3e523-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="3e523-164">Para determinar si el dispositivo Windows 10 está registrado en Azure AD, ejecute el siguiente comando en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3e523-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="3e523-165">Si el dispositivo está registrado en Azure AD, verá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="3e523-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="3e523-166">Para quitar la cuenta registrada de Azure AD existente en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3e523-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="3e523-167">Para quitar la cuenta registrada de Azure AD en el dispositivo, use CleanupWPJ, una herramienta que puede descargar desde aquí: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="3e523-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="3e523-168">Extraiga el archivo ZIP y ejecute **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="3e523-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="3e523-169">Esta herramienta iniciará el archivo ejecutable correcto en función de la versión de Windows en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="3e523-170">Mediante un mecanismo como la directiva de grupo, el administrador puede ejecutar el comando en el dispositivo en el contexto de cualquier usuario que haya iniciado sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="3e523-171">Para deshabilitar los mensajes del Administrador de cuentas web para registrar el dispositivo en Azure AD, agregue este valor del Registro:</span><span class="sxs-lookup"><span data-stu-id="3e523-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="3e523-172">Ubicación: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="3e523-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="3e523-173">Tipo: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="3e523-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="3e523-174">Nombre: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="3e523-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="3e523-175">Datos de valor: 1</span><span class="sxs-lookup"><span data-stu-id="3e523-175">Value data: 1</span></span>

<span data-ttu-id="3e523-176">La presencia de este valor del Registro debe bloquear la unión al lugar de trabajo e impedir que los usuarios vean mensajes para unirse al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="3e523-177">Android</span><span class="sxs-lookup"><span data-stu-id="3e523-177">Android</span></span>

<span data-ttu-id="3e523-178">Para Android, los usuarios tendrán que anular el registro y volver a registrar sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3e523-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="3e523-179">Esto se puede hacer a través de la aplicación Microsoft Authenticator o la aplicación Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="3e523-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="3e523-180">Desde la aplicación Microsoft Authenticator, los usuarios pueden ir **a Configuración > Registro de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="3e523-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="3e523-181">Desde allí, los usuarios pueden anular el registro y volver a registrar su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="3e523-182">Desde el Portal de empresa, los usuarios pueden ir a **la pestaña Dispositivos** y quitar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="3e523-183">Después, vuelva a inscribir el dispositivo mediante el Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="3e523-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="3e523-184">Los usuarios también pueden anular el registro y volver a registrarse quitando la cuenta de la página de configuración de la cuenta y, a continuación, agregando de nuevo la cuenta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3e523-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="3e523-185">Para anular el registro y volver a registrar el dispositivo en Android mediante la aplicación Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="3e523-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="3e523-186">Abre la aplicación Microsoft Authenticator y ve a **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="3e523-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="3e523-187">Seleccione **Registro de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="3e523-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="3e523-188">Anula el registro del dispositivo **seleccionando Anular registro**.</span><span class="sxs-lookup"><span data-stu-id="3e523-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="3e523-189">Para **registro de dispositivos,** vuelva a registrar el dispositivo escribiendo la dirección de correo electrónico y, a continuación, **seleccione Registrar**.</span><span class="sxs-lookup"><span data-stu-id="3e523-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="3e523-190">Para anular el registro y volver a registrar un dispositivo Android con la página Configuración de Android:</span><span class="sxs-lookup"><span data-stu-id="3e523-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="3e523-191">Abra **Configuración del dispositivo** y vaya a **Cuentas**.</span><span class="sxs-lookup"><span data-stu-id="3e523-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="3e523-192">Seleccione la cuenta de trabajo que desea volver a registrar y seleccione **Quitar cuenta**.</span><span class="sxs-lookup"><span data-stu-id="3e523-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="3e523-193">Después de quitar la cuenta, en la **página Cuentas,** seleccione **Agregar cuenta > cuenta de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="3e523-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="3e523-194">En **Workplace Join**, escriba su dirección de correo electrónico y seleccione **Unirse** para completar el registro del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="3e523-195">Para anular el registro y volver a registrar el dispositivo en Android desde el Portal de empresa:</span><span class="sxs-lookup"><span data-stu-id="3e523-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="3e523-196">Inicie Portal de empresa y vaya a **la pestaña Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="3e523-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="3e523-197">Selecciona el dispositivo para ver los detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="3e523-198">En el menú puntos suspensivos (tres puntos), selecciona **Quitar** dispositivo y completa la eliminación confirmando en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3e523-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="3e523-199">Ahora debes haber cerrado sesión en la aplicación Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="3e523-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="3e523-200">Selecciona **Iniciar sesión** para volver a registrar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="3e523-201">Para obtener más información sobre las acciones necesarias durante la fase de migración de esta carga de trabajo, o el impacto en la administración o el uso, revise la información sobre Azure Active Directory (Azure AD) en Información adicional de Azure AD para la migración desde [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="3e523-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="3e523-202">iOS</span><span class="sxs-lookup"><span data-stu-id="3e523-202">iOS</span></span>

<span data-ttu-id="3e523-203">En dispositivos iOS, un usuario tendrá que quitar manualmente las cuentas almacenadas en caché de Microsoft Authenticator, anular el registro del dispositivo y cerrar sesión de cualquier aplicación nativa del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e523-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="3e523-204">Paso 1: Si está presente, quite la cuenta de la aplicación Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="3e523-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="3e523-205">Pulsa la cuenta en la aplicación Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="3e523-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="3e523-206">Pulsa el **icono Configuración** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="3e523-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="3e523-207">Si no ve el icono **Configuración,** es posible que no esté usando la versión más reciente de Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="3e523-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="3e523-208">Pulsa el **botón Quitar cuenta.**</span><span class="sxs-lookup"><span data-stu-id="3e523-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="3e523-209">Pulsa **Todas las aplicaciones en este dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="3e523-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="3e523-210">Paso 2: Anular el registro del dispositivo desde la aplicación Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="3e523-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="3e523-211">Pulsa el icono del menú en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="3e523-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="3e523-212">Pulsa **Configuración** y, a continuación, **Registro de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="3e523-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="3e523-213">Si se muestra tu cuenta, pulsa **Anular registro del dispositivo** y **Continuar** en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3e523-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="3e523-214">No debería ver ninguna cuenta después de eso.</span><span class="sxs-lookup"><span data-stu-id="3e523-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="3e523-215">Paso 3: Cerrar sesión de aplicaciones individuales si es necesario</span><span class="sxs-lookup"><span data-stu-id="3e523-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="3e523-216">Los usuarios pueden ir a aplicaciones individuales como Outlook, Teams y OneDrive y quitar cuentas de esas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3e523-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="3e523-217">Más información</span><span class="sxs-lookup"><span data-stu-id="3e523-217">More information</span></span>

<span data-ttu-id="3e523-218">Introducción:</span><span class="sxs-lookup"><span data-stu-id="3e523-218">Getting started:</span></span>

- [<span data-ttu-id="3e523-219">Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán</span><span class="sxs-lookup"><span data-stu-id="3e523-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="3e523-220">Asistencia para la migración a Microsoft Cloud Alemania</span><span class="sxs-lookup"><span data-stu-id="3e523-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="3e523-221">Cómo participar en la migración</span><span class="sxs-lookup"><span data-stu-id="3e523-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="3e523-222">Experiencia del cliente durante la migración</span><span class="sxs-lookup"><span data-stu-id="3e523-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="3e523-223">Pasar a través de la transición:</span><span class="sxs-lookup"><span data-stu-id="3e523-223">Moving through the transition:</span></span>

- [<span data-ttu-id="3e523-224">Impactos y acciones de las fases de migración</span><span class="sxs-lookup"><span data-stu-id="3e523-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="3e523-225">Pre-work adicional</span><span class="sxs-lookup"><span data-stu-id="3e523-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="3e523-226">Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="3e523-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="3e523-227">Aplicaciones en la nube:</span><span class="sxs-lookup"><span data-stu-id="3e523-227">Cloud apps:</span></span>

- [<span data-ttu-id="3e523-228">Información del programa de migración de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3e523-228">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="3e523-229">Información del programa de migración de Power BI</span><span class="sxs-lookup"><span data-stu-id="3e523-229">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="3e523-230">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e523-230">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)