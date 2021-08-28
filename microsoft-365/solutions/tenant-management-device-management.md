---
title: Paso 5. Administración de dispositivos y aplicaciones para Microsoft 365 para inquilinos empresariales
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implemente la opción correcta para la administración de dispositivos y aplicaciones para Microsoft 365 inquilinos.
ms.openlocfilehash: 1d96042f2733a69919fd0dbaa9f30be6835d6469
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58571198"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Paso 5. Administración de dispositivos y aplicaciones para Microsoft 365 para inquilinos empresariales

Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y el uso de aplicaciones en esos dispositivos dentro de la organización con administración de dispositivos móviles (MDM) y administración de aplicaciones móviles (MAM). Puedes administrar dispositivos iOS, Android, macOS y Windows para proteger el acceso a los recursos de la organización, incluidos los datos. Por ejemplo, puede impedir que los correos electrónicos se envíen a personas de fuera de la organización o aislar los datos de la organización de datos personales en los dispositivos personales del trabajador.

Este es un ejemplo de validación y administración de los usuarios, sus dispositivos y el uso de aplicaciones de productividad locales y en la nube como Microsoft Teams.

![Validación y administración de usuarios, dispositivos y aplicaciones.](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Para ayudarle a proteger y proteger los recursos de su organización, Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y su acceso a aplicaciones. Hay dos opciones para la administración de dispositivos:

- Microsoft Intune, que es una solución completa de administración de dispositivos y aplicaciones para empresas.
- Movilidad y seguridad básicas, que es un subconjunto de servicios de Intune incluidos con todos los Microsoft 365 para administrar dispositivos de la organización. Para obtener más información, vea [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).

Si tiene Microsoft 365 E3 O E5, debe usar Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

Usas [Microsoft Intune](/mem/intune/fundamentals/planning-guide) para administrar el acceso a tu organización con MDM o MAM. MDM es cuando los usuarios "inscriben" sus dispositivos en Intune. Después de inscribir un dispositivo, es un dispositivo administrado y puede recibir las directivas, reglas y configuración de la organización. Por ejemplo, puedes instalar aplicaciones específicas, crear una directiva de contraseña, instalar una conexión VPN y mucho más.

Es posible que los usuarios con sus propios dispositivos personales no quieran inscribir sus dispositivos o que Intune y las directivas de su organización lo administren. Pero aún necesita proteger los recursos y los datos de su organización. En este escenario, puedes proteger tus aplicaciones con MAM. Por ejemplo, puedes usar una directiva MAM que requiere que un usuario escriba un PIN al acceder a SharePoint en el dispositivo.

También determinarás cómo vas a administrar dispositivos personales y dispositivos propiedad de la organización. Es posible que quieras tratar los dispositivos de forma diferente, según sus usos.

## <a name="identity-and-device-access-configurations"></a>Configuraciones de acceso a dispositivos e identidades

Microsoft proporciona un conjunto de configuraciones para el acceso a identidades y [dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) para garantizar un personal seguro y productivo. Estas configuraciones incluyen el uso de:

- Directivas de acceso condicional de Azure AD
- Microsoft Intune de cumplimiento de dispositivos y protección de aplicaciones
- Directivas de riesgo de usuario de Azure AD Identity Protection
- Directivas adicionales de aplicaciones en la nube

Este es un ejemplo de la aplicación de estas directivas y configuraciones para validar y restringir a los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube, como Microsoft Teams.

![Configuraciones de acceso de identidad y dispositivo para requisitos y restricciones en los usuarios, sus dispositivos y el uso de aplicaciones.](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Para el acceso a dispositivos y la administración de aplicaciones, usa las configuraciones de estos artículos:

- [Requisitos previos](../security/office-365-security/identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Resultados del paso 5

Para la administración de dispositivos y aplicaciones para su inquilino de Microsoft 365, ha determinado la configuración y las directivas de Intune para validar y restringir los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube.

Este es un ejemplo de un inquilino con la administración de dispositivos y aplicaciones de Intune con los nuevos elementos resaltados.

![Ejemplo de inquilino con administración de dispositivos y aplicaciones de Intune.](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

En esta ilustración, el inquilino tiene:

- Dispositivos propiedad de la organización inscritos en Intune.
- Directivas de dispositivos y aplicaciones de Intune para dispositivos inscritos y personales.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Mantenimiento continuo para la administración de dispositivos y aplicaciones

De forma continua, es posible que deba: 

- Administrar la inscripción de dispositivos.
- Revise la configuración y las directivas para obtener más aplicaciones, dispositivos y requisitos de seguridad.