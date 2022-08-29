---
title: Información sobre la administración del ciclo de vida de datos de Microsoft Purview
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
description: Obtenga información sobre cómo la administración del ciclo de vida de datos de Microsoft Purview le ayuda a mantener lo que necesita y a eliminar lo que no.
ms.openlocfilehash: 6252bb9824a534ffca5f295bf9f9c54816bcb320
ms.sourcegitcommit: a1c86e51f6fec7517356251c3b99b1a86705c8c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2022
ms.locfileid: "67336696"
---
# <a name="learn-about-data-lifecycle-management"></a>Más información sobre la administración del ciclo de vida de los datos

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

La administración del ciclo de vida de datos de Microsoft Purview (anteriormente gobernanza de información de Microsoft) le proporciona herramientas y capacidades para conservar el contenido que necesita conservar y eliminar el que no. 

A menudo, es necesario conservar y eliminar contenido para el cumplimiento y los requisitos normativos, pero eliminar contenido que ya no tiene valor empresarial también le ayuda a administrar el riesgo y la responsabilidad. Por ejemplo, reduce la superficie de ataque.

## <a name="microsoft-365-features"></a>Características de Microsoft 365

Las **directivas de retención** son la piedra angular para la administración del ciclo de vida de los datos. Úselas para las cargas de trabajo de Microsoft 365 que incluyen Exchange, SharePoint, OneDrive, Teams y Yammer. Configure si el contenido de estos servicios debe conservarse indefinidamente o durante un período específico si los usuarios lo editan o eliminan. O bien, puede configurar la directiva para eliminar automáticamente el contenido de forma permanente después de un período especificado si aún no se ha eliminado. También puede combinar estas dos acciones para conservar y luego eliminar, que es una configuración muy típica. Por ejemplo, conservar el correo electrónico durante tres años y después eliminarlo.

Al configurar una directiva de retención, puede dirigirse a todas las instancias de la organización (por ejemplo, a todos los buzones de correo y a todos los sitios de SharePoint) o a instancias individuales (por ejemplo, solo a los buzones de correo de departamentos o regiones específicos, o solo a sitios seleccionados de SharePoint).

Si necesita excepciones para correos electrónicos o documentos individuales, como un período de retención más largo para documentos legales, puede hacerlo con **etiquetas de retención** publicadas en las aplicaciones para que los usuarios puedan aplicarlas o aplicarlas automáticamente inspeccionando el contenido.

Para obtener más información acerca de las directivas de retención y las etiquetas de retención, y cómo funciona la retención en Microsoft 365, consulte [Más información sobre las directivas y las etiquetas de retención](retention.md). 

> [!NOTE]
> Si necesita administrar elementos de gran valor para cumplir requisitos de retención de registros empresariales, legales o normativos, use etiquetas de retención con [administración de registros](records-management.md) en lugar de etiquetas de retención con administración del ciclo de vida de los datos.

Otras funcionalidades de administración del ciclo de vida de los datos para ayudarle a mantener lo que necesita y eliminar lo que no:

- **Archivado de buzones de correo** para proporcionar a los usuarios espacio adicional de almacenamiento en los buzones y archivado de expansión automática para buzones que necesitan más de 100 GB de almacenamiento. Una directiva de archivado predeterminada mueve automáticamente el correo electrónico al buzón de archivo y, si en caso necesario, puede personalizar esta directiva. Para obtener más información acerca del archivado de buzones, consulte [Más información sobre los buzones de archivo](archive-mailboxes.md).
    
- **Buzones inactivos** que conservan el contenido del buzón después de que los empleados abandonen la organización. Para obtener más información acerca de los buzones inactivos, consulte [Más información sobre buzones inactivos](inactive-mailboxes-in-office-365.md).

- **Servicio de importación para archivos PST** mediante la carga de red o el envío de unidades. Para obtener más información, consulte [Más información sobre la importación de archivos PST de su organización](importing-pst-files-to-office-365.md).

## <a name="exchange-legacy-features"></a>Características de Exchange (heredadas)

**Las directivas de retención y las etiquetas de retención** de la administración de registros de mensajería (MRM) y **las reglas de registro en diario** son características de cumplimiento anteriores de Exchange que se configuraron originalmente desde el Centro de administración de Exchange clásico. No se han presentado al [nuevo Centro de administración de Exchange](/exchange/features-in-new-eac).

Si aún no usa estas características o tiene un requisito empresarial específico para usarlas en lugar de las características de Microsoft 365 para la administración del ciclo de vida de datos, no se recomienda usar estas características de cumplimiento anteriores. En su lugar, use las características más recientes de Microsoft 365 que conservan los datos en su lugar y las directivas de soporte técnico en otros servicios de Microsoft 365.

Para más información, consulte [Usar directivas y etiquetas de retención en lugar de características anteriores](retention.md#use-retention-policies-and-retention-labels-instead-of-older-features).


## <a name="deployment-guidance"></a>Instrucciones de implementación

Para obtener instrucciones de implementación para la administración del ciclo de vida de los datos, que incluye una guía de implementación recomendada, información de licencias, permisos, una lista de escenarios admitidos y documentación para el usuario final, consulte [Introducción a la administración del ciclo de vida de los datos](get-started-with-information-governance.md).

¿Está buscando instrucciones de implementación para proteger sus datos? Consulte [Implementar una solución de protección de la información con Microsoft Purview](information-protection-solution.md).

