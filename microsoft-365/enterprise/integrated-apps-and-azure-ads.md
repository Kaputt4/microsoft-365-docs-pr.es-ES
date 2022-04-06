---
title: Aplicaciones integradas y Azure AD para Microsoft 365 administradores
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: landing-page
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Obtén información sobre cómo registrar y administrar Office 365 aplicaciones integradas en Azure AD, lo que permite las autorizaciones de aplicaciones en el nivel Azure AD **administrador de DC** o **administrador global.**
ms.openlocfilehash: ddb22c6e1be3d337fe7b54f27cae6a197f823c71
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681268"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Aplicaciones integradas y Azure AD para Microsoft 365 administradores

Hay más que administrar aplicaciones integradas que administrar el consentimiento [de los usuarios para las aplicaciones](../admin/misc/user-consent.md). Con la llegada de las API de REST de Microsoft 365, los usuarios pueden conceder a las aplicaciones acceso a sus datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. De forma predeterminada, los usuarios necesitan conceder permisos individualmente a cada aplicación. 

Pero esto no se escala bien si quieres autorizar una aplicación una vez en el nivel de administrador de **DC de Azure AD** o en el  nivel de administrador global y la revierte a toda la organización a través del iniciador de aplicaciones. Para ello, debes registrar la aplicación en Azure Active Directory (Azure AD). Hay algunos pasos que debes seguir antes de registrar una aplicación en Azure AD y alguna información en segundo plano que debes saber que puede ayudarte a administrar aplicaciones en tu Microsoft 365 organización.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Azure AD recursos para Microsoft 365 administradores

Debes realizar estas dos tareas antes de poder administrar las aplicaciones Microsoft 365 en Azure AD.
  
|Requisitos previos|Comentarios|
|:-----|:-----|
|[Usar la suscripción Azure AD gratuita](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |Cada suscripción de pago Microsoft 365 incluye una suscripción gratuita a Azure AD. Puedes usar Azure AD para administrar tus aplicaciones y para crear y administrar cuentas de usuario y grupo. Para usar Azure AD, solo tienes que ir a Azure Portal en [https://portal.azure.com](https://portal.azure.com) e iniciar sesión con tu cuenta Microsoft 365 usuario.  <br/> |
|[Administrar el consentimiento del usuario a las aplicaciones](../admin/misc/user-consent.md) <br/> |Debes administrar el consentimiento del usuario a las aplicaciones para permitir que las aplicaciones de terceros accedan a la información del usuario Microsoft 365 y para que registres aplicaciones en Azure AD. Por ejemplo, cuando alguien usa una aplicación de terceros, puede que la aplicación le pida permiso para tener acceso a su calendario y para modificar los archivos que están en una carpeta de OneDrive.  <br/> |
   
Administrar Microsoft 365 aplicaciones requiere que tenga conocimientos de aplicaciones en Azure AD. Use estos artículos para proporcionar el fondo que necesita.
  
|Artículo|Comentarios|
|:-----|:-----|
|[Conoce el iniciador Microsoft 365 aplicaciones](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Si eres nuevo en el iniciador de aplicaciones, es posible que te estés preguntando qué es y cómo usarlo. El iniciador de aplicaciones está diseñado para ayudarte a llegar a tus aplicaciones desde cualquier lugar de Microsoft 365.  <br/> |
|[Office 365 de api de administración](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Las API de administración de Microsoft 365 permiten proporcionar acceso a los datos de Microsoft 365, incluidos los aspectos que más les importan: su correo, calendarios, contactos, usuarios y grupos, archivos y carpetas. <br/> |
|[Integración de aplicaciones en Azure AD](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Obtenga información sobre las aplicaciones que están integradas con Azure AD y cómo registrar la aplicación, comprender los conceptos detrás de una aplicación registrada y obtener información sobre las directrices de personal de marca para aplicaciones multiinquilino.  <br/> |
|[Agregar iconos personalizados al iniciador de aplicaciones](/office365/admin/manage/customize-the-app-launcher)  <br/> |El iniciador de aplicaciones Microsoft 365 facilita a los usuarios la búsqueda y el acceso a sus aplicaciones. En este artículo se describen las formas en que usted como desarrollador puede hacer que sus aplicaciones aparezcan en los iniciadores de aplicaciones de los usuarios y también darles una experiencia de inicio de sesión único (SSO) con sus credenciales Microsoft 365 usuario.  <br/> |
|[Azure AD tutoriales de integración](/azure/active-directory/saas-apps/tutorial-list) <br/> |El objetivo de estos tutoriales es mostrarte cómo configurar Azure AD SSO para aplicaciones SaaS de terceros.  <br/> |
|[Escenarios de autenticación de Azure AD](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD simplifica la autenticación para desarrolladores proporcionando identidad como servicio, con compatibilidad con protocolos estándar del sector como OAuth 2.0 y OpenID Conectar, así como bibliotecas de código abierto para diferentes plataformas que le ayudarán a iniciar rápidamente la codificación. Este documento le ayuda a comprender los distintos escenarios Azure AD admite y le muestra cómo empezar.  <br/> |
|[Acceso a aplicaciones](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD facilita la integración de muchas de las aplicaciones de software como servicio (SaaS) populares de hoy en día. Proporciona administración de identidades y acceso, y proporciona un Panel de acceso para los usuarios donde pueden descubrir qué acceso de aplicación tienen y dónde pueden usar SSO para acceder a sus aplicaciones. Este artículo le proporciona vínculos a los recursos relacionados que le permiten obtener más información sobre las mejoras de acceso de aplicaciones para Azure AD y cómo puede contribuir a ellos.  <br/> |
|[Personalizar su Office 365 experiencia](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Puedes obtener acceso rápido a las aplicaciones que usas todos los días agregando o quitando aplicaciones en el iniciador Microsoft 365 aplicaciones.  <br/> |
