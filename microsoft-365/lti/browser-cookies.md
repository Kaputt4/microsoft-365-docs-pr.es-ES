---
title: Permitir cookies para direcciones URL de LMS en el explorador
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Obtenga información sobre cómo permitir cookies para direcciones URL LMS en los exploradores Edge, Chrome y Firefox y Safari.
ms.openlocfilehash: fcaae51c9cdbab3a052a3c29d24e5386f4f852ee
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68167371"
---
# <a name="allow-cookies-for-lms-urls-in-your-browser"></a>Permitir cookies para direcciones URL de LMS en el explorador

Se necesitan cookies de navegador de terceros para completar el protocolo de enlace LTI 1.3 de acuerdo con los estándares globales de IMS. Por lo tanto, al iniciar la herramienta LTI desde un sistema de administración de aprendizaje (LMS), la configuración del explorador debe permitir cookies de terceros para la dirección URL de LMS.

Estos son los pasos para permitir las cookies en su navegador.

# <a name="microsoft-edge"></a>[Microsoft Edge](#tab/edge)

## <a name="allow-cookies-for-lms-urls-in-microsoft-edge"></a>Permitir cookies para direcciones URL de LMS en Microsoft Edge

1. En la ventana **Configuración** de Edge, seleccione **Cookies y permisos del sitio** > **Cookies y datos almacenados** > **Administra y elimina cookies y datos del sitio**.
2. Active **Permitir que los sitios guarden y lean datos de cookies (recomendado)** y asegúrese de que **Bloquear las cookies de terceros** esté desactivado.

Si debe mantener bloqueadas las cookies de terceros:

1. En la ventana **Configuración** de Edge, seleccione **Cookies y permisos del sitio** > **Cookies y datos almacenados** > **Administra y elimina cookies y datos del sitio**.
2. En **Permitir**, seleccione **Agregar** para agregar la dirección URL del dominio de la plataforma LMS.
   1. Por ejemplo, si la plataforma LMS está hospedada en `https://contoso.com`, esa dirección URL debe agregarse en **Permitir**.

![Captura de pantalla de la página de configuración de cookies de Microsoft Edge](media/edge-cookies.png)

# <a name="google-chrome"></a>[Google Chrome](#tab/chrome)

## <a name="allow-cookies-for-lms-urls-in-google-chrome"></a>Permitir cookies para DIRECCIONES URL DE LMS en Google Chrome

1. En la pestaña **Privacidad y seguridad** de la ventana **Configuración** de Chrome, seleccione **Cookies y otros datos de sitios web**.

2. En **Sitios web que pueden usar cookies siempre**, seleccione **Añadir** y luego seleccione la casilla **Incluir cookies de terceros en este sitio web**.

3. Agregue la dirección URL del dominio de la plataforma LMS.
   1. Por ejemplo, si la plataforma LMS está hospedada en `https://contoso.com`, se debe usar esa dirección URL.

![Captura de pantalla de la página de configuración de cookies de Google Chrome](media/chrome-cookies.png)

# <a name="mozilla-firefox"></a>[Mozilla Firefox](#tab/firefox)

## <a name="allow-cookies-for-lms-urls-in-mozilla-firefox"></a>Permitir cookies para LMS URLS en Mozilla Firefox

1. En la ventana **Ajustes** de Firefox, seleccione la pestaña **Privacidad & Seguridad**.

2. En **Cookies y datos del sitio**, seleccione **Gestionar excepciones**.

3. En el cuadro **de texto Dirección del sitio web** , escriba la dirección URL de la plataforma LMS.
   1. Por ejemplo, si la plataforma LMS está hospedada en `https://contoso.com`, se debe usar esa dirección URL.

4. Seleccione **Permitir** para permitir cookies para el sitio web especificado.

5. Seleccione **Guardar cambios**.

![Captura de pantalla de la página de configuración de cookies de Mozilla Firefox](media/firefox-cookies.png)

# <a name="safari"></a>[Safari](#tab/safari)

## <a name="allow-cookies-for-lms-urls-in-safari"></a>Permitir cookies para direcciones URL de LMS en Safari

1. Seleccione **Preferencias** > **Privacidad**.

2. Desmarque la casilla **Evitar el seguimiento entre sitios**.

---

> [!NOTE]
> En no puede cambiar la configuración usted mismo (el explorador lo administra su organización), póngase en contacto con el departamento de TI.
