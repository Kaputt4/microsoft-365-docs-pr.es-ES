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
description: Con las etiquetas de retención puede hacer que un período de retención se base en el momento en que se produce un tipo específico de evento. El evento desencadena el inicio del período de retención y se exigirán las acciones de retención de etiqueta en todo el contenido que tenga aplicada una etiqueta de retención para ese tipo de evento. La retención controlada por eventos suele usarse como parte de un proceso de administración de registros.
ms.openlocfilehash: 100381d87c51a8ef403a88f19159235081c2a8df
ms.sourcegitcommit: 330e9baf02b5bc220d61f777c2338814459626ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44385012"
---
# <a name="overview-of-event-driven-retention"></a>Información general sobre la retención controlada por eventos

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Al conservar contenido, el período de retención suele basarse en la antigüedad del contenido (por ejemplo, puede conservar documentos durante siete años después de su creación y eliminarlos cuando transcurra ese período). Pero, con las etiquetas de retención en Microsoft 365, también puede hacer que un período de retención se base en el momento en que se produzca un tipo específico de evento. El evento desencadena el inicio del período de retención y se exigirán las acciones de retención de etiqueta en todo el contenido que tenga aplicada una etiqueta de retención para ese tipo de evento.
  
Por ejemplo, puede usar etiquetas con la retención controlada por eventos para:
  
- **Empleados que abandonen la organización** Imagine que necesita conservar los registros de los empleados durante 10 años desde el momento en que un empleado abandona la organización. Una vez transcurridos los 10 años, tendrán que eliminarse todos los documentos relacionados con la contratación, desempeño y terminación de ese empleado. El evento que desencadena el período de retención de 10 años es cuando el empleado abandona la organización. 
    
- **Expiración del contrato** Imagine que todos los registros relacionados con los contratos tienen que conservarse durante cinco años desde el momento en que expire el contrato. El evento que desencadena el período de retención de cinco años es la expiración del contrato. 
    
- **Vida útil del producto** Puede que su organización tenga requisitos de retención relacionados con la última fecha de fabricación de productos para contenido como especificaciones técnicas. En ese caso, la última fecha de fabricación es el evento que desencadena el período de retención. 
    
La retención controlada por eventos suele usarse como parte de un proceso de administración de registros. Esto quiere decir que:
  
- Las etiquetas basadas en eventos también suelen clasificar contenido como registros. Para obtener más información, vea [Usar Búsqueda de contenido para encontrar todo el contenido que tenga aplicada una etiqueta de retención específica](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- Un documento declarado como un registro, pero cuyo desencadenador de eventos aún no se produjo, se conserva de manera indefinida (los registros no se pueden eliminar de forma permanente), hasta que un evento desencadene el período de retención del documento.
    
- Las etiquetas de retención basadas en eventos suelen desencadenar una revisión para eliminación al finalizar el período de retención, por lo que un administrador de registros puede revisar y eliminar el contenido de forma manual. Para más información, vea [Eliminación de contenido](disposition.md).
    
Una etiqueta de retención basada en un evento tiene las mismas funciones que una etiqueta de retención de Microsoft 365. Para más información, consulte [Información general sobre las etiquetas](labels.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Información sobre la relación entre tipos de evento, etiquetas, eventos e id. de activo

Para usar correctamente la retención controlada por eventos, es importante comprender la relación entre tipos de evento, etiquetas de retención, eventos e id. de activos, como se muestra en los diagramas y la explicación siguiente: 
  
![Diagrama de tipo de evento, etiquetas, eventos e id. de activo](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagrama de tipo de evento, etiquetas, eventos e id. de activo](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Puede crear etiquetas de retención para diferentes tipos de contenido y asociarlas a un tipo de evento. Por ejemplo, las etiquetas de retención para distintos tipos de registros y archivos de producto se asocian con un tipo de evento denominado Vida útil del producto, ya que esos registros tienen que conservarse durante 10 años desde el momento en que el producto alcanza el fin de vida.
    
2. Los usuarios (normalmente, los administradores de registros) aplican esas etiquetas de retención en el contenido y (para documentos SharePoint y OneDrive) especifican un id. de activo para cada elemento. En este ejemplo, el identificador de activo es un nombre de producto o un código usado por la organización. Por lo tanto, se asigna una etiqueta de retención a los registros de cada producto, y cada registro tiene una propiedad que contiene un id. de activo. El diagrama representa **todo el contenido** de todos los registros de productos de una organización, y cada elemento tiene asignado el id. de activo del producto al que pertenece el registro. 
    
3. La vida útil del producto es el tipo de evento; un producto específico que llega al fin de vida es un evento. Cuando se produce este tipo de evento (en este caso, cuando un producto alcanza el fin de vida), creará un evento que especifique:
    
  - Un id. de activo (para documentos de OneDrive y SharePoint)
    
  - Palabras clave (para elementos de Exchange). En este ejemplo, la organización usa un código de producto en mensajes que contienen registros de productos, por lo que la palabra clave para los elementos de Exchange coincide con el id. de activo para documentos de OneDrive y SharePoint.
    
  - La fecha en que se produjo el evento. La fecha se usa como el inicio del período de retención. Esta fecha puede ser la fecha actual, una fecha pasada o una fecha futura.
    
4. Después de crear un evento, la fecha del evento se sincroniza con todo el contenido que tenga aplicada una etiqueta de retención de ese tipo de evento y que contenga la palabra clave o el id. de activo especificado. Al igual que con cualquier etiqueta de retención, esta sincronización puede tardar hasta 7 días en completarse. En el diagrama anterior, todos los elementos rodeados con un círculo rojo tienen el período de retención activado por este evento. Es decir, cuando este producto llega al final de su vida, el evento provoca el período de retención de los registros del producto.
    
Es importante comprender que, si no especifica palabras clave o un Id. de activo para un evento, el evento desencadenará el período de retención de **todo el contenido** que tenga aplicada una etiqueta de retención de ese tipo de evento. Esto quiere decir que, en el diagrama anterior, se empezaría a conservar todo el contenido. Es posible que no sea esto lo que quiera realizar. 
  
Por último, recuerde que cada etiqueta de retención tiene sus propias opciones de retención. En este ejemplo, todas especifican 10 años, pero puede que un evento desencadene etiquetas de retención donde cada etiqueta tenga un período de retención distinto.
  
## <a name="how-to-set-up-event-driven-retention"></a>Configurar la retención controlada por eventos

Flujo de trabajo general para la retención controlada por eventos:
  
![Diagrama del flujo de trabajo para configurar la retención controlada por eventos](../media/event-based-retention-process.png)
  
> [!TIP]
> Para obtener más información sobre cómo usar las propiedades administradas en SharePont para aplicar automáticamente las etiquetas de retención y implementar la retención basada en eventos, vea [administrar el ciclo de vida de los documentos de SharePoint con etiquetas de retención](auto-apply-retention-labels-scenario.md).

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Paso 1: Crear una etiqueta cuyo período de retención se base en un evento

En el Centro de cumplimiento de Microsoft 365, el Centro de seguridad de Microsoft 365 o el Centro de seguridad y cumplimiento, en el panel de navegación izquierdo, elija **Clasificación** > **Etiquetas de retención** > ** pestaña Etiquetas** > **Crear una etiqueta**.
  
Al crear la etiqueta, active la retención y, después, seleccione la opción que se muestra abajo para conservar o eliminar el contenido basándose en un evento. Esto quiere decir que la configuración de retención no se aplicará hasta el paso 5, cuando cree un evento en la página **Eventos**. 
  
Tenga en cuenta que la retención controlada por eventos suele usarse para contenido clasificado como un registro. Por este motivo, al crear etiquetas de retención basadas en un evento, suele seleccionarse la opción **Usar etiqueta para clasificar contenido como un "registro"**.
  
Además, tenga en cuenta que la retención controlada por eventos necesita una configuración de retención que:
  
- Conserve el contenido.
    
- Elimine el contenido automáticamente o desencadene una revisión para eliminación al finalizar el período de retención.
    
![Opción para basar una etiqueta en un evento](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>Paso 2: Seleccionar un tipo de evento para esa etiqueta

En la configuración de etiquetas, después de seleccionar la opción para basar la etiqueta en **un evento**, verá la opción para **Seleccionar un tipo de evento**. Un tipo de evento es simplemente una descripción general de un evento con el que quiera asociar una etiqueta.
  
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

### <a name="step-4-enter-an-asset-id"></a>Paso 4: Escribir un id. de activo

Después de aplicar una etiqueta controlada por eventos en contenido, puede especificar un id. de activo para cada elemento. Por ejemplo, su organización podría usar:
  
- Códigos de producto que puede usar para conservar contenido solo para un producto específico.
    
- Códigos de proyecto que puede usar para conservar contenido solo para un proyecto específico.
    
- Id. de empleado que puede usar para conservar contenido solo para una persona específica.
    
Tenga en cuenta que el id. de activo es simplemente otra propiedad de documento en SharePoint y OneDrive para la Empresa. Puede que la organización ya use otras propiedades del documento o id. para clasificar contenido. En ese caso, puede usar esas propiedades y valores al crear un evento (vea el paso 6 más adelante). Lo importante es que su organización tiene que usar alguna combinación de propiedad:valor en las propiedades del documento para asociar ese elemento con un tipo de evento.
  
![Cuadro de texto para especificar un id. de activo](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Paso 5: Crear un evento

Si se produce un caso concreto de ese tipo de evento (por ejemplo, un producto llega al final de su vida útil), acceda a la página **Eventos de gestión de registros** > ** en el Centro** de cumplimiento de la seguridad&amp; y cree un evento. Se debe desencadenar manualmente un evento mediante su creación.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Paso 6: Seleccionar el mismo tipo de evento usado por la etiqueta en el paso 2

Al crear el evento, seleccione el mismo tipo de evento usado por la etiqueta de retención en el paso 2 (por ejemplo, Vida de producto). Solo se desencadenará el período de retención del contenido que tenga aplicadas etiquetas de retención de ese tipo de evento.
  
![Opción en Configuración de evento para seleccionar un tipo de evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Paso 7: Escribir las palabras clave o un id. de activo

Ahora, para restringir el ámbito del contenido, especifique id. de activo para contenido de SharePoint y OneDrive, o bien palabras clave para contenido de Exchange. En el caso de los id. de activo, la retención solo se exigirá en contenido con el par especificado de propiedad:valor. Si no se especifica un id. de activo, se aplicará la misma fecha de retención en **todo el contenido** con etiquetas de ese tipo de evento. 
  
Tenga en cuenta que el id. de activo es simplemente otra propiedad de documento en SharePoint y OneDrive para la Empresa. Si usa la propiedad de id. de activo, escriba ComplianceAssetID:\<value\> en el cuadro de id. de activo que se muestra abajo.
  
Puede que su organización aplicara otras propiedades e id. en los documentos relacionados con ese tipo de evento. Por ejemplo, si necesita detectar los registros de un producto específico, el id. podría ser una combinación de la propiedad personalizada IdProducto y el valor “XYZ”. En este caso, escribiría IdProducto:XYZ en el cuadro “Id. de activo” que se muestra abajo.
  
En el caso de elementos de Exchange, puede incluir palabras clave. Puede restringir la consulta con operadores de búsqueda como AND, OR y NOT. Para obtener más información sobre los operadores, vea [Consultas de palabras clave y condiciones de búsqueda para Búsqueda de contenido](keyword-queries-and-search-conditions.md).
  
Por último, elija la fecha en la que se ha producido el evento, esta fecha se usa como inicio del periodo de retención. Después de crear un evento, la fecha del evento se sincroniza con todo el contenido con una etiqueta de retención de ese tipo de evento, id. de activo y palabras clave. Al igual que con cualquier etiqueta de retención, esta sincronización puede tardar hasta 7 días en completarse.
  
![Página Configuración de evento](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Usar Búsqueda de contenido para encontrar todo el contenido que tenga aplicada una etiqueta o id. de activo específicos

Después de asignar etiquetas de retención a contenido, puede usar la búsqueda de contenido para encontrar todo el contenido clasificado con una etiqueta de retención específica o que contiene un id. de activo específico.
  
Al crear una búsqueda de contenido:
  
- Para encontrar todo el contenido con una etiqueta de retención específica, seleccione la condición **Etiqueta de cumplimiento** y, después, escriba el nombre de etiqueta completo o una parte del nombre de la etiqueta y use un comodín. 
    
- Para encontrar todo el contenido con un id. de activo específico, escriba la propiedad **ComplianceAssetID** y un valor, como ComplianceAssetID:\<value\>. 
    
Para obtener más información, consulte [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de Contenido](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Permisos

Para obtener acceso a la página **Eventos**, los revisores tienen que ser miembros de un grupo de roles con el rol **Administración de disposición** y rol **Registros de auditoría de solo vista**. Le recomendamos que cree un grupo de roles llamado Revisores de disposiciones, que agregue estos dos roles al grupo de roles y que, después, agregue miembros al grupo de roles. 
  
Para más información, vea [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Automatizar eventos con PowerShell

En el centro de administración, solo puede crear eventos manualmente. No es posible desencadenar automáticamente un evento cuando se produce. Sin embargo, puede usar una API de Rest para desencadenar eventos automáticamente. Para obtener más información, vea [Automatizar la retención basada en eventos](automate-event-driven-retention.md).

También puede usar un script de PowerShell para automatizar la retención basada en eventos desde sus aplicaciones empresariales. Los cmdlets de PowerShell disponibles para la retención controlada por eventos:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

