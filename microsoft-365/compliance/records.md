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
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372525"
---
# <a name="learn-about-records"></a><span data-ttu-id="04ad5-103">Obtenga más información sobre los registros</span><span class="sxs-lookup"><span data-stu-id="04ad5-103">Learn about records</span></span>

><span data-ttu-id="04ad5-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="04ad5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="04ad5-105">La administración de registros de Microsoft 365 ayuda a su organización a cumplir con las directivas corporativas y las obligaciones legales o reglamentarias, al mismo tiempo que reduce el riesgo y la responsabilidad legal.</span><span class="sxs-lookup"><span data-stu-id="04ad5-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="04ad5-106">Cuando el contenido está marcado como un registro:</span><span class="sxs-lookup"><span data-stu-id="04ad5-106">When content is marked as a record:</span></span>

- <span data-ttu-id="04ad5-107">Se colocan restricciones en los elementos relativas a qué [acciones se permiten o se bloquean](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="04ad5-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="04ad5-108">Se registran otras actividades sobre el elemento.</span><span class="sxs-lookup"><span data-stu-id="04ad5-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="04ad5-109">Tendrá la prueba de la eliminación cuando se eliminen los elementos al final de su período de retención.</span><span class="sxs-lookup"><span data-stu-id="04ad5-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="04ad5-110">Puede usar las [etiquetas de retención](retention.md#retention-labels) para marcar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="04ad5-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="04ad5-111">Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.</span><span class="sxs-lookup"><span data-stu-id="04ad5-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="04ad5-112">Al usar las etiquetas de retención para marcar contenido como registros, puede implementar una sola estrategia de administración de registros uniforme en todo el entorno de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04ad5-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="04ad5-113">Comparar restricciones de acciones permitidas o bloqueadas</span><span class="sxs-lookup"><span data-stu-id="04ad5-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="04ad5-114">Use la tabla siguiente para identificar qué restricciones se colocan en el contenido como resultado de aplicar una etiqueta de retención estándar y conocer las etiquetas de retención que marcan el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="04ad5-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="04ad5-115">Una etiqueta de retención estándar tiene la configuración para conservar datos sin marcar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="04ad5-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="04ad5-116">Por motivos de integridad, la tabla contiene columnas para un registro bloqueado y desbloqueado, lo que se aplica a SharePoint y OneDrive, pero no a Exchange.</span><span class="sxs-lookup"><span data-stu-id="04ad5-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="04ad5-117">La capacidad de bloquear y desbloquear un registro usa el [control de versiones de registros](#record-versioning) que no es compatible con los elementos de Exchange.</span><span class="sxs-lookup"><span data-stu-id="04ad5-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="04ad5-118">Por lo tanto, para todos los elementos de Exchange que estén marcados como un registro, el comportamiento que se asigna a la columna **registro bloqueado** y a la columna **registro desbloqueado** no es relevante.</span><span class="sxs-lookup"><span data-stu-id="04ad5-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="04ad5-119">Acción</span><span class="sxs-lookup"><span data-stu-id="04ad5-119">Action</span></span>| <span data-ttu-id="04ad5-120">Etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="04ad5-120">Retention label</span></span> |<span data-ttu-id="04ad5-121">Registro: bloqueado</span><span class="sxs-lookup"><span data-stu-id="04ad5-121">Record - locked</span></span>| <span data-ttu-id="04ad5-122">Registro: desbloqueado</span><span class="sxs-lookup"><span data-stu-id="04ad5-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="04ad5-123">Editar contenidos</span><span class="sxs-lookup"><span data-stu-id="04ad5-123">Edit contents</span></span>|<span data-ttu-id="04ad5-124">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-124">Allowed</span></span> | <span data-ttu-id="04ad5-125">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="04ad5-125">**Blocked**</span></span> | <span data-ttu-id="04ad5-126">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-126">Allowed</span></span>|
|<span data-ttu-id="04ad5-127">Editar propiedades, incluido cambiar nombre</span><span class="sxs-lookup"><span data-stu-id="04ad5-127">Edit properties, including rename</span></span>|<span data-ttu-id="04ad5-128">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-128">Allowed</span></span> |<span data-ttu-id="04ad5-129">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-129">Allowed</span></span> | <span data-ttu-id="04ad5-130">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-130">Allowed</span></span>|
|<span data-ttu-id="04ad5-131">Eliminar</span><span class="sxs-lookup"><span data-stu-id="04ad5-131">Delete</span></span>|<span data-ttu-id="04ad5-132">Permitido<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="04ad5-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="04ad5-133">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="04ad5-133">**Blocked**</span></span> | <span data-ttu-id="04ad5-134">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="04ad5-134">**Blocked**</span></span>|
|<span data-ttu-id="04ad5-135">Copiar</span><span class="sxs-lookup"><span data-stu-id="04ad5-135">Copy</span></span>|<span data-ttu-id="04ad5-136">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-136">Allowed</span></span> |<span data-ttu-id="04ad5-137">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-137">Allowed</span></span> | <span data-ttu-id="04ad5-138">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-138">Allowed</span></span>|
|<span data-ttu-id="04ad5-139">Moverse dentro del contenedor<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="04ad5-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="04ad5-140">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-140">Allowed</span></span> |<span data-ttu-id="04ad5-141">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-141">Allowed</span></span> | <span data-ttu-id="04ad5-142">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-142">Allowed</span></span>|
|<span data-ttu-id="04ad5-143">Moverse entre contenedores<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="04ad5-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="04ad5-144">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-144">Allowed</span></span> |<span data-ttu-id="04ad5-145">Permitido si nunca se desbloquea</span><span class="sxs-lookup"><span data-stu-id="04ad5-145">Allowed if never unlocked</span></span> | <span data-ttu-id="04ad5-146">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-146">Allowed</span></span>|
|<span data-ttu-id="04ad5-147">Abrir y leer</span><span class="sxs-lookup"><span data-stu-id="04ad5-147">Open/Read</span></span>|<span data-ttu-id="04ad5-148">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-148">Allowed</span></span> |<span data-ttu-id="04ad5-149">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-149">Allowed</span></span> | <span data-ttu-id="04ad5-150">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-150">Allowed</span></span>|
|<span data-ttu-id="04ad5-151">Cambiar etiqueta</span><span class="sxs-lookup"><span data-stu-id="04ad5-151">Change label</span></span>|<span data-ttu-id="04ad5-152">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-152">Allowed</span></span> |<span data-ttu-id="04ad5-153">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="04ad5-153">Allowed - container admin only</span></span> | <span data-ttu-id="04ad5-154">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="04ad5-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="04ad5-155">Quitar etiqueta</span><span class="sxs-lookup"><span data-stu-id="04ad5-155">Remove label</span></span>|<span data-ttu-id="04ad5-156">Permitido</span><span class="sxs-lookup"><span data-stu-id="04ad5-156">Allowed</span></span> |<span data-ttu-id="04ad5-157">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="04ad5-157">Allowed - container admin only</span></span> | <span data-ttu-id="04ad5-158">Permitido: solo administradores del contenedor</span><span class="sxs-lookup"><span data-stu-id="04ad5-158">Allowed - container admin only</span></span>|

<span data-ttu-id="04ad5-159">Notas al pie:</span><span class="sxs-lookup"><span data-stu-id="04ad5-159">Footnotes:</span></span>

<span data-ttu-id="04ad5-160"><sup>1</sup> Compatible con OneDrive y Exchange reteniendo una copia en una ubicación segura, pero bloqueado por SharePoint.</span><span class="sxs-lookup"><span data-stu-id="04ad5-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="04ad5-161">Mensaje que ve el usuario si intenta eliminar un documento con etiquetas en SharePoint:</span><span class="sxs-lookup"><span data-stu-id="04ad5-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Mensaje que indica que el elemento no se elimina de SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="04ad5-163"><sup>2</sup> Los contenedores incluyen librerías de documentos de SharePoint y buzones de Exchange.</span><span class="sxs-lookup"><span data-stu-id="04ad5-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="04ad5-164">Usar etiquetas de retención para declarar registros</span><span class="sxs-lookup"><span data-stu-id="04ad5-164">Using retention labels to declare records</span></span>

<span data-ttu-id="04ad5-165">Al crear una etiqueta de retención, tiene la opción de usarla para marcar el contenido como un registro:</span><span class="sxs-lookup"><span data-stu-id="04ad5-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="04ad5-166">En el Centro de cumplimiento de Microsoft 365, vaya a **Administración de registros** \> **Plan de archivos**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="04ad5-167">En la página **Plan de archivos**, seleccione **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="04ad5-168">En la página **Configuración de la etiqueta** del asistente, elija la opción para clasificar el contenido como un registro.</span><span class="sxs-lookup"><span data-stu-id="04ad5-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Haga clic en la casilla Usar una etiqueta para clasificar contenido como un "registro"](../media/recordversioning6.png)

3. <span data-ttu-id="04ad5-170">Aplique la etiqueta de retención a los documentos de SharePoint o OneDrive y los correos electrónicos de Exchange, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="04ad5-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="04ad5-171">Para obtener instrucciones, consulte:</span><span class="sxs-lookup"><span data-stu-id="04ad5-171">For instructions:</span></span>
    
    - [<span data-ttu-id="04ad5-172">Crear etiquetas de retención y aplicarlas en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="04ad5-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="04ad5-173">Aplicar una etiqueta de retención automáticamente al contenido</span><span class="sxs-lookup"><span data-stu-id="04ad5-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="04ad5-174">Aplicar una etiqueta de retención configurada al contenido</span><span class="sxs-lookup"><span data-stu-id="04ad5-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="04ad5-175">Cuando las etiquetas de retención que marcan el contenido como un registro se ponen a disposición de los usuarios para que las usen en aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="04ad5-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="04ad5-176">Para Exchange, todos los usuarios con acceso de escritura al buzón pueden aplicar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="04ad5-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="04ad5-177">Para SharePoint y OneDrive, cualquier usuario del grupo predeterminado de miembros (con nivel de permisos de contribución) puede aplicar las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="04ad5-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="04ad5-178">Ejemplo de un documento marcado como registro con una etiqueta de retención:</span><span class="sxs-lookup"><span data-stu-id="04ad5-178">Example of a document marked as record by using a retention label:</span></span>

![Panel de detalles para los documentos etiquetados como registro](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="04ad5-180">Control de versiones de registros</span><span class="sxs-lookup"><span data-stu-id="04ad5-180">Record versioning</span></span>

<span data-ttu-id="04ad5-181">La posibilidad de marcar un documento como registro y restringir las acciones que se pueden realizar en el registro es un objetivo esencial de cualquier solución de administración de registros.</span><span class="sxs-lookup"><span data-stu-id="04ad5-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="04ad5-182">Sin embargo, puede ser necesaria la colaboración para crear versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="04ad5-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="04ad5-183">Por ejemplo, podría marcar un contrato de ventas como un registro, pero después tiene que actualizar el contrato con nuevos términos y marcar la versión más reciente como un nuevo registro, manteniendo aún la versión de registro anterior.</span><span class="sxs-lookup"><span data-stu-id="04ad5-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="04ad5-184">Para estos tipos de escenarios, SharePoint Online y OneDrive admite el *control de versiones de registros*.</span><span class="sxs-lookup"><span data-stu-id="04ad5-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="04ad5-185">Las carpetas del Bloc de notas de OneNote no admiten el control de versiones de registros.</span><span class="sxs-lookup"><span data-stu-id="04ad5-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="04ad5-186">Para usar el control de versiones de registros, etiquete primero el documento y márquelo como registro.</span><span class="sxs-lookup"><span data-stu-id="04ad5-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="04ad5-187">En ese momento, se mostrará la propiedad de documento, llamada *Estado del registro* junto a la etiqueta de retención, y el estado del registro inicial será **bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="04ad5-188">Puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="04ad5-188">You can now do the following things:</span></span>

  - <span data-ttu-id="04ad5-189">**Editar y retener continuamente versiones individuales del documento como registros, desbloqueando y bloqueando la propiedad Estado del registro**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="04ad5-190">Solo se retiene una nueva versión del registro cuando la propiedad **Estado del registro** se establece en **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="04ad5-191">Esta alternancia de bloqueado y desbloqueado reduce el riesgo de conservar versiones y copias innecesarias del documento.</span><span class="sxs-lookup"><span data-stu-id="04ad5-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="04ad5-192">**Hacer que los registros se almacenen automáticamente en un repositorio de registros locales que se encuentra dentro de la colección de sitios**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="04ad5-193">Todas las colecciones de sitios de SharePoint y OneDrive conserva el contenido en su biblioteca de suspensión para conservación.</span><span class="sxs-lookup"><span data-stu-id="04ad5-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="04ad5-194">Las versiones de registro se almacenan en la carpeta registros de esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="04ad5-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="04ad5-195">**Mantenga un documento de hoja perenne que contenga todas las versiones**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="04ad5-196">De forma predeterminada, todos los documentos de SharePoint y OneDrive tienen un historial de versiones disponible en el menú elemento.</span><span class="sxs-lookup"><span data-stu-id="04ad5-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="04ad5-197">En esta historia de versiones, puede ver fácilmente las versiones que son registros y ver esos documentos.</span><span class="sxs-lookup"><span data-stu-id="04ad5-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="04ad5-198">El control de versiones de registros está disponible automáticamente para todos los documentos que contengan una etiqueta de retención que marca el elemento como un registro.</span><span class="sxs-lookup"><span data-stu-id="04ad5-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="04ad5-199">Cuando un usuario ve las propiedades del documento en el panel de detalles, puede cambiar el **Estado del registro** de **bloqueado** a **desbloqueado**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="04ad5-200">Esta acción crea un registro en la carpeta registros de la biblioteca de suspensión para conservación, donde se encuentra por el resto de su período de retención.</span><span class="sxs-lookup"><span data-stu-id="04ad5-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="04ad5-201">Cuando el documento esté desbloqueado, todos los usuarios con permisos de edición estándar podrán editar el archivo.</span><span class="sxs-lookup"><span data-stu-id="04ad5-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="04ad5-202">Sin embargo, los usuarios no pueden eliminar el archivo porque aún es un registro.</span><span class="sxs-lookup"><span data-stu-id="04ad5-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="04ad5-203">Cuando termine de editar, el usuario puede cambiar el **Estado de registro** de **Desbloqueado** a **Bloqueado**, lo que impide que se realicen otras modificaciones mientras se encuentre en este estado.</span><span class="sxs-lookup"><span data-stu-id="04ad5-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Propiedad de estado de registro en un documento etiquetado como registro](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="04ad5-205">Bloquear y desbloquear un registro</span><span class="sxs-lookup"><span data-stu-id="04ad5-205">Locking and unlocking a record</span></span>

<span data-ttu-id="04ad5-206">Cuando se aplica a un documento una etiqueta de retención que marca contenido como un registro, cualquier usuario con permisos de contribución o un nivel de permisos más limitado puede desbloquear un registro o bloquear un registro desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="04ad5-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![El estado del registro muestra que el documento de registro está desbloqueado](../media/recordversioning9.png)

<span data-ttu-id="04ad5-208">Cuando un usuario desbloquea un registro, tienen lugar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="04ad5-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="04ad5-209">Si la colección de sitios actual no tiene una biblioteca de suspensión para conservación, se crea una.</span><span class="sxs-lookup"><span data-stu-id="04ad5-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="04ad5-210">Si la biblioteca de suspensión para conservación no tiene una carpeta de registros, se crea una.</span><span class="sxs-lookup"><span data-stu-id="04ad5-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="04ad5-211">Una acción **Copiar a** copia la última versión del documento en la carpeta registros.</span><span class="sxs-lookup"><span data-stu-id="04ad5-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="04ad5-212">La acción **Copiar a** solo incluye la versión más reciente y ninguna de las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="04ad5-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="04ad5-213">Este documento copiado se considera ahora una versión de registro del documento y su nombre de archivo tiene el formato: \[Título GUID versión\#\]</span><span class="sxs-lookup"><span data-stu-id="04ad5-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="04ad5-214">La copia creada en la carpeta de registros se agrega al historial de versiones del documento original y esta versión muestra la palabra **Registro** en el campo de comentarios.</span><span class="sxs-lookup"><span data-stu-id="04ad5-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="04ad5-215">El documento original es una nueva versión que se puede editar, pero no eliminar.</span><span class="sxs-lookup"><span data-stu-id="04ad5-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="04ad5-216">La columna de la biblioteca de documentos **El elemento es un registro** aún muestra el valor **Sí**, ya que el documento aún es un registro incluso si ahora se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="04ad5-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="04ad5-217">Cuando un usuario bloquea un registro, no se puede editar el documento original.</span><span class="sxs-lookup"><span data-stu-id="04ad5-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="04ad5-218">Sin embargo, es la acción de desbloquear un registro que copia una versión en la carpeta registros de la biblioteca de suspensión para conservación.</span><span class="sxs-lookup"><span data-stu-id="04ad5-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="04ad5-219">Versiones de registro</span><span class="sxs-lookup"><span data-stu-id="04ad5-219">Record versions</span></span>

<span data-ttu-id="04ad5-220">Cada vez que un usuario desbloquea un registro, la versión más reciente se copia en la carpeta registros de la biblioteca de suspensión para conservación, que contiene el valor de **registro** en el campo **comentarios** del historial de versiones.</span><span class="sxs-lookup"><span data-stu-id="04ad5-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Registro que se muestra en la biblioteca de conservación de documentos](../media/recordversioning10.png)

<span data-ttu-id="04ad5-222">Para ver el historial de versiones, seleccione un documento de la biblioteca de documentos y, a continuación, haga clic en **Historial de versiones** en el menú elemento.</span><span class="sxs-lookup"><span data-stu-id="04ad5-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="04ad5-223">Dónde se almacenan los registros</span><span class="sxs-lookup"><span data-stu-id="04ad5-223">Where records are stored</span></span>

<span data-ttu-id="04ad5-224">Los registros se almacenan en la carpeta registros de la biblioteca de suspensión para conservación en el sitio de nivel superior de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="04ad5-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="04ad5-225">En el panel de navegación izquierdo en el sitio de nivel superior, elija **Contenidos del sitio** \> **Biblioteca de suspensión para conservación**.</span><span class="sxs-lookup"><span data-stu-id="04ad5-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Biblioteca de conservación de documentos](../media/recordversioning11.png)

<br/><br/>

![La carpeta registros en la biblioteca de conservación de documentos](../media/recordversioning12.png)

<span data-ttu-id="04ad5-228">La biblioteca de suspensión para conservación solo es visible para los administradores de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="04ad5-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="04ad5-229">Asimismo, la biblioteca de suspensión para conservación no existe de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="04ad5-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="04ad5-230">Solo se crea cuando el contenido sometido a una etiqueta de retención o una directiva de retención se elimina por primera vez en la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="04ad5-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="04ad5-231">Buscar en el registro de auditoría los eventos de control de versiones de registros</span><span class="sxs-lookup"><span data-stu-id="04ad5-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="04ad5-232">Las acciones para bloquear y desbloquear registros se registran en el registro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="04ad5-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="04ad5-233">Puede buscar actividades específicas **cambiado el estado del registro a bloqueado** y **cambiado el estado del registros a desbloqueado**, que se encuentran en la sección **Actividades de archivo y de página** de la lista desplegable **Actividades** en la página **Búsqueda de registros de auditoría** en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="04ad5-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Buscar en el registro de auditoría los eventos de control de versiones de registros](../media/recordversioning13.png)

<span data-ttu-id="04ad5-235">Para obtener más información sobre la búsqueda de estos eventos, vea la sección "Actividades de archivo y de página" en [Buscar el registro de auditoría en el centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="04ad5-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="04ad5-236">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="04ad5-236">Next steps</span></span>

<span data-ttu-id="04ad5-237">Si aún no tiene etiquetas de retención que se usarán para la administración de registros, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="04ad5-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="04ad5-238">Para obtener más información sobre la eliminación de registros, consulte [Eliminación del contenido](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="04ad5-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
