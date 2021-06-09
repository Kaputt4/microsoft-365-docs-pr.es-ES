---
title: Microsoft 365 de aplicaciones de cliente y servicios
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: En este artículo, encontrará detalles sobre Microsoft 365 de aplicaciones de cliente y servicios.
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905013"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365 de aplicaciones de cliente y servicios

Microsoft admite una amplia variedad de características de seguridad, autenticación y cumplimiento para mantener la seguridad de los datos de los clientes y permite a los administradores de TI personalizar las directivas dentro del centro de administración de Microsoft 365 para sus usuarios. Las siguientes características son solo un subconjunto de las muchas características empresariales que puede configurar en función de su Microsoft 365 suscripción.

## <a name="client-and-service-support"></a>Soporte técnico de cliente y servicio

### <a name="continuous-access-evaluation-preview"></a>Evaluación continua de acceso (versión preliminar)

La evaluación continua del acceso se implementa habilitando servicios, como Exchange Online, SharePoint Online y Teams, para suscribirse a eventos críticos en Azure Active Directory de modo que estos eventos se puedan evaluar y aplicar casi en tiempo real. La evaluación de eventos críticos no se basa en directivas de acceso condicional, por lo que está disponible en cualquier espacio empresarial.

Actualmente se evalúan los siguientes eventos:

- Se elimina o deshabilita una cuenta de usuario
- Se cambia o restablece la contraseña de un usuario
- La autenticación multifactor está habilitada para el usuario
- El administrador revoca explícitamente todos los tokens de actualización para un usuario
- Riesgo elevado de usuario detectado por Azure AD Identity Protection

Para obtener más información acerca de la evaluación continua de acceso para la compatibilidad con aplicaciones de cliente y servicios, consulta Evaluación continua de acceso [(versión preliminar).](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>Compatibilidad con clientes

### <a name="certificate-based-authentication"></a>Autenticación basada en certificados

La autenticación basada en certificados (CBA) es el uso de un certificado digital para identificar a un usuario, máquina o dispositivo antes de conceder acceso a un recurso, red, aplicación o servicio. En la autenticación de usuario, a menudo se implementa en coordinación con métodos tradicionales, como nombres de usuario y contraseñas.

Algunas soluciones tradicionales solo funcionan para los usuarios, como la biometría y las contraseñas de un solo uso (OTP). Con la autenticación basada en certificados, se puede usar la misma solución para todos los puntos de conexión; usuarios, dispositivos y el creciente Internet de las cosas (IoT).

Para obtener más información acerca de la autenticación basada en certificados para la compatibilidad con aplicaciones de cliente y servicios, [vea Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).

### <a name="conditional-access"></a>Acceso condicional

El acceso condicional es la herramienta que Azure Active Directory para unir señales, tomar decisiones y aplicar directivas de acceso de la organización. El acceso condicional es el núcleo del nuevo modelo de control basado en identidades.

Las directivas de acceso condicional son instrucciones if-then para conceder acceso a recursos. Si un usuario quiere tener acceso a un recurso, debe completar una acción. Las señales comunes que el acceso condicional puede usar al tomar una decisión de acceso de directiva son:

- Pertenencia a grupos o usuarios
- Información de ubicación IP
- Información del dispositivo
- Información de la aplicación
- Detección de riesgos calculados y en tiempo real
- Microsoft Cloud App Security (MCAS)

Al tomar estas decisiones de acceso, las directivas pueden realizar diferentes acciones:

- La directiva puede bloquear el acceso: esta configuración es la acción más restrictiva e impide que el usuario obtenga acceso al recurso.
- La directiva puede conceder acceso: esta configuración es una decisión menos restrictiva y aún puede requerir una o varias de las siguientes opciones:

    - Autenticación multifactor
    - El dispositivo que se marcará como compatible
    - El dispositivo está unido a Azure AD híbrido
    - Una aplicación cliente aprobada
    - Directiva de protección de aplicaciones configurada (versión preliminar)

Para obtener más información sobre el acceso condicional para la compatibilidad con aplicaciones de cliente y servicios, vea:

- [Microsoft 365 Compatibilidad con aplicaciones cliente: acceso condicional basado en dispositivos](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Administración de aplicaciones móviles

Los usuarios a menudo tienen acceso tanto a documentos personales como de organización, correo electrónico y datos desde el mismo dispositivo móvil. Estos dispositivos suelen ser de propiedad personal y deben configurarse para proteger tanto los datos de la organización como la privacidad personal del usuario.

Cuando un usuario accede a los datos de la organización, la organización debe estar segura de que las directivas de la organización, como las directivas de configuración y las directivas de protección, se aplican para ayudar a proteger los datos de la organización en el dispositivo. Además, el contenido personal del usuario en el dispositivo debe permanecer fuera del control de la organización.

Para el contenido administrado por la organización, puede aplicar directivas de administración de aplicaciones para controlar cómo se accede, comparte y usa los datos mediante Microsoft Intune. Por ejemplo, se admiten las siguientes acciones:

- Borrar de forma remota el contenido de la organización administrada (también se hace referencia a los datos de la organización)
- Impedir pegar contenido de la organización en ubicaciones que no son de la organización
- Requerir un PIN para obtener acceso al contenido de la organización
- Impedir que las aplicaciones administradas se ejecuten en dispositivos con jailbreak o root
- Impedir que el contenido de la organización se guarde en proveedores de almacenamiento en la nube no aprobados
- Impedir que el contenido no aprobado se transfiera a aplicaciones administradas
- Permitir el acceso al contenido de la organización solo después de aplicar directivas
- Entregar la configuración de la aplicación para administrar el comportamiento y la configuración de la aplicación
- Restringir la aplicación administrada a una identidad definida deshabilitando las capacidades de identidad múltiple o el uso personal

Para obtener más información acerca de la administración de aplicaciones móviles Microsoft Intune, consulta [¿Qué es Microsoft Intune administración de aplicaciones móviles?](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>Autenticación multifactor

[Autenticación multifactor (MFA) es un método de control de acceso de equipo en el que se concede acceso a un usuario solo después de presentar correctamente varias pruebas independientes a un mecanismo de autenticación. Este método suele usar al menos dos de las siguientes categorías:

- Conocimiento (algo que saben)
- Posesión (algo que tienen)
- Coherencia (algo que son)

Para obtener más información acerca de la autenticación multifactor para la compatibilidad con aplicaciones de cliente y servicios, vea Microsoft 365 [Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).

### <a name="single-sign-on"></a>Inicio de sesión único

El inicio de sesión único (SSO) agrega seguridad y comodidad cuando los usuarios inician sesión en las aplicaciones de Azure Active Directory. Con el inicio de sesión único, los usuarios inician sesión una vez con una cuenta para acceder a dispositivos locales unidos a dominio de Servicios de dominio de Active Directory (AD DS), aplicaciones de software como servicio (SaaS) y aplicaciones web de la organización.

Para obtener más información sobre el inicio de sesión único para la compatibilidad con aplicaciones de cliente y servicios, vea [Microsoft 365 Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md).

## <a name="services-support"></a>Soporte técnico de servicios

### <a name="modern-authentication"></a>Autenticación moderna

La autenticación moderna permite que los clientes se autentiquen en Office 365 y que los administradores de inquilinos exijan requisitos de autenticación específicos en el Office 365 arrendamiento, como:

- Compatibilidad con la autenticación multifactor para la interacción administrativa con el arrendamiento y los servicios, y la interacción del usuario final con las aplicaciones y sus datos
- Acceso condicional
- Inicio de sesión del proveedor de identidades de terceros basado en SAML
- Registro de tarjetas inteligentes en equipos personales
- Autenticación basada en certificados en dispositivos móviles
- Ya no requiere la transmisión de credenciales a través de la autenticación básica.

Para obtener más información sobre la compatibilidad con los servicios de autenticación modernos, vea [Autenticación frente a autorización.](/azure/active-directory/develop/authentication-vs-authorization)

### <a name="azure-active-directory-conditional-access"></a>Acceso condicional de Azure Active Directory

Azure Active Directory (Azure AD) Las reglas de acceso condicional permiten a los clientes controlar el acceso a los servicios en línea, en función de atributos como el cumplimiento del dispositivo o la ubicación de red. Se pueden usar las siguientes soluciones:

- Acceso condicional basado en autenticación multifactor de Azure AD
- Acceso condicional basado en ubicación de Azure AD
- Acceso condicional basado en dispositivos de Azure AD

Las reglas de acceso condicional de Azure AD se aplican por aplicación y están disponibles para que los clientes puedan controlar el acceso en función de diferentes condiciones. Con la Administración de dispositivos móviles [(MDM)](/mem/intune/fundamentals/what-is-device-management)o Intune, los clientes deben poder restringir el acceso a Microsoft 365 solo a aquellos usuarios que usan un dispositivo de la organización o que han inscrito su dispositivo personal para su administración. Por ejemplo, los clientes pueden configurar reglas de acceso condicional para aplicar controles como:

- Solo permitir el acceso desde dispositivos unidos a un dominio o compatibles con el dominio
- Exigir la autenticación multifactor para todo el acceso a Exchange Online servicios

Para obtener más información Azure Active Directory acceso condicional, vea [¿Qué es el acceso condicional?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>Compatibilidad con TLS 1.2

Para proporcionar el mejor cifrado de su clase a nuestros clientes, Microsoft planea interrumpir la compatibilidad con las versiones 1.0 y 1.1 de seguridad de la capa de transporte (TLS) en Office 365 y Office 365 GCC.

Entendemos que la seguridad de los datos es importante y estamos garantizamos transparencia en cuanto a los cambios que pueden afectar al uso del servicio TLS. Se recomienda que todas las combinaciones cliente-servidor y explorador-servidor usen TLS 1.2 (o una versión posterior) para mantener la conexión a Office 365 servicios. Es posible que tenga que actualizar ciertas combinaciones cliente-servidor y navegador-servidor.

Para obtener más información acerca de la compatibilidad y los servicios de TLS 1.2, vea [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md).