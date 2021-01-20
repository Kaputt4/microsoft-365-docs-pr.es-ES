---
title: Paso 5. Administración de dispositivos y aplicaciones para los inquilinos de Microsoft 365 para empresas
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
ms.custom:
- Ent_Solutions
description: Implemente la opción correcta para la administración de dispositivos y aplicaciones para sus inquilinos de Microsoft 365.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908712"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Paso 5. Administración de dispositivos y aplicaciones para los inquilinos de Microsoft 365 para empresas

Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y el uso de aplicaciones en esos dispositivos dentro de la organización con la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Puedes administrar dispositivos iOS, Android, macOS y Windows para proteger el acceso a los recursos de la organización, incluidos los datos. Por ejemplo, puede evitar que se envíen correos electrónicos a personas ajenas a la organización o aislar los datos de la organización de datos personales en los dispositivos personales de su trabajador.

Este es un ejemplo de la validación y administración de los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube, como Microsoft Teams.

![Validación y administración de usuarios, dispositivos y aplicaciones](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Para ayudarle a proteger y proteger los recursos de su organización, Microsoft 365 para empresas incluye características para ayudar a administrar los dispositivos y su acceso a las aplicaciones. Existen dos opciones para la administración de dispositivos:

- Microsoft Intune, que es una solución completa de administración de dispositivos y aplicaciones para empresas.
- Movilidad y seguridad básicas, que es un subconjunto de servicios de Intune incluidos con todos los productos de Microsoft 365 para administrar dispositivos en su organización. Para obtener más información, vea [Funcionalidades de movilidad y seguridad básicas.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)

Si tiene Microsoft 365 E3 o E5, debe usar Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

Usas [Microsoft Intune para](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) administrar el acceso a tu organización mediante MDM o MAM. MDM es cuando los usuarios "inscriben" sus dispositivos en Intune. Después de inscribir un dispositivo, es un dispositivo administrado y puede recibir las directivas, reglas y configuración de la organización. Por ejemplo, puedes instalar aplicaciones específicas, crear una directiva de contraseña, instalar una conexión VPN y mucho más.

Es posible que los usuarios con sus propios dispositivos personales no quieran inscribir sus dispositivos o que Intune y las directivas de la organización los administren. Pero aún necesita proteger los recursos y los datos de su organización. En este escenario, puedes proteger tus aplicaciones mediante MAM. Por ejemplo, puede usar una directiva MAM que requiera que un usuario escriba un PIN al acceder a SharePoint en el dispositivo.

También determinará cómo va a administrar los dispositivos personales y los dispositivos propiedad de la organización. Es posible que quieras tratar los dispositivos de forma diferente, en función de sus usos.

## <a name="identity-and-device-access-configurations"></a>Configuraciones de acceso a dispositivos e identidades

Microsoft proporciona un conjunto de configuraciones para el acceso a dispositivos e [identidades](../security/office-365-security/microsoft-365-policies-configurations.md) para garantizar un personal seguro y productivo. Estas configuraciones incluyen el uso de:

- Directivas de acceso condicional de Azure AD
- Directivas de cumplimiento de dispositivos y protección de aplicaciones de Microsoft Intune
- Directivas de riesgo de usuario de Azure AD Identity Protection
- Directivas adicionales de aplicaciones en la nube

Este es un ejemplo de la aplicación de estas configuraciones y directivas para validar y restringir usuarios, sus dispositivos y el uso de aplicaciones de productividad locales y en la nube, como Microsoft Teams.

![Configuraciones de acceso a dispositivos e identidades para requisitos y restricciones en los usuarios, sus dispositivos y el uso de aplicaciones](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Para el acceso a dispositivos y la administración de aplicaciones, usa las configuraciones de estos artículos:

- [Requisitos previos](../security/office-365-security/identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Resultados del paso 5

Para la administración de dispositivos y aplicaciones para su inquilino de Microsoft 365, ha determinado la configuración y las directivas de Intune para validar y restringir a los usuarios, sus dispositivos y el uso de aplicaciones de productividad locales y en la nube.

Este es un ejemplo de un inquilino con la administración de dispositivos y aplicaciones de Intune con los nuevos elementos resaltados.

![Ejemplo de un inquilino con administración de dispositivos y aplicaciones de Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

En esta ilustración, el inquilino tiene:

- Dispositivos propiedad de la organización inscritos en Intune.
- Directivas de dispositivos y aplicaciones de Intune para dispositivos inscritos y personales.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Mantenimiento continuo para la administración de dispositivos y aplicaciones

De forma continua, es posible que deba: 

- Administrar la inscripción de dispositivos.
- Revise la configuración y las directivas para obtener más aplicaciones, dispositivos y requisitos de seguridad.
