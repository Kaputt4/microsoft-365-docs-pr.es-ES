---
title: Paso 1. Implementar directivas de protección de aplicaciones de nivel 2
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
ms.openlocfilehash: ea39a9b37c3f618bc9497b21e7a926d55456c2c5
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2021
ms.locfileid: "61129294"
---
# <a name="step-1-implement-level-2-app-protection-policies"></a>Paso 1. Implementar directivas de protección de aplicaciones de nivel 2

Las directivas de Protección de aplicaciones (APP) de Intune, a veces denominadas Administración de aplicaciones móviles (MAM), protegen los datos corporativos incluso si no se administra un dispositivo en sí. Esto te permite habilitar dispositivos personales y bring-your-own (BYO) en el trabajo donde los usuarios pueden ser reacios a "inscribir" su dispositivo en la administración. Las directivas de Protección de aplicaciones garantizan que los datos corporativos de las aplicaciones que especifiques no se puedan copiar y pegar en otras aplicaciones del dispositivo.

![Pasos para crear directivas de protección de aplicaciones](../media/devices/intune-app-steps.png#lightbox)

En esta ilustración:
- Con APP, Intune crea un muro entre los datos de la organización y los datos personales. Las directivas de protección de aplicaciones definen qué aplicaciones se usan para acceder a la organización.
- Si un usuario inicia sesión con sus credenciales de la organización, Intune aplica una directiva en el nivel de aplicación para evitar copiar y pegar datos de la organización en aplicaciones personales y para requerir acceso pin a estos datos.
- Después de crear una directiva de Protección de aplicaciones, se aplica la protección de datos con una directiva de acceso condicional. 

Esta configuración aumenta en gran medida la posición de seguridad sin casi ningún impacto en la experiencia del usuario.  Los empleados pueden usar aplicaciones como Office y Microsoft Teams, que conocen y aman, al mismo tiempo que su organización puede proteger los datos contenidos en las aplicaciones y dispositivos.

Si tienes aplicaciones personalizadas de línea de negocio que necesitan protección, actualmente puedes usar la herramienta de ajuste de aplicaciones para habilitar MAM con estas aplicaciones. O bien, puede integrar con intune App SDK. Cuando tu aplicación tiene directivas de protección de aplicaciones aplicadas, Intune la puede administrar y Intune la reconoce como una aplicación administrada. Para obtener más información sobre cómo proteger las aplicaciones de línea de negocio con Intune, consulte [Preparar las aplicaciones para la administración de aplicaciones móviles con Microsoft Intune](/mem/intune/developer/apps-prepare-mobile-application-management).

## <a name="configuring-mobile-app-protection"></a>Configurando la protección de aplicaciones móviles

Esta guía está estrechamente coordinada con las [directivas de acceso de dispositivos e identidad de Confianza cero](../security/office-365-security/microsoft-365-policies-configurations.md). Después de crear las directivas de protección de aplicaciones móviles en Intune, trabaje con el equipo de identidades para configurar las directivas de acceso condicional en Azure AD que aplica la protección de aplicaciones móviles. 

En esta ilustración se resaltan las dos directivas (también descritas en la tabla debajo de la ilustración).

[![Directivas de acceso de dispositivos e identidad de Confianza cero](../media/devices/identity-device-starting-point.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-starting-point.png)

Para configurar estas directivas, use las instrucciones recomendadas y las opciones de configuración indicadas en [Políticas de acceso a dispositivos e identidad de Confianza cero](../security/office-365-security/microsoft-365-policies-configurations.md). La tabla siguiente se vincula directamente a las instrucciones para configurar estas directivas en Intune y Azure AD.


|Paso  |Directivas  |Más información  |Licencias  |
|---------|---------|---------|---------|
|1   |  [Aplicar protección de datos de directivas de protección de aplicaciones (APP)](../security/office-365-security/identity-access-policies.md#apply-app-data-protection-policies)       | Una directiva de Protección de aplicaciones de Intune por plataforma (Windows, iOS/iPadOS, Android).        | Microsoft 365 E3 o E5        |
|2     | [Requerir aplicaciones aprobadas y protección de aplicaciones ](../security/office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)       |  Aplica la protección de aplicaciones móviles para teléfonos y tabletas con iOS, iPadOS o Android.   |  Microsoft 365 E3 o E5       |
| | | | |

## <a name="next-steps"></a>Pasos siguientes

Vaya al [Paso 2. Inscribir dispositivos en la administración con Intune](manage-devices-with-intune-enroll.md). 