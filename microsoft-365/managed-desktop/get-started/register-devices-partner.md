---
title: Pasos para que los Socios puedan registrar dispositivos
description: Cómo pueden los socios registrar los dispositivos para que puedan ser administrados por el escritorio administrado por Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a9a2a0ccb1e0830d674f4b1b1ef5495fafb38ca3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596557"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="3682b-103">Pasos para que los Socios puedan registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="3682b-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="3682b-104">En este tema se describen los pasos que deben seguir los socios para registrar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3682b-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="3682b-105">El proceso para registrar los dispositivos usted mismo está documentado en [registrar los dispositivos en el escritorio administrado por Microsoft](register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="3682b-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="3682b-106">Preparar el registro</span><span class="sxs-lookup"><span data-stu-id="3682b-106">Prepare for registration</span></span> 
<span data-ttu-id="3682b-107">Antes de completar el registro de un cliente, primero debe establecer una relación con ellos en el [centro de Partners](https://partner.microsoft.com/dashboard).</span><span class="sxs-lookup"><span data-stu-id="3682b-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="3682b-108">Asegúrese de seleccionar **incluir privilegios de administración delegados para Azure Active Directory y Office 365**.</span><span class="sxs-lookup"><span data-stu-id="3682b-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="3682b-109">Para obtener más información, vea [ayuda del centro de asociados](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span><span class="sxs-lookup"><span data-stu-id="3682b-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="3682b-110">Para completar el registro del cliente, cree primero un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="3682b-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="3682b-111">Para su comodidad, puede descargar un [archivo CSV de ejemplo](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv) para esta *versión del asociado*.</span><span class="sxs-lookup"><span data-stu-id="3682b-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv) for this *Partner version*.</span></span>

<span data-ttu-id="3682b-112">El archivo tiene que incluir **exactamente los mismos encabezados de columna** que el ejemplo uno (fabricante, modelo, etc.), pero sus propios datos para las otras filas.</span><span class="sxs-lookup"><span data-stu-id="3682b-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="3682b-113">Si usa la plantilla, ábrala en una herramienta de edición de texto como el Bloc de notas y considere la posibilidad de dejar sólo todos los datos de la fila 1, introduciendo solo los datos en las filas 2 y anteriores.</span><span class="sxs-lookup"><span data-stu-id="3682b-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="3682b-114">Este formato es solo para el proceso asociado.</span><span class="sxs-lookup"><span data-stu-id="3682b-114">This format is only for the Partner process.</span></span> <span data-ttu-id="3682b-115">El proceso de registro automático está documentado en los [dispositivos de registro del escritorio administrado por Microsoft](register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="3682b-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="3682b-116">Estos valores deben coincidir exactamente con los valores de fabricante de SMBIOS, incluidos el carácter de mayúsculas y caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="3682b-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="3682b-117">Fabricante del dispositivo (ejemplo: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="3682b-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="3682b-118">Modelo de dispositivo (ejemplo: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="3682b-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="3682b-119">Número de serie del dispositivo</span><span class="sxs-lookup"><span data-stu-id="3682b-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="3682b-120">Registrar dispositivos con Azure portal</span><span class="sxs-lookup"><span data-stu-id="3682b-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="3682b-121">El registro mediante el portal de Azure es el mismo que para el autoservicio, excepto que se obtiene acceso al portal de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="3682b-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="3682b-122">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3682b-122">Follow these steps:</span></span>

1. <span data-ttu-id="3682b-123">Ir al [centro de asociados](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="3682b-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="3682b-124">Seleccione **clientes**.</span><span class="sxs-lookup"><span data-stu-id="3682b-124">Select **Customers**.</span></span>
3. <span data-ttu-id="3682b-125">Seleccione el cliente que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="3682b-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="3682b-126">Seleccione **Administración del servicio**.</span><span class="sxs-lookup"><span data-stu-id="3682b-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="3682b-127">Seleccione **Intune**.</span><span class="sxs-lookup"><span data-stu-id="3682b-127">Select **Intune**.</span></span>
6. <span data-ttu-id="3682b-128">Busque "MMD" en el cuadro de búsqueda superior de Azure portal.</span><span class="sxs-lookup"><span data-stu-id="3682b-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="3682b-129">Seleccione **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="3682b-129">Select **Devices**.</span></span>
8. <span data-ttu-id="3682b-130">En **carga de archivos**, especifique una ruta de acceso al archivo CSV que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3682b-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="3682b-131">Opcionalmente, puede Agregar un identificador de **pedido** o un **identificador de compra** para sus propios fines de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3682b-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="3682b-132">No hay ningún requisito de formato para estos valores.</span><span class="sxs-lookup"><span data-stu-id="3682b-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="3682b-133">Seleccione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="3682b-133">Select **Register devices**.</span></span> <span data-ttu-id="3682b-134">El sistema agregará los dispositivos a la lista de dispositivos en la **hoja dispositivos**, marcada como **pendiente de registro**.</span><span class="sxs-lookup"><span data-stu-id="3682b-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="3682b-135">El registro suele tardar menos de 10 minutos y, cuando se ejecuta correctamente, el dispositivo se muestra como **listo para el usuario** significa que está listo y esperando a que un usuario final empiece a usar.</span><span class="sxs-lookup"><span data-stu-id="3682b-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="3682b-136">Puede supervisar el progreso del registro de dispositivos en la Página principal de **Microsoft administrada para equipos de escritorio** .</span><span class="sxs-lookup"><span data-stu-id="3682b-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="3682b-137">Los posibles Estados que se notifican incluyen:</span><span class="sxs-lookup"><span data-stu-id="3682b-137">Possible states reported there include:</span></span>

| <span data-ttu-id="3682b-138">Estado</span><span class="sxs-lookup"><span data-stu-id="3682b-138">State</span></span> | <span data-ttu-id="3682b-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="3682b-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="3682b-140">Registro pendiente</span><span class="sxs-lookup"><span data-stu-id="3682b-140">Registration pending</span></span> | <span data-ttu-id="3682b-141">Aún no se ha realizado el registro.</span><span class="sxs-lookup"><span data-stu-id="3682b-141">Registration is not done yet.</span></span> <span data-ttu-id="3682b-142">Vuelva a comprobarla más tarde.</span><span class="sxs-lookup"><span data-stu-id="3682b-142">Check back later.</span></span> |
| <span data-ttu-id="3682b-143">Error en el registro</span><span class="sxs-lookup"><span data-stu-id="3682b-143">Registration failed</span></span> | <span data-ttu-id="3682b-144">No se pudo completar el registro.</span><span class="sxs-lookup"><span data-stu-id="3682b-144">Registration could not be completed.</span></span> <span data-ttu-id="3682b-145">Consulte [solución de problemas del registro de dispositivos](register-devices-self.md#troubleshooting-device-registration) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3682b-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="3682b-146">Listo para el usuario</span><span class="sxs-lookup"><span data-stu-id="3682b-146">Ready for user</span></span> | <span data-ttu-id="3682b-147">El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario final.</span><span class="sxs-lookup"><span data-stu-id="3682b-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="3682b-148">El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional.</span><span class="sxs-lookup"><span data-stu-id="3682b-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="3682b-149">Activo</span><span class="sxs-lookup"><span data-stu-id="3682b-149">Active</span></span> | <span data-ttu-id="3682b-150">El dispositivo se entregó al usuario final y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="3682b-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="3682b-151">Esto también indica que los usuarios usan el dispositivo con regularidad.</span><span class="sxs-lookup"><span data-stu-id="3682b-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="3682b-152">Inactivo</span><span class="sxs-lookup"><span data-stu-id="3682b-152">Inactive</span></span> | <span data-ttu-id="3682b-153">El dispositivo se entregó al usuario final y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="3682b-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="3682b-154">Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).</span><span class="sxs-lookup"><span data-stu-id="3682b-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="3682b-155">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="3682b-155">Troubleshooting</span></span>

| <span data-ttu-id="3682b-156">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="3682b-156">Error message</span></span> | <span data-ttu-id="3682b-157">Detalles</span><span class="sxs-lookup"><span data-stu-id="3682b-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="3682b-158">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="3682b-158">Device not found</span></span> | <span data-ttu-id="3682b-159">No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="3682b-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="3682b-160">Confirma estos valores con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3682b-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="3682b-161">Hash de hardware no válido</span><span class="sxs-lookup"><span data-stu-id="3682b-161">Hardware hash not valid</span></span> | <span data-ttu-id="3682b-162">El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="3682b-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="3682b-163">Compruebe el hash de hardware y vuelva a enviarlo.</span><span class="sxs-lookup"><span data-stu-id="3682b-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="3682b-164">El dispositivo ya está registrado</span><span class="sxs-lookup"><span data-stu-id="3682b-164">Device already registered</span></span> | <span data-ttu-id="3682b-165">Este dispositivo ya está registrado en su organización.</span><span class="sxs-lookup"><span data-stu-id="3682b-165">This device is already registered to your organization.</span></span> <span data-ttu-id="3682b-166">No se requiere ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="3682b-166">No further action required.</span></span> |
| <span data-ttu-id="3682b-167">Dispositivo reclamado por otra organización</span><span class="sxs-lookup"><span data-stu-id="3682b-167">Device claimed by another organization</span></span> | <span data-ttu-id="3682b-168">Este dispositivo ya ha sido reclamado por otra organización.</span><span class="sxs-lookup"><span data-stu-id="3682b-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="3682b-169">Consulta con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3682b-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="3682b-170">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="3682b-170">Unexpected error</span></span> | <span data-ttu-id="3682b-171">La solicitud no se pudo procesar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3682b-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="3682b-172">Póngase en contacto<support link>con el soporte técnico () y proporcione el identificador de solicitud:<requestId></span><span class="sxs-lookup"><span data-stu-id="3682b-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
