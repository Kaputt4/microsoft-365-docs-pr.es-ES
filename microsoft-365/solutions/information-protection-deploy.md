---
title: Implementar la protección de la información para las regulaciones de privacidad de datos con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Configure la infraestructura de seguridad y servicio para proteger su información y cumplir con las regulaciones de privacidad de datos.
ms.openlocfilehash: 35ccfb21accd969c2a2cbdddde9a4ec1c7eeed64
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695115"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Implementar la protección de la información para las regulaciones de privacidad de datos con Microsoft 365

Esta solución proporciona instrucciones sobre cómo planear y proteger los datos personales almacenados en los servicios de 365 de Microsoft y, potencialmente, sujetos a normas de privacidad de datos, como el Reglamento General de protección de datos (RGPD) de la Unión Europea. Esta solución se centra en las características de cumplimiento y protección de la información de Microsoft, la puntuación de cumplimiento de Microsoft y las herramientas de evaluación para ayudarle a conocer sus datos. 
 
También se proporciona información adicional sobre el uso de controles de identidad de Microsoft, dispositivos y protección contra amenazas para las necesidades de privacidad de datos, así como para las herramientas de detección y respuesta de incidentes de datos. 

## <a name="organization-of-this-guidance-material"></a>Organización de este material de orientación

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
