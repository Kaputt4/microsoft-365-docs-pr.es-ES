---
title: Información adicional de Azure Active Directory para la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: información adicional de Azure Active Directory al pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 1e3871dc5a8a8a9ecbef29df21431aa3707871d0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923855"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información adicional de Azure Active Directory para la migración desde Microsoft Cloud Deutschland

Para completar el traslado de la nube de Azure German a la nube pública de Azure, recomendamos que el punto de conexión de autenticación, el graph de Azure Active Directory (Azure AD) y los puntos de conexión de MS Graph para las aplicaciones se actualicen a los de la nube comercial cuando el extremo OpenID Connect (OIDC), comience a informar de los puntos de conexión de nube `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` comerciales. 
 
**¿Cuándo debo realizar este cambio?**

Recibirá una notificación en Azure/Office Portal cuando el inquilino complete la migración de la nube alemana a la nube comercial. Tienes 30 días después de recibir esta notificación para completar estas actualizaciones para que la aplicación siga funcionando para los inquilinos que se migran de la nube de Azure Germany a la nube pública de Azure.
 
Existen tres condiciones previas para actualizar la entidad de inicio de sesión:

 - El punto de conexión de detección de OIDC para el inquilino devuelve puntos de conexión de nube pública `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` de Azure AD.

 - Si el inquilino está configurado para federación, los Servicios de federación de Active Directory (AD FS) se actualizan para sincronizarse con Azure AD Public. Puedes seguir las instrucciones para actualizar la configuración de Azure AD Connect para realizar este cambio.

 - Las aplicaciones de recursos, si las hay, se modifican para aceptar tokens firmados por Azure AD Germany y Azure AD Public.
 
**¿Qué tipo de aplicaciones?**

Una aplicación puede ser cualquiera de las siguientes:

- [Aplicación de una sola página (SPA)](/azure/active-directory/develop/scenario-spa-overview)
- [Aplicación web que inicia sesión en usuarios](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Aplicación web que llama a API web](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [API web protegida](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [API web que llama a API web](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Aplicación de escritorio](/azure/active-directory/develop/scenario-desktop-overview)
- [Aplicación demonio](/azure/active-directory/develop/scenario-daemon-overview)
- [Aplicación móvil](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Cuando una aplicación pasa a `login.microsoftonline.com` usarse como autoridad, los tokens se firmarán con esta nueva autoridad. Si hospedas cualquier aplicación de recursos a la que llamen otras aplicaciones, deberás permitir la validación de tokens lax. Esto significa que la aplicación debe permitir tokens firmados por las nubes públicas de Azure AD Germany y Azure AD. Esta validación de token lax es necesaria hasta que todas las aplicaciones cliente que llaman al servicio se migren completamente a la nube pública de Azure AD. Después de la migración, la aplicación de recursos solo debe aceptar tokens firmados por la nube pública de Azure AD.

**¿Qué necesito actualizar?**

1. Si hospeda una aplicación en Azure Germany que se usa para autenticar usuarios de Azure Germany u Office 365 Germany, asegúrese de que se usa como autoridad en el contexto `https://login.microsoftonline.com` de autenticación.

    - Consulte Contextos de autenticación de Azure AD.
    - Esto se aplica tanto a la autenticación a la aplicación como a la autenticación a cualquier API que la aplicación pueda llamar (es decir, Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Actualice el extremo de Azure AD Graph para que sea `https://graph.windows.net` .

3. Actualizar el extremo de MS Graph para que sea `https://graph.microsoft.com` .

4. Actualice los extremos de la nube alemán (como los de Exchange Online y SharePoint Online) que las aplicaciones usan para que sean los de la nube pública.

5. Actualice los parámetros del entorno `AzurePublic` para que sean (en lugar de ) `AzureGermany` en herramientas administrativas y scripts para:

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**¿Qué sucede con las aplicaciones que publico?**

Si publica una aplicación que está disponible para los usuarios que están fuera de su espacio empresarial, es posible que tenga que cambiar el registro de la aplicación para garantizar la continuidad. Otros inquilinos que usan la aplicación pueden moverse en un momento diferente al del inquilino. Para asegurarse de que nunca pierden el acceso a la aplicación, deberás dar su consentimiento para que la aplicación se sincronice de Azure Germany con Azure public.

## <a name="additional-considerations"></a>Consideraciones adicionales

Estas son algunas consideraciones adicionales para Azure AD:

- Para la autenticación federada:

  - No debe crear, promover ni disminuir el nivel de un dominio federado mientras la transición del espacio empresarial está en proceso. Una vez completada la migración al servicio de Azure AD (el espacio empresarial está completo), puede reanudar la administración de dominios federados.

  - Si usa la autenticación federada con servicios de federación de Active Directory (AD FS), no debe realizar cambios en los URI del emisor usados para toda la autenticación con los Servicios de dominio de Active Directory (AD DS) locales durante la migración. Cambiar los URI del emisor provocará errores de autenticación para los usuarios del dominio. Los URI del emisor se pueden cambiar directamente en AD FS o cuando un dominio se convierte de administrado a federado y viceversa. Microsoft recomienda a los clientes que no agreguen, quiten o conviertan un dominio federado en el inquilino de Azure AD que se va a migrar. Los URI del emisor se pueden cambiar una vez completada la migración.

- Para redes:

  - La creación de redes con nombre IPv6 no funciona en Azure Portal, `http://portal.microsoftazure.de/` . Use Azure Portal at `https://portal.azure.com` para crear redes con nombre IPv6.
 
   - No puede crear intervalos de direcciones IP de confianza para la configuración del servicio Azure Multi-Factor Authentication (MFA) desde el portal de Microsoft Cloud Deutschland. Use los servicios de Azure AD Portal para Office 365 para crear intervalos de direcciones IP de confianza de Azure MFA.


- Para acceso condicional: 

  - Las directivas de acceso condicional con los siguientes controles de concesión no se admiten hasta que se complete la migración a los servicios de Office 365 (después de finalizar la fase de migración de [Azure AD):](ms-cloud-germany-transition.md#how-is-the-migration-organized)

    - Requerir dispositivo compatible
    - Requerir aplicación aprobada
    - Requerir directiva de protección de aplicaciones
    
  - La interfaz de directiva de acceso condicional proporciona una advertencia falsa sobre los valores predeterminados de seguridad que se habilitan para el inquilino incluso cuando está deshabilitado, y las directivas de acceso condicional ya existen para el inquilino. Debe omitir la advertencia o usar el portal de servicios de Office 365 para administrar directivas de acceso condicional. 

- Los escenarios de Intune solo se admiten en los puntos de conexión de todo el mundo una vez completada la migración de inquilinos, incluidas todas las migraciones de cargas de trabajo de office.

- Los usuarios de Microsoft Cloud Deutschland que usan el método Mobile App Notification para las solicitudes MFA ven el ObjectId (un GUID) del usuario en lugar del nombre principal de usuario (UPN) en la aplicación Microsoft Authenticator. Una vez completada la migración del inquilino de Azure AD y hospedada en los servicios de Office 365, las nuevas activaciones de Microsoft Authenticator mostrarán los UPN de los usuarios. Las cuentas existentes de Microsoft Authenticator seguirán mostrando el ObjectId de usuario, pero seguirán funcionando para las notificaciones de aplicaciones móviles. 

- Para los inquilinos que se crean después del 22 de octubre de 2019, los valores predeterminados de seguridad pueden habilitarse automáticamente para el inquilino cuando se migra al servicio de Office 365. Los administradores de inquilinos pueden optar por dejar habilitados los valores predeterminados de seguridad y registrarse en MFA, o bien pueden deshabilitar la característica. Para obtener más información, vea [Deshabilitar valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults). 

  > [!NOTE]
  > Las organizaciones que no están habilitadas automáticamente durante la migración aún pueden inscribirse automáticamente en el futuro, ya que la característica para habilitar los valores predeterminados de seguridad se incluye en el servicio de Office 365. Los administradores que deciden deshabilitar o habilitar explícitamente los valores predeterminados de seguridad pueden hacerlo actualizando la característica en **Azure Active Directory > Propiedades**. Después de que el administrador habilite explícitamente la característica, no se habilitará automáticamente.

- Habrá advertencias sobre la versión de Azure AD Connect en el portal de Office 365 Germany, así como en el portal de Office 365 una vez que el inquilino esté en migración. Esto puede omitirse si la advertencia de versión ya no muestra la advertencia una vez completada la migración. Si hay una advertencia, antes o después de la migración, en cualquiera de los dos portales, Azure AD Connect debe actualizarse. El mensaje de advertencia indica: "Hemos detectado que está usando una herramienta de sincronización de directorios obsoleta. Se recomienda ir al Centro de descarga de Microsoft para obtener la versión más reciente de Azure AD Connect".

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar a través de la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Información del programa de migración de Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introducción a su actualización de Microsoft Teams](/microsoftteams/upgrade-start-here)