---
title: Introducción a la clasificación de los datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El panel de clasificación de datos le permite ver la cantidad de información confidencial que se ha encontrado y clasificado en la organización.
ms.openlocfilehash: 7bf9a7151f8df45716ab032dd3c62a33f4f5adc8
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999400"
---
# <a name="know-your-data---data-classification-overview"></a><span data-ttu-id="d800a-103">Información general sobre la clasificación de datos</span><span class="sxs-lookup"><span data-stu-id="d800a-103">Know your data - data classification overview</span></span>

<span data-ttu-id="d800a-104">Como administrador de Microsoft 365 o administrador de cumplimiento, puede evaluar y etiquetar el contenido de la organización para controlar el lugar al que se dirige, protegerlo sin importar su ubicación y garantizar que se conserve y elimine en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="d800a-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according to your organizations needs.</span></span> <span data-ttu-id="d800a-105">Para ello, puede aplicar [etiquetas de confidencialidad](sensitivity-labels.md) y [etiquetas de retención](retention.md#retention-labels) y clasificar la información según el tipo de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="d800a-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](retention.md#retention-labels), and sensitive information type classification.</span></span> <span data-ttu-id="d800a-106">Hay varias formas de llevar a cabo la detección, la evaluación y el etiquetado, pero es posible que el resultado final sea un gran número de documentos y mensajes de correo electrónico marcados y clasificados con una o ambas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="d800a-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large number of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="d800a-107">Después de aplicar las etiquetas de retención y de confidencialidad, le interesará ver cómo se utilizan las etiquetas en el espacio empresarial y qué se hace con esos elementos.</span><span class="sxs-lookup"><span data-stu-id="d800a-107">After you apply your retention labels and sensitivity labels, you'll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="d800a-108">La página de clasificación de datos ofrece información sobre ese contenido, en particular:</span><span class="sxs-lookup"><span data-stu-id="d800a-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="d800a-109">el número de elementos que se han clasificado como tipo de información sensible y cuáles son esas clasificaciones;</span><span class="sxs-lookup"><span data-stu-id="d800a-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="d800a-110">las etiquetas principales de confidencialidad aplicadas en Microsoft 365 y Azure Information Protection;</span><span class="sxs-lookup"><span data-stu-id="d800a-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="d800a-111">las etiquetas principales de retención aplicadas</span><span class="sxs-lookup"><span data-stu-id="d800a-111">the top applied retention labels</span></span>
- <span data-ttu-id="d800a-112">un resumen de las actividades que los usuarios llevan a cabo con el contenido confidencial;</span><span class="sxs-lookup"><span data-stu-id="d800a-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="d800a-113">las ubicaciones de los datos confidenciales y retenidos.</span><span class="sxs-lookup"><span data-stu-id="d800a-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="d800a-114">También puede administrar estas características en la página de clasificación de datos:</span><span class="sxs-lookup"><span data-stu-id="d800a-114">You also manage these features on the data classification page:</span></span>
- [<span data-ttu-id="d800a-115">clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="d800a-115">trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="d800a-116">tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="d800a-116">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)

<span data-ttu-id="d800a-117">Puede encontrar la clasificación de los datos en el **Centro de cumplimiento de Microsoft 365** o en el **Centro de seguridad de Microsoft 365** > **Clasificación** > **Clasificación de datos**.</span><span class="sxs-lookup"><span data-stu-id="d800a-117">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

<span data-ttu-id="d800a-118">Participe en un recorrido en vídeo de nuestras características de clasificación de datos.</span><span class="sxs-lookup"><span data-stu-id="d800a-118">Take a video tour of our data classification features.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

<span data-ttu-id="d800a-119">La clasificación de datos analizará su contenido confidencial y el contenido etiquetado antes de crear ninguna directiva.</span><span class="sxs-lookup"><span data-stu-id="d800a-119">Data classification will scan your sensitive content and labeled content before you create any policies.</span></span> <span data-ttu-id="d800a-120">Esto se denomina **administración de cambios de zero**.</span><span class="sxs-lookup"><span data-stu-id="d800a-120">This is called **zero change management**.</span></span> <span data-ttu-id="d800a-121">Esto le permite ver el impacto que las etiquetas de confidencialidad y retención están teniendo en su entorno para que pueda comenzar con la evaluación de sus necesidades de protección y directivas de gobernanza de datos.</span><span class="sxs-lookup"><span data-stu-id="d800a-121">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d800a-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d800a-122">Prerequisites</span></span>

<span data-ttu-id="d800a-123">Un numero de diferentes suscripciones admite punto de conexión DLP.</span><span class="sxs-lookup"><span data-stu-id="d800a-123">A number of different subscriptions support Endpoint DLP.</span></span> <span data-ttu-id="d800a-124">Para ver las opciones de licencia para el punto de conexión DLP, vea [Concesión de licencias de protección de la información para obtener instrucciones](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="d800a-124">To see licensing options for Endpoint DLP see [Information Protection licensing for guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span> 

### <a name="permissions"></a><span data-ttu-id="d800a-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="d800a-125">Permissions</span></span>

 <span data-ttu-id="d800a-126">Para obtener acceso a la página de clasificación de datos, una cuenta debe tener asignada una suscripción en cualquiera de estos roles o grupos de roles.</span><span class="sxs-lookup"><span data-stu-id="d800a-126">In order to get access to the data classification page, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="d800a-127">**Grupos de roles de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="d800a-127">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="d800a-128">Administrador global</span><span class="sxs-lookup"><span data-stu-id="d800a-128">Global administrator</span></span>
- <span data-ttu-id="d800a-129">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d800a-129">Compliance administrator</span></span>
- <span data-ttu-id="d800a-130">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="d800a-130">Security administrator</span></span>
- <span data-ttu-id="d800a-131">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d800a-131">Compliance data administrator</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="d800a-132">Tipos de información confidencial más usados en el contenido.</span><span class="sxs-lookup"><span data-stu-id="d800a-132">Sensitive information types used most in your content</span></span>

<span data-ttu-id="d800a-133">Microsoft 365 dispone de un gran número de definiciones de tipos de información confidencial, como, por ejemplo, para elementos que contengan números de la seguridad social o números de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="d800a-133">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="d800a-134">Para obtener más información sobre los tipos de información confidencial, consulte [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="d800a-134">For more information on sensitive information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="d800a-135">En la tarjeta del tipo de información confidencial se muestran los tipos de información confidencial principales que se han encontrado y etiquetado en la organización.</span><span class="sxs-lookup"><span data-stu-id="d800a-135">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![tipos principales de información confidencial](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="d800a-137">Para averiguar cuántos elementos hay en una categoría de clasificación determinada, mueva el puntero sobre la barra de la categoría.</span><span class="sxs-lookup"><span data-stu-id="d800a-137">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![detalle de los tipos principales de información confidencial](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="d800a-139">Si la tarjeta muestra el mensaje "No se ha encontrado ningún dato que contenga información confidencial".</span><span class="sxs-lookup"><span data-stu-id="d800a-139">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="d800a-140">Significa que no hay ningún elemento de la organización que se haya clasificado como un tipo de información confidencial o que no se ha rastreado ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="d800a-140">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="d800a-141">Para comenzar a usar las etiquetas, vea:</span><span class="sxs-lookup"><span data-stu-id="d800a-141">To get started with labels, see:</span></span>
>- [<span data-ttu-id="d800a-142">Introducción a las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="d800a-142">Get started with sensitivity labels</span></span>](get-started-with-sensitivity-labels.md)
>- [<span data-ttu-id="d800a-143">Introducción a las directivas de retención y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="d800a-143">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)
>- [<span data-ttu-id="d800a-144">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="d800a-144">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="d800a-145">Etiquetas principales de confidencialidad que se aplican al contenido</span><span class="sxs-lookup"><span data-stu-id="d800a-145">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="d800a-146">Al aplicar una etiqueta de confidencialidad a un elemento a través de Microsoft 365 o de Azure Information Protection (AIP), ocurren dos cosas:</span><span class="sxs-lookup"><span data-stu-id="d800a-146">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="d800a-147">se incrusta en el documento una etiqueta que indica el valor que tiene el elemento para la organización y que acompañará al documento a cualquier lugar al que vaya;</span><span class="sxs-lookup"><span data-stu-id="d800a-147">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="d800a-148">la presencia de la etiqueta habilita varios comportamientos de protección, como, por ejemplo, la marca de agua o el cifrado obligatorios.</span><span class="sxs-lookup"><span data-stu-id="d800a-148">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="d800a-149">Con la protección del punto de conexión habilitada, podrá incluso evitar que un elemento abandone el control de la organización.</span><span class="sxs-lookup"><span data-stu-id="d800a-149">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="d800a-150">Para obtener más información sobre las etiquetas de confidencialidad, vea: [Información general de etiquetas de confidencialidad](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="d800a-150">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="d800a-151">Las etiquetas de confidencialidad deben habilitarse para los archivos de SharePoint y OneDrive para que los datos correspondientes aparezcan en la página de clasificación de datos.</span><span class="sxs-lookup"><span data-stu-id="d800a-151">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="d800a-152">Para más información, vea [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="d800a-152">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="d800a-153">La tarjeta de la etiqueta de confidencialidad muestra el número de elementos (correo electrónico o documento) por nivel de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="d800a-153">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![captura de pantalla de marcador de posición del desglose del contenido según la clasificación de las etiquetas de confidencialidad](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="d800a-155">Si no ha creado ni publicado ninguna etiqueta de confidencialidad o si el contenido no tiene ninguna etiqueta de confidencialidad aplicada, esta tarjeta mostrará el mensaje "No se ha detectado ninguna etiqueta de confidencialidad".</span><span class="sxs-lookup"><span data-stu-id="d800a-155">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="d800a-156">Para empezar a usar las etiquetas de confidencialidad, consulte:</span><span class="sxs-lookup"><span data-stu-id="d800a-156">To get started with sensitivity labels, see:</span></span>
>- <span data-ttu-id="d800a-157">[Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) o, para AIP, [Configuración de la directiva de Information Protection de Azure](https://docs.microsoft.com/azure/information-protection/configure-policy)</span><span class="sxs-lookup"><span data-stu-id="d800a-157">[Get started with sensitivity labels](get-started-with-sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="d800a-158">Etiquetas principales de retención que se aplican al contenido</span><span class="sxs-lookup"><span data-stu-id="d800a-158">Top retention labels applied to content</span></span>

<span data-ttu-id="d800a-159">Las etiquetas de retención se usan para administrar la retención y la eliminación de contenido en la organización.</span><span class="sxs-lookup"><span data-stu-id="d800a-159">Retention labels are used to manage the retention and disposition of content in your organization.</span></span> <span data-ttu-id="d800a-160">Cuando se aplican, pueden usarse para controlar la forma en que se conservará un documento antes de eliminarlo, si debe revisarse antes de eliminarlo, cuándo expira su periodo de retención o si debe marcarse como un registro que no puede eliminarse nunca.</span><span class="sxs-lookup"><span data-stu-id="d800a-160">When applied, they can be used to control how an item will be kept before deletion, whether it should be reviewed prior to deletion, when its retention period expires, and whether it should be marked as a record.</span></span> <span data-ttu-id="d800a-161">Para obtener más información, consulte [Información sobre las etiquetas y directivas de retención](retention.md).</span><span class="sxs-lookup"><span data-stu-id="d800a-161">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="d800a-162">La tarjeta de etiquetas principales de retención aplicadas muestra el número de elementos que tienen una etiqueta de retención determinada.</span><span class="sxs-lookup"><span data-stu-id="d800a-162">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![captura de pantalla de marcador de posición de etiquetas principales de retención aplicadas](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="d800a-164">Si esta tarjeta muestra el mensaje "No se ha detectado ninguna etiqueta de retención", significa que no se ha creado ni publicado ninguna etiqueta de retención o que no hay ningún contenido con etiquetas de retención aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d800a-164">If this card displays the message, "No retention labels detected", it means you haven't created or published any retention labels or no content has had a retention label applied.</span></span> <span data-ttu-id="d800a-165">Para comenzar a usar las etiquetas de retención, vea:</span><span class="sxs-lookup"><span data-stu-id="d800a-165">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="d800a-166">Introducción a las directivas y etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="d800a-166">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)

## <a name="top-activities-detected"></a><span data-ttu-id="d800a-167">Actividades principales detectadas</span><span class="sxs-lookup"><span data-stu-id="d800a-167">Top activities detected</span></span>

<span data-ttu-id="d800a-168">Esta tarjeta ofrece un breve resumen de las acciones más comunes que llevan a cabo los usuarios con los elementos etiquetados como confidenciales.</span><span class="sxs-lookup"><span data-stu-id="d800a-168">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="d800a-169">Puede usar el [Explorador de actividad](data-classification-activity-explorer.md) para ver los detalles de las ocho diferentes actividades de las que Microsoft 365 realiza el seguimiento en el contenido etiquetado y en el contenido que se encuentra en los puntos de conexión de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d800a-169">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="d800a-170">Si esta tarjeta muestra el mensaje "No se ha detectado ninguna actividad", significa que no ha habido ninguna actividad en los archivos o que no está activada la auditoría de usuarios y administradores.</span><span class="sxs-lookup"><span data-stu-id="d800a-170">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="d800a-171">Para activar los registros de auditoría, vea:</span><span class="sxs-lookup"><span data-stu-id="d800a-171">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="d800a-172">Buscar el registro de auditoría en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d800a-172">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="d800a-173">Datos con etiquetas de confidencialidad y retención por ubicación</span><span class="sxs-lookup"><span data-stu-id="d800a-173">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="d800a-174">El informe de la clasificación de datos tiene la finalidad de ofrecer información sobre el número de elementos etiquetados y su ubicación.</span><span class="sxs-lookup"><span data-stu-id="d800a-174">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="d800a-175">Estas tarjetas le permiten saber cuántos elementos etiquetados hay en Exchange, SharePoint y OneDrive, entre otros.</span><span class="sxs-lookup"><span data-stu-id="d800a-175">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="d800a-176">Si esta tarjeta muestra el mensaje "No se ha detectado ninguna ubicación", significa que no se ha creado ni publicado ninguna etiqueta de confidencialidad o que no hay ningún contenido con una etiqueta de retención aplicada.</span><span class="sxs-lookup"><span data-stu-id="d800a-176">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="d800a-177">Para empezar a usar las etiquetas de confidencialidad, vea:</span><span class="sxs-lookup"><span data-stu-id="d800a-177">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="d800a-178">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="d800a-178">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="d800a-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="d800a-179">See also</span></span>

- [<span data-ttu-id="d800a-180">Ver actividad de la etiqueta</span><span class="sxs-lookup"><span data-stu-id="d800a-180">View label activity</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d800a-181">Ver contenido etiquetado</span><span class="sxs-lookup"><span data-stu-id="d800a-181">View labeled content</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="d800a-182">Más información sobre las etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="d800a-182">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="d800a-183">Más información sobre las directivas y las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="d800a-183">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="d800a-184">Definiciones de entidad de tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="d800a-184">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="d800a-185">Obtenga información sobre los clasificadores entrenables (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="d800a-185">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)