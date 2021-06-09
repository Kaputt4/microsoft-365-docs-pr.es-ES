---
title: Implementar un conector para archivar datos de páginas de Facebook Empresa
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden configurar un conector nativo para importar y archivar páginas de Facebook Business en Microsoft 365. Después de importar estos datos a Microsoft 365, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar el gobierno de los datos de Facebook de su organización.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619956"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>Implementar un conector para archivar datos de páginas de Facebook Empresa

Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de páginas de Facebook Empresa a Microsoft 365. Para obtener información general de alto nivel sobre este proceso y una lista de requisitos previos necesarios para implementar un conector de Facebook, vea Configurar un conector para archivar [datos de Facebook](archive-facebook-data-with-sample-connector.md).

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

1. Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global.

    ![Crear aplicación en AAD](../media/FBCimage1.png)

2. En el panel de navegación izquierdo, haga clic en **Azure Active Directory**

    ![Haga clic Azure Active Directory](../media/FBCimage2.png)

3. En el panel de navegación izquierdo, haga clic en **Registros de aplicaciones (versión preliminar)** y, a continuación, haga clic **en Nuevo registro.**

    ![Haga clic en **Registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **Nuevo registro**](../media/FBCimage3.png)

4. Registrar la aplicación. En URI de redireccionamiento, seleccione Web en la lista desplegable tipo de aplicación y, a continuación, escriba <https://portal.azure.com> el cuadro para el URI.

   ![Registrar la aplicación](../media/FBCimage4.png)

5. Copie el **identificador de aplicación (cliente)** y el id. de directorio **(inquilino)** y guárdelos en un archivo de texto u otra ubicación segura. Estos IDs se usan en pasos posteriores.

   ![Copie el id. de aplicación y el id. de directorio y guárdelos](../media/FBCimage5.png)

6. Ve a **Certificados & secretos de la nueva aplicación.**

   ![Ir a Certificados & secretos de la nueva aplicación](../media/FBCimage6.png)

7. Haga **clic en Nuevo secreto de cliente**

   ![Haga clic en Nuevo secreto de cliente](../media/FBCimage7.png)

8. Cree un nuevo secreto. En el cuadro descripción, escriba el secreto y, a continuación, elija un período de expiración.

    ![Escriba el secreto y, a continuación, elija un período de expiración](../media/FBCimage8.png)

9. Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento. Este es el secreto de aplicación de AAD que se usa en los pasos posteriores.

   ![Copiar el valor del secreto y guardarlo](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Paso 2: Implementar el servicio web del conector GitHub en su cuenta de Azure

1. Vaya a [este GitHub y](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) haga clic en Implementar en **Azure**.

    ![Haga clic en Implementar en Azure](../media/FBCGithubApp.png)

2. Después de hacer **clic en Implementar en Azure,** se le redirigirá a un Portal de Azure con una página de plantilla personalizada. Rellene los detalles **básicos** **y Configuración** y, a continuación, haga clic en **Comprar**.

   - **Suscripción:** Seleccione la suscripción de Azure en la que desea implementar el servicio web del conector de páginas empresariales de Facebook.

   - **Grupo de recursos:** Elija o cree un nuevo grupo de recursos. Un grupo de recursos es un contenedor que contiene recursos relacionados para una solución de Azure.

   - **Ubicación:** Elija una ubicación.

   - **Nombre de aplicación web:** Proporcione un nombre único para la aplicación web del conector. Th nombre debe tener entre 3 y 18 caracteres de longitud. Este nombre se usa para crear la dirección URL del servicio de aplicaciones de Azure; por ejemplo, si proporciona el nombre de la aplicación web de **fbconnector,** la dirección URL del servicio de aplicaciones de Azure **se mostrará fbconnector.azurewebsites.net**.

   - **tenantId:** El identificador de inquilino de la Microsoft 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 1.

   - **APISecretKey:** Puede escribir cualquier valor como secreto. Esto se usa para tener acceso a la aplicación web del conector en el paso 5.

     ![Haga clic en Crear un recurso y escriba cuenta de almacenamiento](../media/FBCimage12.png)

3. Una vez que la implementación se realiza correctamente, la página tendrá un aspecto similar a la siguiente captura de pantalla:

   ![Haga clic Storage y, a continuación, haga clic Storage cuenta](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>Paso 3: Registrar la aplicación de Facebook

1. Vaya a , inicie sesión con las credenciales de la cuenta de las páginas de Facebook Empresa de su organización y, a <https://developers.facebook.com> continuación, haga clic en Agregar nueva **aplicación**.

   ![Agregar una nueva página de aplicación para Empresas de Facebook](../media/FBCimage25.png)

2. Crea un nuevo identificador de aplicación.

   ![Crear un nuevo identificador de aplicación](../media/FBCimage26.png)

3. En el panel de navegación izquierdo, haga clic **en Agregar productos** y, a continuación, haga clic en **Configurar** en el icono Inicio de sesión **de Facebook.**

   ![Haga clic en Agregar productos](../media/FBCimage27.png)

4. En la página Integrar inicio de sesión de Facebook, haga clic en **Web**.

   ![Haga clic en Web en la página Integrar inicio de sesión de Facebook](../media/FBCimage28.png)

5. Agregar la dirección URL del servicio de aplicaciones de Azure; por ejemplo `https://fbconnector.azurewebsites.net` .

   ![Agregar la dirección URL del servicio de aplicaciones de Azure](../media/FBCimage29.png)

6. Complete la sección Inicio rápido de la configuración de inicio de sesión de Facebook.

   ![Completar la sección Inicio rápido](../media/FBCimage30.png)

7. En el panel de navegación izquierdo en Inicio de sesión de **Facebook,** **haga** clic Configuración y agregue el URI de redireccionamiento de OAuth en el cuadro Uri de redireccionamiento **de OAuth** válido. Use el formato **\<connectorserviceuri> /Views/FacebookOAuth**, donde el valor de connectorserviceuri es la dirección URL del servicio de aplicaciones de Azure para su organización; por ejemplo, `https://fbconnector.azurewebsites.net` .

   ![Agregar el URI de redireccionamiento de OAuth al cuadro Uri de redireccionamiento de OAuth válido](../media/FBCimage31.png)

8. En el panel de navegación izquierdo, haga clic **en Agregar productos** y, a continuación, haga clic en **Webhooks.** En el **menú** desplegable Página, haga clic en **Página**.

   ![Haga clic en Agregar productos y, a continuación, en **Webhooks](../media/FBCimage32.png)

9. Agregue la dirección URL de devolución de llamada de webhooks y agregue un token de comprobación. El formato de la dirección URL de devolución de llamada, use el formato **<connectorserviceuri> /api/FbPageWebhook**, donde el valor de connectorserviceuri es la dirección URL del servicio de aplicaciones de Azure para su organización; por `https://fbconnector.azurewebsites.net` ejemplo.

   El token de comprobación debe ser similar a una contraseña segura. Copie el token de comprobación en un archivo de texto u otra ubicación de almacenamiento.

   ![Agregar el token de comprobación](../media/FBCimage33.png)

10. Pruebe y suscríbete al punto de conexión para la fuente.

    ![Probar y suscribirse al punto de conexión](../media/FBCimage34.png)

11. Agrega una dirección URL de privacidad, un icono de aplicación y un uso empresarial. Además, copia el identificador de la aplicación y el secreto de la aplicación en un archivo de texto u otra ubicación de almacenamiento.

    ![Agregar una dirección URL de privacidad, un icono de aplicación y un uso empresarial](../media/FBCimage35.png)

12. Haz que la aplicación sea pública.

    ![Hacer pública la aplicación](../media/FBCimage36.png)

13. Agregar usuario al rol de administrador o evaluador.

    ![Agregar usuario al rol de administrador o evaluador](../media/FBCimage37.png)

14. Agregue el **permiso Acceso al contenido público de la** página.

    ![dd el permiso Acceso a contenido público de página](../media/FBCimage38.png)

15. Agregar permiso Administrar páginas.

    ![Agregar permiso Administrar páginas](../media/FBCimage39.png)

16. Obtener la aplicación revisada por Facebook.

    ![Obtener la aplicación revisada por Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>Paso 4: Configurar la aplicación web del conector

1. Vaya a (donde AzureAppResourceName es el nombre del recurso de la `https://<AzureAppResourceName>.azurewebsites.net` aplicación de Azure al que llamó en el paso 4). Por ejemplo, si el nombre es **fbconnector**, vaya a `https://fbconnector.azurewebsites.net` . La página principal de la aplicación tendrá el aspecto de la siguiente captura de pantalla:

   ![Ir a la aplicación web de conector](../media/FBCimage41.png)

2. Haga **clic en** Configurar para mostrar una página de inicio de sesión.

   ![Haga clic en Configurar para mostrar una página de inicio de sesión](../media/FBCimage42.png)

3. En el cuadro Identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2). En el cuadro contraseña, escriba o pegue APISecretKey (que obtuvo en el paso 2) y, a **continuación,** haga clic en Establecer configuración Configuración para mostrar la página de detalles de configuración.

    ![Inicie sesión con el identificador de inquilino y la contraseña y vaya a la página de detalles de configuración](../media/FBCimage43.png)

4. Escriba las siguientes opciones de configuración

   - **Id. de aplicación de Facebook:** El identificador de aplicación de la aplicación de Facebook que obtuvo en el paso 3.

   - **Secreto de aplicación de Facebook:** El secreto de la aplicación para la aplicación de Facebook que obtuvo en el paso 3.

   - **Los webhooks de Facebook comprueban el token:** El token de comprobación que creó en el paso 3.

   - **Id. de aplicación de AAD:** El identificador de aplicación para la Azure Active Directory que creaste en el paso 1.

   - **Secreto de aplicación de AAD:** Valor del secreto APISecretKey que creó en el paso 1.

5. Haga **clic en** Guardar para guardar la configuración del conector.

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: Configurar un conector de Facebook en el centro de Microsoft 365 cumplimiento

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic **en Conectores de datos** en la navegación izquierda.

2. En la página **Conectores de datos** de las páginas **de Facebook Empresa,** haga clic en **Ver**.

3. En la página **Páginas empresariales de Facebook,** haga clic **en Agregar conector**.

4. En la **página Términos de** servicio, haga clic **en Aceptar**.

5. En la **página Agregar credenciales para la aplicación del conector,** escriba la siguiente información y, a continuación, haga clic en Validar **conexión**.

   ![Escribir credenciales de la aplicación del conector](../media/TCimage38.png)

   - En el **cuadro** Nombre, escriba un nombre para el conector, como la página **de noticias de Facebook**.

   - En el **cuadro Dirección URL de** conexión, escriba o pegue la dirección URL del servicio de aplicaciones de Azure; por ejemplo `https://fbconnector.azurewebsites.net` .

   - En el **cuadro Contraseña,** escriba o pegue el valor de APISecretKey que agregó en el paso 2.

   - En el **cuadro Id. de** aplicación de Azure, escriba o pegue el valor del identificador de aplicación (cliente) llamado también como id. de aplicación de AAD que creó en el paso 1.

6. Después de validar correctamente la conexión, haga clic en **Siguiente**.

7. En la **página Autorizar Microsoft 365** importar datos, escriba o pegue la APISecretKey de nuevo y, a continuación, haga clic en Iniciar sesión en la aplicación **web**.

8. En la página Configurar la aplicación del conector de **Facebook,** haga clic en Iniciar sesión con **Facebook** e inicie sesión con las credenciales de la cuenta de las páginas de Facebook Empresa de su organización. Asegúrate de que la cuenta de Facebook en la que has iniciado sesión tiene asignada la función de administrador de las páginas de Facebook Business de la organización.

   ![Iniciar sesión con Facebook](../media/FBCimage50.png)

9. Se muestra una lista de las páginas empresariales administradas por la cuenta de Facebook en la que inició sesión. Seleccione la página que desea archivar y, a continuación, haga clic **en Siguiente**.

   ![Seleccione la página de negocio de la organización que desea archivar](../media/FBCimage52.png)

10. Haga **clic en** Continuar para salir de la configuración de la aplicación de servicio del conector.

11. En la **página Establecer filtros,** puede aplicar un filtro para importar inicialmente elementos que tienen una edad determinada. Seleccione una antigüedad y, a continuación, haga clic **en Siguiente**.

12. En la **página Elegir ubicación de** almacenamiento, escriba la dirección de correo electrónico de Microsoft 365 buzón al que se importarán los elementos de Facebook y, a continuación, haga clic en **Siguiente**.

13. Haga **clic en** Siguiente para revisar la configuración del conector y, a continuación, haga clic en **Finalizar** para completar la configuración del conector.

14. En el Centro de cumplimiento, vaya a la  página **Conectores** de datos y haga clic en la pestaña Conectores para ver el progreso del proceso de importación.
