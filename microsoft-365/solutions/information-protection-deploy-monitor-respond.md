---
title: Supervisar y responder a incidentes de privacidad de datos en su organización
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use directivas de auditoría y alertas y solicitudes del interesado para supervisar y responder a incidentes de datos personales.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928429"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Supervisar y responder a incidentes de privacidad de datos en su organización

Microsoft 365 están disponibles para ayudarle a supervisar, investigar y responder a incidentes de privacidad de datos en su organización a medida que opera las capacidades relacionadas. Tener procesos, procedimientos y otra documentación para cada uno de ellos también puede ser importante para demostrar el cumplimiento de los organismos reguladores.

Entre ellas se incluyen: 

- Directivas de auditoría y alerta
- Solicitudes del interesado (incluida la búsqueda de contenido y la exhibición de documentos electrónicos)
- Herramientas de investigación e informes adicionales

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Normativas de privacidad de datos que afectan al uso de herramientas de supervisión y respuesta

Esta es una lista de ejemplo de las normativas de privacidad de datos que pueden estar relacionadas con los controles de gobierno de la información:

- Artículo 46 de LGPD
- Artículo 48 de LGPD
- Artículo del RGPD (5)(1)(f)
- Artículo del RGPD (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

Para obtener más información, vea [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).

Por lo general, los reglamentos de privacidad de datos piden lo siguiente para la supervisión y respuesta:

- Auditoría, alerta e informes de actividades relacionadas con el almacenamiento, uso compartido y procesamiento de datos personales
- La capacidad de responder a una solicitud de interesado (DSR) y, en algunos casos, realizar medidas de investigación y otras medidas administrativas para cumplir con dichas solicitudes.

Es posible que su organización también desee realizar actividades de supervisión y respuesta para otros fines, como otras necesidades de cumplimiento o por motivos empresariales. Establecer el esquema de supervisión y respuesta para la privacidad de datos debe realizarse como parte de la planeación, implementación y administración de la supervisión y respuesta generales.

Para ayudarle a empezar con un esquema de supervisión y respuesta en Microsoft 365 para las regulaciones de privacidad de datos, en este artículo se enumeran las funcionalidades útiles en Microsoft 365 para responder a preguntas como: 

- ¿Qué tipo de técnicas diarias de supervisión, investigación e informes están disponibles para los distintos tipos de datos y orígenes?
- Qué mecanismos se necesitan para controlar las solicitudes de interesados (DSR) y las acciones correctivas, como anonimización, redacción y eliminación.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Auditoría y directivas de alerta en el Centro de seguridad y cumplimiento

Vea estos artículos para configurar directivas de auditoría, auditoría avanzada y alertas:

- [Auditoría unificada](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Auditoría de buzones](../compliance/enable-mailbox-auditing.md)
- [Auditoría avanzada](../compliance/advanced-audit.md)
- [Directivas de alerta](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes del interesado para el RGPD y el CCPA

Consulte Solicitudes del interesado para el RGPD y [el CCPA](/compliance/regulatory/gdpr-dsr-Office365) para obtener información sobre cómo responder a un DSR en Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Administrar usuarios eliminados en Microsoft Stream

Para Microsoft Stream, cuando se elimina un usuario de Azure Active Directory (Azure AD), si su nombre estaba asociado a un vídeo stream publicado antes de ese punto, su dirección de correo electrónico permanece asociada al vídeo. Consulta [Administrar usuarios eliminados de Microsoft Stream](/stream/managing-deleted-users) para quitarlo.

## <a name="insider-risk-management-as-an-investigative-tool"></a>Administración de riesgos de Insider como herramienta de investigación

La administración de riesgos de [Insider](../compliance/insider-risk-management.md) en Microsoft 365 es una característica del Centro de administración de Cumplimiento de Microsoft para ayudarle a minimizar los riesgos internos, ya que le permite detectar, investigar y tomar medidas en actividades de riesgo en su organización.