---
title: 'Paso 4: Configurar Windows Information Protection'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprender e implementar Windows Information Protection en Microsoft 365.
ms.openlocfilehash: e32b09c20e86ff927748f7aedd8b8d769e07916e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073570"
---
# <a name="step-4-configure-windows-information-protection"></a>Paso 4: Configurar Windows Information Protection

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

A medida que se utilizan más dispositivos personales para el trabajo, aumenta el riesgo de que aplicaciones y dispositivos sufran una pérdida de datos privados de la organización. Por ejemplo, un empleado envía accidentalmente una imagen de un plan de marketing de un producto futuro a una red social o guarda un archivo que contiene información confidencial en su almacenamiento de nube público. 

Windows Information Protection (WIP) le ayuda a protegerse contra estos tipos de filtrado de datos en dispositivos con Windows 10. Para obtener más información, vea [Proteger los datos empresariales con WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

En Microsoft 365 Enterprise, WIP es una combinación de Windows 10 Enterprise y Microsoft Intune, que se incluye con Enterprise Mobility + Security (EMS) en su suscripción. 

Para implementar WIP en su organización con Microsoft 365 Enterprise:

1. Inscriba los dispositivos de Windows en Intune. Debería haberlo hecho en la [Fase 5: administración de dispositivos móviles](mobility-infrastructure.md).
2. Cree una [directiva Intune para WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).
  - Asegúrese de que se ha rellenado la lista de aplicaciones protegidas.
  - Elija el nivel de protección de WIP.

También puede usar WIP con [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm). 

Vea [Procedimientos recomendados para WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) para obtener más información.

Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step4) correspondientes a este paso.

## <a name="next-step"></a>Paso siguiente


|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Configurar la Prevención de pérdida de datos de Office 365](infoprotect-data-loss-prevention.md)|


