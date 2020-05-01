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
description: Con la administración de registros de Microsoft 365, puede aplicar las programaciones de retención específicas de su organización en un plan de archivos para administrar la retención, la declaración de registros y la eliminación para dar soporte al ciclo de vida completo del contenido.
ms.openlocfilehash: e4454ba5940d9a67d9f160d90d0a9db14563bcf7
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949253"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="fb0b9-103">Administración de registros en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fb0b9-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="fb0b9-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="fb0b9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="fb0b9-105">Las organizaciones de todo tipo requieren una solución de administración de registros para administrar los registros reglamentarios, legales y críticos para el negocio en sus datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="fb0b9-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="fb0b9-106">La administración de registros de Microsoft 365 ayuda a las organizaciones a administrar sus obligaciones legales, ofrece la posibilidad de demostrar el cumplimiento de las normativas y aumenta la eficiencia con la eliminación regular de elementos que ya no es necesario retener, que no son de gran valor o que ya no son necesarios para fines empresariales.</span><span class="sxs-lookup"><span data-stu-id="fb0b9-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="fb0b9-107">La solución de administración de registros es compatible con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="fb0b9-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="fb0b9-108">**Etiquetar contenido como un registro**.</span><span class="sxs-lookup"><span data-stu-id="fb0b9-108">**Label content as a record**.</span></span> <span data-ttu-id="fb0b9-109">Cree y publique las etiquetas de retención que declaran el contenido como un [registro](records.md) que puede ser aplicado por los usuarios finales o [aplicado automáticamente](labels.md#applying-a-retention-label-automatically-based-on-conditions) mediante la identificación de información confidencial, palabras clave o tipos de contenido</span><span class="sxs-lookup"><span data-stu-id="fb0b9-109">Create and publish retention labels that declare content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="fb0b9-110">**Migrar y administrar su plan de retención con el plan de archivos** y usar el [administrador del plan de archivos](file-plan-manager.md) para incorporar su plan de retención existente, o crear uno nuevo con los descriptores de archivo y las jerarquías de expansión.</span><span class="sxs-lookup"><span data-stu-id="fb0b9-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="fb0b9-111">**Establecer directivas de retención y eliminación**.</span><span class="sxs-lookup"><span data-stu-id="fb0b9-111">**Establish retention and deletion policies**.</span></span> <span data-ttu-id="fb0b9-112">Definir períodos de [retención](retention-policies.md#retaining-content-for-a-specific-period-of-time) y [eliminación](retention-policies.md#deleting-content-thats-older-than-a-specific-age) en función de una serie de factores que incluyen la fecha de la última modificación o creación.</span><span class="sxs-lookup"><span data-stu-id="fb0b9-112">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="fb0b9-113">**Activar retención basada en eventos** con [retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="fb0b9-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="fb0b9-114">**Revisar y validar la eliminación** con [la revisión de eliminación](disposition.md#disposition-reviews) y la prueba de [eliminación de registros](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="fb0b9-114">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="fb0b9-115">**Exportar la información sobre todos los elementos que se han eliminado** con la [opción exportar](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="fb0b9-115">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="fb0b9-116">**Configurar permisos específicos** para las funciones del administrador de registros en su organización para [tener el acceso correcto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fb0b9-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="fb0b9-117">Con la solución de administración de registros de Microsoft 365, puede incorporar las programaciones de retención de su organización en el plan de archivos para administrar la retención, la declaración de registros y la eliminación para dar soporte a todo el ciclo de vida del contenido.</span><span class="sxs-lookup"><span data-stu-id="fb0b9-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>
