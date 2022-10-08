---
title: Guía básica de administración de dispositivos para Microsoft 365
keywords: Microsoft 365, Microsoft 365 para empresas, documentación de Microsoft 365, administración de dispositivos móviles, Intune
author: kelleyvice-msft
ms.author: kvice
manager: scotv
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.service: microsoft-365-enterprise
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.collection: scotvorg
description: La hoja de ruta para configurar la administración de dispositivos para Microsoft 365.
ms.openlocfilehash: 2b4c67df00c3dc9675da9d24d55628abf3883173
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68185631"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Guía básica de administración de dispositivos para Microsoft 365

Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y sus aplicaciones dentro de la organización. La administración de dispositivos móviles le ayuda a proteger y proteger los recursos de su organización.

Hay dos opciones para la administración de dispositivos:

- [Microsoft Intune](#microsoft-intune)
- [Movilidad y seguridad básicas](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Puede usar Microsoft Intune para administrar el acceso a su organización mediante la administración de dispositivos móviles o la administración de aplicaciones móviles. La administración de dispositivos móviles es cuando los usuarios "inscriben" sus dispositivos en Intune. Después de inscribir un dispositivo, es un dispositivo administrado; por lo tanto, puede recibir las directivas, las reglas y la configuración de la organización. Por ejemplo, puede instalar aplicaciones específicas, crear una directiva de contraseñas, instalar una conexión VPN y mucho más.

Es posible que los usuarios con sus propios dispositivos personales no quieran inscribir sus dispositivos o que estén administrados por Intune y las directivas de su organización. Pero todavía tiene que proteger los recursos y los datos de su organización. En este escenario, puede proteger las aplicaciones mediante la administración de aplicaciones móviles. Por ejemplo, puede usar una directiva de administración de aplicaciones móviles que requiera que un usuario escriba un PIN al acceder a SharePoint Online en el dispositivo.

También determinará cómo va a administrar los dispositivos personales y los dispositivos propiedad de la organización. Es posible que quiera tratar los dispositivos de forma diferente, en función de sus usos.

## <a name="basic-mobility-and-security"></a>Movilidad y seguridad básicas

Esto está integrado en Microsoft 365 y le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhones, iPads, Android y teléfonos Windows. Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.

## <a name="choose-between-the-two-options"></a>Elegir entre las dos opciones

Para ayudarle a evaluar mejor qué opción de administración de dispositivos es mejor para usted, consulte [Elegir entre Basic Mobility Security y Intune](/office365/securitycompliance/choose-between-mdm-and-intune).

En función de la evaluación, empiece a administrar los dispositivos con:

- [Intune](/microsoft-365/solutions/manage-devices-with-intune-overview)
- [Movilidad y seguridad básicas](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>Recomendaciones de acceso a dispositivos e identidades

Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados. Para el acceso a dispositivos, use las recomendaciones y la configuración de estos artículos:

- [Requisitos previos](../security/office-365-security/identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Cómo contoso hizo la administración de dispositivos para Microsoft 365

Para obtener información sobre cómo una empresa multinacional ficticia pero representativa implementó su infraestructura de administración de dispositivos móviles con los servicios en la nube de Microsoft 365, consulte [Administración de dispositivos móviles para Contoso](contoso-mdm.md).