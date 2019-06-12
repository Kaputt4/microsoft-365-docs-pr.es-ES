---
title: Registrar los dispositivos en el escritorio administrado de Microsoft personalmente
description: Registrar los dispositivos usted mismo para que el escritorio administrado de Microsoft pueda administrarlos
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1e61cfc7fd1d6d597efbfa2480155e06a3d3eb7
ms.sourcegitcommit: d6fcd57a0689abbe4ab47489034f52e327f4e5f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857303"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="97068-103">Registrar dispositivos en el escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="97068-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="97068-104">En este tema se describen los pasos para registrar los dispositivos por su cuenta.</span><span class="sxs-lookup"><span data-stu-id="97068-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="97068-105">El proceso para socios está documentado en [Register Devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="97068-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="97068-106">Microsoft Managed Desktop puede trabajar con dispositivos nuevos o puede volver a usar dispositivos que ya tiene (lo que requerirá que vuelva a crear imágenes).</span><span class="sxs-lookup"><span data-stu-id="97068-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="97068-107">Puede registrar dispositivos con Microsoft Managed Desktop en el portal de Azure o ganar flexibilidad usando una API.</span><span class="sxs-lookup"><span data-stu-id="97068-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="97068-108">Preparar el registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="97068-108">Prepare to register devices</span></span>

<span data-ttu-id="97068-109">Si todavía no obtuvo los dispositivos que desea usar, compruebe los [dispositivos de escritorio administrados por Microsoft](../service-description/device-list.md) y trabaje con un partner de dispositivos para obtener los dispositivos compatibles.</span><span class="sxs-lookup"><span data-stu-id="97068-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="97068-110">Si está trabajando con dispositivos completamente nuevos o vuelve a usar los existentes, para registrarlos con el escritorio administrado de Microsoft, deberá preparar un **archivo delimitado por comas (CSV)**.</span><span class="sxs-lookup"><span data-stu-id="97068-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="97068-111">Este archivo debe incluir la siguiente información para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="97068-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="97068-112">Este formato es solo para el registro de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="97068-112">This format is for self-service registration only.</span></span> <span data-ttu-id="97068-113">El formato que usan los asociados se documenta en [registrar dispositivos en escritorio administrado de Microsoft para partners](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="97068-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="97068-114">Estos valores se usan con fines de presentación y no es necesario que coincidan exactamente con las propiedades del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97068-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="97068-115">Fabricante del dispositivo (ejemplo: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="97068-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="97068-116">Modelo de dispositivo (ejemplo: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="97068-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="97068-117">Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="97068-117">Device serial number</span></span>

<span data-ttu-id="97068-118">El hash de hardware debe ser una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="97068-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="97068-119">Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="97068-119">Hardware hash</span></span>

<span data-ttu-id="97068-120">Para obtener el hash de hardware, puede solicitar ayuda a su OEM o Partner, o bien siga estos pasos para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="97068-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="97068-121">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="97068-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="97068-122">Realizar`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="97068-122">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="97068-123">Realizar`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="97068-123">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="97068-124">Como alternativa, puede seguir estos pasos en un dispositivo nuevo (antes de pasar por la OOBE por primera vez):</span><span class="sxs-lookup"><span data-stu-id="97068-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="97068-125">En otro dispositivo, inserte una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="97068-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="97068-126">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="97068-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="97068-127">Realizar`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="97068-127">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="97068-128">Encienda el dispositivo de destino, pero no inicie la instalación.</span><span class="sxs-lookup"><span data-stu-id="97068-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="97068-129">Si inicia de forma accidental la experiencia del programa de instalación, tendrá que restablecer o volver a crear una imagen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97068-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="97068-130">Inserte la unidad USB y, a continuación, presione Mayús + F10.</span><span class="sxs-lookup"><span data-stu-id="97068-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="97068-131">Abra un símbolo del sistema de PowerShell con derechos administrativos y `cd <pathToUsb>`, a continuación, ejecute.</span><span class="sxs-lookup"><span data-stu-id="97068-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="97068-132">Realizar`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="97068-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="97068-133">Realizar`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="97068-133">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="97068-134">Quite la unidad USB y, a continuación, apague el dispositivo ejecutando`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="97068-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="97068-135">No vuelva a encender el dispositivo de destino hasta que haya completado el registro para él.</span><span class="sxs-lookup"><span data-stu-id="97068-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="97068-136">Para su comodidad, puede descargar una [plantilla](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) para este archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="97068-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="97068-137">El archivo tiene que incluir **exactamente los mismos encabezados de columna** que el ejemplo uno (fabricante, modelo, etc.), pero sus propios datos para las otras filas.</span><span class="sxs-lookup"><span data-stu-id="97068-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="97068-138">Si usa la plantilla, ábrala en una herramienta de edición de texto como el Bloc de notas y considere la posibilidad de dejar sólo todos los datos de la fila 1, introduciendo solo los datos en las filas 2 y anteriores.</span><span class="sxs-lookup"><span data-stu-id="97068-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="97068-139">Si olvida cambiar alguno de los datos de muestra, se producirá un error en el registro.</span><span class="sxs-lookup"><span data-stu-id="97068-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="97068-140">Registrar dispositivos con Azure portal</span><span class="sxs-lookup"><span data-stu-id="97068-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="97068-141">En el portal de Microsoft Managed Desktop [Azure](https://aka.ms/mmdportal), seleccione **dispositivos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="97068-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="97068-142">Seleccione **+ registrar dispositivos**; se abre el repaso:</span><span class="sxs-lookup"><span data-stu-id="97068-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="97068-143">[![Volar después de seleccionar dispositivos de registro](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="97068-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (Por desgracia, esto no es cierto. Podemos quitar esta nota, pero dejarla ahora hasta que podamos conversar sobre ella.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="97068-145">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="97068-145">Follow these steps:</span></span>

1. <span data-ttu-id="97068-146">En **carga de archivos**, especifique una ruta de acceso al archivo CSV que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="97068-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="97068-147">Opcionalmente, puede Agregar un identificador de **pedido** o un **identificador de compra** para sus propios fines de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="97068-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="97068-148">No hay ningún requisito de formato para estos valores.</span><span class="sxs-lookup"><span data-stu-id="97068-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="97068-149">Seleccione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="97068-149">Select **Register devices**.</span></span> <span data-ttu-id="97068-150">El sistema agregará los dispositivos a la lista de dispositivos en la **hoja dispositivos**, marcada como **pendiente de registro**.</span><span class="sxs-lookup"><span data-stu-id="97068-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="97068-151">El registro suele tardar menos de 10 minutos y, cuando se ejecuta correctamente, el dispositivo se muestra como **listo para el usuario** significa que está listo y esperando a que un usuario final empiece a usar.</span><span class="sxs-lookup"><span data-stu-id="97068-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="97068-152">Puede supervisar el progreso del registro de dispositivos en la Página principal de **Microsoft administrada para equipos de escritorio** .</span><span class="sxs-lookup"><span data-stu-id="97068-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="97068-153">Los posibles Estados que se notifican incluyen:</span><span class="sxs-lookup"><span data-stu-id="97068-153">Possible states reported there include:</span></span>

| <span data-ttu-id="97068-154">Estado</span><span class="sxs-lookup"><span data-stu-id="97068-154">State</span></span> | <span data-ttu-id="97068-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="97068-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="97068-156">Registro pendiente</span><span class="sxs-lookup"><span data-stu-id="97068-156">Registration pending</span></span> | <span data-ttu-id="97068-157">Aún no se ha realizado el registro.</span><span class="sxs-lookup"><span data-stu-id="97068-157">Registration is not done yet.</span></span> <span data-ttu-id="97068-158">Vuelva a comprobarla más tarde.</span><span class="sxs-lookup"><span data-stu-id="97068-158">Check back later.</span></span> |
| <span data-ttu-id="97068-159">Error en el registro</span><span class="sxs-lookup"><span data-stu-id="97068-159">Registration failed</span></span> | <span data-ttu-id="97068-160">No se pudo completar el registro.</span><span class="sxs-lookup"><span data-stu-id="97068-160">Registration could not be completed.</span></span> <span data-ttu-id="97068-161">Consulte [solución de problemas](register-devices-self.md#troubleshooting) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="97068-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="97068-162">Listo para el usuario</span><span class="sxs-lookup"><span data-stu-id="97068-162">Ready for user</span></span> | <span data-ttu-id="97068-163">El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario final.</span><span class="sxs-lookup"><span data-stu-id="97068-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="97068-164">El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional.</span><span class="sxs-lookup"><span data-stu-id="97068-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="97068-165">Activo</span><span class="sxs-lookup"><span data-stu-id="97068-165">Active</span></span> | <span data-ttu-id="97068-166">El dispositivo se entregó al usuario final y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="97068-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="97068-167">Esto también indica que los usuarios usan el dispositivo con regularidad.</span><span class="sxs-lookup"><span data-stu-id="97068-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="97068-168">Inactivo</span><span class="sxs-lookup"><span data-stu-id="97068-168">Inactive</span></span> | <span data-ttu-id="97068-169">El dispositivo se entregó al usuario final y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="97068-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="97068-170">Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).</span><span class="sxs-lookup"><span data-stu-id="97068-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="97068-171">Registrar dispositivos con una API</span><span class="sxs-lookup"><span data-stu-id="97068-171">Register devices by using an API</span></span>

<span data-ttu-id="97068-172">Hay disponible una API de REST para permitir una mayor flexibilidad y repetibilidad con registros de dispositivos independientes y frecuentes.</span><span class="sxs-lookup"><span data-stu-id="97068-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="97068-173">Actualmente, para usar la API, pida ayuda al contacto de Microsoft para unirse a una versión preliminar de esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="97068-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="97068-174">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="97068-174">Troubleshooting</span></span>

| <span data-ttu-id="97068-175">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="97068-175">Error message</span></span> | <span data-ttu-id="97068-176">Detalles</span><span class="sxs-lookup"><span data-stu-id="97068-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="97068-177">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="97068-177">Device not found</span></span> | <span data-ttu-id="97068-178">No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="97068-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="97068-179">Confirma estos valores con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97068-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="97068-180">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="97068-180">Device not found</span></span> | <span data-ttu-id="97068-181">No pudimos anular el registro de este dispositivo porque no existe en la organización.</span><span class="sxs-lookup"><span data-stu-id="97068-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="97068-182">No se requiere ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="97068-182">No further action required.</span></span> |
| <span data-ttu-id="97068-183">Hash de hardware no válido</span><span class="sxs-lookup"><span data-stu-id="97068-183">Hardware hash not valid</span></span> | <span data-ttu-id="97068-184">El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="97068-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="97068-185">Compruebe el hash de hardware y vuelva a enviarlo.</span><span class="sxs-lookup"><span data-stu-id="97068-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="97068-186">El dispositivo ya está registrado</span><span class="sxs-lookup"><span data-stu-id="97068-186">Device already registered</span></span> | <span data-ttu-id="97068-187">Este dispositivo ya está registrado en su organización.</span><span class="sxs-lookup"><span data-stu-id="97068-187">This device is already registered to your organization.</span></span> <span data-ttu-id="97068-188">No se requiere ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="97068-188">No further action required.</span></span> |
| <span data-ttu-id="97068-189">Dispositivo reclamado por otra organización</span><span class="sxs-lookup"><span data-stu-id="97068-189">Device claimed by another organization</span></span> | <span data-ttu-id="97068-190">Este dispositivo ya ha sido reclamado por otra organización.</span><span class="sxs-lookup"><span data-stu-id="97068-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="97068-191">Consulta con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97068-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="97068-192">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="97068-192">Unexpected error</span></span> | <span data-ttu-id="97068-193">La solicitud no se pudo procesar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="97068-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="97068-194">Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud:<requestId></span><span class="sxs-lookup"><span data-stu-id="97068-194">Contact Support and provide the Request ID: <requestId></span></span> |




