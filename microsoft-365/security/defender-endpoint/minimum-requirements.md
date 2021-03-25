---
title: Requisitos mínimos para Microsoft Defender para endpoint
description: Comprender los requisitos y requisitos de licencias para la incorporación de dispositivos al servicio
keywords: requisitos mínimos, licencias, tabla de comparación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c6afa48fcee80c0b8fb7ed0563264932566b6321
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185796"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="2c9c6-104">Requisitos mínimos para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="2c9c6-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c9c6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2c9c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c9c6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2c9c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2c9c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c9c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2c9c6-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2c9c6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2c9c6-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="2c9c6-110">Existen algunos requisitos mínimos para incorporar dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="2c9c6-111">Obtenga información sobre los requisitos de licencias, hardware y software y otras opciones de configuración para incorporar dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> <span data-ttu-id="2c9c6-112">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="2c9c6-112">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="2c9c6-113">[Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="2c9c6-113">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span></span>

> [!TIP]
> - <span data-ttu-id="2c9c6-114">Obtenga información sobre las últimas mejoras en Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span><span class="sxs-lookup"><span data-stu-id="2c9c6-114">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="2c9c6-115">Defender for Endpoint demostró las capacidades de detección y óptica líderes del sector en la reciente evaluación de MITRE.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-115">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="2c9c6-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="2c9c6-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2c9c6-117">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="2c9c6-117">Licensing requirements</span></span>
<span data-ttu-id="2c9c6-118">Microsoft Defender para endpoint requiere una de las siguientes ofertas de licencias por volumen de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-118">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="2c9c6-119">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="2c9c6-119">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="2c9c6-120">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="2c9c6-120">Windows 10 Education A5</span></span>
- <span data-ttu-id="2c9c6-121">Microsoft 365 E5 (M365 E5) que incluye Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="2c9c6-121">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="2c9c6-122">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="2c9c6-122">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="2c9c6-123">Seguridad de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2c9c6-123">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="2c9c6-124">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="2c9c6-124">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="2c9c6-125">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2c9c6-125">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="2c9c6-126">Los usuarios con licencia elegibles pueden usar Microsoft Defender para Endpoint en hasta cinco dispositivos simultáneos.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-126">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="2c9c6-127">Microsoft Defender para endpoint también está disponible para la compra de un proveedor de soluciones en la nube (CSP).</span><span class="sxs-lookup"><span data-stu-id="2c9c6-127">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="2c9c6-128">Microsoft Defender para endpoint para servidores requiere una de las siguientes opciones de licencia:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-128">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="2c9c6-129">Centro de seguridad de Azure con Azure Defender habilitado</span><span class="sxs-lookup"><span data-stu-id="2c9c6-129">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="2c9c6-130">Microsoft Defender para endpoint for Server (uno por servidor cubierto)</span><span class="sxs-lookup"><span data-stu-id="2c9c6-130">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="2c9c6-131">Los clientes pueden adquirir licencias de servidor (una por servidor cubierto Entorno de sistema operativo (OSE)) para Microsoft Defender para Endpoint for Servers si tienen un mínimo combinado de 50 licencias para una o más de las siguientes licencias de usuario:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-131">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="2c9c6-132">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2c9c6-132">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="2c9c6-133">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="2c9c6-133">Windows E5/A5</span></span>
> * <span data-ttu-id="2c9c6-134">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="2c9c6-134">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="2c9c6-135">Seguridad de Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="2c9c6-135">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="2c9c6-136">Para obtener información detallada sobre las licencias, consulta el sitio [términos](https://www.microsoft.com/licensing/terms/) del producto y trabaja con el equipo de tu cuenta para obtener más información sobre los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-136">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="2c9c6-137">Para obtener más información sobre la matriz de características de las ediciones de Windows 10, consulta [Comparar ediciones de Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="2c9c6-137">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="2c9c6-138">Para obtener una tabla de comparación detallada de la comparación de la edición comercial de Windows 10, consulta [el PDF de comparación.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="2c9c6-138">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="2c9c6-139">Requisitos de los exploradores</span><span class="sxs-lookup"><span data-stu-id="2c9c6-139">Browser requirements</span></span>
<span data-ttu-id="2c9c6-140">El acceso a Defender for Endpoint se realiza a través de un explorador, que admite los siguientes exploradores:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-140">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="2c9c6-141">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2c9c6-141">Microsoft Edge</span></span>
- <span data-ttu-id="2c9c6-142">Versión 11 de Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2c9c6-142">Internet Explorer version 11</span></span>
- <span data-ttu-id="2c9c6-143">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="2c9c6-143">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="2c9c6-144">Aunque otros exploradores pueden funcionar, los exploradores mencionados son los que se admiten.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-144">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="2c9c6-145">Requisitos de hardware y software</span><span class="sxs-lookup"><span data-stu-id="2c9c6-145">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="2c9c6-146">Versiones compatibles de Windows</span><span class="sxs-lookup"><span data-stu-id="2c9c6-146">Supported Windows versions</span></span>
- <span data-ttu-id="2c9c6-147">Windows 7 SP1 Enterprise[(requiere ESU para ser compatible).)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)</span><span class="sxs-lookup"><span data-stu-id="2c9c6-147">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="2c9c6-148">Windows 7 SP1 Pro ([Requiere ESU para admitir](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="2c9c6-148">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="2c9c6-149">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c9c6-149">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="2c9c6-150">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="2c9c6-150">Windows 8.1 Pro</span></span>
- <span data-ttu-id="2c9c6-151">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c9c6-151">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="2c9c6-152">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="2c9c6-152">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="2c9c6-153">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="2c9c6-153">Windows 10 Education</span></span>
- <span data-ttu-id="2c9c6-154">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="2c9c6-154">Windows 10 Pro</span></span>
- <span data-ttu-id="2c9c6-155">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="2c9c6-155">Windows 10 Pro Education</span></span>
- <span data-ttu-id="2c9c6-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="2c9c6-156">Windows server</span></span>
  - <span data-ttu-id="2c9c6-157">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="2c9c6-157">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="2c9c6-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2c9c6-158">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="2c9c6-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2c9c6-159">Windows Server 2016</span></span>
  - <span data-ttu-id="2c9c6-160">Windows Server, versión 1803 o posterior</span><span class="sxs-lookup"><span data-stu-id="2c9c6-160">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="2c9c6-161">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2c9c6-161">Windows Server 2019</span></span>
- <span data-ttu-id="2c9c6-162">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="2c9c6-162">Windows Virtual Desktop</span></span>

<span data-ttu-id="2c9c6-163">Los dispositivos de la red deben ejecutar una de estas ediciones.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-163">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="2c9c6-164">Los requisitos de hardware de Defender para Endpoint en dispositivos son los mismos para las ediciones admitidas.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-164">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="2c9c6-165">Las máquinas que ejecutan versiones móviles de Windows (como Windows CE y Windows 10 Mobile) no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-165">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) are not supported.</span></span>
>
> <span data-ttu-id="2c9c6-166">Las máquinas virtuales que ejecutan Windows 10 Enterprise 2016 LTSB pueden encontrar problemas de rendimiento si se ejecutan en plataformas de virtualización que no son de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-166">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="2c9c6-167">Para entornos virtuales, se recomienda usar Windows 10 Enterprise LTSC 2019 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-167">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="2c9c6-168">Otros sistemas operativos compatibles</span><span class="sxs-lookup"><span data-stu-id="2c9c6-168">Other supported operating systems</span></span>
- <span data-ttu-id="2c9c6-169">Android</span><span class="sxs-lookup"><span data-stu-id="2c9c6-169">Android</span></span>
- <span data-ttu-id="2c9c6-170">Linux</span><span class="sxs-lookup"><span data-stu-id="2c9c6-170">Linux</span></span>
- <span data-ttu-id="2c9c6-171">macOS</span><span class="sxs-lookup"><span data-stu-id="2c9c6-171">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="2c9c6-172">Tendrás que conocer las distribuciones y versiones exactas de Linux de Android y macOS que son compatibles con Defender for Endpoint para que la integración funcione.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-172">You'll need to know the exact Linux distributions and versions of Android and macOS that are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="2c9c6-173">Requisitos de configuración y almacenamiento de datos y red</span><span class="sxs-lookup"><span data-stu-id="2c9c6-173">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="2c9c6-174">Al ejecutar el asistente de incorporación por primera vez, debe elegir dónde se almacena la información relacionada con El punto de conexión de Microsoft Defender: en la Unión Europea, el Reino Unido o el centro de datos de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-174">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="2c9c6-175">No puede cambiar la ubicación de almacenamiento de datos después de la configuración por primera vez.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-175">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="2c9c6-176">Revisa [Microsoft Defender para el almacenamiento y](data-storage-privacy.md) privacidad de datos de punto de conexión para obtener más información sobre dónde y cómo almacena Microsoft los datos.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-176">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="2c9c6-177">Configuración de datos de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2c9c6-177">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="2c9c6-178">Microsoft Defender para endpoint no requiere ningún nivel de diagnóstico específico mientras esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-178">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="2c9c6-179">Asegúrese de que el servicio de datos de diagnóstico está habilitado en todos los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-179">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="2c9c6-180">De forma predeterminada, este servicio está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-180">By default, this service is enabled.</span></span> <span data-ttu-id="2c9c6-181">Es una buena práctica comprobar para asegurarse de que los datos del sensor se obtienen de ellos.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-181">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="2c9c6-182">Usa la línea de comandos para comprobar el tipo de inicio del servicio de datos de diagnóstico **de Windows 10:**</span><span class="sxs-lookup"><span data-stu-id="2c9c6-182">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="2c9c6-183">Abra un símbolo del sistema con privilegios elevados en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-183">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="2c9c6-184">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-184">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="2c9c6-185">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-185">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2c9c6-186">Escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-186">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="2c9c6-187">Si el servicio está habilitado, el resultado debería ser parecido a la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-187">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Resultado del comando de consulta sc para diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="2c9c6-189">Deberá establecer el servicio para que se inicie automáticamente si el START_TYPE **no** está establecido en **AUTO_START**.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-189">You'll need to set the service to automatically start if the **START_TYPE** is not set to **AUTO_START**.</span></span>


<span data-ttu-id="2c9c6-190">**Usa la línea de comandos para establecer el servicio de datos de diagnóstico de Windows 10 para que se inicie automáticamente:**</span><span class="sxs-lookup"><span data-stu-id="2c9c6-190">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="2c9c6-191">Abra un símbolo del sistema con privilegios elevados en el extremo:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-191">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="2c9c6-192">Vaya a **Inicio** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-192">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="2c9c6-193">Haga clic derecho en **Símbolo del sistema** y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-193">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="2c9c6-194">Escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-194">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="2c9c6-195">Se muestra un mensaje de éxito.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-195">A success message is displayed.</span></span> <span data-ttu-id="2c9c6-196">Para comprobar el cambio, escriba el siguiente comando y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="2c9c6-196">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="2c9c6-197">Conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="2c9c6-197">Internet connectivity</span></span>
<span data-ttu-id="2c9c6-198">La conectividad a Internet en dispositivos es necesaria directamente o a través del proxy.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-198">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="2c9c6-199">El sensor Defender for Endpoint puede usar un ancho de banda promedio diario de 5 MB para comunicarse con el servicio en la nube de Defender for Endpoint e informar de los datos cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-199">The Defender for Endpoint sensor can utilize a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="2c9c6-200">Las actividades únicas, como las cargas de archivos y la colección de paquetes de investigación, no se incluyen en este ancho de banda promedio diario.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-200">One-off activities such as file uploads and investigation package collection are not included in this daily average bandwidth.</span></span>

<span data-ttu-id="2c9c6-201">Para obtener más información acerca de las opciones de configuración de proxy adicionales, vea [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="2c9c6-201">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="2c9c6-202">Antes de incorporar dispositivos, el servicio de datos de diagnóstico debe estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-202">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="2c9c6-203">El servicio está habilitado de forma predeterminada en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-203">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="2c9c6-204">Requisito de configuración de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2c9c6-204">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="2c9c6-205">El agente de Defender for Endpoint depende de la capacidad de Antivirus de Microsoft Defender para examinar archivos y proporcionar información sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-205">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="2c9c6-206">Configure las actualizaciones de inteligencia de seguridad en los dispositivos defender para puntos de conexión independientemente de si antivirus de Microsoft Defender es el antimalware activo o no.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-206">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="2c9c6-207">Para obtener más información, vea [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="2c9c6-207">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="2c9c6-208">Cuando Antivirus de Microsoft Defender no es el antimalware activo de la organización y usa el servicio Defender para endpoints, Antivirus de Microsoft Defender pasa al modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-208">When Microsoft Defender Antivirus is not the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="2c9c6-209">Si su organización ha desactivado Antivirus de Microsoft Defender a través de la directiva de grupo u otros métodos, los dispositivos que están incorporados deben excluirse de esta directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-209">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="2c9c6-210">Si está incorporando servidores y Antivirus de Microsoft Defender no es el antimalware activo en sus servidores, antivirus de Microsoft Defender tendrá que configurarse para ir en modo pasivo o desinstalar.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-210">If you are onboarding servers and Microsoft Defender Antivirus is not the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="2c9c6-211">La configuración depende de la versión del servidor.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-211">The configuration is dependent on the server version.</span></span> <span data-ttu-id="2c9c6-212">Para obtener más información, vea [Compatibilidad de Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="2c9c6-212">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2c9c6-213">La directiva de grupo normal no se aplica a la Protección contra alteraciones y los cambios en la configuración de Antivirus de Microsoft Defender se omitirán cuando esté la protección contra alteraciones.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-213">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="2c9c6-214">El controlador antimalware de inicio anticipado (ELAM) de Antivirus de Microsoft Defender está habilitado</span><span class="sxs-lookup"><span data-stu-id="2c9c6-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="2c9c6-215">Si ejecuta Antivirus de Microsoft Defender como el producto antimalware principal en sus dispositivos, el agente defender para endpoint se incorporará correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-215">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="2c9c6-216">Si ejecuta un cliente antimalware de terceros y usa soluciones de administración de dispositivos móviles o Microsoft Endpoint Manager (rama actual), deberá asegurarse de que el controlador ELAM de Antivirus de Microsoft Defender está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2c9c6-216">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure that the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="2c9c6-217">Para obtener más información, vea [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="2c9c6-217">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="2c9c6-218">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2c9c6-218">Related topics</span></span>
- [<span data-ttu-id="2c9c6-219">Configurar Microsoft Defender para la implementación de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="2c9c6-219">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="2c9c6-220">Dispositivos integrados</span><span class="sxs-lookup"><span data-stu-id="2c9c6-220">Onboard devices</span></span>](onboard-configure.md)
