---
title: Buscar dispositivos expuestos
description: Obtenga información Administración de amenazas y vulnerabilidades puede usarse para ayudar a los administradores de seguridad, los administradores de TI y SecOps a colaborar.
keywords: Escenarios de Microsoft Defender para Endpoint-tvm, Microsoft Defender para endpoint, tvm, escenarios de tvm, reducir la exposición & vulnerabilidad & amenazas, reducir la amenaza y vulnerabilidad, mejorar la configuración de seguridad, aumentar la puntuación segura de Microsoft para dispositivos, aumentar la vulnerabilidad & Microsoft Secure Score para dispositivos, Puntuación segura de Microsoft para dispositivos, puntuación de exposición, controles de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934098"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a>Buscar dispositivos expuestos: Administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Amenaza y administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a>Usar la búsqueda avanzada para buscar dispositivos con vulnerabilidades

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar de forma proactiva los eventos de la red para localizar indicadores y entidades de amenazas. El acceso flexible a los datos permite la búsqueda sin restricciones para amenazas conocidas y potenciales. [Más información sobre la búsqueda avanzada](advanced-hunting-overview.md)

### <a name="schema-tables"></a>Tablas del esquema

- [DeviceTvmSoftwareInventory:](advanced-hunting-devicetvmsoftwareinventory-table.md) inventario de software instalado en dispositivos, incluida la información de su versión y el estado de finalización del soporte técnico.

- [DeviceTvmSoftwareVulnerabilities:](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) vulnerabilidades de software encontradas en dispositivos y la lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad.

- [DeviceTvmSoftwareVulnerabilitiesKB:](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) base de conocimiento de las vulnerabilidades divulgadas públicamente, incluido si el código de vulnerabilidad está disponible públicamente.

- [DeviceTvmSecureConfigurationAssessment:](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) eventos de evaluación de amenazas y administración de vulnerabilidades, que indican el estado de varias configuraciones de seguridad en dispositivos.

- [DeviceTvmSecureConfigurationAssessmentKB:](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) base de conocimientos de varias configuraciones de seguridad usadas por threat & Vulnerability Management para evaluar los dispositivos; incluye asignaciones a diversos estándares y puntos de referencia

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a>Comprobar qué dispositivos están implicados en alertas de alta gravedad

1. Vaya a **Búsqueda avanzada desde** el panel de navegación izquierdo de la Centro de seguridad de Microsoft Defender.

2. Desplácese hacia abajo hasta los esquemas de búsqueda avanzados de TVM para familiarizarse con los nombres de columna.

3. Escriba las siguientes consultas:

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre amenazas administración de vulnerabilidades amenazas](next-gen-threat-and-vuln-mgt.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [API](next-gen-threat-and-vuln-mgt.md#apis)
- [Configurar el acceso a datos para Administración de amenazas y vulnerabilidades roles](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [Información general sobre la búsqueda avanzada de amenazas](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Todas las tablas de búsqueda avanzadas](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
