---
title: Usar Exchange Online y el Centro de seguridad y cumplimiento para cumplir con la norma SEC 17a-4
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Configure el Centro de cumplimiento y Exchange Online para cumplir con los requisitos de las normas CFTC 1.31(c)-(d), FINRA 4511 y SEC 17a-4.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 769e13951ce15fb698131860fa78f25fa133e327
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127307"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>Usar Exchange Online y el Centro de seguridad y cumplimiento para cumplir con la norma SEC 17a-4

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.

However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.

Para que estas organizaciones puedan comprender mejor cómo aprovechar el Centro de seguridad y cumplimiento para adaptarse a sus obligaciones reglamentarias para Exchange Online, específicamente en relación con los requisitos de la norma 17a-4, publicamos una evaluación de forma conjunta con Cohasset Associates.

Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.

## <a name="download-the-cohasset-assessment"></a>Descargar la evaluación de Cohasset

Puede [descargar la evaluación de Cohasset aquí](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).

![Página de título de la evaluación descargable por Cohasset Associates](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>Esta evaluación es específica para Exchange Online.

Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.

It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>Usar Bloqueo de conservación es clave para la configuración recomendada

Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:

- Conservarse durante un período de retención que no puede acortarse, solo incrementarse.
- Ser inmutable, lo que significa que el registro no se puede sobrescribir, borrar ni modificar durante el período de retención necesario.

In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.

By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:

- El período de retención de la directiva solo se puede incrementar, no se puede acortar.
- Se pueden agregar usuarios a la directiva, pero no se puede quitar ningún usuario.
- Un administrador no puede eliminar una directiva de retención.

Bloqueo de conservación puede ayudarle a cumplir con los requisitos reglamentarios de SEC 17a-4.

## <a name="how-to-set-up-preservation-lock"></a>Configurar Bloqueo de conservación

Puede bloquear una directiva de retención con PowerShell. Para más información, consulte [Usar el bloqueo de conservación para cumplir los requisitos normativos](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).

## <a name="known-limitations"></a>Limitaciones conocidas

Actualmente existen algunas limitaciones para Exchange Online:

- Las comunicaciones en conversaciones no están disponibles para los mensajes de canal y de chat de Teams.
- Los “me gusta” no se conservan para los mensajes de canal y de chat de Teams.

> [!NOTE]
> La auditoría de nivel de elemento ya está disponible en los buzones de grupo de Microsoft 365. Para más información, consulte [Administrar auditoría del buzón](enable-mailbox-auditing.md)..
