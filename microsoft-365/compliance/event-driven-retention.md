---
title: Información general sobre la retención controlada por eventos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Por lo general, como parte de una solución de administración de registros, puede configurar una etiqueta para iniciar el período de retención en función de un evento identificado.
ms.openlocfilehash: 1e716cc886e8378308054d4f2eedf961045f4486
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817809"
---
# <a name="overview-of-event-driven-retention"></a>Información general sobre la retención controlada por eventos

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them. But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.
  
Por ejemplo, puede usar etiquetas con la retención controlada por eventos para:
  
- **Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization. After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed. The event that triggers the 10-year retention period is the employee leaving the organization. 
    
- **Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract. 
    
- **Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period. 
    
Event-driven retention is typically used as part of a records-management process. This means that:
  
- Labels based on events also usually classify content as a record. For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- Un documento declarado como un registro, pero cuyo desencadenador de eventos aún no se produjo, se conserva de manera indefinida (los registros no se pueden eliminar de forma permanente), hasta que un evento desencadene el período de retención del documento.
    
- Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content. For more information, see [Disposition of content](disposition.md).
    
Una etiqueta basada en un evento tiene las mismas funciones que cualquier etiqueta de retención en Microsoft 365. Para obtener más información, consulte la [información sobre las etiquetas de retención](labels.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Información sobre la relación entre tipos de evento, etiquetas, eventos e id. de activo

Para usar correctamente la retención controlada por eventos, es importante comprender la relación entre tipos de evento, etiquetas de retención, eventos e id. de activos, como se muestra en los diagramas y la explicación siguiente: 
  
![Diagrama de tipo de evento, etiquetas, eventos e id. de activo](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagrama de tipo de evento, etiquetas, eventos e id. de activo](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Puede crear etiquetas de retención para diferentes tipos de contenido y asociarlas a un tipo de evento. Por ejemplo, las etiquetas de retención para distintos tipos de registros y archivos de producto se asocian con un tipo de evento denominado Vida útil del producto, ya que esos registros tienen que conservarse durante 10 años desde el momento en que el producto alcanza el fin de vida.
    
2. Los usuarios (normalmente, los administradores de registros) aplican esas etiquetas de retención en el contenido y (para documentos SharePoint y OneDrive) especifican un id. de activo para cada elemento. En este ejemplo, el identificador de activo es un nombre de producto o un código usado por la organización. Por lo tanto, se asigna una etiqueta de retención a los registros de cada producto, y cada registro tiene una propiedad que contiene un id. de activo. El diagrama representa **todo el contenido** de todos los registros de productos de una organización, y cada elemento tiene asignado el id. de activo del producto al que pertenece el registro. 
    
3. Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:
    
  - Un id. de activo (para documentos de OneDrive y SharePoint)
    
  - Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.
    
  - The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.
    
4. Después de crear un evento, la fecha del evento se sincroniza con todo el contenido que tenga aplicada una etiqueta de retención de ese tipo de evento y que contenga la palabra clave o el id. de activo especificado. Al igual que con cualquier etiqueta de retención, esta sincronización puede tardar hasta 7 días en completarse. En el diagrama anterior, todos los elementos rodeados con un círculo rojo tienen el período de retención activado por este evento. Es decir, cuando este producto llega al final de su vida, el evento provoca el período de retención de los registros del producto.
    
Es importante comprender que, si no especifica palabras clave o un id. de activo para un evento, el evento desencadenará el período de retención de **todo el contenido** que tenga aplicada una etiqueta de ese tipo de evento. En el diagrama anterior, esto quiere decir que se empezaría a conservar todo el contenido. Es posible que no sea esto lo que quiera realizar. 
  
Por último, recuerde que cada etiqueta de retención tiene sus propias opciones de retención. En este ejemplo, todas especifican 10 años, pero puede que un evento desencadene etiquetas de retención donde cada etiqueta tenga un período de retención distinto.
  
## <a name="how-to-set-up-event-driven-retention"></a>Configurar la retención controlada por eventos

Flujo de trabajo general para la retención controlada por eventos:
  
![Diagrama del flujo de trabajo para configurar la retención controlada por eventos](../media/event-based-retention-process.png)
  
> [!TIP]
> Vea [Administrar el ciclo de vida de los documentos de SharePoint con etiquetas de retención](auto-apply-retention-labels-scenario.md) para obtener más información sobre cómo usar las propiedades administradas en SharePoint para aplicar automáticamente las etiquetas de retención e implementar la retención basada en eventos.

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Paso 1: Crear una etiqueta cuyo período de retención se base en un evento

En el Centro de cumplimiento de Microsoft 365, en el panel de navegación izquierdo, seleccione **Gobierno de información** > **Etiquetas** > **Crear una etiqueta**. Si **Gobierno de información** no se muestra en el panel de navegación, desplácese hacia abajo y seleccione **Mostrar todo**.
  
When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event. This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page. 
  
Tenga en cuenta que la retención controlada por eventos suele usarse para contenido clasificado como un registro. Por este motivo, al crear etiquetas de retención basadas en un evento, suele seleccionarse la opción **Usar etiqueta para clasificar contenido como un "registro"**.
  
Además, tenga en cuenta que la retención controlada por eventos necesita una configuración de retención que:
  
- Conserve el contenido.
    
- Elimine el contenido automáticamente o desencadene una revisión para eliminación al finalizar el período de retención.
    
![Opción para basar una etiqueta en un evento](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>Paso 2: Seleccionar un tipo de evento para esa etiqueta

En la configuración de etiquetas, después de seleccionar la opción para que la etiqueta se base en un **evento**, verá la opción **Seleccionar un tipo de evento**. Un tipo de evento es simplemente una descripción general de un evento al que puede asociar una etiqueta.
  
Por ejemplo, si crea un tipo de evento denominado "Vida útil del producto", creará etiquetas de retención basadas en eventos con nombres que describan los tipos de contenido donde quiere que se apliquen las etiquetas, como "Archivos de desarrollo de productos" o "Registros de decisiones empresariales de producto".
  
Tenga en cuenta que, después de seleccionar un tipo de evento y crear la etiqueta de retención, el tipo de evento no se puede cambiar.
  
![Opciones para crear o seleccionar un tipo de evento](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Paso 3: Publicar o aplicar automáticamente las etiquetas de retención basadas en eventos

Como en cualquier etiqueta de retención, es necesario [publicar o aplicar automáticamente](create-retention-labels.md) una etiqueta basada en eventos, de modo que se aplique manual o automáticamente al contenido.

> [!NOTE]
> Si selecciona una etiqueta de retención basada en eventos de **Administración de registros** > **pestaña Plan de archivos** o **Gobierno de datos** > **pestaña Etiquetas**, el botón **Aplicar automáticamente una etiqueta** no está disponible.
> 
> En lugar de este botón, use la opción **Aplicar automáticamente una etiqueta** encima de la lista de etiquetas o directivas de una de las siguientes ubicaciones:
> - **Administración de registros** > **pestaña Directivas de etiqueta**
> - **Gobierno de datos** > **pestaña Etiquetas** o **pestaña Directivas de etiqueta**


![Opciones para publicar o aplicar automáticamente una etiqueta de retención](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>Paso 4: Escribir un id. de activo

After an event-driven label is applied to content, you can enter an asset ID for each item. For example, your organization might use:
  
- Códigos de producto que puede usar para conservar contenido solo para un producto específico.
    
- Códigos de proyecto que puede usar para conservar contenido solo para un proyecto específico.
    
- Id. de empleado que puede usar para conservar contenido solo para una persona específica.
    
Tenga en cuenta que el id. de activo es simplemente otra propiedad de documento en SharePoint y OneDrive para la Empresa. Es posible que la organización ya use otras propiedades del documento o id. para clasificar contenido. En ese caso, puede usar esas propiedades y valores al crear un evento (vea el paso 6 más adelante). Lo importante es que su organización tiene que usar alguna combinación de propiedad:valor en las propiedades del documento para asociar ese elemento con un tipo de evento.
  
![Cuadro de texto para especificar un id. de activo](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Paso 5: Crear un evento

When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event. You need to manually trigger an event by creating it.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Paso 6: Seleccionar el mismo tipo de evento usado por la etiqueta en el paso 2

Al crear el evento, seleccione el mismo tipo de evento usado por la etiqueta de retención en el paso 2 (por ejemplo, Vida de producto). Solo se desencadenará el período de retención del contenido que tenga aplicadas etiquetas de retención de ese tipo de evento.
  
![Opción en Configuración de evento para seleccionar un tipo de evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Paso 7: Escribir las palabras clave o un id. de activo

Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content. For asset IDs, retention will be enforced only on content with the specified property:value pair. If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them. 
  
Tenga en cuenta que el id. de activo es simplemente otra propiedad de documento en SharePoint y OneDrive para la Empresa. Si usa la propiedad de id. de activo, escriba ComplianceAssetID:\<value\> en el cuadro de id. de activo que se muestra abajo.
  
Your organization might have applied other properties and IDs to the documents related to this event type. For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ". In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.
  
For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
Por último, elija la fecha en la que se ha producido el evento, esta fecha se usa como inicio del periodo de retención. Después de crear un evento, la fecha del evento se sincroniza con todo el contenido con una etiqueta de retención de ese tipo de evento, id. de activo y palabras clave. Al igual que con cualquier etiqueta de retención, esta sincronización puede tardar hasta 7 días en completarse.
  
![Página Configuración de evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Usar Búsqueda de contenido para encontrar todo el contenido que tenga aplicada una etiqueta o id. de activo específicos

Después de asignar etiquetas de retención a contenido, puede usar la búsqueda de contenido para encontrar todo el contenido clasificado con una etiqueta de retención específica o que contiene un id. de activo específico.
  
Al crear una búsqueda de contenido:
  
- Para encontrar todo el contenido con una etiqueta de retención específica, seleccione la condición **Etiqueta de cumplimiento** y, después, escriba el nombre de etiqueta completo o una parte del nombre de la etiqueta y use un comodín. 
    
- Para encontrar todo el contenido con un id. de activo específico, escriba la propiedad **ComplianceAssetID** y un valor, como ComplianceAssetID:\<value\>. 
    
Para obtener más información, consulte [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de Contenido](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Permisos

To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
Para obtener más información, vea [Conceder acceso a los usuarios al Centro de seguridad y cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatizar eventos con PowerShell

In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs. However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).

También puede usar un script de PowerShell para automatizar la retención basada en eventos desde sus aplicaciones empresariales. Los cmdlets de PowerShell disponibles para la retención controlada por eventos:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

