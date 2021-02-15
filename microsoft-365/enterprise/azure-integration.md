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
description: Integre Microsoft 365 con Azure AD si desea sincronizar la contraseña o el inicio de sesión único con su entorno local.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384745"
---
# <a name="azure-integration-with-microsoft-365"></a>Integración de Azure con Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 usa Azure Active Directory (Azure AD) para administrar identidades de usuario en segundo plano. Su suscripción de Microsoft 365 incluye una suscripción gratuita de Azure AD para que pueda integrar los Servicios de dominio de Active Directory (AD DS) locales para sincronizar las cuentas de usuario y contraseñas o configurar el inicio de sesión único. También puedes comprar características avanzadas para administrar mejor tus cuentas.
  
Azure AD también ofrece otras funciones, como la administración de aplicaciones integradas, que puede usar para ampliar y personalizar las suscripciones de Microsoft 365.
  
Puede usar los asesores de implementación de Azure AD para una experiencia de configuración y configuración guiada en el Centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):

 - [Asesor de Azure AD Connect](https://aka.ms/aadconnectpwsync)
 - [Asesor de implementación de AD FS](https://aka.ms/adfsguidance)
 - [Guía de configuración de Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Ediciones de Azure AD y administración de identidades de Microsoft 365

Si tiene una suscripción de pago a Microsoft 365, también tiene una suscripción gratuita de Azure AD. Puede usar Azure AD para crear y administrar cuentas de usuario y grupo. Para activar esta suscripción, debe completar un registro único. Después, puede acceder a Azure AD desde el Centro de administración de Microsoft 365. 

Para obtener instrucciones para registrar tu suscripción gratuita de Azure AD, consulta usar la suscripción gratuita [de Azure AD.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) No vaya directamente a azure.microsoft.com para registrarse o terminará con una suscripción de prueba o de pago a Microsoft Azure que sea independiente de su suscripción gratuita de Azure AD con Microsoft 365. 
  
Con la suscripción gratuita puede sincronizarse con directorios locales, configurar el inicio de sesión único y sincronizarse con muchos software como aplicaciones de servicio, como Salesforce, DropBox y muchos más.
  
Si quieres mejorar la funcionalidad de AD DS, la sincronización bidireccional y otras funcionalidades de administración, puedes actualizar tu suscripción gratuita a una suscripción premium de pago. Para obtener más información, [vea las ediciones de Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)
  
Para obtener más información acerca de Microsoft 365 y Azure AD, vea modelos de [identidad de Microsoft 365.](about-microsoft-365-identity.md)
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Ampliar las capacidades de su inquilino de Microsoft 365

|**Característica**|**Descripción**|
|:-----|:-----|
|Aplicaciones integradas  <br/> |Puede conceder acceso a aplicaciones individuales a los datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. También puedes autorizar estas aplicaciones en el nivel de administrador global y hacer que estén disponibles para toda la empresa registrando las aplicaciones en Azure AD. Para obtener más información, vea [Aplicaciones integradas y Azure AD para administradores de Microsoft 365.](integrated-apps-and-azure-ads.md)  <br/> Consulta también [Inicio de sesión único.](https://go.microsoft.com/fwlink/p/?LinkId=698604)  <br/> |
|PowerApps  <br/> | Las aplicaciones power son aplicaciones centradas para dispositivos móviles que pueden conectarse a los orígenes de datos existentes, como listas de SharePoint y otras aplicaciones de datos. Para obtener más información, vea Crear una PowerApp para obtener una lista [en SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) y la página de [PowerApps.](https://powerapps.microsoft.com/)  <br/> |
   
## <a name="see-also"></a>Vea también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
