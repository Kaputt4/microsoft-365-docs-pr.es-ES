---
title: Supervisión y respuesta a incidentes de privacidad de datos en su organización
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use directivas de auditoría y alertas y solicitudes de interesados para supervisar y responder a incidentes de datos personales.
ms.openlocfilehash: 730eb42fdf6aed66f5beac69621981848ffa6510
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64953335"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Supervisión y respuesta a incidentes de privacidad de datos en su organización

Microsoft 365 características están disponibles para ayudarle a supervisar, investigar y responder a incidentes de privacidad de datos en su organización a medida que pone en marcha las funcionalidades relacionadas. Tener procesos, procedimientos y otra documentación para cada uno de ellos también puede ser importante para demostrar el cumplimiento de los organismos reguladores.

Incluyen: 

- Directivas de auditoría y alertas
- Solicitudes del interesado (incluida la búsqueda de contenido y eDiscovery)
- Herramientas de investigación e informes adicionales

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Normativas de privacidad de datos que afectan al uso de herramientas de supervisión y respuesta

Esta es una lista de ejemplo de las regulaciones de privacidad de datos que pueden estar relacionadas con los controles de gobernanza de la información:

- Artículo 46 de la LGPD
- Artículo 48 de la LGPD
- Artículo del RGPD (5)(1)(f)
- Artículo del RGPD (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

Para obtener más información, consulte [Evaluación de riesgos de privacidad de datos e identificación de información confidencial](information-protection-deploy-assess.md).

Por lo general, las regulaciones de privacidad de datos exigen lo siguiente para la supervisión y la respuesta:

- Auditoría, alertas e informes de actividades relacionadas con el almacenamiento, el uso compartido y el procesamiento de datos personales
- La capacidad de responder a una solicitud de interesado (DSR) y, en algunos casos, realizar medidas administrativas y de investigación para cumplir dichas solicitudes.

Es posible que su organización también desee realizar actividades de supervisión y respuesta para otros fines, como otras necesidades de cumplimiento o por motivos empresariales. El establecimiento del esquema de supervisión y respuesta para la privacidad de los datos debe realizarse como parte de la supervisión general y el planeamiento, la implementación y la administración de respuestas.

Para ayudarle a empezar a trabajar con un esquema de supervisión y respuesta en Microsoft 365 para las regulaciones de privacidad de datos, en este artículo se enumeran las funcionalidades útiles de Microsoft 365 para responder a preguntas como: 

- ¿Qué tipo de técnicas diarias de supervisión, investigación e informes están disponibles para los diferentes tipos de datos y orígenes?
- Qué mecanismos serán necesarios para controlar las solicitudes del interesado (DSR) y las acciones correctivas, como anonimización, censura y eliminación.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Directivas de auditoría y alertas en el Centro de seguridad y cumplimiento

Consulte estos artículos para configurar directivas de auditoría, auditoría avanzada y alertas:

- [Auditoría unificada](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Auditoría de buzones](../compliance/enable-mailbox-auditing.md)
- [Auditoría (Premium)](../compliance/advanced-audit.md)
- [Directivas de alerta](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de interesados para el RGPD y CCPA

Consulte [Solicitudes de interesados para el RGPD y CCPA](/compliance/regulatory/gdpr-dsr-Office365) para obtener información sobre cómo responder a un DSR en Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Administración de usuarios eliminados en Microsoft Stream

Por Microsoft Stream, cuando se elimina un usuario de Azure Active Directory (Azure AD), si su nombre estaba asociado a un vídeo de Stream publicado antes de ese momento, su dirección de correo electrónico permanece asociada al vídeo. Consulte [Administración de usuarios eliminados de Microsoft Stream](/stream/managing-deleted-users) para quitarlos.

## <a name="insider-risk-management-as-an-investigative-tool"></a>Administración de riesgos internos como herramienta de investigación

[La administración de riesgos](../compliance/insider-risk-management.md) internos es una característica del portal de cumplimiento de Microsoft Purview para ayudarle a minimizar el riesgo interno, ya que le permite detectar, investigar y tomar medidas sobre actividades de riesgo en su organización.