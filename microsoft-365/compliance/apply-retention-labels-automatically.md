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
ms.openlocfilehash: 088a521089d34e74865c94b3cd147b02f8d812cb
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816973"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="dfe23-103">Aplicar una etiqueta de retención automáticamente para conservar o eliminar contenido</span><span class="sxs-lookup"><span data-stu-id="dfe23-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="dfe23-104">*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="dfe23-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dfe23-105">Una de las características más eficaces de las [etiquetas de retención](retention.md) es la capacidad de aplicarlas automáticamente al contenido que coincide con condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="dfe23-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="dfe23-106">En este caso, no es necesario que las personas de la organización apliquen las etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="dfe23-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="dfe23-107">Microsoft 365 realiza el trabajo por ellos.</span><span class="sxs-lookup"><span data-stu-id="dfe23-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="dfe23-108">Las etiquetas de retención auto aplicadas son poderosas porque:</span><span class="sxs-lookup"><span data-stu-id="dfe23-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="dfe23-109">No es necesario formar a los usuarios para que conozcan todas las clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="dfe23-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="dfe23-110">No es necesario depender de los usuarios para clasificar todo el contenido correctamente.</span><span class="sxs-lookup"><span data-stu-id="dfe23-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="dfe23-111">Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.</span><span class="sxs-lookup"><span data-stu-id="dfe23-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="dfe23-112">Las etiquetas de retención se pueden aplicar a contenido automáticamente cuando dicho contenido contiene información confidencial, palabras clave o propiedades que permiten búsquedas, o una coincidencia para [clasificadores que se puedan entrenar](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="dfe23-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="dfe23-113">Los procesos para aplicar automáticamente una etiqueta de retención se basan en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="dfe23-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![Diagrama de roles y tareas para etiquetas de aplicación automática](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="dfe23-115">Utilice las siguientes instrucciones para los dos pasos de administrador.</span><span class="sxs-lookup"><span data-stu-id="dfe23-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="dfe23-116">Las directivas automáticas emplean etiquetado del lado del servicio con condiciones para aplicar etiquetas de retención automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dfe23-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="dfe23-117">También puede aplicar automáticamente una etiqueta de retención con una directiva de etiqueta al hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dfe23-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="dfe23-118">Aplique una etiqueta de retención predeterminada a una biblioteca de SharePoint, carpeta o conjunto de documentos para que el contenido sin etiquetar de ese contenedor se etiquete automáticamente</span><span class="sxs-lookup"><span data-stu-id="dfe23-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="dfe23-119">Aplicar automáticamente una etiqueta de retención al correo electrónico mediante el uso de reglas</span><span class="sxs-lookup"><span data-stu-id="dfe23-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="dfe23-120">Para estos escenarios, consulte [Crear y aplicar etiquetas de retención en aplicaciones](create-apply-retention-labels.md).</span><span class="sxs-lookup"><span data-stu-id="dfe23-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dfe23-121">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="dfe23-121">Before you begin</span></span>

<span data-ttu-id="dfe23-122">El administrador global de su organización tiene permisos totales para crear y modificar etiquetas de retención y las directivas de las mismas.</span><span class="sxs-lookup"><span data-stu-id="dfe23-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="dfe23-123">Si no va a iniciar sesión como administrador global, consulte [Permisos necesarios para crear y administrar directivas de retención y etiquetas de retención](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="dfe23-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="dfe23-124">Cómo aplicar automáticamente una etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="dfe23-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="dfe23-125">En primer lugar, cree la etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="dfe23-125">First, create your retention label.</span></span> <span data-ttu-id="dfe23-126">A continuación, cree una directiva automática para aplicar dicha etiqueta.</span><span class="sxs-lookup"><span data-stu-id="dfe23-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="dfe23-127">Si ya ha creado la etiqueta de retención, consulte [Crear una directiva automática](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="dfe23-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="dfe23-128">Las instrucciones de navegación dependerán de si está usando o no la [administración de registros](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="dfe23-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="dfe23-129">Se proporcionan instrucciones para ambos escenarios.</span><span class="sxs-lookup"><span data-stu-id="dfe23-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="dfe23-130">Paso 1: Cree una etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="dfe23-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="dfe23-131">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="dfe23-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="dfe23-132">Si utiliza la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="dfe23-132">If you are using records management:</span></span>
        - <span data-ttu-id="dfe23-133">**Soluciones** > **Administración de registros** > pestaña**Plan de archivos** tab > **+ Crear una etiqueta** > **Etiqueta de retención**</span><span class="sxs-lookup"><span data-stu-id="dfe23-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="dfe23-134">Si no está utilizando la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="dfe23-134">If you are not using records management:</span></span>
       - <span data-ttu-id="dfe23-135">**Soluciones** > **Gobierno de información** > pestaña**Etiquetas** > + **Crear una etiqueta**</span><span class="sxs-lookup"><span data-stu-id="dfe23-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="dfe23-136">¿No ve su opción inmediatamente?</span><span class="sxs-lookup"><span data-stu-id="dfe23-136">Don't immediately see your option?</span></span> <span data-ttu-id="dfe23-137">Primero seleccione **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="dfe23-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="dfe23-138">Siga las instrucciones del asistente.</span><span class="sxs-lookup"><span data-stu-id="dfe23-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="dfe23-139">Si utiliza la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="dfe23-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="dfe23-140">Para obtener información sobre los descriptores del plan de archivos, consulte [Usar plan de archivos para administrar etiquetas de retención](file-plan-manager.md) </span><span class="sxs-lookup"><span data-stu-id="dfe23-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="dfe23-141">Para usar la etiqueta de retención para declarar un [registro](records-management.md#records), habilite la opción **Marcar elementos como registro**.</span><span class="sxs-lookup"><span data-stu-id="dfe23-141">To use the retention label to declare a [record](records-management.md#records), enable the option **Mark items as a record**.</span></span>

3. <span data-ttu-id="dfe23-142">Después de crear la etiqueta y ver las opciones para publicar la etiqueta, aplique la etiqueta automáticamente o simplemente guárdela: seleccione **Aplicar esta etiqueta automáticamente a un tipo de contenido específico**y luego, seleccione **Finalizado** para iniciar el Asistente para la creación de etiquetas automáticas, que lo llevará directamente al paso 2 del procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="dfe23-142">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="dfe23-143">Para editar una etiqueta existente, selecciónela y después seleccione la opción **Editar etiqueta** para iniciar el Asistente de edición de etiquetas de retención, el cual le permite cambiar las descripciones de las etiquetas, así como cualquier [configuración que cumpla con los requisitos](#updating-retention-labels-and-their-policies) del paso 2.</span><span class="sxs-lookup"><span data-stu-id="dfe23-143">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="dfe23-144">Paso 2: Cree una directiva de aplicación automática</span><span class="sxs-lookup"><span data-stu-id="dfe23-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="dfe23-145">Cuando se crea una directiva de aplicación automática, se selecciona una etiqueta de retención para aplicarla automáticamente a contenido, en función de las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="dfe23-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="dfe23-146">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:</span><span class="sxs-lookup"><span data-stu-id="dfe23-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="dfe23-147">Si utiliza la administración de registros:**Gobierno de información**:</span><span class="sxs-lookup"><span data-stu-id="dfe23-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="dfe23-148">**Soluciones** > **Administración de registros** > pestaña de **Directivas de etiquetas** > **Aplicar etiqueta automáticamente**</span><span class="sxs-lookup"><span data-stu-id="dfe23-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="dfe23-149">Si no está utilizando la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="dfe23-149">If you are not using records management:</span></span>
        - <span data-ttu-id="dfe23-150">**Soluciones** > **Gobierno de información** > pestaña de **Directivas de etiquetas** > **Aplicar etiqueta automáticamente**</span><span class="sxs-lookup"><span data-stu-id="dfe23-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="dfe23-151">¿No ve su opción inmediatamente?</span><span class="sxs-lookup"><span data-stu-id="dfe23-151">Don't immediately see your option?</span></span> <span data-ttu-id="dfe23-152">Primero seleccione **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="dfe23-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="dfe23-153">Siga las indicaciones del Asistente para la creación de etiquetas automáticas.</span><span class="sxs-lookup"><span data-stu-id="dfe23-153">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="dfe23-154">Para obtener información sobre la configuración de las condiciones que aplican automáticamente la etiqueta de retención, consulte la sección [Configuración de las condiciones para la aplicación automática de etiquetas de retención en](#configuring-conditions-for-auto-apply-retention-labels) esta página.</span><span class="sxs-lookup"><span data-stu-id="dfe23-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="dfe23-155">Para obtener información sobre las ubicaciones compatibles con las etiquetas de retención, vea la sección [Etiquetas de retención y ubicaciones](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="dfe23-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="dfe23-156">Para editar una directiva existente de aplicación automática, selecciónela para iniciar el Asistente para editar directivas de retención, el cual le permite cambiar la etiqueta de retención seleccionada, así como cualquier [configuración que cumpla con los requisitos](#updating-retention-labels-and-their-policies) del paso 2.</span><span class="sxs-lookup"><span data-stu-id="dfe23-156">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="dfe23-157">Configurar las condiciones para la aplicación automática de etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="dfe23-157">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="dfe23-158">Puede aplicar etiquetas de retención al contenido automáticamente cuando éste contiene:</span><span class="sxs-lookup"><span data-stu-id="dfe23-158">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="dfe23-159">Tipos específicos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="dfe23-159">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="dfe23-160">Palabras clave específicas o propiedades que permiten búsquedas que coinciden con una consulta que usted creó</span><span class="sxs-lookup"><span data-stu-id="dfe23-160">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="dfe23-161">Una coincidencia para clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="dfe23-161">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="dfe23-162">Aplicar automáticamente etiquetas a los contenidos con tipos específicos de información sensible</span><span class="sxs-lookup"><span data-stu-id="dfe23-162">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="dfe23-163">Al crear etiquetas de retención de aplicación automática para información confidencial, verá la misma lista de plantillas de directiva que cuando se crea una directiva de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="dfe23-163">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="dfe23-164">Cada plantilla está preconfigurada para buscar determinados tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="dfe23-164">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="dfe23-165">Por ejemplo, la plantilla que se muestra aquí busca los números de ITIN, SSN y pasaporte de Estados Unidos de la categoría **Privacidad** y de la **Plantilla de datos de identificación personal (PII) de Estados Unidos**:</span><span class="sxs-lookup"><span data-stu-id="dfe23-165">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![Plantillas de directiva con tipos de información confidencial](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="dfe23-167">Para obtener más información sobre los tipos de información confidencial, consulte [Definiciones de entidad del tipo de información confidencial](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="dfe23-167">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="dfe23-168">Después de seleccionar una plantilla de directiva, puede agregar o quitar cualquier tipo de información confidencial y cambiar el recuento de instancias y la precisión de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="dfe23-168">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="dfe23-169">En el recorte de pantalla de ejemplo que se muestra a continuación, solo se aplicará la etiqueta de retención automáticamente cuando:</span><span class="sxs-lookup"><span data-stu-id="dfe23-169">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="dfe23-170">El tipo de información confidencial que se detecta tiene una precisión de coincidencia (o nivel de confianza) de al menos 75.</span><span class="sxs-lookup"><span data-stu-id="dfe23-170">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="dfe23-171">Muchos tipos de información confidencial se definen con varios patrones, donde un patrón con una mayor precisión de coincidencia requiere más pruebas para ser encontrado (por ejemplo, palabras clave, fechas o direcciones), mientras que un patrón con una precisión de coincidencia inferior requiere menos pruebas.</span><span class="sxs-lookup"><span data-stu-id="dfe23-171">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="dfe23-172">Cuanto menor sea la precisión de coincidencia **mín**, más fácil será que el contenido coincida con la condición.</span><span class="sxs-lookup"><span data-stu-id="dfe23-172">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="dfe23-173">El contenido tenga entre 1 y 9 instancias de cualquiera de estos tres tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="dfe23-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="dfe23-174">Puede eliminar el valor **hasta** para cambiarlo a **Cualquiera**.</span><span class="sxs-lookup"><span data-stu-id="dfe23-174">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="dfe23-175">Para obtener más información sobre estas opciones, consulte las siguientes instrucciones de la documentación DLP: [Ajustar las reglas para que sea más o menos fácil que coincidan](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="dfe23-175">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opciones para identificar tipos de información confidencial](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="dfe23-177">Aplicar automáticamente etiquetas a contenido con palabras clave o propiedades que se puedan buscar</span><span class="sxs-lookup"><span data-stu-id="dfe23-177">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="dfe23-p113">Puede aplicar etiquetas automáticamente al contenido mediante una consulta que contenga palabras, frases o valores de propiedades que permiten búsquedas específicos. Puede restringir la consulta con operadores de búsqueda como Y, O y NO.</span><span class="sxs-lookup"><span data-stu-id="dfe23-p113">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Editor de consultas](../media/new-retention-query-editor.png)

<span data-ttu-id="dfe23-181">Para obtener más información sobre la sintaxis de consulta que usa el Lenguaje de consultas de palabras clave (KQL), vea [Referencia de la sintaxis del Lenguaje de consultas de palabras clave (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="dfe23-181">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="dfe23-182">Las etiquetas basadas en consultas usan el índice de búsqueda para identificar contenido.</span><span class="sxs-lookup"><span data-stu-id="dfe23-182">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="dfe23-183">Para obtener más información sobre las propiedades que permiten búsquedas que puede usar, vea:</span><span class="sxs-lookup"><span data-stu-id="dfe23-183">For more information about the searchable properties that you can use, see:</span></span>

- <span data-ttu-id="dfe23-184">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="dfe23-184">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
- [<span data-ttu-id="dfe23-185">Información general sobre las propiedades administradas y rastreadas en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="dfe23-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="dfe23-186">Aunque las propiedades administradas de SharePoint admiten alias, no los utilice cuando configure las etiquetas de retención.</span><span class="sxs-lookup"><span data-stu-id="dfe23-186">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="dfe23-187">Siempre debe especificar el nombre real de la propiedad administrada, por ejemplo, "RefinableString01".</span><span class="sxs-lookup"><span data-stu-id="dfe23-187">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="dfe23-188">Consultas de ejemplos:</span><span class="sxs-lookup"><span data-stu-id="dfe23-188">Examples queries:</span></span>

| <span data-ttu-id="dfe23-189">Carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="dfe23-189">Workload</span></span> | <span data-ttu-id="dfe23-190">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfe23-190">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="dfe23-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="dfe23-191">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="dfe23-192">Exchange</span><span class="sxs-lookup"><span data-stu-id="dfe23-192">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="dfe23-193">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dfe23-193">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="dfe23-194">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dfe23-194">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="dfe23-195">Aplicar automáticamente etiquetas al contenido con clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="dfe23-195">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="dfe23-196">Si elige la opción para un clasificador que se puede entrenar, puede seleccionar uno de los clasificadores integrado o un clasificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="dfe23-196">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="dfe23-197">Los clasificadores integrados incluyen **Currículum**, **Código fuente**, **Código fuente**, **Acoso selectivo**, **Amenazas**:</span><span class="sxs-lookup"><span data-stu-id="dfe23-197">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Elegir clasificador que se puede entrenar](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="dfe23-199">Estamos desaprobando el clasificador incorporado de **Lenguaje ofensivo** porque ha estado produciendo un alto número de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="dfe23-199">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="dfe23-200">No use este clasificador incorporado y si lo está usando actualmente, debería mover sus procesos de negocios fuera de él.</span><span class="sxs-lookup"><span data-stu-id="dfe23-200">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="dfe23-201">Recomendamos que usen los clasificadores integrados de**Acoso selectivo**, **Blasfemias**, **Amenazas**</span><span class="sxs-lookup"><span data-stu-id="dfe23-201">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="dfe23-202">Para aplicar una etiqueta automáticamente usando esta opción, los buzones y sitios de SharePoint deben tener al menos 10 MB de datos.</span><span class="sxs-lookup"><span data-stu-id="dfe23-202">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="dfe23-203">Para obtener más información sobre los clasificadores que se pueden entrenar, consulte [Introducción al entrenamiento de clasificadores (vista previa)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="dfe23-203">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="dfe23-204">Para obtener un ejemplo de configuración, consulte [cómo preparar y usar un clasificador integrado](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="dfe23-204">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="dfe23-205">Tiempo que tardan las etiquetas de retención en aplicarse</span><span class="sxs-lookup"><span data-stu-id="dfe23-205">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="dfe23-206">Si aplica automáticamente las etiquetas de retención, puede tardar hasta siete días en aplicar las etiquetas de retención a todo el contenido existente que coincida con las condiciones.</span><span class="sxs-lookup"><span data-stu-id="dfe23-206">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagrama de cuándo entran en vigor las etiquetas de aplicación automática](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="dfe23-208">Actualización de las etiquetas de retención y de sus directivas</span><span class="sxs-lookup"><span data-stu-id="dfe23-208">Updating retention labels and their policies</span></span>

<span data-ttu-id="dfe23-209">Si edita una etiqueta de retención o una directiva de aplicación automática y la etiqueta de retención ya se aplica al contenido, la configuración actualizada se aplicará automáticamente a este contenido, además de al contenido recién identificado.</span><span class="sxs-lookup"><span data-stu-id="dfe23-209">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="dfe23-210">Después de crear y guardar la etiqueta o la directiva, no se pueden cambiar algunas opciones de configuración, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="dfe23-210">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="dfe23-211">La configuración de retención excepto el período de retención, a menos que haya configurado la etiqueta para conservar o eliminar el contenido en función de cuándo se creó.</span><span class="sxs-lookup"><span data-stu-id="dfe23-211">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="dfe23-212">La opción de marcar los elementos como un registro.</span><span class="sxs-lookup"><span data-stu-id="dfe23-212">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dfe23-213">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="dfe23-213">Next steps</span></span>

<span data-ttu-id="dfe23-214">Consulte [Usar las etiquetas de retención para administrar el ciclo de vida de los documentos almacenados en SharePoint](auto-apply-retention-labels-scenario.md) para obtener un escenario de ejemplo que usa una directiva de aplicación automática con propiedades administradas en SharePoint y una retención basada en eventos para iniciar el período de retención.</span><span class="sxs-lookup"><span data-stu-id="dfe23-214">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
