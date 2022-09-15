---
title: Paso 3. Configurar directivas de cumplimiento para dispositivos con Intune
ms.author: bcarter
author: brendacarter
f1.keywords:
- Create compliance policies
- Intune device compliance policy
manager: dougeby
audience: ITPro
description: Aprenda a crear directivas de cumplimiento de dispositivos que especifiquen los requisitos mínimos para que un dispositivo acceda a su entorno.
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
keywords: ''
ms.openlocfilehash: 68375d7992df0daee91bf1fb1be87e17529b34d9
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730910"
---
# <a name="step-3-set-up-compliance-policies-for-devices-with-intune"></a>Paso 3. Configurar directivas de cumplimiento para dispositivos con Intune

La inscripción de dispositivos en Intune le ofrece la posibilidad de lograr una mayor seguridad y control de los datos en su entorno. [Paso 2. Inscribir dispositivos en Intune](manage-devices-with-intune-enroll.md) detalla cómo hacerlo mediante Intune. En este artículo se describe el paso siguiente, que consiste en configurar directivas de cumplimiento de dispositivos. 

![Pasos para administrar dispositivos](../media/devices/intune-mdm-step-2.png#lightbox)

Debes asegurarte de que los dispositivos que acceden a las aplicaciones y los datos cumplen los requisitos mínimos; por ejemplo, están protegidos con código PIN o contraseña, y el sistema operativo está actualizado. Las directivas de cumplimiento son la manera de definir los requisitos que los dispositivos deben cumplir. MEM usa estas directivas de cumplimiento para marcar un dispositivo como compatible o no compatible. Este estado binario se pasa a Azure AD que puede usar este estado en reglas de acceso condicional para permitir o impedir que un dispositivo acceda a los recursos. 

## <a name="configuring-device-compliance-policies"></a>Configurando las directivas de cumplimiento de dispositivos

Esta guía está estrechamente coordinada con las [directivas de acceso de dispositivos e identidad de Confianza cero](../security/office-365-security/microsoft-365-policies-configurations.md).

Esta ilustración destaca dónde encaja el trabajo de definir políticas de cumplimiento en el conjunto general de políticas recomendadas de Confianza cero. 

[![Directivas de acceso de dispositivos e identidad de Confianza cero](../media/devices/identity-device-define-compliance.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-define-compliance.png)

En esta ilustración, la definición de directivas de cumplimiento de dispositivos es una dependencia para lograr el nivel recomendado de protección dentro del marco de Confianza cero. 

Para configurar las directivas de cumplimiento de dispositivos, utilice la guía y la configuración recomendadas prescritas en las [políticas de acceso a dispositivos e identidad de Confianza cero](../security/office-365-security/microsoft-365-policies-configurations.md). La tabla siguiente se vincula directamente a las instrucciones para configurar estas directivas en Intune, incluidas las opciones recomendadas para cada plataforma.


|Directivas |Más información  |Licencias |
|---------|---------|---------|
|[Definir directivas de cumplimiento de dispositivos ](../security/office-365-security/identity-access-policies.md#define-device-compliance-policies)   |  Una directiva para cada plataforma       |  Microsoft 365 E3 o E5       |
|  |         |         |

## <a name="next-steps"></a>Pasos siguientes

Vaya al [Paso 4. Requerir dispositivos correctos y compatibles](manage-devices-with-intune-require-compliance.md) para obtener instrucciones sobre cómo crear la regla de acceso condicional en Azure AD.