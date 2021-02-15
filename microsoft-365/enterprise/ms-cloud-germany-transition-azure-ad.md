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
description: 'Resumen: información adicional de Azure Active Directory al pasar de Microsoft Cloud Alemania (Microsoft Cloud Deutschland) a los servicios de Office 365 en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688837"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información adicional de Azure Active Directory para la migración desde Microsoft Cloud Deutschland

Para completar el traslado de la nube de Azure German a la nube pública de Azure, recomendamos que el punto de conexión de autenticación, Azure Active Directory (Azure AD) Graph y los puntos de conexión de MS Graph para sus aplicaciones se actualicen a los de la nube comercial cuando el punto de conexión de OpenID Connect (OIDC) empiece a notificar los puntos de conexión de la nube `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` comercial. 
 
**¿Cuándo debo realizar este cambio?**

Recibirá una notificación en el portal de Azure/Office cuando el inquilino complete la migración de la nube alemana a la nube comercial. Tienes 30 días después de recibir esta notificación para completar estas actualizaciones para que la aplicación siga funcionando para los inquilinos que se migran de la nube de Azure Alemania a la nube pública de Azure.
 
Existen tres condiciones previas para actualizar la autoridad de inicio de sesión:

 - El punto de conexión de detección de OIDC para el inquilino devuelve puntos de conexión de nube pública `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` de Azure AD.

 - Si el inquilino está configurado para la federación, los Servicios de federación de Active Directory (AD FS) se actualizan para sincronizarse con Azure AD Public. Puede seguir las instrucciones para actualizar la configuración de Azure AD Connect para realizar este cambio.

 - Las aplicaciones de recursos, si las hay, que usan las aplicaciones se modifican para aceptar tokens firmados por Azure AD Alemania y Azure AD Public.
 
**¿Qué tipo de aplicaciones?**

Una aplicación puede ser cualquiera de las siguientes:

- [Aplicación de una sola página (SPA)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [Aplicación web que inicia sesión en usuarios](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Aplicación web que llama a las API web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [API web protegida](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [API web que llama a las API web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Aplicación de escritorio](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [Aplicación de demonio](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [Aplicación móvil](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Cuando una aplicación pasa a usarse como su autoridad, esta nueva autoridad firmará los `login.microsoftonline.com` tokens. Si hospeda aplicaciones de recursos a las que llaman otras aplicaciones, deberá permitir la validación de tokens lax. Esto significa que la aplicación debe permitir tokens firmados por las nubes públicas de Azure AD Alemania y Azure AD. Esta validación de token lax es necesaria hasta que todas las aplicaciones cliente que llaman al servicio se migren completamente a la nube pública de Azure AD. Después de la migración, la aplicación de recursos solo necesita aceptar tokens firmados por la nube pública de Azure AD.

**¿Qué necesito actualizar?**

1. Si hospeda una aplicación en Azure Alemania que se usa para autenticar usuarios de Azure Alemania u Office 365 Germany, asegúrese de que se usa como autoridad en el contexto `https://login.microsoftonline.com` de autenticación.

    - Vea contextos de autenticación de Azure AD.
    - Esto se aplica tanto a la autenticación de la aplicación como a la autenticación a cualquier API que la aplicación pueda estar llamando (es decir, Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Actualice el punto de conexión de Azure AD Graph para que sea `https://graph.windows.net` .

3. Actualizar el punto de conexión de MS Graph para que sea `https://graph.microsoft.com` .

4. Actualice los puntos de conexión de la nube alemana (como los de Exchange Online y SharePoint Online) que las aplicaciones usan para que sean los de la nube pública.

5. Actualice los parámetros del entorno `AzurePublic` para que sean (en lugar `AzureGermany` de) en herramientas administrativas y scripts para:

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**¿Qué sucede con las aplicaciones que publico?**

Si publica una aplicación que está disponible para los usuarios que están fuera de su espacio empresarial, es posible que tenga que cambiar el registro de la aplicación para garantizar la continuidad. Otros inquilinos que usan la aplicación pueden moverse en un momento diferente al de su espacio empresarial. Para asegurarse de que nunca pierden el acceso a la aplicación, deberás dar tu consentimiento para que la aplicación se sincronice de Azure Germany a Azure public.

## <a name="additional-considerations"></a>Consideraciones adicionales

Estas son algunas consideraciones adicionales para Azure AD:

- Para la autenticación federada:

  - No debe crear, promover ni disminuir el nivel de un dominio federado mientras la transición del espacio empresarial está en proceso. Una vez completada la migración al servicio de Azure AD (el inquilino está completo), puede reanudar la administración de dominios federados.

  - Si usa la autenticación federada con servicios de federación de Active Directory (AD FS), no debe realizar cambios en los URI del emisor usados para toda la autenticación con los Servicios de dominio de Active Directory (AD DS) locales durante la migración. Cambiar los URI del emisor provocará errores de autenticación para los usuarios del dominio. Los URI del emisor se pueden cambiar directamente en AD FS o cuando un dominio se convierte de administrado a federado y viceversa. Microsoft recomienda que los clientes no agreguen, quiten ni conviertan un dominio federado en el inquilino de Azure AD que se va a migrar. Los URI del emisor se pueden cambiar una vez completada por completo la migración.

- Para redes:

  - La creación de redes con nombre IPv6 no funciona en Azure `http://portal.microsoftazure.de/` Portal. Use Azure Portal para `https://portal.azure.com` crear redes con nombre IPv6.
 
   - No puede crear intervalos de direcciones IP de confianza para la configuración del servicio azure Multi-Factor Authentication (MFA) desde el portal de Microsoft Cloud Deutschland. Use el portal de Azure AD para los servicios de Office 365 para crear intervalos de direcciones IP de confianza de Azure MFA.


- Para el acceso condicional: 

  - Las directivas de acceso condicional con los siguientes controles de concesión no se admiten hasta que se complete la migración a los servicios de Office 365 (después de finalizar la fase de migración de [Azure AD):](ms-cloud-germany-transition.md#how-is-the-migration-organized)

    - Requerir dispositivo compatible
    - Requerir aplicación aprobada
    - Requerir directiva de protección de aplicaciones
    
  - La interfaz de directiva de acceso condicional ofrece una advertencia falsa sobre los valores predeterminados de seguridad que se habilitan para el inquilino incluso cuando está deshabilitado, y las directivas de acceso condicional ya existen para el inquilino. Debe omitir la advertencia o usar el portal de servicios de Office 365 para administrar directivas de acceso condicional. 

- Los escenarios de Intune solo se admiten en los puntos de conexión de todo el mundo una vez completada la migración de inquilinos, incluidas todas las migraciones de cargas de trabajo de Office.

- Los usuarios de Microsoft Cloud Deutschland que usan el método de notificación de aplicaciones móviles para solicitudes MFA ven el ObjectId (un GUID) del usuario en lugar del nombre principal del usuario (UPN) en la aplicación Microsoft Authenticator. Una vez completada la migración del inquilino de Azure AD y hospedada en los servicios de Office 365, las nuevas activaciones de Microsoft Authenticator mostrarán los UPN de los usuarios. Las cuentas existentes de Microsoft Authenticator seguirán mostrando el ObjectId del usuario, pero seguirán funcionando para las notificaciones de aplicaciones móviles. 

- Para los inquilinos que se crean después del 22 de octubre de 2019, los valores predeterminados de seguridad pueden habilitarse automáticamente para el inquilino cuando se migra al servicio de Office 365. Los administradores de inquilinos pueden dejar habilitados los valores predeterminados de seguridad y registrarse para MFA, o bien pueden deshabilitar la característica. Para obtener más información, vea [Deshabilitar los valores predeterminados de seguridad.](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults) 

  > [!NOTE]
  > Es posible que las organizaciones que no están habilitadas automáticamente durante la migración aún se inscriban automáticamente en el futuro, ya que la característica para habilitar los valores predeterminados de seguridad se incluye en el servicio de Office 365. Los administradores que eligen deshabilitar o habilitar explícitamente los valores predeterminados de seguridad pueden hacerlo actualizando la característica en **Azure Active Directory > Propiedades.** Después de que el administrador habilite explícitamente la característica, no se habilitará automáticamente.

- Habrá una advertencia sobre la versión de Azure AD Connect en el portal de Office 365 Germany, así como en el portal de Office 365 una vez que el inquilino esté en migración. Esto puede omitirse si la advertencia de versión ya no muestra la advertencia una vez completada la migración. Si hay una advertencia, antes o después de la migración, en cualquiera de los portales, azure AD Connect debe actualizarse. The warning message says: "We detected you're using an outdated directory sync tool. Le recomendamos que vaya al Centro de descarga de Microsoft para obtener la versión más reciente de Azure AD Connect".

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a los servicios de Office 365 en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Trabajo previo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
