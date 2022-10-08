---
title: Uso de api de Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Obtén información sobre cómo diseñar una aplicación nativa de Windows para obtener acceso mediante programación a Microsoft Defender para punto de conexión sin un usuario.
keywords: api, graph api, api admitidas, actor, alertas, dispositivo, usuario, dominio, ip, archivo, búsqueda avanzada, consulta
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: ce7d7f1973f618984e0ee63270ce7fca5d7fdc87
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193067"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a>Uso de api de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/index.yml)

> [!IMPORTANT]
> Las funcionalidades avanzadas de búsqueda no se incluyen en Defender para empresas. Consulte [Comparar Microsoft Defender para Empresas con los planes 1 y 2 de Microsoft Defender para punto de conexión](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2).


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

En esta página se describe cómo crear una aplicación para obtener acceso mediante programación a Defender for Endpoint en nombre de un usuario.

Si necesita acceso mediante programación Microsoft Defender para punto de conexión sin un usuario, consulte [Acceso a Microsoft Defender para punto de conexión con el contexto de la aplicación](exposed-apis-create-app-webapp.md).

Si no está seguro de qué acceso necesita, lea la [página Introducción](apis-intro.md).

Microsoft Defender para punto de conexión expone gran parte de sus datos y acciones a través de un conjunto de API mediante programación. Estas API le permitirán automatizar los flujos de trabajo e innovar en función de las capacidades de Microsoft Defender para punto de conexión. El acceso a la API requiere la autenticación de OAuth2.0. Para obtener más información, vea [Flujo de código de autorización de OAuth 2.0](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

En general, deberá realizar los pasos siguientes para usar las API:

- Creación de una aplicación de AAD
- Obtención de un token de acceso mediante esta aplicación
- Uso del token para acceder a Defender for Endpoint API

En esta página se explica cómo crear una aplicación de AAD, obtener un token de acceso para Microsoft Defender para punto de conexión y validar el token.

> [!NOTE]
> Al acceder a Microsoft Defender para punto de conexión API en nombre de un usuario, necesitará el permiso de aplicación y el permiso de usuario correctos.
> Si no está familiarizado con los permisos de usuario en Microsoft Defender para punto de conexión, consulte [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md).

> [!TIP]
> Si tiene permiso para realizar una acción en el portal, tiene el permiso para realizar la acción en la API.

## <a name="create-an-app"></a>Crear una aplicación

1. Inicie sesión en [Azure](https://portal.azure.com) con una cuenta de usuario que tenga el rol **Administrador global** .

2. Vaya a **Azure Active Directory** \> **Registros de aplicaciones** \> **Nuevo registro**.

   :::image type="content" source="images/atp-azure-new-app2.png" alt-text="Página Registros de aplicaciones de Microsoft Azure Portal" lightbox="images/atp-azure-new-app2.png":::

3. Cuando aparezca la página **Registrar una aplicación**, escriba la información de registro de la aplicación:
   - **Nombre**: escriba un nombre significativo para la aplicación, que se mostrará a los usuarios de la aplicación.
   - **Tipos de cuentas compatibles**: seleccione qué cuentas desea que admita la aplicación.

     <br>

     |Tipos de cuenta admitidos|Descripción|
     |---|---|
     |**Solo las cuentas de este directorio organizativo**|Seleccione esta opción si va a crear una aplicación de línea de negocio (LOB). Esta opción no está disponible si no va a registrar la aplicación en un directorio. <p> Esta opción se asigna solo a un único inquilino de Azure AD. <p> Esta es la opción predeterminada a menos que registre la aplicación fuera de un directorio. En los casos en los que la aplicación se registra fuera de un directorio, el valor predeterminado son las cuentas personales de Microsoft y cuentas multiinquilino de Azure AD.|
     |**Cuentas en cualquier directorio organizativo**|Seleccione esta opción si desea tener como destino todos los clientes de negocios y del sector educativo. <p> Esta opción se asigna a un multiinquilino de solo Azure AD. <p> Si ha registrado la aplicación como solo para un único inquilino de Azure AD, puede actualizarla para que sea de multiinquilino de Azure AD y que vuelva a serlo para un solo inquilino mediante la hoja **Autenticación**.|
     |**Cuentas en cualquier directorio organizativo y cuentas personales de Microsoft**|Seleccione esta opción para establecer como destino el mayor conjunto posible de clientes. <p> Esta opción asigna cuentas personales de Microsoft y cuentas multiinquilinos de Azure AD. <p> Si registró la aplicación como cuentas multiinquilino de Azure AD y cuentas personales de Microsoft, no puede cambiar esto en la interfaz de usuario. En su lugar, debe usar el editor de manifiestos de aplicación para cambiar los tipos de cuenta admitidos.|

   - **URI de redirección (opcional)**: seleccione el tipo de aplicación que se va a crear, **Web** o **Cliente público (móvil y escritorio)** y, a continuación, escriba el identificador URI de redireccionamiento (o la dirección URL de respuesta) para la aplicación.

     - Para aplicaciones web, proporcione la dirección URL base de la aplicación. Por ejemplo, `http://localhost:31544` podría ser la dirección URL de una aplicación web que se ejecuta en la máquina local. Los usuarios utilizan esta dirección URL para iniciar sesión en una aplicación cliente web.

     - Para aplicaciones cliente públicas, proporcione el identificador URI que utiliza Azure AD para devolver las respuestas de los tokens. Escriba un valor específico para la aplicación, como `myapp://auth`.

     Si desea ejemplos específicos de aplicaciones web o aplicaciones nativas, visite nuestras [guías de inicio rápido](/azure/active-directory/develop/#quickstarts).

     Cuando termine, seleccione **Registrar**.

4. Permita que la aplicación acceda a Microsoft Defender para punto de conexión y asígnele el permiso "Leer alertas":

   - En la página de la aplicación, seleccione **Permisos** \> de API **Agregar API de permisos** \> **Que mi organización usa** > escriba **WindowsDefenderATP** y seleccione en **WindowsDefenderATP**.

     > [!NOTE]
     > *WindowsDefenderATP* no aparece en la lista original. Empiece a escribir su nombre en el cuadro de texto para verlo aparecer.

     :::image type="content" alt-text="agregar permiso." source="images/add-permission.png" lightbox="images/add-permission.png":::

   - Elija **Permisos** \> delegados **Alert.Read** > seleccione **Agregar permisos**.

      :::image type="content" source="images/application-permissions-public-client.png" alt-text="El tipo de aplicación y los paneles de permisos" lightbox="images/application-permissions-public-client.png":::

   > [!IMPORTANT]
   > Seleccione los permisos pertinentes. Las alertas de lectura son solo un ejemplo.

     Por ejemplo:

     - Para [ejecutar consultas avanzadas](run-advanced-query-api.md), seleccione **El permiso Ejecutar consultas avanzadas** .
     - Para [aislar un dispositivo](isolate-machine.md), seleccione **Aislar permiso de máquina** .
     - Para determinar qué permiso necesita, consulte la sección **Permisos** de la API a la que está interesado llamar.

   - Seleccione **Conceder consentimiento**.

      > [!NOTE]
      > Cada vez que agregue permiso, debe seleccionar en **Conceder consentimiento** para que el nuevo permiso surta efecto.

      :::image type="content" source="images/grant-consent.png" alt-text="Opción de consentimiento del gran administrador" lightbox="images/grant-consent.png":::

5. Anote el identificador de la aplicación y el identificador de inquilino.

    En la página de la aplicación, vaya a **Información general** y copie la siguiente información:

    :::image type="content" source="images/app-and-tenant-ids.png" alt-text="Identificador de la aplicación creada"  lightbox="images/app-and-tenant-ids.png":::

## <a name="get-an-access-token"></a>Obtener un token de acceso

Para más información sobre los tokens de AAD, consulte [el tutorial de Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="using-c"></a>Uso de C\#

- Copie o pegue la clase siguiente en la aplicación.
- Use **el método AcquireUserTokenAsync** con el identificador de aplicación, el identificador de inquilino, el nombre de usuario y la contraseña para adquirir un token.

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a>Validar el token

Compruebe para asegurarse de que tiene un token correcto:

- Copie o pegue en [JWT](https://jwt.ms) el token que obtuvo en el paso anterior para descodificarlo.
- Valide que obtiene una notificación "scp" con los permisos de aplicación deseados.
- En la captura de pantalla siguiente, puede ver un token descodificado adquirido de la aplicación en el tutorial:

  :::image type="content" source="images/nativeapp-decoded-token.png" alt-text="Página de validación de tokens" lightbox="images/nativeapp-decoded-token.png":::

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>Uso del token para acceder a Microsoft Defender para punto de conexión API

- Elija la API que desea usar: API [de Microsoft Defender para punto de conexión admitidas](exposed-apis-list.md).
- Establezca el encabezado Authorization en la solicitud HTTP que envíe a "Bearer {token}" (Bearer es el esquema de autorización).
- La hora de expiración del token es de 1 hora (puede enviar más de una solicitud con el mismo token).

- Ejemplo de envío de una solicitud para obtener una lista de alertas **mediante C#**:

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>Vea también

- [API de Microsoft Defender para punto de conexión](exposed-apis-list.md)
- [Acceso a Microsoft Defender para punto de conexión con contexto de aplicación](exposed-apis-create-app-webapp.md)
