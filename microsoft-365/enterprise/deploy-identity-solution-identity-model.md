---
title: Paso 1. Determinación del modelo de identidad en la nube
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
- m365solution-m365-identity
- m365solution-scenario
- zerotrust-solution
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Paso 1. Determinación del modelo de identidad en la nube de Microsoft
ms.openlocfilehash: a2e5d57d353527061a08d3bb6b116f3c52be3753
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "66749185"
---
# <a name="step-1-determine-your-cloud-identity-model"></a>Paso 1. Determinación del modelo de identidad en la nube

Microsoft 365 usa Azure Active Directory (Azure AD), un servicio de autenticación e identidad de usuario basado en la nube que se incluye con su suscripción de Microsoft 365, para administrar identidades y autenticación para Microsoft 365. La configuración correcta de la infraestructura de identidad es fundamental para administrar el acceso de usuarios y los permisos de Microsoft 365 para su organización.

Antes de empezar, vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

La primera opción de planeamiento es el modelo de identidad en la nube.

## <a name="microsoft-cloud-identity-models"></a>Modelos de identidad en la nube de Microsoft

Para planear las cuentas de usuario, primero debe comprender los dos modelos de identidad de Microsoft 365. Puede mantener las identidades de su organización solo en la nube, o bien puede mantener las identidades de Active Directory local Domain Services (AD DS) y usarlas para la autenticación cuando los usuarios acceden a los servicios en la nube de Microsoft 365.

Estos son los dos tipos de identidad y su mejor ajuste y ventajas.

| Atributo | Identidad solo de nube | Identidad híbrida |
|:-------|:-----|:-----|
| **Definición** | La cuenta de usuario solo existe en el inquilino de Azure AD para la suscripción de Microsoft 365. | La cuenta de usuario existe en AD DS y también hay una copia en el inquilino de Azure AD para la suscripción de Microsoft 365. La cuenta de usuario de Azure AD también puede incluir una versión con hash de la contraseña de la cuenta de usuario de AD DS ya con hash. |
| **Cómo Microsoft 365 autentica las credenciales de usuario** | El inquilino de Azure AD para la suscripción de Microsoft 365 realiza la autenticación con la cuenta de identidad en la nube. | El inquilino de Azure AD para la suscripción de Microsoft 365 controla el proceso de autenticación o redirige al usuario a otro proveedor de identidades. |
| **Ideal para** | Organizaciones que no tienen o necesitan un AD DS local. | Organizaciones que usan AD DS u otro proveedor de identidades. |
| **Principales ventajas** | Fácil de usar. No se requieren herramientas de directorio ni servidores adicionales. | Los usuarios pueden usar las mismas credenciales al acceder a recursos locales o basados en la nube. |
||||

## <a name="cloud-only-identity"></a>Identidad solo de nube

Una identidad solo en la nube usa cuentas de usuario que solo existen en Azure AD. La identidad solo en la nube se usa normalmente en organizaciones pequeñas que no tienen servidores locales o no usan AD DS para administrar identidades locales.

Estos son los componentes básicos de la identidad solo en la nube.

![Componentes básicos de la identidad solo en la nube.](../media/about-microsoft-365-identity/cloud-only-identity.png)

Los usuarios locales y remotos (en línea) usan sus cuentas de usuario y contraseñas de Azure AD para acceder a los servicios en la nube de Microsoft 365. Azure AD autentica las credenciales de usuario en función de sus cuentas de usuario y contraseñas almacenadas.

### <a name="administration"></a>Administración
Dado que las cuentas de usuario solo se almacenan en Azure AD, se administran identidades [en la nube](/admin) con herramientas como Centro de administración de Microsoft 365 y [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).

## <a name="hybrid-identity"></a>Identidad híbrida

La identidad híbrida usa cuentas que se originan en un AD DS local y tienen una copia en el inquilino de Azure AD de una suscripción de Microsoft 365. La mayoría de los cambios, con la excepción de [atributos de cuenta específicos](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized), solo fluyen de una manera. Los cambios realizados en las cuentas de usuario de AD DS se sincronizan con su copia en Azure AD.

Azure AD Connect proporciona la sincronización de cuentas en curso. Se ejecuta en un servidor local, comprueba si hay cambios en AD DS y reenvía esos cambios a Azure AD. Azure AD Connect proporciona la capacidad de filtrar qué cuentas se sincronizan y si se sincroniza una versión con hash de contraseñas de usuario, conocida como sincronización de hash de contraseñas (PHS).

Al implementar la identidad híbrida, su AD DS local es el origen autoritativo para la información de la cuenta. Esto significa que realiza tareas de administración principalmente locales, que luego se sincronizan con Azure AD.

Estos son los componentes de la identidad híbrida.

![Componentes de la identidad híbrida.](../media/about-microsoft-365-identity/hybrid-identity.png)

El inquilino de Azure AD tiene una copia de las cuentas de AD DS. En esta configuración, los usuarios locales y remotos que acceden a los servicios en la nube de Microsoft 365 se autentican en Azure AD.

> [!NOTE]
> Siempre debe usar Azure AD Connect para sincronizar cuentas de usuario para la identidad híbrida. Necesita las cuentas de usuario sincronizadas de Azure AD para realizar la asignación de licencias y la administración de grupos, configurar permisos y otras tareas administrativas que impliquen cuentas de usuario.

### <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Sincronización de identidades híbridas y directorios para Microsoft 365

En función de las necesidades empresariales y los requisitos técnicos, el modelo de identidad híbrida y la sincronización de directorios son la opción más común para los clientes empresariales que adoptan Microsoft 365. La sincronización de directorios permite administrar identidades en el Servicios de dominio de Active Directory (AD DS) y todas las actualizaciones de cuentas de usuario, grupos y contactos se sincronizan con el inquilino de Azure Active Directory (Azure AD) de la suscripción de Microsoft 365.

>[!Note]
>Cuando las cuentas de usuario de AD DS se sincronizan por primera vez, no se les asigna automáticamente una licencia de Microsoft 365 y no pueden acceder a los servicios de Microsoft 365, como el correo electrónico. Primero debe asignarles una ubicación de uso. A continuación, asigne una licencia a estas cuentas de usuario, ya sea de forma individual o dinámica a través de la suscripción a grupos.
>

#### <a name="authentication-for-hybrid-identity"></a>Autenticación para la identidad híbrida

Hay dos tipos de autenticación al usar el modelo de identidad híbrida:

- Autenticación administrada

  Azure AD controla el proceso de autenticación mediante una versión con hash almacenada localmente de la contraseña o envía las credenciales a un agente de software local para que lo autentique AD DS local.

- Autenticación federada

  Azure AD redirige el equipo cliente que solicita autenticación a otro proveedor de identidades.

#### <a name="managed-authentication"></a>Autenticación administrada

Hay dos tipos de autenticación administrada:

- Sincronización del hash de la contraseña (PHS)

  Azure AD realiza la autenticación en sí.

- Autenticación de paso a través (PTA)

  Azure AD hace que AD DS realice la autenticación.


##### <a name="password-hash-synchronization-phs"></a>Sincronización del hash de la contraseña (PHS)

Con PHS, sincroniza las cuentas de usuario de AD DS con Microsoft 365 y administra los usuarios locales. Los hashes de contraseñas de usuario se sincronizan entre AD DS y Azure AD para que los usuarios tengan la misma contraseña en el entorno local y en la nube. Esta es la manera más sencilla de habilitar la autenticación para identidades de AD DS en Azure AD. 

![Sincronización de hash de contraseña (PHS).](../media/plan-for-directory-synchronization/phs-authentication.png)

Cuando las contraseñas se cambian o restablecen localmente, los nuevos hashes de contraseña se sincronizan con Azure AD para que los usuarios puedan usar siempre la misma contraseña para los recursos en la nube y los recursos locales. Las contraseñas de usuario nunca se envían a Azure AD ni se almacenan en Azure AD en texto no cifrado. Algunas características premium de Azure AD, como Identity Protection, requieren PHS independientemente del método de autenticación seleccionado.
  
Consulte [Elección del método de autenticación adecuado](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.
  
##### <a name="pass-through-authentication-pta"></a>Autenticación de paso a través (PTA)

PTA proporciona una validación de contraseña sencilla para los servicios de autenticación de Azure AD mediante un agente de software que se ejecuta en uno o varios servidores locales para validar a los usuarios directamente con AD DS. Con PTA, sincroniza las cuentas de usuario de AD DS con Microsoft 365 y administra los usuarios locales. 

![Autenticación de paso a través (PTA).](../media/plan-for-directory-synchronization/pta-authentication.png)

PTA permite a los usuarios iniciar sesión en recursos y aplicaciones locales y de Microsoft 365 mediante su cuenta y contraseña locales. Esta configuración valida las contraseñas de los usuarios directamente en ad DS local sin almacenar los hashes de contraseña en Azure AD. 

PTA también es para las organizaciones con un requisito de seguridad para aplicar inmediatamente los estados de la cuenta de usuario local, las directivas de contraseña y las horas de inicio de sesión. 
  
Consulte [Elección del método de autenticación adecuado](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.
  
##### <a name="federated-authentication"></a>Autenticación federada

La autenticación federada es principalmente para organizaciones empresariales grandes con requisitos de autenticación más complejos. Las identidades de AD DS se sincronizan con Microsoft 365 y las cuentas de los usuarios se administran de forma local. Con la autenticación federada, los usuarios tienen la misma contraseña en el entorno local y en la nube y no tienen que volver a iniciar sesión para usar Microsoft 365. 

La autenticación federada puede admitir requisitos de autenticación adicionales, como la autenticación basada en tarjeta inteligente o una autenticación multifactor de terceros, y normalmente se requiere cuando las organizaciones tienen un requisito de autenticación no compatible de forma nativa con Azure AD.
 
Consulte [Elección del método de autenticación adecuado](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.
  
Para proveedores de identidades y autenticación de terceros, los objetos de directorio locales se pueden sincronizar con Microsoft 365 y el acceso a recursos en la nube que administra principalmente un proveedor de identidades (IdP) de terceros. Si su organización usa una solución de federación de terceros, puede configurar el inicio de sesión con esa solución para Microsoft 365 siempre que la solución de federación de terceros sea compatible con Azure AD.
  
Consulte la [lista de compatibilidad de federación de Azure AD](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) para obtener más información.
  
### <a name="administration"></a>Administración

Dado que las cuentas de usuario original y autoritativa se almacenan en AD DS local, las identidades se administran con las mismas herramientas que administra AD DS.

No usa la Centro de administración de Microsoft 365 ni PowerShell para Microsoft 365 para administrar cuentas de usuario sincronizadas en Azure AD.

## <a name="next-step"></a>Paso siguiente

[![Protección de las cuentas con privilegios de Microsoft 365](../media/deploy-identity-solution-overview/protect-your-global-administrator-accounts.png)](protect-your-global-administrator-accounts.md)

Continúe con [el paso 2](protect-your-global-administrator-accounts.md) para proteger las cuentas de administrador globales.
