---
title: Creación de EDM SIT con la nueva experiencia
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Creación de una nueva experiencia del paquete de reglas sit de EDM
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4c0139fd6a14a24195679b77aa71321ec201a635
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799442"
---
# <a name="create-edm-sit-using-the-new-experience"></a>Creación de EDM SIT con la nueva experiencia

Puede crear el esquema EDM y el tipo de información confidencial (o paquete de reglas) mediante la nueva experiencia en el portal de cumplimiento.

## <a name="applies-to"></a>Se aplica a

- Nueva experiencia

Si desea crear una sit de EDM con la experiencia clásica, consulte Creación de un [flujo de trabajo de experiencia clásica de SIT de EDM](sit-create-edm-sit-classic-ux-workflow.md). Si necesita ayuda para decidir cuál usar, consulte [Elección de la experiencia de creación correcta de SIT de EDM para usted](sit-get-started-exact-data-match-based-sits-overview.md#choosing-the-right-edm-sit-creation-experience-for-you).

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que ha completado los pasos de estos artículos antes de iniciar los procedimientos de este artículo.

1. [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md)
1. [Creación de un archivo de ejemplo sit de EDM para la nueva experiencia](sit-create-edm-sit-unified-ux-sample-file.md)

Si no está familiarizado con SITS basado en EDM o su implementación, es esencial que se familiarice con los conceptos de:

- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md)
- [Creación de una nueva experiencia de tipo de información confidencial de coincidencia exacta de datos](sit-create-edm-sit-unified-ux-workflow.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)

### <a name="permissions"></a>Permisos

- Debe contar con los permisos de administrador global o de administrador de cumplimiento para crear, probar e implementar un tipo de información confidencial personalizada por medio de la interfaz de usuario. Consulte [Acerca de los roles de administrador en Office 365](/office365/admin/add-users/about-admin-roles).

## <a name="create-your-edm-schema-and-sit"></a>Creación del esquema EDM y SIT

> [!IMPORTANT]
> El sistema sugerirá una asignación entre un SIT existente y el elemento principal. Debe revisar los [SIT existentes](sensitive-information-type-entity-definitions.md) para obtener una idea de cuáles satisfacerán sus necesidades. Asegúrese de que el SIT existente detectará exactamente las cadenas que desea seleccionar y no incluirá ningún carácter circundante ni excluirá ninguna parte válida de la cadena tal como se almacena en la tabla de información confidencial.

> [!NOTE]
> Todos los datos se conservan a medida que navega hacia delante y hacia atrás a través de la interfaz de usuario. La navegación hacia atrás (al seleccionar **Atrás**) solo admite el traslado de la página de nivel superior a la página de nivel superior y la subpágina a la subpágina. No se puede navegar hacia atrás desde la página de nivel superior a la subpágina anterior o desde una subpágina a una página de nivel superior anterior. 

1. En el portal de cumplimiento Microsoft Purview del inquilino, vaya a **Clasificación** >  de **datos Coincidencias exactas de datos**.

1. Asegúrese de que la **nueva experiencia de EDM** esté establecida **en Activado**.

1. Seleccione **+ Crear clasificador EDM**.

1. Asigne un nombre a SIT y agregue una descripción. El nombre que genera el sistema para el esquema será el nombre sit que escriba aquí concatenado con *el esquema*. Se mostrará al final del flujo. Seleccione **Siguiente**.

1. Seleccione el método que desea usar para definir el esquema, cargue **un archivo que contenga datos de ejemplo** o **defina manualmente la estructura de datos**. Se recomienda la opción Cargar archivo de datos de ejemplo y el resto de este procedimiento supone que ha elegido cargar el archivo de ejemplo. Seleccione **Siguiente**.

> [!NOTE]
> Independientemente de la opción que seleccione, usará la información del archivo de ejemplo que creó en [Creación de un archivo de ejemplo sit de EDM para la nueva experiencia](sit-create-edm-sit-unified-ux-sample-file.md).

6. Seleccione el archivo de ejemplo y seleccione **Cargar archivo** y, a continuación, **seleccione Siguiente**. Si recibe algún error durante la carga, solucione los errores e inténtelo de nuevo.

7. Una vez cargados los datos, se mostrarán en la página Comprobar que los **datos de ejemplo son correctos** . Inspeccione los nombres de columna y los datos de ejemplo y elija **Siguiente**.

8. Seleccione los elementos principales en función de las recomendaciones presentadas. Examine los valores de la columna **Coincidencia de validación** para obtener instrucciones y elija **Siguiente**.

> [!TIP]
> - Seleccione los elementos principales cuyos valores hacen que esa fila sea única en la tabla. Por ejemplo, no elija campos como *FirstName* o *DateOfBirth* , ya que lo más probable es que haya muchas duplicaciones de nombres o fechas de nacimiento en el archivo de datos confidenciales real. En su lugar, elija elementos como *Social Security Number* y *BankAccountNumber* cuyo valor será único en la tabla y, por tanto, haga que la fila sea única en la tabla.
> - Debe elegir un elemento principal, pero no más de diez elementos principales. Si tiene un campo de datos corroborativos de varios tokens, también debe asignarlo a una SIT base. Cuanto más pueda elegir que tengan valores únicos en la tabla de datos confidenciales reales, mejor será la precisión de su SIT de EDM. También mejorará el rendimiento y evitará los tiempos de espera causados por la sobrecarga de procesos. 
> - Seleccione un tipo de información confidencial que coincida estrechamente con el formato del contenido que desea encontrar. Seleccionar una SIT que coincida con contenido innecesario, como una que coincida con todas las cadenas de texto o todos los números, puede provocar una carga excesiva en el sistema, lo que podría dar lugar a que se perdiese información confidencial.

9. En los **campos Configure settings for data (Configurar opciones para los campos de datos** ), puede indicar cómo trata EDM los casos y qué delimitadores se deben omitir. Puede establecerlo para los valores de todos los valores de elementos o especificar la configuración de cada elemento individualmente. Elija **Siguiente**.

> [!IMPORTANT]
Si seleccionó la opción Delimitadores omitidos para la columna de elemento principal en el esquema, asegúrese de que sit al que se asigna coincidirá con los datos con y sin los delimitadores seleccionados.

10. EDM generará automáticamente una regla de detección para cada uno de los elementos principales identificados. EDM creará una regla de confianza alta y una regla de confianza media. Las reglas de confianza alta tienen más requisitos que deben cumplirse que las reglas medianas. Del mismo modo, las reglas de confianza medianas tienen más requisitos que las reglas de confianza baja si decide crear una regla de confianza baja. Puede revisar y editar esas reglas en la página **Configurar reglas de detección para elementos principales** . Choose **Submit**.

> [!TIP]
> Todos los elementos que no están seleccionados como elementos principales todavía se pueden usar como pruebas corroboradoras o auxiliares. Cuantos más elementos auxiliares se encuentren en una proximidad definida a los elementos primarios, mayor será la confianza en que el elemento sea un verdadero positivo.

> [!NOTE]
Al seleccionar **Enviar**, EDM creará el esquema y el paquete de reglas. El nombre del esquema se puede encontrar en la página final del flujo de creación.  


## <a name="next-step"></a>Paso siguiente

- **Para obtener una nueva experiencia**: [hash y carga de la tabla de origen de información confidencial para obtener datos exactos que coincidan con tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md)

