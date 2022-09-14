---
title: Descripción de la sección de informe de analistas en análisis de amenazas.
ms.reviewer: ''
description: Cómo la sección de informes de informes de análisis de amenazas proporciona información sobre amenazas, mitigación, detecciones, consultas de búsqueda avanzadas, etc.
keywords: informe de analistas, análisis de amenazas, detecciones, consultas de búsqueda avanzadas, mitigaciones,
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 1d47b966ccce5a22a2d61f18353cefa77c7a58c3
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67689303"
---
# <a name="the-analyst-report-in-threat-analytics"></a>Informe de analistas en análisis de amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cada [informe de análisis de amenazas](threat-analytics.md) incluye secciones dinámicas y una sección completa escrita denominada _informe de analistas_. Para acceder a esta sección, abra el informe sobre la amenaza de la que se ha seguido y seleccione la pestaña **Informe de analista** .

:::image type="content" source="images/ta-analyst-report-small.png" alt-text="Sección de informe de analistas de un informe de análisis de amenazas" lightbox="images/ta-analyst-report-small.png":::

_Sección de informe de analistas de un informe de análisis de amenazas_

## <a name="scan-the-analyst-report"></a>Examinar el informe del analista

Cada sección del informe de analistas está diseñada para proporcionar información accionable. Aunque los informes varían, la mayoría de los informes incluyen las secciones descritas en la tabla siguiente.

<br>

****

|Sección informe|Descripción|
|---|---|
|Resumen ejecutivo|Introducción a la amenaza, incluida la primera vez que se vio, sus motivaciones, eventos notables, objetivos principales y herramientas y técnicas distintas. Puede usar esta información para evaluar aún más cómo priorizar la amenaza en el contexto del sector, la ubicación geográfica y la red.|
|Análisis|Información técnica sobre las amenazas, incluidos los detalles de un ataque y cómo los atacantes pueden usar una nueva técnica o superficie de ataque|
|Técnicas de MITRE ATT&CK observadas|Cómo se asignan las técnicas observadas al [marco de ataque de MITRE ATT&CK](https://attack.mitre.org/)|
|[Mitigaciones](#apply-additional-mitigations)|Recomendaciones que pueden detener o ayudar a reducir el impacto de la amenaza. Esta sección también incluye mitigaciones que no se realizan un seguimiento dinámico como parte del informe de análisis de amenazas.|
|[Detalles de detección](#understand-how-each-threat-can-be-detected)|Detecciones específicas y genéricas proporcionadas por soluciones de seguridad de Microsoft que pueden exponer la actividad o los componentes asociados a la amenaza.|
|[Búsqueda avanzada de amenazas](#find-subtle-threat-artifacts-using-advanced-hunting)|[Consultas de búsqueda avanzadas](advanced-hunting-overview.md) para identificar proactivamente la posible actividad de amenazas. La mayoría de las consultas se proporcionan para complementar las detecciones, especialmente para localizar componentes potencialmente malintencionados o comportamientos que no se pudieron evaluar dinámicamente como malintencionados.|
|Referencias|Publicaciones de Microsoft y de terceros a las que hacen referencia los analistas durante la creación del informe. El contenido de análisis de amenazas se basa en los datos validados por los investigadores de Microsoft. La información de fuentes de terceros disponibles públicamente se identifica claramente como tal.|
|Registro de cambios|El momento en que se publicó el informe y cuándo se realizaron cambios significativos en el informe.|
|

## <a name="apply-additional-mitigations"></a>Aplicación de mitigaciones adicionales

Análisis de amenazas realiza un seguimiento dinámico del [estado de las actualizaciones de seguridad y las configuraciones seguras](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices). Esta información está disponible como gráficos y tablas en la pestaña **Mitigaciones** .

Además de estas mitigaciones de seguimiento, el informe del analista también describe las mitigaciones que _no_ se supervisan dinámicamente. Estos son algunos ejemplos de mitigaciones importantes de las que no se realiza un seguimiento dinámico:

- Bloquear correos electrónicos con datos adjuntos _.lnk_ u otros tipos de archivos sospechosos
- Aleatorización de contraseñas de administrador local
- Educar a los usuarios finales sobre el correo electrónico de suplantación de identidad (phishing) y otros vectores de amenazas
- Activar reglas específicas de [reducción de superficie expuesta a ataques](attack-surface-reduction.md)

Aunque puede usar la pestaña **Mitigaciones** para evaluar la posición de seguridad frente a una amenaza, estas recomendaciones le permiten realizar pasos adicionales para mejorar su posición de seguridad. Lea detenidamente todas las instrucciones de mitigación del informe del analista y aplíquelas siempre que sea posible.

## <a name="understand-how-each-threat-can-be-detected"></a>Comprender cómo se puede detectar cada amenaza

El informe de analistas también proporciona las detecciones del Antivirus de Microsoft Defender y las funcionalidades _de detección y respuesta de puntos de conexión_ (EDR).

### <a name="antivirus-detections"></a>Detecciones antivirus

Estas detecciones están disponibles en dispositivos con [antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) activado. Cuando estas detecciones se producen en dispositivos que se han incorporado a Microsoft Defender para punto de conexión, también desencadenan alertas que iluminan los gráficos del informe.

> [!NOTE]
> El informe de analistas también enumera **detecciones genéricas** que pueden identificar una amplia gama de amenazas, además de componentes o comportamientos específicos de la amenaza de seguimiento. Estas detecciones genéricas no se reflejan en los gráficos.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Alertas de detección y respuesta de puntos de conexión (EDR)

Se generan alertas de EDR para [los dispositivos incorporados a Microsoft Defender para punto de conexión](onboard-configure.md). Por lo general, estas alertas se basan en las señales de seguridad recopiladas por el sensor de Microsoft Defender para punto de conexión y otras funcionalidades de punto de conexión (como antivirus, protección de red, protección contra alteraciones) que sirven como fuentes de señal eficaces.

Al igual que la lista de detecciones de antivirus, algunas alertas de EDR están diseñadas para marcar genéricamente el comportamiento sospechoso que podría no estar asociado a la amenaza de seguimiento. En tales casos, el informe identificará claramente la alerta como "genérica" y que no influye en ninguno de los gráficos del informe.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Búsqueda de artefactos de amenazas sutiles mediante la búsqueda avanzada

Aunque las detecciones le permiten identificar y detener la amenaza rastreada automáticamente, muchas actividades de ataque dejan seguimientos sutiles que requieren inspección adicional. Algunas actividades de ataque muestran comportamientos que también pueden ser normales, por lo que detectarlas dinámicamente puede dar lugar a ruido operativo o incluso falsos positivos.

[La búsqueda avanzada](advanced-hunting-overview.md) proporciona una interfaz de consulta basada en Lenguaje de consulta Kusto que simplifica la localización de indicadores sutiles de actividad de amenazas. También permite exponer información contextual y comprobar si los indicadores están conectados a una amenaza.

Los analistas de Microsoft han examinado las consultas de búsqueda avanzada en los informes de analistas y están listas para ejecutarse en el [editor de consultas de búsqueda avanzada](https://security.microsoft.com/advanced-hunting). También puede usar las consultas para crear [reglas de detección personalizadas](custom-detection-rules.md) que desencadenen alertas para futuras coincidencias.

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre el Análisis de amenazas](threat-analytics.md)
- [Búsqueda proactiva de amenazas con la búsqueda avanzada](advanced-hunting-overview.md)
- [Reglas de detección personalizada](custom-detection-rules.md)
