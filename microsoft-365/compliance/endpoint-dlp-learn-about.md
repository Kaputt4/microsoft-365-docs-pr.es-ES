---
title: Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 Endpoint (versión preliminar)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'La prevención de pérdida de datos de Microsoft 365 Endpoint amplía la supervisión de las actividades de archivo y de las acciones de protección de estos archivos en los puntos de conexión. Los archivos se exponen en las soluciones del Centro de cumplimiento de Microsoft 365 '
ms.openlocfilehash: 3dedf8f3134dbdd00c45e6b0aed741a3b3173984
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931974"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a>Más información sobre la prevención de pérdida de datos en punto de conexión de Microsoft 365 (versión preliminar)

Puede usar la prevención de pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se realizan en elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido accidental de estos elementos. Para obtener más información sobre DLP, consulte [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md).

**La prevención de pérdida de datos en punto de conexión** (Endpoint DLP) amplía la supervisión de la actividad y las capacidades de protección de DLP a elementos confidenciales que estén en dispositivos con Windows 10. Una vez que los dispositivos están incorporados en las soluciones del Centro de cumplimiento de Microsoft 365, la información sobre las acciones de los usuarios relacionadas con los elementos confidenciales se hace visible en el[explorador de actividades](data-classification-activity-explorer.md), y se pueden aplicar acciones de protección a estos elementos mediante [directivas DLP](create-test-tune-dlp-policy.md).

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Actividades en punto de conexión que puede supervisar y sobre las que puede tomar medidas

DLP en punto de conexión de Microsoft le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10. Esto incluye:


|actividad en el elemento |auditable/restringible  |
|---------|---------|
|creado    | auditable      |
|nombre cambiado    |  auditable       |
|se copió a un medio extraíble o se creó en un medio extraíble     |     auditable y restringible|
|se copió al recurso compartido de red, por ejemplo \\my-server\fileshare   |     auditable y restringible    |
|impreso |    auditable y restringible       |
|se copió en la nube a través de Chromium Edge    |   auditable y restringible        |
|se accedió mediante aplicaciones y exploradores no permitidos    |  auditable y restringible       |

## <a name="whats-different-in-endpoint-dlp"></a>¿Qué es diferente en DLP en punto de conexión?

Debe tener en cuenta algunos conceptos adicionales antes de profundizar en DLP en punto de conexión.

### <a name="enabling-device-management"></a>Habilitar la administración de dispositivos

La administración de dispositivos es la funcionalidad que permite la colección de telemetría desde dispositivos y la incluye en las soluciones de cumplimiento de Microsoft 365 como DLP en punto de conexión y la [administración de riesgos internos](insider-risk-management.md). Necesitará incorporar todos los dispositivos que quiera usar como ubicaciones en directivas DLP.

> [!div class="mx-imgBorder"]
> ![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

La incorporación y la retirada se controlan mediante scripts que se descargan desde el centro de la administración de dispositivos. El centro tiene scripts personalizados para cada uno de estos métodos de implementación:

- script local (hasta 10 equipos)
- Directiva de grupo
- System Center Configuration Manager (versión 1610 o posterior)
- Administración de dispositivos móviles/Microsoft Intune
- Scripts de incorporación de VDI para equipos no persistentes

> [!div class="mx-imgBorder"]
> ![página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Use los procedimientos descritos en la [Introducción a la DLP en Microsoft 365 Endpoint](endpoint-dlp-getting-started.md) para incorporar dispositivos.

Si incorporó dispositivos a través de [Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.

> [!div class="mx-imgBorder"]
> ![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Visualizar datos sobre la DLP de Endpoint

 DLP de Endpoint supervisa la actividad basada en un tipo de extensiones multipropósito de correo Internet (MIME), por lo que las actividades se capturan incluso si se cambia la extensión de archivo. En la versión preliminar pública, se inspeccionan los siguientes archivos:

- archivos de Word
- archivos de PowerPoint
- archivos de Excel
- archivos PDF
- archivos .csv
- archivos .tsv
- archivos .txt
- archivos .rtf
- archivos .c
- archivos .class
- archivos .cpp
- archivos .cs
- archivos .h
- archivos .java

> [!NOTE]
> La DLP de Endpoint evalúa todos los tipos de archivo anteriores según la directiva DLP y aplica las acciones de protección correspondientes. Todos los archivos que coinciden con una directiva DLP, estén o no bloqueados, se auditan para todas las acciones admitidas. Además, la actividad de archivo que se lleva a cabo en cualquier archivo de Word, PowerPoint, Excel, PDF o archivo .csv se audita de forma predeterminada, independientemente de si existe una directiva DLP o si estos archivos coinciden.

Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye al explorador de actividad, incluso antes de que configure e implemente alguna directivas DLP que tenga dispositivos como ubicación.

> [!div class="mx-imgBorder"]
> ![eventos de DLP de Endpoint en el explorador de actividad](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

DLP de Endpoint recopila información exhaustiva sobre la actividad auditada.

Por ejemplo, si se copia un archivo a un medio USB extraíble, vería estos atributos en los detalles de actividad:

- tipo de actividad
- IP del cliente
- ruta de acceso del archivo de destino
- ocurrió una marca de tiempo
- nombre de archivo
- usuario
- extensión de archivo
- tamaño de archivo
- tipo de información confidencial (si corresponde)
- valor sha1
- valor sha256
- nombre de archivo anterior
- ubicación
- primario
- ruta de acceso al archivo
- tipo de ubicación de origen
- plataforma
- nombre de dispositivo
- tipo de ubicación de destino
- aplicación que realizó la copia
- Id. de dispositivo de Microsoft Defender para punto de conexión (si corresponde)
- fabricante del dispositivo multimedia extraíble
- modelo del dispositivo multimedia extraíble
- número de serie del dispositivo multimedia extraíble

> [!div class="mx-imgBorder"]
> ![copiar a los atributos de actividad del USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>Siguientes pasos

Ahora que ya conoce DLP en punto de conexión, estos son los pasos siguientes:

1) [Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)](endpoint-dlp-getting-started.md)
2) [Uso de la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)](endpoint-dlp-using.md)

## <a name="see-also"></a>Vea también

- [Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)](endpoint-dlp-getting-started.md)
- [Uso de la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)](endpoint-dlp-using.md)
- [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/)
- [Administración de riesgos internos](insider-risk-management.md)
