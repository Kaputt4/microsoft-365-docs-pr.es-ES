---
title: Creación de una aplicación para acceder a Microsoft 365 Defender API en nombre de un usuario
description: Obtenga información sobre cómo acceder a las API de Microsoft 365 Defender en nombre de un usuario.
keywords: access, en nombre del usuario, api, aplicación, usuario, token de acceso, token,
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
ms.custom: api
ms.openlocfilehash: 41f2763d73bbb9ed0b7ae32dce431cb2c1a4d71f
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102600"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Creación de una aplicación para acceder a Microsoft 365 Defender API en nombre de un usuario

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Microsoft 365 Defender en nombre de un único usuario.

Si necesita acceso mediante programación a Microsoft 365 Defender sin un usuario definido (por ejemplo, si está escribiendo una aplicación en segundo plano o un demonio), consulte [Creación de una aplicación para acceder a Microsoft 365 Defender sin un usuario](api-create-app-web.md). Si necesita proporcionar acceso para varios inquilinos(por ejemplo, si está atendiendo a una organización grande o a un grupo de clientes), consulte [Creación de una aplicación con acceso de asociado a Microsoft 365 Defender API](api-partner-access.md). Si no está seguro del tipo de acceso que necesita, consulte [Comenzar](api-access.md).

Microsoft 365 Defender expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Esas API le ayudan a automatizar flujos de trabajo y a usar las funcionalidades de Microsoft 365 Defender. Este acceso a la API requiere la autenticación de OAuth2.0. Para obtener más información, vea [Flujo de código de autorización de OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los pasos siguientes para usar estas API:

- Cree una aplicación de Azure Active Directory (Azure AD).
- Obtenga un token de acceso mediante esta aplicación.
- Use el token para acceder a Microsoft 365 Defender API.

En este artículo se explica cómo:

- Crear una aplicación Azure AD
- Obtención de un token de acceso para Microsoft 365 Defender
- Validar el token

> [!NOTE]
> Al acceder a Microsoft 365 Defender API en nombre de un usuario, necesitará los permisos de aplicación y permisos de usuario correctos.

> [!TIP]
> Si tiene permiso para realizar una acción en el portal, tiene el permiso para realizar la acción en la API.

## <a name="create-an-app"></a>Crear una aplicación

1. Inicie sesión en [Azure](https://portal.azure.com) como usuario con el rol **Administrador global** .

2. Vaya a **Azure Active Directory** >  **Registros de aplicaciones** >  **Nuevo registro**.

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="La opción Nuevo registro del panel Administrar de la Azure Portal" lightbox="../../media/atp-azure-new-app2.png":::

3. En el formulario, elija un nombre para la aplicación y escriba la siguiente información para el URI de redirección y, a continuación, seleccione **Registrar**.

   :::image type="content" source="../../media/nativeapp-create2.PNG" alt-text="Panel de registro de la aplicación en el Azure Portal" lightbox="../../media/nativeapp-create2.PNG":::
   

   - **Tipo de aplicación:** Cliente público
   - **URI de redireccionamiento:** https://portal.azure.com

4. En la página de la aplicación, seleccione **Permisos** >  de API **Agregar API de permisos** > **Que mi organización usa** >, escriba **Microsoft Threat Protection** y seleccione **Microsoft Threat Protection**. La aplicación ahora puede acceder a Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* es un nombre anterior para Microsoft 365 Defender y no aparecerá en la lista original. Debe empezar a escribir su nombre en el cuadro de texto para verlo aparecer.

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Panel API de la organización en el portal de Microsoft 365 Defender" lightbox="../../media/apis-in-my-org-tab.PNG":::

   - Elija **Permisos delegados**. Elija los permisos pertinentes para el escenario (por ejemplo **, Incident.Read**) y, a continuación, seleccione **Agregar permisos**.

     :::image type="content" source="../../media/request-api-permissions-delegated.PNG" alt-text="Panel Permisos delegados en el portal de Microsoft 365 Defender" lightbox="../../media/request-api-permissions-delegated.PNG":::

    > [!NOTE]
    > Debe seleccionar los permisos pertinentes para el escenario. *Leer todos los incidentes* es solo un ejemplo. Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que desea llamar.
    >
    > Por ejemplo, para [ejecutar consultas avanzadas](api-advanced-hunting.md), seleccione el permiso "Ejecutar consultas avanzadas"; Para [aislar un dispositivo](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), seleccione el permiso "Aislar máquina".

5. Seleccione **Conceder consentimiento de administrador**. Cada vez que agregue un permiso, debe seleccionar **Conceder consentimiento del administrador** para que surta efecto.

   :::image type="content" source="../../media/grant-consent-delegated.PNG" alt-text="Panel de concesión de consentimiento del administrador en el portal de Microsoft 365 Defender" lightbox="../../media/grant-consent-delegated.PNG":::

6. Registre el identificador de la aplicación y el identificador de inquilino en un lugar seguro. Se enumeran en **Información general** en la página de la aplicación.

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Panel Información general del portal de Microsoft 365 Defender" lightbox="../../media/app-and-tenant-ids.png":::

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para obtener más información sobre los tokens de Azure Active Directory, consulte el [tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="get-an-access-token-on-behalf-of-a-user-using-powershell"></a>Obtención de un token de acceso en nombre de un usuario mediante PowerShell

Use la biblioteca MSAL.PS para adquirir tokens de acceso con permisos delegados. Ejecute los siguientes comandos para obtener el token de acceso en nombre de un usuario:

```PowerShell
Install-Module -Name MSAL.PS # Install the MSAL.PS module from PowerShell Gallery

$TenantId = " " # Paste your directory (tenant) ID here.
$AppClientId="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" # Paste your application (client) ID here.

$MsalParams = @{
   ClientId = $AppClientId
   TenantId = $TenantId
   Scopes   = 'https://graph.microsoft.com/User.Read.All','https://graph.microsoft.com/Files.ReadWrite'
}

$MsalResponse = Get-MsalToken @MsalParams
$AccessToken  = $MsalResponse.AccessToken
 
$AccessToken # Display the token in PS console
```
## <a name="validate-the-token"></a>Validar el token

1. Copie y pegue el token en [JWT](https://jwt.ms) para descodificarlo.
2. Asegúrese de que la notificación de *roles* dentro del token descodificado contiene los permisos deseados.

En la imagen siguiente, puede ver un token descodificado adquirido de una aplicación, con ```Incidents.Read.All```permisos , ```Incidents.ReadWrite.All```y ```AdvancedHunting.Read.All``` :

:::image type="content" source="../../media/defender-endpoint/webapp-decoded-token.png" alt-text="La sección de permisos del panel Token descodificado del portal de Microsoft 365 Defender" lightbox="../../media/defender-endpoint/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Uso del token para acceder a la API de Microsoft 365 Defender

1. Elija la API que desea usar (incidentes o búsqueda avanzada). Para obtener más información, consulte [API de Microsoft 365 Defender compatibles](api-supported.md).
2. En la solicitud HTTP que va a enviar, establezca el encabezado `"Bearer" <token>`de autorización en , *Bearer* es el esquema de autorización y el *token* es el token validado.
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
- [Acceso a las API de Microsoft 365 Defender](api-access.md)
- [Creación de una aplicación "Hola mundo"](api-hello-world.md)
- [Creación de una aplicación para acceder a Microsoft 365 Defender sin un usuario](api-create-app-web.md)
- [Creación de una aplicación con acceso de asociado multiinquilino a las API de Microsoft 365 Defender](api-partner-access.md)
- [Más información sobre los límites de API y las licencias](api-terms.md)
- [Descripción de los códigos de error](api-error-codes.md)
- [Autorización de OAuth 2.0 para el inicio de sesión de usuario y el acceso a la API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
