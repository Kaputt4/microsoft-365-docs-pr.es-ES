---
title: Registre dispositivos existentes usted mismo
description: Registrar los dispositivos reutilizados es posible que ya los pueda administrar el escritorio administrado de Microsoft.
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a971d8dc413e7794aa48c0b39cc0f42e511739ed
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250450"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="c7616-103">Registre dispositivos existentes usted mismo</span><span class="sxs-lookup"><span data-stu-id="c7616-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="c7616-104">En este tema se describen los pasos necesarios para volver a usar dispositivos que ya tiene y registrarlos en el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7616-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="c7616-105">Si está trabajando con dispositivos nuevos, siga los pasos descritos en [registrar los nuevos dispositivos en el escritorio administrado de Microsoft en](register-devices-self.md) su lugar.</span><span class="sxs-lookup"><span data-stu-id="c7616-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="c7616-106">El proceso para socios se documenta en [pasos para que los partners registren dispositivos](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="c7616-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="c7616-107">Microsoft Managed Desktop puede trabajar con dispositivos nuevos o puede volver a usar dispositivos que ya tiene (lo que requerirá que vuelva a crear imágenes).</span><span class="sxs-lookup"><span data-stu-id="c7616-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="c7616-108">Puede registrar dispositivos con Microsoft Managed Desktop en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="c7616-108">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="c7616-109">Preparar el registro de los dispositivos existentes</span><span class="sxs-lookup"><span data-stu-id="c7616-109">Prepare to register existing devices</span></span>


<span data-ttu-id="c7616-110">Para registrar los dispositivos existentes, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c7616-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="c7616-111">Obtenga el hash de hardware para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c7616-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="c7616-112">Combinar los datos hash</span><span class="sxs-lookup"><span data-stu-id="c7616-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="c7616-113">[Registre los dispositivos en el escritorio administrado por Microsoft](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="c7616-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="c7616-114">Compruebe que la imagen es correcta.</span><span class="sxs-lookup"><span data-stu-id="c7616-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="c7616-115">Entregar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="c7616-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="c7616-116">Obtener el hash de hardware</span><span class="sxs-lookup"><span data-stu-id="c7616-116">Obtain the hardware hash</span></span>

<span data-ttu-id="c7616-117">Microsoft Managed Desktop identifica cada dispositivo de manera única haciendo referencia a su hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="c7616-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="c7616-118">Tiene cuatro opciones para obtener esta información de los dispositivos que ya está usando:</span><span class="sxs-lookup"><span data-stu-id="c7616-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="c7616-119">Solicite al proveedor de OEM el archivo de registro de AutoPilot, que incluirá los hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="c7616-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="c7616-120">Cree un informe personalizado en el [Administrador de configuración](#configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="c7616-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="c7616-121">Ejecute un script de Windows PowerShell, ya sea mediante [Active](#active-directory-powershell-script-method) Directory o [manualmente](#manual-powershell-script-method) en cada dispositivo, y recopile los resultados en un archivo.</span><span class="sxs-lookup"><span data-stu-id="c7616-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="c7616-122">Inicie cada dispositivo, pero no complete la experiencia del programa de instalación de Windows y [reúna los valores hash en una unidad Flash extraíble](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="c7616-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="c7616-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c7616-123">Configuration Manager</span></span>

<span data-ttu-id="c7616-124">Puede usar el administrador de configuración de Microsoft Endpoint para recopilar los hash de hardware de los dispositivos existentes que desee registrar con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7616-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7616-125">Los dispositivos para los que quiera obtener esta información deben ejecutar Windows 10, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="c7616-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="c7616-126">También necesitará un dispositivo que sea un cliente de Configuration Manager conectado al sitio del administrador de configuración (rama actual).</span><span class="sxs-lookup"><span data-stu-id="c7616-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="c7616-127">También necesita el rol de sistema del sitio del punto de informe configurado en su entorno con SQL Server Reporting Services habilitado.</span><span class="sxs-lookup"><span data-stu-id="c7616-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="c7616-128">Si ha cumplido todos estos requisitos previos, estará listo para recopilar la información siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c7616-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="c7616-129">En la consola de Configuration Manager, seleccione **supervisión**.</span><span class="sxs-lookup"><span data-stu-id="c7616-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="c7616-130">En el área de trabajo supervisión, expanda **informes**y, a continuación, seleccione **informes**.</span><span class="sxs-lookup"><span data-stu-id="c7616-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="c7616-131">En la pestaña **Inicio** , en la sección **crear** , seleccione **crear informe** para abrir el asistente crear informe.</span><span class="sxs-lookup"><span data-stu-id="c7616-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="c7616-132">En la página de **información** , establezca estas opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="c7616-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="c7616-133">**Name:** Especifique un nombre para el informe.</span><span class="sxs-lookup"><span data-stu-id="c7616-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="c7616-134">**Descripción:** Especifique una descripción para el informe.</span><span class="sxs-lookup"><span data-stu-id="c7616-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="c7616-135">**Servidor:** Muestra el nombre del servidor de informes en el que se va a crear este informe.</span><span class="sxs-lookup"><span data-stu-id="c7616-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="c7616-136">**Ruta de acceso:** Seleccione **examinar** para especificar una carpeta en la que desea almacenar el informe.</span><span class="sxs-lookup"><span data-stu-id="c7616-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="c7616-137">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c7616-137">Select **Next**.</span></span> 
6. <span data-ttu-id="c7616-138">En la página **Resumen** , revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="c7616-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="c7616-139">Seleccione **anterior** para cambiar la configuración o seleccione **siguiente** para crear el informe en Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c7616-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="c7616-140">En la página **finalización** , seleccione **cerrar** para salir del asistente y abrir **Report Builder** para especificar la configuración del informe.</span><span class="sxs-lookup"><span data-stu-id="c7616-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="c7616-141">Escriba la cuenta de usuario y la contraseña si se le piden y, a continuación, seleccione **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="c7616-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="c7616-142">Si el generador de informes no está instalado en el dispositivo, se le pedirá que lo instale.</span><span class="sxs-lookup"><span data-stu-id="c7616-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="c7616-143">Seleccione **ejecutar para instalar Report Builder**, que es necesario para modificar y crear informes.</span><span class="sxs-lookup"><span data-stu-id="c7616-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="c7616-144">**En el generador de informes de Microsoft**, proporcione la instrucción SQL para el informe y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c7616-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="c7616-145">En el panel izquierdo, seleccione **conjuntos de valores**y, a continuación, haga clic con el botón secundario para **Agregar DataSet**.</span><span class="sxs-lookup"><span data-stu-id="c7616-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="c7616-146">Vaya a la pestaña **consulta** y, a continuación, escriba el nombre como *DataSet0*.</span><span class="sxs-lookup"><span data-stu-id="c7616-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="c7616-147">Seleccione **usar un conjunto de un objeto incrustado en el informe**; Se abrirá el generador de informes.</span><span class="sxs-lookup"><span data-stu-id="c7616-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="c7616-148">En el **generador de informes**, seleccione origen de **datos:**.</span><span class="sxs-lookup"><span data-stu-id="c7616-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="c7616-149">Seleccione el origen de datos predeterminado, que debe empezar por "AutoGen".</span><span class="sxs-lookup"><span data-stu-id="c7616-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="c7616-150">Elija **tipo de consulta como texto**y, a continuación, escriba esta consulta:</span><span class="sxs-lookup"><span data-stu-id="c7616-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="c7616-151">Desplácese a la pestaña **campo** , wehre valores para **el nombre de campo** y el origen de **campo** ya deben rellenarse.</span><span class="sxs-lookup"><span data-stu-id="c7616-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="c7616-152">Si no son, seleccione **Agregar**y, a continuación, seleccione **campo de consulta**.</span><span class="sxs-lookup"><span data-stu-id="c7616-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="c7616-153">Escriba el **nombre del campo** y el **origen del campo**.</span><span class="sxs-lookup"><span data-stu-id="c7616-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="c7616-154">Repita este procedimiento para cada uno de estos valores:</span><span class="sxs-lookup"><span data-stu-id="c7616-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="c7616-155">Manufacturer</span><span class="sxs-lookup"><span data-stu-id="c7616-155">Manufacturer</span></span> 
    - <span data-ttu-id="c7616-156">Model</span><span class="sxs-lookup"><span data-stu-id="c7616-156">Model</span></span> 
    - <span data-ttu-id="c7616-157">Serial_Number</span><span class="sxs-lookup"><span data-stu-id="c7616-157">Serial_Number</span></span> 
    - <span data-ttu-id="c7616-158">HardwareHash</span><span class="sxs-lookup"><span data-stu-id="c7616-158">HardwareHash</span></span>
7. <span data-ttu-id="c7616-159">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c7616-159">Select **OK**.</span></span>

<span data-ttu-id="c7616-160">A **continuación, defina la visualización del informe y cree el informe** siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c7616-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="c7616-161">Seleccione **tabla o matriz**; se abrirá un nuevo asistente.</span><span class="sxs-lookup"><span data-stu-id="c7616-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="c7616-162">En **elegir un conjunto**de recursos, seleccione **elegir un conjunto de recursos existente en este informe o un conjunto de recursos compartido**.</span><span class="sxs-lookup"><span data-stu-id="c7616-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="c7616-163">Seleccione **DataSet0** (opción predeterminada) y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c7616-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="c7616-164">Arrastre **fabricante**, **modelo**y **número de serie** en el cuadro **grupos de filas** .</span><span class="sxs-lookup"><span data-stu-id="c7616-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="c7616-165">Arrastre **HardwareHash** hasta el cuadro **valores** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c7616-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="c7616-166">Desactive las casillas de verificación **Mostrar subtotales y totales generales** y **expandir o contraer grupos**.</span><span class="sxs-lookup"><span data-stu-id="c7616-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="c7616-167">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c7616-167">Select **Next**.</span></span>
6. <span data-ttu-id="c7616-168">Seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c7616-168">Select **Finish**.</span></span>
7. <span data-ttu-id="c7616-169">Seleccione **Ejecutar** para ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="c7616-169">Select **Run** to run your report.</span></span> <span data-ttu-id="c7616-170">Compruebe que el informe proporciona la información que espera.</span><span class="sxs-lookup"><span data-stu-id="c7616-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="c7616-171">Si es necesario, seleccione **diseño** para volver a la vista Diseño y modificar el informe.</span><span class="sxs-lookup"><span data-stu-id="c7616-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="c7616-172">Seleccione **Guardar** para guardar el informe en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c7616-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="c7616-173">Puede ejecutar el nuevo informe en el nodo informes en el área de trabajo supervisión.</span><span class="sxs-lookup"><span data-stu-id="c7616-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="c7616-174">**Por último, exporte el informe y úselo para registrar dispositivos** siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c7616-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="c7616-175">(Solo debe seguir los pasos 1 y 2 de esta sección si ha navegado fuera de los pasos anteriores):</span><span class="sxs-lookup"><span data-stu-id="c7616-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="c7616-176">En la consola de Configuration Manager, seleccione **supervisión**.</span><span class="sxs-lookup"><span data-stu-id="c7616-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="c7616-177">En **supervisión**, expanda **informes**y, a continuación, seleccione **informes**.</span><span class="sxs-lookup"><span data-stu-id="c7616-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="c7616-178">Busque el informe con el nombre que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c7616-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="c7616-179">Haga clic con el botón derecho en este informe y seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c7616-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="c7616-180">En el cuadro de diálogo que se abre, seleccione **exportar** y, a continuación, seleccione **Guardar como CSV**.</span><span class="sxs-lookup"><span data-stu-id="c7616-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="c7616-181">Esta versión del informe extrae los hash de todos los dispositivos con Windows 10 con los que se comunica Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c7616-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="c7616-182">Tendrá que filtrar los resultados solo para los dispositivos que planea registrar con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7616-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c7616-183">La consulta en Configuration Manager no permite espacios en los nombres de columna exportados; por este motivo, los pasos que ha escrito son "Serial_Number" y "HardwareHash".</span><span class="sxs-lookup"><span data-stu-id="c7616-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="c7616-184">Ahora que ya tiene el archivo CSV exportado, debe editar los encabezados del informe para leer el *número de serie* y el *hash de hardware* , tal y como se muestra aquí antes de continuar con el registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c7616-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="c7616-185">Ahora puede seguir [registrando dispositivos con Azure portal](#register-devices-by-using-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c7616-185">Now you can proceed to [Register devices by using the Azure Portal](#register-devices-by-using-the-azure-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="c7616-186">Método de script de PowerShell de Active Directory</span><span class="sxs-lookup"><span data-stu-id="c7616-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="c7616-187">En un entorno de Active Directory, puede usar el `Get-MMDRegistrationInfo` cmdlet de PowerShell para recopilar de forma remota la información de los dispositivos de los grupos de Active Directory mediante WinRM.</span><span class="sxs-lookup"><span data-stu-id="c7616-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="c7616-188">También puede usar el `Get-AD Computer` cmdlet y obtener resultados filtrados para los nombres de modelo de hardware específicos incluidos en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="c7616-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="c7616-189">Para ello, primero confirme estos requisitos previos y, a continuación, siga los pasos:</span><span class="sxs-lookup"><span data-stu-id="c7616-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="c7616-190">WinRM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c7616-190">WinRM is enabled.</span></span>
- <span data-ttu-id="c7616-191">Los dispositivos que desea registrar están activos en la red (es decir, no están desconectados ni desactivados).</span><span class="sxs-lookup"><span data-stu-id="c7616-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="c7616-192">Asegúrese de que tiene un parámetro de credencial de dominio con permiso para ejecutar de forma remota en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c7616-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="c7616-193">Asegúrese de que el Firewall de Windows permite el acceso a WMI.</span><span class="sxs-lookup"><span data-stu-id="c7616-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="c7616-194">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c7616-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="c7616-195">Abra el panel de control del **firewall de Windows Defender** y seleccione **permitir una aplicación o una característica a través de Firewall de Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="c7616-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="c7616-196">Buscar **instrumental de administración de Windows (WMI)** en la lista, habilitar para **privado y público**y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c7616-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="c7616-197">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="c7616-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="c7616-198">Ejecute *alguno de estos* scripts:</span><span class="sxs-lookup"><span data-stu-id="c7616-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="c7616-199">Obtenga acceso a los directorios en los que haya entradas para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c7616-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="c7616-200">Quite las entradas de *todos los dispositivos de todos los* directorios, incluidos los servicios de dominio de Active Directory de Windows Server y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7616-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="c7616-201">Tenga en cuenta que esta eliminación puede tardar varias horas en procesarse por completo.</span><span class="sxs-lookup"><span data-stu-id="c7616-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="c7616-202">Acceso a servicios de administración donde es posible que haya entradas para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c7616-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="c7616-203">Quite las entradas de *todos los dispositivos de todos los* servicios de administración, incluidos Microsoft Endpoint Configuration Manager, Microsoft Intune y Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="c7616-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="c7616-204">Tenga en cuenta que esta eliminación puede tardar varias horas en procesarse por completo.</span><span class="sxs-lookup"><span data-stu-id="c7616-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="c7616-205">Ahora puede seguir [registrando dispositivos](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="c7616-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="c7616-206">Método de script de PowerShell manual</span><span class="sxs-lookup"><span data-stu-id="c7616-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="c7616-207">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="c7616-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="c7616-208">Realizar`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="c7616-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="c7616-209">Realizar`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="c7616-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="c7616-210">Combinar los datos hash.</span><span class="sxs-lookup"><span data-stu-id="c7616-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="c7616-211">Método Flash Drive</span><span class="sxs-lookup"><span data-stu-id="c7616-211">Flash drive method</span></span>

1. <span data-ttu-id="c7616-212">Inserte una unidad USB en un dispositivo que no sea el que está registrando.</span><span class="sxs-lookup"><span data-stu-id="c7616-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="c7616-213">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="c7616-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="c7616-214">Realizar`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="c7616-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="c7616-215">Activa el dispositivo que estás registrando, pero *no inicia la experiencia de instalación*.</span><span class="sxs-lookup"><span data-stu-id="c7616-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="c7616-216">Si inicia de forma accidental la experiencia del programa de instalación, tendrá que restablecer o volver a crear una imagen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c7616-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="c7616-217">Inserte la unidad USB y, a continuación, presione Mayús + F10.</span><span class="sxs-lookup"><span data-stu-id="c7616-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="c7616-218">Abra un símbolo del sistema de PowerShell con derechos administrativos y `cd <pathToUsb>`, a continuación, ejecute.</span><span class="sxs-lookup"><span data-stu-id="c7616-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="c7616-219">Realizar`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="c7616-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="c7616-220">Realizar`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="c7616-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="c7616-221">Quite la unidad USB y, a continuación, apague el dispositivo ejecutando`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="c7616-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="c7616-222">Combinar los datos hash.</span><span class="sxs-lookup"><span data-stu-id="c7616-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="c7616-223">No encienda el dispositivo de nuevo hasta que haya completado el registro para él.</span><span class="sxs-lookup"><span data-stu-id="c7616-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="c7616-224">Combinar datos hash</span><span class="sxs-lookup"><span data-stu-id="c7616-224">Merge hash data</span></span>

<span data-ttu-id="c7616-225">Si ha recopilado los datos de hash de hardware mediante los métodos manuales de la unidad de disco o de PowerShell, ahora debe tener los datos en los archivos CSV combinados en un único archivo para completar el registro.</span><span class="sxs-lookup"><span data-stu-id="c7616-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="c7616-226">Este es un script de PowerShell de ejemplo para facilitar esta tarea:</span><span class="sxs-lookup"><span data-stu-id="c7616-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="c7616-227">Una vez que los datos de hash se combinan en un archivo CSV, ahora puede continuar con [el registro de los dispositivos](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="c7616-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="c7616-228">Registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="c7616-228">Register devices</span></span>

<span data-ttu-id="c7616-229">El archivo CSV debe tener un formato en particular para el registro.</span><span class="sxs-lookup"><span data-stu-id="c7616-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="c7616-230">Si ha recopilado los datos personalmente en los pasos anteriores, el archivo ya debe estar en el formato correcto; Si obtiene el archivo de un proveedor, es posible que deba ajustar el formato.</span><span class="sxs-lookup"><span data-stu-id="c7616-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="c7616-231">Para su comodidad, puede descargar una [plantilla](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) para este archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c7616-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="c7616-232">El archivo tiene que incluir **exactamente los mismos encabezados de columna** que el ejemplo uno (fabricante, modelo, etc.), pero sus propios datos para las otras filas.</span><span class="sxs-lookup"><span data-stu-id="c7616-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="c7616-233">Si usa la plantilla, ábrala en una herramienta de edición de texto como el Bloc de notas y considere la posibilidad de dejar sólo todos los datos de la fila 1, introduciendo solo los datos en las filas 2 y anteriores.</span><span class="sxs-lookup"><span data-stu-id="c7616-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="c7616-234">Si olvida cambiar alguno de los datos de muestra, se producirá un error en el registro.</span><span class="sxs-lookup"><span data-stu-id="c7616-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="c7616-235">Registrar dispositivos con Azure portal</span><span class="sxs-lookup"><span data-stu-id="c7616-235">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="c7616-236">En el portal de Microsoft Managed Desktop [Azure](https://aka.ms/mmdportal), seleccione **dispositivos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="c7616-236">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="c7616-237">Seleccione **+ registrar dispositivos**; se abre el repaso:</span><span class="sxs-lookup"><span data-stu-id="c7616-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="c7616-238">[![Paso a paso después de seleccionar los dispositivos de registro, enumerar los dispositivos con columnas para los usuarios asignados, el número de serie, el estado, la fecha de última visualización y la antigüedad.](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="c7616-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Por desgracia, esto no es cierto. Podemos quitar esta nota, pero dejarla ahora hasta que podamos conversar sobre ella.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="c7616-240">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c7616-240">Follow these steps:</span></span>

1. <span data-ttu-id="c7616-241">En **carga de archivos**, especifique una ruta de acceso al archivo CSV que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c7616-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="c7616-242">Opcionalmente, puede Agregar un identificador de **pedido** o un **identificador de compra** para sus propios fines de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c7616-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="c7616-243">No hay ningún requisito de formato para estos valores.</span><span class="sxs-lookup"><span data-stu-id="c7616-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="c7616-244">Seleccione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="c7616-244">Select **Register devices**.</span></span> <span data-ttu-id="c7616-245">El sistema agregará los dispositivos a la lista de dispositivos en la **hoja dispositivos**, marcada como **pendiente de registro**.</span><span class="sxs-lookup"><span data-stu-id="c7616-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="c7616-246">El registro suele tardar menos de 10 minutos y, cuando se ejecuta correctamente, el dispositivo se muestra como **listo para el usuario** significa que está listo y esperando a que un usuario final empiece a usar.</span><span class="sxs-lookup"><span data-stu-id="c7616-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="c7616-247">Puede supervisar el progreso del registro de dispositivos en la Página principal de **Microsoft administrada para equipos de escritorio** .</span><span class="sxs-lookup"><span data-stu-id="c7616-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="c7616-248">Los posibles Estados que se notifican incluyen:</span><span class="sxs-lookup"><span data-stu-id="c7616-248">Possible states reported there include:</span></span>

| <span data-ttu-id="c7616-249">Estado</span><span class="sxs-lookup"><span data-stu-id="c7616-249">State</span></span> | <span data-ttu-id="c7616-250">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7616-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="c7616-251">Registro pendiente</span><span class="sxs-lookup"><span data-stu-id="c7616-251">Registration pending</span></span> | <span data-ttu-id="c7616-252">Aún no se ha realizado el registro.</span><span class="sxs-lookup"><span data-stu-id="c7616-252">Registration is not done yet.</span></span> <span data-ttu-id="c7616-253">Vuelva a comprobarla más tarde.</span><span class="sxs-lookup"><span data-stu-id="c7616-253">Check back later.</span></span> |
| <span data-ttu-id="c7616-254">Error en el registro</span><span class="sxs-lookup"><span data-stu-id="c7616-254">Registration failed</span></span> | <span data-ttu-id="c7616-255">No se pudo completar el registro.</span><span class="sxs-lookup"><span data-stu-id="c7616-255">Registration could not be completed.</span></span> <span data-ttu-id="c7616-256">Consulte [solución de problemas del registro de dispositivos](#troubleshooting-device-registration) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c7616-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="c7616-257">Listo para el usuario</span><span class="sxs-lookup"><span data-stu-id="c7616-257">Ready for user</span></span> | <span data-ttu-id="c7616-258">El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario final.</span><span class="sxs-lookup"><span data-stu-id="c7616-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="c7616-259">El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional.</span><span class="sxs-lookup"><span data-stu-id="c7616-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="c7616-260">Activo</span><span class="sxs-lookup"><span data-stu-id="c7616-260">Active</span></span> | <span data-ttu-id="c7616-261">El dispositivo se entregó al usuario final y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c7616-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="c7616-262">Esto también indica que los usuarios usan el dispositivo con regularidad.</span><span class="sxs-lookup"><span data-stu-id="c7616-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="c7616-263">Inactivo</span><span class="sxs-lookup"><span data-stu-id="c7616-263">Inactive</span></span> | <span data-ttu-id="c7616-264">El dispositivo se entregó al usuario final y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="c7616-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="c7616-265">Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).</span><span class="sxs-lookup"><span data-stu-id="c7616-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="c7616-266">Solución de problemas de registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c7616-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="c7616-267">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="c7616-267">Error message</span></span> | <span data-ttu-id="c7616-268">Detalles</span><span class="sxs-lookup"><span data-stu-id="c7616-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="c7616-269">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="c7616-269">Device not found</span></span> | <span data-ttu-id="c7616-270">No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c7616-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="c7616-271">Confirma estos valores con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c7616-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="c7616-272">Hash de hardware no válido</span><span class="sxs-lookup"><span data-stu-id="c7616-272">Hardware hash not valid</span></span> | <span data-ttu-id="c7616-273">El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="c7616-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="c7616-274">Compruebe el hash de hardware y vuelva a enviarlo.</span><span class="sxs-lookup"><span data-stu-id="c7616-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="c7616-275">El dispositivo ya está registrado</span><span class="sxs-lookup"><span data-stu-id="c7616-275">Device already registered</span></span> | <span data-ttu-id="c7616-276">Este dispositivo ya está registrado en su organización.</span><span class="sxs-lookup"><span data-stu-id="c7616-276">This device is already registered to your organization.</span></span> <span data-ttu-id="c7616-277">No se requiere ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="c7616-277">No further action required.</span></span> |
| <span data-ttu-id="c7616-278">Dispositivo reclamado por otra organización</span><span class="sxs-lookup"><span data-stu-id="c7616-278">Device claimed by another organization</span></span> | <span data-ttu-id="c7616-279">Este dispositivo ya ha sido reclamado por otra organización.</span><span class="sxs-lookup"><span data-stu-id="c7616-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="c7616-280">Consulta con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c7616-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="c7616-281">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="c7616-281">Unexpected error</span></span> | <span data-ttu-id="c7616-282">La solicitud no se pudo procesar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c7616-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="c7616-283">Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud:<requestId></span><span class="sxs-lookup"><span data-stu-id="c7616-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="c7616-284">Comprobar la imagen</span><span class="sxs-lookup"><span data-stu-id="c7616-284">Check the image</span></span>

<span data-ttu-id="c7616-285">Si el dispositivo proviene de un proveedor de asociados de escritorio administrado por Microsoft, la imagen debe ser correcta.</span><span class="sxs-lookup"><span data-stu-id="c7616-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="c7616-286">También tiene la bienvenida de aplicar la imagen por su cuenta si lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="c7616-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="c7616-287">Para empezar, póngase en contacto con el representante de Microsoft con el que está trabajando y le proporcionará la ubicación y los pasos para aplicar la imagen.</span><span class="sxs-lookup"><span data-stu-id="c7616-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="c7616-288">Entregar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="c7616-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7616-289">Antes de entregar el dispositivo al usuario, asegúrese de que ha obtenido y aplicado las [licencias adecuadas](../get-ready/prerequisites.md) para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="c7616-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="c7616-290">Si se aplican todas las licencias, puede preparar a los [usuarios para que usen dispositivos](get-started-devices.md)y, a continuación, el usuario puede iniciar el dispositivo y continuar con la experiencia del programa de instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c7616-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









