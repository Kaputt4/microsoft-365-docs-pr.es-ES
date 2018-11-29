---
title: Criterios de salida de infraestructura de administración de dispositivos móviles
description: Microsoft 365 Enterprise incluye administración de dispositivos móviles con Microsoft Intune. Revise los requisitos y requisitos previos, configurar Intune con su recurso de Azure Active Directory, inscribirse iOS, Mac OS, Android y Windows dispositivos, implementar aplicaciones, crear un perfil de configuración, use una directiva de cumplimiento de normas y habilitar el acceso condicional para mobile administración de dispositivos con Microsoft 365 Enterprise.
keywords: Documentación de Microsoft 365 365 de Microsoft, Microsoft 365 Enterprise, administración de dispositivos móviles, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871330"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Criterios de salida de infraestructura de administración de dispositivos móviles

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Esto se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

Antes de pasar a la siguiente fase del proceso de implementación, asegúrese de que la configuración cumple los siguientes requisitos de infraestructura de administración de dispositivos móviles.

- Intune está configurado y se han creado los usuarios y los grupos de Azure AD para aplicar las reglas de la organización para dispositivos.
- Ha inscrito los dispositivos en Intune para que puedan recibir las directivas que cree.
- Se agregaron las aplicaciones a los dispositivos para que los usuarios obtengan acceso a los servicios en la nube de Microsoft 365 de su organización, como Exchange Online y SharePoint Online.
- Las características y ajustes se configuraron y aplicaron en los dispositivos con los usuarios y grupos de Azure AD que creó (por ejemplo, habilitar la protección antivirus y restringir aplicaciones específicas).
- Las directivas de cumplimiento se aplicaron para exigir un firewall o una longitud de contraseña en un dispositivo. Si los dispositivos no cumplen estas normas, el acceso condicional bloquea el acceso a los datos de la organización.

## <a name="next-phase"></a>Fase siguiente

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| La siguiente fase del proceso de implementación de extremo a extremo para Microsoft 365 Enterprise es la [protección de la información](infoprotect-infrastructure.md). |
