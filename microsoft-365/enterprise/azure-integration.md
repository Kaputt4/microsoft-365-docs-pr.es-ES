---
title: Integración de Azure con Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integre Microsoft 365 con Azure AD si desea la sincronización de contraseñas o el inicio de sesión único con su entorno local.
ms.openlocfilehash: 9369437e556e3faf1691c2af513ace846e0ad944
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68209302"
---
# <a name="azure-integration-with-microsoft-365"></a>Integración de Azure con Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 usa Azure Active Directory (Azure AD) para administrar identidades de usuario en segundo plano. La suscripción de Microsoft 365 incluye una suscripción gratuita de Azure AD para que pueda integrar su Active Directory local Domain Services (AD DS) para sincronizar cuentas de usuario y contraseñas o configurar el inicio de sesión único. También puede comprar características avanzadas para administrar mejor sus cuentas.
  
Azure AD también ofrece otras funciones, como la administración de aplicaciones integradas, que puede usar para ampliar y personalizar las suscripciones de Microsoft 365.
  
Puede usar los asesores de implementación de Azure AD para una experiencia de configuración y configuración guiada en el Centro de administración de Microsoft 365 (debe iniciar sesión en Microsoft 365):

 - [Asesor de Azure AD Connect](https://aka.ms/aadconnectpwsync)
 - [Asesor de implementación de AD FS](https://aka.ms/adfsguidance)
 - [Guía de configuración de Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Ediciones de Azure AD y administración de identidades de Microsoft 365

Si tiene una suscripción de pago a Microsoft 365, también tiene una suscripción gratuita a Azure AD. Puede usar Azure AD para crear y administrar cuentas de usuario y grupo. Para activar esta suscripción, debe completar un registro único. Después, puede acceder a Azure AD desde el Centro de administración de Microsoft 365. 

Para obtener instrucciones para registrar la suscripción gratuita de Azure AD, consulte [Uso de la suscripción gratuita de Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). No vaya directamente a azure.microsoft.com para registrarse o terminará con una suscripción de prueba o de pago a Microsoft Azure que sea independiente de la suscripción gratuita de Azure AD con Microsoft 365. 
  
Con la suscripción gratuita, puede sincronizar con directorios locales, configurar el inicio de sesión único y sincronizar con muchas aplicaciones de software como servicio, como Salesforce, DropBox y muchas más.
  
Si desea mejorar la funcionalidad de AD DS, la sincronización bidireccional y otras funcionalidades de administración, puede actualizar la suscripción gratuita a una suscripción Premium de pago. Para más información, consulte [Ediciones de Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).
  
Para obtener más información sobre Microsoft 365 y Azure AD, consulte [Modelos de identidad de Microsoft 365](deploy-identity-solution-identity-model.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Ampliación de las funcionalidades del inquilino de Microsoft 365

|**Característica**|**Descripción**|
|:-----|:-----|
|Aplicaciones integradas  <br/> |Puede conceder a las aplicaciones individuales acceso a los datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. También puede autorizar estas aplicaciones en el nivel **de administrador de Azure AD DC** o **administrador global** y ponerlas a disposición de toda la empresa mediante el registro de las aplicaciones en Azure AD. Para más información, consulte [Aplicaciones integradas y Azure AD para administradores de Microsoft 365](integrated-apps-and-azure-ads.md).<br/> Para más información, consulte[Sobre los roles de administrador](/microsoft-365/admin/add-users/about-admin-roles?). <br/> Consulte también [Inicio de sesión único](/azure/active-directory/manage-apps/what-is-single-sign-on).  <br/> |
|Power Apps  <br/> | Power Apps son aplicaciones centradas para dispositivos móviles que pueden conectarse a los orígenes de datos existentes, como listas de SharePoint y otras aplicaciones de datos. Vea [Crear una aplicación de Power para obtener una lista en SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) y la [página De Power Apps](https://powerapps.microsoft.com/) para obtener más información.  <br/> |
   
## <a name="see-also"></a>Vea también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
