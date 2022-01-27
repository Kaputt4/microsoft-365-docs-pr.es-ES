---
title: Usar el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtenga información acerca de los registros para que pueda implementar la solución de administración de registros en Microsoft 365.
ms.openlocfilehash: 2aabfbf1b3e0aedd8ec7ba54d452cb01ad81776a
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242052"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a>Usar el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Dado que los registros reglamentarios bloquean la edición, el control de versiones de registros no está disponible para los registros reglamentarios.
>
> También puede impedir el control de versiones de registros para el inquilino, incluso si no usa registros normativos: vaya al nodo de **Administración de registros** en el centro de cumplimiento de Microsoft 365 > **Configuración de administración de registros** > **Etiquetas de retención** > **Configurar el control de versiones de registros** y, a continuación, desactive la configuración para **Habilitar el control de versiones de registros**.

La capacidad de marcar un documento como [registro](records-management.md#records) y restringir las acciones que se pueden realizar en el registro es un objetivo esencial para cualquier solución de administración de registros. Sin embargo, también puede ser necesaria la colaboración para que los usuarios creen versiones posteriores.

Por ejemplo, podría marcar un contrato de ventas como un registro, pero después tiene que actualizar el contrato con nuevos términos y marcar la versión más reciente como un nuevo registro, manteniendo aún la versión de registro anterior. Para estos tipos de escenarios, SharePoint Online y OneDrive admite el *control de versiones de registros*. Las carpetas del Bloc de notas de OneNote no admiten el control de versiones de registros.

Para usar el control de versiones de registros, primero [etiquete el documento y márquelo como registro](declare-records.md). En ese momento, se mostrará la propiedad de documento, llamada *Estado del registro* junto a la etiqueta de retención, y el estado del registro inicial será **bloqueado**.

Puede hacer lo siguiente:

- **Editar y retener continuamente versiones individuales del documento como registros, desbloqueando y bloqueando la propiedad Estado del registro**. Solo se retiene una nueva versión del registro cuando la propiedad **Estado del registro** se establece en **Bloqueado**. Esta alternancia de bloqueado y desbloqueado reduce el riesgo de conservar versiones y copias innecesarias del documento.

- **Hacer que los registros se almacenen automáticamente en un repositorio de registros locales que se encuentra dentro de la colección de sitios**. Todas las colecciones de sitios de SharePoint y OneDrive conserva el contenido en su biblioteca de suspensión para conservación. Las versiones de registro se almacenan en la carpeta registros de esta biblioteca.

- **Mantenga un documento de hoja perenne que contenga todas las versiones**. De forma predeterminada, todos los documentos de SharePoint y OneDrive tienen un historial de versiones disponible en el menú elemento. En esta historia de versiones, puede ver fácilmente las versiones que son registros y ver esos documentos.

> [!TIP]
> Al usar el control de versiones de registros con una etiqueta de retención que tiene una acción de eliminación, considere la posibilidad de establecer la configuración de retención **Iniciar el período de retención en función de:** en **Cuando se etiquetaron los elementos**. Con esta configuración de etiqueta, se restablece el inicio del período de retención para cada versión de registro nueva, lo que garantiza que las versiones anteriores se eliminarán antes que las versiones más recientes.

El control de versiones de registros está disponible automáticamente para cualquier documento que tenga aplicada una etiqueta de retención que marque el elemento como un registro y esa etiqueta se [publique en el sitio](create-apply-retention-labels.md). Cuando un usuario ve las propiedades del documento en el panel de detalles, puede cambiar el **Estado del registro** de **bloqueado** a **desbloqueado**. Esta acción crea un registro en la carpeta registros de la biblioteca de suspensión para conservación, donde se encuentra por el resto de su período de retención.

Cuando el documento esté desbloqueado, todos los usuarios con permisos de edición estándar podrán editar el archivo. Sin embargo, los usuarios no pueden eliminar el archivo porque aún es un registro. Cuando termine de editar, el usuario puede cambiar el **Estado de registro** de **Desbloqueado** a **Bloqueado**, lo que impide que se realicen otras modificaciones mientras se encuentre en este estado.
<br/><br/>

:::image type="content" alt-text="Propiedad de estado de registro en un documento etiquetado como registro." source="../media/recordversioning8.png" lightbox="../media/recordversioning8.png":::

## <a name="locking-and-unlocking-a-record"></a>Bloquear y desbloquear un registro

Cuando se aplica a un documento una etiqueta de retención que marca contenido como un registro, cualquier usuario con permisos de contribución o un nivel de permisos más limitado puede desbloquear un registro o bloquear un registro desbloqueado.
<br/><br/>

:::image type="content" alt-text="Estado del registro muestra que el documento de registro está desbloqueado." source="../media/recordversioning9.png" lightbox="../media/recordversioning9.png":::

Cuando un usuario desbloquea un registro, tienen lugar las siguientes acciones:

1. Si la colección de sitios actual no tiene una biblioteca de suspensión para conservación, se crea una.

2. Si la biblioteca de suspensión para conservación no tiene una carpeta de registros, se crea una.

3. Una acción **Copiar a** copia la última versión del documento en la carpeta registros. La acción **Copiar a** solo incluye la versión más reciente y ninguna de las versiones anteriores. Este documento copiado se considera ahora una versión de registro del documento y su nombre de archivo tiene el formato: \[Título GUID versión\#\]

4. La copia creada en la carpeta de registros se agrega al historial de versiones del documento original y esta versión muestra la palabra **Registro** en el campo de comentarios.

5. El documento original es una nueva versión que se puede editar, pero no eliminar. La columna de la biblioteca de documentos **El elemento es un registro** aún muestra el valor **Sí**, ya que el documento aún es un registro incluso si ahora se puede modificar.

Cuando un usuario bloquea un registro, no se puede editar el documento original. Sin embargo, es la acción de desbloquear un registro que copia una versión en la carpeta registros de la biblioteca de suspensión para conservación.

## <a name="record-versions"></a>Versiones de registro

Cada vez que un usuario desbloquea un registro, la versión más reciente se copia en la biblioteca de conservación de documentos y esa versión contiene el valor del **Registro** en el campo **Comentarios** del historial de versiones.
<br/><br/>

:::image type="content" alt-text="Registro que se muestra en la biblioteca de suspensión para conservación." source="../media/recordversioning10.png" lightbox="../media/recordversioning10.png":::

Para ver el historial de versiones, seleccione un documento de la biblioteca de documentos y, a continuación, haga clic en **Historial de versiones** en el menú elemento.

## <a name="where-records-are-stored"></a>Dónde se almacenan los registros

Los registros se almacenan en la carpeta registros de la biblioteca de suspensión para conservación en el sitio de nivel superior de la colección de sitios. En el panel de navegación izquierdo en el sitio de nivel superior, elija **Contenidos del sitio** \> **Biblioteca de suspensión para conservación**.
<br/><br/>

![Biblioteca de suspensión para conservación.](../media/recordversioning11.png)

<br/><br/>

![La carpeta Registros en la biblioteca de suspensión para conservación.](../media/recordversioning12.png)

Para obtener más información sobre la Biblioteca de suspensión para conservación, vea [Cómo funciona la retención para SharePoint y OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).

## <a name="searching-the-audit-log-for-record-versioning-events"></a>Buscar en el registro de auditoría los eventos de control de versiones de registros

Las acciones para bloquear y desbloquear registros se registran en el registro de auditoría. Desde **Actividad de archivos y páginas**, seleccione **Estado de registro cambiado a bloqueado** y **Estado de registro cambiado a**.

Para obtener más información sobre cómo buscar estos eventos, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Pasos siguientes

Para ver otros escenarios admitidos por la administración de registros, vea [Escenarios comunes de la administración de registros](get-started-with-records-management.md#common-scenarios).
