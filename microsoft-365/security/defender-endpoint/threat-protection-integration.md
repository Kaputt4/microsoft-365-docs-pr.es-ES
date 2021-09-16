---
title: Integrar Microsoft Defender para endpoint con otras soluciones de Microsoft
description: Obtenga información sobre cómo Microsoft Defender para Endpoint se integra con otras soluciones de Microsoft, como Microsoft Defender para Identity y Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, acceso condicional, office, Microsoft Defender para endpoint, microsoft defender para la identidad, microsoft defender para office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8f842c46f87e51d026f1e1793e3cc73d25b0739c
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2021
ms.locfileid: "59400647"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender para endpoint y otras soluciones de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integrar con otras soluciones de Microsoft

Microsoft Defender para endpoint se integra directamente con varias soluciones de Microsoft.

### <a name="azure-defender"></a>Azure Defender

Microsoft Defender para endpoint proporciona una solución completa de protección de servidores, que incluye detección y respuesta de puntos de conexión (EDR) en Windows servidores.

### <a name="azure-sentinel"></a>Azure Sentinel

El conector de Microsoft Defender para puntos de conexión te permite transmitir alertas de Microsoft Defender para endpoint en Azure Sentinel. Esto te permitirá analizar más exhaustivamente los eventos de seguridad en toda la organización y crear libros de juegos para obtener una respuesta eficaz e inmediata.

### <a name="azure-information-protection"></a>Azure Information Protection

Recientemente hemos dejado de usar la integración de Azure Information Protection, ya que nuestras capacidades DLP de punto de conexión incorporan una solución mejorada de detección y protección para datos confidenciales almacenados en dispositivos de punto de conexión que facilita una mayor visibilidad e integración entre soluciones. Esto se anunció en el [siguiente blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555). Se recomienda que los clientes pasen a usar DLP de extremo.

### <a name="conditional-access"></a>Acceso condicional

La puntuación de riesgo de dispositivo dinámico de Microsoft Defender para endpoint está integrada en la evaluación de acceso condicional, lo que garantiza que solo los dispositivos seguros tengan acceso a los recursos.

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Microsoft Cloud App Security aprovecha las señales de Microsoft Defender para endpoints para permitir la visibilidad directa del uso de aplicaciones en la nube, incluido el uso de servicios en la nube no compatibles (TI de instantánea) de todos los dispositivos supervisados por Microsoft Defender para puntos de conexión.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity

Las actividades sospechosas son procesos que se ejecutan en un contexto de usuario. La integración entre Microsoft Defender para Endpoint y Microsoft Defender for Identity proporciona la flexibilidad de realizar investigaciones de ciberseguridad entre actividades e identidades.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender para Office

[Defender for Office 365](/office365/securitycompliance/office-365-atp) ayuda a proteger su organización contra malware en mensajes de correo electrónico o archivos a través de vínculos de Caja fuerte, datos adjuntos de Caja fuerte, capacidades avanzadas de inteligencia anti phishing y suplantación de identidad. La integración entre Microsoft Defender para Office 365 y Microsoft Defender para endpoint permite a los analistas de seguridad ir hacia arriba para investigar el punto de entrada de un ataque. A través del uso compartido de inteligencia de amenazas, los ataques pueden contenerse y bloquearse.

> [!NOTE]
> Defender para Office 365 se muestra para eventos en los últimos 30 días. Para las alertas, Defender para Office 365 datos se muestra en función de la primera hora de actividad. Después de eso, los datos ya no están disponibles en Defender para Office 365.

### <a name="skype-for-business"></a>Skype Empresarial

La Skype Empresarial permite a los analistas comunicarse con un usuario o propietario de dispositivo potencialmente comprometido a través de un botón sencillo del portal.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender

Con Microsoft 365 Defender, Microsoft Defender para endpoint y varias soluciones de seguridad de Microsoft forman un conjunto de aplicaciones de defensa empresarial unificado previo y posterior a la infracción que se integra de forma nativa en puntos de conexión, identidad, correo electrónico y aplicaciones para detectar, prevenir, investigar y responder automáticamente a ataques sofisticados.

[Obtenga más información sobre Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)

## <a name="related-topics"></a>Temas relacionados

- [Configurar la integración y otras características avanzadas](advanced-features.md)
- [Microsoft 365 Defender introducción](/microsoft-365/security/defender/microsoft-threat-protection)
- [Activar Microsoft 365 Defender](/microsoft-365/security/defender/mtp-enable)
- [Proteger usuarios, datos y dispositivos con acceso condicional](conditional-access.md)
