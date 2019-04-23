---
title: Registrar los dispositivos en el escritorio administrado de Microsoft personalmente
description: Registrar los dispositivos usted mismo para que el escritorio administrado de Microsoft pueda administrarlos
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 217418cfce66baa02b30ae7d8a01b938a1f2366e
ms.sourcegitcommit: 7af6350fb5a6d37934c1b6bfdc38acd09b2d5d86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988436"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="76b26-103">Registrar dispositivos en el escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="76b26-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="76b26-104">En este tema se describen los pasos para registrar los dispositivos por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="76b26-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="76b26-105">El proceso para socios está documentado en [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="76b26-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="76b26-106">Microsoft manAged Desktop puede trabajar con dispositivos nuevos o puede volver a usar dispositivos que ya tiene (lo que requerirá que vuelva a crear imágenes).</span><span class="sxs-lookup"><span data-stu-id="76b26-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="76b26-107">Puede registrar dispositivos con Microsoft manAged Desktop en el portal de Azure o ganar flexibilidad usando una API.</span><span class="sxs-lookup"><span data-stu-id="76b26-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="76b26-108">Preparar el registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="76b26-108">Prepare to register devices</span></span>

<span data-ttu-id="76b26-109">Si todavía no obtuvo los dispositivos que desea usar, compruebe los [dispositivos de escritorio administrados por Microsoft](../service-description/device-list.md) y trabaje con un partner de dispositivos para obtener los dispositivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="76b26-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="76b26-110">Si está trabajando con dispositivos completamente nuevos o vuelve a usar los existentes, para registrarlos con el escritorio administrado de Microsoft, deberá preparar un **archivo delimitado por comas (CSV)**.</span><span class="sxs-lookup"><span data-stu-id="76b26-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="76b26-111">Este archivo debe incluir la siguiente información para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="76b26-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="76b26-112">Este formato es solo para el registro de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="76b26-112">This format is for self-service registration only.</span></span> <span data-ttu-id="76b26-113">El formato que usan los asociados se documenta en [registrar dispositivos en escritorio administrado de Microsoft para partners](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="76b26-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="76b26-114">Estos valores se usan con fines de presentación y no es necesario que coincidan exactamente con las propiedades del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76b26-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="76b26-115">Fabricante del dispositivo (ejemplo: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="76b26-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="76b26-116">Modelo de dispositivo (ejemplo: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="76b26-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="76b26-117">Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="76b26-117">Device serial number</span></span>

<span data-ttu-id="76b26-118">El hash de hardware debe ser una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="76b26-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="76b26-119">Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="76b26-119">Hardware hash</span></span>

<span data-ttu-id="76b26-120">Para obtener el hash de hardware, puede solicitar ayuda a su OEM o Partner, o bien siga estos pasos para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="76b26-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="76b26-121">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="76b26-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="76b26-122">Realizar`Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="76b26-122">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="76b26-123">Realizar`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="76b26-123">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="76b26-124">Como alternativa, puede seguir estos pasos en un dispositivo nuevo (antes de pasar por la OOBE por primera vez):</span><span class="sxs-lookup"><span data-stu-id="76b26-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="76b26-125">En otro dispositivo, inserte una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="76b26-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="76b26-126">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="76b26-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="76b26-127">Realizar`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="76b26-127">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="76b26-128">Encienda el dispositivo de destino, pero no inicie la instalación.</span><span class="sxs-lookup"><span data-stu-id="76b26-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="76b26-129">Si inicia de forma accidental la experiencia del programa de instalación, tendrá que restablecer o volver a crear una imagen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76b26-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="76b26-130">Inserte la unidad USB y, a continuación, presione Mayús + F10.</span><span class="sxs-lookup"><span data-stu-id="76b26-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="76b26-131">Abra un símbolo del sistema de PowerShell con derechos administrativos y `cd <pathToUsb>`, a continuación, ejecute.</span><span class="sxs-lookup"><span data-stu-id="76b26-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="76b26-132">Realizar`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="76b26-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="76b26-133">Realizar`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="76b26-133">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="76b26-134">Quite la unidad USB y, a continuación, apague el dispositivo ejecutando`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="76b26-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="76b26-135">No vuelva a encender el dispositivo de destino hasta que haya completado el registro para él.</span><span class="sxs-lookup"><span data-stu-id="76b26-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="76b26-136">Para su comodidad, puede descargar una [plantilla](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) para este archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="76b26-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/live/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) for this CSV file.</span></span>

<span data-ttu-id="76b26-137">El archivo tiene que incluir **exactamente los mismos encabezados de columna** que el ejemplo uno (fabricante, modelo, etc.), pero sus propios datos para las otras filas.</span><span class="sxs-lookup"><span data-stu-id="76b26-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="76b26-138">Si usa la plantilla, ábrala en una herramienta de edición de texto como el Bloc de notas y considere la posibilidad de dejar sólo todos los datos de la fila 1, introduciendo solo los datos en las filas 2 y anteriores.</span><span class="sxs-lookup"><span data-stu-id="76b26-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="76b26-139">Si olvida cambiar alguno de los datos de muestra, se producirá un error en el registro.</span><span class="sxs-lookup"><span data-stu-id="76b26-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="76b26-140">Registrar dispositivos con Azure portal</span><span class="sxs-lookup"><span data-stu-id="76b26-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="76b26-141">En el portal de Microsoft manAged Desktop [Azure](https://aka.ms/mmdportal), seleccione **dispositivos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="76b26-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="76b26-142">Seleccione **+ registrar dispositivos**; se abre el repaso:</span><span class="sxs-lookup"><span data-stu-id="76b26-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="76b26-143">[![Volar después de seleccionar dispositivos de registro](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="76b26-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Por desGracia, esto no es cierto. Podemos quitar esta nota, pero dejarla ahora hasta que podamos conversar sobre ella.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="76b26-145">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="76b26-145">Follow these steps:</span></span>

1. <span data-ttu-id="76b26-146">En **carga de archivos**, especifique una ruta de acceso al archivo CSV que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="76b26-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="76b26-147">Opcionalmente, puede Agregar un identificador de **pedido** o un **identificador de compra** para sus propios fines de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="76b26-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="76b26-148">No hay ningún requisito de formato para estos valores.</span><span class="sxs-lookup"><span data-stu-id="76b26-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="76b26-149">Seleccione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="76b26-149">Select **Register devices**.</span></span> <span data-ttu-id="76b26-150">El sistema agregará los dispositivos a la lista de dispositivos en la **hoja dispositivos**, marcada como **pendiente de registro**.</span><span class="sxs-lookup"><span data-stu-id="76b26-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="76b26-151">El registro suele tardar menos de 10 minutos y, cuando se ejecuta correctamente, el dispositivo se muestra como **listo para el usuario** significa que está listo y esperando a que un usuario final empiece a usar.</span><span class="sxs-lookup"><span data-stu-id="76b26-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="76b26-152">Puede supervisar el progreso del registro de dispositivos en la Página principal de **Microsoft administrada para equipos de escritorio** .</span><span class="sxs-lookup"><span data-stu-id="76b26-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="76b26-153">Los posibles Estados que se notifican incluyen:</span><span class="sxs-lookup"><span data-stu-id="76b26-153">Possible states reported there include:</span></span>

| <span data-ttu-id="76b26-154">Estado</span><span class="sxs-lookup"><span data-stu-id="76b26-154">State</span></span> | <span data-ttu-id="76b26-155">Description</span><span class="sxs-lookup"><span data-stu-id="76b26-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="76b26-156">Registro pendiente</span><span class="sxs-lookup"><span data-stu-id="76b26-156">Registration pending</span></span> | <span data-ttu-id="76b26-157">Aún no se ha realizado el registro.</span><span class="sxs-lookup"><span data-stu-id="76b26-157">Registration is not done yet.</span></span> <span data-ttu-id="76b26-158">Vuelva a comProbarla más tarde.</span><span class="sxs-lookup"><span data-stu-id="76b26-158">Check back later.</span></span> |
| <span data-ttu-id="76b26-159">Error en el registro</span><span class="sxs-lookup"><span data-stu-id="76b26-159">Registration failed</span></span> | <span data-ttu-id="76b26-160">No se pudo completar el registro.</span><span class="sxs-lookup"><span data-stu-id="76b26-160">Registration could not be completed.</span></span> <span data-ttu-id="76b26-161">Consulte [solución de problemas](register-devices-self.md#troubleshooting) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="76b26-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="76b26-162">Listo para el usuario</span><span class="sxs-lookup"><span data-stu-id="76b26-162">Ready for user</span></span> | <span data-ttu-id="76b26-163">El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario final.</span><span class="sxs-lookup"><span data-stu-id="76b26-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="76b26-164">El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional.</span><span class="sxs-lookup"><span data-stu-id="76b26-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="76b26-165">Active</span><span class="sxs-lookup"><span data-stu-id="76b26-165">Active</span></span> | <span data-ttu-id="76b26-166">El dispositivo se entregó al usuario final y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="76b26-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="76b26-167">Esto también indica que los usuarios usan el dispositivo con regularidad.</span><span class="sxs-lookup"><span data-stu-id="76b26-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="76b26-168">Inactivo</span><span class="sxs-lookup"><span data-stu-id="76b26-168">Inactive</span></span> | <span data-ttu-id="76b26-169">El dispositivo se entregó al usuario final y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="76b26-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="76b26-170">Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).</span><span class="sxs-lookup"><span data-stu-id="76b26-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="76b26-171">Registrar dispositivos con una API</span><span class="sxs-lookup"><span data-stu-id="76b26-171">Register devices by using an API</span></span>

<span data-ttu-id="76b26-172">Hay disponible una API de REST para permitir una mayor flexibilidad y repetibilidad con registros de dispositivos independientes y frecuentes.</span><span class="sxs-lookup"><span data-stu-id="76b26-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="76b26-173">Actualmente, para usar la API, pida ayuda al contacto de Microsoft para unirse a una versión preliminar de esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="76b26-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="76b26-174">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="76b26-174">Troubleshooting</span></span>

| <span data-ttu-id="76b26-175">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="76b26-175">Error message</span></span> | <span data-ttu-id="76b26-176">Detalles</span><span class="sxs-lookup"><span data-stu-id="76b26-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="76b26-177">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="76b26-177">Device not found</span></span> | <span data-ttu-id="76b26-178">No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="76b26-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="76b26-179">Confirma estos valores con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76b26-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="76b26-180">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="76b26-180">Device not found</span></span> | <span data-ttu-id="76b26-181">No pudimos anular el registro de este dispositivo porque no existe en la organización.</span><span class="sxs-lookup"><span data-stu-id="76b26-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="76b26-182">No se requiere ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="76b26-182">No further action required.</span></span> |
| <span data-ttu-id="76b26-183">Hash de hardware no válido</span><span class="sxs-lookup"><span data-stu-id="76b26-183">Hardware hash not valid</span></span> | <span data-ttu-id="76b26-184">El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="76b26-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="76b26-185">Compruebe el hash de hardware y vuelva a enviarlo.</span><span class="sxs-lookup"><span data-stu-id="76b26-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="76b26-186">El dispositivo ya está registrado</span><span class="sxs-lookup"><span data-stu-id="76b26-186">Device already registered</span></span> | <span data-ttu-id="76b26-187">Este dispositivo ya está registrado en su organización.</span><span class="sxs-lookup"><span data-stu-id="76b26-187">This device is already registered to your organization.</span></span> <span data-ttu-id="76b26-188">No se requiere ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="76b26-188">No further action required.</span></span> |
| <span data-ttu-id="76b26-189">Dispositivo reclamado por otra organización</span><span class="sxs-lookup"><span data-stu-id="76b26-189">Device claimed by another organization</span></span> | <span data-ttu-id="76b26-190">Este dispositivo ya ha sido reclamado por otra organización.</span><span class="sxs-lookup"><span data-stu-id="76b26-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="76b26-191">Consulta con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76b26-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="76b26-192">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="76b26-192">Unexpected error</span></span> | <span data-ttu-id="76b26-193">La solicitud no se pudo procesar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="76b26-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="76b26-194">Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud:<requestId></span><span class="sxs-lookup"><span data-stu-id="76b26-194">Contact Support and provide the Request ID: <requestId></span></span> |




