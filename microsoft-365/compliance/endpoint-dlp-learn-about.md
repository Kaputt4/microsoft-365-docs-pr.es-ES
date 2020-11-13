---
title: Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión
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
description: 'La prevención de pérdida de datos de Microsoft 365 Endpoint amplía la supervisión de las actividades de archivo y las acciones de protección para estos archivos en los puntos de conexión. Los archivos se hacen visibles en las soluciones de cumplimiento de Microsoft 365 '
ms.openlocfilehash: 966e201acb8038d85f0d06c0800c9845fd79097e
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984934"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión

Puede usar la prevención de la pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se realizan en elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido no intencionado de estos elementos. Para obtener más información sobre DLP, vea [información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md).

**Prevención de la pérdida de datos en punto de conexión** (DLP en punto de conexión) amplía las funciones de supervisión y protección de la actividad de DLP a elementos confidenciales que estén en dispositivos con Windows 10. Una vez que los dispositivos están integrados en las soluciones de cumplimiento de Microsoft 365, la información sobre lo que los usuarios llevan a cabo con elementos confidenciales se hace visible en el [Explorador de actividades](data-classification-activity-explorer.md) y puede aplicar acciones de protección a estos elementos mediante las [Directivas DLP](create-test-tune-dlp-policy.md).

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Actividades en punto de conexión que puede supervisar y sobre las que puede tomar medidas

Microsoft Endpoint DLP le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10. Se incluye lo siguiente:


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

La administración de dispositivos es la funcionalidad que permite la recopilación de telemetría de dispositivos y la incluye en las soluciones de cumplimiento de Microsoft 365 como el Endpoint DLP y la [Administración de riesgos de Insider](insider-risk-management.md). Necesitará incorporar todos los dispositivos que quiera usar como ubicaciones en directivas DLP.

> [!div class="mx-imgBorder"]
> ![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

La incorporación y retirada se controla mediante scripts que descarga desde el centro de administración de dispositivos. El centro tiene scripts personalizados para cada uno de estos métodos de implementación:

- script local (hasta 10 equipos)
- Directiva de grupo
- System Center Configuration Manager (versión 1610 o posterior)
- Administración de dispositivos móviles/Microsoft Intune
- Scripts de incorporación de VDI para equipos no persistentes

> [!div class="mx-imgBorder"]
> ![página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Use los procedimientos descritos en la [Introducción a la DLP en punto de conexión en Microsoft 365](endpoint-dlp-getting-started.md) para incorporar dispositivos.

Si incorporó dispositivos a través de [Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.

> [!div class="mx-imgBorder"]
> ![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Visualizar datos sobre la DLP en punto de conexión

 DLP en punto de conexión supervisa actividad basada en un tipo MIME, por lo que las actividades se capturarán aunque se cambie la extensión de archivo. En la vista previa pública, vigila todas las siguientes:

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
> DLP en punto de conexión evalúa los archivos de todos los tipos anteriores en la directiva de DLP y aplica las acciones de protección correspondientes. Todos los archivos que coinciden con una directiva de DLP se auditan para todas las acciones admitidas, aunque no estén bloqueados. Además, la actividad de archivos que se lleva a cabo en cualquier archivo Word, PowerPoint, Excel, PDF y .csv se audita de forma predeterminada, independientemente de si una directiva de DLP existe o coincide con estos archivos.

Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye hacia el explorador de actividades incluso antes de configurar e implementar cualquier directiva de DLP que tenga dispositivos como ubicación.

> [!div class="mx-imgBorder"]
> ![eventos de DLP en punto de conexión en el explorador de actividad](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

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
