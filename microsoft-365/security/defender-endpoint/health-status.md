---
title: Investigar problemas de estado del agente
description: Obtenga información sobre los valores devueltos al ejecutar el comando de mantenimiento mdatp.
keywords: estado de mdatp, comando, estado, estado, comando, estado de incorporación
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 0ff6d8074131e1595ee651c40e59a0b9b03eb063
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67692605"
---
# <a name="investigate-agent-health-issues"></a>Investigar problemas de estado del agente

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En la tabla siguiente se proporciona información sobre los valores devueltos al ejecutar el `mdatp health` comando y sus descripciones correspondientes.

<br>

****

|Valor|Descripción|
|---|---|
|automatic_definition_update_enabled|True si las actualizaciones automáticas de definiciones de antivirus están habilitadas, false en caso contrario.|
|cloud_automatic_sample_submission_consent|Nivel de envío de ejemplo actual. Puede ser uno de los siguientes valores: <ul><li>**Ninguno**: no se envían muestras sospechosas a Microsoft.</li><li>**Seguro**: solo se envían automáticamente muestras sospechosas que no contienen información de identificación personal (PII). Este es el valor predeterminado para esta configuración.</li><li>**Todos**: todos los ejemplos sospechosos se envían a Microsoft.</li></ul>|
|cloud_diagnostic_enabled|True si la recopilación de datos de diagnóstico opcional está habilitada, false en caso contrario. Para obtener más información relacionada con Defender para punto de conexión y otros productos y servicios como Antivirus de Microsoft Defender y Windows, consulte [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=827576).|
|cloud_enabled|True si la protección entregada en la nube está habilitada, en caso contrario, false.|
|conflicting_applications|Lista de aplicaciones que posiblemente entren en conflicto con Microsoft Defender para punto de conexión. Esta lista incluye, pero no se limita a, otros productos de seguridad y otras aplicaciones conocidas por causar problemas de compatibilidad.|
|definitions_status|Estado de las definiciones de antivirus.|
|definitions_updated|Fecha y hora de la última actualización de definición de antivirus.|
|definitions_updated_minutes_ago|Número de minutos desde la última actualización de definición de antivirus.|
|definitions_version|Versión de definición del antivirus.|
|edr_client_version|Versión del cliente EDR que se ejecuta en el dispositivo.|
|edr_configuration_version|Versión de configuración de EDR.|
|edr_device_tags|Lista de etiquetas asociadas al dispositivo.|
|edr_group_ids|Identificador de grupo al que está asociado el dispositivo.|
|edr_machine_id|Identificador de dispositivo usado en Microsoft 365 Defender.|
|engine_version|Versión del motor antivirus.|
|Sano|True si el producto está en buen estado, false en caso contrario.|
|Licencia|True si el dispositivo está incorporado a un inquilino, false en caso contrario.|
|log_level|Nivel de registro actual del producto.|
|machine_guid|Identificador de máquina único usado por el componente antivirus.|
|network_protection_status|Estado del componente de protección de red (solo macOS). Puede ser uno de los siguientes valores: <ul><li>**starting** : se está iniciando la protección de red.</li><li>**failed_to_start** : no se pudo iniciar la protección de red debido a un error</li><li>**iniciado** : la protección de red se está ejecutando actualmente en el dispositivo</li><li>**reinicio** : la protección de red se está reiniciando actualmente</li><li>**detención** : la protección de red se está deteniendo</li><li>**detenido** : la protección de red no se está ejecutando</li></ul>|
|org_id|Organización a la que se incorpora el dispositivo. Si el dispositivo aún no está incorporado a ninguna organización, esta impresión no estará disponible. Para obtener más información sobre la incorporación, consulte [Incorporación a Microsoft Defender para punto de conexión](onboarding.md).|
|passive_mode_enabled|True si el componente antivirus está establecido para ejecutarse en modo pasivo, en caso contrario, false.|
|product_expiration|Fecha y hora en que la versión actual del producto llega al final del soporte técnico.|
|real_time_protection_available|True si el componente de protección en tiempo real es correcto, false en caso contrario.|
|real_time_protection_enabled|True si la protección antivirus en tiempo real está habilitada, false en caso contrario.|
|real_time_protection_subsystem|Subsistema que se usa para proporcionar protección en tiempo real. Si la protección en tiempo real no funciona según lo esperado, esta impresión no estará disponible.|
|release_ring|Anillo de liberación. Para obtener más información, consulte [Anillos de implementación](deployment-rings.md).|
|
