---
title: Información general de registros
ms.author: laurawi
author: laurawi
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
description: Para implementar una estrategia de administración de registros en un Office 365 o en la organización de Microsoft, use las etiquetas de retención que declaran el contenido como un registro. Después, publique o aplique automáticamente la etiqueta registro de retención.
ms.openlocfilehash: 37f23dcd9c2b94edce99fa55977cb26e1faa4d8e
ms.sourcegitcommit: 9a420b16aaa401a822ccfd9b133977ad8bd1024b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2019
ms.locfileid: "39638054"
---
# <a name="overview-of-records"></a>Información general de registros

La administración de registros de Microsoft 365 ayuda a las organizaciones a cumplir con sus obligaciones corporativas, jurídicas y reglamentarias, al tiempo que reduce el riesgo y la responsabilidad legal.

En un nivel alto, la declaración de contenido como un registro significa que:

- El elemento pasa a ser inmutable (un registro no se puede modificar ni eliminar)

- Se registran otras actividades sobre el elemento

- Los registros se eliminan cuando se supera el período de retención declarado.

Puede usar las [etiquetas de retención](labels.md) para clasificar el contenido como un registro. Una vez que haya creado las etiquetas de retención que declaran registros, puede [publicarlas](labels.md#how-retention-labels-work-with-retention-label-policies) (de modo que los usuarios puedan usarlas para clasificar el contenido como registros) o [aplicar automáticamente estas etiquetas](labels.md#applying-a-retention-label-automatically-based-on-conditions) al contenido que desea clasificar como registro. Al usar las etiquetas de retención para declarar registros, puede implementar una única estrategia coherente de administración de registros para todos los Office 365, mientras que otras características de administración de registros, como el Centro de registros, solo se aplican al contenido de SharePoint Online.

Tenga en cuenta lo siguiente respecto a los registros:

  - **Los registros son inmutables**. Se puede aplicar una etiqueta de retención que declara el contenido como un registro en el contenido de Exchange, además de SharePoint y OneDrive para la Empresa. Sin embargo, el [control de versiones de registros](#record-versioning) solo está disponible en SharePoint y en OneDrive, y no en Exchange.

    En Exchange, el contenido etiquetado como un registro no es mutable hasta su eliminación final. Cuando un elemento de Exchange se etiqueta como un registro, suceden cuatro situaciones:

    - El elemento no se puede eliminar de forma permanente.

    - El elemento no se puede editar.

    - La etiqueta no se puede cambiar.

    - La etiqueta no se puede quitar.

  - **Registros y carpetas**. Puede aplicar una etiqueta de retención a una carpeta de Exchange, SharePoint y OneDrive. Si una carpeta se etiqueta como un registro y se mueve un elemento a la carpeta, el elemento se etiquetará como un registro. Cuando se mueve el elemento fuera de la carpeta, el elemento seguirá etiquetado como un registro.

    Además, si cambia la etiqueta de registro aplicada a una carpeta (en SharePoint y OneDrive) a una etiqueta de retención que no declara el contenido como un registro, los elementos de la carpeta mantienen su etiqueta de registro existente.

    Para obtener más información sobre cómo aplicar etiquetas de retención a carpetas de SharePoint y OneDrive, consulte [Aplicar una etiqueta de retención predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).

  - **No se pueden eliminar los registros**. Si un usuario intenta eliminar un registro en Exchange, el elemento se mueve a la carpeta elementos recuperables, tal y como se describe en [Cómo funciona una directiva de retención local](retention-policies.md#content-in-mailboxes-and-public-folders).

    Si un usuario intenta eliminar un registro en SharePoint, se muestra un error que indica que no se eliminó el elemento y permanece en la biblioteca.

    ![Mensaje que indica que el elemento no se elimina de SharePoint](media/d0020726-1593-4a96-b07c-89b275e75c49.png)

    Si intenta eliminar un registro en OneDrive, el elemento se moverá a la biblioteca de suspensión para conservación, como se describe en  [Funcionamiento de una directiva de retención con contenido local](retention-policies.md#content-in-onedrive-accounts-and-sharepoint-sites).

  - **Las etiquetas de registros no se pueden quitar**. Cuando se ha aplicado una etiqueta de registro a un elemento, solo el administrador de esa ubicación (por ejemplo, un administrador de la colección de sitios de un sitio de SharePoint) puede quitar la etiqueta de registro.

## <a name="using-retention-labels-to-declare-records"></a>Usar etiquetas de retención para declarar registros

Al crear una etiqueta de retención, puede usarla para clasificar el contenido como un registro. Para declarar el contenido como un registro, debe hacer lo siguiente:

1. Cree una etiqueta de retención. En el Centro de cumplimiento de Microsoft 365, vaya a **Administración de registros** \> **Plan de archivos**. En la página **Plan de archivos**, haga clic en **Crear una etiqueta**.

2. En la página **Configuración de la etiqueta** del asistente, elija la opción para establecer la etiqueta de retención para declarar el contenido como un registro.<br/>

   ![Haga clic en usar etiqueta para clasificar contenido como una casilla de registro](media/recordversioning6.png)

3. [Publicar](labels.md#how-retention-labels-work-with-retention-label-policies) o [aplicar automáticamente](labels.md#applying-a-retention-label-automatically-based-on-conditions) la etiqueta de retención en los sitios de SharePoint y/o cuentas de OneDrive. 

### <a name="applying-a-retention-label-to-content"></a>Aplicar una etiqueta de retención al contenido

Para Exchange, todos los usuarios con acceso de escritura al buzón pueden aplicar una etiqueta de registro a un mensaje de correo electrónico. Para el contenido de SharePoint y OneDrive, cualquier usuario del grupo predeterminado miembros (con nivel de permisos de contribución) puede aplicar una etiqueta de registro al contenido. Solo el administrador de la colección de sitios puede quitar o cambiar la etiqueta de registro una vez que se ha aplicado. Como se ha explicado anteriormente, una etiqueta de retención que clasifica el contenido como un registro se puede aplicar automáticamente al contenido.

Este es el aspecto que tiene esto cuando se aplica una etiqueta de registro a un documento en un sitio de SharePoint o en una cuenta de OneDrive.
<br/><br/>

:::image type="content" source="media/recordversioning7.png" alt-text="Panel Detalles del documento etiquetado como un registro":::

## <a name="record-versioning"></a>Control de versiones de registros

Una parte esencial de la administración de registros es la capacidad para declarar un documento como un registro y tener ese registro. Al mismo tiempo, la inestabilidad del registro evita que la colaboración se realice en el documento si los usuarios necesitan crear versiones posteriores. Por ejemplo, puede declarar un contrato de ventas como un registro, pero después necesita actualizar el contrato con nuevos términos y declarar la versión más reciente como un nuevo registro, manteniendo aún la versión de registro anterior. Para estos tipos de escenarios, SharePoint Online y OneDrive para la Empresa ahora son compatibles con el *control de versiones de registros*. Las carpetas del Bloc de notas de OneNote no son compatibles.

Para usar el control de versiones de registros, el primer paso es usar el Centro de cumplimiento de Microsoft 365 para crear y publicar etiquetas de retención que declaren registros para todos los sitios de SharePoint y/o cuentas de OneDrive, o bien puede publicarlas en sitios de SharePoint específicos y/o cuentas de OneDrive. El siguiente paso es aplicar una etiqueta de registro de retención publicada a un documento. Cuando se haya completado este paso, se mostrará la propiedad de documento, llamada *Estado del registro* junto a la etiqueta de retención, y el estado de la grabación inicial estará **bloqueada**. En este punto, puede llevar a cabo una de las acciones siguientes:

  - **Edite y declare continuamente versiones individuales del documento como registros, desbloqueando y bloqueando la propiedad Estado del registro**. Solo se conservan las versiones declaradas como registros al establecer la propiedad **Estado del registro** en **bloqueada**. Esto reduce el riesgo de conservar las versiones y copias innecesarias del documento.

  - **Hacer que los registros se almacenen automáticamente en un repositorio de registros locales que se encuentra dentro de la colección de sitios**. Todas las colecciones de sitios de SharePoint y OneDrive conserva el contenido en su biblioteca de suspensión para conservación. Las versiones de registro se almacenan en la carpeta registros de esta biblioteca.

  - **Mantenga un documento de hoja perenne que contenga todas las versiones**. De forma predeterminada, todos los documentos de SharePoint y OneDrive tienen un historial de versiones disponible en el menú elemento. En esta historia de versiones, puede ver fácilmente las versiones que son registros y ver esos documentos.

El control de versiones de registros está disponible automáticamente para todos los documentos que contengan una etiqueta de retención que declara el elemento como un registro. Cuando un usuario ve las propiedades del documento en el panel de detalles, se activa el **Estado del registro** de **bloqueado** a **desbloqueado**. Este solo clic crea un registro en la carpeta registros de la biblioteca de suspensión para conservación, donde se encuentra por el resto de su período de retención. Cuando el documento esté desbloqueado, todos los usuarios con permisos podrán editar el archivo. Sin embargo, los usuarios no pueden eliminar el archivo porque se considera un registro declarado. Después de realizar los cambios necesarios, el usuario puede alternar el estado de **Estado del registro** de **Desbloqueado** a **Bloqueado**, de modo que el documento se declare nuevamente un registro y no se pueda editar.
<br/><br/>

:::image type="content" source="media/recordversioning8.png" alt-text="Propiedad de estado de registro en un documento etiquetado como registro":::

> [!NOTE]
> El control de versiones de registros requiere una licencia de Office 365 Enterprise E5 para cada usuario que tenga permisos para editar el contenido que se ha declarado como un registro en un sitio de SharePoint o en una cuenta de OneDrive. Los usuarios que tienen acceso de solo lectura no necesitan una licencia.

### <a name="locking-and-unlocking-a-record"></a>Bloquear y desbloquear un registro

Cuando se asigna una etiqueta de registro a un documento, cualquier usuario del grupo predeterminado miembros (con nivel de permisos de contribución) puede desbloquear un registro o bloquear un registro desbloqueado.
<br/><br/>

:::image type="content" source="media/recordversioning9.png" alt-text="El estado del registro muestra que el documento de registro está desbloqueado":::

Cuando un usuario desbloquea un registro, tienen lugar las siguientes acciones:

1. Si la colección de sitios actual no tiene una biblioteca de suspensión para conservación, se crea una.

2. Si la biblioteca de suspensión para conservación no tiene una carpeta de registros, se crea una.

3. Una acción **Copiar a** copia la última versión del documento en la carpeta registros. La acción **Copiar a** solo incluye la versión más reciente y ninguna de las versiones anteriores. Este documento copiado se considera ahora una versión de registro del documento y su nombre de archivo tiene el formato: \[Título GUID versión\#\]

4. La copia que se ha creado en la carpeta registros que se ha agregado al historial de versiones del documento original, y esta versión muestra el **registro** de Word en el campo Comentarios.

5. El documento original es una nueva versión que se puede editar (pero no eliminar). La columna de la biblioteca de documentos **el elemento es un registro** aún muestra el valor **sí**, ya que el documento se considera un registro aún cuando se puede modificar ahora.

Cuando un usuario bloquea un registro, no se puede editar el documento original. Sin embargo, es la acción de desbloquear un registro que copia una versión en la carpeta registros de la biblioteca de suspensión para conservación.

### <a name="record-versions"></a>Versiones de registro

Cada vez que un usuario desbloquea un registro, la versión más reciente se copia en la carpeta registros de la biblioteca de suspensión para conservación, que contiene el valor de **registro** en el campo **comentarios** del historial de versiones.
<br/><br/>

:::image type="content" source="media/recordversioning10.png" alt-text="Registro que se muestra en la biblioteca de suspensión para conservación":::

Para ver el historial de versiones, seleccione un documento de la biblioteca de documentos y, a continuación, haga clic en **Historial de versiones** en el menú elemento.

### <a name="where-records-are-stored"></a>Dónde se almacenan los registros

Los registros se almacenan en la carpeta registros de la biblioteca de suspensión para conservación en el sitio de nivel superior de la colección de sitios. En el panel de navegación izquierdo en el sitio de nivel superior, elija **Contenidos del sitio** \> **biblioteca de suspensión para conservación**.
<br/><br/>

:::image type="content" source="media/recordversioning11.png" alt-text="Biblioteca de suspensión para conservación":::

<br/><br/>

:::image type="content" source="media/recordversioning12.png" alt-text="La carpeta registros en la biblioteca de suspensión para conservación":::

La biblioteca de suspensión para conservación solo es visible para los administradores de la colección de sitios. Asimismo, la biblioteca de suspensión para conservación no existe de forma predeterminada. Solo se crea cuando el contenido sometido a una etiqueta de retención o una directiva de retención se elimina por primera vez en la colección de sitios.

### <a name="searching-the-audit-log-for-record-versioning-events"></a>Buscar en el registro de auditoría los eventos de control de versiones de registros

Las acciones para bloquear y desbloquear registros se registran en el registro de auditoría de Office 365. Puede buscar actividades específicas **cambiado el estado del registro a bloqueado** y **cambiado el estado del registros a desbloqueado**, que se encuentran en la sección **Actividades de archivo y de página** de la lista desplegable **Actividades** en la página **Búsqueda de registros de auditoría** en el centro de seguridad y cumplimiento.
<br/><br/>

:::image type="content" source="media/recordversioning13.png" alt-text="Buscar en el registro de auditoría los eventos de control de versiones de registros":::

Para obtener más información sobre la búsqueda de estos eventos, vea la sección "Actividades de archivo y de página" en [Buscar el registro de auditoría en el centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).
