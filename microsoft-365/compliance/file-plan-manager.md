---
title: Usar el plan de archivos para administrar las etiquetas de retención durante el ciclo de vida del contenido
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: El plan de archivos ofrece funciones avanzadas de administración para las etiquetas de retención.
ms.custom: seo-marvel-may2020
ms.openlocfilehash: 96150005421f6c2e28183c6e4417edd64b80a814
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126883"
---
# <a name="use-file-plan-to-manage-retention-labels"></a>Use el plan de archivos para administrar las etiquetas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Aunque puede crear y administrar las etiquetas de retención desde **Gobierno de la información** en el centro de cumplimiento de Microsoft 365, el plan de archivos de **Administración de registros** tiene capacidades de administración adicionales:

- Puede crear una etiqueta de retención en masa al importar la información relevante desde una hoja de cálculo.

- Puede exportar la información de las etiquetas de retención existentes para el análisis y la colaboración sin conexión o para la edición en masa.

- Se muestra más información sobre las etiquetas de retención para que sea más fácil ver las opciones de configuración de todas sus etiquetas de retención desde una sola vista.

- Los descriptores del plan de archivos admiten información adicional y opcional para cada etiqueta.

El plan de archivos puede usarse para todas las etiquetas de retención, incluso si estas no marcan el contenido como un registro.

![Página del plan de archivos](../media/compliance-file-plan.png)

Para obtener información sobre qué son las etiquetas de retención y cómo usarlas, consulte [Obtener más información sobre las directivas y las etiquetas de retención](retention.md).

## <a name="accessing-file-plan"></a>Acceder al plan de archivos

Para acceder al plan de archivos, debe tener uno de los siguientes roles de administrador:
    
- Administrador de retención

- Administrador de retención con permiso de vista

En el Centro de cumplimiento de Microsoft 365, vaya a **Soluciones** > **Administración de registros** > ** Plan de archivos**. 

Si **Administración de registros** no se muestra en el panel de navegación, desplácese hacia abajo y seleccione **Mostrar todo**.

![Página del plan de archivos](../media/compliance-file-plan.png)

## <a name="navigating-your-file-plan"></a>Navegar por el plan de archivos

Si ya ha creado las etiquetas de retención desde **Gobierno de la información** en el centro de cumplimiento de Microsoft 365, estas etiquetas se mostrarán automáticamente en su plan de archivos. 

De forma similar, si ahora crea etiquetas de retención en el plan de archivos, también estarán disponibles en **Gobierno de la información** si no se configuran para marcar el contenido como un registro.

En la página **Plan de archivos**, verá todas sus etiquetas con el estado y la configuración, los descriptores opcionales del plan de archivos, una opción de exportación para analizar o habilitar las revisiones sin conexión de sus etiquetas, y una opción de importación para crear etiquetas de retención. 

### <a name="label-settings-columns"></a>Columnas de configuración de etiquetas

A excepción de la etiqueta **Nombre**, todas las columnas se pueden mostrar u ocultar al seleccionar la opción **Personalizar columnas**. Sin embargo, de manera predeterminada, las primeras columnas muestran información sobre el estado de la etiqueta y su configuración: 

- **Estado** identifica si la etiqueta está incluida en una directiva de etiqueta o en una directiva de aplicación automática (**Activa**) o no (**Inactiva**).

- **Basado en** identifica cómo y cuándo comienza el período de retención. Valores válidos:
    - Evento
    - Fecha de creación
    - Última modificación
    - Fecha de etiquetado

- **Es un registro** identifica si el elemento está marcado como un registro al aplicar la etiqueta. Valores válidos:
    - No
    - Sí

- **Duración de la retención** identifica el período de retención. Valores válidos:
    - Días
    - Meses
    - Años
    - Siempre
    - Ninguno

- **Tipo de eliminación** identifica qué ocurrirá con el contenido al final del período de retención. Valores válidos:
    - Ninguna acción
    - Eliminación automática
    - Revisión necesaria

### <a name="file-plan-descriptors-columns"></a>Columnas de descriptores del plan de archivos

El plan de archivos le permite incluir más información como parte de las etiquetas de retención. Estos descriptores del plan de archivos proporcionan más opciones para mejorar la facilidad de uso y la organización del contenido que necesite etiquetar.

De forma predeterminada, empezando por el**Reference Id**, en las siguientes columnas se muestran estos descriptores del plan de archivos que puede especificar al crear una etiqueta de retención, o editar una etiqueta existente. 

Para empezar, hay algunos valores predeterminados para los siguientes descriptores del plan de archivos: 
- Departamento o función empresarial
- Categoría
- Authority type
- Provision/citation 

Ejemplo de descriptores del plan de archivos al crear o editar una etiqueta de retención:

![Descriptores del plan de archivos](../media/file-plan-descriptors.png)

Vista de ejemplo de las columnas de descriptores del plan de archivos:

![file-plan-descriptors-on-labels-tab.png](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a>Exportar todas las etiquetas de retención para analizar o habilitar las revisiones sin conexión

Desde su administrador del plan de archivos, puede exportar los detalles de todas las etiquetas de retención a un archivo .csv, para facilitar las revisiones de cumplimiento periódicas con las partes interesadas del gobierno de datos de su organización.

Para exportar todas las etiquetas de retención: en la página **Plan de archivos**, haga clic en **Exportar**:

![Opción para exportar el plan de archivos](../media/compliance-file-plan-export-labels.png)

Se abrirá un archivo *.csv que contiene todas las etiquetas de retención existentes. Por ejemplo:

![Archivo CSV que muestra todas las etiquetas de retención](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a>Importar las etiquetas de retención al plan de archivos

En el plan de archivos, puede importar en masa nuevas etiquetas de retención y usar el mismo método para modificar en masa las etiquetas existentes.

Para importar nuevas etiquetas de retención y modificar las existentes: 

1. En la página **Plan de archivos**, haga clic en **Importar** para usar la página**Rellenar e importar su plan de archivos**:

   ![Opción para importar el plan de archivos](../media/compliance-file-plan-import-labels.png)

   ![Opción para descargar una plantilla de plan de archivos en blanco](../media/file-plan-blank-template-option.png)

2. Descargue una plantilla en blanco para importar nuevas etiquetas de retención. Como alternativa, puede empezar con el archivo .csv que se exporta al exportar las etiquetas de retención existentes en su organización.

   ![Plantilla en blanco del plan de archivos abierta en Excel](../media/file-plan-blank-template.png)

3. Rellene la plantilla con la siguiente información, que describe las propiedades y los valores válidos para cada propiedad. Para la importación, cada valor tiene una longitud máxima de 64 caracteres. <br/>

   |Propiedad|Tipo|Valores válidos|
   |:-----|:-----|:-----|
   |LabelName|Cadena|Esta propiedad especifica el nombre de la etiqueta de retención.|
   |Comentario|Cadena|Use esta propiedad para agregar una descripción sobre la etiqueta de retención para administradores. Esta descripción solo se mostrará a los administradores que administren la etiqueta de retención en el centro de cumplimiento.|
   |Notas|Cadena|Use esta propiedad para agregar una descripción sobre la etiqueta de retención para usuarios. Esta descripción aparece cuando los usuarios mueven el puntero sobre la etiqueta en aplicaciones como Outlook, SharePoint y OneDrive. Si deja esta propiedad en blanco, se muestra una descripción predeterminada que explica la configuración de retención de la etiqueta. |
   |IsRecordLabel|Cadena|Esta propiedad especifica si la etiqueta marca el contenido como un registro. Los valores válidos son: </br>**TRUE**: la etiqueta marca el elemento como un registro y, por lo tanto, no se puede eliminar el elemento. </br>**FALSE**: la etiqueta no marca el contenido como un registro. Este es el valor predeterminado.|
   |RetentionAction|Cadena|Esta propiedad especifica la acción que se llevará a cabo cuando expire el valor especificado por la propiedad RetentionDuration. Los valores válidos son: </br>**Delete**: se eliminan los elementos anteriores al valor especificado por la propiedad RetentionDuration.</br>**Keep**: se conservan los elementos durante el tiempo que especifica la propiedad RetentionDuration y no se ejecuta ninguna acción cuando expira el período de duración. </br>**KeepAndDelete**: se conservan los elementos durante el tiempo que especifica la propiedad RetentionDuration y, al expirar el período de duración, se eliminan   |
   |RetentionDuration|Cadena|Esta propiedad especifica la cantidad de días que se va a conservar el contenido. Los valores válidos son: </br>**Unlimited**: los elementos se conservarán de forma indefinida. </br>***n***: un entero positivo, por ejemplo,**365**. 
   |RetentionType|Cadena|Esta propiedad especifica si se calcula la duración de la retención desde la fecha de creación del contenido, la fecha del evento, la fecha de etiquetado o la última fecha de modificación. Los valores válidos son: </br>**CreationAgeInDays**</br>**EventAgeInDays**</br>**TaggedAgeInDays**</br>**ModificationAgeInDays** |
   |ReviewerEmail|SmtpAddress|Al rellenar esta propiedad, se activará una revisión de disposición cuando expire la duración de la retención. Esta propiedad especifica la dirección de correo electrónico del revisor para las acción de retención **KeepAndDelete**. Puede incluir la dirección de correo electrónico de usuarios individuales, grupos de seguridad o grupos de distribución. Puede especificar varias direcciones de correo electrónico separadas por punto y coma.|
   |ReferenceId|Cadena|Esta propiedad especifica el valor que se muestra en el descriptor de plan de archivos**Reference Id**, que puede usar como un valor único para su organización.| 
   |DepartmentName|Cadena|Esta propiedad especifica el valor que se muestra en el descriptor del plan de archivos **Function/Department**.|
   |Categoría|Cadena|Esta propiedad especifica el valor que se muestra en el descriptor **Categoría** del plan de archivos.|
   |SubCategory|Cadena|Esta propiedad especifica el valor que se muestra en el descriptor del plan de archivos **Sub category**.|
   |AuthorityType|Cadena|Esta propiedad especifica el valor que se muestra en el descriptor del plan de archivos **Authority type**.|
   |CitationName|Cadena|Esta propiedad especifica el nombre de la cita que se muestra en el descriptor del plan de archivos **Provision/citation**. Por ejemplo, "Ley Sarbanes-Oxley de 2002". |
   |CitationUrl|Cadena|Esta propiedad especifica el valor que se muestra en el descriptor del plan de archivos **Provision/citation**.|
   |CitationJurisdiction|Cadena|Esta propiedad especifica la jurisdicción o agencia que se muestra en el descriptor del plan de archivos **Provision/citation**. Por ejemplo, "Comisión de Bolsa y Valores​​ de Estados Unidos (SEC)".|
   |Regulatory|Cadena|Se deja en blanco. Esta propiedad no se usa en este momento.|
   |EventType|Cadena|Esta propiedad especifica la regla de retención que está asociada a la etiqueta. Puede usar cualquier valor que identifique de forma exclusiva la regla. Por ejemplo:</br>**Nombre**</br>**Nombre distintivo (DN)**</br>**GUID** </br>Puede usar el cmdlet [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule?view=exchange-ps) para ver las reglas de retención disponibles. Tenga en cuenta que, como los valores de EventType son únicos para una organización, si exporta etiquetas desde una organización, no podrá usar los valores de la propiedad EventType de esa organización para importar las etiquetas en otra.|
   |||

   Este es un ejemplo de la plantilla que contiene información sobre las etiquetas de retención.

   ![Plantilla del plan de archivos con información ya completada](../media/file-plan-filled-out-template.png)

4. En el paso 3, en la página **Rellenar e importar su plan de archivos**, haga clic en **Buscar archivos** para cargar la plantilla completada. 

   El plan de archivo validará las entradas y mostrará las estadísticas de importación.

   ![Estadísticas de importación del plan de archivos](../media/file-plan-import-statistics.png)

   Si hay un error de validación, la importación del plan de archivo continuará validando todas las entradas del archivo de importación y mostrará todos los errores que hacen referencia a los números de línea y fila en el archivo de importación. Copie los resultados de error mostrados para que pueda corregirlos cuando vuelva al archivo de importación.

Cuando finalice la importación, puede agregar las etiquetas de retención a una nueva directiva de etiqueta de retención o aplicarlas automáticamente. Puede hacer esto directamente desde la página del **Plan de archivos**, al seleccionar la lista desplegable **+ Crear una etiqueta** y después, **Directiva para publicar etiquetas**, o **Directiva para aplicar automáticamente una etiqueta**.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre cómo crear y editar las etiquetas de retención y sus directivas, consulte las siguientes instrucciones:
- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)
