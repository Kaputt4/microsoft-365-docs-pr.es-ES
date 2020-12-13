---
title: Cifrado de clave doble (DKE)
description: DKE permite proteger datos extremadamente confidenciales y mantener el control total de la clave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 9607b095ba073229edae43c1d2f0e893db07c634
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663095"
---
# <a name="double-key-encryption-for-microsoft-365"></a>Cifrado de doble clave para Microsoft 365

> *Se aplica a: cifrado de doble clave para Microsoft 365, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *Instrucciones para: [cliente de etiquetado Unificado de Azure Information Protection para Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *Descripción del servicio para: [cumplimiento de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

El cifrado de doble clave (DKE) utiliza dos claves conjuntamente para obtener acceso al contenido protegido. Microsoft almacena una clave en Microsoft Azure y mantiene la otra clave. Se mantiene un control total de una de las claves mediante el servicio de cifrado de doble clave. La protección se aplica mediante el cliente de etiquetado Unificado de Azure Information Protection a su contenido extremadamente confidencial.

El cifrado de doble clave admite tanto la nube como las implementaciones locales. Estas implementaciones ayudan a garantizar que los datos cifrados permanezcan opacos dondequiera que almacene los datos protegidos.

Para obtener más información acerca de las claves predeterminadas de raíz de inquilino basadas en la nube, vea [Planning and Implementing Your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).

## <a name="when-your-organization-should-adopt-dke"></a>Cuando su organización debe adoptar DKE

El cifrado de doble clave está destinado a los datos más confidenciales que están sujetos a los requisitos de protección más estrictos. DKE no está pensada para todos los datos. En general, utilizará el cifrado de doble clave para proteger solo una parte muy pequeña de los datos globales. Debe llevar a cabo la diligencia debida para identificar los datos correctos que se incluirán con esta solución antes de implementarla. En algunos casos, es posible que necesite limitar el ámbito y usar otras soluciones para la mayoría de los datos, como Microsoft Information Protection con claves administradas por Microsoft o BYOK. Estas soluciones son suficientes para los documentos que no están sujetos a las protecciones mejoradas y a los requisitos normativos. Además, estas soluciones le permiten usar los servicios de Office 365 más eficaces; servicios que no se pueden usar con contenido cifrado de DKE. Por ejemplo:

- Reglas de transporte que incluyen protección contra malware y correo no deseado que requieren visibilidad en los datos adjuntos
- Microsoft Delve
- eDiscovery
- Búsqueda de contenido e indización
- Office Web Apps, incluida la funcionalidad de co-autoría

Cualquier aplicación o servicio externo que no esté integrado con DKE a través del SDK de MIP no podrá realizar acciones en los datos cifrados.

El SDK de Microsoft Information Protection 1.7 + admite el cifrado de doble clave; las aplicaciones que se integran con nuestro SDK podrán conllevarle motivos sobre estos datos con los permisos e integraciones suficientes.

Recomendamos que las organizaciones usen las capacidades de Microsoft Information Protection (clasificación y etiquetado) para proteger la mayoría de sus datos confidenciales y solo usen DKE para sus datos de misión crítica. El cifrado de doble clave es especialmente relevante para los datos extremadamente confidenciales en industrias altamente reguladas, como los servicios financieros y la asistencia sanitaria.

Si las organizaciones tienen alguno de los siguientes requisitos, puede usar DKE para ayudar a proteger el contenido:

- Desea asegurarse de que *solo usted* puede descifrar el contenido protegido en todas las circunstancias.
- No desea que Microsoft tenga acceso a datos protegidos por su cuenta.
- Tiene requisitos normativos para mantener las claves dentro de un límite geográfico. Todas las claves que se incluyen para el cifrado y descifrado de datos se mantienen en el centro de datos.

## <a name="system-and-licensing-requirements-for-dke"></a>Requisitos de licencia y sistema para DKE

El **cifrado de doble clave para microsoft 365** incluye Microsoft 365 E5. Si no tiene una licencia de Microsoft 365 E5, puede registrarse para obtener una [versión de prueba](https://aka.ms/M365E5ComplianceTrial). Para obtener más información acerca de estas licencias, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

**Azure Information Protection**. DKE funciona con etiquetas de confidencialidad y requiere Azure Information Protection.

Las etiquetas de confidencialidad de DKE están disponibles para los usuarios finales a través de la cinta de confidencialidad en las aplicaciones de escritorio de Office. Instale estos requisitos previos en cada equipo cliente donde quiera proteger y consumir documentos protegidos.

**Microsoft Office apps for Enterprise** versión *. 12711 o posterior (versiones de escritorio de Word, PowerPoint y Excel) en Windows.

**Azure Information Protection el cliente de etiquetado unificado** versiones 2.7.93.0 o posterior. Descargue e instale el cliente de etiquetado unificado desde el [centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Entornos admitidos para almacenar y ver contenido protegido por DKE

**Aplicaciones compatibles**. [Microsoft 365 apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients in Windows, incluidos Word, Excel y PowerPoint.

**Soporte de contenido en línea**. Se admiten los documentos y archivos almacenados en línea tanto en Microsoft SharePoint como en OneDrive para la empresa. Puede compartir contenido cifrado por correo electrónico, pero no puede ver documentos cifrados y archivos en línea. En su lugar, debe ver el contenido protegido con las aplicaciones de escritorio en su equipo local.

## <a name="overview-of-deploying-dke"></a>Información general sobre la implementación de DKE

Seguiremos estos pasos generales para configurar DKE. Una vez que haya completado estos pasos, los usuarios finales podrán proteger los datos extremadamente confidenciales con el cifrado doble de claves.

1. Implemente el servicio DKE tal como se describe en este artículo.

2. Cree una etiqueta con dos claves de cifrado. Navegue a Information Protection en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) y cree una nueva etiqueta con cifrado de doble clave. Consulte [restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).

3. Use las etiquetas de cifrado de doble clave. Proteja los datos seleccionando la etiqueta cifrada de doble clave en la cinta de confidencialidad de Microsoft Office.

Hay varias formas de realizar algunos de los pasos para implementar el cifrado doble de claves. En este artículo se proporcionan instrucciones detalladas para que los administradores menos experimentados implementen correctamente el servicio. Si le resulta cómodo hacerlo, puede elegir usar sus propios métodos.

## <a name="deploy-dke"></a>Implementar DKE

Este artículo y el vídeo de implementación usan Azure como destino de implementación para el servicio DKE. Si va a realizar la implementación en otra ubicación, deberá proporcionar sus propios valores.

Vea el [vídeo sobre la implementación de doble clave](https://youtu.be/vDWfHN_kygg) para ver una introducción paso a paso de los conceptos de este artículo. El vídeo tarda unos 18 minutos en completarse.

Deberá seguir estos pasos generales para configurar el cifrado de doble clave para su organización.

1. [Instalar los requisitos previos de software para el servicio DKE](#install-software-prerequisites-for-the-dke-service)
1. [Clone el repositorio de GitHub con cifrado de doble clave](#clone-the-dke-github-repository)
1. [Modificación de la configuración de la aplicación](#modify-application-settings)
1. [Generar claves de prueba](#generate-test-keys)
1. [Compile el proyecto.](#build-the-project)
1. [Implementar el servicio DKE y publicar el almacén de claves](#deploy-the-dke-service-and-publish-the-key-store)
1. [Validar la implementación](#validate-your-deployment)
1. [Registrar el almacén de claves](#register-your-key-store)
1. [Crear etiquetas de confidencialidad mediante DKE](#create-sensitivity-labels-using-dke)
1. [Habilitar DKE en el cliente](#enable-dke-in-your-client)
1. [Migrar archivos protegidos desde etiquetas HYOK a etiquetas DKE](#migrate-protected-files-from-hyok-labels-to-dke-labels)

Cuando haya terminado, puede cifrar documentos y archivos con DKE. Para obtener más información, consulte [aplicar etiquetas de confidencialidad a los archivos y el correo electrónico en Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

### <a name="install-software-prerequisites-for-the-dke-service"></a>Instalar los requisitos previos de software para el servicio DKE

Instale estos requisitos previos en el equipo en el que desea instalar el servicio DKE.

**SDK .net Core 3,1**. Descargue e instale el SDK desde [download .net Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).

**Visual Studio Code**. Descargue Visual Studio Code desde [https://code.visualstudio.com/](https://code.visualstudio.com) . Una vez instalado, ejecute Visual Studio Code y seleccione **Ver** \> **extensiones**. Instale estas extensiones.

- C# para Visual Studio Code

- Administrador de paquetes NuGet

**Recursos git**. Descargue e instale uno de los siguientes elementos.

- [Git](https://git-scm.com/downloads)

- [Escritorio de GitHub](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** Debe tener instalado [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) para [generar las claves de prueba](#generate-test-keys) después de implementar DKE. Asegúrese de que está invocando correctamente desde la ruta de las variables de entorno. Por ejemplo, consulte "agregar el directorio de instalación a la ruta de acceso" en [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) para más detalles.

### <a name="clone-the-dke-github-repository"></a>Clonar el repositorio de GitHub DKE

Microsoft proporciona los archivos de origen de DKE en un repositorio de GitHub. Clonar el repositorio para compilar el proyecto de forma local para el uso de su organización. El repositorio de GitHub DKE se encuentra en [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

Las siguientes instrucciones están destinadas a usuarios no con experiencia de Git o Visual Studio Code:

1. En el explorador, vaya a: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

2. Hacia el lado derecho de la pantalla, seleccione **código**. Es posible que la versión de la interfaz de usuario muestre un botón **clonar o descargar** . A continuación, en la lista desplegable que aparece, seleccione el icono de copia para copiar la dirección URL en el portapapeles.

    Por ejemplo:

   ![Clone el repositorio del servicio de cifrado de doble clave desde GitHub](../media/dke-clone.png)

3. En Visual Studio Code, seleccione **Ver** \> **paleta de comandos** y seleccione **git: clon**. Para ir a la opción de la lista, empiece a escribir `git: clone` para filtrar las entradas y, a continuación, selecciónela en la lista desplegable. Por ejemplo:

   ![Opción de Visual Studio Code GIT: Clone](../media/dke-vscode-clone.png)

4. En el cuadro de texto, pegue la dirección URL que copió desde git y seleccione **clonar desde GitHub**.

5. En el cuadro de diálogo **Seleccionar carpeta** que aparece, busque y seleccione una ubicación para almacenar el repositorio. En el símbolo del sistema, seleccione **abrir**.

    El repositorio se abre en Visual Studio Code y muestra la rama git actual en la parte inferior izquierda. La rama debe ser **maestra**.

    Por ejemplo:

   ![Rama de patrón de Visual Studio Code](../media/dke-vscode-master.png)

6. Seleccione el **patrón** de palabras de la lista de ramas.

   > [!IMPORTANT]
   > La selección de la rama maestra garantiza que tenga los archivos correctos para compilar el proyecto. Si no elige la rama correcta, se producirá un error en la implementación.

Ahora tiene su repositorio de origen de DKE configurado de forma local. A continuación, [modifique la configuración](#modify-application-settings) de la aplicación para su organización.

### <a name="modify-application-settings"></a>Modificación de la configuración de la aplicación

Para implementar el servicio DKE, debe modificar los siguientes tipos de configuración de aplicación:

- [Configuración de acceso a claves](#key-access-settings)
- [Configuración de inquilinos y claves](#tenant-and-key-settings)

Modifique la configuración de la aplicación en el appsettings.jsarchivo. Este archivo se encuentra en el repositorio de DoubleKeyEncryptionService que clonó localmente en DoubleKeyEncryptionService\src\customer-key-store. Por ejemplo, en Visual Studio Code, puede desplazarse hasta el archivo como se muestra en la siguiente imagen.

![Buscar el appsettings.jsen el archivo para DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>Configuración de acceso a claves

Elija si desea usar el correo electrónico o la autorización de roles. DKE solo admite uno de estos métodos de autenticación a la vez.

- **Autorización de correo electrónico**. Permite a su organización autorizar el acceso a claves basadas solo en direcciones de correo electrónico.

- **Autorización de roles**. Permite a su organización autorizar el acceso a las claves en función de los grupos de Active Directory y requiere que el servicio Web pueda consultar LDAP.

**Para establecer la configuración de acceso clave para DKE mediante autorización de correo electrónico**

1. Abra el **appsettings.jsen** archivo y busque la `AuthorizedEmailAddress` configuración.

2. Agregue las direcciones o direcciones de correo electrónico que quiera autorizar. Separe varias direcciones de correo electrónico con comillas dobles y comas. Por ejemplo:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Busque la `LDAPPath` configuración y quite el texto `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` comprendido entre las comillas dobles. Deje las comillas dobles en su posición. Cuando haya terminado, la configuración debería ser similar a la siguiente.

   ```json
   "LDAPPath": ""
   ```

4. Busque la `AuthorizedRoles` configuración y elimine la línea completa.

Esta imagen muestra la **appsettings.jsen** un archivo con el formato correcto para la autorización de correo electrónico.

   ![El appsettings.jsen archivo que muestra el método de autorización de correo electrónico](../media/dke-email-accesssetting.png)

**Para establecer la configuración de acceso clave de DKE mediante la autorización de roles**

1. Abra el **appsettings.jsen** archivo y busque la `AuthorizedRoles` configuración.

2. Agregue los nombres de grupo de Active Directory que desea autorizar. Separe varios nombres de grupo con comillas dobles y comas. Por ejemplo:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Busque la `LDAPPath` opción y agregue el dominio de Active Directory. Por ejemplo:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Busque la `AuthorizedEmailAddress` configuración y elimine la línea completa.

Esta imagen muestra la **appsettings.jsen** un archivo con el formato correcto para la autorización de rol.

   ![appsettings.jsen el archivo que muestra el método de autorización de roles](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>Configuración de inquilinos y claves

La configuración de clave y de inquilino de DKE se encuentra en el **appsettings.jsen** el archivo.

**Para establecer la configuración de inquilinos y claves para DKE**

1. Abra el **appsettings.jsen** el archivo.

2. Busque la `ValidIssuers` configuración y sustitúyala `<tenantid>` por el identificador de inquilino. Puede encontrar el identificador de inquilino en el portal de Azure y ver las [propiedades del espacio](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)empresarial. Por ejemplo:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

Busque el `JwtAudience` . Reemplace `<yourhostname>` por el nombre de host del equipo en el que se ejecutará el servicio DKE. Por ejemplo:

  > [!IMPORTANT]
  > El valor de `JwtAudience` debe coincidir *exactamente* con el nombre de su host. Puede usar **localhost: 5001** durante la depuración. Sin embargo, cuando haya terminado la depuración, asegúrese de actualizar este valor al nombre de host del servidor.

- `TestKeys:Name`. Escriba un nombre para la clave. Por ejemplo: `TestKey1`
- `TestKeys:Id`. Cree un GUID y escríbalo como el `TestKeys:ID` valor. Por ejemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. Puede usar un sitio como el [generador de GUID en línea](https://guidgenerator.com/) para generar un GUID de forma aleatoria.

Esta imagen muestra el formato correcto para la configuración de inquilinos y claves de **appsettings.js**. `LDAPPath` está configurado para la autorización de roles.

![Muestra los valores correctos de las claves y los inquilinos para DKE en el appsettings.jsen el archivo.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>Generar claves de prueba

Una vez que haya definido la configuración de la aplicación, estará listo para generar claves de prueba públicas y privadas.

Para generar claves:

1. En el menú Inicio de Windows, ejecute el símbolo del sistema de OpenSSL.

2. Cambie a la carpeta en la que desea guardar las claves de prueba. Los archivos que crea al completar los pasos de esta tarea se almacenan en la misma carpeta.

3. Generar la nueva clave de prueba.

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. Generar la clave privada.

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. Generar la clave pública.

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. En un editor de texto, Abra **pubkeyonly. pem**. Copie todo el contenido del archivo **pubkeyonly. pem** , excepto la primera y la última línea, en la `PublicPem` sección de la **appsettings.jsen** el archivo.

7. En un editor de texto, Abra **privkeynopass. pem**. Copie todo el contenido del archivo **privkeynopass. pem** , excepto la primera y la última línea, en la `PrivatePem` sección de la **appsettings.jsen** el archivo.

8. Quite todos los espacios en blanco y las nuevas líneas en las `PublicPem` `PrivatePem` secciones y.

    > [!IMPORTANT]
    > Cuando copie este contenido, no elimine ninguno de los datos del PEM.

9. En Visual Studio Code, vaya al archivo **Startup.CS** . Este archivo se encuentra en el repositorio de DoubleKeyEncryptionService que clonó localmente en DoubleKeyEncryptionService\src\customer-key-store\.

10. Busque las siguientes líneas:

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. Reemplace estas líneas con el texto siguiente:

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   Los resultados finales deben ser similares a los siguientes.

   ![archivo startup.cs para la versión preliminar pública](../media/dke-startupcs-usetestkeys.png)

Ahora está listo para [compilar el proyecto DKE](#build-the-project).

### <a name="build-the-project"></a>Compile el proyecto.

Use las siguientes instrucciones para crear el proyecto DKE de forma local:

1. En Visual Studio Code, en el repositorio del servicio DKE, seleccione **Ver** \> **paleta de comandos** y, a continuación, escriba **generar** en el símbolo del sistema.

2. En la lista, elija **tareas: Ejecutar tarea de compilación**.

   Si no se encuentra ninguna tarea de compilación, seleccione **Configurar tarea de compilación** y cree una para .net Core de la siguiente manera.

   ![Configurar la tarea de compilación que falta para .NET](../media/dke-configurebuildtask.png)

   1. Elija **crear tasks.jsen a partir de plantilla**.

      ![Crear tasks.jsen archivo de plantilla para DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. En la lista de tipos de plantilla, seleccione **.net Core**.

      ![Seleccione la plantilla correcta para DKE](../media/dke-tasksjsontemplate.png)

   3. En la sección generar, busque la ruta de acceso al archivo **customerkeystore. csproj** . Si no está ahí, agregue la siguiente línea:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. Vuelva a ejecutar la compilación.

3. Compruebe que no haya errores rojos en la ventana de salida.

   Si hay errores rojos, compruebe el resultado de la consola. Asegúrese de que ha completado todos los pasos anteriores correctamente y de que las versiones de compilación correctas están presentes.

4. Seleccione **Ejecutar** \> la **depuración de inicio** para depurar el proceso. Si se le pide que seleccione un entorno, seleccione **.net Core**.

El depurador de .NET Core se inicia normalmente en `https://localhost:5001` . Para ver la clave de prueba, vaya a `https://localhost:5001` y anexe una barra diagonal (/) y el nombre de la clave. Por ejemplo:

```https
https://localhost:5001/TestKey1
```

La clave debe mostrarse en formato JSON.

La configuración se ha completado. Antes de publicar el almacén de claves, en appsettings.jsen la configuración de JwtAudience, asegúrese de que el valor para hostname coincide exactamente con el nombre de host del servicio de la aplicación. Puede que lo haya cambiado a localhost para solucionar los problemas de la compilación.

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>Implementar el servicio DKE y publicar el almacén de claves

Para las implementaciones de producción, implemente el servicio en una nube de terceros o [publíquelo en un sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).

Puede que prefiera otros métodos para implementar las claves. Seleccione el método que mejor se adapte a su organización.

Para las implementaciones piloto, puede implementar en Azure y comenzar inmediatamente.

**Para crear una instancia de la aplicación Web de Azure para hospedar la implementación de DKE**

Para publicar el almacén de claves, debe crear una instancia de Azure App Service para hospedar la implementación de DKE. A continuación, publicará las claves generadas en Azure.

1. En el explorador, inicie sesión en el [portal de Microsoft Azure](https://ms.portal.azure.com)y vaya a **App Services**  >  **Add**.

2. Seleccione su suscripción y grupo de recursos y defina los detalles de la instancia.

    - Escriba el nombre de host del equipo en el que desea instalar el servicio DKE. Asegúrese de que es el mismo nombre que el definido para la configuración JwtAudience en el [**appsettings.jsen**](#tenant-and-key-settings) el archivo. El valor que se proporciona para el nombre también es WebAppInstanceName.

    - Para **publicar**, seleccionar **código** y, para **pila en tiempo de ejecución**, seleccione **.net Core 3,1**.

    Por ejemplo:

   ![Agregar el servicio de aplicaciones](../media/dke-azure-add-app-service.png)

3. En la parte inferior de la página, seleccione **revisar + crear** y, a continuación, seleccione **Agregar**.

4. Realice una de las siguientes acciones para publicar las claves generadas:

    - [Publicar a través de ZipDeployUI](#publish-via-zipdeployui)
    - [Publicar mediante FTP](#publish-via-ftp)
    - [Publicar a través de Visual Studio 2019 o versiones posteriores](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>Publicar a través de ZipDeployUI

1. Vaya a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

    Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. En el código base del almacén de claves, vaya a la carpeta **Customer-Key-store\src\customer-Key-Store** y compruebe que esta carpeta contiene el archivo **customerkeystore. csproj** .

3. Ejecutar: **publicación dotnet**

     La ventana resultados muestra el directorio en el que se ha implementado la publicación.

    Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. Enviar todos los archivos del directorio de publicación a un archivo. zip. Al crear el archivo. zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del archivo. zip.

5. Arrastre y coloque el archivo. zip que ha creado en el sitio de ZipDeployUI que ha abierto anteriormente. Por ejemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE está implementado y puede ir a las claves de prueba que ha creado. Siga [validando la implementación](#validate-your-deployment) a continuación.

#### <a name="publish-via-ftp"></a>Publicar mediante FTP

1. Conéctese al App Service que creó [anteriormente](#deploy-the-dke-service-and-publish-the-key-store).

    En el explorador, vaya a: **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **manual de implementación** de  >  **FTP**  >  .

2. Copie las cadenas de conexión que se muestran en un archivo local. Usaremos estas cadenas para conectar con el servicio de la aplicación web y cargar archivos a través de FTP.

    Por ejemplo:

   ![Copiar cadenas de conexión del panel FTP](../media/dke-ftp-dashboard.png)

3. En el código base para el almacenamiento de claves, vaya al **directorio Customer-Key-store\src\customer-Key-Store**.

4. Compruebe que este directorio contiene el archivo **customerkeystore. csproj** .

5. Ejecutar: **publicación dotnet**

    El resultado contiene el directorio en el que se ha implementado la publicación.

    Por ejemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. Enviar todos los archivos del directorio de publicación a un archivo zip. Al crear el archivo. zip, asegúrese de que todos los archivos del directorio se encuentran en el nivel raíz del archivo. zip.

7. Desde el cliente FTP, use la información de conexión que copió para conectarse a su servicio de aplicaciones. Cargue el archivo. zip que creó en el paso anterior en el directorio raíz de la aplicación Web.

DKE está implementado y puede desplazarse a las claves de prueba que ha creado. A continuación, [valide la implementación](#validate-your-deployment).

### <a name="validate-your-deployment"></a>Validar la implementación

Después de implementar DKE con uno de los métodos descritos anteriormente, valide la implementación y la configuración del almacén de claves.

Realizar

src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey

Por ejemplo:

key_store_tester.ps1 https://mydkeservice.com/mykey

Asegúrese de que no aparecen errores en el resultado. Cuando esté listo, [Registre el almacén de claves](#register-your-key-store).

## <a name="register-your-key-store"></a>Registrar el almacén de claves

Los siguientes pasos le permiten registrar el servicio de DKE. El registro del servicio DKE es el último paso en la implementación de DKE para poder empezar a crear etiquetas.

Para registrar el servicio DKE:

1. En el explorador, abra el [portal de Microsoft Azure](https://ms.portal.azure.com/)y vaya a **todos los** registros de la aplicación de \> **identidad** de servicios \> .

2. Seleccione **nuevo registro** y escriba un nombre significativo.

3. Seleccione un tipo de cuenta en las opciones que se muestran.

    Si está usando Microsoft Azure con un dominio no personalizado, como **onmicrosoft.com**, seleccione **cuentas solo en este directorio de organización (solo para el inquilino único de Microsoft).**

    Por ejemplo:

   ![Nuevo registro de la aplicación](../media/dke-app-registration.png)

4. En la parte inferior de la página, seleccione **registrar** para crear el nuevo registro de la aplicación.

5. En el registro de la nueva aplicación, en el panel izquierdo, en **administrar**, seleccione **autenticación**.

6. Seleccione **Agregar una plataforma**.

7. En el menú emergente **configurar plataformas** , seleccione **Web**.

8. En **URI de redireccionamiento**, escriba el URI del servicio de cifrado de doble clave. Escriba la dirección URL del servicio de aplicaciones, incluidos el nombre de host y el dominio.

    Por ejemplo: https://mydkeservicetest.com

    - La dirección URL que especifique debe coincidir con el nombre de host en el que está implementado el servicio de DKE.
    - Si está probando localmente con Visual Studio, use **https://localhost:5001** .
    - En todos los casos, el esquema debe ser **https**.

    Asegúrese de que el nombre de host coincida exactamente con el nombre de host del servicio de aplicaciones. Puede que lo haya cambiado a `localhost` para solucionar los problemas de la compilación. En **appsettings.jsactivado**, este valor es el nombre de host que se establece para `JwtAudience` .

9. En **concesión implícita**, active la casilla de verificación **tokens de identificador** .

10. Seleccione **Guardar** para guardar los cambios.

11. En el panel izquierdo, seleccione **exponer una API** y, a continuación, junto a URI de identificador de aplicación, seleccione **establecer**.

12. Aún en la página **exponer una API** , en el área **ámbitos definidos por esta API** , seleccione **Agregar un ámbito**. En el nuevo ámbito:

    1. Defina el nombre del ámbito como **user_impersonation**.

    2. Seleccione a los administradores y usuarios que pueden conceder consentimiento.

    3. Defina los valores restantes necesarios.

    4. Seleccione **Agregar ámbito**.

    5. Seleccione **Guardar** en la parte superior para guardar los cambios.

13. Aún en la página **exponer una API** , en el área **aplicaciones cliente autorizadas** , seleccione **Agregar una aplicación cliente**.

    En la nueva aplicación cliente:

    1. Defina el identificador de cliente como **d3590ed6-52b3-4102-AEFF-aad2292ab01c**. Este valor es el identificador del cliente de Microsoft Office y permite a Office obtener un token de acceso para su almacén de claves.

    2. En **ámbitos autorizados**, seleccione el ámbito de la **user_impersonation** .

    3. Seleccione **Agregar aplicación**.

    4. Seleccione **Guardar** en la parte superior para guardar los cambios.

El servicio de DKE se ha registrado. Para continuar, [cree etiquetas con DKE](#create-sensitivity-labels-using-dke).

## <a name="create-sensitivity-labels-using-dke"></a>Crear etiquetas de confidencialidad mediante DKE

En el centro de cumplimiento de Microsoft 365, cree una nueva etiqueta de confidencialidad y aplique el cifrado como lo haría en otro caso. Seleccione **usar cifrado doble de clave** y escriba la dirección URL del punto de conexión para la clave.

Por ejemplo:

![Seleccione usar el cifrado de doble clave en el centro de cumplimiento de Microsoft 365](../media/dke-use-dke.png)

Las etiquetas de DKE que agregue empezarán a aparecer para los usuarios en las versiones más recientes de las aplicaciones de Microsoft 365 para empresas.

> [!NOTE]
> Los clientes pueden tardar hasta 24 horas en actualizarse con las nuevas etiquetas.

### <a name="enable-dke-in-your-client"></a>Habilitar DKE en el cliente

Si es Office Insider, DKE está habilitado para usted. De lo contrario, habilite DKE para el cliente agregando las siguientes claves del registro:

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>Migrar archivos protegidos desde etiquetas HYOK a etiquetas DKE

Si quiere, una vez que haya finalizado la configuración de DKE, puede migrar el contenido que ha protegido mediante etiquetas HYOK a etiquetas de DKE. Para realizar la migración, debe usar el analizador de AIP. Para empezar a usar el escáner, vea [¿Qué es el escáner de etiquetado Unificado de Azure Information Protection?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).

Si no migra contenido, el contenido protegido HYOK no se verá afectado.
