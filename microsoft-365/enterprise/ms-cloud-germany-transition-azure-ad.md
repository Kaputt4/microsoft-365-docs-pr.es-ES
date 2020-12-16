---
title: Información adicional de Azure Active Directory para la migración desde la nube de Microsoft Alemania
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
description: 'Resumen: información adicional de Azure Active Directory al cambiar de Microsoft Cloud Germany (Microsoft Cloud Alemania) a Office 365 Services en la nueva región del centro de datos en alemán.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688837"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Información adicional de Azure Active Directory para la migración desde la nube de Microsoft Alemania

Para completar el traslado de la nube de Azure en alemán a la nube pública de Azure, se recomienda actualizar el punto de conexión de autenticación, el gráfico de Azure Active Directory (Azure AD) y los puntos de conexión de MS Graph de las aplicaciones a los de la nube comercial, cuando el punto de conexión de OpenID Connect (OIDC), `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` inicia la notificación de puntos de conexión de nube comercial. 
 
**¿Cuándo debería realizar este cambio?**

Recibirá una notificación en el portal de Azure/Office cuando el inquilino complete la migración de la nube alemana a la nube comercial. Tiene 30 días después de recibir esta notificación para completar estas actualizaciones, de modo que la aplicación siga funcionando para los inquilinos que se migren desde la nube de Azure Germany a la nube pública de Azure.
 
Hay tres condiciones previas para actualizar la autoridad de inicio de sesión:

 - OIDC punto de conexión de detección del inquilino `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` devuelve los puntos de conexión de la nube pública de Azure ad.

 - Si el espacio empresarial está configurado para la Federación, los servicios de Federación de Active Directory (AD FS) se actualizan para sincronizarse con Azure AD público. Puede seguir las instrucciones para actualizar la configuración de Azure AD Connect para realizar este cambio.

 - Las aplicaciones de recursos, si las hay, usadas por las aplicaciones se modifican para aceptar tokens firmados por Azure AD Germany y Azure AD público.
 
**¿Qué tipo de aplicaciones?**

Una aplicación puede ser una de las siguientes:

- [Aplicación de una sola página (SPA)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [Aplicación web que inicia sesión en los usuarios](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Aplicación web que llama a las API Web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [API Web protegida](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [API Web que llama a las API Web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Aplicación de escritorio](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [Aplicación demonio](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [Aplicación móvil](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Cuando una aplicación cambia a usar `login.microsoftonline.com` como su autoridad, los tokens serán firmados por esta nueva entidad de certificación. Si hospeda aplicaciones de recursos en las que otras aplicaciones llaman, deberá permitir la validación de tokens LAX. Esto significa que la aplicación debe permitir tokens que estén firmados por las nubes públicas de Azure AD Alemania y Azure AD. Esta validación de token de LAX es necesaria hasta que todas las aplicaciones cliente que llaman a su servicio se migren por completo a la nube pública de Azure AD. Después de la migración, la aplicación de recursos solo necesita aceptar tokens firmados por la nube pública de Azure AD.

**¿Qué es necesario actualizar?**

1. Si hospeda una aplicación en Azure Germany que se usa para autenticar usuarios de Azure Germany o Office 365 Germany, asegúrese de que `https://login.microsoftonline.com` se usa como la autoridad en el contexto de autenticación.

    - Consulte contextos de autenticación de Azure AD.
    - Esto se aplica tanto a la autenticación en su aplicación como a cualquier API a la que pueda llamar la aplicación (es decir, Microsoft Graph, el gráfico de Azure AD, el administrador de recursos de Azure).

2. Actualizar el extremo de Azure AD Graph `https://graph.windows.net` .

3. Actualizar el extremo de MS Graph `https://graph.microsoft.com` .

4. Actualice los puntos de conexión de nube en alemán (como los de Exchange Online y SharePoint Online) que las aplicaciones usan para que sean los de la nube pública.

5. Actualice los parámetros de entorno para que sean `AzurePublic` (en lugar de `AzureGermany` ) en las herramientas de administración y los scripts para:

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [PowerShell de Azure AD (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [PowerShell de Azure AD (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**¿Qué ocurre con las aplicaciones que se publican?**

Si publica una aplicación que está disponible para los usuarios que están fuera de su inquilino, es posible que deba cambiar el registro de la aplicación para garantizar la continuidad. Otros inquilinos que usan la aplicación pueden moverse en un tiempo diferente al del espacio empresarial. Para asegurarse de que nunca pierdan el acceso a la aplicación, deberá dar su consentimiento a la aplicación que se está sincronizando desde Azure Germany a Azure Public.

## <a name="additional-considerations"></a>Consideraciones adicionales

Estas son algunas consideraciones adicionales para Azure AD:

- Para la autenticación federada:

  - No debe crear, promover o disminuir el nivel de un dominio federado mientras la transición de inquilino esté en proceso. Una vez finalizada la migración al servicio de Azure AD (el inquilino se ha completado completamente), puede reanudar la administración de dominios federados.

  - Si está usando la autenticación federada con los servicios de Federación de Active Directory (AD FS), no debe realizar cambios en las URI del emisor usadas para toda la autenticación con los servicios de dominio de Active Directory (AD DS) locales durante la migración. Cambiar los URI del emisor conducirá a errores de autenticación para los usuarios del dominio. Los URI del emisor se pueden cambiar directamente en AD FS o cuando un dominio se convierte de administrado a federado y viceversa. Microsoft recomienda a los clientes no agregar, quitar ni convertir un dominio federado en el inquilino de Azure AD que se está migrando. Los URI del emisor se pueden cambiar una vez que la migración se haya completado completamente.

- Para redes:

  - La creación de redes con nombre IPv6 no funciona en Azure portal `http://portal.microsoftazure.de/` . Use Azure portal en `https://portal.azure.com` para crear redes con nombre IPv6.
 
   - No puede crear intervalos de direcciones IP de confianza para la configuración del servicio de Azure multi-factor Authentication (MFA) en Microsoft Cloud Alemania portal. Use el portal de Azure AD para los servicios de Office 365 para crear intervalos de direcciones IP de confianza de Azure MFA.


- Para el acceso condicional: 

  - Las directivas de acceso condicional con los siguientes controles Grant no se admiten hasta que se complete la migración a Office 365 Services (después de la finalización de la fase de migración de [Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) ):

    - Requerir dispositivo compatible
    - Requerir una aplicación aprobada
    - Requerir Directiva de protección de aplicaciones
    
  - La interfaz de directiva de acceso condicional da una falsa Advertencia sobre la habilitación de los valores predeterminados de seguridad para el inquilino, incluso cuando está deshabilitado, y las directivas de acceso condicional ya existen para el inquilino. Debe omitir la advertencia o usar el portal de servicios de Office 365 para administrar las directivas de acceso condicional. 

- Los escenarios de Intune solo se admiten en extremos mundiales tras la finalización de la migración de inquilinos, incluidas todas las migraciones de cargas de trabajo de Office.

- Microsoft Cloud Alemania los usuarios que usan el método de notificación de aplicaciones móviles para solicitudes de MFA ven el ObjectId del usuario (un GUID) en lugar del nombre principal del usuario (UPN) en la aplicación Microsoft Authenticator. Después de que se complete la migración del inquilino de Azure AD y se hospede en los servicios de Office 365, las nuevas activaciones de Microsoft Authenticator mostrarán los UPN de los usuarios. Las cuentas existentes de Microsoft Authenticator seguirán mostrando el usuario ObjectId, pero seguirán trabajando para notificaciones de aplicaciones móviles. 

- Para los inquilinos que se crean después del 22 de octubre de 2019, los valores predeterminados de seguridad pueden estar habilitados automáticamente para el inquilino cuando se migre al servicio de Office 365. Los administradores de inquilinos pueden elegir dejar los valores predeterminados de seguridad habilitados y registrarse para MFA, o pueden deshabilitar la característica. Para obtener más información, vea [deshabilitar los valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults). 

  > [!NOTE]
  > Es posible que las organizaciones que no se habilitan automáticamente durante la migración se puedan inscribir automáticamente en el futuro, ya que la característica para habilitar los valores predeterminados de seguridad se implementa en el servicio de Office 365. Los administradores que elijan o deshabiliten explícitamente los valores predeterminados de seguridad pueden hacerlo si actualizan la característica en **propiedades > de Azure Active Directory**. Una vez que el administrador haya habilitado la característica explícitamente, no se habilitará automáticamente.

- Se mostrará una advertencia sobre la versión de Azure AD Connect en el portal de Office 365 Germany y en el portal de Office 365 una vez que el inquilino se encuentra en la migración. Esto puede pasarse por alto si la advertencia de versión ya no muestra la advertencia una vez finalizada la migración. Si hay una advertencia, ya sea antes o después de la migración, en cualquier portal, debe actualizarse Azure AD Connect. El mensaje de advertencia dice: "se detectó que está usando una herramienta de sincronización de directorios obsoleta. Le recomendamos que vaya al centro de descarga de Microsoft para obtener la versión más reciente de Azure AD Connect. "

## <a name="more-information"></a>Más información

Introducción:

- [Migración desde Microsoft Cloud Alemania a Office 365 Services en las nuevas regiones del centro de administración de Office en alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Desplazarse por la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-trabajo adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](https://aka.ms/d365ceoptin)
- [Información del programa de migración de Power BI](https://aka.ms/pbioptin)
- [Introducción a su actualización de Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
