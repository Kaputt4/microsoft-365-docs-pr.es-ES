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
description: Obtenga información sobre cómo registrar y administrar aplicaciones integradas de Office 365 en Azure AD, lo que permite autorizaciones de aplicaciones en el nivel de administrador global.
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384906"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Aplicaciones integradas y Azure AD para administradores de Microsoft 365

La administración de aplicaciones integradas es mucho más que administrar el [consentimiento del usuario para las aplicaciones.](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) Con la llegada de las API de REST de Microsoft 365, los usuarios pueden conceder a las aplicaciones acceso a sus datos de Microsoft 365, como correo, calendarios, contactos, usuarios, grupos, archivos y carpetas. De forma predeterminada, los usuarios necesitan conceder permisos individualmente a cada aplicación. 

Pero esto no se escala bien si quieres autorizar una aplicación una vez en el nivel de administrador global e implantarla en toda la organización a través del iniciador de aplicaciones. Para ello, debe registrar la aplicación en Azure Active Directory (Azure AD). Hay algunos pasos que debe seguir antes de poder registrar una aplicación en Azure AD y cierta información básica que debe saber que puede ayudarle a administrar aplicaciones en su organización de Microsoft 365.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Recursos de Azure AD para administradores de Microsoft 365

Debe realizar estas dos tareas antes de poder administrar las aplicaciones de Microsoft 365 en Azure AD.
  
|Requisitos previos|Comentarios|
|:-----|:-----|
|[Usar la suscripción gratuita de Azure AD](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Cada suscripción de pago a Microsoft 365 viene con una suscripción gratuita a Azure AD. Puedes usar Azure AD para administrar tus aplicaciones y para crear y administrar cuentas de usuario y grupo. Para usar Azure AD, solo tiene que ir a Azure Portal e [https://portal.azure.com](https://portal.azure.com) iniciar sesión con su cuenta de Microsoft 365.  <br/> |
|[Administrar el consentimiento del usuario a las aplicaciones](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |Debe administrar el consentimiento del usuario a las aplicaciones para permitir que las aplicaciones de terceros accedan a la información del usuario de Microsoft 365 y para que registre aplicaciones en Azure AD. Por ejemplo, cuando alguien usa una aplicación de terceros, puede que la aplicación le pida permiso para tener acceso a su calendario y para modificar los archivos que están en una carpeta de OneDrive.  <br/> |
   
La administración de aplicaciones de Microsoft 365 requiere que tenga conocimientos de aplicaciones en Azure AD. Usa estos artículos para proporcionarte los antecedentes que necesitas.
  
|Artículo|Comentarios|
|:-----|:-----|
|[Reunirse con el iniciador de aplicaciones de Microsoft 365](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |Si no estás en el iniciador de aplicaciones, es posible que te preguntes qué es y cómo usarlo. El iniciador de aplicaciones está diseñado para ayudarle a obtener acceso a sus aplicaciones desde cualquier lugar en Microsoft 365.  <br/> |
|[Introducción a las API de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Las API de administración de Microsoft 365 le permiten proporcionar acceso a sus datos de Microsoft 365, incluidas las cosas que más les importan: su correo, calendarios, contactos, usuarios y grupos, archivos y carpetas. <br/> |
|[Integración de aplicaciones en Azure AD](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Obtenga información sobre las aplicaciones que están integradas con Azure AD y cómo registrar la aplicación, comprender los conceptos detrás de una aplicación registrada y obtener información sobre las directrices de personalción de marca para aplicaciones multiinquilino.  <br/> |
|[Agregar iconos personalizados al iniciador de aplicaciones](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |El iniciador de aplicaciones de Microsoft 365 facilita a los usuarios la búsqueda y el acceso a sus aplicaciones. En este artículo se describen las formas en que usted como desarrollador puede hacer que sus aplicaciones aparezcan en los iniciadores de aplicaciones de los usuarios y también darles una experiencia de inicio de sesión único (SSO) con sus credenciales de Microsoft 365.  <br/> |
|[Tutoriales de integración de Azure AD](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |El objetivo de estos tutoriales es mostrar cómo configurar el SSO de Azure AD para aplicaciones SaaS de terceros.  <br/> |
|[Escenarios de autenticación de Azure AD](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD simplifica la autenticación para desarrolladores proporcionando identidad como servicio, con compatibilidad con protocolos estándar del sector como OAuth 2.0 y OpenID Connect, así como bibliotecas de código abierto para distintas plataformas para ayudarle a empezar rápidamente a codificar. Este documento le ayuda a comprender los distintos escenarios compatibles con Azure AD y le muestra cómo empezar.  <br/> |
|[Acceso a la aplicación](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD permite una integración sencilla para muchas de las aplicaciones de software como servicio (SaaS) más populares de hoy en día. Proporciona administración de identidades y acceso, y proporciona un Panel de acceso para los usuarios donde pueden descubrir qué acceso de aplicación tienen y dónde pueden usar SSO para acceder a sus aplicaciones. En este artículo se proporcionan vínculos a los recursos relacionados que le permiten obtener más información sobre las mejoras de acceso a aplicaciones para Azure AD y cómo puede contribuir a ellas.  <br/> |
|[Personalizar la experiencia de Office 365](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Puede obtener acceso rápido a las aplicaciones que usa a diario agregando o quitando aplicaciones en el iniciador de aplicaciones de Microsoft 365.  <br/> |

