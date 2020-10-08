---
title: Integración de Azure con Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
description: Integre Microsoft 365 con Azure AD si desea la sincronización de contraseña o el inicio de sesión único con el entorno local.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384745"
---
# <a name="azure-integration-with-microsoft-365"></a>Integración de Azure con Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 usa Azure Active Directory (Azure AD) para administrar las identidades de usuario en segundo plano. Su suscripción a Microsoft 365 incluye una suscripción gratuita a Azure AD para que pueda integrar los servicios de dominio de Active Directory (AD DS) locales para sincronizar las cuentas de usuario y las contraseñas o configurar el inicio de sesión único. También puede comprar características avanzadas para administrar mejor sus cuentas.
  
Azure AD también ofrece otras funciones, como la administración de aplicaciones integradas, que puede usar para ampliar y personalizar sus suscripciones de Microsoft 365.
  
Puede usar los asesores de implementación de Azure AD para una instalación guiada y una experiencia de configuración en el centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):

 - [Azure AD Connect Advisor](https://aka.ms/aadconnectpwsync)
 - [Asesor de implementación de AD FS](https://aka.ms/adfsguidance)
 - [Guía de configuración de Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD Editions y Microsoft 365 Identity Management

Si tiene una suscripción de pago a Microsoft 365, también tiene una suscripción gratuita de Azure AD. Puede usar Azure AD para crear y administrar cuentas de grupo y de usuario. Para activar esta suscripción, debe realizar un registro único. Después, puede obtener acceso a Azure AD desde el centro de administración de Microsoft 365. 

Para obtener instrucciones sobre cómo registrar su suscripción gratuita a Azure AD, consulte [usar su suscripción gratuita a Azure ad](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). No vaya directamente a azure.microsoft.com para registrarse o obtendrá una suscripción de prueba o de pago a Microsoft Azure que es independiente de su suscripción gratuita a Azure AD con Microsoft 365. 
  
Con la suscripción gratuita, puede sincronizar con directorios locales, configurar el inicio de sesión único y sincronizar con muchos software como aplicaciones de servicio, como Salesforce, DropBox y muchos más.
  
Si desea funcionalidad de AD DS mejorada, sincronización bidireccional y otras capacidades de administración, puede actualizar su suscripción gratuita a una suscripción Premium de pago. Para obtener información detallada, consulte [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).
  
Para obtener más información acerca de Microsoft 365 y Azure AD, consulte [modelos de identidad de 365 de Microsoft](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Ampliar las capacidades de su inquilino de Microsoft 365

|**Característica**|**Descripción**|
|:-----|:-----|
|Aplicaciones integradas  <br/> |Puede conceder acceso a aplicaciones individuales a sus datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. También puede autorizar estas aplicaciones en el nivel de administrador global y ponerlas a disposición de toda la empresa registrando las aplicaciones en Azure AD. Formore información, vea [aplicaciones integradas y Azure ad para administradores de Microsoft 365](integrated-apps-and-azure-ads.md).  <br/> Consulte también [Inicio de sesión único (Single Sign-on)](https://go.microsoft.com/fwlink/p/?LinkId=698604).  <br/> |
|PowerApps  <br/> | Las aplicaciones Power se centran en aplicaciones para dispositivos móviles que se pueden conectar a los orígenes de datos existentes, como las listas de SharePoint y otras aplicaciones de datos. Consulte [Create a PowerApp for a List in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) y la [Página PowerApps](https://powerapps.microsoft.com/) para obtener más información.  <br/> |
   
## <a name="see-also"></a>Consulte también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
