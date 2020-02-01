---
title: Usar un clasificador listo para usar (vista previa)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 incluye varios clasificadores listos para usar para el aprendizaje automático que puede usar para identificar y etiquetar el contenido en toda la organización. En este tema se muestra cómo prepararse para usar estos clasificadores listos para usarlos.
ms.openlocfilehash: c6659bc32131948c57ad0bf7c8e3a30fbce125d9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595897"
---
# <a name="using-a-ready-to-use-classifier-preview"></a><span data-ttu-id="9cfa1-104">Usar un clasificador listo para usar (vista previa)</span><span class="sxs-lookup"><span data-stu-id="9cfa1-104">Using a ready to use classifier (preview)</span></span>

<span data-ttu-id="9cfa1-105">Microsoft ha entrenado y probado varios clasificadores con conjuntos de datos de ejemplo muy grandes, lo que puede ayudar a identificar determinadas categorías de contenido.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-105">Microsoft has trained and tested a number of classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="9cfa1-106">Consulte [Introducción a los clasificadores capacitados (versión preliminar)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="9cfa1-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="9cfa1-107">Estos clasificadores se muestran en el `Ready to use` grupo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="9cfa1-108">**Lenguaje ofensivo**: detecta los elementos de texto que contienen palabras soeces, Slurs, taunts y expresiones disfrazadas (que son expresiones que tienen el mismo significado que un término más ofensivo).</span><span class="sxs-lookup"><span data-stu-id="9cfa1-108">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="9cfa1-109">**Currículos**: detecta los elementos que son cuentas de texto de la cualificación personal, educativa, profesional, experiencia laboral y otra información de identificación personal del solicitante.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-109">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="9cfa1-110">**SourceCode**: detecta elementos que contienen un conjunto de instrucciones e instrucciones escritas en lenguajes de programación de equipos ampliamente usados.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-110">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="9cfa1-111">**Acosar**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con la conducta ofensiva dirigida a uno o varios individuos en función de los siguientes rasgos: raza, étnico, religión, origen nacional, sexo, orientación sexual, edad, discapacidad.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-111">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="9cfa1-112">**Blasfemias**: detecta una categoría específica de elementos de texto de lenguaje ofensivo que contiene expresiones que avergonzan a la mayoría de las personas.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-112">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="9cfa1-113">**Threat**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionadas con amenazas para confirmar violencia o daño físico o daño a una persona o propiedad.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-113">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="9cfa1-114">Antes de usar los clasificadores listos para usar en el flujo de trabajo de clasificación y etiquetado, debe probarlo con una muestra del contenido de la organización que sienta que se ajusta a la categoría para comprobar que sus predicciones de clasificación satisfacen sus expectativas.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-114">Before using ready to use classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cfa1-115">Tenga en cuenta que el idioma ofensivo, el acoso, los términos blasfemos y los clasificadores de amenazas solo funcionan con texto que admite búsquedas no es exhaustivo o completo.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-115">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="9cfa1-116">Además, los estándares de idioma y culturales cambian continuamente y, teniendo en cuenta estas realidades, Microsoft se reserva el derecho de actualizar estos clasificadores según su criterio.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-116">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="9cfa1-117">Aunque los clasificadores pueden ayudar a su organización a supervisar el uso ofensivo y otros idiomas, los clasificadores no abordan las consecuencias de dicho lenguaje y no pretenden proporcionar a los únicos medios de supervisión de la organización o responder al uso de ese idioma.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-117">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="9cfa1-118">Su organización, y no Microsoft o sus subsidiarias, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, la aplicación, el bloqueo, la eliminación y la retención de cualquier contenido identificado por un clasificador previamente entrenado.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-118">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a><span data-ttu-id="9cfa1-119">Cómo preparar y usar un clasificador listo para usar</span><span class="sxs-lookup"><span data-stu-id="9cfa1-119">How to prepare for and use a ready to use classifier</span></span>

1. <span data-ttu-id="9cfa1-120">Recopile los elementos de contenido de pruebas desechables que considera que pertenecen a la categoría del clasificador listo para usar (coincidencias positivas) y de los que no se deben incluir (coincidencias negativas) en la categoría que está probando.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-120">Collect disposable test content items that you feel belong in the category of the ready to use classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cfa1-121">Los elementos de ejemplo no deben estar cifrados y deben estar en inglés.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-121">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="9cfa1-122">Cree una carpeta dedicada de SharePoint Online; espere al menos una hora para que la carpeta se agregue al índice de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-122">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="9cfa1-123">Anote la dirección URL de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-123">Make note of the folder URL.</span></span>

3. <span data-ttu-id="9cfa1-124">Inicie sesión en el centro de cumplimiento de Microsoft 365 con el administrador de cumplimiento o el rol de administrador de seguridad y abra la ficha**directivas** de administración de registros del **Centro** > de cumplimiento de Microsoft 365 **(versión preliminar)** > .</span><span class="sxs-lookup"><span data-stu-id="9cfa1-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="9cfa1-125">Elija `Auto-apply a label`.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-125">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="9cfa1-126">Elija `Choose a label to auto-apply`.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-126">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="9cfa1-127">Elija `Create new labels` y cree una etiqueta para usarla sólo con esta prueba.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-127">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="9cfa1-128">Cuando lo haga, deje `Retention` el valor en desactivado.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-128">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="9cfa1-129">No desea activar ninguna retención ni otras acciones.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-129">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="9cfa1-130">En este caso, utilizará la etiqueta de retención simplemente como una etiqueta de texto, sin aplicar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-130">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="9cfa1-131">Por ejemplo, puede crear una etiqueta de retención denominada "SourceCode Classifier test" sin ninguna acción y, a continuación, aplicar automáticamente esa etiqueta de retención a contenido que tiene clasificador de código fuente como condición.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-131">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="9cfa1-132">Para obtener más información acerca de la creación de etiquetas de retención, consulte [Overview of Retention Labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="9cfa1-132">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="9cfa1-133">Elija `Auto-apply a label` y, `Choose a label to auto-apply`a continuación,.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-133">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="9cfa1-134">Para obtener más información sobre el uso de la aplicación basada en condiciones, aplique automáticamente una etiqueta vea, [aplique automáticamente una directiva de etiqueta de retención basada en una condición](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span><span class="sxs-lookup"><span data-stu-id="9cfa1-134">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="9cfa1-135">Elija su etiqueta de prueba de la lista y `Next`elija.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-135">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="9cfa1-136">Elija `Apply label to content that matches a trainable classifier`.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-136">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![selección de clasificador como condición](media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="9cfa1-138">.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-138">.</span></span>

10. <span data-ttu-id="9cfa1-139">Elija su clasificador de la lista, en este caso`Source Code`</span><span class="sxs-lookup"><span data-stu-id="9cfa1-139">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="9cfa1-140">Asigne un nombre a la Directiva, por ejemplo, "código fuente preparado para usar la prueba de clasificador".</span><span class="sxs-lookup"><span data-stu-id="9cfa1-140">Name the policy, for example "Source code ready to use classifier test".</span></span>

12. <span data-ttu-id="9cfa1-141">Elija `Let me choose specific locations`.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-141">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="9cfa1-142">Desactive todas las ubicaciones `SharePoint sites` excepto y `Choose sites`elija.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-142">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="9cfa1-143">Escriba la dirección URL del sitio en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-143">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="9cfa1-144">Finaliza el asistente y elige`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="9cfa1-144">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="9cfa1-145">Ponga los elementos de prueba en la carpeta dedicada de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-145">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="9cfa1-146">Permite aplicar una hora para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-146">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="9cfa1-147">Compruebe las propiedades de los documentos para la etiqueta para ver si el clasificador incluyó y excluya el contenido de prueba tal como esperaba.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-147">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="9cfa1-148">Revise los elementos etiquetados.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-148">Review the items that were labeled.</span></span>

20. <span data-ttu-id="9cfa1-149">Elimine el contenido y la Directiva de etiqueta si ya ha terminado con las pruebas.</span><span class="sxs-lookup"><span data-stu-id="9cfa1-149">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="9cfa1-150">Vea también:</span><span class="sxs-lookup"><span data-stu-id="9cfa1-150">See also:</span></span>

- [<span data-ttu-id="9cfa1-151">Introducción al entrenamiento de clasificadores (vista previa)</span><span class="sxs-lookup"><span data-stu-id="9cfa1-151">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="9cfa1-152">Introducción a las etiquetas de retención</span><span class="sxs-lookup"><span data-stu-id="9cfa1-152">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="9cfa1-153">Aplicar automáticamente una directiva de etiqueta de retención basada en una condición</span><span class="sxs-lookup"><span data-stu-id="9cfa1-153">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
