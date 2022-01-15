---
title: Paso 4. Requerir dispositivos correctos y compatibles con Intune
ms.author: bcarter
author: brendacarter
f1.keywords:
- Conditional access policy
- Microsoft Intune
- Intune device management
manager: dougeby
audience: ITPro
description: Cree una directiva de acceso condicional en Azure AD para requerir dispositivos compatibles, manteniendo los datos corporativos seguros cuando los usuarios trabajan desde cualquier dispositivo en cualquier ubicación.
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- Conditional access policy
- Microsoft Intune
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
ms.openlocfilehash: 8a953c76a3461b0f6dbf1b3663d5cef41f038371
ms.sourcegitcommit: 23166424125b80b2d615643f394a3c023cba641d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2022
ms.locfileid: "62049124"
---
# <a name="step-4-require-healthy-and-compliant-devices-with-intune"></a>Paso 4. Requerir dispositivos correctos y compatibles con Intune

El acceso condicional proporciona una comprobación adicional del estado del dispositivo antes de permitir el acceso a un servicio. El acceso condicional no funciona a menos que especifiques condiciones. En el [Paso 3. Configurar directivas de cumplimiento](manage-devices-with-intune-compliance-policies.md), has definido directivas de cumplimiento que especifican los requisitos mínimos que debe cumplir un dispositivo para acceder a tu entorno. En este artículo, crearás la directiva de acceso condicional correspondiente en Azure AD para requerir dispositivos compatibles. Esto ayuda a proteger los datos corporativos, a la vez que proporciona a los usuarios la capacidad de trabajar desde cualquier dispositivo y desde cualquier ubicación.

Después de configurar las directivas de cumplimiento de dispositivos y de asignarlas a grupos de usuarios, Intune permite a Azure AD saber si un dispositivo es compatible o no. Para usar este estado como condición de acceso, debes trabajar con el administrador de Azure AD para crear una regla de acceso condicional que requiera equipos y dispositivos móviles compatibles.


![Pasos para administrar dispositivos](../media/devices/intune-mdm-step-3.png#lightbox)

El conjunto de reglas de acceso de dispositivos e identidad de Confianza cero recomendado incluye esta regla. Consulta [Requerir equipos y dispositivos móviles compatibles](../security/office-365-security/identity-access-policies.md#require-compliant-pcs-and-mobile-devices), como se muestra a continuación.


[![Directivas de acceso de dispositivos e identidad de Confianza cero](../media/devices/identity-device-require-compliance.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-require-compliance.png)



Asegúrese de:
- Coordina los grupos de usuarios que asignó a las directivas de cumplimiento con los grupos de usuarios asignados a la directiva de acceso condicional.
- Prueba las directivas de acceso condicional con las funcionalidades de What If y modo de auditoría antes de asignar completamente la directiva de acceso condicional. Esto te ayuda a comprender los resultados de la directiva.
- Establece un período de gracia adaptado a la confidencialidad de los datos o la aplicación a la que se accede. 
- Asegúrate de que las directivas de cumplimiento no interfieren con los requisitos normativos o de cumplimiento. 
- Comprende los intervalos de registro de dispositivos para las directivas de cumplimiento.
- Evita conflictos entre las directivas de cumplimiento y los perfiles de configuración. Comprende los resultados, si lo deseas.

Para solucionar problemas de perfiles de dispositivo en Intune, incluidos los conflictos entre directivas, consulta [Preguntas y respuestas habituales sobre perfiles y directivas de dispositivos en Microsoft Intune](/mem/intune/configuration/device-profile-troubleshoot).

Nota: Si quieres empezar a requerir equipos compatibles, pero no dispositivos móviles, consulta [Requerir equipos compatibles (pero no teléfonos y tabletas)](../security/office-365-security/identity-access-policies.md) 

## <a name="next-steps"></a>Pasos siguientes

Ve al paso [5. Implementar perfiles de dispositivos en Microsoft Intune](manage-devices-with-intune-configuration-profiles.md)
