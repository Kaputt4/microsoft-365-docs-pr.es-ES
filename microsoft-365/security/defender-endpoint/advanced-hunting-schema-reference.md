---
title: Referencia de esquema de búsqueda avanzada
description: Obtenga información sobre las tablas del esquema de búsqueda avanzada para comprender los datos en los que puede ejecutar consultas de búsqueda de amenazas.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, mdatp, atp de Microsoft Defender, microsoft defender para punto de conexión, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, datos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: 76c9f55e99ba13417403a6f9ac2d03913f792326
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67326329"
---
# <a name="understand-the-advanced-hunting-schema-in-microsoft-defender-for-endpoint"></a>Descripción del esquema de búsqueda avanzada en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

El esquema de [búsqueda avanzada](advanced-hunting-overview.md) se compone de varias tablas que proporcionan información de eventos o información sobre dispositivos y otras entidades. Para crear consultas eficaces que abarquen varias tablas, debe comprender las tablas y las columnas del esquema de búsqueda avanzada.

## <a name="get-schema-information-in-the-defender-for-cloud"></a>Obtener información de esquema en Defender for Cloud

Al crear consultas, use la referencia de esquema integrada para obtener rápidamente la siguiente información sobre cada tabla del esquema:

- **Descripción de las tablas**: tipo de datos contenidos en la tabla y el origen de esos datos.
- **Columnas**: todas las columnas de la tabla.
- **Tipos de acción**: valores posibles en la `ActionType` columna que representan los tipos de eventos admitidos por la tabla. Estos valores solo se proporcionan para las tablas que contienen información de eventos.
- **Consulta de ejemplo**: consultas de ejemplo que incluyen cómo se puede usar la tabla.

### <a name="access-the-schema-reference"></a>Acceso a la referencia de esquema

Para acceder rápidamente a la referencia de esquema, seleccione la acción **Ver referencia** junto al nombre de la tabla en la representación del esquema. También puede seleccionar **Referencia de esquema** para buscar una tabla.

:::image type="content" source="images/ah-reference.png" alt-text="Página Búsqueda avanzada" lightbox="images/ah-reference.png":::

## <a name="learn-the-schema-tables"></a>Obtenga información sobre las tablas de esquema

En la referencia siguiente se enumeran todas las tablas del esquema de búsqueda avanzada. Cada nombre de tabla está vinculado a una página donde se describen los nombres de las columnas de esa tabla.

Los nombres de tabla y columna también se enumeran en el portal de Microsoft 365 Defender, en la representación de esquema en la pantalla de búsqueda avanzada.

<br>

****

|Nombre de tabla|Descripción|
|---|---|
|**[DeviceAlertEvents](advanced-hunting-devicealertevents-table.md)**|Alertas en Microsoft 365 Defender |
|**[DeviceInfo](advanced-hunting-deviceinfo-table.md)**|Información del dispositivo, incluida la información del sistema operativo|
|**[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)**|Propiedades de red de dispositivos, incluidos adaptadores, direcciones IP y MAC, así como redes y dominios conectados|
|**[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)**|Creación de procesos y eventos relacionados|
|**[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)**|Conexión de red y eventos relacionados|
|**[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)**|Creación y modificación de archivos y otros eventos del sistema de archivos|
|**[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)**|Creación y modificación de entradas de Registro|
|**[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)**|Inicios de sesión y otros eventos de autenticación|
|**[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)**|Eventos de carga de DLL|
|**[DeviceEvents](advanced-hunting-deviceevents-table.md)**|Varios tipos de eventos, incluidos los eventos desencadenados por controles de seguridad como Antivirus de Microsoft Defender y protección contra vulnerabilidades de seguridad|
|**[DeviceFileCertificateInfo](advanced-hunting-devicefilecertificateinfo-table.md)**|Información de certificados de archivos firmados obtenidos de los eventos de comprobación de certificados en puntos de conexión|
|**[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)**|Inventario del software instalado en dispositivos, incluida la información de la versión y el estado de finalización del soporte técnico|
|**[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)**|Vulnerabilidades de software encontradas en los dispositivos y lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad|
|**[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)**|La base de conocimiento de vulnerabilidades de la que se ha informado públicamente, incluyendo si el código que aprovecha la vulnerabilidad está disponible para el público|
|**[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)**|Administración de vulnerabilidades de Microsoft Defender eventos de evaluación, que indican el estado de varias configuraciones de seguridad en los dispositivos|
|**[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)**|Base de conocimiento de varias configuraciones de seguridad usadas por Defender Vulnerability Management para evaluar los dispositivos; incluye asignaciones a diversos estándares y pruebas comparativas|
|

> [!TIP]
> Use [la búsqueda avanzada en Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) para buscar amenazas mediante datos de Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Cloud Apps y Microsoft Defender for Identity. [Active Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).

Obtenga más información sobre cómo mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde).

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
- [Cambios en el esquema de datos de búsqueda avanzada](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/advanced-hunting-data-schema-changes/ba-p/1043914)
