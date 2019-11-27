---
title: Introducción a la clasificación de los datos (vista previa)
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
search.appverid:
- MOE150
- MET150
description: El panel de clasificación de datos le permite ver la cantidad de información confidencial que se ha encontrado y clasificado en la organización.
ms.openlocfilehash: cb728c4e6a88fc7bb47716a40addd01f9828208f
ms.sourcegitcommit: 9206e7f2d61b5ba7f788fe5e7f75a2218c12c716
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "39622632"
---
# <a name="data-classification-overview-preview"></a><span data-ttu-id="bc890-103">Información general sobre la clasificación de datos (vista previa)</span><span class="sxs-lookup"><span data-stu-id="bc890-103">Data classification overview (preview)</span></span>

<span data-ttu-id="bc890-104">Como administrador de Microsoft 365 o administrador de cumplimiento, puede evaluar y etiquetar el contenido de la organización para controlar el lugar al que se dirige, protegerla sea cual sea su ubicación y garantizar que se conserve y elimine en función de las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="bc890-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according your your organizations needs.</span></span> <span data-ttu-id="bc890-105">Para ello, puede aplicar [etiquetas de confidencialidad](sensitivity-labels.md) y [etiquetas de retención](labels.md) y clasificar la información según el tipo de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="bc890-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](labels.md), and sensitive information type classification.</span></span> <span data-ttu-id="bc890-106">Hay varias formas de llevar a cabo la detección, la evaluación y el etiquetado, pero es posible que el resultado final sea un gran número de documentos y mensajes de correo electrónico marcados y clasificados con una o ambas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="bc890-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large numbers of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="bc890-107">Después de aplicar las etiquetas de retención y de confidencialidad, le interesará ver cómo se utilizan las etiquetas en el espacio empresarial y qué se hace con esos elementos.</span><span class="sxs-lookup"><span data-stu-id="bc890-107">After you apply  your retention labels and sensitivity labels, you’ll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="bc890-108">La página de clasificación de datos ofrece información sobre ese contenido, en particular:</span><span class="sxs-lookup"><span data-stu-id="bc890-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="bc890-109">el número de elementos que se han clasificado como tipo de información sensible y cuáles son esas clasificaciones;</span><span class="sxs-lookup"><span data-stu-id="bc890-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="bc890-110">las etiquetas principales de confidencialidad aplicadas en Microsoft 365 y Azure Information Protection;</span><span class="sxs-lookup"><span data-stu-id="bc890-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="bc890-111">las etiquetas principales de retención aplicadas</span><span class="sxs-lookup"><span data-stu-id="bc890-111">the top applied retention labels</span></span>
- <span data-ttu-id="bc890-112">un resumen de las actividades que los usuarios llevan a cabo con el contenido confidencial;</span><span class="sxs-lookup"><span data-stu-id="bc890-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="bc890-113">las ubicaciones de los datos confidenciales y retenidos.</span><span class="sxs-lookup"><span data-stu-id="bc890-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="bc890-114">Puede encontrar la clasificación de los datos en el **Centro de cumplimiento de Microsoft 365** o en el **Centro de seguridad de Microsoft 365** > **Clasificación** > **Clasificación de datos**.</span><span class="sxs-lookup"><span data-stu-id="bc890-114">You can find label analytics in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Label analytics**.</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="bc890-115">Tipos de información confidencial más usados en el contenido.</span><span class="sxs-lookup"><span data-stu-id="bc890-115">Sensitive information types used most in your content</span></span>

<span data-ttu-id="bc890-116">Microsoft 365 dispone de un gran número de definiciones de tipos de información confidencial, como, por ejemplo, para elementos que contengan números de la seguridad social o números de tarjetas de crédito.</span><span class="sxs-lookup"><span data-stu-id="bc890-116">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="bc890-117">Para obtener más información sobre los tipos de información confidencial, vea [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="bc890-117">For more information on sensitive information types, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="bc890-118">En la tarjeta del tipo de información confidencial se muestran los tipos de información confidencial principales que se han encontrado y etiquetado en la organización.</span><span class="sxs-lookup"><span data-stu-id="bc890-118">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![tipos principales de información confidencial](media/data-classification-sens-info-types-card.png)

<span data-ttu-id="bc890-120">Para averiguar cuántos elementos hay en una categoría de clasificación determinada, mueva el puntero sobre la barra de la categoría.</span><span class="sxs-lookup"><span data-stu-id="bc890-120">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![detalle de los tipos principales de información confidencial](media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="bc890-122">Si la tarjeta muestra el mensaje "No se ha encontrado ningún dato que contenga información confidencial".</span><span class="sxs-lookup"><span data-stu-id="bc890-122">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="bc890-123">Significa que no hay ningún elemento de la organización que se haya clasificado como un tipo de información confidencial o que no se ha rastreado ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="bc890-123">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="bc890-124">Para comenzar a usar las etiquetas, vea:</span><span class="sxs-lookup"><span data-stu-id="bc890-124">To get started with Windows PowerShell, see these topics:</span></span>
>- [<span data-ttu-id="bc890-125">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="bc890-125">Sensitivity labels</span></span>](sensitivity-labels.md)
>- [<span data-ttu-id="bc890-126">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="bc890-126">Retention labels</span></span>](labels.md)
>- [<span data-ttu-id="bc890-127">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="bc890-127">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="bc890-128">Etiquetas principales de confidencialidad que se aplican al contenido</span><span class="sxs-lookup"><span data-stu-id="bc890-128">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="bc890-129">Al aplicar una etiqueta de confidencialidad a un elemento a través de Microsoft 365 o de Azure Information Protection (AIP), ocurren dos cosas:</span><span class="sxs-lookup"><span data-stu-id="bc890-129">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="bc890-130">se incrusta en el documento una etiqueta que indica el valor que tiene el elemento para la organización y que acompañará al documento a cualquier lugar al que vaya;</span><span class="sxs-lookup"><span data-stu-id="bc890-130">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="bc890-131">la presencia de la etiqueta habilita varios comportamientos de protección, como, por ejemplo, la marca de agua o el cifrado obligatorios.</span><span class="sxs-lookup"><span data-stu-id="bc890-131">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="bc890-132">Con la protección del punto de conexión habilitada, podrá incluso evitar que un elemento abandone el control de la organización.</span><span class="sxs-lookup"><span data-stu-id="bc890-132">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="bc890-133">Para obtener más información sobre las etiquetas de confidencialidad, vea [Información general de etiquetas de retención](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="bc890-133">For more information, see [Overview of sensitivity labels](sensitivity-labels.md).</span></span>

<span data-ttu-id="bc890-134">La tarjeta de la etiqueta de confidencialidad muestra el número de elementos (correo electrónico o documento) por nivel de confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="bc890-134">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![captura de pantalla de marcador de posición del desglose del contenido según la clasificación de las etiquetas de confidencialidad](media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="bc890-136">Si no ha creado ni publicado ninguna etiqueta de confidencialidad o si el contenido no tiene ninguna etiqueta de confidencialidad aplicada, esta tarjeta mostrará el mensaje "No se ha detectado ninguna etiqueta de confidencialidad".</span><span class="sxs-lookup"><span data-stu-id="bc890-136">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="bc890-137">Para comenzar a usar las etiquetas, vea:</span><span class="sxs-lookup"><span data-stu-id="bc890-137">To get started with Windows PowerShell, see these topics:</span></span>
>- <span data-ttu-id="bc890-138">[etiquetas de confidencialidad](sensitivity-labels.md) o, para AIP, [Configuración de la directiva de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy)</span><span class="sxs-lookup"><span data-stu-id="bc890-138">[sensitivity labels](sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="bc890-139">Etiquetas principales de retención que se aplican al contenido</span><span class="sxs-lookup"><span data-stu-id="bc890-139">Top retention labels applied to content</span></span>

<span data-ttu-id="bc890-140">Las etiquetas de retención se usan para administrar la eliminación de contenido en la organización.</span><span class="sxs-lookup"><span data-stu-id="bc890-140">Retention labels are used to manage the disposition of content in your organization.</span></span> <span data-ttu-id="bc890-141">Cuando se aplican, pueden usarse para controlar cuánto tiempo se conservará un documento antes de eliminarlo una vez que expire el período de retención, independientemente de si debe revisarse antes de eliminarlo, o si debe marcarse como un registro que no puede eliminarse nunca.</span><span class="sxs-lookup"><span data-stu-id="bc890-141">When applied, they can be used to control how long a document will be kept before deletion, whether it should be reviewed prior to deletion, when it's retention period expires, or whether it should be marked as a record which can never be deleted.</span></span> <span data-ttu-id="bc890-142">Para obtener más información, vea [Introducción a las etiquetas de retención](labels.md).</span><span class="sxs-lookup"><span data-stu-id="bc890-142">For more information about labels, see [Overview of retention labels](labels.md).</span></span>

<span data-ttu-id="bc890-143">La tarjeta de etiquetas principales de retención aplicadas muestra el número de elementos que tienen una etiqueta de retención determinada.</span><span class="sxs-lookup"><span data-stu-id="bc890-143">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![captura de pantalla de marcador de posición de etiquetas principales de retención aplicadas](media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="bc890-145">Si esta tarjeta muestra el mensaje "No se ha detectado ninguna etiqueta de retención", significa que no se ha creado ni publicado ninguna etiqueta de retención o que no hay ningún contenido con una etiqueta de retención aplicada.</span><span class="sxs-lookup"><span data-stu-id="bc890-145">If this card displays the message, "No retention labels detected, it means you haven't created or published any retention  labels or no content has had a retention label applied.</span></span> <span data-ttu-id="bc890-146">Para comenzar a usar las etiquetas de retención, vea:</span><span class="sxs-lookup"><span data-stu-id="bc890-146">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="bc890-147">Introducción a las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="bc890-147">Overview of retention labels</span></span>](labels.md)

## <a name="top-activities-detected"></a><span data-ttu-id="bc890-148">Actividades principales detectadas</span><span class="sxs-lookup"><span data-stu-id="bc890-148">Top activities detected</span></span>

<span data-ttu-id="bc890-149">Esta tarjeta ofrece un breve resumen de las acciones más comunes que llevan a cabo los usuarios con los elementos etiquetados como confidenciales.</span><span class="sxs-lookup"><span data-stu-id="bc890-149">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="bc890-150">Puede usar el [Explorador de actividad](data-classification-activity-explorer.md) para ver los detalles de las ocho diferentes actividades de las que Microsoft 365 realiza el seguimiento en el contenido etiquetado y en el contenido que se encuentra en los puntos de conexión de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bc890-150">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="bc890-151">Si esta tarjeta muestra el mensaje "No se ha detectado ninguna actividad", significa que no ha habido ninguna actividad en los archivos o que no está activada la auditoría de usuarios y administradores.</span><span class="sxs-lookup"><span data-stu-id="bc890-151">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="bc890-152">Para activar los registros de auditoría, vea:</span><span class="sxs-lookup"><span data-stu-id="bc890-152">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="bc890-153">Buscar el registro de auditoría en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="bc890-153">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="bc890-154">Datos con etiquetas de confidencialidad y retención por ubicación</span><span class="sxs-lookup"><span data-stu-id="bc890-154">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="bc890-155">El informe de la clasificación de datos tiene la finalidad de ofrecer información sobre el número de elementos etiquetados y su ubicación.</span><span class="sxs-lookup"><span data-stu-id="bc890-155">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="bc890-156">Estas tarjetas le permiten saber cuántos elementos etiquetados hay en Exchange, SharePoint y OneDrive, entre otros.</span><span class="sxs-lookup"><span data-stu-id="bc890-156">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="bc890-157">Si esta tarjeta muestra el mensaje "No se ha detectado ninguna ubicación", significa que no se ha creado ni publicado ninguna etiqueta de confidencialidad o que no hay ningún contenido con una etiqueta de retención aplicada.</span><span class="sxs-lookup"><span data-stu-id="bc890-157">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="bc890-158">Para empezar a usar las etiquetas de confidencialidad, vea:</span><span class="sxs-lookup"><span data-stu-id="bc890-158">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="bc890-159">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="bc890-159">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="bc890-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc890-160">See also</span></span>

- [<span data-ttu-id="bc890-161">Ver actividad de la etiqueta (vista previa)</span><span class="sxs-lookup"><span data-stu-id="bc890-161">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="bc890-162">Ver contenido etiquetado (vista previa)</span><span class="sxs-lookup"><span data-stu-id="bc890-162">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="bc890-163">Etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="bc890-163">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="bc890-164">Etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="bc890-164">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="bc890-165">Qué buscan los tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="bc890-165">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="bc890-166">Información general sobre las directivas de retención</span><span class="sxs-lookup"><span data-stu-id="bc890-166">Overview of retention policies</span></span>](retention-policies.md)
