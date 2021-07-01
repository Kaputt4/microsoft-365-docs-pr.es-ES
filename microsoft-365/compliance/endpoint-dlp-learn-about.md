---
title: Obtenga más información sobre la Prevención de pérdida de datos de Microsoft 365 de punto de conexión
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
description: 'La Prevención de pérdida de datos en punto de conexión de Microsoft 365 amplía la supervisión de las actividades de archivo y de las acciones de protección de estos archivos en los puntos de conexión. Los archivos se hacen visibles en las soluciones de cumplimiento de Microsoft 365 '
ms.openlocfilehash: 39474f54440ba33c8d7140981c1495a5c46bf0fc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226688"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión

Puede usar la prevención de pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se realizan en elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido accidental de estos elementos. Para más información sobre DLP en punto de conexión de Microsoft, consulte [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md).

**La prevención de pérdida de datos en punto de conexión** (Endpoint DLP) amplía la supervisión de la actividad y las capacidades de protección de DLP a elementos confidenciales que estén en dispositivos con Windows 10. Una vez que los dispositivos están incorporados en las soluciones del Centro de cumplimiento de Microsoft 365, la información sobre las acciones de los usuarios relacionadas con los elementos confidenciales se hace visible en el[explorador de actividades](data-classification-activity-explorer.md), y se pueden aplicar acciones de protección a estos elementos mediante [directivas DLP](create-test-tune-dlp-policy.md).

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Actividades en punto de conexión que puede supervisar y sobre las que puede tomar medidas

DLP en punto de conexión de Microsoft le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10.

|Actividad |Descripción  | Auditable/Restringible|
|---------|---------|---------|
|cargar en el servicio en la nube o acceso por exploradores no permitidos    | Detecta cuándo un usuario intenta cargar un elemento en un dominio de servicio restringido o tener acceso a un elemento con un explorador.  Si usa un explorador que se muestra en DLP como un explorador que no es el permitido, la actividad de carga se bloqueará y se redirigirá al usuario para usar la arista de cromo. Por último, cromo puede permitir o bloquear la carga o el acceso en función de la configuración de la Directiva DLP.         |auditable y restringible|
|copiar a otra aplicación    |Se detecta cuando un usuario intenta copiar información de un elemento protegido y, a continuación, lo pega en otra aplicación, proceso o elemento. Esta actividad no detecta la copia y el pegado de información dentro de la misma aplicación, proceso o elemento.         | auditable y restringible|
|copiar en un medio extraíble USB |Detecta cuando un usuario intenta copiar un elemento o información en un medio extraíble o un dispositivo USB.         | auditable y restringible|
|Copiar en un recurso compartido de red    |Detecta cuando un usuario intenta copiar un elemento en un recurso compartido de red o en una unidad de red asignada         |auditable y restringible|
|imprimir un documento    |Detecta cuando un usuario intenta imprimir un elemento protegido en una impresora local o de red.| auditable y restringible         |
|copiar a una sesión remota|Detecta cuando un usuario intenta copiar un elemento a una sesión de escritorio remoto |  auditable y restringible|
|copiar en un dispositivo Bluetooth|Detecta cuando un usuario intenta copiar un elemento en una aplicación Bluetooth no permitida (según se define en la lista de aplicaciones de Bluetooth no permitidas en la configuración del punto de conexión DLP).| auditable y restringible|
|crear un elemento|Detecta cuándo un usuario crea un elemento| auditable|
|cambiar el nombre de un elemento|Detecta cuando un usuario cambia el nombre de un elemento| auditable|

## <a name="monitored-files"></a>Archivos supervisados

La DLP en punto de conexión admite la supervisión de estos tipos de archivo:

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

De forma predeterminada, la DLP en punto de conexión audita las actividades para estos tipos de archivo, incluso si no hay una coincidencia de directiva. Si solo quiere supervisar los datos de las coincidencias de directivas, puede desactivar **Auditar siempre para la actividad de archivos de los dispositivos** en la configuración global de DLP en punto de conexión. Si esta configuración está instalada, las actividades de cualquier archivo Word, PowerPoint, Excel, PDF y .csv siempre se auditan, incluso si el dispositivo no está dirigido por ninguna directiva.

DLP en punto de conexión supervisa la actividad basada en un tipo de extensiones multipropósito de correo Internet (MIME), por lo que las actividades se capturan incluso si se cambia la extensión de archivo.

## <a name="whats-different-in-endpoint-dlp"></a>¿Qué es diferente en DLP en punto de conexión?

Debe tener en cuenta algunos conceptos adicionales antes de profundizar en DLP en punto de conexión.

### <a name="enabling-device-management"></a>Habilitar la administración de dispositivos

La administración de dispositivos es la funcionalidad que permite la colección de telemetría desde dispositivos y la incluye en las soluciones de cumplimiento de Microsoft 365 como DLP en punto de conexión y la [administración de riesgos internos](insider-risk-management.md). Necesitará incorporar todos los dispositivos que quiera usar como ubicaciones en directivas DLP.

> [!div class="mx-imgBorder"]
> ![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

La incorporación y la retirada se controlan mediante scripts que se descargan desde el centro de administración de dispositivos. El centro tiene scripts personalizados para cada uno de estos métodos de implementación:

- script local (hasta 10 equipos)
- Directiva de grupo
- System Center Configuration Manager (versión 1610 o posterior)
- Administración de dispositivos móviles/Microsoft Intune
- Scripts de incorporación de VDI para equipos no persistentes

> [!div class="mx-imgBorder"]
> ![página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Use los procedimientos descritos en [Introducción a DLP en punto de conexión de Microsoft 365](endpoint-dlp-getting-started.md) para incorporar dispositivos.

Si incorporó dispositivos a través de [Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.

> [!div class="mx-imgBorder"]
> ![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Visualizar datos de DLP en punto de conexión

Puede ver las alertas relacionadas con las directivas DLP ejecutadas en los dispositivos de punto de conexión si va al [Panel de administración de alertas de DLP](dlp-configure-view-alerts-policies.md).

> [!div class="mx-imgBorder"]
> ![Información de la alerta](../media/Alert-info-1.png)

También puede ver los detalles del evento asociado con metadatos enriquecidos en el mismo panel

> [!div class="mx-imgBorder"]
> ![información del evento](../media/Event-info-1.png)

Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye al explorador de actividad, incluso antes de que configure e implemente las directivas DLP que tienen dispositivos como ubicación.

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

## <a name="next-steps"></a>Pasos siguientes

Ahora que ya conoce DLP en punto de conexión, estos son los pasos siguientes:

1. [Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft](endpoint-dlp-getting-started.md)
2. [Uso de la prevención de pérdida de datos en punto de conexión de Microsoft](endpoint-dlp-using.md)

## <a name="see-also"></a>Consulte también

- [Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft](endpoint-dlp-getting-started.md)
- [Uso de la prevención de pérdida de datos en punto de conexión de Microsoft](endpoint-dlp-using.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Crear, probar y optimizar una directiva DLP](create-test-tune-dlp-policy.md)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Microsoft Defender para punto de conexión](/windows/security/threat-protection/)
- [Administración de riesgos internos](insider-risk-management.md)
