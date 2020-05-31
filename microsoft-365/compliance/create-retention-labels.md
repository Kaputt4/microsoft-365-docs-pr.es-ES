---
title: Crear, publicar y aplicar automáticamente etiquetas de retención
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
description: Instrucciones para crear, publicar y aplicar automáticamente etiquetas de retención para retener lo que se necesita, eliminar lo que no se necesita y declarar un elemento como un registro en el entorno de Office 365.
ms.openlocfilehash: 65319baa0fd238ebdc403307fb8bb91a59d87cd6
ms.sourcegitcommit: 3cd487476efe4138d1b42499fbffbbe4bacfe5b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "44408472"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="894b6-103">Crear, publicar y aplicar automáticamente etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="894b6-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="894b6-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="894b6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="894b6-105">Utilice la siguiente información para ayudarle a crear [etiquetas de retención](labels.md), y luego aplicarlas automáticamente a los documentos y correos electrónicos, o publicarlas para que los usuarios puedan aplicarlas manualmente.</span><span class="sxs-lookup"><span data-stu-id="894b6-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="894b6-106">Las etiquetas de retención lo ayudan a retener lo que necesita y a eliminar lo que no.</span><span class="sxs-lookup"><span data-stu-id="894b6-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="894b6-107">También se utilizan para declarar un artículo como registro como parte de una solución de[administración de registros](records-management.md) para sus datos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="894b6-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="894b6-108">El lugar donde se crean y configuran las etiquetas de retención depende de si se utiliza la administración de registros o no.</span><span class="sxs-lookup"><span data-stu-id="894b6-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="894b6-109">Se proporcionan instrucciones para ambos escenarios.</span><span class="sxs-lookup"><span data-stu-id="894b6-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="894b6-110">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="894b6-110">Before you begin</span></span>

<span data-ttu-id="894b6-111">Los miembros de su equipo de cumplimiento que vayan a crear las etiquetas de retención necesitan permisos para el Centro de &amp;Seguridad y Cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="894b6-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="894b6-112">De forma predeterminada, el administrador de inquilinos tendrá acceso a esta ubicación y puede otorgar acceso a los oficiales de cumplimiento y a otros usuarios al Centro de &amp;Cumplimiento y Seguridad, sin concederles todos los permisos de un administrador de inquilinos. Para hacerlo, le recomendamos que vaya a la página **Permisos** del Centro de &amp;Cumplimiento y Seguridad, edite el grupo de roles del **Administrador de Cumplimiento** y agregue miembros a ese grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="894b6-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="894b6-113">Para obtener más información, vea [Conceder acceso a los usuarios al Centro de seguridad y cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="894b6-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="894b6-p104">Estos permisos solo son necesarios para crear y aplicar etiquetas de retención y una directiva de etiquetas. La aplicación de directivas no necesita acceso al contenido.</span><span class="sxs-lookup"><span data-stu-id="894b6-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="894b6-116">Crear y configurar las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="894b6-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="894b6-117">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:</span><span class="sxs-lookup"><span data-stu-id="894b6-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="894b6-118">Si utiliza la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="894b6-118">If you are using records management:</span></span>
        - <span data-ttu-id="894b6-119">**Soluciones** > **Administración de registros** > pestaña**Plan de archivos** tab > **+ Crear una etiqueta** > **Etiqueta de retención**</span><span class="sxs-lookup"><span data-stu-id="894b6-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="894b6-120">Si no está utilizando la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="894b6-120">If you are not using records management:</span></span>
       - <span data-ttu-id="894b6-121">**Soluciones** > **Gobierno de información** > pestaña**Etiquetas** > + **Crear una etiqueta**</span><span class="sxs-lookup"><span data-stu-id="894b6-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="894b6-122">¿No ve su opción inmediatamente?</span><span class="sxs-lookup"><span data-stu-id="894b6-122">Don't immediately see your option?</span></span> <span data-ttu-id="894b6-123">Primero seleccione **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="894b6-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="894b6-124">Siga las instrucciones del asistente.</span><span class="sxs-lookup"><span data-stu-id="894b6-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="894b6-125">Si utiliza la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="894b6-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="894b6-126">Para obtener información sobre los descriptores del plan de archivos, consulte [Descripción general del administrador del plan de archivos](file-plan-manager.md) </span><span class="sxs-lookup"><span data-stu-id="894b6-126">For information about the file plan descriptors, see [Overview of file plan manager](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="894b6-127">Para utilizar la etiqueta de retención para declarar el contenido como un registro, active la casilla de verificación**Utilizar la etiqueta para clasificar el contenido como "Registro"**.</span><span class="sxs-lookup"><span data-stu-id="894b6-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="894b6-128">Repita estos pasos para crear más etiquetas.</span><span class="sxs-lookup"><span data-stu-id="894b6-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="894b6-129">Para editar una etiqueta existente, selecciónela, y luego seleccione **Editar etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="894b6-129">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="894b6-130">Esto inicia el mismo asistente, que le permite cambiar las descripciones de las etiquetas y los ajustes en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="894b6-130">This starts the same wizard, which lets you change the label descriptions and settings in step 2.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="894b6-131">Publicar etiquetas de retención creando una directiva de etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="894b6-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="894b6-132">Publicar etiquetas de retención para que puedan ser aplicadas manualmente por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="894b6-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="894b6-133">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:</span><span class="sxs-lookup"><span data-stu-id="894b6-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="894b6-134">Si utiliza la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="894b6-134">If you are using records management:</span></span>
        - <span data-ttu-id="894b6-135">**Soluciones** > **Administración de registros \*\* > > pestaña**Directivas de etiquetas\*\* > **Etiquetas publicadas**</span><span class="sxs-lookup"><span data-stu-id="894b6-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="894b6-136">Si no está utilizando la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="894b6-136">If you are not using records management:</span></span>
        - <span data-ttu-id="894b6-137">**Soluciones** > **Gobierno de información** > pestaña**Directivas de etiquetas** > **Publicar etiquetas**</span><span class="sxs-lookup"><span data-stu-id="894b6-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="894b6-138">¿No ve su opción inmediatamente?</span><span class="sxs-lookup"><span data-stu-id="894b6-138">Don't immediately see your option?</span></span> <span data-ttu-id="894b6-139">Primero seleccione **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="894b6-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="894b6-140">Siga las instrucciones del asistente.</span><span class="sxs-lookup"><span data-stu-id="894b6-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="894b6-141">Para obtener información sobre las ubicaciones compatibles con las etiquetas de retención, vea la sección [Etiquetas de retención y ubicaciones](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="894b6-141">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span> 

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="894b6-142">Aplicar automáticamente una etiqueta de retención</span><span class="sxs-lookup"><span data-stu-id="894b6-142">Auto-apply a retention label</span></span>

<span data-ttu-id="894b6-143">Aplica automáticamente una etiqueta de retención, basada en las condiciones que especifiques.</span><span class="sxs-lookup"><span data-stu-id="894b6-143">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="894b6-144">En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/), desplácese hasta una de las siguientes locaciones:</span><span class="sxs-lookup"><span data-stu-id="894b6-144">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="894b6-145">Si utiliza la administración de registros:**Gobierno de información**:</span><span class="sxs-lookup"><span data-stu-id="894b6-145">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="894b6-146">**Soluciones** > **Administración de registros \*\* > pestaña**Directivas de etiquetas **>** Aplicar automáticamente etiquetas\*\*</span><span class="sxs-lookup"><span data-stu-id="894b6-146">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="894b6-147">Si no está utilizando la administración de registros:</span><span class="sxs-lookup"><span data-stu-id="894b6-147">If you are not using records management:</span></span>
        - <span data-ttu-id="894b6-148">**Soluciones** > **Gobierno de información** > pestaña**Directivas de etiquetas** > **Aplicar automáticamente etiquetas**</span><span class="sxs-lookup"><span data-stu-id="894b6-148">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="894b6-149">¿No ve su opción inmediatamente?</span><span class="sxs-lookup"><span data-stu-id="894b6-149">Don't immediately see your option?</span></span> <span data-ttu-id="894b6-150">Primero seleccione **Mostrar todo**.</span><span class="sxs-lookup"><span data-stu-id="894b6-150">First select **Show all**.</span></span> 

2. <span data-ttu-id="894b6-151">Siga las instrucciones del asistente.</span><span class="sxs-lookup"><span data-stu-id="894b6-151">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="894b6-152">Para obtener información sobre la configuración de las condiciones que aplican automáticamente la etiqueta de retención, consulte la sección [Configuración de las condiciones para la aplicación automática de etiquetas de retención en](#configuring-conditions-for-auto-apply-retention-labels) esta página.</span><span class="sxs-lookup"><span data-stu-id="894b6-152">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="894b6-153">Para obtener información sobre las ubicaciones compatibles con las etiquetas de retención, vea la sección [Etiquetas de retención y ubicaciones](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="894b6-153">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="894b6-154">Configurar las condiciones para la aplicación automática de etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="894b6-154">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="894b6-155">Puede aplicar etiquetas de retención al contenido automáticamente cuando éste contiene:</span><span class="sxs-lookup"><span data-stu-id="894b6-155">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="894b6-156">Tipos específicos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="894b6-156">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="894b6-157">Palabras clave específicas que coinciden con una consulta que haya creado</span><span class="sxs-lookup"><span data-stu-id="894b6-157">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="894b6-158">Una coincidencia para clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="894b6-158">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![Página de selección de condición para una etiqueta de aplicación automática](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="894b6-160">Las etiquetas de retención aplicadas automáticamente puede tardar hasta siete días en aplicarse a todo el contenido que coincida con las condiciones que ha configurado.</span><span class="sxs-lookup"><span data-stu-id="894b6-160">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="894b6-161">Aplicar automáticamente etiquetas a los contenidos con tipos específicos de información sensible</span><span class="sxs-lookup"><span data-stu-id="894b6-161">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="894b6-162">Al crear etiquetas de retención de aplicación automática para información confidencial, verá la misma lista de plantillas de directiva que cuando se crea una directiva de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="894b6-162">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="894b6-163">Cada plantilla de directiva está preconfigurada para buscar determinados tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="894b6-163">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="894b6-164">Por ejemplo, la plantilla que se muestra aquí busca números de ITIN, SSN y pasaporte de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="894b6-164">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="894b6-165">Para obtener más información sobre DLP, vea [Información general sobre directivas de prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="894b6-165">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Plantillas de directiva con tipos de información confidencial](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="894b6-p111">Después de seleccionar una plantilla de directiva, puede agregar o quitar los tipos de información confidencial, así como cambiar el recuento de instancias y la precisión de coincidencia. En el ejemplo que se muestra aquí, solo se aplicará automáticamente una etiqueta de retención cuando:</span><span class="sxs-lookup"><span data-stu-id="894b6-p111">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="894b6-p112">El contenido tenga entre 1 y 9 instancias de alguno de estos tres tipos de información confidencial. Puede eliminar el valor **máximo** para que cambie a **cualquiera**.</span><span class="sxs-lookup"><span data-stu-id="894b6-p112">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="894b6-p113">El tipo de información confidencial detectado tiene una precisión de coincidencia (o nivel de confianza) mínima de 75. Muchos tipos de información confidencial se definen con varios patrones, donde un patrón con una precisión de coincidencia más alta necesita encontrar más evidencias (como palabras clave, fechas o direcciones), mientras que un patrón con una precisión de coincidencia inferior necesita menos evidencias. En resumen, cuanto menor sea la precisión de coincidencia **mínima**, más fácil será que el contenido coincida con la condición.</span><span class="sxs-lookup"><span data-stu-id="894b6-p113">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="894b6-174">Para obtener más información acerca de estas opciones, vea [Ajustar reglas para que sea más o menos fáciles que coincidan](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="894b6-174">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opciones para identificar tipos de información confidencial](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="894b6-176">Aplicar automáticamente etiquetas a contenido con palabras clave o propiedades que se puedan buscar</span><span class="sxs-lookup"><span data-stu-id="894b6-176">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="894b6-p114">Puede aplicar automáticamente etiquetas a contenido que cumpla determinadas condiciones. Las condiciones disponibles ahora permiten aplicar una etiqueta a contenido que coincida con palabras, frases o propiedades que puedan buscarse. Puede restringir la consulta con operadores de búsqueda como Y, O y NO.</span><span class="sxs-lookup"><span data-stu-id="894b6-p114">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="894b6-180">Para obtener más información sobre la sintaxis de consultas, vea:</span><span class="sxs-lookup"><span data-stu-id="894b6-180">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="894b6-181">Referencia de la sintaxis del lenguaje de consultas de palabras clave (KQL)</span><span class="sxs-lookup"><span data-stu-id="894b6-181">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="894b6-p115">Las etiquetas basadas en consultas usan el índice de búsqueda para identificar el contenido. Para obtener más información sobre las propiedades de búsqueda válidas, vea:</span><span class="sxs-lookup"><span data-stu-id="894b6-p115">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- <span data-ttu-id="894b6-184">[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="894b6-184">[Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md)</span></span>
- [<span data-ttu-id="894b6-185">Información general sobre las propiedades administradas y rastreadas en SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="894b6-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="894b6-186">Consultas de ejemplos:</span><span class="sxs-lookup"><span data-stu-id="894b6-186">Examples queries:</span></span>

- <span data-ttu-id="894b6-187">Exchange</span><span class="sxs-lookup"><span data-stu-id="894b6-187">Exchange</span></span>
    - <span data-ttu-id="894b6-188">asunto:"Finanzas trimestrales"</span><span class="sxs-lookup"><span data-stu-id="894b6-188">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="894b6-189">destinatarios: jorgem</span><span class="sxs-lookup"><span data-stu-id="894b6-189">recipients:garthf</span></span><!--nolink--><span data-ttu-id="894b6-190">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="894b6-190">@contoso.com</span></span>
- <span data-ttu-id="894b6-191">SharePoint y OneDrive</span><span class="sxs-lookup"><span data-stu-id="894b6-191">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="894b6-192">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="894b6-192">contenttype:contract</span></span>
    - <span data-ttu-id="894b6-193">sitio:https</span><span class="sxs-lookup"><span data-stu-id="894b6-193">site:https</span></span><!--nolink--><span data-ttu-id="894b6-194">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="894b6-194">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Editor de consultas](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="894b6-196">Aplicar automáticamente etiquetas al contenido con clasificadores que se pueden entrenar</span><span class="sxs-lookup"><span data-stu-id="894b6-196">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="894b6-197">Si elige la opción para un clasificador que se puede entrenar, puede seleccionar uno de los clasificadores integrado o un clasificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="894b6-197">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="894b6-198">Los clasificadores integrados incluyen **Currículum**, **Código fuente**, **Código fuente**, **Acoso selectivo**, **Amenazas**:</span><span class="sxs-lookup"><span data-stu-id="894b6-198">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Elegir clasificador que se puede entrenar](../media/retention-label-classifers.png)

<span data-ttu-id="894b6-200">Para aplicar una etiqueta automáticamente usando esta opción, los buzones y sitios de SharePoint Online deben tener al menos 10 MB de datos.</span><span class="sxs-lookup"><span data-stu-id="894b6-200">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="894b6-201">Para obtener más información sobre los clasificadores que se pueden entrenar, consulte [Introducción al entrenamiento de clasificadores (vista previa)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="894b6-201">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="894b6-202">Para obtener un ejemplo de configuración, consulte [cómo preparar y usar un clasificador integrado](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="894b6-202">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="894b6-203">Tiempo que tardan las etiquetas de retención en aplicarse</span><span class="sxs-lookup"><span data-stu-id="894b6-203">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="894b6-204">Al publicar o aplicar automáticamente etiquetas de retención, no surten efecto inmediatamente:</span><span class="sxs-lookup"><span data-stu-id="894b6-204">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="894b6-205">Primero, la directiva de etiquetas tiene que sincronizarse desde el centro de administración con las ubicaciones en la directiva.</span><span class="sxs-lookup"><span data-stu-id="894b6-205">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="894b6-206">Entonces la ubicación podría requerir tiempo para poner a disposición de los usuarios finales las etiquetas de retención publicadas o tiempo para aplicar automáticamente las etiquetas al contenido.</span><span class="sxs-lookup"><span data-stu-id="894b6-206">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="894b6-207">El tiempo que se tarda depende de la ubicación y el tipo de etiqueta de retención.</span><span class="sxs-lookup"><span data-stu-id="894b6-207">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="894b6-208">Etiquetas de retención publicadas</span><span class="sxs-lookup"><span data-stu-id="894b6-208">Published retention labels</span></span>

<span data-ttu-id="894b6-p118">Si publica etiquetas de retención en SharePoint o OneDrive, puede que tarden un día en mostrarse a los usuarios finales. Además, si publica etiquetas de retención en Exchange, pueden tardar hasta siete días en mostrarse a los usuarios finales y, además, el buzón necesita contener como mínimo 10 MB de datos.</span><span class="sxs-lookup"><span data-stu-id="894b6-p118">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![Diagrama de cuándo entran en vigor las etiquetas manuales](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="894b6-212">Aplicar automáticamente etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="894b6-212">Auto-apply retention labels</span></span>

<span data-ttu-id="894b6-213">Si aplica automáticamente etiquetas de retención a contenido que coincida con condiciones específicas, estas pueden tardar hasta siete días en aplicarse a todo el contenido existente que coincida con las condiciones.</span><span class="sxs-lookup"><span data-stu-id="894b6-213">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagrama de cuándo entran en vigor las etiquetas de aplicación automática](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="894b6-215">Cómo comprobar el estado de las etiquetas de retención publicadas en Exchange</span><span class="sxs-lookup"><span data-stu-id="894b6-215">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="894b6-216">En Exchange Online, las etiquetas de retención están disponibles para los usuarios finales mediante un proceso que se ejecuta cada siete días.</span><span class="sxs-lookup"><span data-stu-id="894b6-216">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="894b6-217">Mediante el uso de Powershell, se puede ver cuándo se ejecutó este proceso por última vez y así identificar cuándo se volverá a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="894b6-217">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="894b6-218">[Conéctese al PowerShell de Exchange Online](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="894b6-218">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="894b6-219">Ejecute estos comandos.</span><span class="sxs-lookup"><span data-stu-id="894b6-219">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="894b6-220">En los resultados, la propiedad `ELCLastSuccessTimeStamp` (UTC) muestra cuándo fue la última vez que el sistema procesó el buzón.</span><span class="sxs-lookup"><span data-stu-id="894b6-220">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="894b6-221">Si esto no ha ocurrido desde el momento en que se creó la directiva, las etiquetas no van a aparecer.</span><span class="sxs-lookup"><span data-stu-id="894b6-221">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="894b6-222">Para forzar el procesamiento, ejecute `Start-ManagedFolderAssistant -Identity <user>`.</span><span class="sxs-lookup"><span data-stu-id="894b6-222">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="894b6-223">Si las etiquetas no aparecen en Outlook en la Web y cree que tendrían que aparecer, asegúrese de vaciar la caché del explorador (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="894b6-223">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="894b6-224">Actualización de las etiquetas de retención y sus directivas</span><span class="sxs-lookup"><span data-stu-id="894b6-224">Updating retention labels and their policies</span></span>

<span data-ttu-id="894b6-225">Si edita una etiqueta de retención, una directiva de etiquetas de retención o una directiva de aplicación automática y la etiqueta de retención ya se aplica al contenido, la configuración actualizada se aplicará automáticamente a este contenido además del contenido recién etiquetado.</span><span class="sxs-lookup"><span data-stu-id="894b6-225">If you edit a retention label, retention label policy, or auto-apply policy and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly labeled.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="894b6-226">Encuentra los cmdlets de PowerShell para las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="894b6-226">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="894b6-227">Para usar la etiqueta de retención cmdlets:</span><span class="sxs-lookup"><span data-stu-id="894b6-227">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="894b6-228">Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="894b6-228">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="894b6-229">Use estos cmdlets del Centro de seguridad y cumplimiento de Office 365:</span><span class="sxs-lookup"><span data-stu-id="894b6-229">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="894b6-230">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="894b6-230">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [<span data-ttu-id="894b6-231">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="894b6-231">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [<span data-ttu-id="894b6-232">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="894b6-232">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [<span data-ttu-id="894b6-233">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="894b6-233">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [<span data-ttu-id="894b6-234">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="894b6-234">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [<span data-ttu-id="894b6-235">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="894b6-235">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [<span data-ttu-id="894b6-236">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="894b6-236">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="894b6-237">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="894b6-237">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="894b6-238">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="894b6-238">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="894b6-239">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="894b6-239">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="894b6-240">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="894b6-240">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="894b6-241">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="894b6-241">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="894b6-242">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="894b6-242">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="894b6-243">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="894b6-243">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
