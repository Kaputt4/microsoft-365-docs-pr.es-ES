---
title: Usar el control de versiones de registros en SharePoint o OneDrive
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
ms.openlocfilehash: 176e0a005d388681fcda119798fd838d73b7f733
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629363"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a>Usar el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Dado que los registros reglamentarios bloquean la edición, el control de versiones de registros no está disponible para los registros reglamentarios.
>
> También puede impedir el control de versiones de registros para el espacio empresarial, incluso si no usa registros normativos: vaya a **Administración de registros** en el Portal de cumplimiento de Microsoft Purview > **Configuración de administración de registros** > **Etiquetas de retención** > **Configurar el control de versiones de registros** y, después, desactive la configuración para **Habilitar el control de versiones de registros**.

La capacidad de marcar un documento como [registro](records-management.md#records) y restringir las acciones que se pueden realizar en el registro es un objetivo esencial para cualquier solución de administración de registros. Sin embargo, también puede ser necesaria la colaboración para que los usuarios creen versiones posteriores.

Por ejemplo, podría marcar un contrato de ventas como un registro, pero después tiene que actualizar el contrato con nuevos términos y marcar la versión más reciente como un nuevo registro, manteniendo aún la versión de registro anterior. Para estos tipos de escenarios, SharePoint Online y OneDrive admite el *control de versiones de registros*. Las carpetas del Bloc de notas de OneNote no admiten el control de versiones de registros.

Para usar el control de versiones de registros, primero etiquete el documento con una [etiqueta de retención configurada para marcar los elementos como registro](declare-records.md). En este punto, se muestra una propiedad de documento, denominada *Estado de registro*, junto a la etiqueta de retención. Dependiendo de si la etiqueta está configurada para desbloquear el registro de forma predeterminada (actualmente en implementación), el estado inicial del registro es **Bloqueado** o **Desbloqueado**.

Puede hacer lo siguiente:

- **Editar y retener continuamente versiones individuales del documento como registros, desbloqueando y bloqueando la propiedad Estado del registro**. Solo se retiene una nueva versión del registro cuando la propiedad **Estado del registro** se establece en **Bloqueado**. Esta alternancia de bloqueado y desbloqueado reduce el riesgo de conservar versiones y copias innecesarias del documento.
    
    > [!NOTE]
    > Si la etiqueta está configurada para desbloquear el registro de forma predeterminada, pero el administrador no habilita el control de versiones o lo impide la configuración de administración de registros, los usuarios no podrán desbloquear el documento después de bloquearlo.

- **Hacer que los registros se almacenen automáticamente en un repositorio de registros local ubicado con el sitio.** Todos los sitios de SharePoint y OneDrive conservan el contenido en su biblioteca de suspensión para conservación. Las versiones de registro se almacenan en la carpeta registros de esta biblioteca. Para obtener más información sobre la Biblioteca de suspensión para conservación, vea [Cómo funciona la retención para SharePoint y OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).

- **Mantenga un documento de hoja perenne que contenga todas las versiones**. De forma predeterminada, todos los documentos de SharePoint y OneDrive tienen un historial de versiones disponible en el menú elemento. En esta historia de versiones, puede ver fácilmente las versiones que son registros y ver esos documentos.

> [!TIP]
> Al usar el control de versiones de registros con una etiqueta de retención que tiene una acción de eliminación, considere la posibilidad de establecer la configuración de retención **Iniciar el período de retención en función de:** en **Cuando se etiquetaron los elementos**. Con esta configuración de etiqueta, se restablece el inicio del período de retención para cada versión de registro nueva, lo que garantiza que las versiones anteriores se eliminarán antes que las versiones más recientes.

De forma predeterminada, el control de versiones de registros está disponible automáticamente para cualquier documento que tenga aplicada una etiqueta de retención que marque el elemento como un registro y esa etiqueta se [publique en el sitio](create-apply-retention-labels.md). Cuando un usuario ve las propiedades del documento en el panel de detalles, puede cambiar el **Estado del registro** entre **bloqueado** y **desbloqueado**.

Cuando el documento esté desbloqueado, todos los usuarios con permisos de edición estándar podrán editar el archivo. Sin embargo, los usuarios no pueden eliminar el archivo porque aún es un registro. Cuando termine de editar, el usuario puede cambiar el **Estado de registro** de **Desbloqueado** a **Bloqueado**, lo que impide que se realicen otras modificaciones mientras se encuentre en este estado.
<br/><br/>

:::image type="content" alt-text="Propiedad de estado de registro en un documento etiquetado como registro." source="../media/recordversioning8.png" lightbox="../media/recordversioning8.png":::

Para obtener más información sobre qué acciones de usuario se permiten cuando un registro está bloqueado o desbloqueado, vea [Comparar las restricciones de las acciones permitidas o bloqueadas](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).

## <a name="locking-and-unlocking-a-record"></a>Bloquear y desbloquear un registro

Cuando se aplica a un documento una etiqueta de retención que marca contenido como un registro, cualquier usuario con permisos de contribución o un nivel de permisos más limitado puede desbloquear un registro o bloquear un registro desbloqueado.
<br/><br/>

:::image type="content" alt-text="Estado del registro muestra que el documento de registro está desbloqueado." source="../media/recordversioning9.png" lightbox="../media/recordversioning9.png":::

Cuando se desbloquea un registro, se producen las siguientes acciones:

1. Si el sitio actual no tiene una biblioteca de suspensión para conservación, se crea una.

2. Si la biblioteca de suspensión para conservación no tiene una carpeta de registros, se crea una.

3. Una acción **Copiar a** copia la última versión del documento en la carpeta registros. La acción **Copiar a** solo incluye la versión más reciente y ninguna de las versiones anteriores. Este documento copiado se considera ahora una versión de registro del documento y su nombre de archivo tiene el formato: \[Título GUID versión\#\]

4. La copia creada en la carpeta de registros se agrega al historial de versiones del documento original y esta versión muestra la palabra **Registro** en el campo de comentarios.

5. El documento original es una nueva versión que se puede editar, pero no eliminar. La columna de la biblioteca de documentos **El elemento es un registro** aún muestra el valor **Sí**, ya que el documento aún es un registro incluso si ahora se puede modificar.

Cuando un usuario bloquea un registro, no se puede editar el documento original. Sin embargo, es la acción de desbloquear un registro que copia una versión en la carpeta registros de la biblioteca de suspensión para conservación.

## <a name="record-versions"></a>Versiones de registro

Cada vez que se desbloquea un registro, la versión más reciente se copia en la biblioteca de suspensión para conservación y esa versión contiene el valor del **Registro** en el campo **Comentarios** del historial de versiones.
<br/><br/>

:::image type="content" alt-text="Registro que se muestra en la biblioteca de suspensión para conservación." source="../media/recordversioning10.png" lightbox="../media/recordversioning10.png":::

Para ver el historial de versiones, seleccione un documento de la biblioteca de documentos y, a continuación, haga clic en **Historial de versiones** en el menú elemento.

## <a name="searching-the-audit-log-for-record-versioning-events"></a>Buscar en el registro de auditoría los eventos de control de versiones de registros

Las acciones para bloquear y desbloquear registros se registran en el registro de auditoría. Desde **Actividad de archivos y páginas**, seleccione **Estado de registro cambiado a bloqueado** y **Estado de registro cambiado a**.

Para obtener más información sobre cómo buscar estos eventos, vea [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Pasos siguientes

Para ver otros escenarios admitidos por la administración de registros, vea [Escenarios comunes de la administración de registros](get-started-with-records-management.md#common-scenarios).
