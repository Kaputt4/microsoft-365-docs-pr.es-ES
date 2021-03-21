---
title: Sincronización de directorios y identidad híbrida para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Describe la sincronización de directorios con Microsoft 365, la limpieza de servicios de dominio de Active Directory y la herramienta Azure Active Directory Connect.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927549"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Sincronización de directorios y identidad híbrida para Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Según las necesidades empresariales y los requisitos técnicos, el modelo de identidad híbrida y la sincronización de directorios es la opción más común para los clientes empresariales que adoptan Microsoft 365. La sincronización de directorios permite administrar identidades en los Servicios de dominio de Active Directory (AD DS) y todas las actualizaciones de cuentas de usuario, grupos y contactos se sincronizan con el inquilino de Azure Active Directory (Azure AD) de su suscripción a Microsoft 365.

>[!Note]
>Cuando las cuentas de usuario de AD DS se sincronizan por primera vez, no se les asigna automáticamente una licencia de Microsoft 365 y no pueden acceder a los servicios de Microsoft 365, como el correo electrónico. Primero debe asignarles una ubicación de uso. A continuación, asigne una licencia a estas cuentas de usuario, ya sea de forma individual o dinámica a través de la pertenencia a grupos.
>

## <a name="authentication-for-hybrid-identity"></a>Autenticación para identidad híbrida

Hay dos tipos de autenticación al usar el modelo de identidad híbrida:

- Autenticación administrada

  Azure AD controla el proceso de autenticación mediante una versión hash almacenada localmente de la contraseña o envía las credenciales a un agente de software local para que ad DS local lo autentique.

- Autenticación federada

  Azure AD redirige el equipo cliente que solicita autenticación a otro proveedor de identidades.

### <a name="managed-authentication"></a>Autenticación administrada

Hay dos tipos de autenticación administrada:

- Sincronización de hash de contraseña (PHS)

  Azure AD realiza la autenticación en sí.

- Autenticación de paso a través (PTA)

  Azure AD tiene AD DS para realizar la autenticación.


#### <a name="password-hash-synchronization-phs"></a>Sincronización de hash de contraseña (PHS)

Con PHS, sincroniza las cuentas de usuario de AD DS con Microsoft 365 y administra los usuarios locales. Los hash de contraseñas de usuario se sincronizan desde AD DS a Azure AD para que los usuarios tengan la misma contraseña local y en la nube. Esta es la forma más sencilla de habilitar la autenticación para identidades de AD DS en Azure AD. 

![Sincronización de hash de contraseña (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

Cuando se cambian o restablecen las contraseñas locales, los nuevos hashes de contraseña se sincronizan con Azure AD para que los usuarios siempre puedan usar la misma contraseña para los recursos en la nube y los recursos locales. Las contraseñas de usuario nunca se envían a Azure AD ni se almacenan en Azure AD en texto sin formato. Algunas características premium de Azure AD, como Identity Protection, requieren PHS independientemente del método de autenticación seleccionado.
  
Consulta [elegir el método de autenticación correcto](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.
  
#### <a name="pass-through-authentication-pta"></a>Autenticación de paso a través (PTA)

LA PTA proporciona una validación de contraseña sencilla para los servicios de autenticación de Azure AD mediante un agente de software que se ejecuta en uno o varios servidores locales para validar a los usuarios directamente con su AD DS. Con la PTA, sincroniza las cuentas de usuario de AD DS con Microsoft 365 y administra los usuarios locales. 

![Autenticación de paso a través (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

LA PTA permite a los usuarios iniciar sesión en recursos y aplicaciones locales y de Microsoft 365 con su cuenta local y contraseña. Esta configuración valida las contraseñas de los usuarios directamente en su AD DS local sin almacenar hashes de contraseña en Azure AD. 

La PTA también está para que las organizaciones con un requisito de seguridad exijan inmediatamente los estados de cuenta de usuario local, las directivas de contraseña y las horas de inicio de sesión. 
  
Consulta [elegir el método de autenticación correcto](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.
  
### <a name="federated-authentication"></a>Autenticación federada

La autenticación federada es principalmente para organizaciones empresariales grandes con requisitos de autenticación más complejos. Las identidades de AD DS se sincronizan con Microsoft 365 y las cuentas de usuarios se administran localmente. Con la autenticación federada, los usuarios tienen la misma contraseña local y en la nube y no tienen que volver a iniciar sesión para usar Microsoft 365. 

La autenticación federada puede admitir requisitos de autenticación adicionales, como la autenticación basada en tarjetas inteligentes o una autenticación multifactor de terceros, y normalmente es necesaria cuando las organizaciones tienen un requisito de autenticación que Azure AD no admite de forma nativa.
 
Consulta [elegir el método de autenticación correcto](/azure/active-directory/hybrid/choose-ad-authn) para obtener más información.
  
#### <a name="third-party-authentication-and-identity-providers"></a>Proveedores de identidades y autenticación de terceros

Los objetos de directorio locales pueden sincronizarse con Microsoft 365 y el acceso a recursos en la nube lo administra principalmente un proveedor de identidades (IdP) de terceros. Si su organización usa una solución de federación de terceros, puede configurar el inicio de sesión con esa solución para Microsoft 365 siempre que la solución de federación de terceros sea compatible con Azure AD.
  
Consulta la lista [de compatibilidad de federación de Azure AD](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) para obtener más información.
  
## <a name="ad-ds-preparation"></a>Preparación de AD DS

Para garantizar una transición sin problemas a Microsoft 365 mediante la sincronización, debe preparar el bosque de AD DS antes de comenzar la implementación de sincronización de directorios de Microsoft 365.
  
La preparación del directorio debe centrarse en las siguientes tareas:

- Quite los **atributos proxyAddress y** **userPrincipalName duplicados.**
- Actualice los atributos **userPrincipalName** en blanco y no válidos con atributos **userPrincipalName** válidos.
- Quite caracteres no válidos y cuestionables en los atributos **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** y **userPrincipalName.** Para obtener más información acerca de la preparación de atributos, consulte [Lista de atributos sincronizados por la Herramienta de](https://go.microsoft.com/fwlink/p/?LinkId=396719)sincronización de Azure Active Directory .

    > [!NOTE]
    > Estos son los mismos atributos que Sincroniza Azure AD Connect. 
  
## <a name="multi-forest-deployment-considerations"></a>Consideraciones de implementación de varios bosques

Para varios bosques y opciones de SSO, use [una instalación personalizada de Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).
  
Si su organización tiene varios bosques para la autenticación (bosques de inicio de sesión), se recomienda encarecidamente lo siguiente:
  
- **Considere la posibilidad de consolidar los bosques.** En general, hay más sobrecarga necesaria para mantener varios bosques. A menos que su organización tenga restricciones de seguridad que dicten la necesidad de bosques independientes, considere la posibilidad de simplificar el entorno local.
- **Solo se usa en el bosque de inicio de sesión principal.** Considere la posibilidad de implementar Microsoft 365 solo en el bosque de inicio de sesión principal para el lanzamiento inicial de Microsoft 365. 

Si no puedes consolidar la implementación de AD DS de varios bosques o estás usando otros servicios de directorio para administrar identidades, es posible que puedas sincronizarlas con la ayuda de Microsoft o un partner.
  
Consulte [Topologías de Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) para obtener más información.
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>Características que dependen de la sincronización de directorios
  
La sincronización de directorios es necesaria para las siguientes características y funcionalidades:
  
- Azure AD Seamless Single Sign-On (SSO)
- Coexistencia de Skype
- Implementación híbrida de Exchange, que incluye:
  - Lista global de direcciones (GAL) totalmente compartida entre el entorno local de Exchange y Microsoft 365.
  - Sincronización de información de GAL desde varios sistemas de correo.
  - La capacidad de agregar usuarios y quitarlos de las ofertas de servicio de Microsoft 365. Esto requiere lo siguiente:
  - La sincronización bidireccional debe configurarse durante la instalación de sincronización de directorios. De forma predeterminada, las herramientas de sincronización de directorios escriben información de directorio solo en la nube. Al configurar la sincronización bidireccional, se habilita la funcionalidad de reescribición para que un número limitado de atributos de objeto se copien de la nube y, a continuación, se vuelvan a escribir en su AD DS local. La reescribición también se conoce como modo híbrido de Exchange. 
  - Una implementación híbrida de Exchange local
  - La capacidad de mover algunos buzones de usuario a Microsoft 365 mientras se mantienen otros buzones de usuario locales.
  - Los remitentes seguros y los remitentes bloqueados localmente se replican en Microsoft 365.
  - Función de delegación básica y envío en nombre de otra persona.
  - Tiene una tarjeta inteligente local integrada o una solución de autenticación multifactor.
- Sincronización de fotos, miniaturas, salas de conferencia y grupos de seguridad

## <a name="next-step"></a>Paso siguiente

Cuando esté listo para implementar la identidad híbrida, vea [Prepare for directory synchronization](prepare-for-directory-synchronization.md).
