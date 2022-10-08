---
title: Administración de la gobernanza de identidades de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- scotvorg
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo usar las características de gobernanza de identidades de Microsoft 365.
ms.openlocfilehash: 5e233d1a72bcbdfcf3ccdf8dec82e6f03a0bd63b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68201009"
---
# <a name="manage-microsoft-365-identity-governance"></a>Administración de la gobernanza de identidades de Microsoft 365

El gobierno de identidades consiste en proteger, supervisar y auditar el acceso a recursos críticos mientras se garantiza la productividad de los empleados. Por ejemplo, con la gobernanza de identidades puede asegurarse de que los usuarios adecuados tengan el acceso adecuado a los recursos adecuados y determinar si este acceso cambia a lo largo del tiempo.

Para obtener más información, consulte esta [introducción a la gobernanza de identidades para Azure Active Directory (Azure AD).](/azure/active-directory/governance/identity-governance-overview)

## <a name="set-up-azure-ad-access-reviews"></a>Revisiones de acceso de Azure AD

Las revisiones de acceso de Azure AD le permiten revisar el acceso de un usuario para asegurarse de que solo las personas adecuadas tienen acceso continuo. Por ejemplo:

- Cuando un nuevo empleado se une a la organización, usted debe asegurarse de que tiene un acceso adecuado para ser productivo.
- Cuando este empleado sea derivado a otros equipos, ubicaciones o departamentos, usted debe asegurarse de que su acceso a los equipos, ubicaciones o departamentos anteriores se elimine en función de las necesidades.
- Cuando ese empleado o un invitado deje la organización, usted debe asegurarse de que su acceso se elimine.

Esto es especialmente importante si su organización está sujeta a auditorías de seguridad para determinar si las cuentas de usuario tienen un acceso excesivo, lo que podría derivar en infracciones por incumplimiento de normativas del sector o de la región.

Para obtener más información, consulte la [introducción a las revisiones de acceso](/azure/active-directory/governance/access-reviews-overview).

Consulte estos artículos para configurar diferentes tipos de revisiones de acceso:

- [Grupos y aplicaciones](/azure/active-directory/governance/create-access-review)
- [Roles de Azure AD](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Roles de recursos de Azure](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Configuración de la administración de derechos de Azure AD

Con la administración de derechos de Azure AD, puede administrar el ciclo de vida de identidad y acceso a escala mediante la automatización de flujos de trabajo de solicitudes de acceso, asignaciones de acceso, revisiones y expiración.

Los empleados necesitan acceso a varios grupos, aplicaciones y sitios para realizar su trabajo. La administración de este acceso puede ser difícil porque los requisitos cambian, se agregan nuevas aplicaciones o los usuarios necesitan derechos de acceso adicionales. Al colaborar con otras organizaciones, es posible que no sepa quién de la otra organización necesita acceso a los recursos de su organización y los usuarios externos no sabrán qué aplicaciones, grupos o sitios usa su organización.

La administración de derechos de Azure AD puede ayudarle a administrar de forma más eficaz el acceso a grupos, aplicaciones y sitios de SharePoint para usuarios internos y externos.
 
Para obtener más información, consulte [la introducción a la administración de derechos de Azure AD](/azure/active-directory/governance/entitlement-management-overview).
