---
title: Implementar la protección de la información para las regulaciones de privacidad de datos con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: ''
description: Configure la infraestructura de seguridad y servicio para proteger su información y cumplir con las regulaciones de privacidad de datos.
ms.openlocfilehash: 640ce075515c687c037cb0e4ab3e03e3beda81dc
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522294"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Implementar la protección de la información para las regulaciones de privacidad de datos con Microsoft 365

Su organización puede estar sujeta a regulaciones de privacidad de datos regionales que le obligan a proteger, administrar y proporcionar derechos y control sobre la información personal almacenada en su infraestructura de ti, incluidos tanto local como en la nube. El mejor ejemplo de una regla de privacidad de datos es el Reglamento General de protección de datos (RGPD) de la Unión Europea. El incumplimiento de las regulaciones de privacidad de datos puede dar lugar a multas importantes.

Algunos ejemplos de los tipos de datos de Microsoft 365 son las sesiones de chat en Microsoft Teams, los correos electrónicos en Exchange y los archivos en SharePoint y OneDrive. Esta solución proporciona instrucciones sobre cómo identificar, localizar, proteger, controlar y responder a incidentes de privacidad de datos para los datos personales almacenados en los servicios de Microsoft 365 que están sujetos a las regulaciones de privacidad de datos.

![Implementación de protección de la información para las normativas de privacidad de los datos](../media/information-protection-deploy/information-protection-deploy-big-picture.png)

También se proporciona información adicional sobre el uso de los controles de identidad, dispositivo y protección contra amenazas de Microsoft 365 para sus necesidades de privacidad de datos. 

Para cumplir con los criterios de protección de la información para el cumplimiento de las normas de privacidad de datos, use estas funciones y características de Microsoft 365.

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Administrador de cumplimiento | Administre las actividades de cumplimiento normativo relacionadas con los servicios en la nube de Microsoft con esta herramienta de evaluación de riesgos basada en flujos de trabajo en el portal de confianza del servicio de Microsoft. | Microsoft 365 E3 y E5 |
| Puntuación de cumplimiento (versión preliminar) | Vea una calificación general de la configuración de cumplimiento actual y las recomendaciones para mejorarla en el Centro de cumplimiento de Microsoft 365. | Microsoft 365 E3 y E5 |
| Protección contra amenazas avanzada de Office (ATP) | Proteja sus datos y aplicaciones de Microsoft 365, como mensajes de correo electrónico, documentos de Office y herramientas de colaboración, ante posibles ataques. | Microsoft 365 E3 y E5 | 
| Etiquetas de confidencialidad | Clasifique y proteja los datos de su organización sin arriesgar la productividad de los usuarios y su capacidad para colaborar, mediante el establecimiento de etiquetas con distintos niveles de protección en el correo electrónico, los archivos y los sitios. | Microsoft 365 E3 y E5 |
| Protección de pérdida de datos (DLP) | Detecte, advierta y bloquee el uso compartido riesgoso, involuntario o inadecuado, como el de los datos que contengan información personal, tanto interna como externamente. | Microsoft 365 E3 y E5 | 
| Directivas y etiquetas de retención de datos | Implemente controles de gobierno de la información, como cuánto tiempo se conservan los datos y los requisitos de almacenamiento de datos personales sobre los clientes, para cumplir con las directivas de la organización o las regulaciones de datos. | Microsoft 365 E3 y E5 |
| Cifrado de correo electrónico | Envíe y reciba mensajes de correo electrónico cifrado entre las personas de dentro y fuera de la organización que contengan datos regulados, como los datos personales sobre clientes. | Microsoft 365 E3 y E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organización de las instrucciones de esta solución

Para ayudarle a comprender las herramientas de Microsoft 365 disponibles para identificar, administrar, controlar y supervisar los datos personales sujetos a una o más regulaciones relacionadas con la privacidad, esta guía se organiza en secciones.
 
![Implementación de protección de la información para las normativas de privacidad de los datos](../media/information-protection-deploy/information-protection-deploy-grid.png)

Cada una de estas secciones corresponde a un artículo independiente en esta solución.

>[!Note]
>Si ya está familiarizado con sus obligaciones de privacidad de datos y se está ejecutando en un plan existente, es posible que quiera centrarse en las instrucciones de prevención, protección, retención e investigación.

>[!Important]
>Seguir esta guía no necesariamente hará que cumpla con ninguna normativa de privacidad de datos, especialmente teniendo en cuenta el número de pasos necesarios que se encuentran fuera del contexto de las características. Usted es responsable de garantizar su cumplimiento y de consultar a sus equipos legales y de cumplimiento, o bien buscar orientación y consejos de terceros que se especializan en el cumplimiento de las normas.
>

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Planeación: evaluación de los riesgos de privacidad de datos e identificación de elementos confidenciales 

La evaluación de los riesgos y las regulaciones de privacidad de datos a los que está sujeta su organización es un primer paso clave antes de empezar a implementar mejoras, incluidas las que se pueden obtener a través de la configuración de Microsoft 365. Esto puede incluir una evaluación general de la preparación o la identificación de los tipos de información confidencial que están sujetos a controles normativos que la organización debe cumplir, así como la ocurrencia de los mismos en el entorno de Microsoft 365.

Para obtener más información, vea [evaluar los riesgos de privacidad de datos e identificar elementos confidenciales](information-protection-deploy-assess.md).

## <a name="track-use-compliance-score-and-compliance-manager"></a>Seguir: usar la puntuación de cumplimiento y el administrador de cumplimiento 

La puntuación de cumplimiento y el administrador de cumplimiento proporcionan un conjunto integrado de herramientas disponibles en el centro de administración de cumplimiento de Microsoft 365 y en el portal de confianza de servicios. Juntas, estas herramientas le proporcionan una capacidad integrada para realizar un seguimiento de las acciones de mejora y administrarlas en todo el conjunto, así como las relacionadas con las diversas regulaciones de privacidad de datos a las que está sometido.

Las herramientas también le permiten aprovechar las plantillas de evaluación integradas específicas de cada reglamentación, donde puede realizar un seguimiento de los elementos de acción para cada plantilla de evaluación seleccionada, así como ver los controles reguladores específicos y relacionarlos con acciones específicas.

Para obtener más información, consulte [usar la puntuación de cumplimiento y el administrador de cumplimiento para administrar las acciones de mejora](information-protection-deploy-compliance.md).

## <a name="prevent-use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>Evitar: usar la identidad, el dispositivo y la protección contra amenazas para la privacidad de la privacidad de los datos

Microsoft 365 proporciona una serie de capacidades de identidad, dispositivo y protección contra amenazas que puede usar para cumplir con el cumplimiento de las normas de privacidad de los datos. 

Para obtener más información, consulte [usar identidad, dispositivo y protección contra amenazas para la normativa de privacidad de datos](information-protection-deploy-identity-device-threat.md).

En este artículo se describen brevemente las necesidades de privacidad de los datos por lo general en estas áreas y se proporciona una lista de soluciones de Microsoft 365 relacionadas, con vínculos a más información para ayudarle a solucionar los requisitos de implementación. 

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Proteger la información sujeta a la normativa de privacidad de datos

Las regulaciones de privacidad de datos establecen una serie de controles de protección de información personal que se pueden usar en su entorno, incluidos más que 40 proteger los controles de la información a través de las cuatro normas de privacidad de datos en nuestro conjunto de ejemplo de RGPD, California Consumer Protection Act (CCPA), HIPAA-Technology (Act de Sanidad de salud de Estados Unidos) y la ley de protección de datos

Para obtener más información, consulte [proteger la información sujeta a la normativa de privacidad de datos en la organización](information-protection-deploy-protect-information.md).

En este artículo se presentan los principales esquemas de control que se pueden usar para tratar las necesidades de protección de la información para la privacidad de los datos en la organización.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Retain: controle la información sujeta a la normativa de privacidad de datos

Normas de privacidad de datos llame a los controles de gobierno de información personal que se pueden usar en su entorno, incluidos más de veinte controles en las cuatro normas de privacidad de datos en nuestro conjunto de ejemplo de RGPD, CCPA, HIPAA-tecnología y LGPD.

Para obtener más información, consulte [regir la información sujeta a la normativa de privacidad de datos en su organización](information-protection-deploy-govern.md).

Aunque las regulaciones de privacidad de datos pueden ser imprecisas para el gobierno de la información, como la &mdash; retención con fines, la eliminación y el archivado &mdash; en este artículo se presentan los principales esquemas de control que se pueden usar para satisfacer la privacidad de los datos en la organización.

## <a name="investigate-monitor-and-respond-subject-to-data-privacy-regulation"></a>Investigar: supervisar y responder sujeto a la normativa de privacidad de datos

Hay disponibles características de Microsoft 365 para ayudarle a supervisar, investigar y responder a los incidentes de privacidad de los datos de su organización a medida que opera las capacidades relacionadas. 

Tener procesos, procedimientos y otra documentación para cada uno de ellos puede ser importante para demostrar el cumplimiento de los organismos reguladores.

Para obtener más información, vea [supervisar y responder a incidentes de privacidad de datos en la organización](information-protection-deploy-monitor-respond.md).
