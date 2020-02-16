---
title: 'Paso 7: Configurar la administración de acceso con privilegios para Office 365'
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
description: Comprenda y configure la administración del acceso con privilegios para Office 365
ms.openlocfilehash: f29b1e0934a4b9a6d4e3347584f39423d446ed58
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067237"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a>Paso 7: Configurar la administración de acceso con privilegios para Office 365

*Este paso es opcional y solo es válido para las versiones E5 y de cumplimiento avanzado de Microsoft 365 Enterprise*

![Fase 6: Protección de la información](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

La administración del acceso con privilegios se habilita configurando directivas que especifiquen el acceso puntual para actividades basadas en tareas en el inquilino de Office 365. Permite proteger la organización ante infracciones que puedan usar las cuentas existentes de administrador con privilegios y acceso permanente para acceder a datos confidenciales o acceder a opciones de configuración críticas. Por ejemplo, puede configurar una directiva de administración del acceso con privilegios que requiera una autorización explícita para acceder a la configuración del buzón de correo del inquilino de Office 365 y modificar la misma.

En este paso, habilitará la administración del acceso con privilegios en el inquilino de Office 365 y configurará directivas de acceso con privilegios que proporcionen seguridad adicional para el acceso basado en tareas a los datos y las opciones de configuración de Office 365 de la organización. Para empezar con el acceso con privilegios en la organización de Office 365, debe seguir estos tres pasos básicos:
- Crear un grupo de aprobadores
- Habilitar el acceso con privilegios
- Crear directivas de aprobación

Una vez configurada, la administración del acceso con privilegios permitirá a la organización trabajar sin privilegios permanentes y proporcionará un nivel de defensa contra las vulnerabilidades derivadas de dicho acceso administrativo. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea a la que se haya asociado una directiva definida de aprobación. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deberán solicitar y obtener la aprobación de acceso para tener los permisos necesarios para ejecutar las tareas definidas en la directiva.

Para habilitar la administración del acceso con privilegios de Office 365, vea el tema [Configurar la administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Para obtener más información, vea el tema [Administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Para poner en práctica esta configuración en un entorno de prueba, consulte [Guía de gestión de acceso privilegiado en un entorno de pruebas](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step7) correspondientes a este paso.

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de protección de información](infoprotect-exit-criteria.md)
