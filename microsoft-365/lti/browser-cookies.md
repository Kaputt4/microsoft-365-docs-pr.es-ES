---
title: Permitir cookies para direcciones URL de LMS en el explorador
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Obtenga información sobre cómo permitir cookies para direcciones URL LMS en los exploradores Edge, Chrome y Firefox y Safari.
ms.openlocfilehash: 1dabe2d16dc2d559ec1576a2140c48b63c8e2ccd
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2022
ms.locfileid: "65285657"
---
# <a name="allow-cookies-for-lms-urls-in-your-browser"></a>Permitir cookies para direcciones URL de LMS en el explorador

Se necesitan cookies de navegador de terceros para completar el protocolo de enlace LTI 1.3 de acuerdo con los estándares globales de IMS. Por lo tanto, al iniciar la herramienta LTI desde un sistema de administración de Learning (LMS), la configuración del explorador debe permitir cookies de terceros para la dirección URL de LMS.

Estos son los pasos para permitir las cookies en su navegador.

# <a name="microsoft-edge"></a>[Microsoft Edge](#tab/edge)

## <a name="allow-cookies-for-lms-urls-in-microsoft-edge"></a>Permitir cookies para direcciones URL de LMS en Microsoft Edge

1. En la ventana Edge  **Configuración** , seleccioneCookies and site  **permissionsCookies and data storedManage and delete cookies and site data (Cookies and site permissionsCookies and site permissionsCookies and data storedManage and delete cookies and site data(Cookies and site permissionsCookies and site permissionsCookies and data storedManage** >  **and delete cookies and site data**(  **Cookies and site permissionsCookies** > and
2.  **ActivarAllow sites to save and read cookie data (recommended)**, and sure  **thatBlock third-party cookies**  is desactivado.

Si debe mantener bloqueadas las cookies de terceros:

1. En la ventana Edge  **Configuración** , seleccioneCookies and site  **permissionsCookies and data storedManage and delete cookies and site data (Cookies and site permissionsCookies and site permissionsCookies and data storedManage and delete cookies and site data(Cookies and site permissionsCookies and site permissionsCookies and data storedManage** >  **and delete cookies and site data**(  **Cookies and site permissionsCookies** > and
2.  **EnAllow**,  **seleccioneAgregar**  para agregar la dirección URL del dominio de la plataforma LMS.
   1. Por ejemplo, si la plataforma LMS está hospedada en `https://contoso.com`, esa dirección URL debe agregarse en **Permitir**.

![Captura de pantalla de Microsoft Edge página de configuración de cookies](media/edge-cookies.png)

# <a name="google-chrome"></a>[Google Chrome](#tab/chrome)

## <a name="allow-cookies-for-lms-urls-in-google-chrome"></a>Permitir cookies para DIRECCIONES URL DE LMS en Google Chrome

1. En la ventana Chrome  **Configuración** , en la  **fichaPrivacidad y seguridad** ,  **seleccioneCookies y otros datos del sitio**.

2. En  **Sitios que siempre pueden usar cookies**,  **seleccioneAgregar** y, a continuación, seleccione Las  **cookies de terceros de este cuadro** de comprobación de sitio .

3. Agregue la dirección URL del dominio de la plataforma LMS.
   1. Por ejemplo, si la plataforma LMS está hospedada en `https://contoso.com`, se debe usar esa dirección URL.

![Captura de pantalla de la página de configuración de cookies de Google Chrome](media/chrome-cookies.png)

# <a name="mozilla-firefox"></a>[Mozilla Firefox](#tab/firefox)

## <a name="allow-cookies-for-lms-urls-in-mozilla-firefox"></a>Permitir cookies para LMS URLS en Mozilla Firefox

1. En la ventana  **Firefox Configuración** , seleccione la ficha  **Seguridad**  de & Deprivacidad.

2.  **EnCookies and Site Data (Cookies and Site Data**),  **seleccioneManage Exceptions (Administrar excepciones**).

3. En el cuadro  **de textoAddress of website (Dirección URL del sitio web** ), escriba la dirección URL de la plataforma LMS.
   1. Por ejemplo, si la plataforma LMS está hospedada en `https://contoso.com`, se debe usar esa dirección URL.

4. Seleccione **Permitir** para permitir cookies para el sitio web especificado.

5. Seleccione  **Guardar cambios**.

![Captura de pantalla de la página de configuración de cookies de Mozilla Firefox](media/firefox-cookies.png)

# <a name="safari"></a>[Safari](#tab/safari)

## <a name="allow-cookies-for-lms-urls-in-safari"></a>Permitir cookies para direcciones URL de LMS en Safari

1.  **SeleccionePreferencesPrivacy**  ****>.

2. Borre el cuadro de  **comprobación De seguimiento**  entre sitios dePrevent.

---

> [!NOTE]
> En no puede cambiar la configuración usted mismo (el explorador lo administra su organización), póngase en contacto con el departamento de TI.
