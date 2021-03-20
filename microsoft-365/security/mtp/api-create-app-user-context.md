---
title: Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario
description: Obtenga información sobre cómo obtener acceso a las API de Microsoft 365 Defender en nombre de un usuario.
keywords: acceso, en nombre del usuario, api, aplicación, usuario, token de acceso, token,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 85c41c0bae9590e76801c18b2a33401874cc7cc3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903957"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Crear una aplicación para tener acceso a las API de Microsoft 365 Defender en nombre de un usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información está relacionada con el producto predefinido que puede modificarse considerablemente antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 Defender en nombre de un único usuario.

Si necesitas acceso mediante programación a Microsoft 365 Defender sin un usuario definido (por ejemplo, si estás escribiendo una aplicación en segundo plano o un demonio), consulta Crear una aplicación para tener acceso a [Microsoft 365 Defender](api-create-app-web.md)sin un usuario . Si necesita proporcionar acceso a varios inquilinos (por ejemplo, si está prestando servicio a una organización grande o a un grupo de clientes), consulte Crear una aplicación con acceso de asociado a las API de [Microsoft 365 Defender.](api-partner-access.md) Si no está seguro del tipo de acceso que necesita, vea [Introducción.](api-access.md)

Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API programáticas. Estas API le ayudan a automatizar flujos de trabajo y a usar las capacidades de Microsoft 365 Defender. Este acceso a la API requiere autenticación de OAuth2.0. Para obtener más información, vea Flujo de código de autorización de [OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá seguir los siguientes pasos para usar estas API:

- Crear una aplicación de Azure Active Directory (Azure AD).
- Obtener un token de acceso con esta aplicación.
- Use el token para obtener acceso a la API de Microsoft 365 Defender.

En este artículo se explica cómo:

- Crear una aplicación de Azure AD
- Obtener un token de acceso a Microsoft 365 Defender
- Validar el token

> [!NOTE]
> Al obtener acceso a la API de Microsoft 365 Defender en nombre de un usuario, necesitará los permisos de aplicación y de usuario correctos.

> [!TIP]
> Si tiene permiso para realizar una acción en el portal, tiene permiso para realizar la acción en la API.

## <a name="create-an-app"></a>Crear una aplicación

1. Inicie sesión en [Azure](https://portal.azure.com) como usuario con el rol **Administrador** global.

2. Vaya a **Azure Active Directory** App  >  **registrations** New  >  **registration**.

   ![Imagen de Microsoft Azure y navegación al registro de aplicaciones](../../media/atp-azure-new-app2.png)

3. En el formulario, elija un nombre para la aplicación y escriba la siguiente información para el URI de redireccionamiento y, a continuación, **seleccione Registrar**.

   ![Imagen de la ventana Crear aplicación](../../media/nativeapp-create2.PNG)

   - **Tipo de aplicación:** Cliente público
   - **URI de redireccionamiento:**https://portal.azure.com

4. En la página de la aplicación, seleccione **Permisos** de API Agregar API de permisos que mi organización usa  >    >   >, escriba Protección contra amenazas de Microsoft y seleccione **Protección contra** amenazas de Microsoft . La aplicación ahora puede acceder a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* es un nombre antiguo de Microsoft 365 Defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.

   ![Imagen de selección de permisos de API](../../media/apis-in-my-org-tab.PNG)

   - Elija **Permisos delegados**. Elija los permisos relevantes para su escenario (por **ejemplo, Incident.Read**) y, a continuación, **seleccione Agregar permisos**.

   ![Imagen de acceso a api y selección de API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Debe seleccionar los permisos relevantes para su escenario. *Leer todos los incidentes* es solo un ejemplo. Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que desea llamar.
    >
    > Por ejemplo, para [ejecutar consultas avanzadas,](api-advanced-hunting.md)seleccione el permiso "Ejecutar consultas avanzadas"; para [aislar un dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleccione el permiso "Aislar máquina".

5. Seleccione **Conceder consentimiento de administrador**. Cada vez que agregue un permiso, debe seleccionar Conceder consentimiento **de administrador** para que su efecto.

   ![Imagen de concesión de permisos](../../media/grant-consent-delegated.PNG)

6. Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro. Aparecen en Información **general en** la página de la aplicación.

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para obtener más información sobre los tokens de Azure Active Directory, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="get-an-access-token-using-powershell"></a>Obtener un token de acceso con PowerShell

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a>Validar el token

1. Copie y pegue el token en [JWT](https://jwt.ms) para descodificarlo.
1. Asegúrese de que la notificación *de roles* dentro del token descodificado contiene los permisos deseados.

En la siguiente imagen, puedes ver un token descodificado adquirido desde una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:

![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usar el token para obtener acceso a la API de Microsoft 365 Defender

1. Elige la API que quieras usar (incidentes o búsqueda avanzada). Para obtener más información, vea [Supported Microsoft 365 Defender API](api-supported.md).
2. En la solicitud http que está a punto de enviar, establezca el encabezado de autorización en , Bearer es el esquema de autorización `"Bearer" <token>` y el *token* es el token validado. 
3. El token expirará en una hora. Puede enviar más de una solicitud durante este tiempo con el mismo token.

En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **mediante C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Artículos relacionados

- [Introducción a las API de Microsoft 365 Defender](api-overview.md)
- [Obtener acceso a las API de Microsoft 365 Defender](api-access.md)
- [Crear una aplicación "Hello world"](api-hello-world.md)
- [Crear una aplicación para tener acceso a Microsoft 365 Defender sin un usuario](api-create-app-web.md)
- [Crear una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender](api-partner-access.md)
- [Más información sobre los límites de api y las licencias](api-terms.md)
- [Comprender códigos de error](api-error-codes.md)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)