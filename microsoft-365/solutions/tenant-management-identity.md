---
title: Paso 3. Identidad de los inquilinos de Microsoft 365 para empresas
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
description: Implemente el modelo de identidad correcto para sus inquilinos de Microsoft 365 y aplique inicios de sesión de usuario sólidos.
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908688"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>Paso 3. Identidad de los inquilinos de Microsoft 365 para empresas

El inquilino de Microsoft 365 incluye un inquilino de Azure Active Directory (Azure AD) para administrar las identidades y la autenticación de los inicios de sesión. Configurar correctamente la infraestructura de identidades es fundamental para administrar los permisos y el acceso de usuarios de Microsoft 365 para su organización.

## <a name="cloud-only-vs-hybrid"></a>Solo nube frente a híbrida

Estos son los dos tipos de modelos de identidad y su mejor ajuste y ventajas.


| Model | Description | Cómo Autentica Microsoft 365 las credenciales de usuario | Ideal para | Mayor beneficio |
|:-------|:-----|:-----|:-----|:-----|
| Solo de nube | La cuenta de usuario solo existe en el inquilino de Azure AD para su inquilino de Microsoft 365. | El inquilino de Azure AD para su inquilino de Microsoft 365 realiza la autenticación con la cuenta de identidad de la nube. | Organizaciones que no tienen o necesitan un AD DS local. | Fácil de usar. No se necesitan más servidores ni herramientas de directorio. |
| Híbrido |  La cuenta de usuario existe en los Servicios de dominio de Active Directory (AD DS) locales y también hay una copia en el inquilino de Azure AD para el inquilino de Microsoft 365. Azure AD Connect se ejecuta en un servidor local para sincronizar los cambios de AD DS en el inquilino de Azure AD. La cuenta de usuario de Azure AD también puede incluir una versión con hash de la contraseña de la cuenta de usuario de AD DS ya con hash. | El inquilino de Azure AD para su inquilino de Microsoft 365 controla el proceso de autenticación o redirige al usuario a otro proveedor de identidades. | Organizaciones que usan AD DS u otro proveedor de identidades. | Los usuarios pueden usar las mismas credenciales al obtener acceso a recursos locales o basados en la nube. |
||||||

Estos son los componentes básicos de la identidad de solo nube.
 
![Componentes básicos de identidad solo en la nube](../media/about-microsoft-365-identity/cloud-only-identity.png)

En esta ilustración, los usuarios locales y remotos inician sesión con cuentas en el inquilino de Azure AD de su inquilino de Microsoft 365.

Estos son los componentes básicos de la identidad híbrida.

![Componentes básicos de la identidad híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

En esta ilustración, los usuarios locales y remotos inician sesión en su inquilino de Microsoft 365 con cuentas en el inquilino de Azure AD que se han copiado de su AD DS local.

## <a name="synchronizing-your-on-premises-ad-ds"></a>Sincronización de AD DS local

Según sus necesidades empresariales y requisitos técnicos, el modelo de identidad híbrido y la sincronización de directorios es la opción más común para los clientes empresariales que adoptan Microsoft 365. La sincronización de directorios le permite administrar identidades en su AD DS y todas las actualizaciones de cuentas de usuario, grupos y contactos se sincronizan con el inquilino de Azure AD de su inquilino de Microsoft 365.

>[!Note]
>Cuando las cuentas de usuario de AD DS se sincronizan por primera vez, no se les asigna automáticamente una licencia de Microsoft 365 y no pueden acceder a los servicios de Microsoft 365, como el correo electrónico. Primero debe asignarles una ubicación de uso. A continuación, asigna una licencia a estas cuentas de usuario, ya sea de forma individual o dinámica a través de la pertenencia a grupos.
>

Estos son los dos tipos de autenticación al usar el modelo de identidad híbrida.

| Tipo de autenticación | Description |
|:-------|:-----|
| Autenticación administrada | Azure AD controla el proceso de autenticación mediante una versión hash almacenada localmente de la contraseña o envía las credenciales a un agente de software local para que ad DS local los autentique. <br> <br>  Existen dos tipos de autenticación administrada: sincronización de hash de contraseña (PHS) y autenticación de paso a través (PTA). Con PHS, Azure AD realiza la autenticación en sí. Con la PTA, Azure AD tiene AD DS que realiza la autenticación. |
| Autenticación federada | Azure AD redirige el equipo cliente que solicita la autenticación a otro proveedor de identidades. |
|  |  |

Vea [cómo elegir el método de autenticación correcto](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.

## <a name="enforcing-strong-sign-ins"></a>Exigir inicios de sesión fuertes

Para aumentar la seguridad de los inicios de sesión de usuario, use las características y capacidades de la tabla siguiente.

| Funcionalidad | Descripción | Más información | Requisitos de licencia |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello para empresas | Reemplaza las contraseñas con autenticación segura en dos fases al iniciar sesión en un dispositivo Windows. Esta es un nueva forma de inicio de sesión que vincula el dispositivo de un usuario con un factor biométrico o un PIN. | [Introducción a Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 o E5 |
| Protección de contraseñas de Azure AD | Detecta y bloquea contraseñas no seguras conocidas y sus variantes y también puede bloquear términos débiles adicionales específicos de su organización. | [Configurar la protección con contraseña de Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 o E5 |
| Use la autenticación multifactor (MFA) | MFA requiere que los inicios de sesión del usuario se sometán a una comprobación adicional más allá de la contraseña de la cuenta de usuario, como la comprobación con una aplicación de smartphone o un mensaje de texto enviado a un smartphone. Vea [este vídeo para](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) obtener instrucciones sobre cómo los usuarios establecen MFA. | [MFA para Microsoft 365 para empresas](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 o E5 |
| Configuraciones de acceso a dispositivos e identidades | Configuración y directivas que constan de características de requisitos previos recomendadas y su configuración combinadas con las directivas de Acceso condicional, Intune y Azure AD Identity Protection que determinan si se debe conceder una solicitud de acceso determinada y en qué condiciones.  | [Configuraciones de acceso a dispositivos e identidades](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 o E5 |
| Azure AD Identity Protection | Protéjase contra el riesgo de credenciales, donde un atacante determina el nombre de cuenta y la contraseña de un usuario para obtener acceso a los datos y servicios en la nube de una organización. | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Microsoft 365 E5 o Microsoft 365 E3 con el complemento identity & Threat Protection |
|  |  |  |



## <a name="results-of-step-3"></a>Resultados del paso 3

Para la identidad de su inquilino de Microsoft 365, ha determinado:

- Qué modelo de identidad usar.
- Cómo exigirá el acceso seguro de usuarios y dispositivos.

Este es un ejemplo de un inquilino con los nuevos elementos de identidad híbrida resaltados.

![Ejemplo de identidad híbrida para un inquilino](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

En esta ilustración, el inquilino tiene:

- Un bosque de AD DS que se está sincronizando con el inquilino de Azure AD mediante un servidor de DirSync y Azure AD Connect.
- Una copia de las cuentas de usuario de AD DS y otros objetos del bosque de AD DS.
- Conjunto de directivas de acceso condicional para exigir el acceso y el inicio de sesión de usuario seguro en función de la cuenta de usuario. 

## <a name="ongoing-maintenance-for-identity"></a>Mantenimiento continuo de identidad

De forma continua, es posible que deba:

- Agregar o modificar grupos y cuentas de usuario. Para la identidad solo en la nube, se mantienen los usuarios y grupos basados en la nube con herramientas de Azure AD como el Centro de administración de Microsoft 365 o PowerShell. Para la identidad híbrida, se mantienen los usuarios y grupos locales con herramientas de AD DS.
- Agregue o modifique la configuración de acceso a dispositivos e identidades para aplicar los requisitos de seguridad de inicio de sesión.

## <a name="next-step"></a>Paso siguiente

[![Paso 4. Migrar los datos y servidores de Office locales](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

Continúe con [la migración](tenant-management-migration.md) para migrar los servidores de Office locales y sus datos a Microsoft 365.
