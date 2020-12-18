---
title: Utilice el esquema de coincidencia de datos exactos y el asistente para tipos de información confidencial
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga más información sobre como utilizar el esquema de coincidencia de datos exactos y el asistente de tipo de información confidencial.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699157"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="6c75e-103">Utilice el esquema de coincidencia de datos exactos y el asistente para tipos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="6c75e-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="6c75e-104">[Crear un tipo de información confidencial personalizada con una clasificación basada en la coincidencia exacta de datos (EDM) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)implica muchos pasos.</span><span class="sxs-lookup"><span data-stu-id="6c75e-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="6c75e-105">Puede utilizar este asistente para crear su esquema y archivos de tipo de información confidencial (paquete de reglas) para ayudar a simplificar el proceso.</span><span class="sxs-lookup"><span data-stu-id="6c75e-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="6c75e-106">El Esquema de coincidencia exacta de datos y el Asistente para tipos de información confidencial solo están disponibles para las nubes en todo el mundo y GCC.</span><span class="sxs-lookup"><span data-stu-id="6c75e-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="6c75e-107">Este asistente puede ser usado en lugar de:</span><span class="sxs-lookup"><span data-stu-id="6c75e-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="6c75e-108">Definir el esquema de la base de datos de información confidencial</span><span class="sxs-lookup"><span data-stu-id="6c75e-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="6c75e-109">Establecer un patrón (paquete de reglas) </span><span class="sxs-lookup"><span data-stu-id="6c75e-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="6c75e-110">pasos en la[Parte 1: establecer la clasificación basada en el EDM.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="6c75e-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="6c75e-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6c75e-111">Pre-requisites</span></span>

1. <span data-ttu-id="6c75e-112">Familiarícese con los pasos para crear un tipo de información confidencial personalizada con el [ flujo de trabajo del EDM de un vistazo](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span><span class="sxs-lookup"><span data-stu-id="6c75e-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="6c75e-113">Realice los pasos de la sección [Guardar datos confidenciales en formato .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="6c75e-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="6c75e-114">Usar el Esquema de coincidencia exacta de datos y el asistente para información de tipo confidencial</span><span class="sxs-lookup"><span data-stu-id="6c75e-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="6c75e-115">En el Centro de cumplimiento de Microsoft 365 para su inquilino vaya a **Clasificación de datos** > **coincidencias de datos exactos**.</span><span class="sxs-lookup"><span data-stu-id="6c75e-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="6c75e-116">Elija **Crear esquema EDM** para abrir el flotante de configuración del asistente de esquemas.</span><span class="sxs-lookup"><span data-stu-id="6c75e-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Volante de configuración del asistente de creación de esquemas EDM](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="6c75e-118">Rellene con un **Nombre** y una **Descripción apropiados**.</span><span class="sxs-lookup"><span data-stu-id="6c75e-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="6c75e-119">Elija **Ignorar delimitadores y puntuaciones para todos los campos del esquema** si quiere ese comportamiento.</span><span class="sxs-lookup"><span data-stu-id="6c75e-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="6c75e-120">Para obtener más información sobre la configuración del EDM para ignorar mayúsculas y minúsculas o delimitar, consulte [Creación de un tipo de información confidencial personalizada con clasificación basada en la coincidencia de datos exactos (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="6c75e-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="6c75e-121">Rellene los valores deseados para el **Campo #1 del esquema** y agregue más campos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6c75e-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6c75e-122">Al menos uno, pero no más de cinco de los campos de su esquema deben ser designados como de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6c75e-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="6c75e-123">Seleccione Guardar.</span><span class="sxs-lookup"><span data-stu-id="6c75e-123">Choose save.</span></span> <span data-ttu-id="6c75e-124">Su esquema ahora estará en la lista.</span><span class="sxs-lookup"><span data-stu-id="6c75e-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="6c75e-125">Elija **Tipos de información confidencial EDM** y **Crear Tipo de información confidencial EDM** para abrir el asistente de configuración de tipos de información confidencial.</span><span class="sxs-lookup"><span data-stu-id="6c75e-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="6c75e-126">Elija **Elegir un esquema de EDM existente** y elija el esquema que creó en los pasos 2-6 de la lista.</span><span class="sxs-lookup"><span data-stu-id="6c75e-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="6c75e-127">Elija **Siguiente** y seleccione **Crear patrón**.</span><span class="sxs-lookup"><span data-stu-id="6c75e-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="6c75e-128">Elija el **Nivel de confianza** y **Elemento primario**.</span><span class="sxs-lookup"><span data-stu-id="6c75e-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="6c75e-129">Para obtener más información sobre la configuración de un patrón, consulte [Crear un tipo de información confidencial personalizada en el Centro de cumplimiento](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="6c75e-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="6c75e-130">Elija el **tipo de información confidencial del elemento primario** para asociarlo.</span><span class="sxs-lookup"><span data-stu-id="6c75e-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="6c75e-131">Consulte [Tipo de información confidencial según definiciones de entidades](sensitive-information-type-entity-definitions.md) para obtener más información sobre los tipos de información confidencial disponibles.</span><span class="sxs-lookup"><span data-stu-id="6c75e-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="6c75e-132">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="6c75e-132">Choose **Done**.</span></span>

13. <span data-ttu-id="6c75e-133">Elija su **Nivel de confianza y la proximidad de su personaje**.</span><span class="sxs-lookup"><span data-stu-id="6c75e-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="6c75e-134">Este será el valor por defecto para todo el tipo de información confidencial EDM</span><span class="sxs-lookup"><span data-stu-id="6c75e-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="6c75e-135">Elija **Crear patrón** si quiere crear patrones adicionales para su tipo de información confidencial EDM.</span><span class="sxs-lookup"><span data-stu-id="6c75e-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="6c75e-136">Elija **Siguiente** y rellene con un **Nombre** y una **Descripción para los administradores**.</span><span class="sxs-lookup"><span data-stu-id="6c75e-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="6c75e-137">Revise y elija **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="6c75e-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="6c75e-138">Puedes borrar o editar el patrón de tipo de información confidencial seleccionándolo para que aparezca en la superficie de los controles de edición y borrado.</span><span class="sxs-lookup"><span data-stu-id="6c75e-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c75e-139">Si desea eliminar un esquema, y ya está asociado a un tipo de información sensible EDM, primero debe borrar el tipo de información confidencial EDM, luego puede eliminar el esquema.</span><span class="sxs-lookup"><span data-stu-id="6c75e-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="6c75e-140">Pasos posteriores</span><span class="sxs-lookup"><span data-stu-id="6c75e-140">Post steps</span></span>

<span data-ttu-id="6c75e-141">Después de haber usado este asistente para crear sus archivos de esquemas y patrones EDM (paquete de reglas), todavía tiene que realizar los pasos de la [Parte 2: hash y cargar los datos confidenciales](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) antes de poder usar el tipo de información confidencial personalizada EDM.</span><span class="sxs-lookup"><span data-stu-id="6c75e-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>