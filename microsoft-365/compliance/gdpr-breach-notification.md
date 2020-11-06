---
title: Notificación de infracciones
description: Obtenga información acerca de cómo los servicios Microsoft protegen contra una infracción de datos personales y cómo Microsoft responde y le notifica si se produce una infracción.
keywords: Microsoft 365, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a671fc9234f76c63ff7336369c87e680a4432cc3
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920294"
---
# <a name="gdpr-breach-notification"></a>Notificación de incumplimiento del RGPD

The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located. Additional details can be found in the [GDPR Summary topic](gdpr.md). This document leads you to information on the completion of Breach Notifications under the GDPR using Microsoft products and services.

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>¿Qué constituye una vulneración de datos personales en virtud del RGPD?

Personal data means any information related to an individual that can be used to identify them directly or indirectly. A personal data breach is 'a breach of security leading to the accidental or unlawful destruction, loss, alteration, unauthorized disclosure of, or access to, personal data transmitted, stored, or otherwise processed'.

## <a name="terminology"></a>Terminología

Definiciones útiles de los términos del RGPD utilizados en este documento:

- *Controlador de datos (controlador)* : una persona jurídica, autoridad pública, agencia u otro organismo, que por sí solos o conjuntamente con otras personas, determinan el propósito y el medio del procesamiento de datos personales.  
- *Datos personales* e *interesado* : cualquier información relacionada con una persona física identificada o una persona natural identificable (interesado), una persona física identificable es la que puede identificarse, directa o indirectamente.  
- *Procesador* : una persona física o jurídica, entidad pública, agencia u otro organismo que procese datos personales en nombre del controlador.  
- *Datos de clientes* : datos producidos y almacenados en las operaciones diarias de su empresa.

## <a name="microsoft-and-breach-notification"></a>Microsoft y la notificación de incumplimiento

Microsoft takes its obligations under the General Data Protection Regulation (GDPR) seriously. A security incident/data breach refers to events such as unlawful access to customer's data stored on Microsoft equipment or in Microsoft facilities, or unauthorized access to such that has the potential to result in the loss, disclosure, or alteration of customer data.

As a data processor, Microsoft ensures that service customers are able to meet the GDPR's breach notification requirements as data controllers. Our notification provides the information needed to make that assessment. Microsoft notifies customers of any personal data breach, except for those cases where personal data is confirmed to be unintelligible (for example, encrypted data where integrity of the keys is confirmed).

Data controllers are responsible for assessing risks to data privacy and determining whether a breach requires notification of a customer's DPA. Microsoft provides the information needed, along with your GDPR compliance policy, to make that assessment.

Initial notification includes a description of the nature of the breach, approximate user impact, and mitigation steps (if applicable). If our investigation is not complete at the time of initial notification, we will indicate next steps and timelines for subsequent communication. For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.

A continuación, se muestra información sobre las notificaciones de incumplimiento de productos y servicios específicos de Microsoft.
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft invests extensively in systems, processes, and personnel to reduce the likelihood of personal data breach and to quickly detect and mitigate consequence of breach if it does occur. Additional details can be read at [Office 365 Investments in Data Security](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security).

    A customer may become aware of a breach and wish to contact Microsoft. In this case, notify Microsoft Support, which will then interface with engineering teams for more information.

2. **[Azure y Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    Microsoft tiene un servicio ininterrumpido y global de respuesta al incidente que sirve para reducir los efectos de los ataques en Microsoft Azure y Dynamics 365.

    - *Detección de vulneraciones* : ya que tanto Microsoft como el cliente tienen obligaciones de seguridad, los servicios de Azure usan un modelo de responsabilidad compartida para definir las responsabilidades operativas y de seguridad. Microsoft no supervisa ni responde a los incidentes de seguridad que se encuentran en el ámbito de responsabilidad del cliente. La respuesta a las incidencias del cliente puede implicar la colaboración con el [soporte técnico](https://azure.microsoft.com/support/options/) de Azure, si se cuenta con los contratos de servicio adecuados. Microsoft Azure también ofrece varios servicios (por ejemplo, [Azure Defender](https://azure.microsoft.com/services/security-center/)) que los clientes pueden utilizar para desarrollar y administrar la respuesta a incidentes de seguridad.

        For a list of events that trigger a breach investigation in Microsoft Azure, see [Detection of Potential Breaches](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches). [Azure and Breach Notification under the GDPR](gdpr-breach-azure-dynamics.md) further details how Microsoft investigates, manages, and responds to security incidents within Azure.

    - *Data Breach Response* : Microsoft determines appropriate priority and severity levels of a breach by investigating the functional impact, recoverability, and information impact of the incident. Priority and severity may change over the course of the investigation, based on new findings and conclusions. Microsoft's security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. These processes are detailed in [Azure's Data Breach Response](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response).

    - *Customer Notification* : Microsoft Azure notifies customers and regulatory authorities of data breaches as required. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances:

        - Microsoft cree que el acto de realizar una notificación aumentará el riesgo para otros clientes.
        - The 72-hour timeline may leave some incident details available. These details will be provided to you as the investigation proceeds.

        Puede encontrar más detalles en [Notificación de cliente](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification).

3. **[Soporte técnico y Servicios profesionales de Microsoft](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    The nature of professional services means that some data protection incidents may fall within the customer's realm of responsibility. When Microsoft Professional Services identifies a data protection incident, it follows documented industry standard response plan as outlined in [Scope & Limits of Data Protection Incident Response Process](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process).

## <a name="breach-notification-admin-tools"></a>Herramientas de administración de notificación de infracciones

- **Establecer el contacto de privacidad de la organización** : los administradores de espacios empresariales pueden usar el [Portal de administración de Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=2052736) para definir el contacto de privacidad de la organización por si Microsoft necesita comunicarse con él.

## <a name="learn-more"></a>Obtén más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
