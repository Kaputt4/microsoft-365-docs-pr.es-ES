---
title: 'Paso 4: Configurar Privileged Access Management para Office 365'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprenda y configure la administración del acceso con privilegios para Office 365
ms.openlocfilehash: 297d8e042c2a22c93b4ea566081d258e7ca0a5ab
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286953"
---
# <a name="step-4-configure-privileged-access-management-for-office-365"></a>Paso 4: Configurar Privileged Access Management para Office 365

*Este paso es opcional y solo es válido para las versiones E5 y de cumplimiento avanzado de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

La administración del acceso con privilegios se habilita configurando directivas que especifiquen el acceso puntual para actividades basadas en tareas en el inquilino de Office 365. Permite proteger la organización ante infracciones que puedan usar las cuentas existentes de administrador con privilegios y acceso permanente para acceder a datos confidenciales o acceder a opciones de configuración críticas. Por ejemplo, puede configurar una directiva de administración del acceso con privilegios que requiera una autorización explícita para acceder a la configuración del buzón de correo del inquilino de Office 365 y modificar la misma.

En este paso, habilitará la administración del acceso con privilegios en el inquilino de Office 365 y configurará directivas de acceso con privilegios que proporcionen seguridad adicional para el acceso basado en tareas a los datos y las opciones de configuración de Office 365 de la organización. Para empezar con el acceso con privilegios en la organización de Office 365, debe seguir estos tres pasos básicos:
- Crear un grupo de aprobadores
- Habilitar el acceso con privilegios
- Crear directivas de aprobación

Una vez configurada, la administración del acceso con privilegios permitirá a la organización trabajar sin privilegios permanentes y proporcionará un nivel de defensa contra las vulnerabilidades derivadas de dicho acceso administrativo. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea a la que se haya asociado una directiva definida de aprobación. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deberán solicitar y obtener la aprobación de acceso para tener los permisos necesarios para ejecutar las tareas definidas en la directiva.

Para habilitar la administración del acceso con privilegios de Office 365, vea el tema [Configurar la administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Para obtener más información, vea el tema [Administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

## <a name="results"></a>Resultados

El resultado de este paso es que ha incrementado la seguridad de Office 365 al habilitar el acceso puntual para datos clave y opciones de configuración de la organización.

Como control interno, consulte los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step5) correspondientes a este paso.

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de protección de información](infoprotect-exit-criteria.md)