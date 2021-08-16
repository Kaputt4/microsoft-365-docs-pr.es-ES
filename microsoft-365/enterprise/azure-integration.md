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
description: Integre Microsoft 365 con Azure AD si desea la sincronización de contraseñas o el inicio de sesión único con el entorno local.
ms.openlocfilehash: 68ec6098d6873177d573e866e0361b3775be25df1b7751a77f5b589adf5503ac
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53878902"
---
# <a name="azure-integration-with-microsoft-365"></a>Integración de Azure con Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Microsoft 365 usa Azure Active Directory (Azure AD) para administrar identidades de usuario en segundo plano. La suscripción Microsoft 365 incluye una suscripción gratuita de Azure AD para que pueda integrar los Servicios de dominio de Active Directory (AD DS) locales para sincronizar cuentas de usuario y contraseñas o configurar el inicio de sesión único. También puedes comprar características avanzadas para administrar mejor tus cuentas.
  
Azure AD también ofrece otras funciones, como la administración de aplicaciones integradas, que puedes usar para ampliar y personalizar tus Microsoft 365 suscripciones.
  
Puede usar los asesores de implementación de Azure AD para una experiencia de configuración y configuración guiada en el Centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):

 - [Asesor de Conectar Azure AD](https://aka.ms/aadconnectpwsync)
 - [Asesor de implementación de AD FS](https://aka.ms/adfsguidance)
 - [Guía de configuración de Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Ediciones de Azure AD y administración Microsoft 365 identidades

Si tiene una suscripción de pago a Microsoft 365, también tiene una suscripción gratuita de Azure AD. Puede usar Azure AD para crear y administrar cuentas de usuario y grupo. Para activar esta suscripción, debe completar un registro único. Después, puede obtener acceso a Azure AD desde su Centro de administración de Microsoft 365. 

Para obtener instrucciones para registrar la suscripción gratuita de Azure AD, consulta [Usar la suscripción gratuita de Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). No vaya directamente a azure.microsoft.com para registrarse o terminará con una suscripción de prueba o de pago a Microsoft Azure que sea independiente de su suscripción gratuita de Azure AD con Microsoft 365. 
  
Con la suscripción gratuita, puede sincronizar con directorios locales, configurar el inicio de sesión único y sincronizar con muchos software como aplicaciones de servicio, como Salesforce, DropBox y muchos más.
  
Si quieres mejorar la funcionalidad de AD DS, la sincronización bidireccional y otras funciones de administración, puedes actualizar tu suscripción gratuita a una suscripción premium de pago. Para obtener más información, [vea Azure Active Directory ediciones](https://azure.microsoft.com/pricing/details/active-directory/).
  
Para obtener más información sobre Microsoft 365 y Azure AD, vea [Microsoft 365 identity models](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Ampliar las capacidades de su Microsoft 365 inquilino

|**Característica**|**Descripción**|
|:-----|:-----|
|Aplicaciones integradas  <br/> |Puedes conceder acceso a aplicaciones individuales a tus Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. También puede autorizar estas aplicaciones a nivel de administrador global y hacer que estén disponibles para toda la empresa registrando las aplicaciones en Azure AD. Para obtener más información, vea [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).  <br/> Vea también [Inicio de sesión único](/azure/active-directory/manage-apps/what-is-single-sign-on).  <br/> |
|PowerApps  <br/> | Las aplicaciones de energía son aplicaciones centradas para dispositivos móviles que pueden conectarse a los orígenes de datos existentes, como SharePoint listas de datos y otras aplicaciones de datos. Consulta [Crear una PowerApp para obtener una](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) lista en SharePoint Online y la página [PowerApps](https://powerapps.microsoft.com/) para obtener más información.  <br/> |
   
## <a name="see-also"></a>Consulte también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)