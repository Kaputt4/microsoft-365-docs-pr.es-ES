---
title: Administración del ciclo de vida de los datos de Microsoft Purview y Administración de registros de Microsoft Purview
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
recommendations: false
description: Implemente funcionalidades de Administración del ciclo de vida de los datos de Microsoft Purview y Administración de registros de Microsoft Purview para controlar los datos según los requisitos normativos o de cumplimiento.
ms.openlocfilehash: 5b23a81fcf19a985665b536f418c5a5de1d88cb6
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106172"
---
# <a name="govern-your-data-with-microsoft-purview"></a>Controlar los datos con Microsoft Purview

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Use las capacidades de **Administración del ciclo de vida de los datos de Microsoft Purview** (anteriormente, Microsoft Information Governance) y **Administración de registros de Microsoft Purview** para controlar los datos según los requisitos normativos o de cumplimiento.

> [!TIP]
> ¿Quiere asignar y administrar sus datos en todo el patrimonio de datos, incluidas varias nubes y software como servicio (SaaS)? Use [Microsoft Purview Mapa de datos, Microsoft Purview Catálogo de datos y Microsoft Purview Información de recursos en los datos](/azure/purview/overview).

Desde el [punto de vista de las licencias](#licensing-requirements), puede haber una superposición considerable entre la administración del ciclo de vida de los datos y la administración de registros. Ambas soluciones admiten la retención y eliminación de datos para aplicaciones y servicios de Microsoft 365.

Use el siguiente gráfico para identificar los componentes configurables principales de estas soluciones que tienen su propia área de configuración en el portal de cumplimiento de Microsoft Purview:

![Componentes principales para configurar y usar a fin de controlar los datos con Microsoft Purview.](../media/govern-your-data.png)

En las secciones siguientes se detallan las principales funcionalidades de cada solución, con vínculos para comprender más. Sin embargo, si busca una implementación guiada, consulte [Implementación de una solución de gobierno de datos con Microsoft Purview](data-governance-solution.md).

¿Busca funcionalidades complementarias para proteger los datos? Consulte [Protección de los datos con Microsoft Purview](information-protection.md).

## <a name="microsoft-purview-data-lifecycle-management"></a>Administración del ciclo de vida de datos de Microsoft Purview

Para retener lo que necesita y eliminar lo que no:
 
|Funcionalidad|¿Qué problemas se solucionan?|
|:------|:------------|:----------------|
|[Directivas de retención para cargas de trabajo de Microsoft 365, con etiquetas de retención para excepciones](retention.md) | Le permite conservar o eliminar contenido con la administración de directivas para correo electrónico, documentos y mensajes de Teams y Yammer. |
|[Buzones de correo inactivos](inactive-mailboxes-in-office-365.md)| Le permite conservar el contenido del buzón después de que los empleados abandonen la organización para que este contenido siga siendo accesible para los administradores, los responsables de cumplimiento y los administradores de registros. |
|[Buzones de archivo](archive-mailboxes.md)| Proporciona a los usuarios espacio de almacenamiento adicional en el buzón.|
|[Importar servicio para archivos PST](importing-pst-files-to-office-365.md)| Admite la importación en masa de archivos PST a buzones de Exchange Online para conservar y buscar mensajes de correo electrónico de requisitos de cumplimiento o normativos |

¿Quiere obtener más información? Consulte [Más información sobre la administración del ciclo de vida de los datos](data-lifecycle-management.md).

¿Está listo para empezar a usar algunas o todas estas funcionalidades? Consulte [Introducción a la administración del ciclo de vida de los datos](get-started-with-data-lifecycle-management.md).


## <a name="microsoft-purview-records-management"></a>Administración de registros de Microsoft Purview

Administre los elementos de gran valor para los requisitos de mantenimiento de registros empresariales, legales o normativos:

|Funcionalidad|¿Qué problemas se solucionan?|
|:---------|:---------------------------|
|[Plan de archivos](file-plan-manager.md)| Permite crear etiquetas de retención de forma interactiva o importarlas de forma masiva y exportarlas para su análisis. Las etiquetas admiten información administrativa adicional (opcional) para ayudarle a identificar y realizar un seguimiento de los requisitos empresariales o normativos. |
|[Etiquetas de retención para elementos individuales, directivas de retención si es necesario para la retención de línea base](retention.md)| Las etiquetas admiten programaciones flexibles de retención y eliminación que se pueden aplicar manual o automáticamente, con la declaración de registros cuando sea necesario. |
|[Revisión de eliminación y prueba de eliminación](disposition.md)| Revisión manual del contenido antes de su eliminación permanente, con prueba de eliminación de registros.|

¿Quiere obtener más información? Consulte [Más información sobre la administración de registros](records-management.md)

¿Está listo para empezar a usar algunas o todas estas funcionalidades? Consulte [Introducción a la administración de registros](get-started-with-records-management.md).


## <a name="licensing-requirements"></a>Requisitos de licencias

Para saber cuáles son los requisitos y opciones de licencia, consulte la información de la guía de Microsoft 365 de seguridad y cumplimiento, en la sección [Administración del ciclo de vida de datos de Microsoft Purview y Administración de registros de Microsoft Purview](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management), para conocer los requisitos de licencia de nivel de característica.