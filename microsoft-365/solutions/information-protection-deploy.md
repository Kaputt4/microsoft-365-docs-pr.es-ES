---
title: Implementación de la protección de la información para las regulaciones de privacidad de datos con Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/22/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-overview
ms.custom: admindeeplinkCOMPLIANCE
description: Configure la protección de la información en Microsoft 365 para las regulaciones de privacidad de datos como RGPD y la Ley de privacidad del consumidor de California (CCPA), incluidos Microsoft Teams, SharePoint y correo electrónico.
ms.openlocfilehash: ece8483773d3e2f5cdafe90bd93e11c52e2ba838
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939024"
---
# <a name="deploy-information-protection-for-data-privacy-regulations-with-microsoft-365"></a>Implementación de la protección de la información para las regulaciones de privacidad de datos con Microsoft 365

Su organización puede estar sujeta a normativas regionales de privacidad de datos que requieren que proteja, administre y proporcione derechos y control sobre la información personal almacenada en su infraestructura de TI, incluidos tanto en el entorno local como en la nube. El mejor ejemplo de un reglamento de privacidad de datos es el Reglamento General de Protección de Datos (RGPD) de la Unión Europea. El incumplimiento de las regulaciones de privacidad de datos puede dar lugar a importantes multas.

Algunos ejemplos de los tipos de datos de Microsoft 365 incluyen sesiones de chat en Microsoft Teams, correos electrónicos en Exchange y archivos en SharePoint y OneDrive. Esta solución proporciona instrucciones sobre cómo evaluar los riesgos y tomar las medidas adecuadas para proteger los datos personales en Microsoft 365. Esto incluye la identificación de información personal para que pueda proteger, controlar y responder a incidentes de privacidad de datos.

![¿Qué es la protección de la información para las regulaciones de privacidad de datos?](../media/information-protection-deploy/information-protection-data-privacy-regulations-overview.png#lightbox)

También se proporciona información adicional sobre el uso de Microsoft 365 controles de identidad, dispositivo y protección contra amenazas para sus necesidades de privacidad de datos.

Vea este vídeo para obtener información general del proceso.
<br>
<br>
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4NHCQ]

Estas funcionalidades y características Microsoft 365 le ayudan a cumplir los criterios para proteger la información.

| Funcionalidad o característica | Description | Licencias |
|:-------|:-----|:-------|
| Administrador de cumplimiento | Administre las actividades de cumplimiento normativo, obtenga una puntuación general de la configuración de cumplimiento actual y busque recomendaciones para mejorar. Se trata de una herramienta de evaluación de riesgos basada en flujos de trabajo en el portal de cumplimiento de Microsoft Purview. | Microsoft 365 E3 y E5 |
| Microsoft Defender para Office 365 | Proteja sus datos y aplicaciones de Microsoft 365, como mensajes de correo electrónico, documentos de Office y herramientas de colaboración, ante posibles ataques. | Microsoft 365 E3 y E5 |
| Etiquetas de confidencialidad | Clasifique y proteja los datos de su organización sin obstaculizar la productividad de los usuarios y su capacidad de colaborar. Coloque etiquetas con varios niveles de protección en el correo electrónico, los archivos o los sitios. | Microsoft 365 E3 y E5 |
| Protección de pérdida de datos (DLP) | Detecte, advierta y bloquee el uso compartido de datos de riesgo, involuntarios o inadecuados que contengan información personal, tanto interna como externamente. | Microsoft 365 E3 y E5 |
| Directivas y etiquetas de retención de datos | Implementar controles de gobernanza de la información. Estos pueden incluir la determinación del tiempo que se deben conservar los datos (como los datos personales relacionados con los clientes) para cumplir con las directivas o las regulaciones de datos de su organización. | Microsoft 365 E3 y E5 |
| Cifrado de correo electrónico | Proteja los datos personales enviando y recibiendo mensajes de correo electrónico cifrados entre personas dentro y fuera de su organización. | Microsoft 365 E3 y E5 |
||||

## <a name="organization-of-the-guidance-in-this-solution"></a>Organización de las instrucciones de esta solución

Para ayudarle a comprender las herramientas de Microsoft 365 disponibles para ayudarle a cumplir una o varias regulaciones relacionadas con la privacidad, esta guía se organiza en secciones.

![Pasos para implementar la protección de la información para las regulaciones de privacidad de datos.](../media/information-protection-deploy/information-protection-data-privacy-regulations-steps.png)

Cada una de estas secciones corresponde a un artículo independiente de esta solución.

> [!NOTE]
> Si ya está familiarizado con sus obligaciones de privacidad de datos y se está ejecutando en un plan existente, es posible que quiera centrarse en la guía De prevención, protección, retención e investigación.

> [!IMPORTANT]
> Siguiendo esta guía no necesariamente se hará compatible con ninguna regulación de privacidad de datos, especialmente teniendo en cuenta el número de pasos necesarios que están fuera del contexto de las características. Usted es responsable de garantizar su cumplimiento y de consultar a sus equipos legales y de cumplimiento, o de buscar orientación y asesoramiento de terceros que se especializan en el cumplimiento.

## <a name="plan-assess-data-privacy-risks-and-identify-sensitive-items"></a>Plan: Evaluar los riesgos de privacidad de los datos e identificar elementos confidenciales

Evaluar las normativas de privacidad de datos y los riesgos a los que está sujeta su organización es un primer paso clave antes de empezar a implementar mejoras, incluida la configuración de funcionalidades en Microsoft 365. Este trabajo puede incluir una evaluación de preparación general o la identificación de tipos de información confidencial determinados que están sujetos a los controles normativos que su organización debe cumplir.

Para obtener más información, consulte [Evaluación de riesgos de privacidad de datos e identificación de elementos confidenciales](information-protection-deploy-assess.md).

## <a name="track-run-risk-assessments-and-check-your-compliance-score"></a>Seguimiento: Ejecución de evaluaciones de riesgos y comprobación de la puntuación de cumplimiento

El Administrador de cumplimiento, disponible en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento de Microsoft Purview</a>, le proporciona una capacidad integrada para realizar un seguimiento y administrar las acciones de mejora en general, así como las relacionadas con varias regulaciones de privacidad de datos que se aplican a usted.

Puede usar plantillas de evaluación integradas específicas de cada reglamento, donde puede realizar un seguimiento de los elementos de acción de cada plantilla de evaluación seleccionada, así como ver controles normativos específicos y relacionarlos con acciones específicas.

Para obtener más información, consulte [Uso del Administrador de cumplimiento para administrar acciones de mejora](information-protection-deploy-compliance.md).

## <a name="prevent-protect-personal-data"></a>Impedir: Proteger datos personales

Microsoft 365 proporciona funcionalidades de protección contra amenazas, dispositivos y identidades que puede usar para ayudar a cumplir con el cumplimiento normativo de privacidad de datos.

Para obtener más información, consulte [Uso de la protección contra amenazas, dispositivos y identidades para la regulación de privacidad de datos](information-protection-deploy-identity-device-threat.md).

En este artículo se describe brevemente lo que los reglamentos de privacidad de datos suelen solicitar en estas áreas y se proporciona una lista de las soluciones de Microsoft 365 relacionadas, con vínculos a más información para ayudarle a abordar los requisitos de implementación.

## <a name="protect-information-subject-to-data-privacy-regulation"></a>Protección de la información sujeta a la normativa de privacidad de datos

Las regulaciones de privacidad de datos dictan una serie de controles de protección de información personal que se pueden usar en su entorno, incluidos más de 40 controles para proteger la información en solo las cuatro regulaciones de privacidad de datos de nuestro conjunto de ejemplo de RGPD, Ley de protección del consumidor de California (CCPA), HIPAA-HITECH (Estados Unidos ley de privacidad de atención médica) y la Ley de protección de datos de Brasil (LGPD).

Para obtener más información, consulte [Protección de la información sujeta a la regulación de privacidad de datos en su organización](information-protection-deploy-protect-information.md).

En este artículo se establecen los principales esquemas de control que se pueden usar para abordar las necesidades de protección de la información para la privacidad de los datos en su organización.

## <a name="retain-govern-information-subject-to-data-privacy-regulation"></a>Conservar: Controlar la información sujeta a la normativa de privacidad de datos

Las regulaciones de privacidad de datos exigen controles de gobernanza de la información personal que se pueden emplear en su entorno, incluidos más de 24 controles en las cuatro regulaciones de privacidad de datos de nuestro conjunto de ejemplo de RGPD, CCPA, HIPAA-HITECH y LGPD.

Para obtener más información, consulte [Regulación de la información sujeta a la regulación de privacidad de datos en su organización](information-protection-deploy-govern.md).

Aunque las regulaciones de privacidad de datos pueden ser imprecisas con respecto a la gobernanza&mdash; de la información, ya que la retención, eliminación y archivado&mdash; intencionadas este artículo establece los esquemas de control principales que puede usar para abordar las necesidades de gobernanza de la información para la privacidad de los datos en su organización.

## <a name="investigate-monitor-investigate-and-respond-to-data-privacy-incidents"></a>Investigar: Supervisión, investigación y respuesta a incidentes de privacidad de datos

Hay Microsoft 365 características disponibles para ayudarle a supervisar, investigar y responder a incidentes de privacidad de datos en su organización a medida que pone en marcha las funcionalidades relacionadas.

Tener procesos, procedimientos y otra documentación para usar estas características puede ser importante para demostrar el cumplimiento de los organismos normativos.

Para obtener más información, consulte [Supervisión y respuesta a incidentes de privacidad de datos en su organización](information-protection-deploy-monitor-respond.md).

## <a name="training-for-administrators"></a>Entrenamiento para administradores

Estos módulos de entrenamiento de Microsoft Learn pueden ayudarle a obtener información sobre cómo las funcionalidades que son importantes para la protección de la información.


#### <a name="information-protection"></a>Protección de la información

|Aprendizaje:|Proteger la información de la empresa con Microsoft 365|
|:---|:---|
|![Teams icono de entrenamiento de protección de información.](../media/protect-enterprise-information-microsoft-365.svg)|Proteger y asegurar la información de su organización es más difícil que nunca. La ruta de aprendizaje Proteger la información de la empresa con Microsoft 365 analiza cómo proteger su información confidencial de un uso excesivo o indebido accidental, cómo descubrir y clasificar los datos, cómo protegerlos con etiquetas de sensibilidad y cómo supervisar y analizar su información confidencial para protegerla contra su pérdida. Esta ruta de aprendizaje puede ayudarle a prepararse para las certificaciones Microsoft 365 Certified: Security Administrator Associate y Microsoft 365 Certified: Enterprise Administration Expert.<br><br>1 h - ruta de acceso Learning - 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identidad y acceso

|Aprendizaje:|Proteger la identidad y el acceso con Azure Active Directory|
|:---|:---|
|![Icono de entrenamiento de identidad y acceso.](../media/protect-identity-and-access-with-microsoft-365.svg)|La Ruta de aprendizaje de identidad y acceso cubre las últimas tecnologías de identidad y acceso, herramientas para reforzar la autenticación y orientación sobre la protección de la identidad dentro de su organización. Las tecnologías de acceso e identidad de Microsoft le permiten asegurar la identidad de su organización, ya sea en sus instalaciones o en la nube, y permiten a sus usuarios trabajar de forma segura desde cualquier lugar. Esta ruta de aprendizaje puede ayudarle a preparar los certificados Microsoft 365 Certified: Security Administrator Associate y Microsoft 365 Certified: Enterprise Administration Expert.<br><br>2 h 52 min - Learning Ruta de acceso - 6 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/m365-identity-overview/introduction/)