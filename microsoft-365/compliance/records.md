---
title: Obtenga más información sobre los registros
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
description: Obtenga información acerca de los registros para que pueda implementar la solución de administración de registros de Microsoft 365.
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372525"
---
# <a name="learn-about-records"></a>Obtenga más información sobre los registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La administración de registros de Microsoft 365 ayuda a su organización a cumplir con las directivas corporativas y las obligaciones legales o reglamentarias, al mismo tiempo que reduce el riesgo y la responsabilidad legal.

Cuando el contenido está marcado como un registro:

- Se colocan restricciones en los elementos relativas a qué [acciones se permiten o se bloquean](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Se registran otras actividades sobre el elemento.

- Tendrá la prueba de la eliminación cuando se eliminen los elementos al final de su período de retención.

Puede usar las [etiquetas de retención](retention.md#retention-labels) para marcar el contenido como un registro. Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.

Al usar las etiquetas de retención para marcar contenido como registros, puede implementar una sola estrategia de administración de registros uniforme en todo el entorno de Microsoft 365.

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Comparar restricciones de acciones permitidas o bloqueadas

Use la tabla siguiente para identificar qué restricciones se colocan en el contenido como resultado de aplicar una etiqueta de retención estándar y conocer las etiquetas de retención que marcan el contenido como un registro. 

Una etiqueta de retención estándar tiene la configuración para conservar datos sin marcar el contenido como un registro.

>[!NOTE] 
> Por motivos de integridad, la tabla contiene columnas para un registro bloqueado y desbloqueado, lo que se aplica a SharePoint y OneDrive, pero no a Exchange. La capacidad de bloquear y desbloquear un registro usa el [control de versiones de registros](#record-versioning) que no es compatible con los elementos de Exchange. Por lo tanto, para todos los elementos de Exchange que estén marcados como un registro, el comportamiento que se asigna a la columna **registro bloqueado** y a la columna **registro desbloqueado** no es relevante.


|Acción| Etiqueta de retención |Registro: bloqueado| Registro: desbloqueado|
|:-----|:-----|:-----|:-----|:-----|
|Editar contenidos|Permitido | **Bloqueado** | Permitido|
|Editar propiedades, incluido cambiar nombre|Permitido |Permitido | Permitido|
|Eliminar|Permitido<sup>1</sup> |**Bloqueado** | **Bloqueado**|
|Copiar|Permitido |Permitido | Permitido|
|Moverse dentro del contenedor<sup>2</sup>|Permitido |Permitido | Permitido|
|Moverse entre contenedores<sup>2</sup>|Permitido |Permitido si nunca se desbloquea | Permitido|
|Abrir y leer|Permitido |Permitido | Permitido|
|Cambiar etiqueta|Permitido |Permitido: solo administradores del contenedor | Permitido: solo administradores del contenedor|
|Quitar etiqueta|Permitido |Permitido: solo administradores del contenedor | Permitido: solo administradores del contenedor|

Notas al pie:

<sup>1</sup> Compatible con OneDrive y Exchange reteniendo una copia en una ubicación segura, pero bloqueado por SharePoint.

Mensaje que ve el usuario si intenta eliminar un documento con etiquetas en SharePoint:

![Mensaje que indica que el elemento no se elimina de SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> Los contenedores incluyen librerías de documentos de SharePoint y buzones de Exchange.


## <a name="using-retention-labels-to-declare-records"></a>Usar etiquetas de retención para declarar registros

Al crear una etiqueta de retención, tiene la opción de usarla para marcar el contenido como un registro:

1. En el Centro de cumplimiento de Microsoft 365, vaya a **Administración de registros** \> **Plan de archivos**. En la página **Plan de archivos**, seleccione **Crear una etiqueta**.

2. En la página **Configuración de la etiqueta** del asistente, elija la opción para clasificar el contenido como un registro.
    
   ![Haga clic en la casilla Usar una etiqueta para clasificar contenido como un "registro"](../media/recordversioning6.png)

3. Aplique la etiqueta de retención a los documentos de SharePoint o OneDrive y los correos electrónicos de Exchange, según sea necesario. Para obtener instrucciones, consulte:
    
    - [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
    
    - [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a>Aplicar una etiqueta de retención configurada al contenido

Cuando las etiquetas de retención que marcan el contenido como un registro se ponen a disposición de los usuarios para que las usen en aplicaciones:

- Para Exchange, todos los usuarios con acceso de escritura al buzón pueden aplicar las etiquetas. 
- Para SharePoint y OneDrive, cualquier usuario del grupo predeterminado de miembros (con nivel de permisos de contribución) puede aplicar las etiquetas.

Ejemplo de un documento marcado como registro con una etiqueta de retención:

![Panel de detalles para los documentos etiquetados como registro](../media/recordversioning7.png)

## <a name="record-versioning"></a>Control de versiones de registros

La posibilidad de marcar un documento como registro y restringir las acciones que se pueden realizar en el registro es un objetivo esencial de cualquier solución de administración de registros. Sin embargo, puede ser necesaria la colaboración para crear versiones posteriores.

Por ejemplo, podría marcar un contrato de ventas como un registro, pero después tiene que actualizar el contrato con nuevos términos y marcar la versión más reciente como un nuevo registro, manteniendo aún la versión de registro anterior. Para estos tipos de escenarios, SharePoint Online y OneDrive admite el *control de versiones de registros*. Las carpetas del Bloc de notas de OneNote no admiten el control de versiones de registros.

Para usar el control de versiones de registros, etiquete primero el documento y márquelo como registro. En ese momento, se mostrará la propiedad de documento, llamada *Estado del registro* junto a la etiqueta de retención, y el estado del registro inicial será **bloqueado**. 

Puede hacer lo siguiente:

  - **Editar y retener continuamente versiones individuales del documento como registros, desbloqueando y bloqueando la propiedad Estado del registro**. Solo se retiene una nueva versión del registro cuando la propiedad **Estado del registro** se establece en **Bloqueado**. Esta alternancia de bloqueado y desbloqueado reduce el riesgo de conservar versiones y copias innecesarias del documento.

  - **Hacer que los registros se almacenen automáticamente en un repositorio de registros locales que se encuentra dentro de la colección de sitios**. Todas las colecciones de sitios de SharePoint y OneDrive conserva el contenido en su biblioteca de suspensión para conservación. Las versiones de registro se almacenan en la carpeta registros de esta biblioteca.

  - **Mantenga un documento de hoja perenne que contenga todas las versiones**. De forma predeterminada, todos los documentos de SharePoint y OneDrive tienen un historial de versiones disponible en el menú elemento. En esta historia de versiones, puede ver fácilmente las versiones que son registros y ver esos documentos.

El control de versiones de registros está disponible automáticamente para todos los documentos que contengan una etiqueta de retención que marca el elemento como un registro. Cuando un usuario ve las propiedades del documento en el panel de detalles, puede cambiar el **Estado del registro** de **bloqueado** a **desbloqueado**. Esta acción crea un registro en la carpeta registros de la biblioteca de suspensión para conservación, donde se encuentra por el resto de su período de retención. 

Cuando el documento esté desbloqueado, todos los usuarios con permisos de edición estándar podrán editar el archivo. Sin embargo, los usuarios no pueden eliminar el archivo porque aún es un registro. Cuando termine de editar, el usuario puede cambiar el **Estado de registro** de **Desbloqueado** a **Bloqueado**, lo que impide que se realicen otras modificaciones mientras se encuentre en este estado.
<br/><br/>

![Propiedad de estado de registro en un documento etiquetado como registro](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a>Bloquear y desbloquear un registro

Cuando se aplica a un documento una etiqueta de retención que marca contenido como un registro, cualquier usuario con permisos de contribución o un nivel de permisos más limitado puede desbloquear un registro o bloquear un registro desbloqueado.
<br/><br/>

![El estado del registro muestra que el documento de registro está desbloqueado](../media/recordversioning9.png)

Cuando un usuario desbloquea un registro, tienen lugar las siguientes acciones:

1. Si la colección de sitios actual no tiene una biblioteca de suspensión para conservación, se crea una.

2. Si la biblioteca de suspensión para conservación no tiene una carpeta de registros, se crea una.

3. Una acción **Copiar a** copia la última versión del documento en la carpeta registros. La acción **Copiar a** solo incluye la versión más reciente y ninguna de las versiones anteriores. Este documento copiado se considera ahora una versión de registro del documento y su nombre de archivo tiene el formato: \[Título GUID versión\#\]

4. La copia creada en la carpeta de registros se agrega al historial de versiones del documento original y esta versión muestra la palabra **Registro** en el campo de comentarios.

5. El documento original es una nueva versión que se puede editar, pero no eliminar. La columna de la biblioteca de documentos **El elemento es un registro** aún muestra el valor **Sí**, ya que el documento aún es un registro incluso si ahora se puede modificar.

Cuando un usuario bloquea un registro, no se puede editar el documento original. Sin embargo, es la acción de desbloquear un registro que copia una versión en la carpeta registros de la biblioteca de suspensión para conservación.

### <a name="record-versions"></a>Versiones de registro

Cada vez que un usuario desbloquea un registro, la versión más reciente se copia en la carpeta registros de la biblioteca de suspensión para conservación, que contiene el valor de **registro** en el campo **comentarios** del historial de versiones.
<br/><br/>

![Registro que se muestra en la biblioteca de conservación de documentos](../media/recordversioning10.png)

Para ver el historial de versiones, seleccione un documento de la biblioteca de documentos y, a continuación, haga clic en **Historial de versiones** en el menú elemento.

### <a name="where-records-are-stored"></a>Dónde se almacenan los registros

Los registros se almacenan en la carpeta registros de la biblioteca de suspensión para conservación en el sitio de nivel superior de la colección de sitios. En el panel de navegación izquierdo en el sitio de nivel superior, elija **Contenidos del sitio** \> **Biblioteca de suspensión para conservación**.
<br/><br/>

![Biblioteca de conservación de documentos](../media/recordversioning11.png)

<br/><br/>

![La carpeta registros en la biblioteca de conservación de documentos](../media/recordversioning12.png)

La biblioteca de suspensión para conservación solo es visible para los administradores de la colección de sitios. Asimismo, la biblioteca de suspensión para conservación no existe de forma predeterminada. Solo se crea cuando el contenido sometido a una etiqueta de retención o una directiva de retención se elimina por primera vez en la colección de sitios.

### <a name="searching-the-audit-log-for-record-versioning-events"></a>Buscar en el registro de auditoría los eventos de control de versiones de registros

Las acciones para bloquear y desbloquear registros se registran en el registro de auditoría. Puede buscar actividades específicas **cambiado el estado del registro a bloqueado** y **cambiado el estado del registros a desbloqueado**, que se encuentran en la sección **Actividades de archivo y de página** de la lista desplegable **Actividades** en la página **Búsqueda de registros de auditoría** en el centro de seguridad y cumplimiento.
<br/><br/>

![Buscar en el registro de auditoría los eventos de control de versiones de registros](../media/recordversioning13.png)

Para obtener más información sobre la búsqueda de estos eventos, vea la sección "Actividades de archivo y de página" en [Buscar el registro de auditoría en el centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Pasos siguientes

Si aún no tiene etiquetas de retención que se usarán para la administración de registros, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).

Para obtener más información sobre la eliminación de registros, consulte [Eliminación del contenido](disposition.md).
