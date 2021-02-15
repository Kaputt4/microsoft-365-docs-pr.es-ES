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
description: Los administradores pueden configurar un conector nativo para importar y archivar datos de Twitter en Microsoft 365. Después de importar estos datos a Microsoft 365, puede usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar el gobierno de los datos de Twitter de su organización.
ms.openlocfilehash: 0dd996802964b2a2fc58d26e23af57193c89ee8c
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619916"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Implementar un conector para archivar datos de Twitter

Este artículo contiene el proceso paso a paso para implementar un conector que usa el servicio de importación de Office 365 para importar datos desde la cuenta de Twitter de su organización a Microsoft 365. Para obtener información general de alto nivel sobre este proceso y una lista de los requisitos previos necesarios para implementar un conector de Twitter, vea Configurar un conector para archivar [datos de Twitter. ](archive-twitter-data-with-sample-connector.md) 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Paso 1: Crear una aplicación en Azure Active Directory

1. Vaya a <https://portal.azure.com> e inicie sesión con las credenciales de una cuenta de administrador global.

   ![Iniciar sesión en Azure](../media/TCimage01.png)

2. En el panel de navegación izquierdo, haga clic **en Azure Active Directory.**

   ![Ir a Azure Active Directory](../media/TCimage02.png)

3. En el panel de navegación izquierdo, haga clic en **Registros de aplicaciones (vista previa)** y, a continuación, haga clic **en Nuevo registro.**

   ![Crear un nuevo registro de aplicación](../media/TCimage03.png)

4. Registre la aplicación. En **URI de redireccionamiento (opcional),** seleccione **Web** en la lista desplegable de tipos de aplicación y, a continuación, escriba el cuadro para `https://portal.azure.com` el URI.

   ![Tipo https://portal.azure.com para el URI de redireccionamiento ](../media/TCimage04.png)

5. Copie el **id. de aplicación (cliente)** y el id. de directorio **(inquilino)** y guárdelos en un archivo de texto u otra ubicación segura. Estos iDs se usan en pasos posteriores.

    ![Copiar y guardar el id. de aplicación y el id. de directorio](../media/TCimage05.png)

6. Vaya a **Certificados & secretos de la** nueva aplicación y, en Secretos **de** cliente, haga clic en Nuevo secreto **de cliente.**

   ![Crear un nuevo secreto de cliente](../media/TCimage06.png)

7. Cree un nuevo secreto. En el cuadro de descripción, escriba el secreto y, a continuación, elija un período de expiración. 

   ![Escriba el secreto y elija el período de expiración](../media/TCimage08.png)

8. Copie el valor del secreto y guárdelo en un archivo de texto u otra ubicación de almacenamiento. Este es el secreto de aplicación de AAD que se usa en pasos posteriores.

   ![Copiar y guardar el secreto](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Paso 2: Implementar el servicio web del conector desde GitHub en su cuenta de Azure

1. Vaya a [este sitio de GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) y haga **clic en Implementar en Azure.**

    ![Ir a la página principal de Azure](../media/FBCimage11.png)

2. Después de hacer **clic en Implementar en Azure,** se le redirigirá a un portal de Azure con una página de plantilla personalizada. Rellene los detalles **de conceptos básicos** **y configuración** y, a continuación, haga clic en **Comprar**.

   ![Haga clic en Crear una cuenta de almacenamiento de tipo y recurso](../media/FBCimage12.png)

    - **Suscripción:** Seleccione la suscripción de Azure en la que desea implementar el servicio web del conector de Twitter.
    
    - **Grupo de recursos:** Elija o cree un nuevo grupo de recursos. Un grupo de recursos es un contenedor que contiene recursos relacionados para una solución de Azure.

    - **Ubicación:** Elija una ubicación.

    - **Nombre de aplicación web:** Proporcione un nombre único para la aplicación web del conector. El nombre debe tener entre 3 y 18 caracteres de longitud. Este nombre se usa para crear la dirección URL del servicio de aplicaciones de Azure; por ejemplo, si proporciona el nombre de la aplicación web **de twitterconnector,** la dirección URL del servicio de aplicaciones de Azure será **twitterconnector.azurewebsites.net**.
    
    - **tenantId:** El id. de inquilino de su organización de Microsoft 365 que copió después de crear la aplicación conector de Facebook en Azure Active Directory en el paso 1.
    
   - **APISecretKey:** Puede escribir cualquier valor como secreto. Esto se usa para obtener acceso a la aplicación web del conector en el paso 5.

3. Una vez que la implementación se realiza correctamente, la página tendrá un aspecto similar a la siguiente captura de pantalla:

    ![Haga clic en Almacenamiento y, a continuación, haga clic en Cuenta de almacenamiento](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>Paso 3: Crear la aplicación de Twitter

1. Vaya a , inicie sesión con las credenciales de la cuenta de desarrollador de su organización y, a continuación, haga https://developer.twitter.com clic en **Aplicaciones.**

   ![Ir e https://developer.twitter.com iniciar sesión](../media/TCimage25-5.png)
2. Haz **clic en Crear una aplicación.**
   
   ![Ir a la página Aplicaciones para crear una aplicación](../media/TCimage26.png)

3. En **Detalles de la** aplicación, agregue información sobre la aplicación.

   ![Escribir información sobre la aplicación](../media/TCimage27.png)

4. En el panel del desarrollador de Twitter, seleccione la aplicación que acaba de crear y, a continuación, haga clic en **Detalles.**
   
   ![Copiar y guardar el id. de aplicación](../media/TCimage28.png)

5. En la **pestaña Claves y tokens,** en Claves **de la API** de consumidor, copie la clave de API y la clave secreta de la API y guárdelas en un archivo de texto u otra ubicación de almacenamiento. A **continuación,** haga clic en Crear para generar un token de acceso y un secreto de token de acceso y copiarlos en un archivo de texto u otra ubicación de almacenamiento.
   
   ![Copiar y guardar en clave secreta de API](../media/TCimage29.png)

   A **continuación,** haga clic en Crear para generar un token de acceso y un secreto de token de acceso, y cópielos en un archivo de texto u otra ubicación de almacenamiento.

6. Haga clic **en la pestaña Permisos** y configure los permisos como se muestra en la siguiente captura de pantalla:

   ![Configurar permisos](../media/TCimage30.png)

7. Después de guardar la configuración de permisos, haga clic en la **pestaña Detalles** de la aplicación y, a continuación, haga clic en Editar > **Editar detalles.**

   ![Editar los detalles de la aplicación](../media/TCimage31.png)

8. Realice las siguientes tareas:

   - Active la casilla para permitir que la aplicación del conector inicie sesión en Twitter.
   
   - Agregue el URI de redireccionamiento de OAuth con el siguiente formato: **\<connectorserviceuri> /Views/TwitterOAuth**, donde el valor de *connectorserviceuri* es la dirección URL del servicio de aplicaciones de Azure para su organización; por ejemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .

    ![Permitir que la aplicación del conector inicie sesión en Twitter y agregue el URI de redireccionamiento de OAuth](../media/TCimage32.png)

La aplicación para desarrolladores de Twitter ya está lista para usarse.

## <a name="step-4-configure-the-connector-web-app"></a>Paso 4: Configurar la aplicación web del conector 

1. Ve a https:// \<AzureAppResourceName> .azurewebsites.net (donde **AzureAppResourceName** es el nombre del recurso de la aplicación de Azure que llamaste en el paso 4). Por ejemplo, si el nombre es **twitterconnector**, vaya a https://twitterconnector.azurewebsites.net . La página principal de la aplicación es similar a la siguiente captura de pantalla:

   ![Ir a la página de recursos de la aplicación de Azure](../media/FBCimage41.png)

2. Haga **clic en Configurar** para mostrar una página de inicio de sesión.

   ![Haga clic en Configurar para mostrar la página de inicio de sesión](../media/FBCimage42.png)

3. En el cuadro Id. de inquilino, escriba o pegue el id. de inquilino (que obtuvo en el paso 2). En el cuadro de contraseña, escriba o pegue la APISecretKey (que  obtuvo en el paso 2) y, a continuación, haga clic en Establecer opciones de configuración para mostrar la página de detalles de configuración.

   ![Iniciar sesión con el id. de inquilino y la clave secreta de API](../media/TCimage35.png)

4. Escriba las siguientes opciones de configuración 

   - **Clave de api de Twitter:** La clave de API para la aplicación de Twitter que creó en el paso 3.
   
   - **Clave secreta de api de Twitter:** La clave secreta de API para la aplicación de Twitter que creó en el paso 3.
   
   - **Token de acceso de Twitter:** Token de acceso que creó en el paso 3.
   
   - **Secreto de token de acceso de Twitter:** El secreto de token de acceso que creó en el paso 3.
   
   - **Id. de aplicación de AAD:** El identificador de aplicación de la aplicación de Azure Active Directory que creó en el paso 1
   
   - **Secreto de aplicación de AAD:** El valor del secreto APISecretKey que creó en el paso 1.

5. Haga **clic en Guardar** para guardar la configuración del conector.

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Paso 5: Configurar un conector de Twitter en el Centro de cumplimiento de Microsoft 365

1. Vaya a conectores de datos y, a continuación, [https://compliance.microsoft.com](https://compliance.microsoft.com) haga clic en **Conectores** de datos en el panel de navegación izquierdo.

2. En la **página Conectores de** datos en **Twitter,** haga clic **en Ver**.

3. En la página **de Twitter,** haga clic **en Agregar conector.**

4. En la **página Términos de** servicio, haga clic **en Aceptar.**

5. En la **página Agregar credenciales para la aplicación del** conector, escriba la siguiente información y, a continuación, haga clic en Validar **conexión.**

   ![Escribir las credenciales de la aplicación del conector](../media/TCimage38.png)

    - En el **cuadro** Nombre, escriba un nombre para el conector, como el controlador de **ayuda de Twitter.**
    
    - En el **cuadro Dirección URL del** conector, escriba o pegue la dirección URL del servicio de aplicaciones de Azure; por `https://twitterconnector.azurewebsites.net` ejemplo.
    
    - En el **cuadro** Contraseña, escriba o pegue el valor de APISecretKey que creó en el paso 2.
    
    - En el **cuadro Id.** de aplicación de Azure, escriba o pegue el valor del Identificador de aplicación de Azure (también denominado identificador de *cliente)* que obtuvo en el paso 1.

6. Una vez validada correctamente la conexión, haga clic en **Siguiente.**

7. En la **página Autorizar a Microsoft 365** para importar datos, vuelva a escribir o pegar APISecretKey y, a continuación, haga clic en Iniciar sesión en la aplicación **web.**

8. Haga clic **en Iniciar sesión con Twitter.**

9. En la página de inicio de sesión de Twitter, inicie sesión con las credenciales de la cuenta de Twitter de su organización.

   ![Iniciar sesión en la cuenta de Twitter](../media/TCimage42.png)

   Después de iniciar sesión, la página de Twitter mostrará el siguiente mensaje: "El trabajo del conector de Twitter se ha configurado correctamente".

10. Haga **clic en** Continuar para completar la configuración del conector de Twitter.

11. En la **página Establecer filtros,** puede aplicar un filtro para importar inicialmente elementos que tienen una antigüedad determinada. Seleccione una antigüedad y, a continuación, haga clic **en Siguiente**.

12. En la **página Elegir ubicación** de almacenamiento, escriba la dirección de correo electrónico del buzón de Microsoft 365 al que se importarán los elementos de Twitter y, a continuación, haga clic en **Siguiente.**

13. Haga **clic en Siguiente** para revisar la configuración del conector y, a continuación, haga clic en Finalizar para completar la configuración del conector. 

14. En el Centro de cumplimiento, vaya a la  página **Conectores** de datos y haga clic en la pestaña Conectores para ver el progreso del proceso de importación.
