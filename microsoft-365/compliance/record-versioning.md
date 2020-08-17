---
title: Usar el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive
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
description: Obtenga información acerca de los registros para que pueda implementar la solución de administración de registros en Microsoft 365.
ms.openlocfilehash: 943bf3949ab57eb4603695495d7a8ca0c4b90db7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695279"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="0d1c4-103">Usar el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="0d1c4-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="0d1c4-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="0d1c4-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0d1c4-105">La posibilidad de marcar un documento como [registro](records.md) y restringir las acciones que se pueden realizar en el registro es un objetivo esencial de cualquier solución de administración de registros.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-105">The ability to mark a document as a [record](records.md) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="0d1c4-106">Sin embargo, puede ser necesaria la colaboración para crear versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-106">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="0d1c4-107">Por ejemplo, podría marcar un contrato de ventas como un registro, pero después tiene que actualizar el contrato con nuevos términos y marcar la versión más reciente como un nuevo registro, manteniendo aún la versión de registro anterior.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-107">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="0d1c4-108">Para estos tipos de escenarios, SharePoint Online y OneDrive admite el *control de versiones de registros*.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-108">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="0d1c4-109">Las carpetas del Bloc de notas de OneNote no admiten el control de versiones de registros.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-109">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="0d1c4-110">Para usar el control de versiones de registros, primero [etiquete el documento y márquelo como registro](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="0d1c4-110">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="0d1c4-111">En ese momento, se mostrará la propiedad de documento, llamada *Estado del registro* junto a la etiqueta de retención, y el estado del registro inicial será **bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-111">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="0d1c4-112">Puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d1c4-112">You can now do the following things:</span></span>

  - <span data-ttu-id="0d1c4-113">**Editar y retener continuamente versiones individuales del documento como registros, desbloqueando y bloqueando la propiedad Estado del registro**.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-113">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="0d1c4-114">Solo se retiene una nueva versión del registro cuando la propiedad **Estado del registro** se establece en **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-114">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="0d1c4-115">Esta alternancia de bloqueado y desbloqueado reduce el riesgo de conservar versiones y copias innecesarias del documento.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-115">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="0d1c4-116">**Hacer que los registros se almacenen automáticamente en un repositorio de registros locales que se encuentra dentro de la colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-116">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="0d1c4-117">Todas las colecciones de sitios de SharePoint y OneDrive conserva el contenido en su biblioteca de suspensión para conservación.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-117">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="0d1c4-118">Las versiones de registro se almacenan en la carpeta registros de esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-118">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="0d1c4-119">**Mantenga un documento de hoja perenne que contenga todas las versiones**.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-119">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="0d1c4-120">De forma predeterminada, todos los documentos de SharePoint y OneDrive tienen un historial de versiones disponible en el menú elemento.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-120">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="0d1c4-121">En esta historia de versiones, puede ver fácilmente las versiones que son registros y ver esos documentos.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-121">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="0d1c4-122">El control de versiones de registros está disponible automáticamente para todos los documentos que contengan una etiqueta de retención que marca el elemento como un registro.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-122">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="0d1c4-123">Cuando un usuario ve las propiedades del documento en el panel de detalles, puede cambiar el **Estado del registro** de **bloqueado** a **desbloqueado**.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-123">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="0d1c4-124">Esta acción crea un registro en la carpeta registros de la biblioteca de suspensión para conservación, donde se encuentra por el resto de su período de retención.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-124">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="0d1c4-125">Cuando el documento esté desbloqueado, todos los usuarios con permisos de edición estándar podrán editar el archivo.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-125">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="0d1c4-126">Sin embargo, los usuarios no pueden eliminar el archivo porque aún es un registro.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-126">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="0d1c4-127">Cuando termine de editar, el usuario puede cambiar el **Estado de registro** de **Desbloqueado** a **Bloqueado**, lo que impide que se realicen otras modificaciones mientras se encuentre en este estado.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-127">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Propiedad de estado de registro en un documento etiquetado como registro](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="0d1c4-129">Bloquear y desbloquear un registro</span><span class="sxs-lookup"><span data-stu-id="0d1c4-129">Locking and unlocking a record</span></span>

<span data-ttu-id="0d1c4-130">Cuando se aplica a un documento una etiqueta de retención que marca contenido como un registro, cualquier usuario con permisos de contribución o un nivel de permisos más limitado puede desbloquear un registro o bloquear un registro desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-130">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![El estado del registro muestra que el documento de registro está desbloqueado](../media/recordversioning9.png)

<span data-ttu-id="0d1c4-132">Cuando un usuario desbloquea un registro, tienen lugar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0d1c4-132">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="0d1c4-133">Si la colección de sitios actual no tiene una biblioteca de suspensión para conservación, se crea una.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-133">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="0d1c4-134">Si la biblioteca de suspensión para conservación no tiene una carpeta de registros, se crea una.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-134">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="0d1c4-135">Una acción **Copiar a** copia la última versión del documento en la carpeta registros.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-135">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="0d1c4-136">La acción **Copiar a** solo incluye la versión más reciente y ninguna de las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-136">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="0d1c4-137">Este documento copiado se considera ahora una versión de registro del documento y su nombre de archivo tiene el formato: \[Título GUID versión\#\]</span><span class="sxs-lookup"><span data-stu-id="0d1c4-137">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="0d1c4-138">La copia creada en la carpeta de registros se agrega al historial de versiones del documento original y esta versión muestra la palabra **Registro** en el campo de comentarios.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-138">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="0d1c4-139">El documento original es una nueva versión que se puede editar, pero no eliminar.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-139">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="0d1c4-140">La columna de la biblioteca de documentos **El elemento es un registro** aún muestra el valor **Sí**, ya que el documento aún es un registro incluso si ahora se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-140">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="0d1c4-141">Cuando un usuario bloquea un registro, no se puede editar el documento original.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-141">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="0d1c4-142">Sin embargo, es la acción de desbloquear un registro que copia una versión en la carpeta registros de la biblioteca de suspensión para conservación.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-142">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="0d1c4-143">Versiones de registro</span><span class="sxs-lookup"><span data-stu-id="0d1c4-143">Record versions</span></span>

<span data-ttu-id="0d1c4-144">Cada vez que un usuario desbloquea un registro, la versión más reciente se copia en la carpeta registros de la biblioteca de suspensión para conservación, que contiene el valor de **registro** en el campo **comentarios** del historial de versiones.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-144">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Registro que se muestra en la biblioteca de conservación de documentos](../media/recordversioning10.png)

<span data-ttu-id="0d1c4-146">Para ver el historial de versiones, seleccione un documento de la biblioteca de documentos y, a continuación, haga clic en **Historial de versiones** en el menú elemento.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-146">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="0d1c4-147">Dónde se almacenan los registros</span><span class="sxs-lookup"><span data-stu-id="0d1c4-147">Where records are stored</span></span>

<span data-ttu-id="0d1c4-148">Los registros se almacenan en la carpeta registros de la biblioteca de suspensión para conservación en el sitio de nivel superior de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-148">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="0d1c4-149">En el panel de navegación izquierdo en el sitio de nivel superior, elija **Contenidos del sitio** \> **Biblioteca de suspensión para conservación**.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-149">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Biblioteca de conservación de documentos](../media/recordversioning11.png)

<br/><br/>

![La carpeta registros en la biblioteca de conservación de documentos](../media/recordversioning12.png)

<span data-ttu-id="0d1c4-152">La biblioteca de suspensión para conservación solo es visible para los administradores de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-152">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="0d1c4-153">Asimismo, la biblioteca de suspensión para conservación no existe de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-153">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="0d1c4-154">Solo se crea cuando el contenido sometido a una etiqueta de retención o una directiva de retención se elimina por primera vez en la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-154">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="0d1c4-155">Buscar en el registro de auditoría los eventos de control de versiones de registros</span><span class="sxs-lookup"><span data-stu-id="0d1c4-155">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="0d1c4-156">Las acciones para bloquear y desbloquear registros se registran en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-156">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="0d1c4-157">Puede buscar actividades específicas **cambiado el estado del registro a bloqueado** y **cambiado el estado del registros a desbloqueado**, que se encuentran en la sección **Actividades de archivo y de página** de la lista desplegable **Actividades** en la página **Búsqueda de registros de auditoría** en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="0d1c4-157">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Buscar en el registro de auditoría los eventos de control de versiones de registros](../media/recordversioning13.png)

<span data-ttu-id="0d1c4-159">Para obtener más información sobre la búsqueda de estos eventos, vea la sección "Actividades de archivo y de página" en [Buscar el registro de auditoría en el centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="0d1c4-159">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0d1c4-160">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="0d1c4-160">Next steps</span></span>

<span data-ttu-id="0d1c4-161">Para marcar el contenido como un registro, vea [Declarar registros con las etiquetas de retención](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="0d1c4-161">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>

<span data-ttu-id="0d1c4-162">Para obtener más información sobre la eliminación de registros, consulte [Eliminación del contenido](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="0d1c4-162">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
