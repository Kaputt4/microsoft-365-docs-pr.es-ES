---
title: Integración de Microsoft Defender para punto de conexión con otras soluciones de Microsoft
description: Obtenga información sobre cómo se integra Microsoft Defender para punto de conexión con otras soluciones de Microsoft, como Microsoft Defender for Identity y Microsoft Defender for Cloud.
author: mjcaparas
ms.author: macapara
ms.service: microsoft-365-security
keywords: microsoft 365 defender, acceso condicional, office, Microsoft Defender para punto de conexión, microsoft defender for identity, microsoft defender para office, Microsoft Defender for Cloud, Microsoft Cloud App Security, Azure Sentinel
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ae0ab05a353100ef5572ab4079bbf3eb6678041e
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68231668"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender para punto de conexión y otras soluciones de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integración con otras soluciones de Microsoft

Microsoft Defender para punto de conexión se integra directamente con varias soluciones de Microsoft.

### <a name="microsoft-defender-for-cloud"></a>Microsoft Defender for Cloud

Microsoft Defender for Cloud proporciona una solución de protección completa del servidor, incluidas las funcionalidades de detección y respuesta de puntos de conexión (EDR) en servidores Windows Server.

### <a name="microsoft-sentinel"></a>Microsoft Sentinel

El conector de Microsoft Defender para punto de conexión permite transmitir alertas desde Microsoft Defender para punto de conexión a Microsoft Sentinel. Esto le permitirá analizar de forma más completa los eventos de seguridad en toda la organización y crear cuadernos de estrategias para obtener una respuesta eficaz e inmediata.

### <a name="azure-information-protection"></a>Azure Information Protection

Recientemente hemos dejado de usar la integración de Azure Information Protection, ya que nuestras funcionalidades DLP de punto de conexión incorporan una solución mejorada de detección y protección para datos confidenciales almacenados en dispositivos de punto de conexión que facilita una mayor visibilidad e integración entre soluciones. Esto se anunció en el [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555) siguiente. Se recomienda que los clientes pasen a usar DLP de punto de conexión.

### <a name="conditional-access"></a>Acceso condicional

Microsoft Defender para punto de conexión la puntuación de riesgo de dispositivos dinámicos se integra en la evaluación de acceso condicional, lo que garantiza que solo los dispositivos seguros tengan acceso a los recursos.

### <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps aprovecha las señales de Microsoft Defender para punto de conexión para permitir la visibilidad directa del uso de aplicaciones en la nube, incluido el uso de servicios en la nube no admitidos (shadow IT) de todos Microsoft Defender para punto de conexión dispositivos supervisados.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity

Las actividades sospechosas son procesos que se ejecutan en un contexto de usuario. La integración entre Microsoft Defender para punto de conexión y Microsoft Defender for Identity proporciona la flexibilidad de realizar investigaciones de ciberseguridad entre actividades e identidades.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender para Office

[Defender para Office 365](/office365/securitycompliance/office-365-atp) ayuda a proteger su organización contra malware en mensajes de correo electrónico o archivos a través de vínculos seguros, datos adjuntos seguros, funcionalidades avanzadas de inteligencia contra suplantación de identidad y anti phishing. La integración entre Microsoft Defender para Office 365 y Microsoft Defender para punto de conexión permite a los analistas de seguridad ir hacia arriba para investigar el punto de entrada de un ataque. Mediante el uso compartido de inteligencia sobre amenazas, los ataques se pueden contener y bloquear.

> [!NOTE]
> Defender para Office 365 datos se muestran para eventos en los últimos 30 días. En el caso de las alertas, Defender para Office 365 datos se muestran en función de la primera hora de actividad. Después de eso, los datos ya no están disponibles en Defender para Office 365.

### <a name="skype-for-business"></a>Skype Empresarial

La integración Skype Empresarial proporciona una manera para que los analistas se comuniquen con un usuario o propietario de dispositivo potencialmente comprometido a través de un sencillo botón del portal.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender

Con Microsoft 365 Defender, Microsoft Defender para punto de conexión y varias soluciones de seguridad de Microsoft forman un conjunto de defensa empresarial unificado previo y posterior a la vulneración que se integra de forma nativa en los puntos de conexión, la identidad, el correo electrónico y las aplicaciones para detectar, prevenir, investigar y responder automáticamente a ataques sofisticados.

[Más información sobre Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

## <a name="related-topics"></a>Temas relacionados

- [Configuración de la integración y otras características avanzadas](advanced-features.md)
- [introducción a Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
- [Activar Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable)
- [Protección de usuarios, datos y dispositivos con acceso condicional](conditional-access.md)
