---
title: Criterios de salida de la infraestructura de administración de dispositivos móviles
description: Microsoft 365 Enterprise incluye la administración de dispositivos móviles con Microsoft Intune. Revise los requisitos y requisitos previos, configure Intune con el recurso de Azure Active Directory, inscriba dispositivos iOS, macOS, Android y Windows, implemente aplicaciones, cree un perfil de configuración, use una directiva de cumplimiento y habilite el acceso condicional para dispositivos móviles Administración de dispositivos con Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, administración de dispositivos móviles, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291237"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Criterios de salida de la infraestructura de administración de dispositivos móviles

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Esto se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

Asegúrese de que la configuración cumple los siguientes requisitos para la infraestructura de administración de dispositivos móviles.

- Intune está configurado y se han creado los usuarios y los grupos de Azure AD para aplicar las reglas de la organización para dispositivos.
- Ha inscrito los dispositivos en Intune para que puedan recibir las directivas que cree.
- Se agregaron las aplicaciones a los dispositivos para que los usuarios obtengan acceso a los servicios en la nube de Microsoft 365 de su organización, como Exchange Online y SharePoint Online.
- Las características y ajustes se configuraron y aplicaron en los dispositivos con los usuarios y grupos de Azure AD que creó (por ejemplo, habilitar la protección antivirus y restringir aplicaciones específicas).
- Las directivas de cumplimiento se aplicaron para exigir un firewall o una longitud de contraseña en un dispositivo. Si los dispositivos no cumplen estas normas, el acceso condicional bloquea el acceso a los datos de la organización.



## <a name="results-and-next-steps"></a>Resultados y pasos siguientes

Los dispositivos se inscriben en Intune y se configuran con las directivas adecuadas.

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Si sigue las fases de la implementación de un extremo a otro de Microsoft 365 Enterprise, la siguiente fase es la protección de la [información](infoprotect-infrastructure.md). |
