---
title: Más información sobre la prevención de pérdida de datos en punto de conexión de Microsoft 365 (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 'La prevención de pérdida de datos en punto de conexión de Microsoft 365 amplía la supervisión de las actividades de archivo y de las acciones de protección de estos archivos a los puntos de conexión. Los archivos se hacen visibles en las soluciones de cumplimiento de Microsoft 365 '
ms.openlocfilehash: 2423f45fefe994fbaf5704074c49ce862a59340e
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517501"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="dcfa8-104">Más información sobre la prevención de pérdida de datos en punto de conexión de Microsoft 365 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="dcfa8-105">Puede usar la prevención de pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se realizan en elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido accidental de estos elementos.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="dcfa8-106">Para obtener más información sobre DLP, consulte [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa8-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="dcfa8-107">**La prevención de pérdida de datos en punto de conexión** (Endpoint DLP) amplía la supervisión de la actividad y las capacidades de protección de DLP a elementos confidenciales que estén en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="dcfa8-108">Una vez que los dispositivos están incorporados en las soluciones del Centro de cumplimiento de Microsoft 365, la información sobre las acciones de los usuarios relacionadas con los elementos confidenciales se hace visible en el[explorador de actividades](data-classification-activity-explorer.md), y se pueden aplicar acciones de protección a estos elementos mediante [directivas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa8-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="dcfa8-109">Actividades en punto de conexión que puede supervisar y sobre las que puede tomar medidas</span><span class="sxs-lookup"><span data-stu-id="dcfa8-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="dcfa8-110">DLP en punto de conexión de Microsoft le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="dcfa8-111">Esto incluye:</span><span class="sxs-lookup"><span data-stu-id="dcfa8-111">This includes:</span></span>


|<span data-ttu-id="dcfa8-112">actividad en el elemento</span><span class="sxs-lookup"><span data-stu-id="dcfa8-112">activity on item</span></span> |<span data-ttu-id="dcfa8-113">auditable/restringible</span><span class="sxs-lookup"><span data-stu-id="dcfa8-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="dcfa8-114">creado</span><span class="sxs-lookup"><span data-stu-id="dcfa8-114">created</span></span>    | <span data-ttu-id="dcfa8-115">auditable</span><span class="sxs-lookup"><span data-stu-id="dcfa8-115">auditable</span></span>      |
|<span data-ttu-id="dcfa8-116">nombre cambiado</span><span class="sxs-lookup"><span data-stu-id="dcfa8-116">renamed</span></span>    |  <span data-ttu-id="dcfa8-117">auditable</span><span class="sxs-lookup"><span data-stu-id="dcfa8-117">auditable</span></span>       |
|<span data-ttu-id="dcfa8-118">se copió a un medio extraíble o se creó en un medio extraíble</span><span class="sxs-lookup"><span data-stu-id="dcfa8-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="dcfa8-119">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="dcfa8-119">auditable and restrictable</span></span>|
|<span data-ttu-id="dcfa8-120">se copió al recurso compartido de red, por ejemplo \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="dcfa8-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="dcfa8-121">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="dcfa8-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="dcfa8-122">impreso</span><span class="sxs-lookup"><span data-stu-id="dcfa8-122">printed</span></span> |    <span data-ttu-id="dcfa8-123">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="dcfa8-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="dcfa8-124">se copió en la nube a través de Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="dcfa8-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="dcfa8-125">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="dcfa8-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="dcfa8-126">se accedió mediante aplicaciones y exploradores no permitidos</span><span class="sxs-lookup"><span data-stu-id="dcfa8-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="dcfa8-127">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="dcfa8-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="dcfa8-128">¿Qué es diferente en DLP en punto de conexión?</span><span class="sxs-lookup"><span data-stu-id="dcfa8-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="dcfa8-129">Debe tener en cuenta algunos conceptos adicionales antes de profundizar en DLP en punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="dcfa8-130">Habilitar la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="dcfa8-130">Enabling Device management</span></span>

<span data-ttu-id="dcfa8-131">La administración de dispositivos es la funcionalidad que permite la colección de telemetría desde dispositivos y la incluye en las soluciones de cumplimiento de Microsoft 365 como DLP en punto de conexión y la [administración de riesgos internos](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa8-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="dcfa8-132">Necesitará incorporar todos los dispositivos que quiera usar como ubicaciones en directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="dcfa8-134">La incorporación y la retirada se controlan mediante scripts que se descargan desde el centro de administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="dcfa8-135">El centro tiene scripts personalizados para cada uno de estos métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="dcfa8-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="dcfa8-136">script local (hasta 10 equipos)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="dcfa8-137">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="dcfa8-137">Group policy</span></span>
- <span data-ttu-id="dcfa8-138">System Center Configuration Manager (versión 1610 o posterior)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="dcfa8-139">Administración de dispositivos móviles/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dcfa8-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="dcfa8-140">Scripts de incorporación de VDI para equipos no persistentes</span><span class="sxs-lookup"><span data-stu-id="dcfa8-140">VDI onboarding scripts for non-persistent machines</span></span>

![Página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="dcfa8-142">Use los procedimientos descritos en [Introducción a DLP en punto de conexión de Microsoft 365](endpoint-dlp-getting-started.md) para incorporar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="dcfa8-143">Si incorporó dispositivos a través de [la protección contra amenazas avanzada de Microsoft Defender (ATP de Microsoft defender)](https://docs.microsoft.com/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="dcfa8-145">Visualizar datos de DLP en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="dcfa8-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="dcfa8-146">DLP en punto de conexión supervisa la actividad basado en un tipo MIME, por lo que las actividades se capturan incluso si se cambia la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="dcfa8-147">En la versión preliminar pública, inspecciona los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcfa8-147">At public preview it watches all:</span></span>

- <span data-ttu-id="dcfa8-148">archivos de Word</span><span class="sxs-lookup"><span data-stu-id="dcfa8-148">Word files</span></span>
- <span data-ttu-id="dcfa8-149">archivos de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="dcfa8-149">PowerPoint files</span></span>
- <span data-ttu-id="dcfa8-150">archivos de Excel</span><span class="sxs-lookup"><span data-stu-id="dcfa8-150">Excel files</span></span>
- <span data-ttu-id="dcfa8-151">archivos PDF</span><span class="sxs-lookup"><span data-stu-id="dcfa8-151">PDF files</span></span>
- <span data-ttu-id="dcfa8-152">archivos .csv</span><span class="sxs-lookup"><span data-stu-id="dcfa8-152">.csv files</span></span>
- <span data-ttu-id="dcfa8-153">archivos .tsv</span><span class="sxs-lookup"><span data-stu-id="dcfa8-153">.tsv files</span></span>
- <span data-ttu-id="dcfa8-154">archivos c</span><span class="sxs-lookup"><span data-stu-id="dcfa8-154">c files</span></span>
- <span data-ttu-id="dcfa8-155">archivos de clase</span><span class="sxs-lookup"><span data-stu-id="dcfa8-155">class files</span></span>
- <span data-ttu-id="dcfa8-156">archivos cpp</span><span class="sxs-lookup"><span data-stu-id="dcfa8-156">cpp files</span></span>
- <span data-ttu-id="dcfa8-157">archivos cs</span><span class="sxs-lookup"><span data-stu-id="dcfa8-157">cs files</span></span>
- <span data-ttu-id="dcfa8-158">archivos h</span><span class="sxs-lookup"><span data-stu-id="dcfa8-158">h files</span></span>
- <span data-ttu-id="dcfa8-159">archivos Java</span><span class="sxs-lookup"><span data-stu-id="dcfa8-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="dcfa8-160">De forma predeterminada, los archivos .txt y archivos de código fuente no se auditan, DLP los evalúa frente a las directivas aplicadas y, a continuación, las acciones del usuario se auditan o se bloquean en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="dcfa8-161">Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye al explorador de actividad, incluso antes de que configure e implemente las directivas DLP que tienen dispositivos como ubicación.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![eventos de DLP en punto de conexión en el explorador de actividad](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="dcfa8-163">DLP en punto de conexión recopila información exhaustiva sobre la actividad auditada.</span><span class="sxs-lookup"><span data-stu-id="dcfa8-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="dcfa8-164">Por ejemplo, si se copia un archivo a un medio USB extraíble, vería estos atributos en los detalles de actividad:</span><span class="sxs-lookup"><span data-stu-id="dcfa8-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="dcfa8-165">tipo de actividad</span><span class="sxs-lookup"><span data-stu-id="dcfa8-165">activity type</span></span>
- <span data-ttu-id="dcfa8-166">IP del cliente</span><span class="sxs-lookup"><span data-stu-id="dcfa8-166">client IP</span></span>
- <span data-ttu-id="dcfa8-167">ruta de acceso del archivo de destino</span><span class="sxs-lookup"><span data-stu-id="dcfa8-167">target file path</span></span>
- <span data-ttu-id="dcfa8-168">ocurrió una marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="dcfa8-168">happened timestamp</span></span>
- <span data-ttu-id="dcfa8-169">nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="dcfa8-169">file name</span></span>
- <span data-ttu-id="dcfa8-170">usuario</span><span class="sxs-lookup"><span data-stu-id="dcfa8-170">user</span></span>
- <span data-ttu-id="dcfa8-171">extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="dcfa8-171">file extension</span></span>
- <span data-ttu-id="dcfa8-172">tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="dcfa8-172">file size</span></span>
- <span data-ttu-id="dcfa8-173">tipo de información confidencial (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="dcfa8-174">valor sha1</span><span class="sxs-lookup"><span data-stu-id="dcfa8-174">sha1 value</span></span>
- <span data-ttu-id="dcfa8-175">valor sha256</span><span class="sxs-lookup"><span data-stu-id="dcfa8-175">sha256 value</span></span>
- <span data-ttu-id="dcfa8-176">nombre de archivo anterior</span><span class="sxs-lookup"><span data-stu-id="dcfa8-176">previous file name</span></span>
- <span data-ttu-id="dcfa8-177">ubicación</span><span class="sxs-lookup"><span data-stu-id="dcfa8-177">location</span></span>
- <span data-ttu-id="dcfa8-178">primario</span><span class="sxs-lookup"><span data-stu-id="dcfa8-178">parent</span></span>
- <span data-ttu-id="dcfa8-179">ruta de acceso al archivo</span><span class="sxs-lookup"><span data-stu-id="dcfa8-179">filepath</span></span>
- <span data-ttu-id="dcfa8-180">tipo de ubicación de origen</span><span class="sxs-lookup"><span data-stu-id="dcfa8-180">source location type</span></span>
- <span data-ttu-id="dcfa8-181">plataforma</span><span class="sxs-lookup"><span data-stu-id="dcfa8-181">platform</span></span>
- <span data-ttu-id="dcfa8-182">nombre de dispositivo</span><span class="sxs-lookup"><span data-stu-id="dcfa8-182">device name</span></span>
- <span data-ttu-id="dcfa8-183">tipo de ubicación de destino</span><span class="sxs-lookup"><span data-stu-id="dcfa8-183">destination location type</span></span>
- <span data-ttu-id="dcfa8-184">aplicación que realizó la copia</span><span class="sxs-lookup"><span data-stu-id="dcfa8-184">application that performed the copy</span></span>
- <span data-ttu-id="dcfa8-185">Id. del dispositivo MDATP (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-185">MDATP device ID (if applicable)</span></span>
- <span data-ttu-id="dcfa8-186">fabricante del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="dcfa8-186">removable media device manufacturer</span></span>
- <span data-ttu-id="dcfa8-187">modelo del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="dcfa8-187">removable media device model</span></span>
- <span data-ttu-id="dcfa8-188">número de serie del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="dcfa8-188">removable media device serial number</span></span>

![copiar a atributos de actividad USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="dcfa8-190">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="dcfa8-190">Next steps</span></span>

<span data-ttu-id="dcfa8-191">Ahora que ya conoce DLP en punto de conexión, estos son los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="dcfa8-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="dcfa8-192">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="dcfa8-193">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="dcfa8-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcfa8-194">See also</span></span>

- [<span data-ttu-id="dcfa8-195">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="dcfa8-196">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="dcfa8-197">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="dcfa8-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="dcfa8-198">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="dcfa8-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="dcfa8-199">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="dcfa8-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="dcfa8-200">Protección contra amenazas avanzada de Microsoft Defender (ATP de Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="dcfa8-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="dcfa8-201">Administración de riesgos internos</span><span class="sxs-lookup"><span data-stu-id="dcfa8-201">Insider Risk management</span></span>](insider-risk-management.md)