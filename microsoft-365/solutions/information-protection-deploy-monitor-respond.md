---
title: Supervisar y responder a los incidentes de privacidad de los datos de la organización
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
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use las directivas de auditoría y alerta y las solicitudes de sujetos de datos para supervisar y responder a los incidentes de datos personales.
ms.openlocfilehash: 296220ac8b34d9ce10c783194b78ca344e746b84
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377204"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Supervisar y responder a los incidentes de privacidad de los datos de la organización

Las características de Microsoft 365 están disponibles para ayudarle a supervisar, investigar y responder a los incidentes de privacidad de los datos de su organización a medida que opera las capacidades relacionadas. Tener procesos, procedimientos y otra documentación para cada uno de ellos también puede ser importante para demostrar el cumplimiento de los organismos reguladores.

Entre ellos se incluyen: 

- Directivas de auditoría y alerta
- Solicitudes de los interesados (incluida la búsqueda de contenido y eDiscovery)
- Informes y herramientas de investigación adicionales

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Regulaciones de privacidad de datos que afectan al uso de herramientas de supervisión y respuesta

A continuación, se incluye una lista de muestra de las normas de privacidad de datos que pueden relacionarse con controles de gobierno de información:

- Artículo 46 de LGPD
- Artículo 48 de LGPD
- Artículo de RGPD (5) (1) (f)
- Artículo de RGPD (15) (1) (e)
- HIPAA-TECNOLOGÍA (45 C.F.R. 164.308 (a) (1) (II) (D))
- HIPAA-TECNOLOGÍA (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-TECNOLOGÍA (45 C.F.R. 164.312 (b))
- CCPA (1798.105 (c))

Para obtener más información, consulte [evaluar los riesgos de privacidad de datos e identificar la información confidencial](information-protection-deploy-assess.md).

Las regulaciones de privacidad de datos generalmente llaman a los siguientes elementos para la supervisión y la respuesta:

- Auditoría, alertas e informes de actividades relacionadas con el almacenamiento, el uso compartido y el procesamiento de datos personales
- La capacidad para responder a una solicitud de interesado (DSR) y, en algunos casos, realizar una investigación y otras medidas administrativas para cumplir con dichas solicitudes.

La organización también puede desear realizar actividades de supervisión y respuesta para otros fines, como otras necesidades de cumplimiento o motivos empresariales. El establecimiento de la supervisión y el esquema de respuesta para la privacidad de los datos debe realizarse como parte de la planeación general y la planeación, implementación y administración de la respuesta.

Para ayudarle a empezar con un esquema de supervisión y respuesta en Microsoft 365 para las regulaciones de privacidad de datos, en este artículo se enumeran las capacidades útiles de Microsoft 365 para responder a preguntas como las siguientes: 

- ¿Qué tipo de técnicas de supervisión, investigación e informes se encuentran disponibles para los distintos tipos y orígenes de datos?
- Qué mecanismos se necesitarán para controlar las solicitudes del interesado (interesado) y cualquier acción correctiva, como anonymization, censura y eliminación.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Directivas de auditoría y alerta en el centro de seguridad y cumplimiento

Consulte estos artículos para la configuración de auditoría, auditoría avanzada y directivas de alerta:

- [Auditoría unificada](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Auditoría de buzones](../compliance/enable-mailbox-auditing.md)
- [Auditoría avanzada](../compliance/advanced-audit.md)
- [Directivas de alerta](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de interesados para RGPD y CCPA

Consulte [solicitudes de interesados de datos para RGPD y CCPA](../compliance/gdpr-dsr-office365.md) para obtener información sobre cómo responder a un DSR en Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Administrar usuarios eliminados en Microsoft Stream

Para Microsoft Stream, cuando se elimina un usuario de Azure Active Directory (Azure AD), si su nombre estaba asociado con un vídeo de transmisión por secuencias anterior a ese punto, su dirección de correo electrónico permanece asociada al vídeo. Consulte [administrar usuarios eliminados de Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) para quitarlo.

## <a name="additional-investigative-tools"></a>Herramientas de investigación adicionales

A continuación se muestran dos herramientas adicionales que podrían ser útiles para supervisar, investigar y corregir incidentes relacionados con la privacidad de los datos en su organización:

- [Administración de riesgos de Insider en microsoft 365](../compliance/insider-risk-management.md), una característica del centro de administración de cumplimiento de Microsoft para ayudar a minimizar el riesgo interno, ya que permite detectar, investigar y realizar acciones en actividades de riesgo de la organización.
- [Investigaciones de datos en microsoft 365](../compliance/overview-data-investigations.md), una característica del centro de administración de cumplimiento de Microsoft para buscar datos confidenciales, malintencionados o mal colocados en Microsoft 365 y, a continuación, investigar qué ocurrió para llevar a cabo las acciones adecuadas para corregir el incidente.
