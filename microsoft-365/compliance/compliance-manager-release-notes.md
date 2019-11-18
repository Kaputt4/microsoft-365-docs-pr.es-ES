---
title: Notas de la versión de Microsoft Compliance Manager
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en flujos de trabajo en el portal de confianza de servicios de Microsoft. El administrador de cumplimiento le permite realizar un seguimiento, asignar y comprobar actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.
ms.openlocfilehash: 1a490212b2275b9f297e2585e7242f5331d0fe56
ms.sourcegitcommit: 5c6c30ec5541d2fb77e53a1309db1fe7b75fc3e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "38687655"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="b1ef5-104">Notas de la versión del administrador de cumplimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b1ef5-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="b1ef5-105">La versión preliminar pública del administrador de cumplimiento le proporciona acceso anticipado a las actualizaciones y funciones futuras.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="b1ef5-106">Puede usar la herramienta actualizada del [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) en el portal de confianza de [servicios](https://servicetrust.microsoft.com) para realizar un seguimiento, asignar y comprobar las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="b1ef5-107">Novedades del administrador de cumplimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b1ef5-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="b1ef5-108">**Acceso basado en roles al administrador de cumplimiento:** Se ha quitado el rol de **acceso de invitado** predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="b1ef5-109">Para que un usuario tenga acceso al administrador de cumplimiento, el administrador global debe [asignar un permiso a cada usuario](compliance-manager-overview.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="b1ef5-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="b1ef5-110">**Puntuación de cumplimiento actualizada**: la puntuación de cumplimiento ahora incluye los resultados de las acciones administradas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="b1ef5-111">La puntuación se incrementará como resultado.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="b1ef5-112">**Elementos de acciones:** Los elementos de acción son ahora elementos individuales y muchos incluyen la colección de telemetría de la API de Microsoft Secure score Graph.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="b1ef5-113">Siempre que sea posible, las recomendaciones de acciones técnicas ahora tienen vínculos a la página de configuración correspondiente en el servicio de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="b1ef5-114">**Administración de inquilinos:** Nueva interfaz para la administración de elementos de datos nuevos en el administrador de cumplimiento (versión preliminar):</span><span class="sxs-lookup"><span data-stu-id="b1ef5-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="b1ef5-115">**Dimensiones:** Permite ver, agregar y personalizar metadatos para plantillas, evaluaciones y elementos de acción que permiten crear tablas dinámicas personalizadas para los filtros.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="b1ef5-116">**Propietarios:** Especifique un propietario para cada elemento de acción.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="b1ef5-117">**Acciones del cliente:** Administrar la lista completa de elementos de acciones incluidos en el administrador de cumplimiento (versión preliminar) y habilitar o deshabilitar la supervisión de la puntuación segura para los elementos de acción integrados con calificación segura.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="b1ef5-118">Problemas conocidos en el administrador de cumplimiento (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="b1ef5-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="b1ef5-119">En las siguientes secciones se abordan los problemas conocidos que deben resolverse en próximas versiones del administrador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="b1ef5-120">Puntuación de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="b1ef5-120">Compliance Score</span></span>

- <span data-ttu-id="b1ef5-121">Para los elementos de acción marcados como **no en el ámbito**, la puntuación asignada al elemento de acción no se excluye del cálculo de puntuación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the compliance score calculation.</span></span> <span data-ttu-id="b1ef5-122">Los elementos de acción marcados **sin ámbito** no aumentan la puntuación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-122">Action Items marked **Not in Scope** do not increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="b1ef5-123">Puntuación segura</span><span class="sxs-lookup"><span data-stu-id="b1ef5-123">Secure Score</span></span>

- <span data-ttu-id="b1ef5-124">Los resultados de la puntuación segura no están disponibles para algunos elementos de acciones en determinadas suscripciones de Microsoft 365 y Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-124">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="b1ef5-125">**No se pudo detectar** el resultado de la puntuación segura en estos casos.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="b1ef5-126">A veces, se devuelven resultados de puntuación seguros para las directivas y los elementos de acción correspondientes no completados.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="b1ef5-127">Para los nuevos inquilinos, se activan automáticamente las actualizaciones de puntuación seguras para todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="b1ef5-128">El administrador global puede establecer el cambio de actualización continua de puntuación segura en desactivado, lo que desactiva las actualizaciones para todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
- <span data-ttu-id="b1ef5-129">Cuando las actualizaciones de calificaciones seguras están activadas, las acciones se supervisan activamente mediante una puntuación segura, aunque la fecha de prueba de la acción no se actualizará para reflejar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-129">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date will not be updated to reflect monitoring.</span></span>
- <span data-ttu-id="b1ef5-130">Cuando se crean nuevas evaluaciones, las puntuaciones incluyen automáticamente los resultados de los controles administrados por Microsoft y la integración de la puntuación segura.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-130">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="b1ef5-131">Controles administrados por Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1ef5-131">Microsoft-managed Controls</span></span>

- <span data-ttu-id="b1ef5-132">La fecha de prueba de los controles administrados por Microsoft no aparece en la interfaz de usuario, incluso cuando se incluye en la evaluación.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-132">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="b1ef5-133">Para ver la información de fecha de prueba, debe exportar la evaluación.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-133">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="b1ef5-134">Personalización</span><span class="sxs-lookup"><span data-stu-id="b1ef5-134">Customization</span></span>

- <span data-ttu-id="b1ef5-135">Agregar controles personalizados permite agregar un control nuevo a una familia de controles existente, pero no permite agregar una nueva familia de controles.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-135">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="b1ef5-136">Esta versión no admite la vinculación de elementos de acción ni la adición de elementos o controles de acciones a una evaluación.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-136">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="b1ef5-137">Si crea una acción personalizada, no podrá editarla ni eliminarla.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-137">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="b1ef5-138">Familias de control que no se muestran en las evaluaciones</span><span class="sxs-lookup"><span data-stu-id="b1ef5-138">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="b1ef5-139">Al importar una plantilla, todas las evaluaciones basadas en dicha plantilla reflejan todas las familias de controles que forman parte de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-139">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="b1ef5-140">Pero si agrega nuevas familias de controles a la plantilla, las evaluaciones existentes no reflejarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-140">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="b1ef5-141">Solo las nuevas evaluaciones creadas a partir de la plantilla actualizada reflejan los cambios.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-141">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="b1ef5-142">Plantillas</span><span class="sxs-lookup"><span data-stu-id="b1ef5-142">Templates</span></span>

- <span data-ttu-id="b1ef5-143">Al crear una plantilla, debe incluir las dimensiones del **producto** y la **certificación** para asegurarse de que la plantilla se muestra en la puntuación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-143">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="b1ef5-144">Las plantillas archivadas son editables y no se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-144">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="b1ef5-145">Las plantillas bloqueadas permiten la creación de evaluaciones cuando no deberían.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-145">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="b1ef5-146">Bloquear una plantilla tiene como objetivo evitar que se use para crear evaluaciones.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-146">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="b1ef5-147">Exportar</span><span class="sxs-lookup"><span data-stu-id="b1ef5-147">Export</span></span>

- <span data-ttu-id="b1ef5-148">Se produce un error en la exportación de plantillas a JSON cuando el estado de la plantilla está establecido en **importado** o **pendiente de aprobación**.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-148">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="b1ef5-149">Exploradores compatibles</span><span class="sxs-lookup"><span data-stu-id="b1ef5-149">Supported browsers</span></span>

- <span data-ttu-id="b1ef5-150">Se admiten las versiones más recientes de Microsoft Edge, Chrome y Safari.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-150">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="b1ef5-151">Puede haber casos en los que los datos actualizados no aparezcan hasta que se actualice el explorador.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-151">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="b1ef5-152">La versión preliminar de Microsoft Edge no es compatible, pero no tiene problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-152">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="b1ef5-153">Internet Explorer no es compatible.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-153">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="b1ef5-154">Tiempo de espera de sesión</span><span class="sxs-lookup"><span data-stu-id="b1ef5-154">Session timeout</span></span>

- <span data-ttu-id="b1ef5-155">Cuando se agota el tiempo de espera de una sesión, puede aparecer un error "se ha producido un problema".</span><span class="sxs-lookup"><span data-stu-id="b1ef5-155">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="b1ef5-156">Para solucionarlo, vaya al [Administrador de cumplimiento](https://servicetrust.microsoft.com/ComplianceManager) e inicie sesión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-156">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="b1ef5-157">Compatibilidad con idiomas</span><span class="sxs-lookup"><span data-stu-id="b1ef5-157">Language support</span></span>

- <span data-ttu-id="b1ef5-158">No todos los idiomas son compatibles con todas las páginas Web.</span><span class="sxs-lookup"><span data-stu-id="b1ef5-158">All languages are not supported for all webpages.</span></span> <span data-ttu-id="b1ef5-159">Si el idioma local no es compatible, consulte en inglés (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="b1ef5-159">If your local language is unsupported, view in US English.</span></span>