---
title: Guía básica de administración de dispositivos para Microsoft 365
keywords: Microsoft 365, Microsoft 365 para empresas, documentación Microsoft 365, administración de dispositivos móviles, Intune
author: kelleyvice-msft
ms.author: kvice
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
description: Guía básica para configurar la administración de dispositivos para Microsoft 365.
ms.openlocfilehash: 0fef31697657b4694090ae7a1b63516920d8c71b
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61933352"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Guía básica de administración de dispositivos para Microsoft 365

Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y sus aplicaciones en su organización. La administración de dispositivos móviles le ayuda a proteger y proteger los recursos de su organización.

Hay dos opciones para la administración de dispositivos:

- [Microsoft Intune](#microsoft-intune)
- [Movilidad y seguridad básicas](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Puedes usar Microsoft Intune para administrar el acceso a tu organización mediante la administración de dispositivos móviles o la administración de aplicaciones móviles. La administración de dispositivos móviles es cuando los usuarios "inscriben" sus dispositivos en Intune. Después de inscribir un dispositivo, es un dispositivo administrado; por lo tanto, puede recibir las directivas, reglas y configuración de la organización. Por ejemplo, puedes instalar aplicaciones específicas, crear una directiva de contraseña, instalar una conexión VPN y mucho más.

Es posible que los usuarios con sus propios dispositivos personales no quieran inscribir sus dispositivos o que Intune y las directivas de su organización lo administren. Pero aún necesita proteger los recursos y los datos de su organización. En este escenario, puedes proteger tus aplicaciones mediante la administración de aplicaciones móviles. Por ejemplo, puedes usar una directiva de administración de aplicaciones móviles que requiere que un usuario escriba un PIN al acceder a SharePoint Online en el dispositivo.

También determinarás cómo vas a administrar dispositivos personales y dispositivos propiedad de la organización. Es posible que quieras tratar los dispositivos de forma diferente, según sus usos.

## <a name="basic-mobility-and-security"></a>Movilidad y seguridad básicas

Esto está integrado en Microsoft 365 y le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhones, iPads, Androides y Windows teléfonos. Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.

## <a name="choose-between-the-two-options"></a>Elegir entre las dos opciones

Para ayudarte a evaluar mejor la opción de administración de dispositivos que mejor te conste, consulta Elegir entre Seguridad básica de [movilidad e Intune.](/office365/securitycompliance/choose-between-mdm-and-intune)

En función de tu evaluación, empieza a administrar tus dispositivos con:

- [Intune](/microsoft-365/solutions/manage-devices-with-intune-overview)
- [Movilidad y seguridad básicas](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>Recomendaciones de acceso a dispositivos e identidades

Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados. Para el acceso a dispositivos, usa las recomendaciones y la configuración de estos artículos:

- [Requisitos previos](../security/office-365-security/identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Cómo Contoso hizo la administración de dispositivos Microsoft 365

Para obtener información sobre cómo una empresa multinacionales ficticia pero representativa implementó su infraestructura de administración de dispositivos móviles con Microsoft 365 en la nube, consulte Administración de dispositivos [móviles para Contoso](contoso-mdm.md).