---
title: Aplicaciones integradas y Azure AD para Microsoft 365 administradores
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
description: Obtenga información sobre cómo registrar y administrar Office 365 aplicaciones integradas en Azure AD, lo que permite las autorizaciones de aplicaciones en el nivel de administrador global.
ms.openlocfilehash: 0b7392984b77b01abb0992fea5db62b80ed9fb6c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909779"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Aplicaciones integradas y Azure AD para Microsoft 365 administradores

Hay más que administrar aplicaciones integradas que administrar el consentimiento [de los usuarios para las aplicaciones.](../admin/misc/user-consent.md) Con la llegada de las API de REST de Microsoft 365, los usuarios pueden conceder a las aplicaciones acceso a sus datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. De forma predeterminada, los usuarios necesitan conceder permisos individualmente a cada aplicación. 

Pero esto no se escala bien si quieres autorizar una aplicación una vez en el nivel de administrador global y realizarla en toda la organización a través del iniciador de aplicaciones. Para ello, debes registrar la aplicación en Azure Active Directory (Azure AD). Hay algunos pasos que debe seguir antes de poder registrar una aplicación en Azure AD y alguna información en segundo plano que debe saber que puede ayudarle a administrar aplicaciones en su Microsoft 365 organización.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Recursos de Azure AD para Microsoft 365 administradores

Debe realizar estas dos tareas para poder administrar las aplicaciones Microsoft 365 en Azure AD.
  
|Requisitos previos|Comentarios|
|:-----|:-----|
|[Usar la suscripción gratuita de Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Cada suscripción de pago Microsoft 365 incluye una suscripción gratuita a Azure AD. Puede usar Azure AD para administrar las aplicaciones y para crear y administrar cuentas de usuario y grupo. Para usar Azure AD, solo tiene que ir a Azure Portal en [https://portal.azure.com](https://portal.azure.com) e iniciar sesión con su Microsoft 365 cuenta.  <br/> |
|[Administrar el consentimiento del usuario a las aplicaciones](../admin/misc/user-consent.md) <br/> |Debe administrar el consentimiento del usuario a las aplicaciones para permitir que las aplicaciones de terceros accedan a la información de Microsoft 365 y para que registre aplicaciones en Azure AD. Por ejemplo, cuando alguien usa una aplicación de terceros, puede que la aplicación le pida permiso para tener acceso a su calendario y para modificar los archivos que están en una carpeta de OneDrive.  <br/> |
   
La administración Microsoft 365 aplicaciones requiere que tenga conocimientos de aplicaciones en Azure AD. Use estos artículos para proporcionar el fondo que necesita.
  
|Artículo|Comentarios|
|:-----|:-----|
|[Conoce el iniciador Microsoft 365 aplicaciones](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Si eres nuevo en el iniciador de aplicaciones, es posible que te estés preguntando qué es y cómo usarlo. El iniciador de aplicaciones está diseñado para ayudarte a llegar a tus aplicaciones desde cualquier lugar de Microsoft 365.  <br/> |
|[Office 365 de api de administración](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Las API de administración de Microsoft 365 permiten proporcionar acceso a los datos de Microsoft 365, incluidos los aspectos que más les importan: su correo, calendarios, contactos, usuarios y grupos, archivos y carpetas. <br/> |
|[Integración de aplicaciones en Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Obtenga información sobre las aplicaciones que están integradas con Azure AD y cómo registrar la aplicación, comprender los conceptos detrás de una aplicación registrada y obtener información sobre las directrices de personal de marca para aplicaciones multiinquilino.  <br/> |
|[Agregar iconos personalizados al iniciador de aplicaciones](/office365/admin/manage/customize-the-app-launcher)  <br/> |El iniciador de aplicaciones Microsoft 365 facilita a los usuarios la búsqueda y el acceso a sus aplicaciones. En este artículo se describen las formas en que usted como desarrollador puede hacer que sus aplicaciones aparezcan en los iniciadores de aplicaciones de los usuarios y también darles una experiencia de inicio de sesión único (SSO) con sus credenciales Microsoft 365 usuario.  <br/> |
|[Tutoriales de integración de Azure AD](/azure/active-directory/saas-apps/tutorial-list) <br/> |El objetivo de estos tutoriales es mostrarte cómo configurar sso de Azure AD para aplicaciones SaaS de terceros.  <br/> |
|[Escenarios de autenticación de Azure AD](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD simplifica la autenticación para desarrolladores proporcionando identidad como servicio, con compatibilidad con protocolos estándar del sector como OAuth 2.0 y OpenID Conectar, así como bibliotecas de código abierto para diferentes plataformas que le ayudarán a empezar a codificar rápidamente. Este documento le ayuda a comprender los distintos escenarios que Admite Azure AD y le muestra cómo empezar.  <br/> |
|[Acceso a aplicaciones](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD permite una integración sencilla en muchas de las aplicaciones de software populares como servicio (SaaS) actuales. Proporciona administración de identidades y acceso, y proporciona un Panel de acceso para los usuarios donde pueden descubrir qué acceso de aplicación tienen y dónde pueden usar SSO para acceder a sus aplicaciones. Este artículo le proporciona vínculos a los recursos relacionados que le permiten obtener más información sobre las mejoras de acceso a aplicaciones para Azure AD y cómo puede contribuir a ellos.  <br/> |
|[Personalizar su Office 365 experiencia](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Puedes obtener acceso rápido a las aplicaciones que usas todos los días agregando o quitando aplicaciones en el iniciador Microsoft 365 aplicaciones.  <br/> |