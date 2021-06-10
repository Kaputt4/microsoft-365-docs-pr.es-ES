---
title: Utilice el esquema de coincidencia de datos exactos y el asistente para tipos de información confidencial
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga más información sobre como utilizar el esquema de coincidencia de datos exactos y el asistente de tipo de información confidencial.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5fdf289c403d8c09342a1eac1434c4219bb7b13c
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861664"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="90b4b-103">Utilice el esquema de coincidencia de datos exactos y el asistente para tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="90b4b-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="90b4b-104">[Crear un tipo de información confidencial personalizada con una clasificación basada en la coincidencia exacta de datos (EDM) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)implica muchos pasos.</span><span class="sxs-lookup"><span data-stu-id="90b4b-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="90b4b-105">Puede usar este asistente para crear los archivos de patrón de esquema y de tipo de información confidencial (SIT) (paquete de reglas) para simplificar el proceso.</span><span class="sxs-lookup"><span data-stu-id="90b4b-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="90b4b-106">El Esquema de coincidencia exacta de datos y el Asistente para tipos de información confidencial solo están disponibles para las nubes en todo el mundo y GCC.</span><span class="sxs-lookup"><span data-stu-id="90b4b-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="90b4b-107">Este asistente puede ser usado en lugar de:</span><span class="sxs-lookup"><span data-stu-id="90b4b-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="90b4b-108">Definir el esquema de la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="90b4b-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="90b4b-109">Establecer un patrón (paquete de reglas) </span><span class="sxs-lookup"><span data-stu-id="90b4b-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="90b4b-110">pasos en la[Parte 1: establecer la clasificación basada en el EDM.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="90b4b-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="90b4b-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="90b4b-111">Pre-requisites</span></span>

1. <span data-ttu-id="90b4b-112">Familiarícese con los pasos para crear un tipo de información confidencial personalizada con el [ flujo de trabajo del EDM de un vistazo](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span><span class="sxs-lookup"><span data-stu-id="90b4b-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="90b4b-113">Realice los pasos de la sección [Guardar datos confidenciales en formato .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="90b4b-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="90b4b-114">Usar el Esquema de coincidencia exacta de datos y el asistente para información de tipo confidencial</span><span class="sxs-lookup"><span data-stu-id="90b4b-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="90b4b-115">En el Centro de cumplimiento de Microsoft 365 para su inquilino vaya a **Clasificación de datos** > **coincidencias de datos exactos**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="90b4b-116">Elija **Crear esquema EDM** para abrir el flotante de configuración del asistente de esquemas.</span><span class="sxs-lookup"><span data-stu-id="90b4b-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Volante de configuración del asistente de creación de esquemas EDM](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="90b4b-118">Rellene con un **Nombre** y una **Descripción apropiados**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="90b4b-119">Elija **Omitir delimitadores y puntuación** para todos los campos de esquema si desea ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="90b4b-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="90b4b-120">Para obtener más información acerca de cómo configurar EDM para omitir mayúsculas o minúsculas, vea [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="90b4b-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="90b4b-121">Rellene los valores deseados para el **Campo #1 del esquema** y agregue más campos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="90b4b-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="90b4b-122">Al menos uno, pero no más de cinco de los campos de su esquema deben ser designados como de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="90b4b-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="90b4b-123">Seleccione Guardar.</span><span class="sxs-lookup"><span data-stu-id="90b4b-123">Choose save.</span></span> <span data-ttu-id="90b4b-124">Su esquema ahora estará en la lista.</span><span class="sxs-lookup"><span data-stu-id="90b4b-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="90b4b-125">Elija **Tipos de información confidencial EDM** y **Crear Tipo de información confidencial EDM** para abrir el asistente de configuración de tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="90b4b-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="90b4b-126">Elija **Elegir un esquema de EDM existente** y elija el esquema que creó en los pasos 2-6 de la lista.</span><span class="sxs-lookup"><span data-stu-id="90b4b-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="90b4b-127">Elija **Siguiente** y seleccione **Crear patrón**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="90b4b-128">Elija el **Nivel de confianza** y **Elemento primario**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="90b4b-129">Para obtener más información sobre la configuración de un patrón, consulte [Crear un tipo de información confidencial personalizada en el Centro de cumplimiento](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="90b4b-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="90b4b-130">Elija el **tipo de información confidencial del elemento primario** para asociarlo.</span><span class="sxs-lookup"><span data-stu-id="90b4b-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="90b4b-131">Consulte [Tipo de información confidencial según definiciones de entidades](sensitive-information-type-entity-definitions.md) para obtener más información sobre los tipos de información confidencial disponibles.</span><span class="sxs-lookup"><span data-stu-id="90b4b-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="90b4b-132">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-132">Choose **Done**.</span></span>

13. <span data-ttu-id="90b4b-133">Elija su **Nivel de confianza y la proximidad de su personaje**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="90b4b-134">Este será el valor por defecto para todo el tipo de información confidencial EDM</span><span class="sxs-lookup"><span data-stu-id="90b4b-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="90b4b-135">Elige **Crear patrón** si quieres crear patrones adicionales para el tipo de información confidencial de EDM.</span><span class="sxs-lookup"><span data-stu-id="90b4b-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="90b4b-136">Elija **Siguiente** y rellene con un **Nombre** y una **Descripción para los administradores**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="90b4b-137">Revise y elija **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="90b4b-138">Puedes borrar o editar el patrón de tipo de información confidencial seleccionándolo para que aparezca en la superficie de los controles de edición y borrado.</span><span class="sxs-lookup"><span data-stu-id="90b4b-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90b4b-139">Si desea eliminar un esquema, y ya está asociado a un tipo de información sensible EDM, primero debe borrar el tipo de información confidencial EDM, luego puede eliminar el esquema.</span><span class="sxs-lookup"><span data-stu-id="90b4b-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="90b4b-140">Pasos posteriores a la creación</span><span class="sxs-lookup"><span data-stu-id="90b4b-140">Post creation steps</span></span>

<span data-ttu-id="90b4b-141">Después de haber usado este asistente para crear sus archivos de esquemas y patrones EDM (paquete de reglas), todavía tiene que realizar los pasos de la [Parte 2: hash y cargar los datos confidenciales](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) antes de poder usar el tipo de información confidencial personalizada EDM.</span><span class="sxs-lookup"><span data-stu-id="90b4b-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="90b4b-142">Después de comprobar que la tabla de información confidencial se ha cargado correctamente, puede probar que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="90b4b-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="90b4b-143">Open **Compliance center** Data  >  **classification** Sensitive Information  >  **Types**.</span><span class="sxs-lookup"><span data-stu-id="90b4b-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="90b4b-144">Seleccione su SIT de EDM en la lista y, a continuación, **seleccione Probar** en el panel desplegable.</span><span class="sxs-lookup"><span data-stu-id="90b4b-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="90b4b-145">Upload elemento que contiene datos que desea detectar, por ejemplo, cree un elemento que contenga algunos de los datos de la tabla de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="90b4b-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="90b4b-146">Si usó la característica de coincidencia configurable en el esquema para definir delimitadores ignorados, asegúrese de que el elemento incluye ejemplos con y sin esos delimitadores.</span><span class="sxs-lookup"><span data-stu-id="90b4b-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="90b4b-147">Después de cargar y examinar el archivo, compruebe si hay coincidencias en su SIT de EDM.</span><span class="sxs-lookup"><span data-stu-id="90b4b-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="90b4b-148">Si la **función Test** del SIT detecta una coincidencia, compruebe que no la está recortando o extrayendo incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="90b4b-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="90b4b-149">Por ejemplo, extrayendo solo una subcadena de la cadena completa que se supone que debe detectar, o tomando solo la primera palabra de una cadena de varias palabras, o incluyendo símbolos o caracteres adicionales en la extracción.</span><span class="sxs-lookup"><span data-stu-id="90b4b-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="90b4b-150">Consulte [Lenguaje de expresión regular: referencia rápida para](/dotnet/standard/base-types/regular-expression-language-quick-reference) la referencia del lenguaje de expresión regular.</span><span class="sxs-lookup"><span data-stu-id="90b4b-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="90b4b-151">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="90b4b-151">Troubleshooting</span></span>

<span data-ttu-id="90b4b-152">Si no encuentra ninguna coincidencia, pruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90b4b-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="90b4b-153">Confirme que los datos confidenciales se cargaron correctamente con los comandos que se explican en las instrucciones para cargar los datos confidenciales [mediante la herramienta EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="90b4b-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="90b4b-154">Compruebe que los ejemplos especificados en el elemento están presentes en la tabla de información confidencial y que los delimitadores omitido son correctos.</span><span class="sxs-lookup"><span data-stu-id="90b4b-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="90b4b-155">**Pruebe** el SIT que usó al configurar el elemento principal en cada uno de los patrones.</span><span class="sxs-lookup"><span data-stu-id="90b4b-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="90b4b-156">Esto confirmará que el SIT puede coincidir con los ejemplos del elemento.</span><span class="sxs-lookup"><span data-stu-id="90b4b-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="90b4b-157">Si el SIT que seleccionó para un elemento principal del tipo EDM no encuentra una coincidencia en el elemento o encuentra menos coincidencias de las esperadas, compruebe que admite separadores y delimitadores que existen en el contenido.</span><span class="sxs-lookup"><span data-stu-id="90b4b-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="90b4b-158">Asegúrese de incluir los delimitadores omitidos definidos en el esquema.</span><span class="sxs-lookup"><span data-stu-id="90b4b-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="90b4b-159">Si la **función Test** no detecta ningún contenido, compruebe si el SIT seleccionado incluye requisitos para palabras clave adicionales u otras validaciones.</span><span class="sxs-lookup"><span data-stu-id="90b4b-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="90b4b-160">Para los SIT [integrados,](sensitive-information-type-entity-definitions.md) vea Sensitive information types entity definitions to verify what the minimum requirements are for matching each type.</span><span class="sxs-lookup"><span data-stu-id="90b4b-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
