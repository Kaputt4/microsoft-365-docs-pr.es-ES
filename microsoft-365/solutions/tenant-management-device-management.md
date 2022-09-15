---
title: Paso 5. Administración de dispositivos y aplicaciones para los inquilinos de Microsoft 365 para empresas
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implemente la opción correcta para la administración de dispositivos y aplicaciones para los inquilinos de Microsoft 365.
ms.openlocfilehash: 5650c4e11258c621a420927a73aaba380802b07e
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730251"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Paso 5. Administración de dispositivos y aplicaciones para los inquilinos de Microsoft 365 para empresas

Microsoft 365 para empresas incluye características para ayudar a administrar dispositivos y el uso de aplicaciones en esos dispositivos dentro de su organización con la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Puede administrar dispositivos iOS, Android, macOS y Windows para proteger el acceso a los recursos de su organización, incluidos los datos. Por ejemplo, puede evitar que los correos electrónicos se envíen a personas ajenas a su organización o aislar los datos de la organización de los datos personales en los dispositivos personales del trabajador.

Este es un ejemplo de la validación y administración de los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube, como Microsoft Teams.

![Validación y administración de usuarios, dispositivos y aplicaciones.](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Para ayudarle a proteger y proteger los recursos de su organización, Microsoft 365 para empresas incluye características para ayudar a administrar los dispositivos y su acceso a las aplicaciones. Hay dos opciones para la administración de dispositivos:

- Microsoft Intune, que es una solución completa de administración de dispositivos y aplicaciones para empresas.
- Basic Mobility and Security, que es un subconjunto de Intune servicios incluidos con todos los productos de Microsoft 365 para administrar dispositivos en su organización. Para obtener más información, consulte [Funcionalidades de movilidad y seguridad básicas](../admin/basic-mobility-security/capabilities.md).

Si tiene Microsoft 365 E3 o E5, debe usar Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

Use [Microsoft Intune](/mem/intune/fundamentals/planning-guide) para administrar el acceso a su organización mediante MDM o MAM. MDM es cuando los usuarios "inscriben" sus dispositivos en Intune. Una vez inscrito un dispositivo, es un dispositivo administrado y puede recibir las directivas, las reglas y la configuración de la organización. Por ejemplo, puede instalar aplicaciones específicas, crear una directiva de contraseñas, instalar una conexión VPN y mucho más.

Es posible que los usuarios con sus propios dispositivos personales no quieran inscribir sus dispositivos o que estén administrados por Intune y las directivas de su organización. Pero todavía tiene que proteger los recursos y los datos de su organización. En este escenario, puede proteger las aplicaciones mediante MAM. Por ejemplo, puede usar una directiva MAM que requiera que un usuario escriba un PIN al acceder a SharePoint en el dispositivo.

También determinará cómo va a administrar los dispositivos personales y los dispositivos propiedad de la organización. Es posible que quiera tratar los dispositivos de forma diferente, en función de sus usos.

## <a name="identity-and-device-access-configurations"></a>Configuraciones de acceso a dispositivos e identidades

Microsoft proporciona un conjunto de configuraciones para el [acceso a identidades y dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) con el fin de garantizar un personal seguro y productivo. Estas configuraciones incluyen el uso de:

- Directivas de acceso condicional de Azure AD
- Microsoft Intune directivas de cumplimiento de dispositivos y protección de aplicaciones
- Directivas de riesgo de usuario de Azure AD Identity Protection
- Directivas adicionales de aplicaciones en la nube

Este es un ejemplo de la aplicación de estas directivas y configuración para validar y restringir a los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube como Microsoft Teams.

![Configuraciones de acceso de identidad y dispositivo para requisitos y restricciones en los usuarios, sus dispositivos y su uso de aplicaciones.](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Para el acceso a dispositivos y la administración de aplicaciones, use las configuraciones de estos artículos:

- [Requisitos previos](../security/office-365-security/identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Resultados del paso 5

En el caso de la administración de dispositivos y aplicaciones para el inquilino de Microsoft 365, ha determinado la configuración de Intune y las directivas para validar y restringir a los usuarios, sus dispositivos y su uso de aplicaciones de productividad locales y en la nube.

Este es un ejemplo de un inquilino con Intune administración de dispositivos y aplicaciones con los nuevos elementos resaltados.

![Ejemplo de un inquilino con Intune administración de dispositivos y aplicaciones.](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

En esta ilustración, el inquilino tiene:

- Dispositivos propiedad de la organización inscritos en Intune.
- Intune directivas de dispositivos y aplicaciones para dispositivos inscritos y personales.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Mantenimiento continuo de la administración de dispositivos y aplicaciones

De forma continua, es posible que tenga que: 

- Administrar la inscripción de dispositivos.
- Revise la configuración y las directivas de aplicaciones, dispositivos y requisitos de seguridad adicionales.
