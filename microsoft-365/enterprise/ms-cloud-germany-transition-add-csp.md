---
title: Información adicional para proveedores de soluciones en la nube
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: información adicional para proveedores de soluciones en la nube relevante para la migración desde Microsoft Cloud Deutschland.'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984921"
---
# <a name="additional-information-for-cloud-solution-providers"></a>Información adicional para proveedores de soluciones en la nube

Los proveedores de soluciones en la nube (CSP) que admiten clientes deben tomar medidas adicionales durante la migración de Microsoft Cloud Deutschland a la nueva región del centro de datos alemán.

## <a name="partner-tenant-migration"></a>Migración de inquilinos asociados

Los inquilinos de Microsoft Cloud Deutschland asociados no se migrarán. En su lugar, se creará un nuevo inquilino Office 365 servicios de correo electrónico para cada partner de Microsoft en la nueva región del centro de datos alemán.

Los inquilinos de clientes csp se migrarán a la nueva región del centro de datos alemán y se vincularán al nuevo inquilino de Office 365 de servicios del mismo partner. Después de la transición del cliente, el partner puede administrar el cliente mediante el nuevo inquilino de Office 365 servicios en la región del centro de datos alemán.

## <a name="missing-subscriptions-in-azure"></a>Faltan suscripciones en Azure

Una vez completada la transición de suscripción y licencia [(fase 3),](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) los proveedores de soluciones en la nube ya no tendrán acceso a la suscripción de Azure.

Para recuperar el acceso, siga estos pasos para elevar el acceso para administrar todas las [suscripciones y grupos de administración de Azure.](/azure/role-based-access-control/elevate-access-global-admin)
