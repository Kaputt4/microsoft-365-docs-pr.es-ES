---
title: Cifrado de clave doble (DKE)
description: DKE le permite proteger datos altamente confidenciales mientras mantiene el control total de la clave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 0ee4269c61c4c9e2a9341c3b700db9f65e003114
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786463"
---
# <a name="double-key-encryption-for-microsoft-365"></a>Cifrado de clave doble para Microsoft 365

> *Se aplica a: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), Azure [Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *Instrucciones para: Cliente de etiquetado [unificado de Azure Information Protection para Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *Descripción del servicio para: [Microsoft 365 cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Double Key Encryption (DKE) usa dos claves juntas para obtener acceso al contenido protegido. Microsoft almacena una clave en Microsoft Azure y mantiene la otra clave. Se mantiene el control total de una de las claves mediante el servicio de cifrado de clave doble. Puede aplicar protección mediante el cliente de etiquetado unificado de Azure Information Protection a su contenido altamente confidencial.

Double Key Encryption admite implementaciones locales y en la nube. Estas implementaciones ayudan a garantizar que los datos cifrados permanecen opacos siempre que almacene los datos protegidos.

Para obtener más información acerca de las claves raíz de inquilino predeterminadas basadas en la nube, vea [Planning and implementing your Azure Information Protection tenant key](/azure/information-protection/plan-implement-tenant-key).

## <a name="when-your-organization-should-adopt-dke"></a>Cuando su organización debe adoptar DKE

El cifrado de clave doble está pensado para los datos más confidenciales que están sujetos a los requisitos de protección más estrictos. DKE no está pensado para todos los datos. En general, usarás cifrado de clave doble para proteger solo una pequeña parte de los datos generales. Debe realizar la debida diligencia en la identificación de los datos adecuados para cubrir con esta solución antes de implementar. En algunos casos, es posible que deba restringir el ámbito y usar otras soluciones para la mayoría de los datos, como Microsoft Information Protection con claves administradas por Microsoft o BYOK. Estas soluciones son suficientes para documentos que no están sujetos a protecciones mejoradas y requisitos normativos. Además, estas soluciones le permiten usar los servicios de Office 365 más eficaces; servicios que no puede usar con contenido cifrado DKE. Por ejemplo:

- Reglas de transporte como antimalware y correo no deseado que requieren visibilidad en los datos adjuntos
- Microsoft Delve
- eDiscovery
- Búsqueda de contenido e indización
- Office Aplicaciones web, incluida la funcionalidad de coautoría

Las aplicaciones o servicios externos que no estén integrados con DKE a través del SDK de MIP no podrán realizar acciones en los datos cifrados.

El Microsoft Information Protection SDK 1.7+ admite el cifrado de clave doble; las aplicaciones que se integran con nuestro SDK podrán razonar estos datos con suficientes permisos e integraciones en su lugar.

Se recomienda que las organizaciones usen las capacidades de Protección de información de Microsoft (clasificación y etiquetado) para proteger la mayoría de sus datos confidenciales y solo usan DKE para sus datos de misión crítica. El cifrado de doble clave es relevante para los datos confidenciales en sectores altamente regulados como los servicios financieros y la atención sanitaria.

Si sus organizaciones tienen cualquiera de los siguientes requisitos, puede usar DKE para ayudar a proteger el contenido:

- Desea asegurarse de que *solo puede* descifrar el contenido protegido, en todas las circunstancias.
- No desea que Microsoft tenga acceso a datos protegidos por sí mismo.
- Tiene requisitos normativos para contener claves dentro de un límite geográfico. Todas las claves que contiene para el cifrado y descifrado de datos se mantienen en el centro de datos.

## <a name="system-and-licensing-requirements-for-dke"></a>Requisitos de sistema y licencias para DKE

**Double Key Encryption for Microsoft 365** viene con Microsoft 365 E5. Si no tiene una licencia de Microsoft 365 E5, puede registrarse para obtener una [versión de prueba](https://aka.ms/M365E5ComplianceTrial). Para obtener más información acerca de estas licencias, vea Microsoft 365 guía de licencias para [seguridad y & cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

**Azure Information Protection**. DKE funciona con etiquetas de confidencialidad y requiere Azure Information Protection.

Las etiquetas de confidencialidad DKE están disponibles para los usuarios finales a través de la cinta de confidencialidad Office aplicaciones de escritorio. Instale estos requisitos previos en cada equipo cliente donde desee proteger y consumir documentos protegidos.

**Microsoft Office aplicaciones para empresas** versión 2009 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.

**Azure Information Protection Unified Labeling Client versions** 2.7.93.0 o posterior. Descargue e instale el cliente de etiquetado unificado desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Entornos compatibles para almacenar y ver contenido protegido por DKE

**Aplicaciones admitidas**. [Aplicaciones Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clientes en Windows, incluidos Word, Excel y PowerPoint.

**Compatibilidad con contenido en línea**. Puede almacenar documentos y archivos protegidos con cifrado de clave doble en línea en Microsoft SharePoint y OneDrive para la Empresa. Antes de cargar en estas ubicaciones, debe etiquetar y proteger documentos y archivos con DKE. Puede compartir contenido cifrado por correo electrónico, pero no puede ver documentos y archivos cifrados en línea. En su lugar, debe ver el contenido protegido con las aplicaciones de escritorio y los clientes admitidos en el equipo local.

## <a name="overview-of-deploying-dke"></a>Información general sobre la implementación de DKE

Seguirá estos pasos generales para configurar DKE. Una vez completados estos pasos, los usuarios finales podrán proteger los datos altamente confidenciales con cifrado de clave doble.

1. Implemente el servicio DKE tal como se describe en este artículo.

2. Cree una etiqueta con cifrado de clave doble. Vaya a Protección de la información en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">la Centro de cumplimiento de Microsoft 365</a> y cree una nueva etiqueta con cifrado de clave doble. Consulte [Restringir el acceso al contenido mediante etiquetas de confidencialidad para aplicar cifrado.](./encryption-sensitivity-labels.md)

3. Use etiquetas de cifrado de clave doble. Proteja los datos seleccionando la etiqueta Double Key Encrypted de la cinta de opciones De confidencialidad en Microsoft Office.

Hay varias maneras de completar algunos de los pasos para implementar el cifrado de clave doble. En este artículo se proporcionan instrucciones detalladas para que los administradores con menos experiencia implemente correctamente el servicio. Si se siente cómodo al hacerlo, puede elegir usar sus propios métodos.

## <a name="deploy-dke"></a>Implementar DKE

Este artículo y el vídeo de implementación usan Azure como destino de implementación para el servicio DKE. Si está implementando en otra ubicación, deberá proporcionar sus propios valores.

Vea el [vídeo de implementación de cifrado de clave](https://youtu.be/vDWfHN_kygg) doble para ver una introducción paso a paso de los conceptos de este artículo. El vídeo tarda unos 18 minutos en completarse.

Seguirá estos pasos generales para configurar el cifrado de clave doble para su organización.

1. [Instalar requisitos previos de software para el servicio DKE](#install-software-prerequisites-for-the-dke-service)
1. [Clonar el repositorio de GitHub clave doble](#clone-the-dke-github-repository)
1. [Modificar la configuración de la aplicación](#modify-application-settings)
1. [Generar claves de prueba](#generate-test-keys)
1. [Compile el proyecto.](#build-the-project)
1. [Implementar el servicio DKE y publicar el almacén de claves](#deploy-the-dke-service-and-publish-the-key-store)
1. [Validar la implementación](#validate-your-deployment)
1. [Registrar el almacén de claves](#register-your-key-store)
1. [Crear etiquetas de confidencialidad con DKE](#create-sensitivity-labels-using-dke)
1. [Habilitar DKE en el cliente](#enable-dke-in-your-client)
1. [Migrar archivos protegidos de etiquetas HYOK a etiquetas DKE](#migrate-protected-files-from-hyok-labels-to-dke-labels)

Cuando haya terminado, puede cifrar documentos y archivos mediante DKE. Para obtener información, vea [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

### <a name="install-software-prerequisites-for-the-dke-service"></a>Instalar requisitos previos de software para el servicio DKE

Instale estos requisitos previos en el equipo donde desea instalar el servicio DKE.

**SDK de .NET Core 3.1**. Descargue e instale el SDK desde [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).

**Visual Studio Code**. Descargue Visual Studio Code desde [https://code.visualstudio.com/](https://code.visualstudio.com) . Una vez instalado, ejecute Visual Studio Code  y seleccione \> **Ver extensiones**. Instale estas extensiones.

- C# para Visual Studio Code

- NuGet Administrador de paquetes

**Recursos de Git**. Descargue e instale una de las siguientes opciones.

- [Git](https://git-scm.com/downloads)

- [GitHub Escritorio](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** Debe tener [OpenSSL instalado](https://slproweb.com/products/Win32OpenSSL.html) para generar [claves de prueba](#generate-test-keys) después de implementar DKE. Asegúrese de invocarla correctamente desde la ruta de acceso de variables de entorno. Por ejemplo, vea "Agregar el directorio de instalación a PATH" en [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) para obtener más información.

### <a name="clone-the-dke-github-repository"></a>Clonar el repositorio de GitHub DKE

Microsoft proporciona los archivos de origen DKE en un GitHub de datos. Clone el repositorio para crear el proyecto localmente para el uso de su organización. El repositorio GitHub DKE se encuentra en [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

Las siguientes instrucciones están destinadas a usuarios de git o usuarios Visual Studio Code experiencia:

1. En el explorador, vaya a: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

2. Hacia el lado derecho de la pantalla, seleccione **Código**. La versión de la interfaz de usuario puede mostrar un **botón Clonar o** descargar. A continuación, en el desplegable que aparece, seleccione el icono de copia para copiar la dirección URL en el Portapapeles.

    Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Clone el repositorio del servicio de cifrado de clave doble GitHub.](../media/dke-clone.png)

3. En Visual Studio Code, seleccione **Ver paleta** \> **de comandos** y seleccione **Git: Clonar**. Para ir a la opción de la lista, empiece a escribir para filtrar las entradas y, a continuación, `git: clone` selecciónelo en la lista desplegable. Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Visual Studio Code Opción GIT:Clone.](../media/dke-vscode-clone.png)

4. En el cuadro de texto, pegue la dirección URL que copió de Git y seleccione **Clonar de GitHub**.

5. En el **cuadro de diálogo** Seleccionar carpeta que aparece, busque y seleccione una ubicación para almacenar el repositorio. En el símbolo del sistema, seleccione **Abrir**.

    El repositorio se abre en Visual Studio Code y muestra la rama git actual en la parte inferior izquierda. Por ejemplo, la rama debe ser **principal**. Por ejemplo:

   ![Captura de pantalla del repositorio de DKE en Visual Studio Code muestra la rama principal.](../media/dke-vscode-main-branch.jpg)

6. Si no está en la rama principal, tendrá que seleccionarla. En Visual Studio Code, seleccione la rama y elija **main** en la lista de ramas que se muestra.

   > [!IMPORTANT]
   > La selección de la rama principal garantiza que tenga los archivos correctos para compilar el proyecto. Si no elige la rama correcta, se producirá un error en la implementación.

Ahora tiene el repositorio de origen de DKE configurado localmente. A continuación, [modifique la configuración de la aplicación](#modify-application-settings) para su organización.

### <a name="modify-application-settings"></a>Modificar la configuración de la aplicación

Para implementar el servicio DKE, debe modificar los siguientes tipos de configuración de la aplicación:

- [Configuración de acceso clave](#key-access-settings)
- [Configuración de inquilino y clave](#tenant-and-key-settings)

Puede modificar la configuración de la aplicación en el archivo appsettings.json. Este archivo se encuentra en el repositorio DoubleKeyEncryptionService clonado localmente en DoubleKeyEncryptionService\src\customer-key-store. Por ejemplo, en Visual Studio Code, puede examinar el archivo como se muestra en la siguiente imagen.

![Localizar el archivo appsettings.json para DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>Configuración de acceso clave

Elija si desea usar la autorización de correo electrónico o de roles. DKE solo admite uno de estos métodos de autenticación a la vez.

- **Autorización de correo** electrónico . Permite que su organización autorice el acceso a las claves solo en función de las direcciones de correo electrónico.

- **Autorización de roles**. Permite que su organización autorice el acceso a claves basadas en grupos de Active Directory y requiere que el servicio web pueda consultar LDAP.

##### <a name="to-set-key-access-settings-for-dke-using-email-authorization"></a>Para establecer la configuración de acceso de clave para DKE mediante autorización de correo electrónico

1. Abra el **archivo appsettings.json** y busque la `AuthorizedEmailAddress` configuración.

2. Agregue la dirección de correo electrónico o las direcciones que desee autorizar. Separe varias direcciones de correo electrónico con comillas dobles y comas. Por ejemplo:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Busque la `LDAPPath` configuración y quite el texto entre las `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` comillas dobles. Deje las comillas dobles en su lugar. Cuando haya terminado, la configuración debería tener este aspecto.

   ```json
   "LDAPPath": ""
   ```

4. Busque la `AuthorizedRoles` configuración y elimine toda la línea.

Esta imagen muestra el **archivo appsettings.json** con el formato correcto para la autorización de correo electrónico.

   ![El archivo appsettings.json que muestra el método de autorización de correo electrónico.](../media/dke-email-accesssetting.png)

##### <a name="to-set-key-access-settings-for-dke-using-role-authorization"></a>Para establecer la configuración de acceso de clave para DKE mediante la autorización de roles

1. Abra el **archivo appsettings.json** y busque la `AuthorizedRoles` configuración.

2. Agregue los nombres de grupo de Active Directory que desee autorizar. Separe varios nombres de grupo con comillas dobles y comas. Por ejemplo:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Busque la `LDAPPath` configuración y agregue el dominio de Active Directory. Por ejemplo:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Busque la `AuthorizedEmailAddress` configuración y elimine toda la línea.

Esta imagen muestra el **archivo appsettings.json** con el formato correcto para la autorización de roles.

   ![archivo appsettings.json que muestra el método de autorización de roles.](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>Configuración de inquilino y clave

La configuración de inquilino y clave de DKE se encuentra en el **archivo appsettings.json.**

##### <a name="to-configure-tenant-and-key-settings-for-dke"></a>Para configurar la configuración de inquilino y clave para DKE

1. Abra el **archivo appsettings.json.**

2. Busque la `ValidIssuers` configuración y reemplace por su identificador de `<tenantid>` inquilino. Para localizar el identificador de inquilino, vaya a Azure Portal y vea las propiedades [del espacio empresarial.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) Por ejemplo:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

> [!NOTE]
> Si desea habilitar el acceso B2B externo al almacén de claves, también tendrá que incluir estos inquilinos externos como parte de la lista de emisores válidos.

Busque `JwtAudience` el archivo . Reemplace por el nombre de host de la máquina donde se ejecutará `<yourhostname>` el servicio DKE. Por ejemplo:

  > [!IMPORTANT]
  > El valor de `JwtAudience` debe coincidir exactamente con el nombre del host . Puede usar **localhost:5001** durante la depuración. Sin embargo, cuando haya terminado de depurar, asegúrese de actualizar este valor al nombre de host del servidor.

- `TestKeys:Name`. Escriba un nombre para la clave. Por ejemplo: `TestKey1`
- `TestKeys:Id`. Cree un GUID y introdúzcalo como `TestKeys:ID` valor. Por ejemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. Puede usar un sitio como [Generador de GUID en](https://guidgenerator.com/) línea para generar aleatoriamente un GUID.

Esta imagen muestra el formato correcto para la configuración de inquilino y claves **en appsettings.json**. `LDAPPath` se configura para la autorización de roles.

![Muestra la configuración de inquilino y clave correcta para DKE en el archivo appsettings.json.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>Generar claves de prueba

Una vez que haya definido la configuración de la aplicación, estará listo para generar claves de prueba públicas y privadas.

Para generar claves:

1. En el Windows menú Inicio, ejecute el símbolo del sistema openSSL.

2. Cambie a la carpeta donde desea guardar las claves de prueba. Los archivos que cree completando los pasos de esta tarea se almacenan en la misma carpeta.

3. Genere la nueva clave de prueba.

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. Genere la clave privada.

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. Generar la clave pública.

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. En un editor de texto, abra **pubkeyonly.pem**. Copie todo el contenido del archivo **pubkeyonly.pem,** excepto la primera y la última línea, en la sección `PublicPem` del archivo **appsettings.json.**

7. En un editor de texto, abra **privkeynopass.pem**. Copie todo el contenido del archivo **privkeynopass.pem,** excepto la primera y la última línea, en la sección `PrivatePem` del archivo **appsettings.json.**

8. Quite todos los espacios en blanco y las líneas nuevas de las `PublicPem` `PrivatePem` secciones y.

    > [!IMPORTANT]
    > Al copiar este contenido, no elimine ninguno de los datos PEM.

9. En Visual Studio Code, vaya al **archivo Startup.cs.** Este archivo se encuentra en el repositorio DoubleKeyEncryptionService clonado localmente en DoubleKeyEncryptionService\src\customer-key-store\.

10. Busque las líneas siguientes:

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. Reemplace estas líneas por el texto siguiente:

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    Los resultados finales deben ser similares a los siguientes.

    ![archivo startup.cs para la vista previa pública.](../media/dke-startupcs-usetestkeys.png)

Ahora ya está listo para [crear el proyecto DKE](#build-the-project).

### <a name="build-the-project"></a>Compile el proyecto.

Use las siguientes instrucciones para crear el proyecto DKE localmente:

1. En Visual Studio Code, en el repositorio de servicios DKE, seleccione **Ver** paleta de comandos y, a continuación, \>  escriba **compilación** en el símbolo del sistema.

2. En la lista, elija **Tareas: Ejecutar tarea de compilación**.

   Si no se encuentran tareas de compilación, seleccione **Configurar tarea de compilación** y cree una para .NET core de la siguiente manera.

   ![Configurar la tarea de compilación que falta para .NET.](../media/dke-configurebuildtask.png)

   1. Elija **Create tasks.json from template**.

      ![Cree un archivo tasks.json a partir de la plantilla para DKE.](../media/dke-createtasksjsonfromtemplate.png)

   2. En la lista de tipos de plantilla, seleccione **.NET Core**.

      ![Seleccione la plantilla correcta para DKE.](../media/dke-tasksjsontemplate.png)

   3. En la sección compilación, busque la ruta de acceso al **archivo customerkeystore.csproj.** Si no está ahí, agregue la siguiente línea:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. Vuelva a ejecutar la compilación.

3. Compruebe que no hay errores rojos en la ventana de salida.

   Si hay errores rojos, compruebe el resultado de la consola. Asegúrese de que ha completado todos los pasos anteriores correctamente y de que las versiones de compilación correctas están presentes.

4. Seleccione **Ejecutar** \> **la depuración de inicio** para depurar el proceso. Si se le pide que seleccione un entorno, seleccione **.NET core**.

   El depurador de .NET core normalmente se inicia en `https://localhost:5001` . Para ver la clave de prueba, vaya a y anexe una barra `https://localhost:5001` diagonal (/) y el nombre de la clave. Por ejemplo:

   ```https
   https://localhost:5001/TestKey1
   ```

   La clave debe mostrarse en formato JSON.

La configuración ya está completa. Antes de publicar el almacén de claves, en appsettings.json, para la configuración JwtAudience, asegúrese de que el valor del nombre de host coincide exactamente con el nombre de host de App Service. Es posible que lo haya cambiado a localhost para solucionar problemas de la compilación.

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>Implementar el servicio DKE y publicar el almacén de claves

Para implementaciones de producción, implemente el servicio en una nube de terceros o [publique en un sistema local.](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)

Es posible que prefiera otros métodos para implementar las claves. Seleccione el método que mejor funciona para su organización.

Para las implementaciones piloto, puede implementar en Azure y empezar inmediatamente.

#### <a name="to-create-an-azure-web-app-instance-to-host-your-dke-deployment"></a>Para crear una instancia de Azure Web App para hospedar la implementación de DKE

Para publicar el almacén de claves, creará una instancia de Azure App Service para hospedar la implementación de DKE. A continuación, publicará las claves generadas en Azure.

1. En el explorador, inicie sesión en el [portal Microsoft Azure y](https://ms.portal.azure.com)vaya a App **Services**  >  **Add**.

2. Seleccione la suscripción y el grupo de recursos y defina los detalles de la instancia.

   - Escriba el nombre de host del equipo donde desea instalar el servicio DKE. Asegúrese de que es el mismo nombre que el definido para la configuración JwtAudience en el [**archivo appsettings.json.**](#tenant-and-key-settings) El valor que proporciona para el nombre también es WebAppInstanceName.

   - En **Publish**, select **code** y for **Runtime stack**, select **.NET Core 3.1**.

   Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Agregue el Servicio de aplicaciones.](../media/dke-azure-add-app-service.png)

3. En la parte inferior de la página, seleccione **Revisar + crear** y, a continuación, seleccione **Agregar**.

4. Realice una de las siguientes acciones para publicar las claves generadas:

   - [Publicar a través de ZipDeployUI](#publish-via-zipdeployui)
   - [Publicar a través de FTP](#publish-via-ftp)
   - [Publicar mediante Visual Studio 2019 o posterior](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>Publicar a través de ZipDeployUI

1. Ve a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

   Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. En la base de código del almacén de claves, vaya a la carpeta **customer-key-store\src\customer-key-store** y compruebe que esta carpeta contiene el archivo **customerkeystore.csproj.**

3. Ejecutar: **publicación de dotnet**

   La ventana de salida muestra el directorio donde se implementó la publicación.

   Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. Envíe todos los archivos del directorio de publicación a .zip archivo. Al crear el .zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del .zip archivo.

5. Arrastre y coloque el .zip archivo que cree en el sitio ZipDeployUI que abrió anteriormente. Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE se implementa y puede examinar las claves de prueba que ha creado. Continúe [validando la implementación que se muestra](#validate-your-deployment) a continuación.

#### <a name="publish-via-ftp"></a>Publicar a través de FTP

1. Conectar al Servicio de aplicaciones que creó [anteriormente](#deploy-the-dke-service-and-publish-the-key-store).

   En el explorador, vaya a: Panel FTP de implementación manual del Centro de implementación de **Azure Portal** App  >  **Service**  >    >    >    >  .

2. Copie las cadenas de conexión que se muestran en un archivo local. Usará estas cadenas para conectarse al Servicio de aplicaciones web y cargar archivos a través de FTP.

   Por ejemplo:

   ![Copie las cadenas de conexión desde el panel FTP.](../media/dke-ftp-dashboard.png)

3. En la base de código para el almacenamiento de claves, vaya al **directorio customer-key-store\src\customer-key-store**.

4. Compruebe que este directorio contiene el **archivo customerkeystore.csproj.**

5. Ejecutar: **publicación de dotnet**

   El resultado contiene el directorio donde se implementó la publicación.

   Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. Envíe todos los archivos del directorio de publicación a un archivo zip. Al crear el .zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del .zip archivo.

7. Desde el cliente FTP, use la información de conexión que copió para conectarse al Servicio de aplicaciones. Upload el .zip que creó en el paso anterior al directorio raíz de la aplicación web.

DKE se implementa y puede examinar las claves de prueba que creó. A continuación, [valide la implementación](#validate-your-deployment).

### <a name="validate-your-deployment"></a>Validar la implementación

Después de implementar DKE con uno de los métodos descritos anteriormente, valide la implementación y la configuración del almacén de claves.

Ejecute: 

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

Por ejemplo:

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

Asegúrese de que no aparecen errores en el resultado. Cuando esté listo, [registre el almacén de claves](#register-your-key-store).

El nombre de clave distingue mayúsculas de minúsculas. Escriba el nombre de la clave tal como aparece en el archivo appsettings.json.

## <a name="register-your-key-store"></a>Registrar el almacén de claves

Los siguientes pasos permiten registrar el servicio DKE. Registrar el servicio DKE es el último paso para implementar DKE antes de empezar a crear etiquetas.

Para registrar el servicio DKE:

1. En el explorador, abra el [portal Microsoft Azure y](https://ms.portal.azure.com/)vaya a **Registros** de la aplicación de identidad de todos \>  \> **los servicios.**

2. Seleccione **Nuevo registro** y escriba un nombre significativo.

3. Seleccione un tipo de cuenta en las opciones que se muestran.

   Si usas Microsoft Azure con un dominio no personalizado, como **onmicrosoft.com,** selecciona Cuentas solo en este directorio de la organización **(solo Microsoft - Inquilino único).**

   Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Nuevo registro de aplicaciones.](../media/dke-app-registration.png)

4. En la parte inferior de la página, selecciona **Registrar** para crear el nuevo registro de aplicaciones.

5. En el nuevo registro de aplicaciones, en el panel izquierdo, en **Administrar**, seleccione **Autenticación**.

6. Seleccione **Agregar una plataforma**.

7. En el elemento **emergente Configurar plataformas,** seleccione **Web**.

8. En **Uri de redireccionamiento,** escriba el URI del servicio de cifrado de clave doble. Escribe la dirección URL de App Service, incluidos el nombre de host y el dominio.

   Por ejemplo: https://mydkeservicetest.com

   - La dirección URL que escriba debe coincidir con el nombre de host donde se implementa el servicio DKE.
   - Si está probando localmente con Visual Studio, use **https://localhost:5001** .
   - En todos los casos, el esquema debe ser **https**.

   Asegúrese de que el nombre de host coincide exactamente con el nombre de host de App Service. Es posible que lo haya cambiado para `localhost` solucionar problemas de la compilación. En **appsettings.json,** este valor es el nombre de host para el que se establece `JwtAudience` .

9. En **Concesión implícita,** active la casilla **tokens de** identificador.

10. Seleccione **Guardar** para guardar los cambios.

11. En el panel izquierdo, seleccione **Exponer una API** y, a continuación, junto a URI de id. de aplicación, seleccione **Establecer**.

12. En la página **Exponer una API,** en el área **Ámbitos definidos** por esta API, seleccione **Agregar un ámbito**. En el nuevo ámbito:

    1. Defina el nombre del ámbito **como user_impersonation**.

    2. Seleccione los administradores y usuarios que pueden dar su consentimiento.

    3. Defina los valores restantes necesarios.

    4. Seleccione **Agregar ámbito**.

    5. Seleccione **Guardar** en la parte superior para guardar los cambios.

13. En la página **Exponer una API,** en el **área Aplicaciones cliente autorizadas,** seleccione Agregar una **aplicación cliente.**

    En la nueva aplicación cliente:

    1. Defina el identificador de cliente como `d3590ed6-52b3-4102-aeff-aad2292ab01c` . Este valor es el Microsoft Office de cliente y permite Office obtener un token de acceso para el almacén de claves.

    2. En **Ámbitos autorizados,** seleccione **user_impersonation** ámbito.

    3. Seleccione **Agregar aplicación**.

    4. Seleccione **Guardar** en la parte superior para guardar los cambios.

    5. Repita estos pasos, pero esta vez defina el identificador de cliente como `c00e9d32-3c8d-4a7d-832b-029040e7db99` . Este valor es el identificador de cliente de etiquetado unificado de Azure Information Protection.

El servicio DKE ya está registrado. Continúe creando [etiquetas con DKE](#create-sensitivity-labels-using-dke).

## <a name="create-sensitivity-labels-using-dke"></a>Crear etiquetas de confidencialidad con DKE

En el Centro de cumplimiento de Microsoft 365, crea una nueva etiqueta de confidencialidad y aplica el cifrado como lo harías en caso contrario. Seleccione **Usar cifrado de clave doble** e introduzca la dirección URL del extremo de la clave.

Por ejemplo:

> [!div class="mx-imgBorder"]
> ![Seleccione Usar cifrado de clave doble en el Centro de cumplimiento de Microsoft 365.](../media/dke-use-dke.png)

Las etiquetas DKE que agregue empezarán a aparecer para los usuarios en las versiones más recientes de Aplicaciones Microsoft 365 para empresas.

> [!NOTE]
> Los clientes pueden tardar hasta 24 horas en actualizarse con las nuevas etiquetas.

### <a name="enable-dke-in-your-client"></a>Habilitar DKE en el cliente

Si eres un Office Insider, DKE está habilitado para ti. De lo contrario, habilite DKE para el cliente agregando las siguientes claves del Registro:

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>Migrar archivos protegidos de etiquetas HYOK a etiquetas DKE

Si lo desea, una vez que haya terminado de configurar DKE, puede migrar el contenido que ha protegido con etiquetas HYOK a etiquetas DKE. Para migrar, usará el escáner AIP. Para empezar a usar el escáner, vea ¿Qué es el escáner de etiquetado unificado de [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner).

Si no migra contenido, el contenido protegido por HYOK no se verá afectado.
