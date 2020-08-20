---
title: Administración de registros
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Con la administración de registros de Microsoft 365, puede aplicar programaciones de retención en un plan de archivos para administrar la retención, la declaración de registros y la eliminación.
ms.openlocfilehash: c2ff344d22286fcd865aa08344389dad6334d48d
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778328"
---
# <a name="learn-about-records-management"></a><span data-ttu-id="2ec10-103">Más información sobre la administración de registros</span><span class="sxs-lookup"><span data-stu-id="2ec10-103">Learn about records management</span></span>

><span data-ttu-id="2ec10-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="2ec10-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="2ec10-105">Las organizaciones de todo tipo requieren una solución de administración de registros para administrar los registros reglamentarios, legales y críticos para el negocio en sus datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="2ec10-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="2ec10-106">La administración de registros de Microsoft 365 ayuda a las organizaciones a administrar sus obligaciones legales, ofrece la posibilidad de demostrar el cumplimiento de las normativas y aumenta la eficiencia con la eliminación regular de elementos que ya no es necesario retener, que no son de gran valor o que ya no son necesarios para fines empresariales.</span><span class="sxs-lookup"><span data-stu-id="2ec10-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="2ec10-107">Use las siguientes funciones para dar soporte a la solución de administración de registros en Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="2ec10-107">Use the following capabilities to support your records management solution in Microsoft 365:</span></span>

- <span data-ttu-id="2ec10-108">**Etiquetar contenido como un registro**.</span><span class="sxs-lookup"><span data-stu-id="2ec10-108">**Label content as a record**.</span></span> <span data-ttu-id="2ec10-109">Cree y configure etiquetas de retención para marcar el contenido como un [registro](#records) que pueden ser aplicadas por los usuarios o aplicadas automáticamente al identificar palabras clave, tipos de contenido o información confidencial.</span><span class="sxs-lookup"><span data-stu-id="2ec10-109">Create and configure retention labels to mark content as a [record](#records) that can then be applied by users or automatically applied by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="2ec10-110">**Migrar y administrar los requisitos de retención con el plan de archivos**.</span><span class="sxs-lookup"><span data-stu-id="2ec10-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="2ec10-111">Si usa un [plan de archivo](file-plan-manager.md), puede agregar un plan de retención existente a Microsoft 365 o crear uno nuevo para las funciones de administración mejoradas.</span><span class="sxs-lookup"><span data-stu-id="2ec10-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="2ec10-112">**Configure las opciones de retención y eliminación con etiquetas de retención**.</span><span class="sxs-lookup"><span data-stu-id="2ec10-112">**Configure retention and deletion settings with retention labels**.</span></span> <span data-ttu-id="2ec10-113">Configure [etiquetas de retención](retention.md#retention-labels) con los períodos de retención y las acciones en función de varios factores que incluyan la fecha de la última modificación o creación.</span><span class="sxs-lookup"><span data-stu-id="2ec10-113">Configure [retention labels](retention.md#retention-labels) with the retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="2ec10-114">**Inicie diferentes períodos de retención cuando se produzca un evento** con la [retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="2ec10-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="2ec10-115">**Revisar y validar la eliminación** con [la revisión de eliminación](disposition.md#disposition-reviews) y la prueba de [eliminación de registros](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="2ec10-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="2ec10-116">**Exportar la información sobre todos los elementos que se han eliminado** con la [opción exportar](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="2ec10-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="2ec10-117">**Configurar permisos específicos** para las funciones del administrador de registros en su organización para [tener el acceso correcto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2ec10-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="2ec10-118">Con estas funciones, puede incorporar los requisitos y las programaciones de retención de su organización en una solución de administración de registros para administrar la retención, la declaración de registros y la eliminación para dar soporte a todo el ciclo de vida del contenido.</span><span class="sxs-lookup"><span data-stu-id="2ec10-118">Using these capabilities, you can incorporate your organization's retention schedules and requirements into a records management solution that manages retention, records declaration, and disposition, to support the full lifecycle of your content.</span></span>

<span data-ttu-id="2ec10-119">Además de la documentación en línea, es posible que le resulte útil escuchar la [grabación del seminario web](https://aka.ms/MIPC/Video-RecordsManagementWebinar) para la administración de registros y descargar la [presentación acompañante con preguntas más frecuentes](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span><span class="sxs-lookup"><span data-stu-id="2ec10-119">In addition to the online documentation, you might find it useful to listen to the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) for records management, and download the accompanying [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).</span></span>

## <a name="records"></a><span data-ttu-id="2ec10-120">Registros</span><span class="sxs-lookup"><span data-stu-id="2ec10-120">Records</span></span>

<span data-ttu-id="2ec10-121">Cuando el contenido está marcado como un registro:</span><span class="sxs-lookup"><span data-stu-id="2ec10-121">When content is marked as a record:</span></span>

- <span data-ttu-id="2ec10-122">Se colocan restricciones en los elementos relativas a qué [acciones se permiten o se bloquean](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="2ec10-122">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="2ec10-123">Se registran otras actividades sobre el elemento.</span><span class="sxs-lookup"><span data-stu-id="2ec10-123">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="2ec10-124">Tendrá la prueba de la eliminación cuando se eliminen los elementos al final de su período de retención.</span><span class="sxs-lookup"><span data-stu-id="2ec10-124">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="2ec10-125">Puede usar las [etiquetas de retención](retention.md#retention-labels) para marcar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="2ec10-125">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="2ec10-126">Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.</span><span class="sxs-lookup"><span data-stu-id="2ec10-126">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="2ec10-127">Al usar las etiquetas de retención para marcar contenido como registros, puede implementar una sola estrategia de administración de registros uniforme en todo el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ec10-127">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="2ec10-128">Comparar restricciones de acciones permitidas o bloqueadas</span><span class="sxs-lookup"><span data-stu-id="2ec10-128">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="2ec10-129">Use la tabla siguiente para identificar qué restricciones se colocan en el contenido como resultado de aplicar una etiqueta de retención estándar y conocer las etiquetas de retención que marcan el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="2ec10-129">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="2ec10-130">Una etiqueta de retención estándar tiene opciones de retención y acciones, pero no marca el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="2ec10-130">A standard retention label has retention settings and actions but doesn't mark content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="2ec10-131">Por motivos de integridad, la tabla contiene columnas para un registro bloqueado y desbloqueado, lo que se aplica a SharePoint y OneDrive, pero no a Exchange.</span><span class="sxs-lookup"><span data-stu-id="2ec10-131">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="2ec10-132">La capacidad de bloquear y desbloquear un registro usa el [control de versiones de registros](record-versioning.md) que no es compatible con los elementos de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2ec10-132">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="2ec10-133">Por lo tanto, para todos los elementos de Exchange que estén marcados como un registro, el comportamiento que se asigna a la columna **registro bloqueado** y a la columna **registro desbloqueado** no es relevante.</span><span class="sxs-lookup"><span data-stu-id="2ec10-133">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="2ec10-134">Acción</span><span class="sxs-lookup"><span data-stu-id="2ec10-134">Action</span></span>| <span data-ttu-id="2ec10-135">Etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="2ec10-135">Retention label</span></span> |<span data-ttu-id="2ec10-136">Registro: bloqueado</span><span class="sxs-lookup"><span data-stu-id="2ec10-136">Record - locked</span></span>| <span data-ttu-id="2ec10-137">Registro: desbloqueado</span><span class="sxs-lookup"><span data-stu-id="2ec10-137">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ec10-138">Editar contenidos</span><span class="sxs-lookup"><span data-stu-id="2ec10-138">Edit contents</span></span>|<span data-ttu-id="2ec10-139">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-139">Allowed</span></span> | <span data-ttu-id="2ec10-140">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="2ec10-140">**Blocked**</span></span> | <span data-ttu-id="2ec10-141">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-141">Allowed</span></span>|
|<span data-ttu-id="2ec10-142">Editar propiedades, incluido cambiar nombre</span><span class="sxs-lookup"><span data-stu-id="2ec10-142">Edit properties, including rename</span></span>|<span data-ttu-id="2ec10-143">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-143">Allowed</span></span> |<span data-ttu-id="2ec10-144">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-144">Allowed</span></span> | <span data-ttu-id="2ec10-145">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-145">Allowed</span></span>|
|<span data-ttu-id="2ec10-146">Eliminar</span><span class="sxs-lookup"><span data-stu-id="2ec10-146">Delete</span></span>|<span data-ttu-id="2ec10-147">Permitido<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2ec10-147">Allowed <sup>1</sup></span></span> |<span data-ttu-id="2ec10-148">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="2ec10-148">**Blocked**</span></span> | <span data-ttu-id="2ec10-149">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="2ec10-149">**Blocked**</span></span>|
|<span data-ttu-id="2ec10-150">Copiar</span><span class="sxs-lookup"><span data-stu-id="2ec10-150">Copy</span></span>|<span data-ttu-id="2ec10-151">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-151">Allowed</span></span> |<span data-ttu-id="2ec10-152">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-152">Allowed</span></span> | <span data-ttu-id="2ec10-153">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-153">Allowed</span></span>|
|<span data-ttu-id="2ec10-154">Moverse dentro del contenedor<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2ec10-154">Move within container <sup>2</sup></span></span>|<span data-ttu-id="2ec10-155">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-155">Allowed</span></span> |<span data-ttu-id="2ec10-156">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-156">Allowed</span></span> | <span data-ttu-id="2ec10-157">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-157">Allowed</span></span>|
|<span data-ttu-id="2ec10-158">Moverse entre contenedores<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2ec10-158">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="2ec10-159">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-159">Allowed</span></span> |<span data-ttu-id="2ec10-160">Permitido si nunca se desbloquea</span><span class="sxs-lookup"><span data-stu-id="2ec10-160">Allowed if never unlocked</span></span> | <span data-ttu-id="2ec10-161">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-161">Allowed</span></span>|
|<span data-ttu-id="2ec10-162">Abrir y leer</span><span class="sxs-lookup"><span data-stu-id="2ec10-162">Open/Read</span></span>|<span data-ttu-id="2ec10-163">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-163">Allowed</span></span> |<span data-ttu-id="2ec10-164">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-164">Allowed</span></span> | <span data-ttu-id="2ec10-165">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-165">Allowed</span></span>|
|<span data-ttu-id="2ec10-166">Cambiar etiqueta</span><span class="sxs-lookup"><span data-stu-id="2ec10-166">Change label</span></span>|<span data-ttu-id="2ec10-167">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-167">Allowed</span></span> |<span data-ttu-id="2ec10-168">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="2ec10-168">Allowed - container admin only</span></span> | <span data-ttu-id="2ec10-169">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="2ec10-169">Allowed - container admin only</span></span>|
|<span data-ttu-id="2ec10-170">Quitar etiqueta</span><span class="sxs-lookup"><span data-stu-id="2ec10-170">Remove label</span></span>|<span data-ttu-id="2ec10-171">Permitido</span><span class="sxs-lookup"><span data-stu-id="2ec10-171">Allowed</span></span> |<span data-ttu-id="2ec10-172">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="2ec10-172">Allowed - container admin only</span></span> | <span data-ttu-id="2ec10-173">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="2ec10-173">Allowed - container admin only</span></span>|

<span data-ttu-id="2ec10-174">Notas al pie:</span><span class="sxs-lookup"><span data-stu-id="2ec10-174">Footnotes:</span></span>

<span data-ttu-id="2ec10-175"><sup>1</sup> Compatible con OneDrive y Exchange reteniendo una copia en una ubicación segura, pero bloqueado por SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2ec10-175"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="2ec10-176">Mensaje que ve el usuario si intenta eliminar un documento con etiquetas en SharePoint:</span><span class="sxs-lookup"><span data-stu-id="2ec10-176">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Mensaje que indica que el elemento no se elimina de SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="2ec10-178"><sup>2</sup> Los contenedores incluyen librerías de documentos de SharePoint y buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="2ec10-178"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2ec10-179">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2ec10-179">Next steps</span></span>

<span data-ttu-id="2ec10-180">Consulte [Introducción a la administración de registros](get-started-with-records-management.md).</span><span class="sxs-lookup"><span data-stu-id="2ec10-180">See [Get started with records management](get-started-with-records-management.md).</span></span>

<span data-ttu-id="2ec10-181">Para marcar el contenido como un registro, vea [Declarar registros con las etiquetas de retención](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="2ec10-181">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
