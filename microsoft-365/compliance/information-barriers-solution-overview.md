---
title: Barreras de información
description: Obtenga información sobre cómo configurar barreras de información en Microsoft Purview.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, barreras de información
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: aaba1c642d4615d3eb5163736450f3f8f3c27062
ms.sourcegitcommit: 99494a5530ad64802f341573ad42796134190296
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "65396187"
---
# <a name="information-barriers"></a>Barreras de información

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft 365 permite la comunicación y la colaboración entre grupos y organizaciones y admite formas de restringir la comunicación y la colaboración entre grupos específicos de usuarios cuando sea necesario. Esto puede incluir situaciones o escenarios en los que quiera restringir la comunicación y la colaboración entre dos grupos para evitar que se produzca un conflicto de interés en su organización. Esto también puede incluir situaciones en las que necesite restringir la comunicación y la colaboración entre ciertas personas dentro de su organización para proteger la información interna.

Microsoft Purview Barreras de información (IB) se admite en Microsoft Teams, SharePoint Online y OneDrive para la Empresa. Un administrador de cumplimiento o un administrador de IB puede definir directivas para permitir o impedir las comunicaciones entre grupos de usuarios en Microsoft Teams. Las directivas de IB se pueden usar para situaciones como las siguientes:

- El usuario del grupo de operadores de día no debe comunicarse ni compartir archivos con el equipo de marketing.
- El personal financiero que trabaja con información confidencial de la empresa no debe comunicarse ni compartir archivos con determinados grupos de su organización.
- Un equipo interno con material secreto comercial no debe llamar ni chatear en línea con personas de determinados grupos dentro de su organización.
- Un equipo de investigación solo debe llamar o chatear en línea con un equipo de desarrollo de productos.

## <a name="configure-information-barriers"></a>Configuración de barreras de información

Siga estos pasos para configurar IB para su organización:

![Pasos de barreras de información de soluciones de riesgo interno.](../media/ir-solution-ib-steps.png)

1. Más información sobre [las barreras de información](information-barriers.md)
2. Configuración [de requisitos previos y permisos](information-barriers-policies.md#step-1-make-sure-prerequisites-are-met)
3. Segmentar [usuarios de la organización](information-barriers-policies.md#step-2-segment-users-in-your-organization)
4. Creación y configuración de [directivas de IB](information-barriers-policies.md#step-3-create-ib-policies)
5. Aplicación de [directivas de IB](information-barriers-policies.md#step-4-apply-ib-policies)

## <a name="more-information-about-information-barriers"></a>Más información sobre las barreras de información

- [Atributos para directivas de IB](information-barriers-attributes.md)
- [Edición o eliminación de directivas de IB](information-barriers-edit-segments-policies.md)
