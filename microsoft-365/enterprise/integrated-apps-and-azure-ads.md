---
title: Aplicaciones integradas y Azure AD para administradores de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Obtenga información sobre cómo registrar y administrar aplicaciones integradas de Office 365 en Azure AD, lo que permite autorizar las aplicaciones en el nivel de administrador global.
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384906"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Aplicaciones integradas y Azure AD para administradores de Microsoft 365

Hay más información sobre la administración de aplicaciones integradas que solo la [Administración del consentimiento del usuario para las aplicaciones](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps). Con la llegada de las API de REST de 365 de Microsoft, los usuarios pueden conceder acceso a las aplicaciones a sus datos de 365 de Microsoft, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. De forma predeterminada, los usuarios deben conceder individualmente permisos para cada aplicación. 

Pero esto no escala bien si desea autorizar una aplicación una vez en el nivel de administrador global y aplicarla a toda la organización a través del iniciador de aplicaciones. Para ello, debe registrar la aplicación en Azure Active Directory (Azure AD). Hay algunos pasos que debe tener en cuenta antes de poder registrar una aplicación en Azure AD y la información básica que necesita saber que puede ayudarle a administrar las aplicaciones de su organización de Microsoft 365.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Recursos de Azure AD para administradores de Microsoft 365

Tiene que realizar estas dos tareas antes de poder administrar las aplicaciones de Microsoft 365 en Azure AD.
  
|Requisitos previos|Comentarios|
|:-----|:-----|
|[Usar su suscripción gratuita a Azure AD](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Todas las suscripciones de pago a Microsoft 365 incluyen una suscripción gratuita a Azure AD. Puede usar Azure AD para administrar las aplicaciones y para crear y administrar cuentas de usuario y de grupo. Para usar Azure AD, solo tiene que ir a Azure portal en [https://portal.azure.com](https://portal.azure.com) e iniciar sesión con su cuenta de Microsoft 365.  <br/> |
|[Administrar el consentimiento del usuario para las aplicaciones](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |Debe administrar el consentimiento del usuario a las aplicaciones para permitir a las aplicaciones de terceros el acceso a la información de Microsoft 365 del usuario y para registrar aplicaciones en Azure AD. Por ejemplo, cuando alguien usa una aplicación de terceros, puede que la aplicación le pida permiso para tener acceso a su calendario y para modificar los archivos que están en una carpeta de OneDrive.  <br/> |
   
Para administrar las aplicaciones de 365 de Microsoft, es necesario tener conocimientos de las aplicaciones en Azure AD. Use estos artículos para proporcionar el fondo que necesite.
  
|Artículo|Comentarios|
|:-----|:-----|
|[Conozca el iniciador de aplicaciones de 365 de Microsoft](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Si no está familiarizado con el iniciador de aplicaciones, es posible que se pregunte qué es y cómo usarlo. El iniciador de aplicaciones está diseñado para ayudarle a acceder a sus aplicaciones desde cualquier lugar en Microsoft 365.  <br/> |
|[Información general sobre las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Las API de administración de 365 de Microsoft le permiten proporcionar acceso a los datos de Microsoft 365, incluidos los aspectos que le interesan de la mayoría: el correo, los calendarios, los contactos, los usuarios y grupos, los archivos y las carpetas. <br/> |
|[Integración de aplicaciones en Azure AD](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Obtenga información sobre las aplicaciones que se integran con Azure AD y cómo registrar la aplicación, comprender los conceptos de una aplicación registrada y obtener información sobre las pautas de personalización de marca para las aplicaciones multiinquilino.  <br/> |
|[Agregar mosaicos personalizados al iniciador de aplicaciones](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |El iniciador de aplicaciones de Microsoft 365 facilita a los usuarios la búsqueda y el acceso a sus aplicaciones. En este artículo se describen las formas en las que el desarrollador puede hacer que las aplicaciones aparezcan en los iniciadores de aplicaciones de los usuarios y darles una experiencia de inicio de sesión único (SSO) mediante sus credenciales de Microsoft 365.  <br/> |
|[Tutoriales de integración de Azure AD](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |El objetivo de estos tutoriales es mostrarle cómo configurar el SSO de Azure AD para las aplicaciones SaaS de terceros.  <br/> |
|[Escenarios de autenticación de Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD simplifica la autenticación para los desarrolladores al proporcionar identidad como un servicio, con compatibilidad para protocolos estándar de la industria como OAuth 2,0 y OpenID Connect, así como bibliotecas de código abierto para diferentes plataformas que le ayudarán a empezar a codificar rápidamente. Este documento le ayuda a comprender los diversos escenarios que Azure AD admite y le muestra cómo empezar.  <br/> |
|[Acceso a la aplicación](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD permite una integración sencilla con muchas de las aplicaciones de software de hoy en día (SaaS) más conocidas. Proporciona administración de identidades y acceso, y ofrece un panel de acceso para los usuarios donde pueden descubrir qué acceso a la aplicación tienen y dónde pueden usar SSO para obtener acceso a sus aplicaciones. En este artículo se proporcionan vínculos a los recursos relacionados que le permiten obtener más información sobre las mejoras de acceso a la aplicación para Azure AD y cómo puede contribuir a ellas.  <br/> |
|[Personalizar su experiencia de Office 365](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Puede obtener acceso rápido a las aplicaciones que usa cada día si agrega o quita aplicaciones en el iniciador de aplicaciones de Microsoft 365.  <br/> |

