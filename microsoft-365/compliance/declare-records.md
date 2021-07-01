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
ms.openlocfilehash: ba0587619609adba2d7746a45a3b24008a4a00be
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227000"
---
# <a name="declare-records-by-using-retention-labels"></a>Usar etiquetas de retención para declarar registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Para declarar documentos y correos electrónicos como [registros](records-management.md#records), use las [etiquetas de retención](retention.md#retention-labels) que marcan el contenido como **registro** o como **registro normativo**.

Si no está seguro de si debe usar un registro o un registro normativo, consulte [Comparar las restricciones de las acciones que se permiten o se bloquean](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked). Si necesita usar registros normativos, primero tiene que ejecutar un comando de PowerShell, como se describe en la sección siguiente.

Podrá entonces, o bien publicar dichas etiquetas en una directiva de etiquetas de retención (de modo que los usuarios y administradores puedan aplicarlas al contenido), o bien, en el caso de las etiquetas que marcan elementos como registros (no como registros normativos), podrá aplicarlas automáticamente al contenido que desee declarar como registro.

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a>Cómo mostrar la opción para marcar contenido como un registro normativo

> [!NOTE]
> El procedimiento siguiente es una acción auditable, con el registro **Opción de registro normativo habilitado para las etiquetas de retención** en la sección [Directivas de retención y actividades de etiqueta de retención](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) del registro de auditoría.

De forma predeterminada, la opción de etiqueta de retención para marcar contenido como un registro normativo no se muestra en el asistente de etiquetas de retención. Para mostrar esta opción, primero tiene que ejecutar un comando de PowerShell:

1. [Conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365.](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)

2. Ejecute el siguiente cmdlet:

    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````

    No se pide confirmación y la configuración surte efecto inmediatamente.

Si cambia de opinión sobre cómo ver esta opción en el asistente de etiquetas de retención, puede ocultarla de nuevo ejecutando el mismo cmdlet con el valor **false**: `Set-RegulatoryComplianceUI -Enabled $false`

## <a name="configuring-retention-labels-to-declare-records"></a>Configurar etiquetas de retención para declarar registros

Al crear una etiqueta de retención de la solución **administración de registros** del Centro de cumplimiento de Microsoft 365, tiene la opción de marcar los elementos como un registro. Si ha ejecutado el comando de PowerShell de la sección anterior, como alternativa puede marcar los elementos como un registro normativo.

Por ejemplo:

![Configurar una etiqueta de retención para marcar contenido como un registro o como un registro normativo](../media/recordversioning6.png)

Ahora puede aplicar esta etiqueta de retención a documentos de SharePoint o OneDrive y a correos electrónicos de Exchange, según sea necesario.

Instrucciones completas:

- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)

- [Aplicar una etiqueta de retención a contenido automáticamente](apply-retention-labels-automatically.md) (no es compatible con los registros normativos)


## <a name="applying-the-configured-retention-label-to-content"></a>Aplicar una etiqueta de retención configurada al contenido

Cuando las etiquetas de retención que marcan elementos como un registro o como un registro normativo se ponen a disposición de los usuarios para aplicarlas a aplicaciones:

- Para Exchange, todos los usuarios con acceso de escritura al buzón pueden aplicar las etiquetas.
- Para SharePoint y OneDrive, cualquier usuario del grupo predeterminado de miembros (con nivel de permisos de contribución) puede aplicar las etiquetas.

Ejemplo de un documento marcado como registro con una etiqueta de retención:

![Panel de detalles para los documentos etiquetados como registro](../media/recordversioning7.png)

## <a name="searching-the-audit-log-for-labeled-items-that-were-declared-records"></a>Buscar en el registro de auditoría elementos etiquetados que se declararon como registros

Las acciones de etiquetado para declarar elementos como registros se registran en el registro de auditoría.

Para elementos de SharePoint:
- En **Actividades de archivos y páginas**, seleccione **Etiqueta de retención cambiada para un archivo**. Este evento de auditoría es para etiquetas de retención que marcan elementos como registros, registros normativos o que son etiquetas de retención estándar.

Para elementos de Exchange:
- En **Actividades del buzón de Exchange**, seleccione **Mensaje etiquetado como registro**. Este evento de auditoría es para las etiquetas de retención que marcan los elementos como registros o registros reglamentarios.

Para obtener más información sobre cómo buscar estos eventos, vea [Buscar en el registro de auditoría del Centro de Seguridad y Cumplimiento](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).

## <a name="next-steps"></a>Pasos siguientes

Para obtener una lista de los escenarios admitidos por la administración de registros, vea [Escenarios comunes de la administración de registros](get-started-with-records-management.md#common-scenarios-for-records-management).
