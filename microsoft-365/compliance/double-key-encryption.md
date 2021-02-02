---
title: Cifrado de clave doble (DKE)
description: DKE le permite proteger datos altamente confidenciales a la vez que mantiene el control total de la clave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c10a10a5922755db2c901137c3dff8acee5b8445
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066863"
---
# <a name="double-key-encryption-for-microsoft-365"></a>Cifrado de doble clave para Microsoft 365

> *Se aplica a: Cifrado de doble clave para Microsoft 365, Cumplimiento de [Microsoft 365,](https://www.microsoft.com/microsoft-365/business/compliance-management) [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *Instrucciones para: Cliente de etiquetado unificado de [Azure Information Protection para Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *Descripción del servicio para: [Cumplimiento de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

El cifrado de doble clave (DKE) usa dos claves juntas para obtener acceso al contenido protegido. Microsoft almacena una clave en Microsoft Azure y usted mantiene la otra clave. Mantiene el control total de una de las claves mediante el servicio cifrado de doble clave. Puede aplicar protección mediante el cliente de etiquetado unificado de Azure Information Protection a su contenido altamente confidencial.

El cifrado de doble clave admite implementaciones locales y en la nube. Estas implementaciones ayudan a garantizar que los datos cifrados permanecen opacos donde se almacenan los datos protegidos.

Para obtener más información acerca de las claves raíz de inquilino predeterminadas basadas en la nube, consulte Planeación e implementación de la clave de inquilino [de Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)

## <a name="when-your-organization-should-adopt-dke"></a>Cuándo debe adoptar su organización DKE

El cifrado de doble clave está pensado para los datos más confidenciales que están sujetos a los requisitos de protección más estrictos. DKE no está pensado para todos los datos. En general, va a usar cifrado de doble clave para proteger solo una pequeña parte de los datos generales. Debe realizar la debida diligencia a la hora de identificar los datos adecuados que se deben cubrir con esta solución antes de implementar. En algunos casos, es posible que deba restringir el ámbito y usar otras soluciones para la mayoría de los datos, como Microsoft Information Protection con claves administradas por Microsoft o BYOK. Estas soluciones son suficientes para documentos que no están sujetos a protecciones mejoradas y requisitos normativos. Además, estas soluciones le permiten usar los servicios más eficaces de Office 365; que no puede usar con contenido cifrado DKE. Por ejemplo:

- Reglas de transporte como antimalware y correo no deseado que requieren visibilidad de los datos adjuntos
- Microsoft Delve
- eDiscovery
- Búsqueda e indización de contenido
- Office Web Apps, incluida la funcionalidad de coautoría

Las aplicaciones o servicios externos que no están integrados con DKE a través del SDK de MIP no podrán realizar acciones en los datos cifrados.

Microsoft Information Protection SDK 1.7+ admite el cifrado de doble clave; las aplicaciones que se integran con nuestro SDK podrán realizar una razón sobre estos datos con permisos e integraciones suficientes en su lugar.

Se recomienda que las organizaciones usen las capacidades de Protección de la información de Microsoft (clasificación y etiquetado) para proteger la mayoría de sus datos confidenciales y usar solo DKE para sus datos fundamentales. El cifrado de doble clave es relevante para datos confidenciales en sectores altamente regulados, como servicios financieros y sanidad.

Si su organización tiene cualquiera de los siguientes requisitos, puede usar DKE para ayudar a proteger su contenido:

- Desea asegurarse de que *solo usted pueda* descifrar el contenido protegido, en todas las circunstancias.
- No quiere que Microsoft tenga acceso a datos protegidos por sí mismo.
- Tiene requisitos normativos para contener claves dentro de un límite geográfico. Todas las claves que conserva para el cifrado y descifrado de datos se mantienen en el centro de datos.

## <a name="system-and-licensing-requirements-for-dke"></a>Requisitos de sistema y licencias para DKE

**Cifrado de doble clave para Microsoft 365** viene con Microsoft 365 E5. Si no tiene una licencia de Microsoft 365 E5, puede registrarse para obtener una [versión de prueba.](https://aka.ms/M365E5ComplianceTrial) Para obtener más información acerca de estas licencias, vea la guía de licencias de [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)para la seguridad & cumplimiento.

**Azure Information Protection**. DKE funciona con etiquetas de confidencialidad y requiere Azure Information Protection.

Las etiquetas de confidencialidad DKE están disponibles para los usuarios finales a través de la cinta de opciones de confidencialidad en aplicaciones de escritorio de Office. Instale estos requisitos previos en cada equipo cliente donde desee proteger y consumir documentos protegidos.

**Microsoft Office Aplicaciones para** empresas versión *.12711 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.

**Cliente de etiquetado unificado de Azure Information Protection** versión 2.7.93.0 o posterior. Descargue e instale el cliente de etiquetado unificado desde el Centro [de descarga de Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Entornos admitidos para almacenar y ver contenido protegido por DKE

**Aplicaciones admitidas.** [Aplicaciones de Microsoft 365 para clientes empresariales](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) en Windows, incluidos Word, Excel y PowerPoint.

**Compatibilidad con contenido en línea.** Se admiten documentos y archivos almacenados en línea en Microsoft SharePoint y OneDrive para la Empresa. Puede compartir contenido cifrado por correo electrónico, pero no puede ver documentos y archivos cifrados en línea. En su lugar, debes ver el contenido protegido mediante las aplicaciones de escritorio del equipo local.

## <a name="overview-of-deploying-dke"></a>Información general sobre la implementación de DKE

Siga estos pasos generales para configurar DKE. Una vez que haya completado estos pasos, los usuarios finales podrán proteger los datos altamente confidenciales con cifrado de doble clave.

1. Implemente el servicio DKE como se describe en este artículo.

2. Cree una etiqueta con cifrado de doble clave. Vaya a Protección de la información en el Centro [de cumplimiento de Microsoft 365](https://compliance.microsoft.com) y cree una nueva etiqueta con cifrado de doble clave. Vea [Restringir el acceso al contenido mediante etiquetas de confidencialidad para aplicar el cifrado.](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

3. Use etiquetas de cifrado de doble clave. Proteja los datos seleccionando la etiqueta Cifrado de doble clave en la cinta de opciones de confidencialidad Microsoft Office.

Hay varias maneras de completar algunos de los pasos para implementar el cifrado de doble clave. En este artículo se proporcionan instrucciones detalladas para que los administradores menos experimentados implemente correctamente el servicio. Si se siente cómodo al hacerlo, puede elegir usar sus propios métodos.

## <a name="deploy-dke"></a>Implementar DKE

Este artículo y el vídeo de implementación usan Azure como destino de implementación para el servicio DKE. Si está implementando en otra ubicación, deberá proporcionar sus propios valores.

Vea el [vídeo de implementación de cifrado de doble](https://youtu.be/vDWfHN_kygg) clave para ver una introducción paso a paso de los conceptos de este artículo. El vídeo tarda unos 18 minutos en completarse.

Siga estos pasos generales para configurar el cifrado de doble clave para su organización.

1. [Instalación de requisitos previos de software para el servicio DKE](#install-software-prerequisites-for-the-dke-service)
1. [Clonar el repositorio de GitHub de cifrado de doble clave](#clone-the-dke-github-repository)
1. [Modificar la configuración de la aplicación](#modify-application-settings)
1. [Generar claves de prueba](#generate-test-keys)
1. [Compilar el proyecto](#build-the-project)
1. [Implementar el servicio DKE y publicar el almacén de claves](#deploy-the-dke-service-and-publish-the-key-store)
1. [Validar la implementación](#validate-your-deployment)
1. [Registrar el almacén de claves](#register-your-key-store)
1. [Crear etiquetas de confidencialidad con DKE](#create-sensitivity-labels-using-dke)
1. [Habilitar DKE en el cliente](#enable-dke-in-your-client)
1. [Migrar archivos protegidos de etiquetas HYOK a etiquetas DKE](#migrate-protected-files-from-hyok-labels-to-dke-labels)

Cuando haya terminado, puede cifrar documentos y archivos mediante DKE. Para obtener información, vea [Aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office.](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

### <a name="install-software-prerequisites-for-the-dke-service"></a>Instalación de requisitos previos de software para el servicio DKE

Instale estos requisitos previos en el equipo donde desea instalar el servicio DKE.

**.NET Core 3.1 SDK**. Descargue e instale el SDK desde [Descargar .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1)

**Visual Studio código.** Descargar Visual Studio código de [https://code.visualstudio.com/](https://code.visualstudio.com) . Una vez instalado, ejecute Visual Studio  código y seleccione \> **Ver extensiones**. Instale estas extensiones.

- C# para Visual Studio código

- NuGet Administrador de paquetes

**Recursos de Git**. Descargue e instale una de las siguientes opciones.

- [Git](https://git-scm.com/downloads)

- [Escritorio de GitHub](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** Debe tener [OpenSSL instalado](https://slproweb.com/products/Win32OpenSSL.html) para generar [claves de prueba](#generate-test-keys) después de implementar DKE. Asegúrese de invocarlo correctamente desde la ruta de variables de entorno. Por ejemplo, consulte "Agregar el directorio de instalación a PATH" para [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) obtener más información.

### <a name="clone-the-dke-github-repository"></a>Clonar el repositorio de GitHub de DKE

Microsoft proporciona los archivos de origen DKE en un repositorio de GitHub. Clone el repositorio para compilar el proyecto localmente para el uso de su organización. El repositorio de GitHub DKE se encuentra en [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

Las siguientes instrucciones están pensadas para usuarios de git o Visual Studio código no experimentados:

1. En el explorador, vaya a: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

2. Hacia el lado derecho de la pantalla, seleccione **Código**. Es posible que la versión de la interfaz de usuario muestre un **botón Clonar o** descargar. A continuación, en la lista desplegable que aparece, seleccione el icono de copia para copiar la dirección URL en el Portapapeles.

    Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Clonar el repositorio del servicio de cifrado de doble clave desde GitHub](../media/dke-clone.png)

3. En Visual Studio, seleccione **Ver** paleta \> **de** comandos y **seleccione Git: Clonar**. Para ir a la opción de la lista, empiece a escribir para filtrar las entradas y, a continuación, `git: clone` selecciónelo en la lista desplegable. Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Visual Studio de código GIT:Clone](../media/dke-vscode-clone.png)

4. En el cuadro de texto, pegue la dirección URL que copió de Git y seleccione **Clonar desde GitHub**.

5. En el **cuadro de diálogo Seleccionar** carpeta que aparece, busque y seleccione una ubicación para almacenar el repositorio. En el símbolo del sistema, seleccione **Abrir**.

    El repositorio se abre en Visual Studio código y muestra la rama de Git actual en la parte inferior izquierda. Por ejemplo, la rama debe ser **principal.** Por ejemplo:

   ![Captura de pantalla del repositorio DKE en Visual Studio código que muestra la rama principal](../media/dke-vscode-main-branch.jpg)

6. Si no estás en la rama principal, tendrás que seleccionarla. En Visual Studio código, seleccione la rama y elija **principal** en la lista de sucursales que se muestra.

   > [!IMPORTANT]
   > La selección de la rama principal garantiza que tiene los archivos correctos para compilar el proyecto. Si no elige la rama correcta, se producirá un error en la implementación.

Ahora tiene el repositorio de origen de DKE configurado localmente. A [continuación, modifique la configuración de](#modify-application-settings) la aplicación para su organización.

### <a name="modify-application-settings"></a>Modificar la configuración de la aplicación

Para implementar el servicio DKE, debe modificar los siguientes tipos de configuración de la aplicación:

- [Configuración de acceso de teclas](#key-access-settings)
- [Configuración de inquilino y clave](#tenant-and-key-settings)

La configuración de la aplicación se modifica en el appsettings.jsdel archivo. Este archivo se encuentra en el repositorio DoubleKeyEncryptionService clonado localmente en DoubleKeyEncryptionService\src\customer-key-store. Por ejemplo, en Visual Studio código, puede examinar el archivo como se muestra en la siguiente imagen.

![Ubicar el archivo appsettings.jsarchivo de DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>Configuración de acceso de teclas

Elija si desea usar la autorización de correo electrónico o rol. DKE solo admite uno de estos métodos de autenticación a la vez.

- **Autorización de correo electrónico.** Permite que su organización autorice el acceso a las claves solo en función de las direcciones de correo electrónico.

- **Autorización de roles.** Permite que su organización autorice el acceso a claves basadas en grupos de Active Directory y requiere que el servicio web pueda consultar LDAP.

**Para establecer la configuración de acceso clave para DKE mediante la autorización de correo electrónico**

1. Abra el **appsettings.jsen el archivo** y busque la `AuthorizedEmailAddress` configuración.

2. Agregue la dirección de correo electrónico o las direcciones que desee autorizar. Separe varias direcciones de correo electrónico con comillas dobles y comas. Por ejemplo:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Busque la `LDAPPath` configuración y quite el texto entre las `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` comillas dobles. Deje las comillas dobles en su lugar. Cuando haya terminado, la configuración debería tener este aspecto.

   ```json
   "LDAPPath": ""
   ```

4. Busque la `AuthorizedRoles` configuración y elimine toda la línea.

En esta imagen se muestra **appsettings.jsarchivo** con el formato correcto para la autorización de correo electrónico.

   ![El appsettings.jsarchivo que muestra el método de autorización de correo electrónico](../media/dke-email-accesssetting.png)

**Para establecer la configuración de acceso clave para DKE mediante la autorización de roles**

1. Abra el **appsettings.jsen el archivo** y busque la `AuthorizedRoles` configuración.

2. Agregue los nombres de grupo de Active Directory que desee autorizar. Separe varios nombres de grupo con comillas dobles y comas. Por ejemplo:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Busque la `LDAPPath` configuración y agregue el dominio de Active Directory. Por ejemplo:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Busque la `AuthorizedEmailAddress` configuración y elimine toda la línea.

En esta imagen se muestra **appsettings.jsarchivo** con el formato correcto para la autorización de roles.

   ![appsettings.jsarchivo que muestra el método de autorización de roles](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>Configuración de inquilino y clave

La configuración del inquilino y la clave de DKE se encuentran **enappsettings.jsarchivo de** inicio de sesión.

**Para configurar el espacio empresarial y las opciones de clave para DKE**

1. Abra el **appsettings.jsen el** archivo.

2. Busque la `ValidIssuers` configuración y reempláctela `<tenantid>` por su id. de espacio empresarial. Puede buscar su id. de inquilino yendo a Azure Portal y viendo las propiedades [del espacio empresarial.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) Por ejemplo:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

Busque el `JwtAudience` archivo . Reemplace `<yourhostname>` por el nombre de host de la máquina donde se ejecutará el servicio DKE. Por ejemplo:

  > [!IMPORTANT]
  > El valor debe `JwtAudience` coincidir exactamente con el nombre del host. Puede usar **localhost:5001** durante la depuración. Sin embargo, cuando haya terminado la depuración, asegúrese de actualizar este valor al nombre de host del servidor.

- `TestKeys:Name`. Escriba un nombre para la clave. Por ejemplo: `TestKey1`
- `TestKeys:Id`. Crear un GUID y escribirlo como `TestKeys:ID` el valor. Por ejemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. Puede usar un sitio como [el generador guid en](https://guidgenerator.com/) línea para generar aleatoriamente un GUID.

Esta imagen muestra el formato correcto para la configuración del espacio empresarial y las **clavesappsettings.jsen**. `LDAPPath` está configurado para la autorización de roles.

![Muestra la configuración de inquilino y clave correcta para DKE en appsettings.jsarchivo on.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>Generar claves de prueba

Una vez que haya definido la configuración de la aplicación, estará listo para generar claves de prueba públicas y privadas.

Para generar claves:

1. En el menú Inicio de Windows, ejecuta el símbolo del sistema de OpenSSL.

2. Cambie a la carpeta donde desea guardar las claves de prueba. Los archivos que cree completando los pasos de esta tarea se almacenan en la misma carpeta.

3. Genere la nueva clave de prueba.

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. Genera la clave privada.

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. Genere la clave pública.

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. En un editor de texto, **abra pubkeyonly.pem**. Copie todo el contenido del archivo **pubkeyonly.pem,** excepto la primera y la última línea, en la sección del archivo `PublicPem` **appsettings.jsarchivo.**

7. En un editor de texto, abra **privkeynopass.pem**. Copie todo el contenido del archivo **privkeynopass.pem,** excepto la primera y la última línea, en la sección del archivo `PrivatePem` **appsettings.jsarchivo.**

8. Quite todos los espacios en blanco y las nuevas líneas tanto en `PublicPem` las secciones como en las `PrivatePem` secciones.

    > [!IMPORTANT]
    > Al copiar este contenido, no elimine ninguno de los datos PEM.

9. En Visual Studio código, vaya al **Startup.cs** archivo. Este archivo se encuentra en el repositorio DoubleKeyEncryptionService clonado localmente en DoubleKeyEncryptionService\src\customer-key-store\.

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

    ![startup.cs de vista previa pública](../media/dke-startupcs-usetestkeys.png)

Ahora ya está listo para compilar [el proyecto DKE.](#build-the-project)

### <a name="build-the-project"></a>Compile el proyecto.

Siga las instrucciones siguientes para crear el proyecto DKE localmente:

1. En Visual Studio código, en el repositorio del servicio  DKE, seleccione Ver paleta de comandos y, a \>  continuación, **escriba compilación** en el símbolo del sistema.

2. En la lista, elija **Tareas: Ejecutar tarea de compilación.**

   Si no se encuentran tareas de compilación, seleccione Configurar tarea **de** compilación y cree una para .NET Core de la siguiente manera.

   ![Configurar la tarea de compilación que falta para .NET](../media/dke-configurebuildtask.png)

   1. Elija **Crear tasks.jsa partir de la plantilla.**

      ![Crear tasks.jsarchivo a partir de la plantilla para DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. En la lista de tipos de plantilla, seleccione **.NET Core**.

      ![Seleccionar la plantilla correcta para DKE](../media/dke-tasksjsontemplate.png)

   3. En la sección de compilación, busque la ruta de acceso al **archivo customerkeystore.csproj.** Si no está ahí, agregue la siguiente línea:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. Vuelva a ejecutar la compilación.

3. Compruebe que no haya errores rojos en la ventana de salida.

   Si hay errores de color rojo, compruebe la salida de la consola. Asegúrese de que ha completado todos los pasos anteriores correctamente y de que están presentes las versiones de compilación correctas.

4. Seleccione **Ejecutar** \> **la depuración de inicio** para depurar el proceso. Si se le pide que seleccione un entorno, seleccione **.NET core**.

   El depurador de .NET core normalmente se inicia en `https://localhost:5001` . Para ver la clave de prueba, vaya y anexe una barra diagonal `https://localhost:5001` (/) y el nombre de la clave. Por ejemplo:

   ```https
   https://localhost:5001/TestKey1
   ```

   La clave debe mostrarse en formato JSON.

La configuración ya está completa. Antes de publicar el almacén de claves, en appsettings.js, para la configuración JwtAudience, asegúrate de que el valor del nombre de host coincida exactamente con el nombre de host de App Service. Es posible que lo haya cambiado a localhost para solucionar problemas de la compilación.

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>Implementar el servicio DKE y publicar el almacén de claves

Para implementaciones de producción, implemente el servicio en una nube de terceros o [publeméntelo en un sistema local.](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)

Es posible que prefieras otros métodos para implementar las claves. Seleccione el método que mejor se adapte a su organización.

Para las implementaciones piloto, puede implementar en Azure y empezar a trabajar inmediatamente.

**Para crear una instancia de Azure Web App para hospedar la implementación de DKE**

Para publicar el almacén de claves, creará una instancia de Azure App Service para hospedar la implementación de DKE. A continuación, publicará las claves generadas en Azure.

1. En el explorador, inicie sesión en [Microsoft Azure Portal](https://ms.portal.azure.com)y vaya a App **Services**  >  **Add**.

2. Seleccione la suscripción y el grupo de recursos y defina los detalles de la instancia.

   - Escriba el nombre de host del equipo donde desea instalar el servicio DKE. Asegúrese de que es el mismo nombre que el definido para la configuración jwtAudience en el [**appsettings.jsarchivo on.**](#tenant-and-key-settings) El valor que proporcione para el nombre también es WebAppInstanceName.

   - Para **Publicar,** seleccionar **código y** para la pila de tiempo **de** ejecución, seleccione **.NET Core 3.1**.

   Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Agregar el servicio de aplicaciones](../media/dke-azure-add-app-service.png)

3. En la parte inferior de la página, seleccione **Revisar + crear** y, a continuación, seleccione **Agregar**.

4. Realice una de las siguientes acciones para publicar las claves generadas:

   - [Publicar a través de ZipDeployUI](#publish-via-zipdeployui)
   - [Publicar a través de FTP](#publish-via-ftp)
   - [Publicar a Visual Studio 2019 o posterior](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>Publicar a través de ZipDeployUI

1. Vaya a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

   Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. En el código base del almacén de claves, vaya a la carpeta **customer-key-store\src\customer-key-store** y compruebe que esta carpeta contiene el archivo **customerkeystore.csproj.**

3. Ejecutar: **publicación de dotnet**

   La ventana de salida muestra el directorio donde se implementó la publicación.

   Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. Envíe todos los archivos del directorio de publicación a un archivo .zip. Al crear el archivo .zip, asegúrate de que todos los archivos del directorio se encuentran en el nivel raíz del archivo .zip.

5. Arrastre y coloque el archivo .zip que cree en el sitio ZipDeployUI que abrió anteriormente. Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE se implementa y puede buscar las claves de prueba que ha creado. Continúe [validando la implementación que se muestra](#validate-your-deployment) a continuación.

#### <a name="publish-via-ftp"></a>Publicar a través de FTP

1. Conéctese al servicio de aplicaciones que creó [anteriormente.](#deploy-the-dke-service-and-publish-the-key-store)

   En el explorador, vaya a: Panel FTP de implementación manual del Centro de implementación de **Azure Portal** App  >    >    >    >    >  Service.

2. Copie las cadenas de conexión que se muestran en un archivo local. Usará estas cadenas para conectarse al servicio web de aplicaciones y cargar archivos a través de FTP.

   Por ejemplo:

   ![Copiar cadenas de conexión desde el panel FTP](../media/dke-ftp-dashboard.png)

3. En el código base para el almacenamiento de claves, vaya al directorio **customer-key-store\src\customer-key-store**.

4. Compruebe que este directorio contiene el **archivo customerkeystore.csproj.**

5. Ejecutar: **publicación de dotnet**

   El resultado contiene el directorio donde se implementó la publicación.

   Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. Envíe todos los archivos del directorio de publicación a un archivo zip. Al crear el archivo .zip, asegúrate de que todos los archivos del directorio se encuentran en el nivel raíz del archivo .zip.

7. Desde el cliente FTP, use la información de conexión que copió para conectarse a App Service. Cargue el archivo .zip que creó en el paso anterior en el directorio raíz de la aplicación web.

DKE está implementado y puede buscar las claves de prueba que ha creado. A continuación, [valide la implementación.](#validate-your-deployment)

### <a name="validate-your-deployment"></a>Validar la implementación

Después de implementar DKE mediante uno de los métodos descritos anteriormente, valide la implementación y la configuración del almacén de claves.

Ejecute:

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

Por ejemplo:

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

Asegúrese de que no aparecen errores en el resultado. Cuando esté listo, [registre el almacén de claves.](#register-your-key-store)

El nombre de la clave distingue mayúsculas de minúsculas. Escriba el nombre de la clave tal como aparece en el appsettings.jsarchivo de inicio de sesión.

## <a name="register-your-key-store"></a>Registrar el almacén de claves

Los siguientes pasos permiten registrar el servicio DKE. El último paso para implementar DKE es registrar el servicio DKE antes de empezar a crear etiquetas.

Para registrar el servicio DKE:

1. En el explorador, abra [Microsoft Azure Portal](https://ms.portal.azure.com/)y vaya a **Registros** de aplicaciones de identidad de todos \>  \> **los servicios.**

2. Seleccione **Nuevo registro** y escriba un nombre significativo.

3. Seleccione un tipo de cuenta de las opciones mostradas.

   Si usa Microsoft Azure con un dominio no personalizado, como **onmicrosoft.com,** seleccione Solo cuentas en este directorio de la organización **(Solo Microsoft - Inquilino único).**

   Por ejemplo:

   > [!div class="mx-imgBorder"]
   > ![Registro de nuevas aplicaciones](../media/dke-app-registration.png)

4. En la parte inferior de la página, seleccione **Registrar** para crear el nuevo registro de aplicaciones.

5. En el nuevo registro de aplicaciones, en el panel izquierdo, en **Administrar**, seleccione **Autenticación.**

6. Seleccione **Agregar una plataforma.**

7. En el elemento **emergente Configurar plataformas,** seleccione **Web**.

8. En **URI de redireccionamiento,** escriba el URI de su servicio de cifrado de doble clave. Escribe la dirección URL de App Service, incluidos el nombre de host y el dominio.

   Por ejemplo: https://mydkeservicetest.com

   - La dirección URL que escriba debe coincidir con el nombre de host donde se implementa el servicio DKE.
   - Si está probando localmente con Visual Studio, use **https://localhost:5001** .
   - En todos los casos, el esquema debe ser **https**.

   Asegúrate de que el nombre de host coincida exactamente con el nombre de host de App Service. Es posible que lo haya cambiado para `localhost` solucionar problemas de la compilación. En **appsettings.js,** este valor es el nombre de host para el que se estableció `JwtAudience` .

9. En **Concesión implícita,** active la casilla **de verificación de tokens de** identificador.

10. Seleccione **Guardar** para guardar los cambios.

11. En el panel izquierdo, seleccione **Exponer una API** y, a continuación, junto a URI de id. de aplicación, seleccione **Establecer**.

12. Still on the **Expose an API** page, in the **Scopes defined by this API** area, select Add a **scope**. En el nuevo ámbito:

    1. Defina el nombre del ámbito **como user_impersonation**.

    2. Seleccione los administradores y usuarios que pueden dar su consentimiento.

    3. Defina los valores restantes necesarios.

    4. Seleccione **Agregar ámbito**.

    5. Seleccione **Guardar** en la parte superior para guardar los cambios.

13. En la página **Exponer una API,** en el **área Aplicaciones cliente autorizadas,** seleccione Agregar una **aplicación cliente.**

    En la nueva aplicación cliente:

    1. Defina el identificador de cliente como **d3590ed6-52b3-4102-aeff-aad2292ab01c**. Este valor es el Microsoft Office de cliente y permite a Office obtener un token de acceso para el almacén de claves.

    2. En **Ámbitos autorizados,** seleccione **user_impersonation** ámbito.

    3. Seleccione **Agregar aplicación**.

    4. Seleccione **Guardar** en la parte superior para guardar los cambios.

El servicio DKE ya está registrado. Continúe creando [etiquetas con DKE](#create-sensitivity-labels-using-dke).

## <a name="create-sensitivity-labels-using-dke"></a>Crear etiquetas de confidencialidad con DKE

En el Centro de cumplimiento de Microsoft 365, cree una nueva etiqueta de confidencialidad y aplique el cifrado como lo haría de otro modo. Seleccione **Usar cifrado de doble clave** y escriba la dirección URL del extremo de la clave.

Por ejemplo:

> [!div class="mx-imgBorder"]
> ![Seleccione Usar cifrado de doble clave en el Centro de cumplimiento de Microsoft 365](../media/dke-use-dke.png)

Las etiquetas DKE que agregue empezarán a aparecer para los usuarios en las versiones más recientes de Aplicaciones de Microsoft 365 para empresas.

> [!NOTE]
> Los clientes pueden tardar hasta 24 horas en actualizarse con las nuevas etiquetas.

### <a name="enable-dke-in-your-client"></a>Habilitar DKE en el cliente

Si es un usuario de Office Insider, DKE está habilitado para usted. De lo contrario, habilite DKE para el cliente agregando las siguientes claves del Registro:

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>Migrar archivos protegidos de etiquetas HYOK a etiquetas DKE

Si lo desea, una vez que haya terminado de configurar DKE, puede migrar el contenido que ha protegido mediante etiquetas HYOK a etiquetas DKE. Para migrar, usará el escáner AIP. Para empezar a usar el escáner, consulte ¿Qué es el escáner de etiquetado unificado de [Azure Information Protection?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)

Si no migra contenido, el contenido protegido con HYOK no se verá afectado.
