---
title: Cifrado de clave doble (DKE)
description: DKE le permite proteger datos altamente confidenciales mientras mantiene el control total de la clave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 02/28/2022
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 631df77a6f10c15dafcb78e58a715a029d32bb73
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66627555"
---
# <a name="double-key-encryption"></a>Cifrado de claves doble

> *Se aplica a: Cifrado de clave doble de Microsoft Purview, [Microsoft Purview](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/)*
>
> *Instrucciones para: [Azure Information Protection cliente de etiquetado unificado para Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*

> *Descripción del servicio para: [Microsoft Purview](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

El cifrado de doble clave (DKE) usa dos claves juntas para acceder al contenido protegido. Microsoft almacena una clave en Microsoft Azure y usted mantiene la otra clave. Mantenga el control total de una de las claves mediante el servicio de cifrado de claves dobles. Aplique la protección mediante Azure Information Protection cliente de etiquetado unificado al contenido altamente confidencial.

Double Key Encryption admite implementaciones tanto en la nube como en el entorno local. Estas implementaciones ayudan a garantizar que los datos cifrados permanezcan opacos dondequiera que almacene los datos protegidos.

Para obtener más información sobre las claves raíz de inquilino predeterminadas basadas en la nube, consulte [Planeamiento e implementación de la clave de inquilino de Azure Information Protection](/azure/information-protection/plan-implement-tenant-key).

## <a name="when-your-organization-should-adopt-dke"></a>Cuándo la organización debe adoptar DKE

El cifrado de doble clave está pensado para los datos más confidenciales que están sujetos a los requisitos de protección más estrictos. DKE no está pensado para todos los datos. En general, usará el cifrado de doble clave para proteger solo una pequeña parte de los datos generales. Debe realizar la debida diligencia en la identificación de los datos adecuados para cubrir con esta solución antes de realizar la implementación. En algunos casos, es posible que tenga que restringir el ámbito y usar otras soluciones para la mayoría de los datos, como Microsoft Purview Information Protection con claves administradas por Microsoft o BYOK. Estas soluciones son suficientes para documentos que no están sujetos a protecciones mejoradas y requisitos normativos. Además, estas soluciones le permiten usar los servicios de Office 365 más eficaces; los servicios que no se pueden usar con contenido cifrado DKE. Por ejemplo:

- Reglas de transporte que incluyen antimalware y correo no deseado que requieren visibilidad sobre los datos adjuntos
- Microsoft Delve
- eDiscovery
- Búsqueda e indexación de contenido
- Office Web Apps incluida la funcionalidad de coautoría

Las aplicaciones o servicios externos que no estén integrados con DKE a través del SDK de Microsoft Information Protection (MIP) no podrán realizar acciones en los datos cifrados.

El SDK de Microsoft Information Protection 1.7 y versiones posteriores admite el cifrado de doble clave. Las aplicaciones que se integran con nuestro SDK pueden razonar sobre estos datos con permisos e integraciones suficientes.

Use Microsoft Purview Information Protection funcionalidades (clasificación y etiquetado) para proteger la mayoría de los datos confidenciales y solo use DKE para los datos críticos. El cifrado de doble clave es relevante para los datos confidenciales en sectores altamente regulados, como los servicios financieros y la atención sanitaria.

Si las organizaciones tienen cualquiera de los siguientes requisitos, puede usar DKE para proteger el contenido:

- Quiere asegurarse de que *solo pueda* descifrar el contenido protegido en todas las circunstancias.
- No quiere que Microsoft tenga acceso a datos protegidos por sí mismo.
- Tiene requisitos normativos para contener claves dentro de un límite geográfico. Todas las claves que contiene para el cifrado y descifrado de datos se mantienen en el centro de datos.

## <a name="system-and-licensing-requirements-for-dke"></a>Requisitos del sistema y de licencias para DKE

**El cifrado de clave doble** incluye Microsoft 365 E5. Si no tiene una licencia de Microsoft 365 E5, puede registrarse para obtener una [prueba](https://aka.ms/M365E5ComplianceTrial). Para obtener más información sobre estas licencias, consulte [Guía de licencias de Microsoft 365 para el cumplimiento de & seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

**Azure Information Protection**. DKE funciona con etiquetas de confidencialidad y requiere azure Information Protection.

Las etiquetas de confidencialidad de DKE están disponibles para los usuarios finales mediante el botón de confidencialidad del cliente de etiquetado unificado de AIP en Aplicaciones de escritorio de Office. Instale estos requisitos previos en cada equipo cliente donde quiera proteger y consumir documentos protegidos.

**Aplicaciones de Microsoft Office para empresas** versión 2009 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.

**Azure Information Protection las** versiones 2.7.93.0 o posterior del cliente de etiquetado unificado. Descargue e instale el cliente de etiquetado unificado desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Entornos admitidos para almacenar y ver contenido protegido por DKE

**Aplicaciones admitidas**. [Aplicaciones Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clientes en Windows, incluidos Word, Excel y PowerPoint.

**Compatibilidad con contenido en línea**. Puede almacenar documentos y archivos protegidos con el cifrado de doble clave en línea en Microsoft SharePoint y OneDrive para la Empresa. Debe etiquetar y proteger documentos y archivos con DKE mediante aplicaciones admitidas antes de cargarlos en estas ubicaciones. Puede compartir contenido cifrado por correo electrónico, pero no puede ver documentos y archivos cifrados en línea. En su lugar, debe ver el contenido protegido mediante las aplicaciones de escritorio y los clientes admitidos en el equipo local.

## <a name="overview-of-deploying-dke"></a>Introducción a la implementación de DKE

Seguirá estos pasos generales para configurar DKE. Una vez completados estos pasos, los usuarios finales pueden proteger los datos altamente confidenciales con el cifrado de doble clave.

1. Implemente el servicio DKE como se describe en este artículo.

2. Cree una etiqueta con el cifrado de doble clave. En el portal de cumplimiento Microsoft Purview, vaya a **Protección de la información** y cree una nueva etiqueta con Cifrado de doble clave. Consulte [Restricción del acceso al contenido mediante etiquetas de confidencialidad para aplicar el cifrado](./encryption-sensitivity-labels.md).

3. Use etiquetas de cifrado de doble clave. Proteja los datos seleccionando la etiqueta Double Key Encrypted en la cinta de confidencialidad de Microsoft Office.

Hay varias maneras de completar algunos de los pasos para implementar el cifrado de doble clave. En este artículo se proporcionan instrucciones detalladas para que los administradores con menos experiencia implementen correctamente el servicio. Si se siente cómodo al hacerlo, puede elegir usar sus propios métodos.

## <a name="deploy-dke"></a>Implementación de DKE

En este artículo y en el vídeo de implementación se usa Azure como destino de implementación para el servicio DKE. Si va a realizar la implementación en otra ubicación, deberá proporcionar sus propios valores.


Seguirá estos pasos generales para configurar el cifrado de doble clave para su organización.

1. [Instalación de requisitos previos de software para el servicio DKE](#install-software-prerequisites-for-the-dke-service)
1. [Clonación del repositorio de GitHub de cifrado de clave doble](#clone-the-dke-github-repository)
1. [Modificación de la configuración de la aplicación](#modify-application-settings)
1. [Generación de claves de prueba](#generate-test-keys)
1. [Compile el proyecto.](#build-the-project)
1. [Implementación del servicio DKE y publicación del almacén de claves](#deploy-the-dke-service-and-publish-the-key-store)
1. [Validar la implementación](#validate-your-deployment)
1. [Registro del almacén de claves](#register-your-key-store)
1. [Creación de etiquetas de confidencialidad mediante DKE](#create-sensitivity-labels-using-dke)
1. [Habilitación de DKE en el cliente](#enable-dke-in-your-client)
1. [Migración de archivos protegidos de etiquetas HYOK a etiquetas DKE](#migrate-protected-files-from-hyok-labels-to-dke-labels)

Cuando haya terminado, puede cifrar documentos y archivos mediante DKE. Para obtener información, vea [Aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

### <a name="install-software-prerequisites-for-the-dke-service"></a>Instalación de requisitos previos de software para el servicio DKE

Instale estos requisitos previos en el equipo donde desea instalar el servicio DKE.

**SDK de .NET Core 3.1**. Descargue e instale el SDK desde [Descargar .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).

**Visual Studio Code**. Descargue Visual Studio Code de [https://code.visualstudio.com/](https://code.visualstudio.com). Una vez instalado, ejecute Visual Studio Code y seleccione **Ver** \> **extensiones**. Instale estas extensiones.

- C# para Visual Studio Code

- Administrador de paquetes NuGet

**Recursos de Git**. Descargue e instale una de las siguientes opciones.

- [Git](https://git-scm.com/downloads)

- [Escritorio de GitHub](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**Openssl** Debe tener [instalado OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) para [generar claves de prueba](#generate-test-keys) después de implementar DKE. Asegúrese de invocarla correctamente desde la ruta de acceso de las variables de entorno. Por ejemplo, consulte "Agregar el directorio de instalación a PATH" en [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) para obtener más información.

### <a name="clone-the-dke-github-repository"></a>Clonación del repositorio de GitHub DKE

Microsoft proporciona los archivos de origen DKE en un repositorio de GitHub. Clone el repositorio para compilar el proyecto localmente para el uso de su organización. El repositorio de GitHub DKE se encuentra en [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).

Las instrucciones siguientes están destinadas a los usuarios de git o Visual Studio Code inexpertos:

1. En el explorador, vaya a: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).

2. Hacia el lado derecho de la pantalla, seleccione **Código**. La versión de la interfaz de usuario podría mostrar un botón **Clonar o descargar** . A continuación, en la lista desplegable que aparece, seleccione el icono de copia para copiar la dirección URL en el Portapapeles.

    Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Clone el repositorio del servicio Double Key Encryption desde GitHub.](../media/dke-clone.png)

3. En Visual Studio Code, seleccione **Ver** \> **paleta de comandos** y seleccione **Git: Clonar**. Para ir a la opción de la lista, empiece a escribir `git: clone` para filtrar las entradas y, a continuación, selecciónela en la lista desplegable. Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Visual Studio Code opción GIT:Clone.](../media/dke-vscode-clone.png)

4. En el cuadro de texto, pegue la dirección URL que copió de Git y seleccione **Clonar desde GitHub**.

5. En el cuadro **de diálogo Seleccionar carpeta** que aparece, vaya a y seleccione una ubicación para almacenar el repositorio. En el símbolo del sistema, seleccione **Abrir**.

    El repositorio se abre en Visual Studio Code y muestra la rama de Git actual en la parte inferior izquierda. Por ejemplo, la rama debe ser **principal**. Por ejemplo:

   ![Captura de pantalla del repositorio DKE en Visual Studio Code que muestra la rama principal.](../media/dke-vscode-main-branch.jpg)

6. Si no está en la rama principal, deberá seleccionarla. En Visual Studio Code, seleccione la rama y elija **principal** en la lista de ramas que se muestra.

   > [!IMPORTANT]
   > Al seleccionar la rama principal, se garantiza que tiene los archivos correctos para compilar el proyecto. Si no elige la rama correcta, se producirá un error en la implementación.

Ahora tiene el repositorio de origen DKE configurado localmente. A continuación, [modifique la configuración de la aplicación](#modify-application-settings) para su organización.

### <a name="modify-application-settings"></a>Modificación de la configuración de la aplicación

Para implementar el servicio DKE, debe modificar los siguientes tipos de configuración de aplicación:

- [Configuración de acceso de clave](#key-access-settings)
- [Configuración de inquilinos y claves](#tenant-and-key-settings)

La configuración de la aplicación se modifica en el archivo appsettings.json. Este archivo se encuentra en el repositorio DoubleKeyEncryptionService que ha clonado localmente en DoubleKeyEncryptionService\src\customer-key-store. Por ejemplo, en Visual Studio Code, puede ir al archivo como se muestra en la siguiente imagen.

![Buscar el archivo appsettings.json para DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>Configuración de acceso de clave

Elija si desea usar el correo electrónico o la autorización de roles. DKE solo admite uno de estos métodos de autenticación a la vez.

- **Autorización por correo electrónico**. Permite que su organización autorice el acceso a las claves solo en función de las direcciones de correo electrónico.

- **Autorización de roles**. Permite que su organización autorice el acceso a claves basadas en grupos de Active Directory y requiere que el servicio web pueda consultar LDAP.

##### <a name="to-set-key-access-settings-for-dke-using-email-authorization"></a>Para establecer la configuración de acceso de clave para DKE mediante la autorización por correo electrónico

1. Abra el archivo **appsettings.json** y busque la `AuthorizedEmailAddress` configuración.

2. Agregue la dirección de correo electrónico o las direcciones que desea autorizar. Separe varias direcciones de correo electrónico con comillas dobles y comas. Por ejemplo:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Busque la `LDAPPath` configuración y quite el texto `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` entre comillas dobles. Deje las comillas dobles en su lugar. Cuando haya terminado, la configuración debería tener este aspecto.

   ```json
   "LDAPPath": ""
   ```

4. Busque la `AuthorizedRoles` configuración y elimine toda la línea.

Esta imagen muestra el archivo **appsettings.json** con el formato correcto para la autorización por correo electrónico.

   ![El archivo appsettings.json que muestra el método de autorización por correo electrónico.](../media/dke-email-accesssetting.png)

##### <a name="to-set-key-access-settings-for-dke-using-role-authorization"></a>Para establecer la configuración de acceso de clave para DKE mediante la autorización de roles

1. Abra el archivo **appsettings.json** y busque la `AuthorizedRoles` configuración.

2. Agregue los nombres de grupo de Active Directory que desea autorizar. Separe varios nombres de grupo con comillas dobles y comas. Por ejemplo:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Busque la `LDAPPath` configuración y agregue el dominio de Active Directory. Por ejemplo:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Busque la `AuthorizedEmailAddress` configuración y elimine toda la línea.

Esta imagen muestra el archivo **appsettings.json** con el formato correcto para la autorización de roles.

   ![archivo appsettings.json que muestra el método de autorización de roles.](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>Configuración de inquilinos y claves

La configuración de clave y el inquilino de DKE se encuentran en el archivo **appsettings.json** .

##### <a name="to-configure-tenant-and-key-settings-for-dke"></a>Para configurar los valores de inquilino y clave para DKE

1. Abra el archivo **appsettings.json** .

2. Busque la `ValidIssuers` configuración y reemplace por `<tenantid>` el identificador de inquilino. Para localizar el identificador de inquilino, vaya a la Azure Portal y vea las [propiedades del inquilino](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). Por ejemplo:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

> [!NOTE]
> Si desea habilitar el acceso B2B externo al almacén de claves, también deberá incluir estos inquilinos externos como parte de la lista de emisores válidos.

Busque .`JwtAudience` Reemplace por `<yourhostname>` el nombre de host de la máquina donde se ejecutará el servicio DKE. Por ejemplo: "https://dkeservice.contoso.com"

  > [!IMPORTANT]
  > El valor de `JwtAudience` debe coincidir *exactamente* con el nombre del host.  

- `TestKeys:Name`. Escriba un nombre para la clave. Por ejemplo: `TestKey1`
- `TestKeys:Id`. Cree un GUID y introdúzcalo como `TestKeys:ID` valor. Por ejemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. Puede usar un sitio como [generador de GUID en línea](https://guidgenerator.com/) para generar aleatoriamente un GUID.

Esta imagen muestra el formato correcto para la configuración de inquilinos y claves en **appsettings.json**. `LDAPPath` está configurado para la autorización de roles.

![Muestra la configuración de inquilino y clave correcta para DKE en el archivo appsettings.json.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>Generación de claves de prueba

Una vez que haya definido la configuración de la aplicación, estará listo para generar claves de prueba públicas y privadas.

Para generar claves:

1. En el menú Inicio de Windows, ejecute el símbolo del sistema de OpenSSL.

1. Cambie a la carpeta donde desea guardar las claves de prueba. Los archivos que cree completando los pasos de esta tarea se almacenan en la misma carpeta.

1. Genere la nueva clave de prueba.

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

1. Genere la clave privada.

   Si instaló OpenSSL versión 3 o posterior, ejecute el siguiente comando:
  
  ```console
  openssl rsa -in key.pem -out privkeynopass.pem -outform PEM -traditional
  ```
  
>  De lo contrario, ejecute el siguiente comando:
>  ```console
>  openssl rsa -in key.pem -out privkeynopass.pem -outform PEM
>  ```

1. Genere la clave pública.

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. En un editor de texto, abra **pubkeyonly.pem**. Copie todo el contenido del archivo **pubkeyonly.pem** , excepto la primera y la última línea, en la `PublicPem` sección del archivo **appsettings.json** .

1. En un editor de texto, abra **privkeynopass.pem**. Copie todo el contenido del archivo **privkeynopass.pem** , excepto la primera y la última línea, en la `PrivatePem` sección del archivo **appsettings.json** .

1. Quite todos los espacios en blanco y las líneas nuevas en las `PublicPem` secciones y `PrivatePem` .

    > [!IMPORTANT]
    > Al copiar este contenido, no elimine ninguno de los datos PEM.

1. En Visual Studio Code, vaya al archivo **Startup.cs**. Este archivo se encuentra en el repositorio DoubleKeyEncryptionService que clonó localmente en DoubleKeyEncryptionService\src\customer-key-store\.

1. Busque las siguientes líneas de código:

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

1. Reemplace estas líneas por el texto siguiente:

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    Los resultados finales deben tener un aspecto similar al siguiente.

    ![archivo startup.cs para la versión preliminar pública.](../media/dke-startupcs-usetestkeys.png)

Ahora está listo para [compilar el proyecto DKE](#build-the-project).

### <a name="build-the-project"></a>Compile el proyecto.

Use las siguientes instrucciones para compilar el proyecto DKE localmente:

1. En Visual Studio Code, en el repositorio de servicios DKE, seleccione **Ver** \> **paleta de comandos** y, a continuación, escriba **build** en el símbolo del sistema.

2. En la lista, elija **Tareas: Ejecutar tarea de compilación**.

   Si no se encuentra ninguna tarea de compilación, seleccione **Configurar tarea de compilación** y cree una para .NET Core como se indica a continuación.

   ![Configurar la tarea de compilación que falta para .NET.](../media/dke-configurebuildtask.png)

   1. Elija **Create tasks.json from template (Crear tasks.json a partir de la plantilla**).

      ![Cree el archivo tasks.json a partir de la plantilla para DKE.](../media/dke-createtasksjsonfromtemplate.png)

   2. En la lista de tipos de plantilla, seleccione **.NET Core**.

      ![Seleccione la plantilla correcta para DKE.](../media/dke-tasksjsontemplate.png)

   3. En la sección de compilación, busque la ruta de acceso al archivo **customerkeystore.csproj** . Si no está allí, agregue la línea siguiente:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. Vuelva a ejecutar la compilación.

3. Compruebe que no haya errores rojos en la ventana de salida.

   Si hay errores rojos, compruebe la salida de la consola. Asegúrese de que ha completado todos los pasos anteriores correctamente y que las versiones de compilación correctas están presentes.


La configuración ya está completa. Antes de publicar el almacén de claves, en appsettings.json, para la configuración jwtAudience, asegúrese de que el valor del nombre de host coincida exactamente con el nombre de host App Service. 

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>Implementación del servicio DKE y publicación del almacén de claves

Para las implementaciones de producción, implemente el servicio en una nube de [terceros o publíquelo en un sistema local](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1).

Es posible que prefiera otros métodos para implementar las claves. Seleccione el método que mejor funcione para su organización.

En el caso de las implementaciones piloto, puede implementar en Azure y empezar a trabajar de inmediato.

#### <a name="to-create-an-azure-web-app-instance-to-host-your-dke-deployment"></a>Para crear una instancia de Azure Web App para hospedar la implementación de DKE

Para publicar el almacén de claves, creará una instancia de Azure App Service para hospedar la implementación de DKE. A continuación, publicará las claves generadas en Azure.

1. En el explorador, inicie sesión en microsoft [Azure Portal](https://ms.portal.azure.com) y vaya a **Agregar** de **App Services** > .

2. Seleccione la suscripción y el grupo de recursos y defina los detalles de la instancia.

   - Escriba el nombre de host del equipo donde desea instalar el servicio DKE. Asegúrese de que es el mismo nombre que el definido para la configuración jwtAudience en el archivo [**appsettings.json**](#tenant-and-key-settings) . El valor que se proporciona para el nombre también es WebAppInstanceName.

   - En **Publicar**, seleccione **código** y, en **Pila en tiempo de ejecución**, seleccione **.NET Core 3.1**.

   Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Agregue el App Service.](../media/dke-azure-add-app-service.png)

3. En la parte inferior de la página, seleccione **Revisar y crear** y, a continuación, seleccione **Agregar**.

4. Realice una de las siguientes acciones para publicar las claves generadas:

   - [Publicación a través de ZipDeployUI](#publish-via-zipdeployui)
   - [Publicación a través de FTP](#publish-via-ftp)
   - [Publicación a través de Visual Studio 2019 o posterior](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>Publicación a través de ZipDeployUI

1. Ve a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

   Por ejemplo: `https://dkeservice.contoso.scm.azurewebsites.net/ZipDeployUI`

2. En el código base del almacén de claves, vaya a la carpeta **customer-key-store\src\customer-key-store** y compruebe que esta carpeta contiene el archivo **customerkeystore.csproj** .

3. Ejecución: **dotnet publish**

   La ventana de salida muestra el directorio donde se implementó la publicación.

   Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. Envíe todos los archivos del directorio de publicación a un archivo .zip. Al crear el archivo .zip, asegúrese de que todos los archivos del directorio están en el nivel raíz del archivo .zip.

5. Arrastre y coloque el archivo .zip que creó en el sitio ZipDeployUI que abrió anteriormente. Por ejemplo: `https://dkeservice.scm.azurewebsites.net/ZipDeployUI`

DKE está implementado y puede ir a las claves de prueba que ha creado. Continúe con [La validación de la implementación](#validate-your-deployment) a continuación.

#### <a name="publish-via-ftp"></a>Publicación a través de FTP

1. Conéctese al App Service que creó [anteriormente](#deploy-the-dke-service-and-publish-the-key-store).

   En el explorador, vaya a: **Azure Portal** >  **App Service** >  Panel **FTP** >  de **implementación manual** **del Centro** >  de implementación > **.**

2. Copie las cadenas de conexión mostradas en un archivo local. Usará estas cadenas para conectarse a la App Service web y cargar archivos a través de FTP.

   Por ejemplo:

   ![Copie las cadenas de conexión desde el panel FTP.](../media/dke-ftp-dashboard.png)

3. En el código base del almacenamiento de claves, vaya al **directorio customer-key-store\src\customer-key-store**.

4. Compruebe que este directorio contiene el archivo **customerkeystore.csproj** .

5. Ejecución: **dotnet publish**

   La salida contiene el directorio donde se implementó la publicación.

   Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. Envíe todos los archivos del directorio de publicación a un archivo ZIP. Al crear el archivo .zip, asegúrese de que todos los archivos del directorio están en el nivel raíz del archivo .zip.

7. Desde el cliente FTP, use la información de conexión que copió para conectarse a la App Service. Cargue el archivo .zip que creó en el paso anterior en el directorio raíz de la aplicación web.

DKE está implementado y puede ir a las claves de prueba que ha creado. A continuación, [valide la implementación](#validate-your-deployment).

### <a name="validate-your-deployment"></a>Validar la implementación

Después de implementar DKE con uno de los métodos descritos anteriormente, valide la implementación y la configuración del almacén de claves.

Ejecutar:

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

Por ejemplo:

```powershell
key_store_tester.ps1 https://dkeservice.contoso.com/TestKey1
```

Asegúrese de que no aparezca ningún error en la salida. Cuando esté listo, [registre el almacén de claves](#register-your-key-store).

El nombre de la clave distingue mayúsculas de minúsculas. Escriba el nombre de clave tal como aparece en el archivo appsettings.json.

## <a name="register-your-key-store"></a>Registro del almacén de claves

Los pasos siguientes le permiten registrar el servicio DKE. El registro del servicio DKE es el último paso para implementar DKE antes de empezar a crear etiquetas.

Para registrar el servicio DKE:

1. En el explorador, abra microsoft [Azure Portal](https://ms.portal.azure.com/) y vaya a **Todos los registros** de aplicaciones **de identidad** \> **de servicios**\>.

2. Seleccione **Nuevo registro** y escriba un nombre significativo.

3. Seleccione un tipo de cuenta en las opciones que se muestran.

    Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Nuevo registro de aplicaciones.](../media/dke-app-registration.png)

4. En la parte inferior de la página, seleccione **Registrar** para crear el nuevo registro de aplicaciones.

5. En el nuevo registro de aplicaciones, en el panel izquierdo, en **Administrar**, seleccione **Autenticación**.

6. Seleccione **Agregar una plataforma**.

7. En el menú emergente **Configurar plataformas** , seleccione **Web**.

8. En **URI de redireccionamiento**, escriba el URI del servicio de cifrado de doble clave. Escriba la dirección URL de App Service, incluidos el nombre de host y el dominio.

   Por ejemplo: `https://mydkeservicetest.com`

   - La dirección URL que escriba debe coincidir con el nombre de host donde se implementa el servicio DKE.
   - El dominio debe ser un [dominio comprobado](/azure/active-directory/develop/reference-breaking-changes#appid-uri-in-single-tenant-applications-will-require-use-of-default-scheme-or-verified-domains).
    - En todos los casos, el esquema debe ser **https**.

   Asegúrese de que el nombre de host coincide exactamente con el nombre de host de App Service.

9. En **Concesión implícita**, active la casilla **Tokens de identificador** .

10. Seleccione **Guardar** para guardar los cambios.

11. En el panel izquierdo, seleccione **Exponer una API**, junto a URI del identificador de aplicación, escriba la dirección URL de App Service, incluidos el nombre de host y el dominio, y, a continuación, seleccione **Establecer**.

12. Todavía en la página **Exponer una API** , en el área **Ámbitos definidos por esta API** , seleccione **Agregar un ámbito**. En el nuevo ámbito:

    1. Defina el nombre del ámbito como **user_impersonation**.

    2. Seleccione los administradores y los usuarios que pueden dar su consentimiento.

    3. Defina los valores restantes necesarios.

    4. Seleccione **Agregar ámbito**.

    5. Seleccione **Guardar** en la parte superior para guardar los cambios.

13. Todavía en la página **Exponer una API** , en el área **Aplicaciones cliente autorizadas** , seleccione **Agregar una aplicación cliente**.

    En la nueva aplicación cliente:

    1. Defina el identificador de cliente como `d3590ed6-52b3-4102-aeff-aad2292ab01c`. Este valor es el identificador de cliente de Microsoft Office y permite a Office obtener un token de acceso para el almacén de claves.

    2. En **Ámbitos autorizados**, seleccione el ámbito **de user_impersonation** .

    3. Seleccione **Agregar aplicación**.

    4. Seleccione **Guardar** en la parte superior para guardar los cambios.

    5. Repita estos pasos, pero esta vez, defina el identificador de cliente como `c00e9d32-3c8d-4a7d-832b-029040e7db99`. Este valor es el identificador de cliente de etiquetado unificado de Azure Information Protection.

El servicio DKE ya está registrado. Para continuar, [cree etiquetas mediante DKE](#create-sensitivity-labels-using-dke).

## <a name="create-sensitivity-labels-using-dke"></a>Creación de etiquetas de confidencialidad mediante DKE

En el portal de cumplimiento Microsoft Purview, cree una nueva etiqueta de confidencialidad y aplique el cifrado como lo haría en caso contrario. Seleccione **Usar cifrado de doble clave** y escriba la dirección URL del punto de conexión de la clave. Debe incluir el nombre de clave que ha proporcionado en la sección "TestKeys" del archivo appsettings.json en la dirección URL.

Por ejemplo: `https://testingdke1.azurewebsites.net/KEYNAME`

> [!div class="mx-imgBorder"]
> ![Seleccione Usar cifrado de doble clave en el portal de cumplimiento Microsoft Purview.](../media/dke-use-dke.png)

Las etiquetas DKE que agregue comenzarán a aparecer para los usuarios en las versiones más recientes de Aplicaciones Microsoft 365 para empresas.

> [!NOTE]
> Los clientes pueden tardar hasta 24 horas en actualizarse con las nuevas etiquetas.

### <a name="enable-dke-in-your-client"></a>Habilitación de DKE en el cliente

Si es office insider, DKE está habilitado para usted. De lo contrario, habilite DKE para el cliente agregando las siguientes claves del Registro:

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>Migración de archivos protegidos de etiquetas HYOK a etiquetas DKE

Si lo desea, una vez que haya terminado de configurar DKE, puede migrar el contenido que ha protegido mediante etiquetas HYOK a etiquetas DKE. Para migrar, usará el analizador de AIP. Para empezar a usar el analizador, consulte [¿Qué es el analizador de etiquetado unificado de Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)

Si no migra contenido, el contenido protegido de HYOK no se verá afectado.

## <a name="other-deployment-options"></a>Otras opciones de implementación

Nos damos cuenta de que, para algunos clientes de sectores altamente regulados, esta implementación de referencia estándar mediante claves basadas en software puede no ser suficiente para satisfacer sus obligaciones y necesidades de cumplimiento mejoradas. Nos hemos asociado con proveedores de módulos de seguridad de hardware (HSM) de terceros para admitir opciones mejoradas de administración de claves en el servicio DKE, entre las que se incluyen:

- [Entrust](https://www.entrust.com/digital-security/hsm/services/packaged-services/double-key-encryption-integration#:~:text=Entrust%20Double%20Key%20Encryption%20for%20Microsoft%20AIP%2C%20offered,trust%20for%20the%20protection%20of%20sensitive%20cryptographic%20keys.)

- [Thales](https://cpl.thalesgroup.com/cloud-security/encryption/double-key-encryption)

Póngase en contacto directamente con estos proveedores para obtener más información e instrucciones sobre sus soluciones de DKE HSM en el mercado.
