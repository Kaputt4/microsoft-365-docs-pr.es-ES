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
ms.openlocfilehash: 0179f208f10921293c164516b26440f5bd043517
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127487"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="93372-103">Administración de registros en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="93372-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="93372-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="93372-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="93372-105">Las organizaciones de todo tipo requieren una solución de administración de registros para administrar los registros reglamentarios, legales y críticos para el negocio en sus datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="93372-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="93372-106">La administración de registros de Microsoft 365 ayuda a las organizaciones a administrar sus obligaciones legales, ofrece la posibilidad de demostrar el cumplimiento de las normativas y aumenta la eficiencia con la eliminación regular de elementos que ya no es necesario retener, que no son de gran valor o que ya no son necesarios para fines empresariales.</span><span class="sxs-lookup"><span data-stu-id="93372-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="93372-107">La administración de registros de Microsoft 365 ofrece las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="93372-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="93372-108">**Etiquetar contenido como un registro**.</span><span class="sxs-lookup"><span data-stu-id="93372-108">**Label content as a record**.</span></span> <span data-ttu-id="93372-109">Cree y publique las etiquetas de retención que marcan el contenido como un [registro](records.md) que puede ser aplicado por los usuarios finales o [aplicado automáticamente](apply-retention-labels-automatically.md) mediante la identificación de información confidencial, palabras clave o tipos de contenido</span><span class="sxs-lookup"><span data-stu-id="93372-109">Create and publish retention labels that mark content as a [record](records.md) that can then be applied by end users or [auto-applied](apply-retention-labels-automatically.md) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="93372-110">**Migrar y administrar los requisitos de retención con el plan de archivos**.</span><span class="sxs-lookup"><span data-stu-id="93372-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="93372-111">Si usa un [plan de archivo](file-plan-manager.md), puede agregar un plan de retención existente a Microsoft 365 o crear uno nuevo para las funciones de administración mejoradas.</span><span class="sxs-lookup"><span data-stu-id="93372-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="93372-112">**Configure las opciones de retención y eliminación con la etiqueta de retención**.</span><span class="sxs-lookup"><span data-stu-id="93372-112">**Configure retention and deletion settings with the retention label**.</span></span> <span data-ttu-id="93372-113">Defina períodos de retención y acciones en función de una serie de factores que incluyen la fecha de la última modificación o creación.</span><span class="sxs-lookup"><span data-stu-id="93372-113">Define retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="93372-114">**Activar retención basada en eventos** con [retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="93372-114">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="93372-115">**Revisar y validar la eliminación** con [la revisión de eliminación](disposition.md#disposition-reviews) y la prueba de [eliminación de registros](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="93372-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="93372-116">**Exportar la información sobre todos los elementos que se han eliminado** con la [opción exportar](disposition.md#filter-and-export-the-views).</span><span class="sxs-lookup"><span data-stu-id="93372-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="93372-117">**Configurar permisos específicos** para las funciones del administrador de registros en su organización para [tener el acceso correcto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="93372-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="93372-118">Con la solución de administración de registros de Microsoft 365, puede incorporar las programaciones de retención de su organización en el plan de archivos para administrar la retención, la declaración de registros y la eliminación para dar soporte a todo el ciclo de vida del contenido.</span><span class="sxs-lookup"><span data-stu-id="93372-118">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93372-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="93372-119">Additional resources</span></span>

<span data-ttu-id="93372-120">Vea la [grabación del seminario web](https://aka.ms/MIPC/Video-RecordsManagementWebinar) y la [presentación de diapositivas con preguntas más frecuentes](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) sobre la administración de registros.</span><span class="sxs-lookup"><span data-stu-id="93372-120">See the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) and [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) for records management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="93372-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="93372-121">Next steps</span></span>

<span data-ttu-id="93372-122">Si está listo para empezar con la administración de registros de Microsoft 365, vea [Información acerca de los registros](records.md).</span><span class="sxs-lookup"><span data-stu-id="93372-122">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
