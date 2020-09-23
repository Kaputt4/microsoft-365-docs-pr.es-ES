---
title: Implementar un conector para archivar datos de Twitter
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
description: Los administradores pueden configurar un conector nativo para importar y archivar datos de Twitter a Microsoft 365. Una vez que estos datos se han importado a Microsoft 365, puede usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar el gobierno de los datos de Twitter de la organización.
ms.openlocfilehash: 01c4901544e47cd1c361a132e144440f00bd8504
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200833"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Implementar un conector para archivar datos de Twitter

Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos de la cuenta de Twitter de su organización a Microsoft 365. Para obtener una introducción de alto nivel de este proceso y una lista de los requisitos previos necesarios para implementar un conector de Twitter, consulte [configurar un conector para archivar datos de Twitter ](archive-twitter-data-with-sample-connector.md). 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: crear una aplicación en Azure Active Directory

1. Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global.

   ![Iniciar sesión en Azure](../media/TCimage01.png)

2. En el panel de navegación izquierdo, haga clic en **Azure Active Directory**.

   ![Ir a Azure Active Directory](../media/TCimage02.png)

3. En el panel de navegación izquierdo, haga clic en **registros de aplicaciones (versión preliminar)** y, a continuación, haga clic en **nuevo registro**.

   ![Crear un nuevo registro de la aplicación](../media/TCimage03.png)

4. Registrar la aplicación. En **URI de redireccionamiento (opcional)**, seleccione **Web** en la lista desplegable tipo de aplicación y, a continuación, escriba `https://portal.azure.com` en el cuadro del URI.

   ![Tipo https://portal.azure.com de URI de redireccionamiento ](../media/TCimage04.png)

5. Copie el identificador de la **aplicación (cliente)** y el **directorio (inquilino)** y guárdelos en un archivo de texto u otra ubicación segura. Estos identificadores se usan en pasos posteriores.

    ![Copiar y guardar el identificador de la aplicación y el identificador del directorio](../media/TCimage05.png)

6. Vaya a **certificados & secretos para la nueva aplicación** y, en **secretos de cliente** , haga clic en **nuevo secreto de cliente**.

   ![Crear un nuevo secreto de cliente](../media/TCimage06.png)

7. Cree un secreto nuevo. En el cuadro Descripción, escriba el secreto y, a continuación, elija un período de expiración. 

   ![Escribir el secreto y elegir período de expiración](../media/TCimage08.png)

8. Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento. Este es el secreto de la aplicación de AAD que se usa en pasos posteriores.

   ![Copiar y guardar el secreto](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Paso 2: implementar el servicio Web del conector desde GitHub a su cuenta de Azure

1. Vaya a [este sitio de github](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) y haga clic en **implementar en Azure**.

    ![Ir a la Página principal de Azure](../media/FBCimage11.png)

2. Después de hacer clic en **implementar en Azure**, se le redirigirá a un portal de Azure con una página de plantilla personalizada. Rellene los detalles de **conceptos básicos** y **configuración** y, a continuación, haga clic en **comprar**.

   ![Haga clic en crear un recurso y escriba la cuenta de almacenamiento](../media/FBCimage12.png)

    - **Suscripción:** Seleccione su suscripción a Azure en la que desea implementar el servicio Web del conector de Twitter.
    
    - **Grupo de recursos:** Elija o cree un nuevo grupo de recursos. Un grupo de recursos es un contenedor que contiene recursos relacionados para una solución de Azure.

    - **Ubicación:** Elija una ubicación.

    - **Nombre de la aplicación web:** Proporcione un nombre único para la aplicación web del conector. El nombre debe tener entre 3 y 18 caracteres de longitud. Este nombre se usa para crear la dirección URL de Azure App Service; por ejemplo, si proporciona el nombre de la aplicación Web de **twitterconnector** , la dirección URL del servicio de aplicación de Azure será **twitterconnector.azurewebsites.net**.
    
    - **tenantId:** El identificador de inquilino de su organización de Microsoft 365 que copió después de crear la aplicación de conector de Facebook en Azure Active Directory en el paso 1.
    
   - **APISecretKey:** Puede escribir cualquier valor como secreto. Se usa para obtener acceso a la aplicación web del conector en el paso 5.

3. Una vez completada la implementación, la página tendrá un aspecto similar al de la siguiente captura de pantalla:

    ![Haga clic en almacenamiento y, a continuación, en cuenta de almacenamiento](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>Paso 3: crear la aplicación de Twitter

1. Vaya a https://developer.twitter.com , inicie sesión con las credenciales de la cuenta de desarrollador de su organización y, a continuación, haga clic en **aplicaciones**.

   ![Ir a https://developer.twitter.com e iniciar sesión](../media/TCimage25-5.png)
2. Haga clic en **crear una aplicación**.
   
   ![Ir a la página de aplicaciones para crear una aplicación](../media/TCimage26.png)

3. En **detalles**de la aplicación, agregue información sobre la aplicación.

   ![Escribir información sobre la aplicación](../media/TCimage27.png)

4. En el panel del programador de Twitter, seleccione la aplicación que acaba de crear y, a continuación, haga clic en **detalles**.
   
   ![Copiar y guardar el identificador de la aplicación](../media/TCimage28.png)

5. En la pestaña **claves y tokens** , en **claves** de la API de consumidor, copie la clave de API y la clave secreta de la API y guárdelas en un archivo de texto u otra ubicación de almacenamiento. A continuación, haga clic en **crear** para generar un token de acceso y un secreto de acceso y cópielos en un archivo de texto u otra ubicación de almacenamiento.
   
   ![Copiar y guardar en clave secreta de la API](../media/TCimage29.png)

   A continuación, haga clic en **crear** para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.

6. Haga clic en la pestaña **permisos** y configure los permisos como se muestra en la siguiente captura de pantalla:

   ![Configurar permisos](../media/TCimage30.png)

7. Una vez que haya guardado la configuración de permisos, haga clic en la pestaña detalles de la **aplicación** y, a continuación, haga clic en **Editar > editar detalles**.

   ![Editar los detalles de la aplicación](../media/TCimage31.png)

8. Realice las siguientes tareas:

   - Active la casilla para permitir que la aplicación conector inicie sesión en Twitter.
   
   - Agregue el URI de redireccionamiento de OAuth con el siguiente formato: ** \<connectorserviceuri> /views/TwitterOAuth**, donde el valor de *connectorserviceuri* es la dirección URL de Azure App Service para su organización; por ejemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .

    ![Permitir que la aplicación conector inicie sesión en Twitter y agregue el URI de redireccionamiento de OAuth](../media/TCimage32.png)

La aplicación de desarrollo de Twitter ya está lista para usarse.

## <a name="step-4-configure-the-connector-web-app"></a>Paso 4: configurar la aplicación web del conector 

1. Vaya a https:// \<AzureAppResourceName> . azurewebsites.net (donde **AzureAppResourceName** es el nombre del recurso de la aplicación de Azure que ha nombrado en el paso 4). Por ejemplo, si el nombre es **twitterconnector**, vaya a https://twitterconnector.azurewebsites.net . La Página principal de la aplicación es similar a la siguiente captura de pantalla:

   ![Ir a la página de recursos de la aplicación de Azure](../media/FBCimage41.png)

2. Haga clic en **configurar** para mostrar una página de inicio de sesión.

   ![Haga clic en configurar para mostrar la página de inicio de sesión](../media/FBCimage42.png)

3. En el cuadro identificador de inquilino, escriba o pegue el identificador de inquilino (que obtuvo en el paso 2). En el cuadro contraseña, escriba o pegue el APISecretKey (que obtuvo en el paso 2) y, a continuación, haga clic en **establecer valores de configuración** para mostrar la página Detalles de la configuración.

   ![Iniciar sesión con el identificador de inquilino y la clave secreta de API](../media/TCimage35.png)

4. Especifique las siguientes opciones de configuración 

   - **Clave de API de Twitter:** La clave de la API de la aplicación de Twitter que creó en el paso 3.
   
   - **Clave secreta de la API de Twitter:** Clave secreta de la API para la aplicación de Twitter que creó en el paso 3.
   
   - **Token de acceso de Twitter:** El token de acceso que ha creado en el paso 3.
   
   - **Secreto de token de acceso de Twitter:** El secreto de token de acceso que creó en el paso 3.
   
   - **Identificador de la aplicación de AAD:** El identificador de aplicación de la aplicación de Azure Active Directory que creó en el paso 1
   
   - **Secreto de la aplicación AAD:** El valor del secreto APISecretKey que creó en el paso 1.

5. Haga clic en **Guardar** para guardar la configuración del conector.

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: configurar un conector de Twitter en el centro de cumplimiento de Microsoft 365

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. En la página **conectores de datos** , en **Twitter**, haga clic en **Ver**.

3. En la página de **Twitter** , haga clic en **Agregar conector**.

4. En la página **condiciones de servicio** , haga clic en **Aceptar**.

5. En la página **agregar credenciales para la aplicación de conector** , escriba la siguiente información y, a continuación, haga clic en **validar conexión**.

   ![Especificar credenciales de aplicación de conector](../media/TCimage38.png)

    - En el cuadro **nombre** , escriba un nombre para el conector, como **controlador de ayuda de Twitter**.
    
    - En el cuadro **dirección URL del conector** , escriba o pegue la dirección URL de Azure App Service; por ejemplo `https://twitterconnector.azurewebsites.net` .
    
    - En el cuadro **contraseña** , escriba o pegue el valor de la APISecretKey que creó en el paso 2.
    
    - En el cuadro identificador de la **aplicación de Azure** , escriba o pegue el valor del identificador de aplicación de la aplicación de Azure (también denominado identificador de *cliente*) que obtuvo en el paso 1.

6. Una vez validada correctamente la conexión, haga clic en **siguiente**.

7. En la página **autorizar a Microsoft 365 a importar datos** , escriba o pegue el APISecretKey de nuevo y, a continuación, haga clic en  **iniciar sesión en la aplicación web**.

8. Haga clic en **iniciar sesión con Twitter**.

9. En la página inicio de sesión de Twitter, inicie sesión con las credenciales de la cuenta de Twitter de su organización.

   ![Iniciar sesión en la cuenta de Twitter](../media/TCimage42.png)

   Después de iniciar sesión, la página de Twitter mostrará el siguiente mensaje de error "el trabajo del conector de Twitter se configuró correctamente".

10. Haga clic en **continuar** para completar la configuración del conector de Twitter.

11. En la página **Establecer filtros** , puede aplicar un filtro para importar inicialmente los elementos que tienen una antigüedad determinada. Seleccione una edad y, a continuación, haga clic en **siguiente**.

12. En la página **Elegir ubicación de almacenamiento** , escriba la dirección de correo electrónico del buzón de correo de Microsoft 365 al que se importarán los elementos de Twitter y, a continuación, haga clic en **siguiente**.

13. En el **acuerdo proporcionar consentimiento del administrador**, haga clic en **proporcionar consentimiento** y, a continuación, siga los pasos. Debe ser administrador global para dar su consentimiento al servicio de importación de Office 365 para obtener acceso a los datos de su organización.

14. Haga clic en **siguiente** para revisar la configuración del conector y, a continuación, haga clic en **Finalizar** para completar la configuración del conector.

15. En el centro de cumplimiento, vaya a la página **conectores de datos** y haga clic en la pestaña **conectores** para ver el progreso del proceso de importación.
