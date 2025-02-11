---
title: Obtenga más información sobre la retención para SharePoint y OneDrive
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
- purview-compliance
- tier1
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo funciona la retención de Microsoft 365 para SharePoint y OneDrive, mediante directivas de retención y etiquetas de retención para administrar la retención o la eliminación automáticas de datos de su organización.
ms.openlocfilehash: dc694171b6964b728a983597a246eb2446c9f472
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564769"
---
# <a name="learn-about-retention-for-sharepoint-and-onedrive"></a>Obtenga más información sobre la retención para SharePoint y OneDrive

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

La información de este artículo complementa[Obtenga más información sobre las directivas de retención](retention.md)porque tiene información específica de SharePoint y OneDrive.

Para otras cargas de trabajo, vea:

- [Más información sobre las directivas de retención para Microsoft Teams](retention-policies-teams.md)
- [Más información sobre la retención para Yammer](retention-policies-yammer.md)
- [Más información sobre las directivas de retención de Exchange](retention-policies-exchange.md)

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="whats-included-for-retention-and-deletion"></a>Qué se incluye para la retención y eliminación

Todos los archivos almacenados en los sitios de SharePoint o OneDrive se pueden conservar si se aplica una directiva de retención o una etiqueta de retención. 

Se pueden eliminar los siguientes archivos:

- Al usar una directiva de retención: todos los archivos de las bibliotecas de documentos, lo cual incluye cualquier biblioteca de documentos de SharePoint que se cree automáticamente, como **Activos del sitio**.
    
- Al usar las etiquetas de retención: todos los archivos de todas las bibliotecas de documentos y todos los archivos en el nivel raíz que no estén en una carpeta.
    
> [!TIP]
> Al usar una [consulta con una directiva de aplicación automática para una etiqueta de retención](apply-retention-labels-automatically.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties), puede excluir las bibliotecas de documentos específicas mediante la siguiente entrada: `NOT(DocumentLink:"<URL to document library>")`

Los elementos de la lista no son compatibles con las directivas de retención, pero sí con las etiquetas de retención, a excepción de los elementos en las listas de sistema. Se trata de listas ocultas utilizadas por SharePoint para administrar el sistema e incluir el catálogo de la página principal, el catálogo de soluciones y los orígenes de datos. Cuando las etiquetas de retención se aplican a los elementos de lista admitidos, siempre se conservarán según la configuración de retención, pero no se eliminarán si están ocultos en la búsqueda.

Cuando aplica una etiqueta de retención a un elemento de lista admitido que tiene un documento adjunto:
- Para una etiqueta de retención estándar (no declara el elemento como registro):
    - El documento adjunto no hereda automáticamente la configuración de retención de la etiqueta, pero se puede etiquetar de manera independiente.
- Para una etiqueta de retención que declare el elemento como registro: 
    - El documento adjunto hereda automáticamente la configuración de retención de la etiqueta si el documento no ha sido etiquetado todavía.

La configuración de retención de las directivas de retención y de las etiquetas de retención no se aplica a las estructuras de organización que contienen bibliotecas, listas y carpetas.

Para directivas de retención y directivas de etiqueta de aplicación automática: los sitios de SharePoint deben estar indexados para que se aplique la configuración de retención. Sin embargo, si los elementos de la biblioteca de documentos de SharePoint se configuran para que no aparezcan en los resultados de búsqueda, esta configuración no excluirá los archivos de la configuración de retención.


## <a name="how-retention-works-for-sharepoint-and-onedrive"></a>Obtenga información acerca de cómo funciona la retención para SharePoint y OneDrive

Para almacenar el contenido que debe conservarse, SharePoint y OneDrive crean una biblioteca de suspensión para conservación si no existe una para el sitio. La biblioteca de suspensión para conservación no está diseñada para usarse de forma interactiva, sino que almacena automáticamente los archivos cuando esto sea necesario por motivos de cumplimiento. Funciona de la siguiente manera:

Cuando un usuario cambia un elemento que está sujeto a retención de una directiva de retención o una etiqueta de retención que marca los elementos como un registro o elimina cualquier elemento sujeto a retención, el contenido original se copia en la biblioteca de suspensión de conservación. Este comportamiento permite al usuario cambiar o eliminar el contenido de su aplicación, al tiempo que mantiene una copia del original por motivos de cumplimiento.

Un trabajo de temporizador se ejecuta periódicamente en la biblioteca de suspensión para conservación. Para el contenido que ha estado en la biblioteca de suspensión para conservación durante más de 30 días, este trabajo compara el contenido con todas las consultas utilizadas por la configuración de retención para ese contenido. El contenido que es más antiguo que su período de retención configurado se elimina de la biblioteca de suspensión para conservación, así como de la ubicación original si todavía está allí. Este trabajo de temporizador se ejecuta cada siete días, lo que significa que, con el mínimo de 30 días, el contenido puede tardar hasta 37 días en eliminarse de la biblioteca de suspensión para conservación.

This behavior for copying files into the Preservation Hold library applies to content that exists when the retention settings were applied. In addition, for retention policies, any new content that's created or added to the site after it was included in the policy will be retained in the Preservation Hold library. However, new content isn't copied to the Preservation Hold library the first time it's edited, only when it's deleted. To retain all versions of a file, [versioning](#how-retention-works-with-document-versions) must be turned on for the original site.
  
Los usuarios ven un mensaje de error si intentan eliminar una biblioteca, lista, carpeta o sitio sujeto a retención. Pueden eliminar una carpeta sin etiquetar si primero mueven o eliminan los archivos de la carpeta que están sujetos a retención.

Los usuarios también ven un mensaje de error si intentan eliminar un elemento etiquetado en cualquiera de las siguientes circunstancias. El elemento no se copia en la biblioteca de suspensión para conservación, pero permanece en la ubicación original:

- La configuración de administración de registros que permite a los usuarios eliminar elementos etiquetados está desactivada.
    
    To check or change this setting, go to the **Records management** solution in the Microsoft Purview compliance portal > **Records management** > **Records management settings** > **Retention labels** > **Deletion of items**. There are separate settings for SharePoint and OneDrive.
    
    Como alternativa, y si no tiene acceso a la solución de **Administración de registros**, puede usar *AllowFilesWithKeepLabelToBeDeletedSPO* y *AllowFilesWithKeepLabelToBeDeletedODB* de [Get-PnPTenant](https://pnp.github.io/powershell/cmdlets/Get-PnPTenant.html) y [Set-PnPTenant](https://pnp.github.io/powershell/cmdlets/Set-PnPTenant.html).

- La etiqueta de retención marca los elementos como un registro y está [bloqueada](record-versioning.md).
    
    Solo cuando se desbloquea el registro, se almacena una copia de la última versión en la biblioteca de conservación de documentos.

- La etiqueta de retención marca los elementos como [registro normativo](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked), que siempre impide que el elemento se edite o elimine.

Cuando se asigna el contenido de una cuenta de OneDrive o un sitio de SharePoint a la configuración de retención, dependen de si la configuración de retención debe retener, eliminar, solo retener o eliminar. En las explicaciones siguientes, el contenido modificado se mueve a la biblioteca de suspensión de conservación para las directivas de retención y las etiquetas de retención que marcan los elementos como registros (y el contenido está desbloqueado). Los elementos que se modifican con etiquetas de retención que no marcan elementos como registros no crean copias en la biblioteca de suspensión de conservación, pero sí cuando se eliminan los elementos.

Cuando los ajustes de retención son para retener y borrar:

![Diagrama del ciclo de vida de contenido en SharePoint y OneDrive.](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Si el contenido se ha modificado o eliminado** durante el periodo de retención, se crea en la biblioteca de suspensión para conservación una copia del contenido original tal como era cuando se asignó la configuración de retención. Allí, el trabajo del temporizador identifica los artículos cuyo período de retención ha expirado. Esos artículos se mueven a la segunda etapa de la Papelera de reciclaje, donde se borran permanentemente al final de los 93 días. La papelera de reciclaje de la segunda etapa no es visible para los usuarios finales (solo la papelera de reciclaje de primer nivel), pero los administradores de colecciones de sitios pueden ver y restaurar el contenido desde allí.

    > [!NOTE]
    > Para ayudar a evitar la pérdida accidental de datos, ya no se elimina permanentemente el contenido de la biblioteca de conservación de documentos. Ahora solo eliminamos de forma permanentemente el contenido de la Papelera de reciclaje. Todo el contenido de la biblioteca de suspensión para conservación pasa por la Papelera de reciclaje de segundo nivel.
    
2. **If the content is not modified or deleted** during the retention period, the timer job moves this content to the first-stage Recycle Bin at the end of the retention period. If a user deletes the content from there or empties this Recycle Bin (also known as purging), the document is moved to the second-stage Recycle Bin. A 93-day retention period spans both the first- and second-stage recycle bins. At the end of 93 days, the document is permanently deleted from wherever it resides, in either the first-stage or second-stage Recycle Bin. The Recycle Bin is not indexed and therefore unavailable for searching. As a result, an eDiscovery search can't find any Recycle Bin content on which to place a hold.

> [!NOTE]
> Debido [al primer principio de retención](retention.md#the-principles-of-retention-or-what-takes-precedence), la eliminación permanente siempre se suspende si el mismo elemento debe conservarse debido a otra directiva de retención o etiqueta de retención, o si está en retención de eDiscovery por motivos legales o de investigación.

Cuando los ajustes de retención son sólo de retención o sólo de borrado, las rutas de contenido son variaciones de retención y borrado:

### <a name="content-paths-for-retain-only-retention-settings"></a>Rutas de contenido para la configuración de la retención de sólo lectura

1. **Si el contenido se modifica o se elimina** durante el período de retención, una copia del documento original se crea en la biblioteca de suspensión para conservación y se conserva hasta el final del período de retención, cuando la copia de la biblioteca de suspensión para conservación se mueve a la Papelera de reciclaje de segundo nivel y se elimina de forma permanente después de 93 días.

2. **Si el contenido no se modifica ni elimina** durante el período de retención, no sucede nada antes y después del período de retención; el documento permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-settings"></a>Rutas de contenido para la configuración de retención de solo eliminación

1. **Si el contenido se elimina** durante el período configurado: el documento es trasladado a la primera etapa de la Papelera de reciclaje. Si un usuario elimina el documento desde allí o vacía esta Papelera de reciclaje, el documento se mueve a la Papelera de reciclaje de segundo nivel. Un período de retención de 93 días abarca las Papeleras de reciclaje de primer nivel y de segundo nivel. Después de 93 días, el documento se elimina de forma permanente de donde se encuentre, ya sea en la Papelera de reciclaje de primer nivel o de segundo nivel. Si el contenido se modifica durante el período configurado, sigue la misma ruta de eliminación después del período configurado.

2. **If the content is not deleted** during the configured period: At the end of the configured period in the retention policy, the document is moved to the first-stage Recycle Bin. If a user deletes the document from there or empties this Recycle Bin (also known as purging), the document is moved to the second-stage Recycle Bin. A 93-day retention period spans both the first-stage and second-stage recycle bins. At the end of 93 days, the document is permanently deleted from wherever it resides, in either the first-stage or second-stage Recycle Bin. The Recycle Bin is not indexed and therefore unavailable for searching. As a result, an eDiscovery search can't find any Recycle Bin content on which to place a hold.

## <a name="how-retention-works-with-cloud-attachments"></a>Cómo funciona la retención con datos adjuntos en la nube

Los datos adjuntos en la nube son vínculos incrustados a archivos que los usuarios comparten y que se pueden conservar y eliminar cuando los usuarios los comparten en mensajes de Teams y correo de Outlook. Cuando se [aplica automáticamente una etiqueta de retención a los datos adjuntos de la nube](apply-retention-labels-automatically.md#auto-apply-labels-to-cloud-attachments), la etiqueta de retención se aplica a una copia del archivo compartido, que se almacena en la Biblioteca de suspensión para conservación.

Para este escenario, se recomienda establecer la configuración de etiqueta para iniciar el período de retención en función del momento en que se etiqueta el elemento. Si configura el período de retención en función de cuándo se crea o modifica por última vez el elemento, esta fecha se toma del archivo original en el momento del uso compartido. Si configura el inicio de retención para que sea cuando se modifique por última vez, esta configuración no tiene efecto para esta copia en la Biblioteca de suspensión para conservación.

Sin embargo, si el archivo original se modifica y, a continuación, se vuelve a compartir, se guarda una nueva copia del archivo como una nueva versión y se etiqueta en la Biblioteca de suspensión para conservación.

Si el archivo original se vuelve a compartir pero no se modifica, se actualiza la fecha etiquetada de la copia en la Biblioteca de suspensión para conservación. Esta acción restablece el inicio del período de retención y por eso se recomienda configurar el inicio del período de retención para que se base en el momento en que se etiqueta el elemento.

Dado que la etiqueta de retención no se aplica al archivo original, un usuario nunca modifica ni elimina el archivo etiquetado. El archivo etiquetado permanece en la Biblioteca de suspensión para conservación hasta que el trabajo del temporizador identifique que su período de retención ha expirado. Si la configuración de retención está configurada para eliminar elementos, el archivo se mueve a la Papelera de reciclaje de segundo nivel, donde se elimina permanentemente al final de 93 días:

![Cómo funciona la retención para los datos adjuntos de la nube almacenados en SharePoint y OneDrive](../media/retention-diagram-of-retention-flow-cloud-attachments.png)

La copia almacenada en la Biblioteca de suspensión para conservación normalmente se crea en una hora a partir del momento en que los datos adjuntos de la nube se comparten.

Para evitar que los usuarios eliminen el archivo original antes de que se pueda crear y etiquetar la copia, los archivos de las ubicaciones incluidas en la directiva de etiquetado automático se copian automáticamente en la biblioteca de suspensión de conservación si se eliminan. Estos archivos tienen un período de retención temporal de un día y, a continuación, siguen el proceso de limpieza estándar descrito en esta página. Cuando se ha eliminado el archivo original, la copia para conservar los datos adjuntos en la nube usa esta versión del archivo. La retención automática y temporal de los archivos eliminados en la biblioteca de suspensión de conservación es única para las directivas de etiquetado automático para los datos adjuntos en la nube.

## <a name="how-retention-works-with-onenote-content"></a>Cómo funciona la retención con el contenido de OneNote

Al aplicar una directiva de retención a una ubicación que incluya contenido OneNote o una etiqueta de retención en una carpeta OneNote, en segundo plano, las distintas páginas y secciones de OneNote son archivos individuales que heredan la configuración de retención. Esto significa que cada sección dentro de una página se conservará y eliminará individualmente, según la configuración de retención que especifique.

Solo las páginas y secciones se verán afectadas por la configuración de retención que especifique. Por ejemplo, aunque vea una fecha de **modificación** para cada bloc de notas individual, esta fecha no se usa en la retención de Microsoft 365.

## <a name="how-retention-works-with-document-versions"></a>Funcionamiento de una directiva de retención con versiones de documentos

Versioning is a feature of all document lists and libraries in SharePoint and OneDrive. By default, versioning retains a minimum of 500 major versions, although you can increase this limit. For more information, see [Enable and configure versioning for a list or library](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37) and [How versioning works in lists and libraries](https://support.microsoft.com/office/how-versioning-works-in-lists-and-libraries-0f6cd105-974f-44a4-aadb-43ac5bdfd247).
  
Cuando un documento con versiones está sujeto a la configuración de retención para conservar ese contenido, la forma en que las versiones se almacenan en la biblioteca de suspensión para conservación cambió en julio de 2022 para mejorar el rendimiento. Ahora todas las versiones del archivo se conservan en un único archivo de la biblioteca de suspensión para conservación. Antes del cambio, las versiones se copiaban a la biblioteca de suspensión para conservación como archivos independientes y, después del cambio, permanecen como archivos independientes.

Si la configuración de retención se configura para eliminar al final del período de retención:

- If the retention period is based on when the content was created, each version has the same expiration date as the original document. The original document and its versions all expire at the same time.

- Si el período de retención se basa en la fecha de última modificación del contenido:
    - **Después del cambio en el que se conservan todas las versiones del archivo en un único archivo en la biblioteca de suspensión para conservación**: cada versión tiene la misma fecha de expiración que la última versión del documento. La última versión del documento y todas sus versiones expiran al mismo tiempo.
    - **Antes del cambio en el que las versiones se copiaban a la biblioteca de suspensión para conservación como archivos independientes**: cada versión tiene su propia fecha de expiración en función de cuándo se modificó el documento original para crear esa versión. Los documentos originales y sus versiones expiran de forma independiente.

Cuando la acción de retención es eliminar el documento, todas las versiones que no se encuentren en la biblioteca de suspensión para conservación se eliminarán al mismo tiempo de acuerdo con la versión actual.

For items that are subject to a retention policy (or an eDiscovery hold), the versioning limits for the document library are ignored until the retention period of the document is reached (or the eDiscovery hold is released). In this scenario, old versions are not automatically purged and users are prevented from deleting versions.

Este no es el caso de las etiquetas de retención cuando el contenido está sujeto a una directiva de retención (o a una retención de eDiscovery). En su lugar, se tienen en cuenta los límites del control de versiones, por lo que las versiones anteriores se eliminan automáticamente para dar lugar a nuevas versiones, pero los usuarios todavía no pueden eliminar versiones.

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización

**SharePoint**:

Cuando un usuario deja la organización, no se verá afectado el contenido creado por el usuario, ya que SharePoint se considera un entorno de colaboración, al contrario que el buzón de un usuario o la cuenta de OneDrive.

**OneDrive**:

Si un usuario abandona la organización, los archivos que estén sujetos a una directiva de retención o que tengan una etiqueta de retención permanecerán sujetos a la configuración de retención durante el período de retención especificado en la directiva o etiqueta. Durante ese tiempo, todo el acceso compartido sigue funcionando y el contenido sigue siendo detectable mediante la búsqueda de contenido y eDiscovery. 

Cuando expira el período de retención y la configuración de retención incluye una acción de eliminación, el contenido se mueve a la papelera de reciclaje de colección de sitios y solo el administrador puede acceder a él.

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si va a configurar la retención en Microsoft 365 por primera vez, consulte [Introducción a la administración del ciclo de vida de los datos](get-started-with-data-lifecycle-management.md).

Si está listo para configurar una directiva de retención o etiqueta de retención para Exchange, consulte las siguientes instrucciones:
- [Crear y configurar directivas de retención](create-retention-policies.md)
- [Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)
