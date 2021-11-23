---
title: Paso 3. Configurar directivas de cumplimiento para dispositivos con Intune
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: 0421a369964b30b767407cd99dba787edaff0e89
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2021
ms.locfileid: "61129486"
---
# <a name="step-3-set-up-compliance-policies-for-devices-with-intune"></a>Paso 3. Configurar directivas de cumplimiento para dispositivos con Intune

La inscripción de dispositivos en la administración le ofrece la capacidad de lograr una mayor seguridad y control de los datos en su entorno. [Paso 2. Inscriba los dispositivos en los detalles de administración](manage-devices-with-intune-enroll.md) sobre cómo lograr esto mediante Intune y Autopilot. En este artículo se describe el paso siguiente, que consiste en configurar directivas de cumplimiento de dispositivos. 

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