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
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817113"
---
# <a name="declare-records-by-using-retention-labels"></a>Usar etiquetas de retención para declarar registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Para declarar documentos y correos electrónicos como un registro, use las [etiquetas de retención](retention.md#retention-labels) que marcan elementos como un registro. Puede publicar esas etiquetas de modo que los usuarios y administradores puedan aplicarlas manualmente al contenido o aplicarlas automáticamente al contenido que desee marcar como registro.

## <a name="configuring-retention-labels-to-declare-records"></a>Configurar etiquetas de retención para declarar registros

Cuando cree o configure una etiqueta de retención, seleccione la opción para marcar elementos como un registro.

>[!NOTE] 
> La opción para marcar el contenido como un registro no está disponible al crear o configurar las etiquetas de retención de **Gobierno de la información** en el Centro de cumplimiento de Microsoft 365. En su lugar, debe usar **Administración de registros**.

Siga estos pasos para crear una nueva etiqueta de retención que marque el contenido como un registro:

1. En el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com), vaya a **Administración de registros** \> **Plan de archivos**. En la página **Plan de archivos**, seleccione **Crear una etiqueta**.

2. En la página **Definir la configuración de retención** del asistente, elija la opción para marcar elementos como registros:
    
   ![Seleccionar la configuración de retención para marcar elementos como registro](../media/recordversioning6.png)

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

Para obtener una lista de los escenarios admitidos por la administración de registros, vea [Escenarios comunes de la administración de registros](get-started-with-records-management.md#common-scenarios-for-records-management).
