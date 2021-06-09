---
title: Comprender la sección de informe de analistas en análisis de amenazas
ms.reviewer: ''
description: Obtenga información sobre la sección de informe de analistas de cada informe de análisis de amenazas. Comprenda cómo proporciona información sobre amenazas, mitigaciones, detecciones, consultas avanzadas de búsqueda y mucho más.
keywords: informe de analistas, análisis de amenazas, detecciones, consultas avanzadas de búsqueda, mitigaciones,
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
ms.technology: mde
ms.openlocfilehash: 2a442a642a71bd6bf3a52dbf3901c4367c2c10d8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844999"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Comprender el informe de analistas en análisis de amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cada [informe de análisis de](threat-analytics.md) amenazas incluye secciones dinámicas y una sección escrita completa denominada informe de _analista._ Para obtener acceso a esta sección, abra el informe sobre la amenaza rastreada y seleccione la **pestaña Informe de** analista.

![Imagen de la sección de informe de analista de un informe de análisis de amenazas](images/ta-analyst-report-small.png)

_Sección de informe de analista de un informe de análisis de amenazas_

## <a name="scan-the-analyst-report"></a>Examinar el informe de analistas 
Cada sección del informe de analista está diseñada para proporcionar información que se puede usar. Aunque los informes varían, la mayoría de los informes incluyen las secciones descritas en la tabla siguiente.

| Sección Informe | Descripción |
|--|--|
| Resumen ejecutivo | Información general sobre la amenaza, incluso cuando se vio por primera vez, sus motivaciones, eventos notables, objetivos principales y distintas herramientas y técnicas. Puede usar esta información para evaluar aún más cómo priorizar la amenaza en el contexto de su industria, ubicación geográfica y red. |
| Análisis | Información técnica sobre las amenazas, incluidos los detalles de un ataque y cómo los atacantes pueden usar una nueva técnica o superficie de ataque | 
| MITRE ATT&técnicas de CK observadas | Cómo se asignan las técnicas observadas al marco de ataque [&MITRE ATT](https://attack.mitre.org/) | 
| [Mitigaciones](#apply-additional-mitigations) | Recomendaciones que pueden detener o ayudar a reducir el impacto de la amenaza. Esta sección también incluye mitigaciones que no se realiza un seguimiento dinámico como parte del informe de análisis de amenazas. |
| [Detalles de detección](#understand-how-each-threat-can-be-detected) | Detecciones específicas y genéricas proporcionadas por soluciones de seguridad de Microsoft que pueden crear actividad o componentes asociados con la amenaza. | 
| [Búsqueda avanzada de amenazas](#find-subtle-threat-artifacts-using-advanced-hunting) | [Consultas avanzadas de búsqueda para](advanced-hunting-overview.md) identificar proactivamente posibles actividades de amenazas. La mayoría de las consultas se proporcionan para complementar las detecciones, especialmente para localizar componentes o comportamientos potencialmente malintencionados que no se pudieron evaluar dinámicamente como malintencionados. | 
| Referencias | Publicaciones de Microsoft y de terceros a las que hacen referencia los analistas durante la creación del informe. El contenido de análisis de amenazas se basa en datos validados por investigadores de Microsoft. La información de fuentes de terceros disponibles públicamente se identifica claramente como tal. | 
| Registro de cambios | La hora en que se publicó el informe y cuándo se realizaron cambios significativos en el informe. |

## <a name="apply-additional-mitigations"></a>Aplicar mitigaciones adicionales
El análisis de amenazas realiza un seguimiento dinámico [del estado de las actualizaciones de seguridad y las configuraciones seguras.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Esta información está disponible como gráficos y tablas en la **pestaña Mitigaciones.**

Además de estas mitigaciones rastreadas, el informe del analista también analiza mitigaciones que no _se_ supervisan dinámicamente. Estos son algunos ejemplos de mitigaciones importantes a las que no se realiza un seguimiento dinámico:

- Bloquear correos electrónicos _con datos adjuntos .lnk_ u otros tipos de archivo sospechosos
- Aleatorizar contraseñas de administrador local
- Educar a los usuarios finales sobre el correo electrónico de suplantación de identidad (phishing) y otros vectores de amenazas
- Activar reglas de [reducción de superficie de ataque específicas](attack-surface-reduction.md)

Aunque puedes usar la pestaña Mitigaciones para evaluar la posición de seguridad frente a una amenaza, estas recomendaciones te permiten tomar **medidas** adicionales para mejorar la posición de seguridad. Lea atentamente todas las instrucciones de mitigación del informe del analista y apliquenlas siempre que sea posible.

## <a name="understand-how-each-threat-can-be-detected"></a>Comprender cómo se puede detectar cada amenaza
El informe del analista también proporciona las detecciones de Microsoft Defender para antivirus de extremo _y_ detección y respuesta de puntos de conexión (EDR).

### <a name="antivirus-detections"></a>Detecciones de antivirus
Estas detecciones están disponibles en dispositivos [con Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) activado. Cuando estas detecciones se producen en dispositivos que se han incorporado a Microsoft Defender para Endpoint, también desencadenan alertas que encienden los gráficos del informe.

>[!NOTE]
>El informe del analista también enumera detecciones **genéricas** que pueden identificar una amplia gama de amenazas, además de componentes o comportamientos específicos de la amenaza rastreada. Estas detecciones genéricas no se reflejan en los gráficos.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Alertas de detección y respuesta de puntos de conexión (EDR)
EDR alertas se genera para dispositivos [incorporados a Microsoft Defender para endpoint](onboard-configure.md). Por lo general, estas alertas se basan en las señales de seguridad recopiladas por el sensor de Microsoft Defender para endpoints y otras capacidades de punto de conexión (como antivirus, protección de red, protección contra alteraciones) que sirven como orígenes de señales eficaces.

Al igual que la lista de detecciones de antivirus, algunas alertas de EDR están diseñadas para marcar de forma genérica comportamientos sospechosos que podrían no estar asociados con la amenaza rastreada. En tales casos, el informe identificará claramente la alerta como "genérica" y que no influye en ninguno de los gráficos del informe.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Buscar artefactos de amenazas sutiles mediante la búsqueda avanzada
Aunque las detecciones permiten identificar y detener automáticamente la amenaza rastreada, muchas actividades de ataque dejan seguimientos sutiles que requieren inspección adicional. Algunas actividades de ataque muestran comportamientos que también pueden ser normales, por lo que detectarlos dinámicamente puede provocar ruido operativo o incluso falsos positivos.

[La búsqueda avanzada](advanced-hunting-overview.md) proporciona una interfaz de consulta basada en kusto Query Language que simplifica la localización de indicadores sutiles de actividad de amenazas. También te permite obtener información contextual y comprobar si los indicadores están conectados a una amenaza.

Los analistas de Microsoft han consultado consultas avanzadas de búsqueda en los informes de analistas y están listas para ejecutarse en el editor de consultas [de búsqueda avanzada.](https://securitycenter.windows.com/advanced-hunting) También puede usar las consultas para crear reglas de [detección personalizadas](custom-detection-rules.md) que desencadene alertas para futuras coincidencias.


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre el Análisis de amenazas](threat-analytics.md)
- [Búsqueda proactiva de amenazas con búsqueda avanzada](advanced-hunting-overview.md) 
- [Reglas de detección personalizada](custom-detection-rules.md)