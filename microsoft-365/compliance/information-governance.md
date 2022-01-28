---
title: Más información sobre el gobierno de la información en Microsoft 365
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
- m365initiative-compliance
description: Obtenga información sobre lo que significa gobernar los datos de su organización con Microsoft 365.
ms.openlocfilehash: c9661aadcef5d70b4099cb44e0fa054ab27e5562
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242230"
---
# <a name="learn-about-information-governance"></a>Más información sobre el gobierno de la información

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Como parte de [Microsoft Information Governance](manage-information-governance.md), que también incluye la [administración de registros](records-management.md) y los [conectores de datos](archiving-third-party-data.md), el gobierno de la información de Microsoft 365 le proporciona herramientas y capacidades para conservar el contenido que necesita conservar y eliminar el contenido que no. A menudo, es necesario conservar y eliminar contenido para el cumplimiento y los requisitos normativos, pero eliminar contenido que ya no tiene valor empresarial también le ayuda a administrar el riesgo y la responsabilidad. Por ejemplo, reduce la superficie de ataque.

Las **directivas de retención** son la piedra angular del gobierno de la información. Úselas para las cargas de trabajo de Microsoft 365 que incluyen Exchange, SharePoint, OneDrive, Teams y Yammer. Configure si el contenido de estos servicios debe conservarse indefinidamente o durante un período específico si los usuarios lo editan o eliminan. O bien, puede configurar la directiva para eliminar automáticamente el contenido de forma permanente después de un período especificado si aún no se ha eliminado. También puede combinar estas dos acciones para conservar y luego eliminar, que es una configuración muy típica. Por ejemplo, conservar el correo electrónico durante tres años y después eliminarlo.

Al configurar una directiva de retención, puede dirigirse a todas las instancias de la organización (por ejemplo, a todos los buzones de correo y a todos los sitios de SharePoint) o a instancias individuales (por ejemplo, solo a los buzones de correo de departamentos o regiones específicos, o solo a sitios seleccionados de SharePoint).

Si necesita excepciones para correos electrónicos o documentos individuales, como un período de retención más largo para documentos legales, puede hacerlo con **etiquetas de retención** publicadas en las aplicaciones para que los usuarios puedan aplicarlas o aplicarlas automáticamente inspeccionando el contenido.

Para obtener más información acerca de las directivas de retención y las etiquetas de retención, y cómo funciona la retención en Microsoft 365, consulte [Más información sobre las directivas y las etiquetas de retención](retention.md). 

> [!NOTE]
> Si necesita administrar del ciclo de vida de elementos de gran valor para requisitos empresariales, legales o de mantenimiento de registros normativos, use etiquetas de retención con [administración de registros](records-management.md), en lugar de etiquetas de retención con gobierno de la información.

Otras funcionalidades de gobierno de la información para ayudarle a conservar lo que necesita y eliminar lo que no:

- **Archivado de buzones de correo** para proporcionar a los usuarios espacio adicional de almacenamiento en los buzones y archivado de expansión automática para buzones que necesitan más de 100 GB de almacenamiento. Una directiva de archivado predeterminada mueve automáticamente el correo electrónico al buzón de archivo y, si en caso necesario, puede personalizar esta directiva. Para obtener más información acerca del archivado de buzones, consulte [Más información sobre los buzones de archivo](archive-mailboxes.md).
    
- **Buzones inactivos** que conservan el contenido del buzón después de que los empleados abandonen la organización. Para obtener más información acerca de los buzones inactivos, consulte [Más información sobre buzones inactivos](inactive-mailboxes-in-office-365.md).

- **Servicio de importación para archivos PST** mediante la carga de red o el envío de unidades. Para obtener más información, consulte [Más información sobre la importación de archivos PST de su organización](importing-pst-files-to-office-365.md).

## <a name="deployment-guidance"></a>Instrucciones de implementación

Para obtener instrucciones de implementación para el gobierno de la información, que incluye una guía de implementación recomendada, información de licencias, permisos, una lista de escenarios admitidos y documentación para el usuario final, consulte [Introducción al gobierno de la información](get-started-with-information-governance.md).

¿Está buscando instrucciones de implementación para proteger sus datos? Consulte [Implementar una solución de Microsoft Information Protection](information-protection-solution.md).

