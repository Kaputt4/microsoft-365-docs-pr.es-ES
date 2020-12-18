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
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>Utilice el esquema de coincidencia de datos exactos y el asistente para tipos de información confidencial

[Crear un tipo de información confidencial personalizada con una clasificación basada en la coincidencia exacta de datos (EDM) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)implica muchos pasos.  Puede utilizar este asistente para crear su esquema y archivos de tipo de información confidencial (paquete de reglas) para ayudar a simplificar el proceso.

> [!NOTE]
> El Esquema de coincidencia exacta de datos y el Asistente para tipos de información confidencial solo están disponibles para las nubes en todo el mundo y GCC.

Este asistente puede ser usado en lugar de:

- [Definir el esquema de la base de datos de información confidencial](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [Establecer un patrón (paquete de reglas) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

pasos en la[Parte 1: establecer la clasificación basada en el EDM.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).

## <a name="pre-requisites"></a>Requisitos previos

1. Familiarícese con los pasos para crear un tipo de información confidencial personalizada con el [ flujo de trabajo del EDM de un vistazo](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).

2. Realice los pasos de la sección [Guardar datos confidenciales en formato .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Usar el Esquema de coincidencia exacta de datos y el asistente para información de tipo confidencial

1. En el Centro de cumplimiento de Microsoft 365 para su inquilino vaya a **Clasificación de datos** > **coincidencias de datos exactos**.

2. Elija **Crear esquema EDM** para abrir el flotante de configuración del asistente de esquemas.

![Volante de configuración del asistente de creación de esquemas EDM](../media/edm-schema-wizard-1.png)

3. Rellene con un **Nombre** y una **Descripción apropiados**.

4. Elija **Ignorar delimitadores y puntuaciones para todos los campos del esquema** si quiere ese comportamiento. Para obtener más información sobre la configuración del EDM para ignorar mayúsculas y minúsculas o delimitar, consulte [Creación de un tipo de información confidencial personalizada con clasificación basada en la coincidencia de datos exactos (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

5. Rellene los valores deseados para el **Campo #1 del esquema** y agregue más campos según sea necesario. 

> [!IMPORTANT]
> Al menos uno, pero no más de cinco de los campos de su esquema deben ser designados como de búsqueda.

6. Seleccione Guardar. Su esquema ahora estará en la lista.

7. Elija **Tipos de información confidencial EDM** y **Crear Tipo de información confidencial EDM** para abrir el asistente de configuración de tipos de información confidencial.

8. Elija **Elegir un esquema de EDM existente** y elija el esquema que creó en los pasos 2-6 de la lista.

9. Elija **Siguiente** y seleccione **Crear patrón**.

10. Elija el **Nivel de confianza** y **Elemento primario**.  Para obtener más información sobre la configuración de un patrón, consulte [Crear un tipo de información confidencial personalizada en el Centro de cumplimiento](create-a-custom-sensitive-information-type.md)

11.  Elija el **tipo de información confidencial del elemento primario** para asociarlo. Consulte [Tipo de información confidencial según definiciones de entidades](sensitive-information-type-entity-definitions.md) para obtener más información sobre los tipos de información confidencial disponibles.

12. Seleccione **Listo**.

13. Elija su **Nivel de confianza y la proximidad de su personaje**.  Este será el valor por defecto para todo el tipo de información confidencial EDM

13. Elija **Crear patrón** si quiere crear patrones adicionales para su tipo de información confidencial EDM.

14. Elija **Siguiente** y rellene con un **Nombre** y una **Descripción para los administradores**.

15. Revise y elija **Enviar**.

Puedes borrar o editar el patrón de tipo de información confidencial seleccionándolo para que aparezca en la superficie de los controles de edición y borrado.

> [!IMPORTANT]
> Si desea eliminar un esquema, y ya está asociado a un tipo de información sensible EDM, primero debe borrar el tipo de información confidencial EDM, luego puede eliminar el esquema.

## <a name="post-steps"></a>Pasos posteriores

Después de haber usado este asistente para crear sus archivos de esquemas y patrones EDM (paquete de reglas), todavía tiene que realizar los pasos de la [Parte 2: hash y cargar los datos confidenciales](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) antes de poder usar el tipo de información confidencial personalizada EDM.