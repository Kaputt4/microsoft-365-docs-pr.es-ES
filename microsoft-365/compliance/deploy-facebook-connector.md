---
title: Implementación de un conector para archivar datos de páginas empresariales de Facebook
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
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden configurar un conector nativo para importar y archivar las páginas de empresa de Facebook a Microsoft 365. Una vez que estos datos se han importado a Microsoft 365, puede usar las características de cumplimiento, como las directivas de retención legal, búsqueda de contenido y retención, para administrar el gobierno de los datos de Facebook de la organización.
ms.openlocfilehash: 48747dade98701303c4ca6a8c00192ec7faff34a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076209"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>Implementación de un conector para archivar datos de páginas empresariales de Facebook

Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación 365 de Microsoft para importar datos de las páginas empresariales de Facebook a Microsoft 365. Para obtener información general de alto nivel de este proceso y una lista de los requisitos previos necesarios para implementar un conector de Facebook, consulte [configurar un conector para archivar datos de Facebook](archive-facebook-data-with-sample-connector.md). 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: crear una aplicación en Azure Active Directory

1. Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global de Office 365.

    ![Crear una aplicación en AAD](../media/FBCimage1.png)

2. En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.

    ![Haga clic en Azure Active Directory](../media/FBCimage2.png)

3. En el panel de navegación izquierdo, haga clic en **registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **nuevo registro**.

    ![Haga clic en * * registros de aplicaciones (versión preliminar) * * y, a continuación, haga clic en * * registro nuevo * *](../media/FBCimage3.png)

4. Registrar la aplicación. En URI de redireccionamiento, seleccione Web en la lista desplegable tipo de <https://portal.azure.com> aplicación y, a continuación, escriba en el cuadro del URI.

   ![Registrar la aplicación](../media/FBCimage4.png)

5. Copie el identificador de la **aplicación (cliente)** y el **directorio (inquilino)** y guárdelos en un archivo de texto u otra ubicación segura. Estos identificadores se usan en pasos posteriores.

   ![Copiar el identificador de la aplicación y el identificador del directorio y guardarlos](../media/FBCimage5.png)

6. Vaya a **certificados & secretos para la nueva aplicación.**

   ![Ir a certificados & secretos para la nueva aplicación](../media/FBCimage6.png)

7. Haga clic en **nuevo secreto de cliente**

   ![Haga clic en nuevo secreto de cliente](../media/FBCimage7.png)

8. Cree un secreto nuevo. En el cuadro Descripción, escriba el secreto y, a continuación, elija un período de expiración. 

    ![Escriba el secreto y, a continuación, elija un período de expiración](../media/FBCimage8.png)

9. Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento. Este es el secreto de la aplicación de AAD que se usa en pasos posteriores.

   ![Copiar el valor del secreto y guardarlo](../media/FBCimage9.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Paso 2: implementar el servicio Web del conector desde GitHub a su cuenta de Azure

1. Vaya a [este sitio de github](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) y haga clic en **implementar en Azure**.

    ![Haga clic en implementar en Azure](../media/FBCGithubApp.png)

2. Después de hacer clic en **implementar en Azure**, se le redirigirá a un portal de Azure con una página de plantilla personalizada. Rellene los detalles de **conceptos básicos** y **configuración** y, a continuación, haga clic en **comprar**.

    - **Suscripción:** Seleccione la suscripción a Azure en la que desea implementar el servicio Web de conector de páginas empresariales de Facebook.
    
    - **Grupo de recursos:** Elija o cree un nuevo grupo de recursos. Un grupo de recursos es un contenedor que contiene recursos relacionados para una solución de Azure.

    - **Ubicación:** Elija una ubicación.

    - **Nombre de la aplicación web:** Proporcione un nombre único para la aplicación web del conector. El nombre debe tener entre 3 y 18 caracteres de longitud. Este nombre se usa para crear la dirección URL de Azure App Service; por ejemplo, si proporciona el nombre de la aplicación Web de **FBconnector** , la dirección URL del servicio de aplicación de Azure será **FBconnector.azurewebsites.net**.
    
    - **tenantId:** El identificador de inquilino de su organización de Microsoft 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 1.
    
   - **APISecretKey:** Puede escribir cualquier valor como secreto. Se usa para obtener acceso a la aplicación web del conector en el paso 5.
   
     ![Haga clic en crear un recurso y escriba la cuenta de almacenamiento](../media/FBCimage12.png)

3. Una vez completada la implementación, la página tendrá un aspecto similar al de la siguiente captura de pantalla:

     ![Haga clic en almacenamiento y, a continuación, en cuenta de almacenamiento](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>Paso 3: registrar la aplicación de Facebook

1. Vaya a <https://developers.facebook.com>, inicie sesión con las credenciales de la cuenta de las páginas de empresa de Facebook de su organización y, a continuación, haga clic en **Agregar nueva aplicación**.

   ![Adición de una nueva aplicación para la página empresarial de Facebook](../media/FBCimage25.png)

2. Cree un nuevo identificador de aplicación.

   ![Crear un nuevo identificador de aplicación](../media/FBCimage26.png)

3. En el panel de navegación izquierdo, haga clic en **Agregar productos** y, a continuación, haga clic en **configurar** en la ventana de **Inicio de sesión de Facebook** .

   ![Haga clic en agregar productos](../media/FBCimage27.png)

4. En la página integrar inicio de sesión de Facebook, haga clic en **Web**.

   ![Haga clic en Web en la página integrar inicio de sesión de Facebook](../media/FBCimage28.png)

5. Agregue la dirección URL de Azure App Service; por ejemplo `https://fbconnector.azurewebsites.net`.

   ![Agregar la dirección URL de Azure App Service](../media/FBCimage29.png)

6. Complete la sección QuickStart de la configuración de inicio de sesión de Facebook.

   ![Completar la sección QuickStart](../media/FBCimage30.png)

7. En el panel de navegación izquierdo, en **Inicio de sesión de Facebook**, haga clic en **configuración**y agregue el URI de redireccionamiento de OAuth en el cuadro **válidos URI de redirección de OAuth** . Use el formato ** \<connectorserviceuri>/views/facebookoauth**, donde el valor de connectorserviceuri es la dirección URL de Azure App Service para su organización; por ejemplo, `https://fbconnector.azurewebsites.net`.

   ![Agregar el URI de redireccionamiento de OAuth al cuadro URI de redireccionamiento de OAuth válido](../media/FBCimage31.png)

8. En el panel de navegación izquierdo, haga clic en **Agregar productos** y, a continuación, en **webhooks.** En el menú desplegable **Página** , haga clic en **Página**. 

   ![Haga clic en agregar productos y, a continuación, haga clic en * * webhooks](../media/FBCimage32.png)

9. Agregue la dirección URL de devolución de llamada de webhook y agregue un token de comprobación. El formato de la dirección URL de devolución de llamada, use el formato ** <connectorserviceuri>/API/FbPageWebhook**, donde el valor de connectorserviceuri es la dirección URL de Azure App Service para su organización; por ejemplo `https://fbconnector.azurewebsites.net`. 

    El token de comprobación debe ser similar a una contraseña segura. Copie el token de comprobación en un archivo de texto u otra ubicación de almacenamiento.

        ![Add the verify token](../media/FBCimage33.png)

10. Pruebe y suscríbase al extremo para la fuente.

    ![Probar y suscribirse al extremo](../media/FBCimage34.png)

11. Agregue una dirección URL de privacidad, un icono de aplicación y un uso empresarial. Además, copie el identificador de aplicación y el secreto de aplicación en un archivo de texto u otra ubicación de almacenamiento.

    ![Agregar una dirección URL de privacidad, un icono de aplicación y un uso empresarial](../media/FBCimage35.png)

12. Hacer que la aplicación sea pública.

    ![Hacer que la aplicación sea pública](../media/FBCimage36.png)

13. Agregue un usuario al rol de administrador o de evaluador.

    ![Agregar un usuario al rol de administrador o de evaluador](../media/FBCimage37.png)

14. Agregue el permiso de **acceso a contenido público** de la página.

    ![DD la página permiso de acceso al contenido público](../media/FBCimage38.png)

15. Permiso agregar páginas de administración.

    ![Permiso para agregar páginas de administración](../media/FBCimage39.png)

16. Obtenga la aplicación revisada por Facebook.

    ![Obtener la aplicación revisada por Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>Paso 4: configurar la aplicación web del conector

1. Vaya a https://\<AzureAppResourceName>. azurewebsites.net (donde AzureAppResourceName es el nombre del recurso de la aplicación de Azure que ha nombrado en el paso 4), por ejemplo, si el nombre es `https://fbconnector.azurewebsites.net` **FBconnector**, vaya a. La Página principal de la aplicación será similar a la siguiente captura de pantalla:

   ![Ir a la aplicación web del conector](../media/FBCimage41.png)

2. Haga clic en **configurar** para mostrar una página de inicio de sesión.
 
   ![Haga clic en configurar para mostrar una página de inicio de sesión](../media/FBCimage42.png)

3. En el cuadro identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2). En el cuadro contraseña, escriba o pegue el APISecretKey (que obtuvo en el paso 2) y, a continuación, haga clic en **establecer valores de configuración** para mostrar la página Detalles de la configuración.

    ![Iniciar sesión con el identificador de inquilino y la contraseña y ir a la página de detalles de configuración](../media/FBCimage43.png)

4. Especifique las siguientes opciones de configuración 

   - **Identificador de la aplicación de Facebook:** El identificador de aplicación de la aplicación de Facebook que obtuvo en el paso 3.
   
   - **Secreto de la aplicación de Facebook:** El secreto de aplicación para la aplicación de Facebook que obtuvo en el paso 3.
   
   - **Token de comprobación de los webhooks de Facebook:** El token de comprobación que ha creado en el paso 3.
   
   - **Identificador de la aplicación de AAD:** El identificador de aplicación de la aplicación de Azure Active Directory que ha creado en el paso 1.
   
   - **Secreto de la aplicación AAD:** El valor del secreto APISecretKey que creó en el paso 1.

5. Haga clic en **Guardar** para guardar la configuración del conector.

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: configurar un conector de Facebook en el centro de cumplimiento de Microsoft 365

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. En la página **conectores de datos (vista previa)** , en **páginas empresariales de Facebook**, haga clic en **Ver**.

3. En la página **páginas empresariales de Facebook** , haga clic en **Agregar conector**.

4. En la página **condiciones de servicio** , haga clic en **Aceptar**.

5.  En la página **agregar credenciales para la aplicación de conector** , escriba la siguiente información y, a continuación, haga clic en **validar conexión**.

    ![Especificar credenciales de aplicación de conector](../media/TCimage38.png)

    - En el cuadro **nombre** , escriba un nombre para el conector, como **Página de noticias de Facebook**.
    
    - En el cuadro **dirección URL de conexión** , escriba o pegue la dirección URL de Azure App Service; por ejemplo `https://fbconnector.azurewebsites.net`.
    
    - En el cuadro **contraseña** , escriba o pegue el valor de la APISecretKey que agregó en el paso 2.
    
    - En el cuadro identificador de la **aplicación de Azure** , escriba o pegue el valor del identificador de la aplicación (cliente) también denominado identificador de la aplicación AAD que creó en el paso 1.
 
6. Una vez validada correctamente la conexión, haga clic en **siguiente**.

7. En la página **autorizar a Microsoft 365 a importar datos** , escriba o pegue el APISecretKey de nuevo y, a continuación, haga clic en **iniciar sesión en la aplicación web**.

8. En la página **configurar la aplicación** para el conector de Facebook, haga clic en **iniciar sesión con Facebook** e inicie sesión con las credenciales de la cuenta de las páginas de empresa de Facebook de su organización. Asegúrese de que la cuenta de Facebook a la que ha iniciado sesión tenga asignado el rol de administrador de las páginas empresariales de Facebook de su organización.

   ![Iniciar sesión con Facebook](../media/FBCimage50.png)

9. Se muestra una lista de las páginas de negocio administradas por la cuenta de Facebook en la que inició sesión. Seleccione la página que desea archivar y, a continuación, haga clic en **siguiente**.

    ![Seleccione la página de empresa de la organización que desea archivar](../media/FBCimage52.png)

10. Haga clic en **continuar** para salir de la instalación de la aplicación del servicio conector.

11. En la página **Establecer filtros** , puede aplicar un filtro para importar inicialmente los elementos que tienen una antigüedad determinada. Seleccione una edad y, a continuación, haga clic en **siguiente**.

12. En la página **Elegir ubicación de almacenamiento** , escriba la dirección de correo electrónico del buzón de correo de Microsoft 365 al que se importarán los elementos de Facebook y, a continuación, haga clic en **siguiente**.

13. En el **acuerdo proporcionar consentimiento del administrador**, haga clic en **proporcionar consentimiento** y, a continuación, siga los pasos. Debe ser administrador global para dar su consentimiento al servicio de importación de Office 365 para obtener acceso a los datos de su organización.

14. Haga clic en **siguiente** para revisar la configuración del conector y, a continuación, haga clic en **Finalizar** para completar la configuración del conector.

15. En el centro de cumplimiento, vaya a la página **conectores de datos** y haga clic en la pestaña **conectores** para ver el progreso del proceso de importación.
