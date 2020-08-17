---
title: Usar etiquetas de retención para declarar registros
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
description: Usar etiquetas de retención para declarar registros.
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695282"
---
# <a name="declare-records-by-using-retention-labels"></a>Usar etiquetas de retención para declarar registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Puede usar las [etiquetas de retención](retention.md#retention-labels) para marcar el contenido como un registro. Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.

## <a name="configuring-retention-labels-to-declare-records"></a>Configurar etiquetas de retención para declarar registros

Cuando cree una [etiqueta de retención](retention.md#retention-labels), seleccione la opción para marcar el contenido como un registro.

>[!NOTE] 
> La opción para marcar el contenido como un registro no está disponible al crear o configurar las etiquetas de retención de **Gobierno de la información** en el Centro de cumplimiento de Microsoft 365. En su lugar, debe usar **Administración de registros**.

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de registros** \> **Plan de archivos**. En la página **Plan de archivos**, seleccione **Crear una etiqueta**.

2. En la página **Configuración de la etiqueta** del asistente, elija la opción para clasificar el contenido como un registro.
    
   ![Haga clic en la casilla Usar una etiqueta para clasificar contenido como un "registro"](../media/recordversioning6.png)

3. Aplique la etiqueta de retención a los documentos de SharePoint o OneDrive y los correos electrónicos de Exchange, según sea necesario. Para obtener instrucciones, consulte:
    
    - [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
    
    - [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a>Aplicar una etiqueta de retención configurada al contenido

Cuando las etiquetas de retención que marcan el contenido como un registro se ponen a disposición de los usuarios para que las usen en aplicaciones:

- Para Exchange, todos los usuarios con acceso de escritura al buzón pueden aplicar las etiquetas. 
- Para SharePoint y OneDrive, cualquier usuario del grupo predeterminado de miembros (con nivel de permisos de contribución) puede aplicar las etiquetas.

Ejemplo de un documento marcado como registro con una etiqueta de retención:

![Panel de detalles para los documentos etiquetados como registro](../media/recordversioning7.png)

## <a name="next-steps"></a>Pasos siguientes

Si necesita actualizar documentos que son registros, vea [Usar el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive](record-versioning.md).

Para más información sobre la eliminación de registros, consulte [Eliminación del contenido](disposition.md).
