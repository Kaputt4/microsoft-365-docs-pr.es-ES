---
title: Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'La prevención de pérdida de datos de Microsoft 365 Endpoint amplía la supervisión de las actividades de archivo y las acciones de protección para estos archivos en los puntos de conexión. Los archivos se hacen visibles en las soluciones de cumplimiento de Microsoft 365 '
ms.openlocfilehash: 966e201acb8038d85f0d06c0800c9845fd79097e
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984934"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="d803a-104">Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d803a-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="d803a-p102">Puede usar la prevención de la pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se realizan en elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido no intencionado de estos elementos. Para obtener más información sobre DLP, vea [información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d803a-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="d803a-p103">**Prevención de la pérdida de datos en punto de conexión** (DLP en punto de conexión) amplía las funciones de supervisión y protección de la actividad de DLP a elementos confidenciales que estén en dispositivos con Windows 10. Una vez que los dispositivos están integrados en las soluciones de cumplimiento de Microsoft 365, la información sobre lo que los usuarios llevan a cabo con elementos confidenciales se hace visible en el [Explorador de actividades](data-classification-activity-explorer.md) y puede aplicar acciones de protección a estos elementos mediante las [Directivas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d803a-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="d803a-109">Actividades en punto de conexión que puede supervisar y sobre las que puede tomar medidas</span><span class="sxs-lookup"><span data-stu-id="d803a-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="d803a-p104">Microsoft Endpoint DLP le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10. Se incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d803a-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="d803a-112">actividad en el elemento</span><span class="sxs-lookup"><span data-stu-id="d803a-112">activity on item</span></span> |<span data-ttu-id="d803a-113">auditable/restringible</span><span class="sxs-lookup"><span data-stu-id="d803a-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="d803a-114">creado</span><span class="sxs-lookup"><span data-stu-id="d803a-114">created</span></span>    | <span data-ttu-id="d803a-115">auditable</span><span class="sxs-lookup"><span data-stu-id="d803a-115">auditable</span></span>      |
|<span data-ttu-id="d803a-116">nombre cambiado</span><span class="sxs-lookup"><span data-stu-id="d803a-116">renamed</span></span>    |  <span data-ttu-id="d803a-117">auditable</span><span class="sxs-lookup"><span data-stu-id="d803a-117">auditable</span></span>       |
|<span data-ttu-id="d803a-118">se copió a un medio extraíble o se creó en un medio extraíble</span><span class="sxs-lookup"><span data-stu-id="d803a-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="d803a-119">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="d803a-119">auditable and restrictable</span></span>|
|<span data-ttu-id="d803a-120">se copió al recurso compartido de red, por ejemplo \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="d803a-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="d803a-121">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="d803a-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="d803a-122">impreso</span><span class="sxs-lookup"><span data-stu-id="d803a-122">printed</span></span> |    <span data-ttu-id="d803a-123">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="d803a-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="d803a-124">se copió en la nube a través de Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="d803a-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="d803a-125">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="d803a-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="d803a-126">se accedió mediante aplicaciones y exploradores no permitidos</span><span class="sxs-lookup"><span data-stu-id="d803a-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="d803a-127">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="d803a-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="d803a-128">¿Qué es diferente en DLP en punto de conexión?</span><span class="sxs-lookup"><span data-stu-id="d803a-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="d803a-129">Debe tener en cuenta algunos conceptos adicionales antes de profundizar en DLP en punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d803a-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="d803a-130">Habilitar la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d803a-130">Enabling Device management</span></span>

<span data-ttu-id="d803a-p105">La administración de dispositivos es la funcionalidad que permite la recopilación de telemetría de dispositivos y la incluye en las soluciones de cumplimiento de Microsoft 365 como el Endpoint DLP y la [Administración de riesgos de Insider](insider-risk-management.md). Necesitará incorporar todos los dispositivos que quiera usar como ubicaciones en directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="d803a-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d803a-133">![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="d803a-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="d803a-p106">La incorporación y retirada se controla mediante scripts que descarga desde el centro de administración de dispositivos. El centro tiene scripts personalizados para cada uno de estos métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="d803a-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="d803a-136">script local (hasta 10 equipos)</span><span class="sxs-lookup"><span data-stu-id="d803a-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="d803a-137">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="d803a-137">Group policy</span></span>
- <span data-ttu-id="d803a-138">System Center Configuration Manager (versión 1610 o posterior)</span><span class="sxs-lookup"><span data-stu-id="d803a-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="d803a-139">Administración de dispositivos móviles/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d803a-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="d803a-140">Scripts de incorporación de VDI para equipos no persistentes</span><span class="sxs-lookup"><span data-stu-id="d803a-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d803a-141">![página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="d803a-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="d803a-142">Use los procedimientos descritos en la [Introducción a la DLP en punto de conexión en Microsoft 365](endpoint-dlp-getting-started.md) para incorporar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d803a-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="d803a-143">Si incorporó dispositivos a través de [Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d803a-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d803a-144">![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="d803a-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="d803a-145">Visualizar datos sobre la DLP en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d803a-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="d803a-p107">DLP en punto de conexión supervisa actividad basada en un tipo MIME, por lo que las actividades se capturarán aunque se cambie la extensión de archivo. En la vista previa pública, vigila todas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d803a-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="d803a-148">archivos de Word</span><span class="sxs-lookup"><span data-stu-id="d803a-148">Word files</span></span>
- <span data-ttu-id="d803a-149">archivos de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d803a-149">PowerPoint files</span></span>
- <span data-ttu-id="d803a-150">archivos de Excel</span><span class="sxs-lookup"><span data-stu-id="d803a-150">Excel files</span></span>
- <span data-ttu-id="d803a-151">archivos PDF</span><span class="sxs-lookup"><span data-stu-id="d803a-151">PDF files</span></span>
- <span data-ttu-id="d803a-152">archivos .csv</span><span class="sxs-lookup"><span data-stu-id="d803a-152">.csv files</span></span>
- <span data-ttu-id="d803a-153">archivos .tsv</span><span class="sxs-lookup"><span data-stu-id="d803a-153">.tsv files</span></span>
- <span data-ttu-id="d803a-154">archivos .txt</span><span class="sxs-lookup"><span data-stu-id="d803a-154">.txt files</span></span>
- <span data-ttu-id="d803a-155">archivos .rtf</span><span class="sxs-lookup"><span data-stu-id="d803a-155">.rtf files</span></span>
- <span data-ttu-id="d803a-156">archivos .c</span><span class="sxs-lookup"><span data-stu-id="d803a-156">.c files</span></span>
- <span data-ttu-id="d803a-157">archivos .class</span><span class="sxs-lookup"><span data-stu-id="d803a-157">.class files</span></span>
- <span data-ttu-id="d803a-158">archivos .cpp</span><span class="sxs-lookup"><span data-stu-id="d803a-158">.cpp files</span></span>
- <span data-ttu-id="d803a-159">archivos .cs</span><span class="sxs-lookup"><span data-stu-id="d803a-159">.cs files</span></span>
- <span data-ttu-id="d803a-160">archivos .h</span><span class="sxs-lookup"><span data-stu-id="d803a-160">.h files</span></span>
- <span data-ttu-id="d803a-161">archivos .java</span><span class="sxs-lookup"><span data-stu-id="d803a-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="d803a-p108">DLP en punto de conexión evalúa los archivos de todos los tipos anteriores en la directiva de DLP y aplica las acciones de protección correspondientes. Todos los archivos que coinciden con una directiva de DLP se auditan para todas las acciones admitidas, aunque no estén bloqueados. Además, la actividad de archivos que se lleva a cabo en cualquier archivo Word, PowerPoint, Excel, PDF y .csv se audita de forma predeterminada, independientemente de si una directiva de DLP existe o coincide con estos archivos.</span><span class="sxs-lookup"><span data-stu-id="d803a-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="d803a-165">Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye hacia el explorador de actividades incluso antes de configurar e implementar cualquier directiva de DLP que tenga dispositivos como ubicación.</span><span class="sxs-lookup"><span data-stu-id="d803a-165">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d803a-166">![eventos de DLP en punto de conexión en el explorador de actividad](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="d803a-166">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="d803a-167">DLP en punto de conexión recopila información exhaustiva sobre la actividad auditada.</span><span class="sxs-lookup"><span data-stu-id="d803a-167">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="d803a-168">Por ejemplo, si se copia un archivo a un medio USB extraíble, vería estos atributos en los detalles de actividad:</span><span class="sxs-lookup"><span data-stu-id="d803a-168">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="d803a-169">tipo de actividad</span><span class="sxs-lookup"><span data-stu-id="d803a-169">activity type</span></span>
- <span data-ttu-id="d803a-170">IP del cliente</span><span class="sxs-lookup"><span data-stu-id="d803a-170">client IP</span></span>
- <span data-ttu-id="d803a-171">ruta de acceso del archivo de destino</span><span class="sxs-lookup"><span data-stu-id="d803a-171">target file path</span></span>
- <span data-ttu-id="d803a-172">ocurrió una marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="d803a-172">happened timestamp</span></span>
- <span data-ttu-id="d803a-173">nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="d803a-173">file name</span></span>
- <span data-ttu-id="d803a-174">usuario</span><span class="sxs-lookup"><span data-stu-id="d803a-174">user</span></span>
- <span data-ttu-id="d803a-175">extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="d803a-175">file extension</span></span>
- <span data-ttu-id="d803a-176">tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="d803a-176">file size</span></span>
- <span data-ttu-id="d803a-177">tipo de información confidencial (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="d803a-177">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="d803a-178">valor sha1</span><span class="sxs-lookup"><span data-stu-id="d803a-178">sha1 value</span></span>
- <span data-ttu-id="d803a-179">valor sha256</span><span class="sxs-lookup"><span data-stu-id="d803a-179">sha256 value</span></span>
- <span data-ttu-id="d803a-180">nombre de archivo anterior</span><span class="sxs-lookup"><span data-stu-id="d803a-180">previous file name</span></span>
- <span data-ttu-id="d803a-181">ubicación</span><span class="sxs-lookup"><span data-stu-id="d803a-181">location</span></span>
- <span data-ttu-id="d803a-182">primario</span><span class="sxs-lookup"><span data-stu-id="d803a-182">parent</span></span>
- <span data-ttu-id="d803a-183">ruta de acceso al archivo</span><span class="sxs-lookup"><span data-stu-id="d803a-183">filepath</span></span>
- <span data-ttu-id="d803a-184">tipo de ubicación de origen</span><span class="sxs-lookup"><span data-stu-id="d803a-184">source location type</span></span>
- <span data-ttu-id="d803a-185">plataforma</span><span class="sxs-lookup"><span data-stu-id="d803a-185">platform</span></span>
- <span data-ttu-id="d803a-186">nombre de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d803a-186">device name</span></span>
- <span data-ttu-id="d803a-187">tipo de ubicación de destino</span><span class="sxs-lookup"><span data-stu-id="d803a-187">destination location type</span></span>
- <span data-ttu-id="d803a-188">aplicación que realizó la copia</span><span class="sxs-lookup"><span data-stu-id="d803a-188">application that performed the copy</span></span>
- <span data-ttu-id="d803a-189">Id. de dispositivo de Microsoft Defender para punto de conexión (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="d803a-189">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="d803a-190">fabricante del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="d803a-190">removable media device manufacturer</span></span>
- <span data-ttu-id="d803a-191">modelo del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="d803a-191">removable media device model</span></span>
- <span data-ttu-id="d803a-192">número de serie del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="d803a-192">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d803a-193">![copiar a los atributos de actividad del USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="d803a-193">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="d803a-194">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="d803a-194">Next steps</span></span>

<span data-ttu-id="d803a-195">Ahora que ya conoce DLP en punto de conexión, estos son los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d803a-195">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="d803a-196">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d803a-196">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="d803a-197">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d803a-197">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="d803a-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="d803a-198">See also</span></span>

- [<span data-ttu-id="d803a-199">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d803a-199">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="d803a-200">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d803a-200">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="d803a-201">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="d803a-201">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="d803a-202">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="d803a-202">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="d803a-203">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="d803a-203">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d803a-204">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d803a-204">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="d803a-205">Administración de riesgos internos</span><span class="sxs-lookup"><span data-stu-id="d803a-205">Insider Risk management</span></span>](insider-risk-management.md)
