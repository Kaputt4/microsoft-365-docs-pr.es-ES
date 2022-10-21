---
title: 'Mejora del flujo de correo con MTA-STS '
f1.keywords:
- NOCSH
ms.author: v-bshilpa
author: Benny-54
manager: serdars
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.assetid: ''
ms.collection:
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- highpri
description: Obtenga información sobre cómo mejorar el flujo de correo con MTA-STS.
ms.openlocfilehash: 51ea4595c208ded39c980eee0ad9445383754350
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68663551"
---
# <a name="enhancing-mail-flow-with-mta-sts"></a>Mejora del flujo de correo con MTA-STS

Se agregó compatibilidad con el estándar [SMTP MTA Strict Transport Security](https://datatracker.ietf.org/doc/html/rfc8461) (MTA-STS) a Exchange Online. El estándar se desarrolló para garantizar que siempre se use TLS para las conexiones entre los servidores de correo electrónico. También proporciona una manera de enviar servidores para validar que el servidor receptor tenga un certificado de confianza. Si no se ofrece TLS o el certificado no es válido, el remitente se negará a enviar los mensajes. Estas nuevas comprobaciones mejoran la seguridad general de SMTP y protegen frente a los ataques de tipo "Man in the middle”.

MTA-STS can be broken down into two scenarios: Inbound and Outbound Protection. Inbound covers the protection of domains hosted in Exchange Online with MTA-STS and Outbound covers the MTA-STS validations performed by Exchange Online when sending emails to MTA-STS protected domains.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="outbound-protection"></a>Protección saliente

Todos los mensajes enviados desde Exchange Online a los destinatarios protegidos con MTA-STS se validan con estas comprobaciones de seguridad adicionales establecidas por el estándar MTA-STS. Los administradores no tienen que hacer nada para aplicarlas. Nuestra implementación saliente respeta los deseos de los propietarios del dominio del destinatario a través de su directiva MTA-STS. MTA-STS forma parte de la infraestructura de seguridad de Exchange Online y, por tanto, siempre está activado (así como otras características principales de SMTP).

## <a name="inbound-protection"></a>Protección de entrada

Los propietarios de dominios pueden tomar medidas para proteger los correos electrónicos enviados a sus dominios con MTA-STS si su registro MX apunta a Exchange Online. Si el registro MX apunta a un servicio de terceros intermediario, deberá comprobar que se cumplan los requisitos de MTA-STS y seguir sus instrucciones.

Una vez configurado MTA-STS para su dominio, todos los mensajes enviados desde remitentes que admitan MTA-STS realizarán las validaciones establecidas por el estándar para garantizar una conexión segura. Si recibe un correo electrónico de un remitente que no es compatible con MTA-STS, el correo electrónico se enviará de todas maneras, pero sin la protección adicional. Del mismo modo, no habrá ninguna interrupción en los mensajes si usted aún no está usando MTA-STS pero el remitente sí lo admite. El único escenario en el que los mensajes no se entregan es cuando ambos lados usan MTA-STS y la validación MTA-STS produce un error.

## <a name="how-to-adopt-mta-sts"></a>Adopción de MTA-STS

MTA-STS permite a un dominio declarar la compatibilidad con TLS y comunicar el registro MX y el certificado de destino esperados. También indica lo que debe hacer un servidor de envío si hay un problema. Esta comunicación se realiza a través de una combinación de un registro TXT de DNS y un archivo de directiva que se publica como una página web HTTPS. La directiva protegida con HTTPS introduce otra protección de seguridad que los atacantes deben superar.

El registro TXT MTA-STS de un dominio indica la compatibilidad con MTA-STS para un remitente, tras lo cual el remitente recupera la directiva MTA-STS basada en HTTPS del dominio. El siguiente registro TXT es un ejemplo que declara la compatibilidad con MTA-STS:

`_mta-sts.contoso.com. 3600 IN TXT v=STSv1; id=20220101000000Z;`

La directiva MTA-STS de un dominio debe encontrarse en una dirección URL predefinida hospedada por la infraestructura web del dominio. La sintaxis de la dirección URL es `https://mta-sts.<domain name>/.well-known/mta-sts.txt`. Por ejemplo, la directiva de Microsoft.com se encuentra en: <https://mta-sts.microsoft.com/.well-known/mta-sts.txt>.

```text
version: STSv1
mode: enforce
mx: *.mail.protection.outlook.com
max_age: 604800
```

Cualquier cliente cuyos registros MX apunten directamente a Exchange Online puede especificar en su propia directiva con los mismos valores que se muestran anteriormente en la directiva de microsoft.com. La información única necesaria en la directiva es el registro MX que apunta a Exchange Online (`*`.mail.protection.outlook.com) y todos los clientes Exchange Online comparten el mismo certificado. Exchange Online solo permite que una organización reciba correos electrónicos para un dominio determinado, por lo que el uso de un carácter comodín no debilita la seguridad, pero puede que no sea el caso de otros servicios de correo electrónico. Es posible publicar la directiva en modo *de prueba* para asegurarse de que es válida antes de cambiarla a modo *de aplicación* . Hay herramientas de validación de terceros que pueden comprobar la configuración.

Estas directivas no son algo que Exchange Online pueda hospedar en nombre de los clientes, por lo que los clientes deben configurar la directiva STS de su dominio mediante los servicios que prefieran. Los servicios de Azure se pueden usar fácilmente para el hospedaje de directivas y hay un tutorial de configuración más adelante en este artículo. La directiva debe protegerse mediante HTTPS con un certificado para el subdominio `mta-sts.<domain name>`.

Una vez que se crea el registro TXT de DNS y el archivo de directiva está disponible en la dirección URL HTTPS necesaria, el dominio estará protegido por MTA-STS. Los detalles sobre MTA-STS están disponibles en [RFC 8461](https://datatracker.ietf.org/doc/html/rfc8461).

### <a name="configuring-inbound-mta-sts-with-azure-services"></a>Configuración de MTA-STS de entrada con Azure Services

> [!NOTE]
> Estos flujos de configuración se desarrollaron para ayudar a Microsoft Exchange Online clientes a hospedar su directiva MTA-STS mediante recursos de Azure. Este flujo de configuración supone que es un cliente Exchange Online que es consciente de cómo funciona MTA-STS y sus requisitos. Para obtener más información sobre el protocolo más allá de este tema, vea [RFC8461](https://www.rfc-editor.org/rfc/rfc8461.html).

Hay dos recursos de Azure que se pueden usar para hospedar la directiva MTA-STS: [Azure Static Web App](https://azure.microsoft.com/services/app-service/static/) y [Azure Functions](/azure/azure-functions/functions-overview). Aunque en este artículo se describe cómo implementar la directiva con ambos recursos, el método recomendado es [Azure Static Web App](https://azure.microsoft.com/services/app-service/static/) , ya que está diseñado para hospedar páginas estáticas, como la directiva STS, y Azure simplifica la configuración proporcionando un certificado TLS para la página web MTA-STS de forma inmediata, sin necesidad de más configuración. Si no puede usar [Azure Static Web App](https://azure.microsoft.com/services/app-service/static/), también puede hospedar la directiva como código sin servidor mediante [Azure Functions](/azure/azure-functions/functions-overview). Este enfoque no es el método preferido porque Azure Function es una característica diseñada para otros escenarios y no emite un certificado TLS automáticamente, a diferencia de Azure Static Web Apps. Por lo tanto, el uso [de Azure Functions](/azure/azure-functions/functions-overview) para MTA-STS requiere que emita su propio "mta-sts.[ su dominio]" y enlazarlo a la función.

Independientemente del enfoque que haya adoptado, le recomendamos que valide que la directiva está configurada correctamente y que el tiempo de respuesta es aceptable: el tiempo de espera por instrucciones RFC es de 60 segundos.

Estos flujos de configuración están diseñados para proporcionar solo información técnica sobre las características de Azure que se pueden usar para hospedar la directiva MTA-STS y no proporcionan información sobre los costos o los cargos de las características de Azure. Si quiere conocer los costos de las características de Azure, use la [calculadora de precios de](https://azure.microsoft.com/pricing/calculator/) Azure.

#### <a name="option-1-recommended-azure-static-web-app"></a>Opción 1 (RECOMENDADO): Aplicación web estática de Azure

1. Cree una organización de Azure DevOps o use una organización que ya exista. En este ejemplo, se usará una organización denominada "ContosoCorporation" para hospedar la directiva MTA-STS.

   :::image type="content" source="../media/projects-tab.png" alt-text="Captura de pantalla que muestra la pestaña proyectos." lightbox="../media/projects-tab.png":::

2. En **Repositorios > Archivos**, clone el repositorio en cualquier IDE que prefiera. En este ejemplo, el repositorio se clonará en Visual Studio.

   :::image type="content" source="../media/clone-to-vs-code.png" alt-text="Captura de pantalla que muestra un ejemplo de clonación en Visual Studio Code." lightbox="../media/clone-to-vs-code.png":::

3. Una vez clonado el repositorio, cree la siguiente ruta de acceso de carpeta: `home\.well-known\`. A continuación, cree los siguientes archivos: 

    - Archivo 1:well-known\mta-sts.txt principal\.

   > [!NOTE]
   > Esta configuración solo permite que Exchange Online reciban mensajes en nombre de su dominio. Si usa varios proveedores de correo electrónico, también debe hacer referencia a hosts MX para los dominios de esos otros proveedores. Los caracteres comodín o '*' no se deben usar como prefijo MX en todos los escenarios de MTA-STS; La configuración siguiente es específica de Exchange Online solo y NO debe usarse como guía general para configurar MTA-STS. 

    1. Escriba el texto siguiente en el archivo mta-sts.txt:
        ```powershell
           version: STSv1
           mode: testing
           mx: *.mail.protection.outlook.com
           max_age: 604800
        ```
       > [!NOTE]
       > Se recomienda establecer inicialmente el modo de directiva como "testing". A continuación, al final de la configuración y después de validar que la directiva funciona según lo esperado, actualice el archivo mta-sts.txt de modo que el modo sea "aplicar".
 
       El archivo solo debe contener el contenido como se muestra en la captura de pantalla siguiente:

       :::image type="content" source="../media/contents-of-file1.png" alt-text="Captura de pantalla que muestra el contenido de File1." lightbox="../media/contents-of-file1.png":::

    - Archivo 2: home\index.html
    
    1. Cree un archivo index.html y escriba el código siguiente en él:
    
       ```powershell
           <!DOCTYPE html>
           <html lang="en">

           <head>
           <meta charset="UTF-8">
           <title>MTA-STS</title>
           </head>

           <body>
           <h1>MTA-STS Static Website index</h1>
           </body>

           </html>
       ```
           
      El archivo solo debe contener el contenido como se muestra en la captura de pantalla siguiente:
   
      :::image type="content" source="../media/contents-of-file2.png" alt-text="Captura de pantalla que muestra el contenido de File2." lightbox="../media/contents-of-file2.png":::

      Una vez creada la ruta de acceso de la carpeta y los archivos, no olvide confirmar los cambios e insertarlos en la rama principal.

4. Cree una nueva aplicación web estática de Azure con la siguiente configuración:

    - **Nombre**: MTA-STS-StaticWebApp
    - **Tipo de plan**: Estándar
    - **Detalles de la implementación**: Azure DevOps
    - **Organización**: ContosoCorporation
    - **Proyecto**: MTA-STS_Project
    - **Repositorio**: MTA-STS_Project
    - **Rama**: master
    - **Valores preestablecidos de compilación**: Angular
    - **Ubicación de la aplicación**: /home
   
    :::image type="content" source="../media/new-app-with-details.png" alt-text="Captura de pantalla que muestra una aplicación web estática de Azure recién creada con su información." lightbox="../media/new-app-with-details.png":::

5. Una vez finalizada la creación de la aplicación web estática y aprovisionado el recurso, vaya a **Información general > Administrar token de implementación**; a continuación, copie el token como se usará en el paso siguiente.

6. Vaya a **Canalizaciones > Crear canalización > Azure Repos Git > MTA-STS_Project** y realice las siguientes subtareas:
    1. Vaya a **Variables > Nueva variable** y escriba lo siguiente:
        1. **Nombre**: token
        1. **Valor**: (pegue el token que copió anteriormente)
    1. Una vez guardada la variable, vuelva a **Revisar yaML de la canalización** y pegue el siguiente yml, guárdelo y ejecútelo.
           
       ```powershell
           trigger:
           - main

           pool:
           vmImage: ubuntu-latest

           steps:
           - checkout: self
           submodules: true
           - task: AzureStaticWebApp@0
           inputs:
            app_location: '/home'
            azure_static_web_apps_api_token: $(token)
       ```

       En Azure DevOps, durante la implementación, si experimenta el error **No se ha comprado o concedido ningún paralelismo hospedado**, solicite a través de este [formulario](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR63mUWPlq7NEsFZhkyH8jChUMlM3QzdDMFZOMkVBWU5BWFM3SDI2QlRBSC4u) o implemente una configuración a través **de Configuración de la organización > Trabajos paralelos > Microsoft Hosted > Change > Trabajos paralelos de pago** , de modo que se permitan "Trabajos paralelos de pago".

7. Una vez que el trabajo finaliza correctamente, puede validar la implementación a través de la Azure Portal yendo a **Azure Static Web App > Environment > Browser**. Debe ver el contenido del archivo index.html.

8. Agregue el dominio de vanidad en **Azure Static Web App > Dominios personalizados > Agregar**. Se le pedirá que cree un registro **CNAME** a través de su proveedor dns (por ejemplo, GoDaddy) para validar que la zona le pertenece. Una vez finalizada la validación, Azure emitirá un certificado y lo enlazará a la aplicación web estática automáticamente.

9. Valide que la directiva MTA-STS se publica a través de: https://mta-sts.[ dominio]/.bien conocido/mta-sts.txt.

10. Cree el registro DNS TXT de MTA-STS a través del proveedor dns. El formato es el siguiente:
     
    ```powershell
        Hostname: _mta-sts.<domain name>
        TTL: 3600 (recommended)
        Type: TXT
        Text: v=STSv1; id=<ID unique for your domain’s STS policy>Z;
    ```

    > [!NOTE]
    > Puede encontrar un registro TXT MTA-STS de ejemplo en [Cómo adoptar MTA-STS](#how-to-adopt-mta-sts).

11. Una vez que el registro TXT esté disponible en DNS, valide la configuración de MTA-STS. Una vez validada correctamente la configuración, actualice el archivo mta-sts.txt para que el modo de directiva sea "aplicar"; a continuación, actualice el identificador de directiva en el registro TXT.

#### <a name="option-2-azure-function"></a>Opción 2: Función de Azure

1. Cree una nueva aplicación de funciones de Azure con la siguiente configuración:

    - **Nombre de la aplicación** de función: [Como prefiera]
    - **Publicar**: Código
    - **Pila en tiempo de ejecución**: .NET
    - **Versión**: 6
    - **Sistema operativo**: Windows
    - **Tipo de plan**: [Como prefiera]

    :::image type="content" source="../media/new-azure-function-app.png" alt-text="Captura de pantalla que muestra las configuraciones de una nueva aplicación de funciones de Azure." lightbox="../media/new-azure-function-app.png":::

2. Agregue el dominio personalizado a function app. Tendrá que crear un registro **CNAME** para validar que el dominio le pertenece.

   :::image type="content" source="../media/custom-domain-to-add.png" alt-text="Captura de pantalla que muestra el dominio personalizado que se va a agregar a function app." lightbox="../media/custom-domain-to-add.png":::

3. Enlace el mta-sts. [su dominio] a la aplicación de funciones.

   :::image type="content" source="../media/binding-to-function-app.png" alt-text="Captura de pantalla que muestra el proceso de enlace del dominio a function app." lightbox="../media/binding-to-function-app.png":::

4. En **Archivo de aplicación**, agregue la siguiente extensión al archivo host.json de function app para eliminar routePrefix. Esta adición es necesaria para quitar /api de la dirección URL de la función.
   
    ```powershell
        "extensions": {
    "http": {
      "routePrefix&quot;: &quot;"
      }
    }
    ```

   :::image type="content" source="../media/extension-added-to-app-file.png" alt-text="Captura de pantalla que muestra la extensión que se va a agregar al archivo de aplicación." lightbox="../media/extension-added-to-app-file.png":::

5. En function app, vaya a **Functions > Create (Crear** ) y configure los parámetros siguientes: 

   > [!NOTE]
   > Aunque en este ejemplo se describe el desarrollo de funciones a través del portal, puede usar VS Code o cualquier otra herramienta que prefiera.

    - **Entorno de desarrollo**: [Como prefiera, en este ejemplo se usará "Desarrollar en el portal"]
    - **Seleccionar una plantilla**: desencadenador HTTP
    - **Nueva función**: [Como elija]
    - **Nivel de autorización**: Anónimo

    :::image type="content" source="../media/create-function-screen.png" alt-text="Captura de pantalla que muestra la página Crear función." lightbox="../media/create-function-screen.png":::

6. Una vez creada la función, abra **Código y prueba** y desarrolle en C# una respuesta HTTP asincrónica sencilla que será la directiva MTA-STS. En el ejemplo siguiente se indica que se espera que Exchange Online reciba correos electrónicos:

   > [!NOTE]
   > Se recomienda establecer inicialmente el modo de directiva como "testing". A continuación, al final de la configuración y después de validar que la directiva funciona según lo esperado, actualice el archivo mta-sts.txt de modo que el modo sea "aplicar".

   :::image type="content" source="../media/mta-sts-policy.png" alt-text="Captura de pantalla que muestra la directiva mta-sts desarrollada." lightbox="../media/mta-sts-policy.png":::

7. En **Integration > HTTP (req)**, edite el desencadenador con los valores siguientes:

    - **Plantilla de ruta**: .well-known/mta-sts.txt
    - **Métodos HTTP seleccionados**: GET

    :::image type="content" source="../media/edit-trigger-screen.png" alt-text="Captura de pantalla que muestra la página Editar desencadenador." lightbox="../media/edit-trigger-screen.png":::

8. Valide que la directiva MTA-STS se publica a través de: https://mta-sts.[ dominio]/.bien conocido/mta-sts.txt.

9. Cree el registro DNS TXT de MTA-STS a través del proveedor DNS en el formato siguiente:

     ```powershell
        Hostname: _mta-sts.<domain name>
        TTL: 3600 (recommended)
        Type: TXT
        Text: v=STSv1; id=<ID unique for your domain’s STS policy>Z;
     ```

   > [!NOTE]
   > Puede encontrar un registro TXT MTA-STS de ejemplo en [Cómo adoptar MTA-STS](#how-to-adopt-mta-sts).

10. Una vez que el registro TXT esté disponible en DNS, valide la configuración de MTA-STS. Una vez que la configuración se haya validado correctamente, actualice el archivo mta-sts.txt de modo que el modo de directiva sea "aplicar"; a continuación, actualice el identificador de directiva en el registro TXT.
