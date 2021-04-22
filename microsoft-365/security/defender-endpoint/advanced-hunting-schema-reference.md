---
title: Referencia de esquema de búsqueda avanzada
description: Obtenga información sobre las tablas del esquema de búsqueda avanzada para comprender los datos en los que puede ejecutar consultas de búsqueda de amenazas.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft Defender para endpoint, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, datos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b35cc32f776083b58bc6467be43508a805d92d9c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934350"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>Comprender el esquema de búsqueda avanzada en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

El [esquema de búsqueda](advanced-hunting-overview.md) avanzada está hecho de varias tablas que proporcionan información de eventos o información sobre dispositivos y otras entidades. Para crear consultas eficaces que abarquen varias tablas, debe comprender las tablas y las columnas del esquema de búsqueda avanzada.

## <a name="get-schema-information-in-the-security-center"></a>Obtener información de esquema en el centro de seguridad
Al crear consultas, use la referencia de esquema integrado para obtener rápidamente la siguiente información sobre cada tabla del esquema:

- **Descripción de tablas:** tipo de datos contenidos en la tabla y el origen de los datos.
- **Columnas**: todas las columnas de la tabla.
- **Tipos de acción:** valores posibles en la `ActionType` columna que representan los tipos de evento admitidos por la tabla. Esto solo se proporciona para tablas que contienen información de eventos.
- **Consulta de** ejemplo: consultas de ejemplo que ofrecen cómo se puede usar la tabla.

### <a name="access-the-schema-reference"></a>Obtener acceso a la referencia de esquema
Para obtener acceso rápidamente a la referencia de esquema, seleccione la acción **Ver** referencia junto al nombre de tabla en la representación del esquema. También puede seleccionar Referencia **de esquema para** buscar una tabla.

![Imagen que muestra cómo obtener acceso a la referencia de esquema en el portal](images/ah-reference.png)

## <a name="learn-the-schema-tables"></a>Obtenga información sobre las tablas de esquema

En la siguiente referencia se enumeran todas las tablas del esquema de búsqueda avanzada. Cada nombre de tabla está vinculado a una página donde se describen los nombres de las columnas de esa tabla.

Los nombres de tabla y columna también se enumeran en el Centro de seguridad de Microsoft Defender, en la representación del esquema en la pantalla de búsqueda avanzada.

| Nombre de tabla | Descripción |
|------------|-------------|
| **[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)** | Alertas en el Centro de seguridad de Microsoft Defender |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Información del dispositivo, incluida la información del sistema operativo |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propiedades de red de dispositivos, incluidos adaptadores, direcciones IP y MAC, así como redes y dominios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Creación de procesos y eventos relacionados |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexión de red y eventos relacionados |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Creación y modificación de archivos y otros eventos del sistema de archivos |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Creación y modificación de entradas de registro |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Inicios de sesión y otros eventos de autenticación |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Eventos de carga de DLL |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad como antivirus de Microsoft Defender y protección contra vulnerabilidades de seguridad |
| **[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)** | Información de certificado de archivos firmados obtenidos de eventos de comprobación de certificados en puntos de conexión |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventario de software instalado en dispositivos, incluida la información de versión y el estado de fin de soporte técnico |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Vulnerabilidades de software encontradas en dispositivos y la lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | La base de conocimiento de vulnerabilidades de la que se ha informado públicamente, incluyendo si el código que aprovecha la vulnerabilidad está disponible para el público |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Eventos de evaluación de administración de amenazas y vulnerabilidades, donde se indica el estado de las distintas configuraciones de seguridad de los dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Base de conocimiento de las configuraciones de seguridad utilizadas por la administración de amenazas y vulnerabilidades para evaluar dispositivos, incluidas las asignaciones a diferentes estándares y criterios de referencia |

>[!TIP]
>Use la búsqueda avanzada en [Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) para buscar amenazas con datos de Defender for Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender for Identity. [Activar Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable)<br><br>
Obtenga más información sobre cómo mover los flujos de trabajo avanzados de búsqueda de Microsoft Defender para endpoint a Microsoft 365 Defender en Migrar consultas avanzadas de búsqueda de [Microsoft Defender para endpoint](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
- [Cambios avanzados del esquema de datos de búsqueda](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
