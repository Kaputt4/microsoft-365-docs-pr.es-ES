---
title: Guía básica de administración de dispositivos para Microsoft 365
keywords: Microsoft 365, Microsoft 365 para empresas, documentación de Microsoft 365, administración de dispositivos móviles, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: La guía básica para configurar la administración de dispositivos para Microsoft 365.
ms.openlocfilehash: bb19c38d5cf92cfc04ac83bc29573ea24c93ef30
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775176"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Guía básica de administración de dispositivos para Microsoft 365

Microsoft 365 para empresas incluye características que ayudan a administrar los dispositivos y sus aplicaciones dentro de su organización. La administración de dispositivos móviles le ayuda a proteger y proteger los recursos de la organización.

Hay dos opciones para la administración de dispositivos:

- [Microsoft Intune](#microsoft-intune)
- [Movilidad y seguridad básica](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Puede usar Microsoft Intune para administrar el acceso a su organización mediante la administración de dispositivos móviles o la administración de aplicaciones móviles. La administración de dispositivos móviles es cuando los usuarios "inscriben" sus dispositivos en Intune. Una vez inscrito un dispositivo, se trata de un dispositivo administrado; por lo tanto, puede recibir las directivas, reglas y opciones de configuración de su organización. Por ejemplo, puede instalar aplicaciones específicas, crear una directiva de contraseñas, instalar una conexión VPN, etc.

Es posible que los usuarios con sus propios dispositivos personales no deseen inscribir sus dispositivos o ser administrados por Intune y las directivas de su organización. Sin embargo, debe proteger los recursos y los datos de la organización. En este escenario, puede proteger sus aplicaciones con la administración de aplicaciones móviles. Por ejemplo, puede usar una directiva de administración de aplicaciones móviles que requiera que un usuario escriba un PIN al tener acceso a Microsoft SharePoint en el dispositivo.

También determinará cómo va a administrar los dispositivos personales y los dispositivos de propiedad de la organización. Es posible que quiera tratar los dispositivos de forma diferente, en función de sus usos.

Para administrar dispositivos con Intune, empiece [aquí](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).

## <a name="basic-mobility-and-security"></a>Movilidad y seguridad básica

Esto está integrado en Microsoft 365 y le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhone, iPad, Android y Windows Phone. Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.

Para administrar dispositivos con la seguridad y la movilidad básicos, empiece [aquí](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).
 
## <a name="identity-and-device-access-recommendations"></a>Recomendaciones de acceso a dispositivos e identidades

Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados. Para el acceso a los dispositivos, use las recomendaciones y la configuración de estos artículos:

- [Requisitos previos](identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Cómo contoso realizó la administración de dispositivos para Microsoft 365

Para obtener información sobre cómo una empresa multinacional ficticia pero representativa ha implementado la infraestructura de administración de dispositivos móviles con los servicios en la nube de Microsoft 365, vea [Mobile Device Management for contoso](contoso-mdm.md).
