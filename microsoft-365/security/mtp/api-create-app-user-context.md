---
title: Crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario
description: Obtenga información sobre cómo acceder a las API de Microsoft 365 defender en nombre de un usuario.
keywords: acceso, en nombre de usuario, API, aplicación, usuario, token de acceso, token
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719421"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Crear una aplicación para acceder a las API de Microsoft 365 defender en nombre de un usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a un producto prelanzamiento que puede modificarse de forma sustancial antes de su lanzamiento comercial. Microsoft makes no warranties, express or implied, with respect to the information provided here.

En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 defender en nombre de un único usuario.

Si necesita acceso mediante programación a Microsoft 365 defender sin un usuario definido (por ejemplo, si está escribiendo una aplicación de fondo o un daemon), vea [crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario](api-create-app-web.md). Si necesita proporcionar acceso para varios inquilinos (por ejemplo, si está atendiendo a una organización de gran tamaño o a un grupo de clientes), vea [crear una aplicación con acceso de socio a las API de Microsoft 365 defender](api-partner-access.md). Si no está seguro de qué tipo de acceso necesita, consulte [Introducción](api-access.md).

Microsoft 365 defender expone gran parte de sus datos y acciones a través de un conjunto de API de programación. Estas API le ayudan a automatizar flujos de trabajo y a usar las capacidades de Microsoft 365 defender. Este acceso a la API requiere la autenticación OAuth 2.0. Para obtener más información, vea [flujo de código de autorización de OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los siguientes pasos para usar estas API:

- Cree una aplicación de Azure Active Directory (Azure AD).
- Obtenga un token de acceso con esta aplicación.
- Use el token para obtener acceso a la API de Microsoft 365 defender.

En este artículo se explica cómo:

- Crear una aplicación de Azure AD
- Obtener un token de acceso a Microsoft 365 defender
- Validar el token

> [!NOTE]
> Al tener acceso a la API de Microsoft 365 defender en nombre de un usuario, necesitará los permisos de usuario y permisos de usuario correctos.

> [!TIP]
> Si tiene permiso para realizar una acción en el portal, tiene permiso para realizar la acción en la API.

## <a name="create-an-app"></a>Crear una aplicación

1. Inicie sesión en [Azure](https://portal.azure.com) como un usuario con el rol de **administrador global** .

2. Navegue a registros de aplicaciones de **Azure Active Directory**  >    >  **nuevo registro**.

   ![Imagen de Microsoft Azure y navegación en el registro de la aplicación](../../media/atp-azure-new-app2.png)

3. En el formulario, elija un nombre para la aplicación y escriba la siguiente información para el URI de redireccionamiento y, a continuación, seleccione **registrar**.

   ![Imagen de la ventana Crear aplicación](../../media/nativeapp-create2.PNG)

   - **Tipo de aplicación:** Cliente público
   - **URI de redireccionamiento:**https://portal.azure.com

4. En la página de la aplicación, seleccione **permisos de API**  >  **Agregar** API de permisos  >  **mi organización usa** >, escriba **protección contra amenazas de Microsoft** y seleccione protección contra amenazas de **Microsoft**. La aplicación ahora puede tener acceso a Microsoft 365 defender.

   > [!TIP]
   > *Microsoft Threat Protection* es un nombre antiguo para Microsoft 365 defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para ver aparezca.

   ![Imagen de la selección de permisos de la API](../../media/apis-in-my-org-tab.PNG)

   - Elija **permisos delegados**. Elija los permisos relevantes para su escenario (por ejemplo, **Incident. Read**) y, a continuación, seleccione **Agregar permisos**.

   ![Imagen de acceso a API y selección de API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Debe seleccionar los permisos relevantes para su escenario. *Leer todos los incidentes* es solo un ejemplo. Para determinar qué permiso necesita, consulte la sección **permisos** en la API que quiera llamar.
    >
    > Por ejemplo, para [ejecutar consultas avanzadas](api-advanced-hunting.md), seleccione el permiso "ejecutar consultas avanzadas"; para [aislar un dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), seleccione el permiso "aislar equipo".

5. Seleccione **conceder consentimiento de administrador**. Cada vez que agregue un permiso, debe seleccionar **conceder consentimiento de administrador** para que surta efecto.

   ![Imagen de permisos de concesión](../../media/grant-consent-delegated.PNG)

6. Registre el identificador de la aplicación y el identificador de inquilino en algún lugar seguro. Aparecen en **información general** en la página de la aplicación.

   ![Imagen del identificador de aplicación creado](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para obtener más información sobre los tokens de Azure Active Directory, vea el [tutorial de Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

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
1. Asegúrese de que la notificación de *roles* dentro del token descodificado contenga los permisos deseados.

En la siguiente imagen, puede ver un token descodificado adquirido de una aplicación, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` y ```AdvancedHunting.Read.All``` permisos:

![Imagen de validación de tokens](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usar el token para obtener acceso a la API de Microsoft 365 defender

1. Elige la API que quieras usar (incidentes o búsqueda avanzada). Para obtener más información, consulte las [API admitidas de Microsoft 365 defender](api-supported.md).
2. En la solicitud HTTP que va a enviar, establezca el encabezado Authorization en `"Bearer" <token>` , el *portador* es el esquema de autorización y el *token* es su token validado.
3. El token expirará en una hora. Puede enviar más de una solicitud durante este tiempo con el mismo token.

En el ejemplo siguiente se muestra cómo enviar una solicitud para obtener una lista de incidentes **con C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las API de Microsoft 365 defender](api-overview.md)
- [Acceso a las API de Microsoft 365 defender](api-access.md)
- [Crear una aplicación "Hola a todos"](api-hello-world.md)
- [Crear una aplicación para obtener acceso a Microsoft 365 defender sin un usuario](api-create-app-web.md)
- [Crear una aplicación con acceso de socio multiinquilino a las API de Microsoft 365 defender](api-partner-access.md)
- [Obtenga información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [OAuth 2,0 autorización para el inicio de sesión de usuario y el acceso a API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
