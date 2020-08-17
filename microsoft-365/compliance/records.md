---
title: Obtenga más información sobre los registros
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtenga información acerca de los registros para que pueda implementar la solución de administración de registros de Microsoft 365.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685446"
---
# <a name="learn-about-records"></a><span data-ttu-id="170e7-103">Obtenga más información sobre los registros</span><span class="sxs-lookup"><span data-stu-id="170e7-103">Learn about records</span></span>

><span data-ttu-id="170e7-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="170e7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="170e7-105">La administración de registros de Microsoft 365 ayuda a su organización a cumplir con las directivas corporativas y las obligaciones legales o reglamentarias, al mismo tiempo que reduce el riesgo y la responsabilidad legal.</span><span class="sxs-lookup"><span data-stu-id="170e7-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="170e7-106">Cuando el contenido está marcado como un registro:</span><span class="sxs-lookup"><span data-stu-id="170e7-106">When content is marked as a record:</span></span>

- <span data-ttu-id="170e7-107">Se colocan restricciones en los elementos relativas a qué [acciones se permiten o se bloquean](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="170e7-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="170e7-108">Se registran otras actividades sobre el elemento.</span><span class="sxs-lookup"><span data-stu-id="170e7-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="170e7-109">Tendrá la prueba de la eliminación cuando se eliminen los elementos al final de su período de retención.</span><span class="sxs-lookup"><span data-stu-id="170e7-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="170e7-110">Puede usar las [etiquetas de retención](retention.md#retention-labels) para marcar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="170e7-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="170e7-111">Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.</span><span class="sxs-lookup"><span data-stu-id="170e7-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="170e7-112">Al usar las etiquetas de retención para marcar contenido como registros, puede implementar una sola estrategia de administración de registros uniforme en todo el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="170e7-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="170e7-113">Comparar restricciones de acciones permitidas o bloqueadas</span><span class="sxs-lookup"><span data-stu-id="170e7-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="170e7-114">Use la tabla siguiente para identificar qué restricciones se colocan en el contenido como resultado de aplicar una etiqueta de retención estándar y conocer las etiquetas de retención que marcan el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="170e7-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="170e7-115">Una etiqueta de retención estándar tiene la configuración para conservar datos sin marcar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="170e7-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="170e7-116">Por motivos de integridad, la tabla contiene columnas para un registro bloqueado y desbloqueado, lo que se aplica a SharePoint y OneDrive, pero no a Exchange.</span><span class="sxs-lookup"><span data-stu-id="170e7-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="170e7-117">La capacidad de bloquear y desbloquear un registro usa el [control de versiones de registros](record-versioning.md) que no es compatible con los elementos de Exchange.</span><span class="sxs-lookup"><span data-stu-id="170e7-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="170e7-118">Por lo tanto, para todos los elementos de Exchange que estén marcados como un registro, el comportamiento que se asigna a la columna **registro bloqueado** y a la columna **registro desbloqueado** no es relevante.</span><span class="sxs-lookup"><span data-stu-id="170e7-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="170e7-119">Acción</span><span class="sxs-lookup"><span data-stu-id="170e7-119">Action</span></span>| <span data-ttu-id="170e7-120">Etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="170e7-120">Retention label</span></span> |<span data-ttu-id="170e7-121">Registro: bloqueado</span><span class="sxs-lookup"><span data-stu-id="170e7-121">Record - locked</span></span>| <span data-ttu-id="170e7-122">Registro: desbloqueado</span><span class="sxs-lookup"><span data-stu-id="170e7-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="170e7-123">Editar contenidos</span><span class="sxs-lookup"><span data-stu-id="170e7-123">Edit contents</span></span>|<span data-ttu-id="170e7-124">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-124">Allowed</span></span> | <span data-ttu-id="170e7-125">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="170e7-125">**Blocked**</span></span> | <span data-ttu-id="170e7-126">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-126">Allowed</span></span>|
|<span data-ttu-id="170e7-127">Editar propiedades, incluido cambiar nombre</span><span class="sxs-lookup"><span data-stu-id="170e7-127">Edit properties, including rename</span></span>|<span data-ttu-id="170e7-128">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-128">Allowed</span></span> |<span data-ttu-id="170e7-129">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-129">Allowed</span></span> | <span data-ttu-id="170e7-130">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-130">Allowed</span></span>|
|<span data-ttu-id="170e7-131">Eliminar</span><span class="sxs-lookup"><span data-stu-id="170e7-131">Delete</span></span>|<span data-ttu-id="170e7-132">Permitido<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="170e7-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="170e7-133">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="170e7-133">**Blocked**</span></span> | <span data-ttu-id="170e7-134">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="170e7-134">**Blocked**</span></span>|
|<span data-ttu-id="170e7-135">Copiar</span><span class="sxs-lookup"><span data-stu-id="170e7-135">Copy</span></span>|<span data-ttu-id="170e7-136">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-136">Allowed</span></span> |<span data-ttu-id="170e7-137">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-137">Allowed</span></span> | <span data-ttu-id="170e7-138">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-138">Allowed</span></span>|
|<span data-ttu-id="170e7-139">Moverse dentro del contenedor<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="170e7-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="170e7-140">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-140">Allowed</span></span> |<span data-ttu-id="170e7-141">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-141">Allowed</span></span> | <span data-ttu-id="170e7-142">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-142">Allowed</span></span>|
|<span data-ttu-id="170e7-143">Moverse entre contenedores<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="170e7-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="170e7-144">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-144">Allowed</span></span> |<span data-ttu-id="170e7-145">Permitido si nunca se desbloquea</span><span class="sxs-lookup"><span data-stu-id="170e7-145">Allowed if never unlocked</span></span> | <span data-ttu-id="170e7-146">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-146">Allowed</span></span>|
|<span data-ttu-id="170e7-147">Abrir y leer</span><span class="sxs-lookup"><span data-stu-id="170e7-147">Open/Read</span></span>|<span data-ttu-id="170e7-148">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-148">Allowed</span></span> |<span data-ttu-id="170e7-149">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-149">Allowed</span></span> | <span data-ttu-id="170e7-150">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-150">Allowed</span></span>|
|<span data-ttu-id="170e7-151">Cambiar etiqueta</span><span class="sxs-lookup"><span data-stu-id="170e7-151">Change label</span></span>|<span data-ttu-id="170e7-152">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-152">Allowed</span></span> |<span data-ttu-id="170e7-153">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="170e7-153">Allowed - container admin only</span></span> | <span data-ttu-id="170e7-154">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="170e7-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="170e7-155">Quitar etiqueta</span><span class="sxs-lookup"><span data-stu-id="170e7-155">Remove label</span></span>|<span data-ttu-id="170e7-156">Permitido</span><span class="sxs-lookup"><span data-stu-id="170e7-156">Allowed</span></span> |<span data-ttu-id="170e7-157">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="170e7-157">Allowed - container admin only</span></span> | <span data-ttu-id="170e7-158">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="170e7-158">Allowed - container admin only</span></span>|

<span data-ttu-id="170e7-159">Notas al pie:</span><span class="sxs-lookup"><span data-stu-id="170e7-159">Footnotes:</span></span>

<span data-ttu-id="170e7-160"><sup>1</sup> Compatible con OneDrive y Exchange reteniendo una copia en una ubicación segura, pero bloqueado por SharePoint.</span><span class="sxs-lookup"><span data-stu-id="170e7-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="170e7-161">Mensaje que ve el usuario si intenta eliminar un documento con etiquetas en SharePoint:</span><span class="sxs-lookup"><span data-stu-id="170e7-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Mensaje que indica que el elemento no se elimina de SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="170e7-163"><sup>2</sup> Los contenedores incluyen librerías de documentos de SharePoint y buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="170e7-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="170e7-164">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="170e7-164">Next steps</span></span>

<span data-ttu-id="170e7-165">Si aún no tiene etiquetas de retención que se usarán para la administración de registros, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="170e7-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="170e7-166">Para marcar el contenido como un registro, vea [Declarar registros con las etiquetas de retención](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="170e7-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
