---
title: Crear una directiva DLP para proteger documentos con FCI u otras propiedades
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Muchas organizaciones disponen de un proceso para identificar y clasificar información confidencial mediante las propiedades de clasificación en la infraestructura de clasificación de archivos (FCI) de Windows Server, las propiedades del documento en SharePoint o las propiedades del documento aplicadas por un sistema de terceros. Si se describe su organización, puede crear una directiva de DLP que reconozca las propiedades que se han aplicado a los documentos por FCI de Windows Server o cualquier otro sistema, de modo que la Directiva DLP se pueda aplicar en documentos de Office con FCI específicos o con otros valores de propiedad.
ms.openlocfilehash: 3fa28492ef4d19903797741795091561de3fa257
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327106"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Crear una directiva DLP para proteger documentos con FCI u otras propiedades

En Microsoft 365, puede usar una directiva de prevención de pérdida de datos (DLP) para identificar, supervisar y proteger información confidencial. Muchas organizaciones disponen de un proceso para identificar y clasificar información confidencial mediante las propiedades de clasificación en la infraestructura de clasificación de archivos (FCI) de Windows Server, las propiedades del documento en SharePoint o las propiedades del documento aplicadas por un sistema de terceros. Si se describe su organización, puede crear una directiva de DLP que reconozca las propiedades que se han aplicado a los documentos por FCI de Windows Server o cualquier otro sistema, de modo que la Directiva DLP se pueda aplicar en documentos de Office con FCI específicos o con otros valores de propiedad.
  
![Diagrama que muestra Office 365 y el sistema de clasificación externo](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
Por ejemplo, su organización puede usar la FCI de Windows Server para identificar los documentos con información de identificación personal (PII), como números de seguridad social, y después clasificar el documento mediante la configuración de la propiedad **Información de identificación personal** en **Alto**, **Moderado**, **Bajo**, **Público** o **No PII** según el tipo y el número de repeticiones de PII encontradas en el documento. En Microsoft 365, puede crear una directiva DLP que identifique los documentos que tienen esa propiedad configurada en valores específicos, como **alto** y **medio**y, a continuación, realiza una acción como bloquear el acceso a esos archivos. La misma directiva puede tener otra regla que realice una acción diferente si la propiedad se establece en **Bajo**, por ejemplo, enviar una notificación por correo electrónico. De esta forma, DLP se integra con Windows Server FCI y puede ayudar a proteger los documentos de Office cargados o compartidos en Microsoft 365 desde servidores de archivos basados en Windows Server.
  
Una directiva DLP simplemente busca un par nombre-valor para una propiedad específica. Se puede usar cualquier propiedad de documento, siempre y cuando la propiedad tenga una propiedad administrada correspondiente para la búsqueda de SharePoint. Por ejemplo, una colección de sitios de SharePoint puede usar un tipo de contenido denominado **Informe de viaje** con un campo obligatorio denominado **Cliente**. Cuando una persona crea un informe de viaje, debe escribir el nombre del cliente. El par nombre-valor de esta propiedad también se puede usar en una directiva DLP. Por ejemplo, si desea que una regla bloquee el acceso al documento para los usuarios externos cuando el campo **Cliente** contiene **Contoso**.
  
Tenga en cuenta que si quiere aplicar la Directiva DLP a contenido con etiquetas 365 específicas de Microsoft, no debe seguir los pasos que se indican aquí. En su lugar, obtenga información sobre cómo [usar una etiqueta de retención como condición en una directiva DLP](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).
  
## <a name="before-you-create-the-dlp-policy"></a>Antes de crear la directiva DLP

Para poder usar una propiedad de FCI de Windows Server u otra propiedad en una directiva DLP, debe crear una propiedad administrada en el centro de administración de SharePoint. Este es el motivo.
  
Ejemplos
  
Esto es importante porque DLP utiliza el rastreador de búsqueda para identificar y clasificar información confidencial en los sitios y, a continuación, almacenar la información confidencial en una parte segura del índice de búsqueda. Al cargar un documento en Office 365, SharePoint crea automáticamente propiedades rastreadas en función de las propiedades del documento. Pero para usar una FCI u otra propiedad en una directiva DLP, la propiedad rastreada debe asignarse a una propiedad administrada para que el contenido con esa propiedad se conserve en el índice.
  
Para obtener más información sobre las propiedades administradas y de búsqueda, vea [administrar el esquema de búsqueda en SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454).
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Paso 1: Cargar un documento con la propiedad necesaria en Office 365

Primero debe cargar un documento con la propiedad a la que desea hacer referencia en la directiva DLP. Microsoft 365 detectará la propiedad y, a continuación, creará automáticamente una propiedad rastreada a partir de ella. En el paso siguiente, creará una propiedad administrada y, a continuación, asignará la propiedad administrada a esta propiedad rastreada.
  
### <a name="step-2-create-a-managed-property"></a>Paso 2: Crear una propiedad administrada

1. Inicie sesión en el Centro de administración de Microsoft 365.
    
2. En el panel de navegación izquierdo, elija **centros de administración** \> **SharePoint**. Ahora está en el Centro de administración de SharePoint.
    
3. En el panel de navegación izquierdo, elija **Buscar** \> en la página **Administración de búsquedas** \> **administrar esquema de búsqueda**.
    
    ![Página de administración de búsqueda en el Centro de administración de SharePoint](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. En la página **propiedades administradas** , \> **nueva propiedad administrada**.
    
    ![Página de Propiedades administradas con el botón Nueva propiedad administrada resaltado](../media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. Escriba un nombre y una descripción para la propiedad. Este nombre es lo que aparecerá en las directivas DLP.
    
6. En **Tipo**, elija **Texto**. 
    
7. En **Características principales**, seleccione **Consultable** y **Recuperable**.
    
8. En **asignaciones a propiedades rastreadas** , \> **agregue una asignación**.
    
9. En el cuadro de diálogo **selección de propiedades rastreadas** \> , busque y seleccione la propiedad rastreada que corresponda a la propiedad de Windows Server FCI u otra propiedad que vaya a usar en la Directiva DLP \> **correcta**.
    
    ![Cuadro de diálogo de selección de propiedades rastreadas](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. En la parte inferior de la página \> **Aceptar**.
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Crear una directiva DLP que use una propiedad de FCI u otra propiedad

En este ejemplo, una organización usa FCI en sus servidores de archivos basados en Windows Server; concretamente, usan la propiedad de clasificación FCI denominada **información de identificación personal** con los valores posibles de **High**, **moderate**, **Low**, **Public**y **no PII**. Ahora quieren aprovechar su clasificación de FCI existente en sus directivas DLP en Office 365.
  
En primer lugar, siguen los pasos anteriores para crear una propiedad administrada en SharePoint Online, que se asigna a la propiedad rastreada creada automáticamente a partir de la propiedad FCI.
  
A continuación, crean una directiva DLP con dos reglas que usan las propiedades de documento de condición que **contienen cualquiera de estos valores**:
  
- **Contenido PII de FCI: alta, moderada** La primera regla restringe el acceso al documento si la propiedad de clasificación FCI **información de identificación personal** es igual a **alta** o **moderada** y el documento se comparte con personas de fuera de la organización. 
    
- **Contenido PII de FCI: bajo** La segunda regla envía una notificación al propietario del documento si la propiedad de clasificación FCI la **información de identificación personal** es **baja** y el documento se comparte con personas de fuera de la organización. 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>Crear la Directiva DLP mediante PowerShell

Tenga en cuenta que las propiedades de documento de condición **contienen alguno de estos valores** no está disponible temporalmente en la interfaz de usuario del centro de seguridad &amp; y cumplimiento, pero puede usar esta condición con PowerShell. Puede usar los `New\Set\Get-DlpCompliancePolicy` cmdlets para trabajar con una directiva DLP y usar los `New\Set\Get-DlpComplianceRule` cmdlets con el `ContentPropertyContainsWords` parámetro para agregar las propiedades del documento de condición que **contienen cualquiera de estos valores**.
  
Para obtener más información sobre estos cmdlets, [consulte &amp; cmdlets del centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).
  
1. [Conectarse al centro de seguridad y &amp; cumplimiento con PowerShell remoto](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Cree la Directiva con el `New-DlpCompliancePolicy` .

A continuación, se muestra un ejemplo de PowerShell que crea una directiva DLP que se aplica a todas las ubicaciones.

```powershell
New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
```

3. Cree las dos reglas descritas anteriormente usando `New-DlpComplianceRule` , donde una regla es para el valor **bajo** , y otra regla es para los valores **alto** y **moderado** . 
    
    A continuación, se muestra un ejemplo de PowerShell que crea estas dos reglas. Tenga en cuenta que los pares nombre-valor de propiedad se incluyen entre comillas, y un nombre de propiedad puede especificar varios valores separados por comas sin espacios, como`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

```powershell
New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
```

    Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example. The possible values for each property can be different for every organization. The **High**, **Moderate**, and **Low** values used here are only an example. For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server. For more information, see [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).
    
Cuando termine, la Directiva debe tener dos reglas nuevas que usen las propiedades del **documento y que contengan cualquiera de estos valores de** condición. Tenga en cuenta que esta condición no aparecerá en la interfaz de usuario, aunque se mostrarán las demás condiciones, acciones y configuración.
  
Una regla bloquea el acceso al contenido donde la propiedad **Información de identificación personal** es igual a **Alto** o **Moderado**. Una segunda regla envía una notificación sobre el contenido donde la propiedad **Información de identificación personal** es igual a **Bajo**.
  
![Cuadro de diálogo de nueva directiva DLP que muestra dos reglas recién creadas](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>Después de crear la directiva DLP

Si realiza los pasos descritos en las secciones anteriores, se creará una directiva de DLP que detectará rápidamente el contenido con esa propiedad, pero solo si el contenido se ha cargado recientemente (para que el contenido indizado), o si el contenido es antiguo, pero solo se ha editado (para que el contenido se vuelva a indexar).
  
Para detectar contenido con esa propiedad en todas partes, tal vez le convenga solicitar de forma manual que la biblioteca, sitio o colección de sitios se vuelva a indexar para que la directiva DLP tenga conocimiento de todo el contenido que incluye esa propiedad. En SharePoint Online, el contenido se rastrea automáticamente según una programación de rastreo definida. El rastreador toma el contenido que ha cambiado desde el último rastreo y actualiza el índice. Si necesita que la directiva DLP proteja contenido antes del siguiente rastreo programado, puede llevar a cabo estos pasos.
  
> [!CAUTION]
> Volver a indexar un sitio puede provocar una carga masiva en el sistema de búsqueda. No vuelva a indizar el sitio a menos que su escenario lo requiera absolutamente. 
  
Para obtener más información, vea [Solicitar manualmente el rastreo y una nueva indexación de un sitio, una biblioteca o una lista](https://go.microsoft.com/fwlink/p/?LinkID=627457).
  
### <a name="re-index-a-site-optional"></a>Volver a indexar un sitio (opcional)

1. En el sitio, elija **configuración** (icono de engranaje en la parte superior derecha) \> **configuración del sitio**.
    
2. En **Buscar**, elija reindizar el sitio de **disponibilidad de búsqueda y sin conexión** \> **Reindex site**.
    
## <a name="more-information"></a>Más información

- [Información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md)
    
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
    
- [Enviar notificaciones y mostrar sugerencias de directivas para directivas DLP](use-notifications-and-policy-tips.md)
    
- [Qué incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md)
    
- [Tipos de información confidencial definiciones de entidad](sensitive-information-type-entity-definitions.md)
