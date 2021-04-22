---
title: Puntuación de seguridad de Microsoft para dispositivos
description: La puntuación de los dispositivos muestra el estado de configuración de seguridad colectiva de los dispositivos en todos los controles de aplicación, sistema operativo, red, cuentas y seguridad.
keywords: Puntuación segura de Microsoft para dispositivos, Puntuación segura de Microsoft Defender para dispositivos, puntuación segura, puntuación de configuración, administración de amenazas y vulnerabilidades, controles de seguridad, oportunidades de mejora, puntuación de configuración de seguridad con el tiempo, posición de seguridad, línea base
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f2c799d477c400482c16b09b4d8a5cdc01106dfa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934086"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="253ff-104">Puntuación de seguridad de Microsoft para dispositivos</span><span class="sxs-lookup"><span data-stu-id="253ff-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="253ff-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="253ff-105">**Applies to:**</span></span>

- [<span data-ttu-id="253ff-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="253ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="253ff-107">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="253ff-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="253ff-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="253ff-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="253ff-109">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="253ff-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="253ff-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="253ff-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="253ff-111">La puntuación de configuración ahora forma parte de la administración de amenazas y vulnerabilidades como Puntuación segura de Microsoft para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="253ff-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="253ff-112">La puntuación de los dispositivos está visible en el panel de [administración](tvm-dashboard-insights.md) de amenazas y vulnerabilidades del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="253ff-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="253ff-113">Una puntuación segura de Microsoft más alta para dispositivos significa que los puntos de conexión son más resistentes frente a los ataques de amenazas de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="253ff-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="253ff-114">Refleja el estado de configuración de seguridad colectiva de los dispositivos en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="253ff-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="253ff-115">Aplicación</span><span class="sxs-lookup"><span data-stu-id="253ff-115">Application</span></span>
- <span data-ttu-id="253ff-116">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="253ff-116">Operating system</span></span>
- <span data-ttu-id="253ff-117">Red</span><span class="sxs-lookup"><span data-stu-id="253ff-117">Network</span></span>
- <span data-ttu-id="253ff-118">Cuentas</span><span class="sxs-lookup"><span data-stu-id="253ff-118">Accounts</span></span>
- <span data-ttu-id="253ff-119">Controles de seguridad</span><span class="sxs-lookup"><span data-stu-id="253ff-119">Security controls</span></span>

<span data-ttu-id="253ff-120">Seleccione una categoría para ir a la [**página Recomendaciones de seguridad**](tvm-security-recommendation.md) y ver las recomendaciones pertinentes.</span><span class="sxs-lookup"><span data-stu-id="253ff-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="253ff-121">Activar el conector de puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="253ff-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="253ff-122">Reenvía Microsoft Defender para las señales de punto de conexión, lo que ofrece a Microsoft Secure Score visibilidad en la posición de seguridad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="253ff-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="253ff-123">Los datos reenviados se almacenan y procesan en la misma ubicación que los datos de puntuación segura de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="253ff-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="253ff-124">Los cambios pueden tardar hasta unas horas en reflejarse en el panel.</span><span class="sxs-lookup"><span data-stu-id="253ff-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="253ff-125">En el panel de navegación, vaya a **Configuración**  >  **Características avanzadas**</span><span class="sxs-lookup"><span data-stu-id="253ff-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="253ff-126">Desplácese hacia abajo **hasta Puntuación segura de Microsoft** y cambie la configuración a **On**.</span><span class="sxs-lookup"><span data-stu-id="253ff-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="253ff-127">Seleccione **Guardar preferencias**.</span><span class="sxs-lookup"><span data-stu-id="253ff-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="253ff-128">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="253ff-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="253ff-129">La puntuación segura de Microsoft para dispositivos actualmente admite configuraciones establecidas a través de la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="253ff-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="253ff-130">Debido a la compatibilidad parcial actual de Intune, las configuraciones que podrían haber sido configuradas a través de Intune podrían aparecer como mal configuradas.</span><span class="sxs-lookup"><span data-stu-id="253ff-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="253ff-131">Póngase en contacto con el administrador de TI para comprobar el estado de configuración real en caso de que su organización use Intune para la administración de configuración segura.</span><span class="sxs-lookup"><span data-stu-id="253ff-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="253ff-132">Los datos de la tarjeta Puntuación segura de Microsoft para dispositivos son el producto del proceso de detección de vulnerabilidades meticuloso y continuo.</span><span class="sxs-lookup"><span data-stu-id="253ff-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="253ff-133">Se agrega con evaluaciones de detección de configuración que continuamente:</span><span class="sxs-lookup"><span data-stu-id="253ff-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="253ff-134">Comparar configuraciones recopiladas con los puntos de referencia recopilados para detectar activos mal configurados</span><span class="sxs-lookup"><span data-stu-id="253ff-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="253ff-135">Asignar configuraciones a vulnerabilidades que se pueden corregir o corregir parcialmente (reducción de riesgos)</span><span class="sxs-lookup"><span data-stu-id="253ff-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="253ff-136">Recopilar y mantener indicadores de configuración de procedimientos recomendados (proveedores, fuentes de seguridad, equipos de investigación internos)</span><span class="sxs-lookup"><span data-stu-id="253ff-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="253ff-137">Recopilar y supervisar los cambios del estado de configuración del control de seguridad de todos los activos</span><span class="sxs-lookup"><span data-stu-id="253ff-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="253ff-138">Mejorar la configuración de seguridad</span><span class="sxs-lookup"><span data-stu-id="253ff-138">Improve your security configuration</span></span>

<span data-ttu-id="253ff-139">Mejore la configuración de seguridad mediante la corrección de problemas de la lista de recomendaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="253ff-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="253ff-140">Al hacerlo, la puntuación segura de Microsoft para dispositivos mejora y la organización se vuelve más resistente frente a las amenazas y vulnerabilidades de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="253ff-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="253ff-141">En la tarjeta Puntuación segura de Microsoft para dispositivos en el panel de administración de amenazas y vulnerabilidades, seleccione una de las categorías.</span><span class="sxs-lookup"><span data-stu-id="253ff-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="253ff-142">Verá la lista de recomendaciones relacionadas con esa categoría.</span><span class="sxs-lookup"><span data-stu-id="253ff-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="253ff-143">Le llevará a la página Recomendaciones [**de**](tvm-security-recommendation.md) seguridad.</span><span class="sxs-lookup"><span data-stu-id="253ff-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="253ff-144">Si desea ver todas las recomendaciones de seguridad, una vez que llegue a la página Recomendaciones de seguridad, desactive el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="253ff-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="253ff-145">Seleccione un elemento en la lista.</span><span class="sxs-lookup"><span data-stu-id="253ff-145">Select an item on the list.</span></span> <span data-ttu-id="253ff-146">El panel desplegable se abrirá con detalles relacionados con la recomendación.</span><span class="sxs-lookup"><span data-stu-id="253ff-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="253ff-147">Seleccione **Opciones de corrección**.</span><span class="sxs-lookup"><span data-stu-id="253ff-147">Select **Remediation options**.</span></span>

   ![Recomendaciones de seguridad relacionadas con controles de seguridad](images/tvm_security_controls.png)

3. <span data-ttu-id="253ff-149">Lea la descripción para comprender el contexto del problema y qué hacer a continuación.</span><span class="sxs-lookup"><span data-stu-id="253ff-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="253ff-150">Seleccione una fecha de vencimiento, agregue notas y **seleccione Exportar** todos los datos de actividad de corrección a CSV para poder adjuntarlos a un correo electrónico para su seguimiento.</span><span class="sxs-lookup"><span data-stu-id="253ff-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="253ff-151">**Enviar solicitud**.</span><span class="sxs-lookup"><span data-stu-id="253ff-151">**Submit request**.</span></span> <span data-ttu-id="253ff-152">Verá un mensaje de confirmación de que se ha creado la tarea de corrección.</span><span class="sxs-lookup"><span data-stu-id="253ff-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="253ff-153">![Confirmación de creación de tareas de corrección](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="253ff-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="253ff-154">Guarde el archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="253ff-154">Save your CSV file.</span></span>
   <span data-ttu-id="253ff-155">![Guardar archivo csv](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="253ff-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="253ff-156">Envíe un correo electrónico de seguimiento a su administrador de TI y permita el tiempo que haya asignado para que la corrección se propague en el sistema.</span><span class="sxs-lookup"><span data-stu-id="253ff-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="253ff-157">Revisa la **tarjeta Puntuación segura de Microsoft para** dispositivos de nuevo en el panel.</span><span class="sxs-lookup"><span data-stu-id="253ff-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="253ff-158">El número de recomendaciones de controles de seguridad disminuirá.</span><span class="sxs-lookup"><span data-stu-id="253ff-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="253ff-159">Cuando selecciona **Controles de seguridad**  para volver a la página Recomendaciones de seguridad, el elemento que ha abordado ya no aparecerá en la lista.</span><span class="sxs-lookup"><span data-stu-id="253ff-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="253ff-160">La puntuación segura de Microsoft para dispositivos debe aumentar.</span><span class="sxs-lookup"><span data-stu-id="253ff-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="253ff-161">Para aumentar las tasas de detección de evaluación de vulnerabilidades, descargue las siguientes actualizaciones de seguridad obligatorias e impleméntelas en la red:</span><span class="sxs-lookup"><span data-stu-id="253ff-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="253ff-162">Clientes de 19H1 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="253ff-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="253ff-163">Clientes de RS5 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="253ff-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="253ff-164">Clientes de RS4 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="253ff-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="253ff-165">Clientes de RS3 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="253ff-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="253ff-166">Para descargar las actualizaciones de seguridad:</span><span class="sxs-lookup"><span data-stu-id="253ff-166">To download the security updates:</span></span>
>1. <span data-ttu-id="253ff-167">Vaya a [Catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/home.aspx).</span><span class="sxs-lookup"><span data-stu-id="253ff-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="253ff-168">Clave en el número KB de actualización de seguridad que necesita descargar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="253ff-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="253ff-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="253ff-169">Related topics</span></span>

- [<span data-ttu-id="253ff-170">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="253ff-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="253ff-171">Panel</span><span class="sxs-lookup"><span data-stu-id="253ff-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="253ff-172">Puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="253ff-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="253ff-173">Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="253ff-173">Security recommendations</span></span>](tvm-security-recommendation.md)
