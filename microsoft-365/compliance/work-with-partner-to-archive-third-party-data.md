---
title: Trabajar con un socio para archivar datos de terceros
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
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo configurar un conector personalizado para importar datos de terceros desde orígenes de datos como Salesforce Chatter, Yahoo Messenger o Yammer.
ms.openlocfilehash: 2026e3c584cb0bc467a2db3903c51b7ed50e51e1
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228764"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>Trabajar con un socio para archivar datos de terceros

Puede trabajar con un partner de Microsoft para importar y archivar datos de un origen de datos de terceros para Microsoft 365. Un partner puede proporcionarle un conector personalizado que esté configurado para extraer elementos del origen de datos de terceros (de forma regular) y, a continuación, importar esos elementos. El conector de asociado convierte el contenido de un elemento del origen de datos a un formato de mensaje de correo electrónico y, a continuación, almacena los elementos en buzones. Después de importar datos de terceros, puede aplicar Microsoft 365 las características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, archivado de In-Place, auditoría y Microsoft 365 directivas de retención a estos datos.

> [!IMPORTANT]
> La [solución de cumplimiento](communication-compliance.md) de Microsoft 365 no se puede aplicar a los datos de terceros importados por los conectores asociados mencionados en este artículo.

A continuación se ofrece información general sobre el proceso y los pasos necesarios para trabajar con un partner de Microsoft para importar datos de terceros.

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Paso 2: Crear y configurar un buzón de datos de terceros](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[Paso 4: Proporcionar información al asociado](#step-4-provide-your-partner-with-information)

[Paso 5: Registrar el conector de datos de terceros en Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>Cómo funciona el proceso de importación de datos de terceros

En la siguiente ilustración y descripción se explica cómo funciona el proceso de importación de datos de terceros al trabajar con un partner.

![Cómo funciona el proceso de importación de datos de terceros](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)

1. El cliente trabaja con su partner de elección para configurar un conector que extraerá elementos del origen de datos de terceros y, a continuación, importará esos elementos a Microsoft 365.

2. El conector de partners se conecta a orígenes de datos de terceros a través de una API de terceros (de forma programada o configurada) y extrae elementos del origen de datos. El conector asociado convierte el contenido de un elemento en un formato de mensaje de correo electrónico. Vea la [sección Más información](#more-information) para obtener una descripción del esquema de formato de mensaje.

3. El conector de partners se conecta al servicio de Azure en Microsoft 365 mediante Exchange Web Service (EWS) a través de un punto final conocido.

4. Los elementos se importan al buzón de un usuario específico o a un buzón global de datos de terceros. Que un elemento se importe al buzón de un usuario específico o al buzón de datos de terceros depende de los criterios siguientes:

   1. **Elementos que tienen un identificador de usuario que corresponde a una cuenta de usuario:** Si el conector de asociado puede asignar el identificador de usuario del elemento del origen de datos de terceros a un identificador de usuario específico de Microsoft 365, el elemento se copia en la carpeta **Purgas** de la carpeta Elementos recuperables del usuario. Los usuarios no pueden acceder a los elementos de esta carpeta. Sin embargo, puede usar herramientas de exhibición de documentos electrónicos para buscar elementos en la carpeta Purgas.

   1. **Elementos que no tienen un identificador de usuario que corresponda a una cuenta de usuario:** Si el conector de asociado no puede asignar el identificador de usuario de un elemento a un identificador de usuario específico, el elemento se copia en la carpeta **Bandeja** de entrada del buzón de datos de terceros. La importación de elementos a la Bandeja de entrada permite que usted u otra persona de la organización inicie sesión en el buzón de correo de terceros para ver y administrar estos elementos, y ver si es necesario realizar ajustes en la configuración del conector asociado.

## <a name="step-1-find-a-third-party-data-partner"></a>Paso 1: Buscar un asociado de datos de terceros

Un componente clave para archivar datos de terceros en Microsoft 365 es buscar y trabajar con un partner de Microsoft especializado en capturar datos de un origen de datos de terceros e importarlos a Microsoft 365. Después de importar los datos, se pueden archivar y conservar junto con otros datos de Microsoft de la organización, como el correo electrónico de Exchange y documentos de SharePoint y OneDrive para la Empresa. Un partner crea un conector que extrae datos de orígenes de datos de terceros de la organización (como BlackBerry, Facebook, Google+, Thomson Reuters, Twitter y YouTube) y pasa esos datos a una API de Microsoft 365 que importa elementos Exchange buzones de correo como mensajes de correo electrónico.

En las secciones siguientes se enumeran los partners de Microsoft (y los orígenes de datos de terceros que admiten) que participan en el programa para archivar datos de terceros en Microsoft 365.

[17a-4 LLC](#17a-4-llc)

[ArchiveSocial](#archivesocial)

[Veritas](#veritas)

[OpenText](#opentext)

[Smarsh](#smarsh)

[Verba](#verba)

### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC](https://www.17a-4.com) admite los siguientes orígenes de datos de terceros:

- BlackBerry

- Secuencias de datos de Bloomberg

- Cisco Jabber

- FactSet

- HipChat

- InvestEdge

- LivePerson

- Secuencias de datos de MessageLabs

- OpenText

- Ayuda de Hacer clic para llamar de Oracle/ATG Live

- Pivot IMTRADER

- Microsoft SharePoint

- MindAlign

- Sitrion One (Newsgator)

- Skype Empresarial (Lync/OCS)

- Skype Empresarial Online (Lync Online)

- Bases de datos SQL

- Squawker

- Thomson Reuters Eikon Messenger

### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial](https://www.archivesocial.com) admite los siguientes orígenes de datos de terceros:

- Facebook

- Flickr

- Instagram

- LinkedIn

- Pinterest

- Twitter

- YouTube

- Vimeo

### <a name="veritas"></a>Veritas

[Veritas](https://www.globanet.com) admite los siguientes orígenes de datos de terceros:

- AOL con cliente Pivot

- Registros de llamadas de BlackBerry (v5, v10, v12)

- BlackBerry Messenger (v5, v10, v12)

- BlackBerry PIN (v5, v10, v12)

- BlackBerry SMS (v5, v10, v12)

- Bloomberg Chat

- Bloomberg Mail

- Box

- CipherCloud para Salesforce Chatter

- Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- Archivos de texto delimitados de forma personalizada

- Archivos XML personalizados

- Facebook (páginas)

- Factset

- FXConnect

- ICE Chat/YellowJacket

- Jive

- Macgregor XIP

- Microsoft Exchange Server

- Microsoft OneDrive para la Empresa

- Microsoft Teams

- Microsoft Yammer

- Mobile Guard

- Documento principal

- Salesforce Chatter

- Skype Empresarial Online

- Skype Empresarial, versiones 2007 R2 - 2016 (local)

- Slack Enterprise Grid

- Symphony

- Thomson Reuters Eikon

- Thomson Reuters Messenger

- Thomson Reuters Dealings 3000 / FX Trading

- Twitter

- UBS Chat

- YouTube

### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) admite los siguientes orígenes de datos de terceros:

- Axs Encrypted

- Axs Exchange

- Axs Local Archive

- Axs PlaceHolder

- Axs Signed

- Bloomberg

- Thomson Reuters

### <a name="smarsh"></a>Smarsh

[Smarsh admite](https://www.smarsh.com) los siguientes orígenes de datos de terceros:

- AIM

- American Idol

- Apple Juice

- AOL con cliente Pivot

- Ares

- Bazaar Voice

- Bear Share

- Bit Torrent

- Registros de llamadas de BlackBerry (v5, v10, v12)

- BlackBerry Messenger (v5, v10, v12)

- BlackBerry PIN (v5, v10, v12)

- BlackBerry SMS (v5, v10, v12)

- Bloomberg Mail

- CellTrust

- Importación de chat

- Directiva y registro en tiempo real de chat

- Chatter

- Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)

- Servidor de presencia unificada de Cisco (v8.6.3, v8.6.4, v8.6.5)

- Importación de colaboración

- Registro de colaboración en tiempo real

- Conexión directa

- Facebook

- FactSet

- FastTrack

- Gnutella

- Google+

- GoToMyPC

- Hopster

- HubConnex

- IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)

- IBM Connections Chat Cloud

- IBM Connections Social Cloud

- IBM SameTime Advanced 8.5.2 IFR1

- IBM SameTime Communicate 9.0

- IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)

- IBM SameTime Complete 9.0

- IBM SameTime Conference 9.0

- IBM SameTime Meeting 8.5.2 IFR1

- ICE/YellowJacket

- Importación de mensajería instantánea

- Directiva y registro de mensajería instantánea en tiempo real

- Indii Messenger

- Instant Bloomberg

- IRC

- Jive

- Jive 6 Real Time Logging (v6, v7)

- Jive Import

- JXTA

- LinkedIn

- Microsoft Lync (2010, 2013)

- MFTP

- Microsoft Lync 2013 Voice

- Microsoft SharePoint (2010, 2013)

- Microsoft SharePoint Online

- Microsoft UC (Unified Communications)

- MindAlign

- Mobile Guard

- MSN

- My Space

- NEONetwork

- Microsoft 365 Dedicado a Lync

- Microsoft 365 Mensajería instantánea compartida

- Pinterest

- Documento principal

- QQ

- Skype Empresarial 2015

- SoftEther

- Symphony

- Thomson Reuters Eikon

- Thomson Reuters Messenger

- Tor

- TTT

- Twitter

- WinMX

- Winny

- Yahoo

- Yammer

- YouTube


### <a name="verba"></a>Verba

[Verba admite](https://www.verba.com) los siguientes orígenes de datos de terceros:

- Avaya Aura Video

- Avaya Aura Voice

- Avtec Radio

- Bosch/Telex Radio

- BroadSoft Video

- BroadSoft Voice

- Centile Voice

- Cisco Jabber IM

- Cisco UC Video

- Cisco UC Voice

- Vídeo de Cisco UCCX/UCCE

- Cisco UCCX/UCCE Voice

- ESChat Radio

- Geoman Contact Expert

- IP Trade Voice

- Centro de contacto de Luware LUCS

- Microsoft UC (Unified Communications)

- Mitel MiContact Center for Lync (prairieFyre)

- Vídeo de controlador de borde de sesión de paquete Oracle/Acme

- Voz de controlador de borde de sesión de paquete Oracle/Acme

- Singtel Mobile Voice

- SIPREC Video

-  SIPREC Voice

- Skype Empresarial/MI de Lync

- Skype Empresarial/Vídeo de Lync

- Skype Empresarial/Voz de Lync

- Speakerbus Voice

- Standard SIP/H.323 Video

- Standard SIP/H.323 Voice

- Truphone Voice

- TwistedPair Radio

- Pantalla de equipo de escritorio de Windows

## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>Paso 2: Crear y configurar un buzón de datos de terceros en Microsoft 365

Estos son los pasos para crear y configurar un buzón de datos de terceros para importar datos a Microsoft 365. Como se explicó anteriormente, los elementos se importan a este buzón si el conector de asociado no puede asignar el identificador de usuario del elemento a una cuenta de usuario.

 **Complete estas tareas en el Centro de administración de Microsoft 365**

1. Cree una cuenta de usuario y asígnele una licencia Exchange Online plan 2; vea [Agregar usuarios a Microsoft 365](../admin/add-users/add-users.md). Se requiere una licencia del plan 2 para colocar el buzón en retención por juicio o habilitar un buzón de archivo que tenga una cuota de almacenamiento ilimitada.

2. Agregue la cuenta de usuario del buzón de datos de terceros al rol de administrador Exchange **de** administrador en Microsoft 365; vea [Asignar roles de administrador en Microsoft 365](../admin/add-users/assign-admin-roles.md).

    > [!TIP]
    > Escriba las credenciales para esta cuenta de usuario. Necesitará proporcionárselas a su socio, tal como se describe en el paso 4.

 **Complete estas tareas en el Centro Exchange administración**

1. Ocultar el buzón de datos de terceros de la libreta de direcciones y otras listas de direcciones de la organización; vea [Administrar buzones de usuario](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes). Como alternativa, puede ejecutar el siguiente comando de PowerShell:

    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Asigne el **permiso FullAccess** al buzón de datos de terceros para que los administradores o responsables de cumplimiento puedan abrir el buzón de datos de terceros en el Outlook de escritorio; vea [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).

3. Habilite las siguientes características relacionadas con el cumplimiento para el buzón de datos de terceros:

    - Habilitar el buzón de archivo; vea [Habilitar buzones de archivo](enable-archive-mailboxes.md) y Habilitar archivado [ilimitado.](enable-unlimited-archiving.md) Esto le permite liberar espacio de almacenamiento en el buzón principal configurando una directiva de archivo que mueve elementos de datos de terceros al buzón de archivo. Esto le proporciona almacenamiento ilimitado para datos de terceros.

    - Coloque el buzón de datos de la tercera persona en retención por juicio. También puede aplicar una directiva de Microsoft 365 de retención en el Centro de seguridad y cumplimiento. Al colocar este buzón en espera, se conservan los elementos de datos de terceros (de forma indefinida o durante una duración especificada) y se evita que se purguen del buzón. Vea uno de los siguientes temas:

      - [Poner un buzón en retención por juicio](./create-a-litigation-hold.md)

      - [Más información sobre las directivas y las etiquetas de retención](retention.md)

    - Habilitar el registro de auditoría de buzones de correo para el acceso de propietario, delegado y administrador al buzón de datos de terceros; vea [Enable mailbox auditing](enable-mailbox-auditing.md). Esto le permite auditar toda la actividad realizada por cualquier usuario que tenga acceso al buzón de datos de terceros.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Paso 3: Configurar los buzones de usuario para los datos de terceros

El paso siguiente es configurar los buzones de usuario para que admitan los datos de terceros. Complete estas tareas mediante el centro Exchange administración o mediante el uso de los cmdlets Windows PowerShell correspondientes.

1. Habilitar el buzón de archivo para cada usuario; vea [Habilitar buzones de archivo](enable-archive-mailboxes.md) y Habilitar archivado [ilimitado.](enable-unlimited-archiving.md)

2. Colocar buzones de usuario en retención por juicio o aplicar una Microsoft 365 de retención; vea uno de los siguientes temas:

    - [Poner un buzón en retención por juicio](./create-a-litigation-hold.md)

    - [Más información sobre las directivas y las etiquetas de retención](retention.md)

    Como ya se ha indicado, al poner los buzones en retención, puede determinar durante cuánto tiempo deben retenerse los elementos del origen de datos de terceros o puede optar por retener los elementos indefinidamente.

## <a name="step-4-provide-your-partner-with-information"></a>Paso 4: Proporcionar información al asociado

El paso final es proporcionar a su partner la siguiente información para que pueda configurar el conector para conectarse a su organización para importar datos a buzones de usuario y al buzón de datos de terceros.

- El punto de conexión que se usa para conectarse al servicio de Azure en Microsoft 365:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- Las credenciales de inicio de sesión (Microsoft 365 de usuario y contraseña) del buzón de datos de terceros que creó en el paso 2. Estas credenciales son necesarias para que el conector asociado pueda tener acceso e importar elementos a los buzones de usuario y al buzón de datos de un tercero.

## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Paso 5: Registrar el conector de datos de terceros en Azure Active Directory

A partir del 30 de septiembre de 2018, el servicio azure en Microsoft 365 empezará a usar la autenticación moderna en Exchange Online para autenticar conectores de datos de terceros que intenten conectarse a su organización para importar datos. El motivo de este cambio es que la autenticación moderna proporciona más seguridad que el método actual, que se basaba en una lista de permitidos para conectores de terceros que usan el extremo descrito anteriormente para conectarse al servicio de Azure.

Para permitir que un conector de datos de terceros se conecte a Microsoft 365 mediante el nuevo método de autenticación moderno, un administrador de la organización debe dar su consentimiento para registrar el conector como una aplicación de servicio de confianza en Azure Active Directory. Para ello, acepta una solicitud de permiso para permitir que el conector tenga acceso a los datos de la organización en Azure Active Directory. Después de aceptar esta solicitud, el conector de datos de terceros se agrega como una aplicación de empresa a Azure Active Directory y se representa como una entidad de servicio. Para obtener más información sobre el proceso de consentimiento, vea  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).

Estos son los pasos para obtener acceso y aceptar la solicitud para registrar el conector:

1. Vaya a [esta página e](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) inicie sesión con las credenciales de un administrador global.

   Se muestra el siguiente cuadro de diálogo. Puede expandir los carets para revisar los permisos que se asignarán al conector.

   ![Se muestra el cuadro de diálogo solicitud de permisos](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. Haga clic en **Aceptar**.

Después de aceptar la solicitud, se muestra [Azure Portal.](https://portal.azure.com) Para ver la lista de aplicaciones de su organización, haga clic **Azure Active Directory**  >  **Enterprise aplicaciones**. El Microsoft 365 de datos de terceros aparece en la **hoja Enterprise aplicaciones.**

> [!IMPORTANT]
> Después del 30 de septiembre de 2018, los datos de terceros ya no se importarán en buzones de la organización si no registra un conector de datos de terceros en Azure Active Directory. Tenga en cuenta que los conectores de datos de terceros existentes (los creados antes del 30 de septiembre de 2018) también deben registrarse en Azure Active Directory siguiendo el procedimiento del paso 5.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Revocación del consentimiento para un conector de datos de terceros

Después de que su organización consiente la solicitud de permisos para registrar un conector de datos de terceros en Azure Active Directory, su organización puede revocar ese consentimiento en cualquier momento. Sin embargo, revocar el consentimiento de un conector significa que los datos del origen de datos de terceros ya no se importarán a Microsoft 365.

Para revocar el consentimiento de un conector de datos de terceros, puede eliminar la aplicación (eliminando la entidad de servicio correspondiente) de Azure Active Directory mediante la hoja aplicaciones **de Enterprise** en Azure Portal o mediante el uso de [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) en Microsoft 365 PowerShell. También puede usar el cmdlet [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) en Azure Active Directory PowerShell.

## <a name="more-information"></a>Más información

- Tal como se ha explicado, los elementos de orígenes de datos de terceros se importan a los buzones de Exchange como mensajes de correo electrónico. El conector de asociado importa el elemento mediante un esquema requerido por la API Microsoft 365 usuario. En la tabla siguiente se describen las propiedades del mensaje de un elemento de un origen de datos de terceros después de que este se importe a un buzón de Exchange como un mensaje de correo electrónico. La tabla también indica si la propiedad del mensaje es obligatoria. Las propiedades obligatorias deben rellenarse. Si a un elemento le falta una propiedad obligatoria, no se importará a Microsoft 365. El proceso de importación devuelve un mensaje de error que explica por qué no se importó un elemento y qué propiedad falta.<br/><br/>

    |**Propiedad del mensaje**|**¿Es obligatoria?**|**Descripción**|**Valor de ejemplo**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |Sí  <br/> |El usuario que originalmente ha creado o enviado el elemento en el origen de datos de terceros. El conector de partners intenta asignar el identificador de usuario del elemento de origen (por ejemplo, un identificador de Twitter) a una cuenta de usuario para todos los participantes (usuarios en los campos FROM y TO). Una copia del mensaje se importará al buzón de cada participante. Si ninguno de los participantes del elemento se puede asignar a una cuenta de usuario, el elemento se importará al buzón de archivado de terceros en Microsoft 365.  <br/> <br/> El participante identificado como el remitente del elemento debe tener un buzón activo en la organización a la que se va a importar el elemento. Si el remitente no tiene un buzón activo, se devolverá el siguiente error:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |Sí  <br/> |El usuario que ha recibido un elemento, si es aplicable a un elemento del origen de datos.  <br/> | `bob@contoso.com` <br/> |
    |**Asunto** <br/> |No  <br/> |El asunto del elemento de origen.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |Sí  <br/> |La fecha en que se creó o publicó originalmente el elemento en el origen de datos del cliente. Por ejemplo, la fecha en que se tuiteó un mensaje de Twitter.  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |No  <br/> |El contenido del mensaje o la publicación. En el caso de algunos orígenes de datos, el contenido de esta propiedad podría ser el mismo que el contenido de la propiedad **SUBJECT**. Durante el proceso de importación, el conector de asociado intenta mantener la fidelidad total desde el origen de contenido como sea posible. Si es posible, los archivos, los gráficos u otro contenido del cuerpo del elemento de origen se incluyen en esta propiedad. Si no es así, el contenido del elemento de origen se incluye en la propiedad **ATTACHMENT**. El contenido de esta propiedad depende del conector de asociado y de la funcionalidad de la plataforma de origen.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**DATOS ADJUNTOS** <br/> |No  <br/> |Si un elemento del origen de datos (como un tweet en Twitter o una conversación de mensajería instantánea) tiene un archivo adjunto o incluye imágenes, el partner connect intentará primero incluir datos adjuntos en la **propiedad BODY.** Si no es posible, se agrega a la propiedad ** ATTACHMENT **. Otros ejemplos de datos adjuntos son los "Me gusta" de Facebook, los metadatos del origen del contenido y las respuestas a un mensaje o una publicación.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Sí  <br/> | Se trata de una propiedad de varios valores, que se crea y rellena mediante el conector de asociado. El formato de esta propiedad es  `IPM.NOTE.Source.Event` . (Esta propiedad debe comenzar por  `IPM.NOTE` . Este formato es similar al de la clase  `IPM.NOTE.X` de mensaje). Esta propiedad incluye la siguiente información:  <br/><br/>`Source`: indica el origen de datos de terceros; por ejemplo, Twitter, Facebook o BlackBerry.  <br/> <br/>  `Event`: indica el tipo de actividad que se realizó en el origen de datos de terceros que produjo los elementos; por ejemplo, un tweet en Twitter o una publicación en Facebook. Los eventos son específicos del origen de datos.  <br/> <br/>  Un objetivo de esta propiedad es filtrar elementos específicos en función del origen de datos en el que un elemento se originó o basó, o bien en función del tipo de evento. Por ejemplo, en una búsqueda de exhibición de documentos electrónicos podría crear una consulta de búsqueda para encontrar todos los tweets publicados por un usuario concreto.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |

- Cuando los elementos se importan correctamente a buzones de correo en Microsoft 365, se devuelve un identificador único al autor de la llamada como parte de la respuesta HTTP. Este identificador, denominado , puede usarse para fines de solución de problemas posteriores por parte de los asociados para realizar un seguimiento de un extremo a  `x-IngestionCorrelationID` otro de los elementos. Se recomienda que los asociados capturen esta información y la registren según corresponda en su extremo. A continuación se incluye un ejemplo de una respuesta HTTP que muestra este identificador:

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT
    ```

- Puede usar la herramienta búsqueda de contenido en el Centro de seguridad y cumplimiento para buscar elementos que se importaron a buzones de correo desde un origen de datos de terceros. Para buscar específicamente estos elementos importados, puede usar los siguientes pares de propiedad-valor de mensaje en el cuadro de palabra clave de una búsqueda de contenido.

  - **`kind:externaldata`**: use este par de propiedades y valores para buscar en todos los tipos de datos de terceros. Por ejemplo, para buscar elementos que se importaron desde un origen de datos de terceros y contenían la palabra "contoso" en la propiedad Subject del elemento importado, se usaría la consulta de palabra clave  `kind:externaldata AND subject:contoso` .

  - **`itemclass:ipm.externaldata.<third-party data type>`**: use este par propiedad-valor para buscar solo un tipo de datos de terceros especificado. Por ejemplo, para buscar solo datos de Facebook que contengan la palabra "contoso" en la propiedad Subject, usaría la consulta de palabra clave  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` .

  Para obtener una lista completa de los valores que se usarán para los tipos de datos de terceros para la propiedad, vea `itemclass` Use Content Search to search [third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).

   Para obtener más información sobre cómo usar la búsqueda de contenido y crear consultas de búsqueda de palabras clave, vea:

  - [Búsqueda de contenido](content-search.md)

  - [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).