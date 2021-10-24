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
ms.localizationpriority: high
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: El plan de archivos ofrece funciones avanzadas de administración para las etiquetas de retención.
ms.custom: seo-marvel-may2020
ms.openlocfilehash: 47f9c3646968dc54aaa9b2d78182585560a8ba1f
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555097"
---
# <a name="use-file-plan-to-manage-retention-labels"></a>Use el plan de archivos para administrar las etiquetas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Aunque puede crear y administrar las etiquetas de retención desde **Gobierno de la información** en el centro de cumplimiento de Microsoft 365, el plan de archivos de **Administración de registros** tiene capacidades de administración adicionales:

- Puede crear una etiqueta de retención en masa al importar la información relevante desde una hoja de cálculo.

- Puede exportar la información de las etiquetas de retención existentes para el análisis y la colaboración sin conexión.

- Se muestra más información sobre las etiquetas de retención para que sea más fácil ver las opciones de configuración de todas sus etiquetas de retención desde una sola vista.

- Los descriptores del plan de archivos admiten información adicional y opcional para cada etiqueta.

El plan de archivos puede usarse para todas las etiquetas de retención, incluso si estas no marcan el contenido como un registro.

Para obtener información sobre qué son las etiquetas de retención y cómo usarlas, consulte [Obtener más información sobre las directivas y las etiquetas de retención](retention.md).

## <a name="accessing-file-plan"></a>Acceder al plan de archivos

Para acceder al plan de archivos, debe tener uno de los siguientes roles de administrador:
    
- Administrador de retención

- Administrador de retención con permiso de vista

En el Centro de cumplimiento de Microsoft 365, vaya a **Soluciones** > **Administración de registros** > **Plan de archivos**:

![Página del plan de archivos](../media/compliance-file-plan.png). 

Si **Administración de registros** no se muestra en el panel de navegación, desplácese hacia abajo y seleccione **Mostrar todo**.

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
    - Sí (Normativa)

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

De forma predeterminada, empezando por el **Reference Id**, en las siguientes columnas, se muestran estos descriptores opcionales del plan de archivos, que puede especificar al crear una etiqueta de retención o editar una etiqueta existente. 

Para empezar, hay algunos valores predeterminados para los siguientes descriptores del plan de archivos: 
- Departamento o función empresarial
- Categoría
- Authority type
- Provision/citation 

Ejemplo de descriptores del plan de archivos al crear o editar una etiqueta de retención:

![Descriptores del plan de archivos al crear o editar una etiqueta de retención.](../media/file-plan-descriptors.png)

Al seleccionar **Elegir** para cada uno de estos descriptores opcionales, puede seleccionar uno de los valores predefinidos o crear uno propio y, a continuación, seleccionarlo. Por ejemplo: 

![Crear nuevo descriptor de plan de archivos para aprovisionar o citar.](../media/file-plan-descriptors-create.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a>Exportar todas las etiquetas de retención para analizar o habilitar las revisiones sin conexión

Desde su administrador del plan de archivos, puede exportar los detalles de todas las etiquetas de retención a un archivo .csv, para facilitar las revisiones de cumplimiento periódicas con las partes interesadas del gobierno de datos de su organización.

Para exportar todas las etiquetas de retención: en la página **Plan de archivos**, haga clic en **Exportar**:

![Opción para exportar el plan de archivos.](../media/compliance-file-plan-export-labels.png)

Se abrirá un archivo *.csv que contiene todas las etiquetas de retención existentes. Por ejemplo:

![Archivo CSV que muestra todas las etiquetas de retención.](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a>Importar las etiquetas de retención al plan de archivos

En el plan de archivos, puede importar en masa nuevas etiquetas de retención mediante un archivo .csv con un formato específico: 

1. En la página **Plan de archivos**, haga clic en **Importar**: ![Opción para importar el plan de archivos](../media/compliance-file-plan-import-labels.png)

2. En el panel **Rellenar e importar el plan de archivos**, seleccione **Descargar una plantilla en blanco**:

   ![Opción para descargar una plantilla de plan de archivos en blanco](../media/file-plan-blank-template-option.png)

3. Después de descargar la plantilla, agregue una fila por cada etiqueta y guarde el archivo. Vea la [siguiente sección](#information-about-the-label-properties-for-import) para obtener información que describe las propiedades y los valores válidos de cada propiedad. 

4. Seleccione **Cargar un archivo** para cargar la plantilla rellenada.
    
   El plan de archivos carga el archivo y valida las entradas.

5. En función de los resultados de la validación:
    
    - Si se produce un error en la validación, anote el número de fila y el nombre de la columna para corregirlos en el archivo de importación. Corrija los errores del archivo, guárdelo y repita el paso 4.
    
    - Si se supera la validación, verá: **Se ha importado correctamente un plan de archivos** y las entradas se convertirán correctamente en etiquetas de retención. Seleccione **Listo** para cerrar el panel y actualizar automáticamente la página **Plan de archivos** y mostrar las nuevas etiquetas.

Ya podrá publicar las nuevas etiquetas de retención o aplicarlas automáticamente. Puede realizar ambas acciones en la pestaña **Directivas de etiquetas** seleccionando **Publicar etiquetas** o **Aplicar automáticamente una etiqueta**.

### <a name="information-about-the-label-properties-for-import"></a>Información sobre las propiedades de etiqueta para importar

Use la siguiente información para rellenar la plantilla descargada e importar nuevas etiquetas de retención. Algunos valores tienen una longitud máxima al importar:

- **LabelName**: longitud máxima de 64 caracteres
- **Comment** y **Notes**: longitud máxima de 1024 caracteres
- Todos los demás valores: longitud ilimitada
<br/>

|Propiedad|Tipo|Obligatorio|Valores válidos|
|:-----|:-----|:-----|:-----|
|LabelName|Cadena|Sí|Esta propiedad especifica el nombre de la etiqueta de retención y debe ser única en el inquilino. Caracteres admitidos para la importación: a-z, A-Z, 0-9, guión (-) y el carácter de espacio.|
|Comentario|Cadena|No|Use esta propiedad para agregar una descripción sobre la etiqueta de retención para administradores. Esta descripción solo se mostrará a los administradores que administren la etiqueta de retención en el centro de cumplimiento.|
|Notas|Cadena|No|Use esta propiedad para agregar una descripción sobre la etiqueta de retención para usuarios. Esta descripción aparece cuando los usuarios mueven el puntero sobre la etiqueta en aplicaciones como Outlook, SharePoint y OneDrive. Si deja esta propiedad en blanco, se muestra una descripción predeterminada que explica la configuración de retención de la etiqueta. |
|IsRecordLabel|Cadena|No, a menos que **Regulatory** esté establecido en **TRUE**|Esta propiedad especifica si la etiqueta marca el contenido como un registro. Los valores válidos son:</br>**TRUE**: la etiqueta marca el elemento como un registro y, por lo tanto, no se puede eliminar el elemento. </br>**FALSE**: la etiqueta no marca el contenido como un registro. Este es el valor predeterminado.</br> </br> Dependencias de grupo: cuando se especifica esta propiedad, también se deben especificar RetentionAction, RetentionDuration y RetentionType.|
|RetentionAction|Cadena|No, a menos que se especifiquen **RetentionDuration**, **RetentionType** o **ReviewerEmail**|Esta propiedad especifica la acción que se llevará a cabo cuando expire el valor especificado por la propiedad RetentionDuration (si está especificado). Los valores válidos son:</br>**Delete**: se eliminan los elementos anteriores al valor especificado por la propiedad RetentionDuration.</br>**Keep**: se conservan los elementos durante el tiempo que especifica la propiedad RetentionDuration y no se ejecuta ninguna acción cuando expira el período de duración. </br>**KeepAndDelete**: se conservan los elementos durante el tiempo que especifica la propiedad RetentionDuration y, al expirar el período de duración, se eliminan </br> </br> Dependencias de grupo: cuando se especifica esta propiedad, también se deben especificar RetentionDuration y RetentionType. |
|RetentionDuration|Cadena|No, a menos que se especifiquen **RetentionAction** o **RetentionType**|Esta propiedad especifica la cantidad de días que se va a conservar el contenido. Los valores válidos son:</br>**Unlimited**: los elementos se conservarán de forma indefinida. </br>**_n_*: un entero positivo en días; por ejemplo, **365**. El número máximo admitido es 24 855, que es 68 años. Si necesita un número más grande, use Unlimited en su lugar.</br> </br> Dependencias de grupo: cuando se especifica esta propiedad, también se deben especificar RetentionAction y RetentionType.
|RetentionType|Cadena|No, a menos que se especifiquen **RetentionAction** o **RetentionDuration**|Esta propiedad especifica si se calcula la duración de la retención (si está especificada) desde la fecha de creación del contenido, la fecha del evento, la fecha de etiquetado o la última fecha de modificación. Los valores válidos son:</br>**CreationAgeInDays**</br>**EventAgeInDays**</br>**TaggedAgeInDays**</br>**ModificationAgeInDays** </br> </br> Dependencias de grupo: cuando se especifica esta propiedad, también se deben especificar RetentionAction y RetentionDuration.|
|ReviewerEmail|SmtpAddress|No|Al especificar esta propiedad, se activará una revisión para eliminación cuando expire la duración de la retención. Esta propiedad especifica la dirección de correo electrónico de un revisor del espacio empresarial para la acción de retención **KeepAndDelete**. </br> </br> Puede incluir la dirección de correo electrónico de usuarios individuales, grupos de seguridad o grupos de distribución en el inquilino. Especifique varias direcciones de correo electrónico separadas por punto y coma. </br> </br> Dependencias de grupo: cuando se especifica esta propiedad, también se deben especificar **RetentionAction** (debe ser **KeepAndDelete**), **RetentionDuration** y **RetentionType**.|
|ReferenceId|Cadena|No|Esta propiedad especifica el valor que se muestra en el descriptor de plan de archivos **Reference Id**, que puede usar como un valor único para su organización.| 
|DepartmentName|Cadena|No|Esta propiedad especifica el valor que se muestra en el descriptor del plan de archivos **Function/Department**.|
|Categoría|Cadena|No|Esta propiedad especifica el valor que se muestra en el descriptor **Categoría** del plan de archivos.|
|SubCategory|Cadena|No|Esta propiedad especifica el valor que se muestra en el descriptor del plan de archivos **Sub category**.|
|AuthorityType|Cadena|No|Esta propiedad especifica el valor que se muestra en el descriptor del plan de archivos **Authority type**.|
|CitationName|Cadena|No|Esta propiedad especifica el nombre de la cita que se muestra en el descriptor del plan de archivos **Provision/citation**. Por ejemplo, "Ley Sarbanes-Oxley de 2002". |
|CitationUrl|Cadena|No|Esta propiedad especifica el valor que se muestra en el descriptor del plan de archivos **Provision/citation**.|
|CitationJurisdiction|Cadena|No|Esta propiedad especifica la jurisdicción o agencia que se muestra en el descriptor del plan de archivos **Provision/citation**. Por ejemplo, "Comisión de Bolsa y Valores de Estados Unidos (SEC)". |
|Regulatory|Cadena|No|Esta propiedad especifica si la etiqueta marca el contenido como un registro normativo, que es [más restrictivo](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) que un registro. Para usar esta configuración de etiqueta, el inquilino debe configurarse para [mostrar la opción de marcar el contenido como un registro normativo](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record) o se producirá un error en la validación de importación. Los valores admitidos son: </br>**TRUE**: la etiqueta marca el elemento como un registro normativo. También debe establecer la propiedad **IsRecordLabel** en TRUE.</br>**FALSE**: la etiqueta no marca el contenido como un registro normativo. Este es el valor predeterminado.|
|EventType|Cadena|No, a menos que **RetentionType** sea **EventAgeInDays**|Esta propiedad especifica un tipo de evento usado para la [retención basada en eventos](event-driven-retention.md). Especifique un tipo de evento existente que se muestre en **Administración de registros** > **Eventos** > **Administrar tipos de eventos**. Como alternativa, use el cmdlet [Get-ComplianceRetentionEventType](/powershell/module/exchange/get-complianceretentioneventtype) para ver los tipos de eventos disponibles. Aunque hay algunos tipos de eventos integrados, como **Actividad de empleado** y **Ciclo de vida del producto**, también puede crear sus propios tipos de eventos. </br> </br> Si especifica su propio tipo de evento, debe existir antes de la importación porque el nombre se valida como parte del proceso de importación.|
|||

## <a name="next-steps"></a>Siguientes pasos

Para obtener más información sobre cómo crear, editar y aplicar etiquetas de retención, consulte los dos escenarios siguientes:
- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)