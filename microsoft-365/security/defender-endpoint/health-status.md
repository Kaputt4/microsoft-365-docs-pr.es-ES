---
title: Investigar problemas de estado de agente
description: Obtenga información sobre los valores devueltos al ejecutar el comando de mantenimiento mdatp
keywords: estado de mdatp, comando, estado, estado, comando, estado de incorporación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acc75a931cb14a7aab729c09a7b835fb9f26d1d1
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281305"
---
# <a name="investigate-agent-health-issues"></a>Investigar problemas de estado de agente

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


En la tabla siguiente se proporciona información sobre los valores devueltos al ejecutar el `mdatp health` comando y sus correspondientes descripciones.

| Valor | Descripción |
|-|-|
| automatic_definition_update_enabled | True si las actualizaciones automáticas de definiciones de antivirus están habilitadas, false de lo contrario. |
|  cloud_automatic_sample_submission_consent | Nivel de envío de ejemplo actual. Puede ser uno de los siguientes valores:     <br><br>  - **Ninguno:** no se envían muestras sospechosas a Microsoft.  <br> <br>     - **Caja fuerte:** solo se envían automáticamente muestras sospechosas que no contienen información de identificación personal (PII). Este es el valor predeterminado para esta configuración.    <br> <br>   - **All**: Todas las muestras sospechosas se envían a Microsoft.   |
| cloud_diagnostic_enabled | True si la recopilación de datos de diagnóstico opcional está habilitada, false en caso contrario. Para obtener más información relacionada con Defender para Endpoint y otros productos y servicios como Antivirus de Microsoft Defender y Windows 10, vea [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=827576). |
| cloud_enabled | True si la protección entregada en la nube está habilitada, false de lo contrario. |
| conflicting_applications | Lista de aplicaciones que posiblemente entren en conflicto con Microsoft Defender para endpoint. Esta lista incluye, entre otros, otros productos de seguridad y otras aplicaciones conocidas por causar problemas de compatibilidad. |
| definitions_status | Estado de las definiciones de antivirus. |
| definitions_updated | Fecha y hora de la última actualización de definición del antivirus. |
| definitions_updated_minutes_ago | Número de minutos desde la última actualización de definición del antivirus. |
| definitions_version | Versión de definición de antivirus. |
| edr_client_version | Versión del cliente EDR que se ejecuta en el dispositivo. |
| edr_configuration_version | EDR de configuración. |
| edr_device_tags | Lista de etiquetas asociadas con el dispositivo. |
| edr_group_ids | Id. de grupo al que está asociado el dispositivo. |
| edr_machine_id | Identificador de dispositivo usado en Centro de seguridad de Microsoft Defender. |
| engine_version | Versión del motor antivirus. |
| healthy | True si el producto está en buen estado, false de lo contrario. |
| licencia | True si el dispositivo está incorporado a un inquilino, false de lo contrario. |
| log_level | Nivel de registro actual del producto. |
| machine_guid | Identificador de máquina único usado por el componente antivirus. |
| network_protection_status                 | Estado del componente de protección de red (solo macOS). Puede ser uno de los siguientes valores:       <br> <br>- **inicio:** se inicia la protección de red  <br> <br>     - **failed_to_start:** no se pudo iniciar la protección de red debido a un error   <br> <br>    - **iniciado:** la protección de red se está ejecutando actualmente en el dispositivo     <br> <br>  - **reinicio:** la protección de red se está reiniciando actualmente   <br> <br>    - **detención:** se detiene la protección de red     <br> <br>  - **detenido:** la protección de red no se está ejecutando |
| org_id | Organización a la que está incorporado el dispositivo. Si el dispositivo aún no está incorporado a ninguna organización, esta impresión no estará disponible. Para obtener más información sobre la incorporación, vea [Onboard to Microsoft Defender for Endpoint](onboarding.md). |
| passive_mode_enabled | True si el componente antivirus está configurado para ejecutarse en modo pasivo, false de lo contrario. |
| product_expiration | Fecha y hora en que la versión actual del producto llega al final de la compatibilidad. |
| real_time_protection_available | True si el componente de protección en tiempo real está en buen estado, false de lo contrario. |
| real_time_protection_enabled | True si la protección antivirus en tiempo real está habilitada, false de lo contrario. |
| real_time_protection_subsystem | Subsistema usado para servir protección en tiempo real. Si la protección en tiempo real no funciona como se esperaba, esta impresión no estará disponible. |
| release_ring | Anillo de liberación. Para obtener más información, vea   [Anillos de implementación](deployment-rings.md). |