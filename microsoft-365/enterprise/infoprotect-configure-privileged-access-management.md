---
title: 'Paso 7: configurar la administración del acceso con privilegios'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprenda y configure la administración del acceso con privilegios.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636993"
---
# <a name="step-7-configure-privileged-access-management"></a>Paso 7: configurar la administración del acceso con privilegios

*Este paso es opcional y solo es válido para las versiones E5 y de cumplimiento avanzado de Microsoft 365 Enterprise*

![Fase 6: Protección de la información](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

La administración del acceso con privilegios está habilitada mediante la configuración de directivas que especifican el acceso Just-in-Time para actividades basadas en tareas en el espacio empresarial. Puede ayudar a proteger su organización de las infracciones que puedan usar las cuentas de administrador con privilegios existentes con acceso permanente a los datos confidenciales o a la configuración crítica. Por ejemplo, puede configurar una directiva de administración de acceso privilegiada que requiera la aprobación explícita para acceder y cambiar la configuración del buzón de la organización en su espacio empresarial.

En este paso, habilitará la administración del acceso con privilegios en su espacio empresarial y configurará directivas de acceso con privilegios que proporcionen seguridad adicional para el acceso basado en tareas a las opciones de configuración y datos de su organización. Hay tres pasos básicos para empezar a trabajar con privilegios de acceso en la organización:
- Crear un grupo de aprobadores
- Habilitar el acceso con privilegios
- Crear directivas de aprobación

Una vez configurada, la administración del acceso con privilegios permitirá a la organización trabajar sin privilegios permanentes y proporcionará un nivel de defensa contra las vulnerabilidades derivadas de dicho acceso administrativo. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea a la que se haya asociado una directiva definida de aprobación. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deberán solicitar y obtener la aprobación de acceso para tener los permisos necesarios para ejecutar las tareas definidas en la directiva.

Para habilitar la administración del acceso privilegiado, consulte el tema [Configure privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .

Para obtener más información, vea el tema [Administración de acceso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .


|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Para poner en práctica esta configuración en un entorno de prueba, consulte [Guía de gestión de acceso privilegiado en un entorno de pruebas](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step7) correspondientes a este paso.

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de protección de información](infoprotect-exit-criteria.md)
