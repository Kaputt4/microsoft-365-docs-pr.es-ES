---
title: Aplicaciones integradas y Azure AD para administradores de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: landing-page
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- scotvorg
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: Obtenga información sobre cómo registrar y administrar Office 365 aplicaciones integradas en Azure AD, lo que permite las autorizaciones de aplicaciones en el nivel de administrador global o administrador **global** de **Azure AD DC**.
ms.openlocfilehash: fac21bb980623c0456727593840628aa2753027e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68208906"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Aplicaciones integradas y Azure AD para administradores de Microsoft 365

La administración de aplicaciones integradas tiene más que ver con [la administración del consentimiento del usuario a las aplicaciones](../admin/misc/user-consent.md). Con la llegada de las API REST de Microsoft 365, los usuarios pueden conceder a las aplicaciones acceso a sus datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. De forma predeterminada, los usuarios deben conceder permisos individualmente a cada aplicación. 

Pero esto no se escala bien si quiere autorizar una aplicación una vez en el nivel de **administrador de Azure AD DC** o **de administrador global** y implementarla en toda la organización a través del iniciador de aplicaciones. Para ello, debe registrar la aplicación en Azure Active Directory (Azure AD). Hay algunos pasos que debe seguir para poder registrar una aplicación en Azure AD y alguna información de fondo que debe saber que puede ayudarle a administrar aplicaciones en su organización de Microsoft 365.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Recursos de Azure AD para administradores de Microsoft 365

Debe realizar estas dos tareas para poder administrar las aplicaciones de Microsoft 365 en Azure AD.
  
|Requisitos previos|Comentarios|
|:-----|:-----|
|[Uso de la suscripción gratuita de Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Cada suscripción de pago a Microsoft 365 incluye una suscripción gratuita a Azure AD. Puede usar Azure AD para administrar las aplicaciones y para crear y administrar cuentas de usuario y grupo. Para usar Azure AD, vaya a la Azure Portal en [https://portal.azure.com](https://portal.azure.com) e inicie sesión con su cuenta de Microsoft 365.  <br/> |
|[Administración del consentimiento del usuario a las aplicaciones](../admin/misc/user-consent.md) <br/> |Debe administrar el consentimiento del usuario a las aplicaciones para permitir que las aplicaciones de terceros accedan a la información de Microsoft 365 del usuario y que registre aplicaciones en Azure AD. Por ejemplo, cuando alguien usa una aplicación de terceros, puede que la aplicación le pida permiso para tener acceso a su calendario y para modificar los archivos que están en una carpeta de OneDrive.  <br/> |
   
La administración de aplicaciones de Microsoft 365 requiere que tenga conocimientos sobre las aplicaciones en Azure AD. Use estos artículos para proporcionarle los antecedentes que necesita.
  
|Artículo|Comentarios|
|:-----|:-----|
|[Conozca el iniciador de aplicaciones de Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Si no está familiarizado con el iniciador de aplicaciones, es posible que se pregunte qué es y cómo usarlo. El iniciador de aplicaciones está diseñado para ayudarle a llegar a sus aplicaciones desde cualquier lugar de Microsoft 365.  <br/> |
|[Introducción a las API de administración de Office 365](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Las API de administración de Microsoft 365 le permiten proporcionar acceso a los datos de Microsoft 365, incluidos los aspectos que más les importan: su correo, calendarios, contactos, usuarios y grupos, archivos y carpetas. <br/> |
|[Integración de aplicaciones en Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Obtenga información sobre las aplicaciones que se integran con Azure AD y cómo registrar la aplicación, comprender los conceptos detrás de una aplicación registrada y obtener información sobre las directrices de personalización de marca para aplicaciones multiinquilino.  <br/> |
|[Adición de iconos personalizados al iniciador de aplicaciones](/office365/admin/manage/customize-the-app-launcher)  <br/> |El iniciador de aplicaciones de Microsoft 365 facilita a los usuarios la búsqueda y el acceso a sus aplicaciones. En este artículo se describen las formas en que como desarrollador puede hacer que las aplicaciones aparezcan en los iniciadores de aplicaciones de los usuarios y también darles una experiencia de inicio de sesión único (SSO) con sus credenciales de Microsoft 365.  <br/> |
|[Tutoriales de integración de Azure AD](/azure/active-directory/saas-apps/tutorial-list) <br/> |El objetivo de estos tutoriales es mostrar cómo configurar el inicio de sesión único de Azure AD para aplicaciones SaaS de terceros.  <br/> |
|[Escenarios de autenticación de Azure AD](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD simplifica la autenticación para los desarrolladores proporcionando identidad como servicio, con compatibilidad con protocolos estándar del sector como OAuth 2.0 y OpenID Connect, así como bibliotecas de código abierto para distintas plataformas que le ayudarán a empezar a codificar rápidamente. Este documento le ayuda a comprender los distintos escenarios que admite Azure AD y le muestra cómo empezar a trabajar.  <br/> |
|[Acceso a la aplicación](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD permite una fácil integración con muchas de las aplicaciones de software como servicio (SaaS) más populares de hoy en día. Proporciona administración de identidades y acceso, y ofrece una Panel de acceso para los usuarios donde pueden descubrir qué acceso a la aplicación tienen y dónde pueden usar el inicio de sesión único para acceder a sus aplicaciones. En este artículo se proporcionan vínculos a los recursos relacionados que le permiten obtener más información sobre las mejoras de acceso a aplicaciones para Azure AD y cómo puede contribuir a ellos.  <br/> |
|[Personalizar la experiencia de Office 365](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Puede obtener acceso rápido a las aplicaciones que usa todos los días agregando o quitando aplicaciones en el iniciador de aplicaciones de Microsoft 365.  <br/> |
