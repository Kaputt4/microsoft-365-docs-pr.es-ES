---
title: Paso 2. Protección de las cuentas con privilegios de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: En este artículo se proporciona información sobre cómo proteger el acceso con privilegios al inquilino de Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9719908fcbe8aa453ac07788ee7771a39242d4e
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "65622571"
---
# <a name="step-2-protect-your-microsoft-365-privileged-accounts"></a>Paso 2. Protección de las cuentas con privilegios de Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Las infracciones de seguridad de un inquilino de Microsoft 365, incluida la recopilación de información y los ataques de suplantación de identidad (phishing), normalmente se realizan poniendo en peligro las credenciales de una cuenta Microsoft 365 con privilegios. La seguridad en la nube es una asociación entre usted y Microsoft:
  
- Los servicios en la nube de Microsoft se basan en unos cimientos de confianza y seguridad. Microsoft le proporciona funcionalidades y controles de seguridad para ayudarle a proteger sus datos y sus aplicaciones.
    
- Usted es propietario de sus datos e identidades, así como es usted mismo el encargado de protegerlos, tal y como debe hacer con sus recursos locales y con la seguridad de los componentes en la nube que controle.
    
Microsoft proporciona funcionalidades para ayudar a proteger su organización, pero solo son eficaces si las usa. Si no los usa, es posible que sea vulnerable a ataques. Para proteger sus cuentas con privilegios, Microsoft está aquí para ayudarle con instrucciones detalladas para:
  
1. Cree cuentas dedicadas, con privilegios y basadas en la nube y úselas solo cuando sea necesario.
    
2. Configure la autenticación multifactor (MFA) para las cuentas con privilegios de Microsoft 365 dedicadas y use la forma más segura de autenticación secundaria.

3. Proteja las cuentas con privilegios con Confianza cero recomendaciones de acceso a dispositivos e identidades.

## <a name="1-create-dedicated-privileged-cloud-based-user-accounts-and-use-them-only-when-necessary"></a>1. Cree cuentas de usuario dedicadas, con privilegios y basadas en la nube y úselas solo cuando sea necesario.

En lugar de usar cuentas de usuario diarias a las que se han asignado roles de administrador, cree cuentas de usuario dedicadas que tengan los roles de administrador en Azure AD. 

A partir de este momento, inicia sesión con las cuentas con privilegios dedicados solo para las tareas que requieren privilegios de administrador. Todas las demás Microsoft 365 administración deben realizarse mediante la asignación de otros roles de administración a cuentas de usuario.
  
> [!NOTE]
> Esto requiere pasos adicionales para cerrar sesión como cuenta de usuario diaria e iniciar sesión con una cuenta de administrador dedicada. Pero esto solo se debe hacer ocasionalmente para las operaciones de administrador. Tenga en cuenta que la recuperación de la suscripción Microsoft 365 después de una infracción de la cuenta de administrador requiere muchos más pasos.

También debe crear cuentas de [acceso de emergencia](/azure/active-directory/roles/security-emergency-access) para evitar que se bloquee accidentalmente Azure AD.

Puede proteger aún más las cuentas con privilegios con Azure AD Privileged Identity Management (PIM) para la asignación just-in-time a petición de roles de administrador. 
 
## <a name="2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-privileged-accounts"></a>2. Configuración de la autenticación multifactor para las cuentas con privilegios de Microsoft 365 dedicadas

La autenticación multifactor (MFA) requiere información adicional más allá del nombre y la contraseña de la cuenta. Microsoft 365 admite estos métodos de comprobación adicionales:
  
- La aplicación de Microsoft Authenticator
- Una llamada de teléfono
- Código de verificación generado aleatoriamente enviado a través de un mensaje de texto
- Una tarjeta inteligente (virtual o física) (requiere autenticación federada)
- Un dispositivo biométrico
- Token de Oauth
- 
    
>[!Note]
>Para las organizaciones que deben cumplir los estándares del Instituto Nacional de Estándares y Tecnología (NIST), el uso de una llamada telefónica o métodos de verificación adicionales basados en mensajes de texto están restringidos. Haga clic [aquí](https://pages.nist.gov/800-63-FAQ/#q-b01) para obtener los detalles.
>

Si es una pequeña empresa que usa cuentas de usuario almacenadas solo en la nube (el modelo de identidad solo en la nube), [configure MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) para configurar MFA mediante una llamada telefónica o un código de verificación de mensajes de texto enviado a un teléfono inteligente para cada cuenta con privilegios dedicada.
    
Si es una organización más grande que usa un modelo de identidad híbrida Microsoft 365, tiene más opciones de verificación. Si ya dispone de la infraestructura de seguridad para un método de autenticación secundario más seguro, [configure MFA](../admin/security-and-compliance/set-up-multi-factor-authentication.md) y configure cada cuenta con privilegios dedicados para el método de verificación adecuado.
  
Si la infraestructura de seguridad para el método de verificación más seguro deseado no está en vigor y funciona para Microsoft 365 MFA, se recomienda encarecidamente configurar cuentas con privilegios dedicados con MFA mediante la aplicación Microsoft Authenticator, una llamada telefónica o un código de verificación de mensajes de texto enviados a un teléfono inteligente para las cuentas con privilegios como medida de seguridad provisional. No deje las cuentas con privilegios dedicados sin la protección adicional proporcionada por MFA.
  
Para obtener más información, vea [MFA para Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md).
  
## <a name="3-protect-administrator-accounts-with-zero-trust-identity-and-device-access-recommendations"></a>3. Protección de cuentas de administrador con recomendaciones de acceso a dispositivos e identidades de Confianza cero

Para ayudar a garantizar una fuerza de trabajo segura y productiva, Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md). Para la identidad, use las recomendaciones y la configuración de estos artículos:

- [Requisitos previos](../security/office-365-security/identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md)

## <a name="additional-protections-for-enterprise-organizations"></a>Protecciones adicionales para organizaciones empresariales

Use estos métodos adicionales para asegurarse de que la cuenta con privilegios y la configuración que realice con ella sean lo más seguras posible.
  
### <a name="privileged-access-workstation"></a>Estación de trabajo de acceso con privilegios

Para asegurarse de que la ejecución de tareas con privilegios elevados es lo más segura posible, use una estación de trabajo de acceso con privilegios (PAW). Un PAW es un equipo dedicado que solo se usa para tareas de configuración confidenciales, como Microsoft 365 configuración que requiere una cuenta con privilegios. Dado que este equipo no se usa diariamente para la navegación por Internet o el correo electrónico, está mejor protegido frente a ataques y amenazas de Internet.
  
Para obtener instrucciones sobre cómo configurar una PAW, vea [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices).

Para habilitar Azure PIM para su espacio empresarial de Azure AD y sus cuentas de administrador, vea los [pasos para configurar PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desarrollar un plan completo a fin de proteger el acceso con privilegios frente a los ciberatacantes, vea [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure AD](/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

En lugar de tener a las cuentas con privilegios asignadas permanentemente un rol de administrador, puede usar PIM de Azure AD para habilitar la asignación just-in-time a petición del rol de administrador cuando sea necesario.
  
Las cuentas de administrador pasan de ser administradores permanentes a administradores aptos. El rol de administrador permanece inactivo hasta que lo necesite. A continuación, complete un proceso de activación para agregar el rol de administrador a la cuenta con privilegios durante un período de tiempo predeterminado. Cuando expire el tiempo, PIM quita el rol de administrador de la cuenta con privilegios.
  
El uso de PIM y este proceso reduce significativamente la cantidad de tiempo que las cuentas con privilegios son vulnerables a ataques y usos por parte de usuarios malintencionados.

PIM está disponible con Azure Active Directory Premium P2, que se incluye con Microsoft 365 E5. Como alternativa, puede comprar licencias individuales de Azure Active Directory Premium P2 para las cuentas de administrador.
  
Para más información, vea:

- [Privileged Identity Management de Azure AD](/azure/active-directory/active-directory-privileged-identity-management-configure).
- [Proteger el acceso con privilegios para implementaciones híbridas y en la nube en Azure AD](/azure/active-directory/roles/security-planning)
  

### <a name="privileged-access-management"></a>Administración del acceso con privilegios

La administración de acceso con privilegios se habilita configurando las directivas que especifiquen el acceso puntual para las actividades basadas en tareas en el espacio empresarial. Puede ayudar a proteger la organización contra infracciones que puedan usar las cuentas existentes de administrador con privilegios con acceso permanente a datos confidenciales o acceder a opciones de configuración críticas. Por ejemplo, puede configurar una directiva de administración de acceso con privilegios que requiera una autorización explícita para acceder y modificar la configuración del buzón de correo del espacio empresarial.

En este paso, habilitará la administración de acceso con privilegios en el inquilino y configurará directivas de acceso con privilegios que proporcionan seguridad adicional para el acceso basado en tareas a los datos y la configuración de la organización. Hay tres pasos básicos para empezar a usar el acceso con privilegios en su organización:

- Crear un grupo de aprobadores
- Habilitar el acceso con privilegios
- Crear directivas de aprobación

La administración de acceso con privilegios permite a su organización operar sin privilegios permanentes y proporcionar una capa de defensa contra las vulnerabilidades que se producen debido a este acceso administrativo permanente. El acceso con privilegios requiere aprobaciones para ejecutar cualquier tarea que tenga definida una directiva de aprobación asociada. Los usuarios que necesiten ejecutar tareas incluidas en la directiva de aprobación deben solicitar y obtener la aprobación de acceso.

Para habilitar la administración de acceso con privilegios, consulte [Configuración de la administración de acceso con privilegios](/office365/securitycompliance/privileged-access-management-configuration).

Para obtener más información, consulte [Administración de acceso con privilegios](/office365/securitycompliance/privileged-access-management-overview).

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Software de administración de eventos e información de seguridad (SIEM) para el registro de Microsoft 365

El software SIEM que se ejecuta en un servidor realiza un análisis en tiempo real de alertas de seguridad y eventos creados por aplicaciones y hardware de red. Para permitir que el servidor SIEM incluya Microsoft 365 alertas y eventos de seguridad en sus funciones de análisis e informes, integre Azure AD en el SEIM. Consulte [Introducción a Azure Log Integration](/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Paso siguiente

[![Protección de las cuentas de usuario Microsoft 365](../media/deploy-identity-solution-overview/microsoft-365-secure-sign-in.png)](microsoft-365-secure-sign-in.md)

Continúe con [el paso 3](microsoft-365-secure-sign-in.md) para proteger las cuentas de usuario.
