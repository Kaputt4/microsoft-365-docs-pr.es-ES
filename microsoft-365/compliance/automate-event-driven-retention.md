---
title: Retención automática controlada por eventos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: En este tema se explica cómo configurar los flujos de procesos empresariales para automatizar la retención mediante eventos con la API de REST de Microsoft 365.
ms.openlocfilehash: c97106597733460caeab8d1d398ff81e23dd2727
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068119"
---
# <a name="automate-event-based-retention"></a>Retención automática basada en eventos

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.

To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.

To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.

Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.

## <a name="about-event-based-retention"></a>Acerca de la retención basada en eventos

An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.

For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:

- **The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.

- **The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.

The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).

## <a name="set-up-event-based-retention"></a>Configuración de la retención basada en eventos

Esta sección describe lo que es necesario realizar antes de retener contenido.

### <a name="identify-roles"></a>Identificación de funciones

Identifica las diferentes funciones en una organización que realizan tareas de administración de registros y son responsables de una retención eficaz y eficiente de los documentos empresariales.

  | Persona | Rol |
  | - | - |
  | Administrador | Crea tipos de eventos de retención, etiquetas de retención y repositorios de registros en SharePoint |
  | Administrador de registros                                  | Proporciona detalles de cumplimiento y guías de políticas de retención y programaciones de retención   |
  | Administrador del sistema (empresa)                          | Configura y administra sistemas externos para que funcionen con Microsoft 365                       |
  | Trabajador de información                               | Administra el ciclo de vida de los procesos de su empresa (Recursos Humanos, Finanzas, TI, etc.)                 |

### <a name="set-up-the-security--compliance-center"></a>Configuración del Centro de seguridad y cumplimiento
  
1. La administración del cumplimiento crea un tipo de evento &ndash; como el final de una relación laboral, la finalización del contrato o el final de fabricación del producto. (Consulte el proceso paso a paso en el artículo [Retención de eventos](event-driven-retention.md)).
    
2. La administración de cumplimiento crea una etiqueta de retención basada en un evento y asocia la etiqueta con un tipo de evento.
    
    Hay 4 tipos de desencadenadores para las etiquetas de retención:
            
    1. Fecha de creación
                
    2. Última modificación
                
    3. Fecha de la etiqueta (cuando se etiquetó el contenido)
                
    4. Basado en eventos
    
3. La administración del cumplimiento publica la etiqueta de retención.

### <a name="set-up-sharepoint"></a>Configurar SharePoint
   
Para crear un repositorio de registros, la administración del cumplimiento:

1. Crea un sitio de SharePoint.

2. Realiza una de las siguientes acciones:
        
   - Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
          
   - Configura un conjunto de documentos en SharePoint. Para más información, vea [Introducción a los conjuntos de documentos](https://support.microsoft.com/es-ES/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).
      
3. Asigna un ID. de activo para cada conjunto de documentos de empleado. Un ID. de activo es el nombre o código de producto usado por la organización. Por ejemplo, el número de empleado puede ser un ID. de activo. Al asignar el ID. de activo a una carpeta, cada elemento de esta carpeta hereda automáticamente el mismo ID. de activo. Esto significa que todos los elementos pueden tener un periodo de retención activado por el mismo evento.

## <a name="ways-to-trigger-event-based-retention"></a>Formas de desencadenar la retención basada en eventos

Existen dos formas de desencadenar la retención basada en eventos:

- **Uso de la interfaz de usuario del Centro de administración** Con este proceso puede retener menos contenido a la vez, o bien, la frecuencia de activación de la retención puede ser menor (p. ej., mensual o anual). Para obtener más información sobre este método, consulte [Información general sobre la retención basada en eventos](event-driven-retention.md). Sin embargo, este método para desencadenar la retención puede consumir demasiado tiempo y producir más errores, lo que daña la escalabilidad. Por lo tanto, una solución automatizada y sin errores para activar la retención puede mejorar la seguridad de los datos y el cumplimiento normativo.

- **Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.

Hay dos opciones para usar la API de REST:

- **Usar Microsoft Flow o una aplicación similar** para desencadenar un evento automáticamente. Microsoft Flow puede orquestar la conexión a otros sistemas. Además, su uso no requiere una solución personalizada.

- **PowerShell o un cliente de HTTP para llamar a la API de REST** Usar PowerShell (versión 6 o posterior) para pedirle a la API de REST de Microsoft 365 que cree eventos. 

Una API de REST es un punto de conexión de servicio que admite conjuntos de operaciones HTTP (métodos), que proporcionan acceso de creación/recuperación/actualización/eliminación a los recursos del servicio. Para obtener más información, vea [Componentes de una solicitud o respuesta de API de REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). En este caso, al usar la API de REST de Microsoft 365, puede crear y recuperar eventos mediante el uso de operaciones (métodos) POST y GET.

## <a name="example-scenarios"></a>Escenarios de ejemplo

Consideremos los siguientes escenarios.

### <a name="scenario-1-employees-leaving-the-organization"></a>Escenario 1: Empleados que dejan la organización 

La organización crea y almacena numerosos documentos relacionados con cada empleado. Estos documentos se administran y conservan durante el tiempo de contratación del empleado. Sin embargo, cuando el empleado abandona la organización o deja de trabajar para ella, la organización esta comercial y legalmente obligada a conservar los documentos de ese empleado durante un período estipulado.

Ahora si varios empleados dejan la organización todos los días, la organización debe activar el reloj de retención de cientos o miles de documentos cada día.

Además, se debe calcular el período de retención de cada uno de estos empleados con el siguiente formato: fecha de despido del empleado + número de días, meses o años en función del tipo de registro del empleado. Por ejemplo, es posible que la compensación y la tramitación de beneficios del mismo empleado necesiten retenciones diferentes.

El siguiente diagrama muestra cómo puede haber varias etiquetas asociadas a un único evento. En este caso, todos los archivos de la etiqueta de indemnización del Trabajador y los que pertenecen a la etiqueta de beneficios del Trabajador se asocian a un único evento, que es la salida del empleado. Cada uno de estos archivos diferentes tiene diferentes relojes de retención. Por lo tanto, cuando un empleado deja la organización, cada archivo dentro de una misma etiqueta experimenta un período de retención diferente. Activar todos estos relojes de retención diferentes para cada tipo de archivo o etiqueta en un solo empleado es una tarea muy desafiante. Imagine este proceso con varios empleados.

![Diagrama de tipo de evento, evento y etiquetas](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

Por lo tanto, un proceso automatizado para activar estos relojes de retención diferentes para varios empleados permitirá ahorrar tiempo, evitar errores y lograr una alta eficiencia.

**Configuración de retención automatizada basada en eventos para este escenario:**

![Diagrama de funciones y acciones para el escenario del empleado que deja la organización](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - La administración crea carpetas del empleado en un conjunto de documentos denominado Naiara Padilla, David Pulido.

  - La administración agrega archivos del empleado, como los de beneficios, nómina o compensación del trabajador a cada carpeta de empleado.

  - La administración asigna el id. de activo a la carpeta de cada empleado. 

  - La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea tipos de eventos relacionados con el empleado como “Desvinculación del empleado”, “Contratación del empleados”.

  - La administración de SCC crea la etiqueta de "Retención de empleados".

  - Esta etiqueta de "Retención de empleados" se publica y se aplican manual o automáticamente a los archivos de empleado en SharePoint.

  - Un sistema de administración de Recursos Humanos como Workday puede trabajar con Microsoft Flow para ejecutarse periódicamente para administrar archivos del empleado.

  - Cuando un empleado deja la organización, Flow activa la API de REST de retención basada en eventos de M365 que inicia el reloj de retención de archivos específicos del empleado.

#### <a name="using-microsoft-flow"></a>Usar Microsoft Flow

Paso 1: crear un flujo para crear un evento mediante la API de REST de Microsoft 365

![Usar Flow para crear un evento](../media/automate-event-driven-retention-flow-1.png)

![Usar Flow para llamar a la API de REST](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>Crear un evento

Código de ejemplo para llamar a la API de REST:

- **Método**: POST
- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **Headers**: Key = Content-Type, Value = application/atom+xml
- **Body**:
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
- **Autenticación**: Básica
- **Nombre de usuario**: “Complianceuser”
- **Contraseña**: “Compliancepassword”


##### <a name="available-parameters"></a>Parámetros disponibles


|Parámetros|Description|Notas|
|--- |--- |--- |
|<d:Name></d:Name>|Escriba un nombre único para el evento.|No puede contener espacios finales ni los siguientes caracteres: % * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|Escribe el nombre del tipo de evento (o Guid)|Example: “Employee termination”. Event type has to be associated with a retention label.|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|Escriba "ComplianceAssetId:" + el Id. del empleado|Ejemplo: "ComplianceAssetId:12345"|
|<d:EventDateTime></d:EventDateTime>|Fecha y hora del evento|Formato: aaaa-MM-ddTHH:mm:ssZ, ejemplo: 2018-12-01T00:00:00Z
|

##### <a name="response-codes"></a>Códigos de respuesta

| Código de respuesta | Descripción       |
| ----------------- | --------------------- |
| 302               | Redirigir              |
| 201               | Fecha de creación               |
| 403               | Error de autorización  |
| 401               | Error de autenticación |

##### <a name="get-events-based-on-time-range"></a>Obtener eventos según el intervalo de tiempo

- **Método**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Autenticación**: Básica

- **Nombre de usuario**: “Complianceuser”

- **Contraseña**: “Compliancepassword”


##### <a name="response-codes"></a>Códigos de respuesta

| Código de respuesta | Descripción                   |
| ----------------- | --------------------------------- |
| 200               | Aceptar, una lista de eventos de atom+ xml |
| 404               | No encontrado                         |
| 302               | Redirigir                          |
| 401               | Error de autorización              |
| 403               | Error de autenticación             |

##### <a name="get-an-event-by-id"></a>Obtén un objeto por id.

- **Método**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Autenticación**: Básica

- **Nombre de usuario**: “Complianceuser”

- **Contraseña**: “Compliancepassword”



##### <a name="response-codes"></a>Códigos de respuesta

| Código de respuesta | Descripción                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml |
| 404               | No encontrado                                            |
| 302               | Redirigir                                             |
| 401               | Error de autorización                                 |
| 403               | Error de autenticación                                |

##### <a name="get-an-event-by-name"></a>Obtén un evento por nombre

- **Método**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **Headers**: Key = Content-Type, Value = application/atom+xml

- **Autenticación**: Básica

- **Nombre de usuario**: “Complianceuser”

- **Contraseña**: “Compliancepassword”


##### <a name="response-codes"></a>Códigos de respuesta

| Código de respuesta | Descripción                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | Aceptar, el cuerpo de la respuesta contiene el evento en atom+ xml |
| 404               | No encontrado                                            |
| 302               | Redirigir                                             |
| 401               | Error de autorización                                 |
| 403               | Error de autenticación                                |

#### <a name="using-powershell-version-6-or-later-or-any-http-client"></a>Usar PowerShell (versión 6 o posterior) o cualquier cliente HTTP

Paso 1: Conéctate a PowerShell.

Paso 2: Ejecuta el siguiente script.

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```


#### <a name="verify-the-outcome-in-both-options"></a>Comprobar el resultado en ambas opciones.

Paso 1: Ir al Centro de seguridad y cumplimiento.

Paso 2: seleccione los **eventos** en **control de la información**.

Paso 3: Comprobar que se creó el evento.

De forma similar, también se pueden usar las opciones anteriores para automatizar la retención basada en eventos para los siguientes escenarios.

### <a name="scenario-2-contracts-expiring"></a>Escenario 2: Contratos que expiran

Una organización puede tener varios registros para un contrato único con clientes, proveedores y asociados. Estos documentos pueden residir en una biblioteca de documentos como SharePoint. Con la finalización de un contrato empieza el periodo de retención de los documentos asociados al contrato. Por ejemplo, se deben conservar todos los registros relacionados con un contrato cinco años después de que expire. El evento que desencadena el período de retención de cinco años es la expiración del contrato.

Un sistema de administración de relaciones de cliente (CRM) puede trabajar con Microsoft 365 y activar la retención de documentos del contrato.

**Configuración de retención automatizada basada en eventos para este escenario:**

![Diagrama de los funciones y tareas para escenarios de expiración del contrato](../media/automate-event-driven-retention-contract-expiration.png)

  - La administración crea una biblioteca de SharePoint con carpetas diferentes para cada tipo de contrato.

  - La administración agrega archivos del contrato como contratos de licencia y contratos de desarrollo para cada carpeta del contrato.

  - La administración asigna el id. de activo a cada carpeta de contrato.

  - La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea tipos de eventos relacionados con el contrato como eventos de "Creación del contrato" y de "Expiración del contrato".

  - La administración de SCC crea la etiqueta "Expiración del contrato".

  - Esta etiqueta de "Expiración del contrato" se publica y se aplican de forma manual o automática a los archivos del contrato en SharePoint.

  - El sistema de administración de contrato puede trabajar con Microsoft Flow o una aplicación similar para ejecutarse periódicamente para administrar archivos de contrato.

  - Si un contrato vence, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del contrato.

### <a name="scenario-3-end-of-product-manufacturing"></a>Escenario 3: Final de fabricación de productos

A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.

Un sistema de planeación de recursos empresariales (ERP) puede trabajar con Microsoft 365 y Microsoft Flow para activar la retención.

**Configuración de retención automatizada basada en eventos para este escenario:**

![Diagrama de las funciones y tareas para escenarios de ciclo de vida del producto](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - La administración crea carpetas de productos en el conjunto de documentos como Producto 1, Producto 2, etc.

  - La administración agrega los archivos de productos como Especificaciones de fabricación, Precio del producto y Licencias del producto a cada carpeta de producto.

  - La administración le asigna el id. de activo a cada carpeta del producto.

  - La administración de SSC inicia sesión en el Centro de seguridad y cumplimiento.

  - La administración de SCC crea tipos de eventos relacionados con el empleado como "Inicio de fabricación del producto" y "Final de fabricación del producto".

  - La administración de SCC crea la etiqueta "Final de fabricación del producto".

  - Esta etiqueta de "Final de fabricación del producto" se publica y se aplica de forma manual o automática a los archivos del producto en SharePoint.

  - Los sistemas de ERP pueden funcionar con Microsoft Flow o con aplicaciones similares para ejecutarse periódicamente para administrar archivos del producto.

  - Si se termina la fabricación de un producto, Microsoft Flow activará la API de REST de retención basada en eventos de M365 que iniciará el reloj de retención de archivos específicos del producto.

## <a name="appendix"></a>Apéndice

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>Cómo usar los resultados de respuesta Redirect 302 para llamar a la API de REST

1. Invoque una llamada al evento de retención POST con la dirección URL de la API de REST: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
    
    Se necesitan permisos de administrador global.

2. Compruebe el código de respuesta. Si es 302, obtener la dirección URL redirigida de la propiedad de ubicación del encabezado de respuesta.

3. Invocar la llamada al evento de retención POST nuevamente mediante el URL redireccionado.

## <a name="credits"></a>Créditos

Este tema fue revisado por:

Antonio Maio<br/>MVP de servicios y aplicaciones de Microsoft Office<br/> Antonio.Maio@Protiviti.com
