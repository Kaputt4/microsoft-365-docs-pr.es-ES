---
title: Más información sobre la prevención de pérdida de datos en punto de conexión de Microsoft 365 (versión preliminar)
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
description: 'La prevención de pérdida de datos en punto de conexión de Microsoft 365 amplía la supervisión de las actividades de archivo y de las acciones de protección de estos archivos a los puntos de conexión. Los archivos se hacen visibles en las soluciones de cumplimiento de Microsoft 365 '
ms.openlocfilehash: fe4ce05c1f9dd0ebce9a6c3be6fffbecfb36c2af
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379230"
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

![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

La incorporación y la retirada se controlan mediante scripts que se descargan desde el centro de administración de dispositivos. El centro tiene scripts personalizados para cada uno de estos métodos de implementación:

- script local (hasta 10 equipos)
- Directiva de grupo
- System Center Configuration Manager (versión 1610 o posterior)
- Administración de dispositivos móviles/Microsoft Intune
- Scripts de incorporación de VDI para equipos no persistentes

![Página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Use los procedimientos descritos en [Introducción a DLP en punto de conexión de Microsoft 365](endpoint-dlp-getting-started.md) para incorporar dispositivos.

Si incorporó dispositivos a través de [la protección contra amenazas avanzada de Microsoft Defender (ATP de Microsoft defender)](https://docs.microsoft.com/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.

![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Visualizar datos de DLP en punto de conexión

 DLP en punto de conexión supervisa la actividad basado en un tipo MIME, por lo que las actividades se capturan incluso si se cambia la extensión de archivo. En la versión preliminar pública, inspecciona los siguientes:

- archivos de Word
- archivos de PowerPoint
- archivos de Excel
- archivos PDF
- archivos .csv
- archivos .tsv
- archivos c
- archivos de clase
- archivos cpp
- archivos cs
- archivos h
- archivos Java

> [!NOTE]
> De forma predeterminada, los archivos .txt y archivos de código fuente no se auditan, DLP los evalúa frente a las directivas aplicadas y, a continuación, las acciones del usuario se auditan o se bloquean en consecuencia.

Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye al explorador de actividad, incluso antes de que configure e implemente las directivas DLP que tienen dispositivos como ubicación.

![eventos de DLP en punto de conexión en el explorador de actividad](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

DLP en punto de conexión recopila información exhaustiva sobre la actividad auditada.

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

![copiar a atributos de actividad USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>Pasos siguientes

Ahora que ya conoce DLP en punto de conexión, estos son los pasos siguientes:

1) [Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)](endpoint-dlp-getting-started.md)
2) [Uso de la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)](endpoint-dlp-using.md)

## <a name="see-also"></a>Vea también

- [Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)](endpoint-dlp-getting-started.md)
- [Uso de la prevención de pérdida de datos en punto de conexión de Microsoft (versión preliminar)](endpoint-dlp-using.md)
- [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Protección contra amenazas avanzada de Microsoft Defender (ATP de Microsoft Defender)](https://docs.microsoft.com/windows/security/threat-protection/)
- [Administración de riesgos internos](insider-risk-management.md)