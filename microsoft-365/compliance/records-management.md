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
ms.openlocfilehash: e74c7d9e5f01b49805fccdfac2c719835354b97a
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106086"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="24bd7-103">Administración de registros en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24bd7-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="24bd7-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="24bd7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="24bd7-105">Las organizaciones de todo tipo requieren una solución de administración de registros para administrar los registros reglamentarios, legales y críticos para el negocio en sus datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="24bd7-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="24bd7-106">La administración de registros de Microsoft 365 ayuda a las organizaciones a administrar sus obligaciones legales, ofrece la posibilidad de demostrar el cumplimiento de las normativas y aumenta la eficiencia con la eliminación regular de elementos que ya no es necesario retener, que no son de gran valor o que ya no son necesarios para fines empresariales.</span><span class="sxs-lookup"><span data-stu-id="24bd7-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="24bd7-107">La solución de administración de registros es compatible con los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="24bd7-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="24bd7-108">**Etiquetar contenido como un registro**.</span><span class="sxs-lookup"><span data-stu-id="24bd7-108">**Label content as a record**.</span></span> <span data-ttu-id="24bd7-109">Publique [etiquetas de registro](records.md) para ser aplicadas por los usuarios finales o [aplique automáticamente](labels.md#applying-a-retention-label-automatically-based-on-conditions) etiquetas de registro a los elementos que contengan información confidencial, palabras clave o tipos de contenido específicos.</span><span class="sxs-lookup"><span data-stu-id="24bd7-109">Publish [record labels](records.md) to be applied by end users or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) record labels to items containing specific sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="24bd7-110">**Migrar y administrar su plan de retención con el plan de archivos** y usar el [administrador del plan de archivos](file-plan-manager.md) para incorporar su plan de retención existente, o crear uno nuevo con los descriptores de archivo y las jerarquías de expansión.</span><span class="sxs-lookup"><span data-stu-id="24bd7-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="24bd7-111">**Establecer directivas de retención y eliminación en la etiqueta de registro**.</span><span class="sxs-lookup"><span data-stu-id="24bd7-111">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="24bd7-112">Definir períodos de [retención](retention-policies.md#retaining-content-for-a-specific-period-of-time) y [eliminación](retention-policies.md#deleting-content-thats-older-than-a-specific-age) en función de una serie de factores, como la fecha de la última modificación o creación.</span><span class="sxs-lookup"><span data-stu-id="24bd7-112">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors including the date last modified or created.</span></span>

- <span data-ttu-id="24bd7-113">**Activar retención basada en eventos** con [retención basada en eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="24bd7-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="24bd7-114">**Revisar y validar la eliminación** con [la revisión de eliminación](disposition-reviews.md).</span><span class="sxs-lookup"><span data-stu-id="24bd7-114">**Review and validate disposition** with [disposition review](disposition-reviews.md).</span></span>

- <span data-ttu-id="24bd7-115">**Revisar elementos eliminados con la revisión de eliminaciones** y [exportar un informe de eliminación](disposition-reviews.md#export-the-disposition-items) para mayor validación y creación de informes.</span><span class="sxs-lookup"><span data-stu-id="24bd7-115">**Review disposed items with disposition review** and [export a disposition report](disposition-reviews.md#export-the-disposition-items) for further validation and reporting.</span></span>

- <span data-ttu-id="24bd7-116">**Configurar permisos específicos** para las funciones del administrador de registros en su organización para [tener el acceso correcto](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="24bd7-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="24bd7-117">Con la solución de administración de registros de Microsoft 365, puede incorporar las programaciones de retención de su organización en el plan de archivos para administrar la retención, la declaración de registros y la eliminación para dar soporte a todo el ciclo de vida del contenido.</span><span class="sxs-lookup"><span data-stu-id="24bd7-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition in support of the full content lifecycle.</span></span>
