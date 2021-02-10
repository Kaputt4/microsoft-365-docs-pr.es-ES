---
title: Comprender la sección del informe de analistas en el análisis de amenazas
ms.reviewer: ''
description: Obtenga información sobre la sección de informes de analistas de cada informe de análisis de amenazas. Comprenda cómo proporciona información sobre amenazas, mitigaciones, detecciones, consultas de búsqueda avanzada y mucho más.
keywords: informe de analista, análisis de amenazas, detecciones, consultas de búsqueda avanzada, mitigaciones,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 650282e0dce49cc392eeb7501f91b3ffed9f0707
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167568"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Comprender el informe de analista en el análisis de amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

> ¿Desea experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio o](https://aka.ms/mtp-trial-lab) ejecutar el proyecto piloto en [producción.](https://aka.ms/m365d-pilotplaybook)
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Cada [informe de análisis de](threat-analytics.md) amenazas incluye secciones dinámicas y una sección completa escrita denominada informe de _analista._ Para obtener acceso a esta sección, abra el informe sobre la amenaza de seguimiento y seleccione la pestaña **Informe de** analistas.

![Imagen de la sección del informe de analista de un informe de análisis de amenazas](../../media/threat-analytics/ta_analystreport_mtp.png)

_Sección de informe de analista de un informe de análisis de amenazas_

## <a name="scan-the-analyst-report"></a>Examinar el informe de analista 
Cada sección del informe de analistas está diseñada para proporcionar información que puede actuar. Aunque los informes varían, la mayoría de los informes incluyen las secciones descritas en la tabla siguiente.

| Sección informe | Descripción |
|--|--|
| Resumen ejecutivo | Información general sobre la amenaza, incluida la primera vez que se vio, sus motivaciones, eventos notables, objetivos principales y distintas herramientas y técnicas. Puedes usar esta información para evaluar aún más cómo priorizar la amenaza en el contexto de tu sector, ubicación geográfica y red. |
| Análisis | Información técnica sobre las amenazas, incluidos los detalles de un ataque y cómo los atacantes pueden usar una nueva técnica o superficie de ataque | 
| Técnicas de&CK de MITRE ATT observadas | Cómo se asignan las técnicas observadas al marco de ataque [de MITRE ATT&CK](https://attack.mitre.org/) | 
| [Mitigaciones](#apply-additional-mitigations) | Recomendaciones que pueden detener o ayudar a reducir el impacto de la amenaza. Esta sección también incluye mitigaciones que no se realiza un seguimiento dinámico como parte del informe de análisis de amenazas. |
| [Detalles de la detección](#understand-how-each-threat-can-be-detected) | Detecciones específicas y genéricas proporcionadas por soluciones de seguridad de Microsoft que pueden detectar actividad o componentes asociados con la amenaza. | 
| [Búsqueda avanzada](#find-subtle-threat-artifacts-using-advanced-hunting) | [Consultas de búsqueda avanzada para](advanced-hunting-overview.md) identificar proactivamente posibles actividades de amenazas. La mayoría de las consultas se proporcionan para complementar las detecciones, especialmente para buscar componentes o comportamientos potencialmente malintencionados que no se pudieron evaluar dinámicamente como malintencionados. | 
| Referencias | Publicaciones de Microsoft y de terceros a las que hacen referencia los analistas durante la creación del informe. El contenido del análisis de amenazas se basa en datos validados por investigadores de Microsoft. La información de fuentes de terceros disponibles públicamente se identifica claramente como tal. | 
| Registro de cambios | La hora en que se publicó el informe y cuándo se realizaron cambios significativos en el informe. |

## <a name="apply-additional-mitigations"></a>Aplicar mitigaciones adicionales
El análisis de amenazas realiza un seguimiento dinámico [del estado de las actualizaciones de seguridad y las configuraciones seguras.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Esta información está disponible como gráficos y tablas en la **pestaña Mitigaciones.**

Además de estas mitigaciones de seguimiento, el informe del analista también analiza las mitigaciones que no _se_ supervisan dinámicamente. Estos son algunos ejemplos de mitigaciones importantes a las que no se realiza un seguimiento dinámico:

- Bloquear correos electrónicos con _datos adjuntos .lnk_ u otros tipos de archivo sospechosos
- Aleatorizar contraseñas de administrador local
- Instruir a los usuarios finales sobre el correo electrónico de suplantación de identidad (phishing) y otros vectores de amenazas
- Activar reglas específicas de [reducción de superficie de ataque](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Aunque puedes usar la pestaña **Mitigaciones** para evaluar tu posición de seguridad frente a una amenaza, estas recomendaciones te permiten realizar pasos adicionales para mejorar tu posición de seguridad. Lee detenidamente todas las instrucciones de mitigación del informe de analista y aplíclílas siempre que sea posible.

## <a name="understand-how-each-threat-can-be-detected"></a>Comprender cómo se puede detectar cada amenaza
El informe del analista también proporciona las detecciones de Microsoft Defender para las capacidades de detección y respuesta _de_ puntos de conexión (EDR) y antivirus de puntos de conexión.

### <a name="antivirus-detections"></a>Detecciones de antivirus
Estas detecciones están disponibles en dispositivos con [antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) activado. Cuando estas detecciones se producen en dispositivos que se han incorporado a Microsoft Defender para Endpoint, también desencadenan alertas que iluminan los gráficos del informe.

>[!NOTE]
>El informe del analista también enumera detecciones **genéricas** que pueden identificar una amplia gama de amenazas, además de componentes o comportamientos específicos de la amenaza rastreada. Estas detecciones genéricas no se reflejan en los gráficos.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Alertas de detección y respuesta de puntos de conexión (EDR)
Se genera alertas de EDR para dispositivos [incorporados a Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure) Por lo general, estas alertas dependen de las señales de seguridad recopiladas por el sensor de Microsoft Defender para puntos de conexión y otras funcionalidades de puntos de conexión (como antivirus, protección de red, protección contra alteraciones) que sirven como potentes orígenes de señal.

Al igual que la lista de detecciones antivirus, algunas alertas de EDR están diseñadas para marcar de forma genérica el comportamiento sospechoso que podría no estar asociado con la amenaza de seguimiento. En tales casos, el informe identificará claramente la alerta como "genérica" y no influirá en ninguno de los gráficos del informe.

### <a name="email-related-detections-and-mitigations"></a>Detecciones y mitigaciones relacionadas con el correo electrónico
Las detecciones y mitigaciones relacionadas con el correo electrónico de Microsoft Defender para Office 365 se incluyen en informes de analistas además de los datos de puntos de conexión ya disponibles en Microsoft Defender para Endpoint. 

La información de intentos de correo electrónico impedido proporciona información sobre si su organización era el objetivo de la amenaza que se abordó en el informe de analista, incluso si el ataque se bloqueó efectivamente antes de la entrega o se entregó a la carpeta de correo no deseado.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Buscar artefactos de amenazas sutiles mediante la búsqueda avanzada
Aunque las detecciones te permiten identificar y detener la amenaza de seguimiento automáticamente, muchas actividades de ataque dejan seguimientos sutiles que requieren una inspección adicional. Algunas actividades de ataque presentan comportamientos que también pueden ser normales, por lo que detectarlas dinámicamente puede provocar ruido operativo o incluso falsos positivos.

[La búsqueda avanzada](advanced-hunting-overview.md) proporciona una interfaz de consulta basada en el lenguaje de consulta Kusto que simplifica la búsqueda de indicadores sutiles de la actividad de amenazas. También te permite ver información contextual y comprobar si los indicadores están conectados a una amenaza.

Los analistas de Microsoft han visto las consultas de búsqueda avanzada en los informes de analistas y están listas para ejecutarse en el editor de consultas [de búsqueda avanzada.](https://security.microsoft.com/advanced-hunting) También puedes usar las consultas para crear reglas de [detección](custom-detection-rules.md) personalizadas que desencadene alertas para futuras coincidencias.


>[!NOTE]
> El análisis de amenazas también está disponible [en Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) Sin embargo, no tiene la integración de datos entre Microsoft Defender para Office y Microsoft Defender para Endpoint que tiene el análisis de amenazas de Microsoft 365 Defender.


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre el Análisis de amenazas](threat-analytics.md)
- [Búsqueda proactiva de amenazas con búsqueda avanzada](advanced-hunting-overview.md) 
- [Reglas de detección personalizadas](custom-detection-rules.md)
