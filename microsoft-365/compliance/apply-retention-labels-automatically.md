---
title: Aplicar una etiqueta de retención automáticamente para conservar o eliminar contenido
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
description: Cree y publique automáticamente etiquetas de retención para aplicar etiquetas de manera automática y así conservar lo que necesita y eliminar lo que no
ms.openlocfilehash: 9ab456cd5b1f5f1bf47a1e24a3d7e58b7992ede0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196383"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="fe5a3-103">Aplicar una etiqueta de retención automáticamente para conservar o eliminar contenido</span><span class="sxs-lookup"><span data-stu-id="fe5a3-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="fe5a3-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="fe5a3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="fe5a3-105">Este escenario no es compatible con los [registros normativos](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="fe5a3-106">Una de las características más eficaces de las [etiquetas de retención](retention.md) es la capacidad de aplicarlas automáticamente al contenido que coincide con condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="fe5a3-107">En este caso, no es necesario que las personas de la organización apliquen las etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="fe5a3-108">Microsoft 365 realiza el trabajo por ellos.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="fe5a3-109">Las etiquetas de retención auto aplicadas son poderosas porque:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="fe5a3-110">No es necesario formar a los usuarios para que conozcan todas las clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="fe5a3-111">No es necesario depender de los usuarios para clasificar todo el contenido correctamente.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="fe5a3-112">Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="fe5a3-113">Las etiquetas de retención se pueden aplicar a contenido automáticamente cuando dicho contenido contiene información confidencial, palabras clave o propiedades que permiten búsquedas, o una coincidencia para [clasificadores que se puedan entrenar](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="fe5a3-114">Ahora, en la versión preliminar, puede utilizar las propiedades que permiten búsquedas para identificar las [grabaciones de reuniones de Teams](#microsoft-teams-meeting-recordings).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="fe5a3-115">Los procesos para aplicar automáticamente una etiqueta de retención se basan en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![Diagrama de roles y tareas para etiquetas de aplicación automática](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="fe5a3-117">Utilice las siguientes instrucciones para los dos pasos de administrador.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="fe5a3-118">Las directivas automáticas emplean etiquetado del lado del servicio con condiciones para aplicar etiquetas de retención automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="fe5a3-119">También puede aplicar automáticamente una etiqueta de retención con una directiva de etiqueta al hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="fe5a3-120">Aplique una etiqueta de retención predeterminada a una biblioteca de SharePoint, carpeta o conjunto de documentos para que el contenido sin etiquetar de ese contenedor se etiquete automáticamente</span><span class="sxs-lookup"><span data-stu-id="fe5a3-120">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="fe5a3-121">Aplicar automáticamente una etiqueta de retención al correo electrónico mediante el uso de reglas</span><span class="sxs-lookup"><span data-stu-id="fe5a3-121">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="fe5a3-122">Para estos escenarios, consulte [Crear y aplicar etiquetas de retención en aplicaciones](create-apply-retention-labels.md).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-122">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fe5a3-123">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="fe5a3-123">Before you begin</span></span>

<span data-ttu-id="fe5a3-124">El administrador global de su organización tiene permisos totales para crear y modificar etiquetas de retención y las directivas de las mismas.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-124">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="fe5a3-125">Si no va a iniciar sesión como administrador global, consulte [Permisos necesarios para crear y administrar directivas de retención y etiquetas de retención](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-125">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="fe5a3-126">Cómo aplicar automáticamente una etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="fe5a3-126">How to auto-apply a retention label</span></span>

<span data-ttu-id="fe5a3-127">En primer lugar, cree la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-127">First, create your retention label.</span></span> <span data-ttu-id="fe5a3-128">A continuación, cree una directiva automática para aplicar dicha etiqueta.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-128">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="fe5a3-129">Si ya ha creado la etiqueta de retención, consulte [Crear una directiva automática](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-129">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="fe5a3-130">Las instrucciones de navegación dependerán de si está usando o no la [administración de registros](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-130">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="fe5a3-131">Se proporcionan instrucciones para ambos escenarios.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-131">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="fe5a3-132">Paso 1: Cree una etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="fe5a3-132">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="fe5a3-133">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="fe5a3-134">Si utiliza la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-134">If you are using records management:</span></span>
        - <span data-ttu-id="fe5a3-135">**Soluciones** > **Administración de registros** > pestaña**Plan de archivos** tab > **+ Crear una etiqueta** > **Etiqueta de retención**</span><span class="sxs-lookup"><span data-stu-id="fe5a3-135">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="fe5a3-136">Si no está utilizando la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-136">If you are not using records management:</span></span>
       - <span data-ttu-id="fe5a3-137">**Soluciones** > **Gobierno de información** > pestaña**Etiquetas** > + **Crear una etiqueta**</span><span class="sxs-lookup"><span data-stu-id="fe5a3-137">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="fe5a3-138">¿No ve su opción inmediatamente?</span><span class="sxs-lookup"><span data-stu-id="fe5a3-138">Don't immediately see your option?</span></span> <span data-ttu-id="fe5a3-139">Primero seleccione **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="fe5a3-140">Siga las instrucciones del asistente.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-140">Follow the prompts in the wizard.</span></span> <span data-ttu-id="fe5a3-141">Si utiliza la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-141">If you are using records management:</span></span>
    
    - <span data-ttu-id="fe5a3-142">Para obtener información sobre los descriptores del plan de archivos, consulte [Usar plan de archivos para administrar etiquetas de retención](file-plan-manager.md) </span><span class="sxs-lookup"><span data-stu-id="fe5a3-142">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="fe5a3-143">Para usar la etiqueta de retención para declarar registros, seleccione **Marcar elementos como registros** o **Marcar elementos como registros normativos**.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-143">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="fe5a3-144">Para obtener más información, vea [Configurar etiquetas de retención para declarar registros](declare-records.md#configuring-retention-labels-to-declare-records).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-144">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="fe5a3-145">Después de crear la etiqueta y ver las opciones para publicar la etiqueta, aplique la etiqueta automáticamente o simplemente guárdela: seleccione **Aplicar esta etiqueta automáticamente a un tipo de contenido específico**y luego, seleccione **Finalizado** para iniciar el Asistente para la creación de etiquetas automáticas, que lo llevará directamente al paso 2 del procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-145">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="fe5a3-146">Para editar una etiqueta existente, selecciónela y después seleccione la opción **Editar etiqueta** para iniciar el Asistente de edición de etiquetas de retención, el cual le permite cambiar las descripciones de las etiquetas, así como cualquier [configuración que cumpla con los requisitos](#updating-retention-labels-and-their-policies) del paso 2.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-146">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="fe5a3-147">Paso 2: Cree una directiva de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="fe5a3-147">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="fe5a3-148">Cuando se crea una directiva de aplicación automática, se selecciona una etiqueta de retención para aplicarla automáticamente a contenido, en función de las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-148">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="fe5a3-149">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-149">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="fe5a3-150">Si utiliza la administración de registros:**Gobierno de información**:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-150">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="fe5a3-151">**Soluciones** > **Administración de registros** > pestaña de **Directivas de etiquetas** > **Aplicar etiqueta automáticamente**</span><span class="sxs-lookup"><span data-stu-id="fe5a3-151">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="fe5a3-152">Si no está utilizando la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-152">If you are not using records management:</span></span>
        - <span data-ttu-id="fe5a3-153">**Soluciones** > **Gobierno de información** > pestaña de **Directivas de etiquetas** > **Aplicar etiqueta automáticamente**</span><span class="sxs-lookup"><span data-stu-id="fe5a3-153">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="fe5a3-154">¿No ve su opción inmediatamente?</span><span class="sxs-lookup"><span data-stu-id="fe5a3-154">Don't immediately see your option?</span></span> <span data-ttu-id="fe5a3-155">Primero seleccione **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-155">First select **Show all**.</span></span> 

2. <span data-ttu-id="fe5a3-156">Siga las indicaciones del Asistente para la creación de etiquetas automáticas.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-156">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="fe5a3-157">Para obtener información sobre la configuración de las condiciones que aplican automáticamente la etiqueta de retención, consulte la sección [Configuración de las condiciones para la aplicación automática de etiquetas de retención en](#configuring-conditions-for-auto-apply-retention-labels) esta página.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-157">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="fe5a3-158">Para obtener información sobre las ubicaciones compatibles con las etiquetas de retención, vea la sección [Etiquetas de retención y ubicaciones](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-158">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="fe5a3-159">Para editar una directiva existente de aplicación automática, selecciónela para iniciar el Asistente para editar directivas de retención, el cual le permite cambiar la etiqueta de retención seleccionada, así como cualquier [configuración que cumpla con los requisitos](#updating-retention-labels-and-their-policies) del paso 2.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-159">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="fe5a3-160">Configurar las condiciones para la aplicación automática de etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="fe5a3-160">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="fe5a3-161">Puede aplicar etiquetas de retención al contenido automáticamente cuando éste contiene:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-161">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="fe5a3-162">Tipos específicos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="fe5a3-162">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="fe5a3-163">Palabras clave específicas o propiedades que permiten búsquedas que coinciden con una consulta que usted creó</span><span class="sxs-lookup"><span data-stu-id="fe5a3-163">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="fe5a3-164">Una coincidencia para clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="fe5a3-164">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="fe5a3-165">Aplicar automáticamente etiquetas a los contenidos con tipos específicos de información sensible</span><span class="sxs-lookup"><span data-stu-id="fe5a3-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="fe5a3-166">Al crear etiquetas de retención de aplicación automática para información confidencial, verá la misma lista de plantillas de directiva que cuando se crea una directiva de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-166">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="fe5a3-167">Cada plantilla está preconfigurada para buscar determinados tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-167">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="fe5a3-168">Por ejemplo, la plantilla que se muestra aquí busca los números de ITIN, SSN y pasaporte de Estados Unidos de la categoría **Privacidad** y de la **Plantilla de datos de identificación personal (PII) de Estados Unidos**:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![Plantillas de directiva con tipos de información confidencial](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="fe5a3-170">Para obtener más información sobre los tipos de información confidencial, consulte [Definiciones de entidad del tipo de información confidencial](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-170">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="fe5a3-171">Después de seleccionar una plantilla de directiva, puede agregar o quitar cualquier tipo de información confidencial y cambiar el recuento de instancias y la precisión de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="fe5a3-172">En el recorte de pantalla de ejemplo que se muestra a continuación, solo se aplicará la etiqueta de retención automáticamente cuando:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-172">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="fe5a3-173">El tipo de información confidencial que se detecta tiene una precisión de coincidencia (o nivel de confianza) de al menos 75.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="fe5a3-174">Muchos tipos de información confidencial se definen con varios patrones, donde un patrón con una mayor precisión de coincidencia requiere más pruebas para ser encontrado (por ejemplo, palabras clave, fechas o direcciones), mientras que un patrón con una precisión de coincidencia inferior requiere menos pruebas.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="fe5a3-175">Cuanto menor sea la precisión de coincidencia **mín**, más fácil será que el contenido coincida con la condición.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="fe5a3-176">El contenido tenga entre 1 y 9 instancias de cualquiera de estos tres tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-176">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="fe5a3-177">Puede eliminar el valor **hasta** para cambiarlo a **Cualquiera**.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-177">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="fe5a3-178">Para obtener más información sobre estas opciones, consulte las siguientes instrucciones de la documentación DLP: [Ajustar las reglas para que sea más o menos fácil que coincidan](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-178">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opciones para identificar tipos de información confidencial](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="fe5a3-180">Aplicar automáticamente etiquetas a contenido con palabras clave o propiedades que se puedan buscar</span><span class="sxs-lookup"><span data-stu-id="fe5a3-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="fe5a3-p114">Puede aplicar etiquetas automáticamente al contenido mediante una consulta que contenga palabras, frases o valores de propiedades que permiten búsquedas específicos. Puede restringir la consulta con operadores de búsqueda como Y, O y NO.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-p114">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Editor de consultas](../media/new-retention-query-editor.png)

<span data-ttu-id="fe5a3-184">Para obtener más información sobre la sintaxis de consulta que usa el Lenguaje de consultas de palabras clave (KQL), vea [Referencia de la sintaxis del Lenguaje de consultas de palabras clave (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-184">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="fe5a3-185">Las etiquetas basadas en consultas usan el índice de búsqueda para identificar contenido.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-185">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="fe5a3-186">Para obtener más información sobre las propiedades que permiten búsquedas que puede usar, vea:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-186">For more information about the searchable properties that you can use, see:</span></span>

- <span data-ttu-id="fe5a3-187">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-187">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
- [<span data-ttu-id="fe5a3-188">Información general sobre las propiedades administradas y rastreadas en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="fe5a3-188">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="fe5a3-189">Aunque las propiedades administradas de SharePoint admiten alias, no los utilice cuando configure las etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-189">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="fe5a3-190">Siempre debe especificar el nombre real de la propiedad administrada, por ejemplo, "RefinableString01".</span><span class="sxs-lookup"><span data-stu-id="fe5a3-190">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="fe5a3-191">Consultas de ejemplos:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-191">Examples queries:</span></span>

| <span data-ttu-id="fe5a3-192">Carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="fe5a3-192">Workload</span></span> | <span data-ttu-id="fe5a3-193">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe5a3-193">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="fe5a3-194">Exchange</span><span class="sxs-lookup"><span data-stu-id="fe5a3-194">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="fe5a3-195">Exchange</span><span class="sxs-lookup"><span data-stu-id="fe5a3-195">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="fe5a3-196">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe5a3-196">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="fe5a3-197">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe5a3-197">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="fe5a3-198">Grabaciones de reuniones de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe5a3-198">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="fe5a3-199">La posibilidad de conservar y eliminar las grabaciones de reuniones de Teams se está implementando en la versión preliminar y no funcionará antes de guardar las grabaciones en OneDrive o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-199">The ability to retain and delete Teams meeting recordings is rolling out in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="fe5a3-200">Para más información, consulte [Usar OneDrive para la Empresa y SharePoint Online o Stream para las grabaciones de reuniones](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-200">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="fe5a3-201">Para identificar las grabaciones de reuniones de Microsoft Teams almacenadas en cuentas de OneDrive de los usuarios o en SharePoint, especifique lo siguiente para el **Editor de consultas de palabras clave**:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-201">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="fe5a3-202">En el caso de esta etiqueta de retención, también tiene que publicarla en los sitios de SharePoint o en las cuentas de OneDrive de los usuarios relevantes mediante la creación de una directiva de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-202">For this retention label, you must also publish it to the relevant users' OneDrive accounts or SharePoint sites by creating a label policy.</span></span> <span data-ttu-id="fe5a3-203">La mayoría de las veces, las grabaciones de reuniones se guardan en OneDrive, pero, en el caso de las reuniones de canal, las grabaciones se guardan en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-203">Most of the time, the meeting recordings are saved to OneDrive, but for channel meetings, they are saved in SharePoint.</span></span>

<span data-ttu-id="fe5a3-204">Cuando haya guardado la directiva de aplicación automática:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-204">When you have saved the auto-apply policy:</span></span>

1. <span data-ttu-id="fe5a3-205">Seleccione la pestaña **Directivas de etiqueta** > **Publicar etiquetas**</span><span class="sxs-lookup"><span data-stu-id="fe5a3-205">Select **Label policies** tab > **Publish labels**</span></span>

2. <span data-ttu-id="fe5a3-206">Cuando se le pida que seleccione una etiqueta, elija la etiqueta que haya creado con la consulta KQL para identificar las grabaciones de reuniones de Teams.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-206">When prompted to select a label, choose the label you created with the KQL query to identify Teams meeting recordings.</span></span>

3. <span data-ttu-id="fe5a3-207">Cuando se le pida seleccionar la ubicación, elija **Sitios de SharePoint** y **Cuentas de OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-207">When prompted for the location, choose **SharePoint sites** and **OneDrive accounts**.</span></span> <span data-ttu-id="fe5a3-208">A continuación, puede mantener el valor predeterminado de **Todo** o especificar ubicaciones individuales. Por ejemplo, puede incluir o excluir cuentas de OneDrive específicas.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-208">You can then keep the default of **All**, or specify individual locations, such as including or excluding specific OneDrive accounts.</span></span>

4. <span data-ttu-id="fe5a3-209">Complete el asistente y guarde esta directiva de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-209">Complete the wizard and save this label policy.</span></span>

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="fe5a3-210">Aplicar automáticamente etiquetas al contenido con clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="fe5a3-210">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="fe5a3-211">Si elige la opción para un clasificador que se puede entrenar, puede seleccionar uno de los clasificadores integrado o un clasificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-211">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="fe5a3-212">Los clasificadores integrados incluyen **Currículum**, **Código fuente**, **Código fuente**, **Acoso selectivo**, **Amenazas**:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-212">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Elegir clasificador que se puede entrenar](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="fe5a3-214">Estamos desaprobando el clasificador incorporado de **Lenguaje ofensivo** porque ha estado produciendo un alto número de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-214">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="fe5a3-215">No use este clasificador incorporado y si lo está usando actualmente, debería mover sus procesos de negocios fuera de él.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-215">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="fe5a3-216">Recomendamos que usen los clasificadores integrados de**Acoso selectivo**, **Blasfemias**, **Amenazas**</span><span class="sxs-lookup"><span data-stu-id="fe5a3-216">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="fe5a3-217">Para aplicar una etiqueta automáticamente usando esta opción, los buzones y sitios de SharePoint deben tener al menos 10 MB de datos.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-217">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="fe5a3-218">Para más información sobre los clasificadores capacitados, consulte [Introducción a los clasificadores capacitados (versión preliminar)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="fe5a3-218">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="fe5a3-219">Si usa clasificadores capacitados para Exchange, consulte [Cómo volver a entrenar a un clasificador en el explorador de contenido (versión preliminar)](classifier-how-to-retrain-content-explorer.md) recientemente lanzado.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-219">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="fe5a3-220">Tiempo que tardan las etiquetas de retención en aplicarse</span><span class="sxs-lookup"><span data-stu-id="fe5a3-220">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="fe5a3-221">Si aplica automáticamente las etiquetas de retención, puede tardar hasta siete días en aplicar las etiquetas de retención a todo el contenido existente que coincida con las condiciones.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-221">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagrama de cuándo entran en vigor las etiquetas de aplicación automática](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="fe5a3-223">Actualización de las etiquetas de retención y de sus directivas</span><span class="sxs-lookup"><span data-stu-id="fe5a3-223">Updating retention labels and their policies</span></span>

<span data-ttu-id="fe5a3-224">Si edita una etiqueta de retención o una directiva de aplicación automática y la etiqueta de retención ya se aplica al contenido, la configuración actualizada se aplicará automáticamente a este contenido, además de al contenido recién identificado.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-224">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="fe5a3-225">Después de crear y guardar la etiqueta o la directiva, no se pueden cambiar algunas opciones de configuración, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="fe5a3-225">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="fe5a3-226">La configuración de retención excepto el período de retención, a menos que haya configurado la etiqueta para conservar o eliminar el contenido en función de cuándo se creó.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-226">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="fe5a3-227">La opción de marcar los elementos como un registro.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-227">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fe5a3-228">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fe5a3-228">Next steps</span></span>

<span data-ttu-id="fe5a3-229">Consulte [Usar las etiquetas de retención para administrar el ciclo de vida de los documentos almacenados en SharePoint](auto-apply-retention-labels-scenario.md) para obtener un escenario de ejemplo que usa una directiva de aplicación automática con propiedades administradas en SharePoint y una retención basada en eventos para iniciar el período de retención.</span><span class="sxs-lookup"><span data-stu-id="fe5a3-229">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
