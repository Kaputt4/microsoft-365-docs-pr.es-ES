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
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar una directiva de prevención de pérdida de datos (DLP) para proteger los documentos que tienen propiedades de un sistema de terceros.
ms.openlocfilehash: 971d2a1dd4f69f7bbd2598e31fc99c9c5cfe1eda
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423803"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Crear una directiva DLP para proteger documentos con FCI u otras propiedades

Las directivas de prevención de pérdida de datos (DLP) de Microsoft 365 pueden usar propiedades de clasificación o propiedades de elementos para identificar elementos confidenciales. Por ejemplo, puede usar:

- Propiedades de la infraestructura de clasificación de archivos (FCI) de Windows Server
- Propiedades del documento de SharePoint
- Propiedades de documentos del sistema de terceros

![Diagrama que muestra Office 365 y el sistema de clasificación externo](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

Por ejemplo, la organización puede usar la FCI de Windows Server para identificar elementos con datos personales como números de seguridad social y, a continuación, clasificar el documento estableciendo la propiedad Información de identificación **personal** en **High**, **Moderate**, **Low**, **Public** o **Not PII** según el tipo y el número de repeticiones de datos personales encontrados en el documento.

En Microsoft 365, puede crear una directiva DLP que identifique los documentos que tienen esa propiedad establecida en valores específicos, como **High** y **Medium,** y, a continuación, realiza una acción como bloquear el acceso a esos archivos. La misma directiva puede tener otra regla que realice una acción diferente si la propiedad se establece en **Bajo**, por ejemplo, enviar una notificación por correo electrónico. De este modo, DLP se integra con la FCI de Windows Server y puede ayudar a proteger los documentos de Office cargados o compartidos en Microsoft 365 desde servidores de archivos basados en Windows Server.

Una directiva DLP simplemente busca un par de nombre y valor de propiedad específicos. Se puede usar cualquier propiedad de documento, siempre que la propiedad tenga una propiedad administrada correspondiente para la búsqueda de SharePoint. Por ejemplo, una colección de sitios de SharePoint puede usar un tipo de contenido denominado **Trip Report** con un campo obligatorio denominado **Customer**. Cada vez que una persona crea un informe de viaje, debe escribir el nombre del cliente. Este par nombre/valor de propiedad también se puede usar en una directiva DLP, por ejemplo,  si desea una regla que bloquee el acceso al documento para invitados cuando el campo Cliente contiene **Contoso**.

Si desea aplicar la directiva DLP al contenido con etiquetas específicas de Microsoft 365, no debe seguir los pasos aquí. En su lugar, obtenga información sobre [cómo usar una etiqueta de retención como condición en una directiva DLP](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).

## <a name="before-you-create-the-dlp-policy"></a>Antes de crear la directiva DLP

Para poder usar una propiedad de FCI de Windows Server u otra propiedad en una directiva DLP, debe crear una propiedad administrada en el centro de administración de SharePoint. Este es el motivo.

Ejemplos

> [!NOTE]
> Asegúrese de usar un nombre de propiedad administrada y no un nombre de propiedad rastreada al crear reglas DLP con la `ContentPropertyContainsWords` condición.

Esto es importante porque DLP usa el rastreador de búsqueda para identificar y clasificar información confidencial en los sitios y, a continuación, almacenar esa información confidencial en una parte segura del índice de búsqueda. Al cargar un documento en Office 365, SharePoint crea automáticamente propiedades rastreadas en función de las propiedades del documento. Pero para usar una FCI u otra propiedad en una directiva DLP, la propiedad rastreada debe asignarse a una propiedad administrada para que el contenido con esa propiedad se conserve en el índice.

Para obtener más información sobre las propiedades administradas y de búsqueda, vea [Manage the search schema in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454).

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Paso 1: Cargar un documento con la propiedad necesaria en Office 365

Primero debe cargar un documento con la propiedad a la que desea hacer referencia en la directiva DLP. Microsoft 365 detectará la propiedad y creará automáticamente una propiedad rastreada a partir de ella. En el paso siguiente, creará una propiedad administrada y, a continuación, asignará la propiedad administrada a esta propiedad rastreada.

### <a name="step-2-create-a-managed-property"></a>Paso 2: Crear una propiedad administrada

1. Inicie sesión en el Centro de administración de Microsoft 365.

2. En la navegación izquierda, elija **Centros de administración de** \> **SharePoint**. Ahora está en el Centro de administración de SharePoint.

3. En la navegación izquierda, elija **buscar en** la página administración \> de **búsqueda** Administrar esquema \> **de búsqueda**.

   ![Página de administración de búsqueda en el Centro de administración de SharePoint](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. En la **página Propiedades administradas** \> **Nueva propiedad administrada**.

   ![Página de Propiedades administradas con el botón Nueva propiedad administrada resaltado](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. Escriba un nombre y una descripción para la propiedad. Este nombre es lo que aparecerá en las directivas DLP.

6. En **Tipo**, elija **Texto**.

7. En **Características principales**, seleccione **Consultable** y **Recuperable**.

8. En **Asignaciones a propiedades rastreadas** \> **Agregue una asignación**.

9. En **el cuadro de** diálogo selección de propiedades rastreadas, busque y seleccione la propiedad rastreada que corresponde a la propiedad FCI de Windows Server u otra propiedad que usará en la directiva \> DLP \> **Aceptar**.

   ![Cuadro de diálogo de selección de propiedades rastreadas](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. En la parte inferior de la página \> **Aceptar**.

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Crear una directiva DLP que use una propiedad de FCI u otra propiedad

En este ejemplo, una organización usa FCI en sus servidores de archivos basados en Windows Server; específicamente, están usando la propiedad de clasificación FCI denominada Información de identificación **personal** con valores posibles de **High**, **Moderate**, **Low**, **Public** y **Not PII**. Ahora quieren usar su clasificación fci existente en sus directivas DLP en Office 365.

En primer lugar, siguen los pasos anteriores para crear una propiedad administrada en SharePoint Online, que se asigna a la propiedad rastreada creada automáticamente a partir de la propiedad FCI.

A continuación, crean una directiva DLP con dos reglas que usan la condición **Propiedades de documento que contienen cualquiera de estos valores:**

- **Contenido de PII de FCI: alto, moderado** La primera regla restringe el acceso al documento si la propiedad de  clasificación FCI Información de identificación **personal** es igual a **Alta** o Moderada y el documento se comparte con personas ajenas a la organización.

- **Contenido DE FCI PII: bajo** La segunda regla envía una notificación al propietario del documento si la propiedad de clasificación FCI Información de identificación **personal** es igual a **Low** y el documento se comparte con personas ajenas a la organización.

### <a name="create-the-dlp-policy-by-using-powershell"></a>Crear la directiva DLP con PowerShell

La condición **Propiedades del** documento que contienen cualquiera de estos valores no está disponible temporalmente en la interfaz de usuario del Centro de cumplimiento de seguridad, pero aún puede usar esta condición mediante &amp; PowerShell. Puede usar los cmdlets para trabajar con una directiva DLP y usar los cmdlets con el parámetro para agregar la condición Las propiedades del documento  `New\Set\Get-DlpCompliancePolicy` contienen cualquiera de estos  `New\Set\Get-DlpComplianceRule`  `ContentPropertyContainsWords` **valores**.

Para obtener más información sobre estos cmdlets, consulte [Security &amp; Compliance Center cmdlets](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).

1. [Conectarse al Centro de &amp; cumplimiento de seguridad con PowerShell remoto](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Cree la directiva mediante  `New-DlpCompliancePolicy` .

Este PowerShell crea una directiva DLP que se aplica a todas las ubicaciones.

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. Cree las dos reglas descritas anteriormente mediante , donde una regla es para el valor Low y otra para los `New-DlpComplianceRule` **valores High** y **Moderate.** 

   Este es un ejemplo de PowerShell que crea estas dos reglas. Los pares nombre/valor de la propiedad están entre comillas y un nombre de propiedad puede especificar varios valores separados por comas sin espacios, como  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Windows Server FCI incluye muchas propiedades integradas, incluida la información de identificación **personal** usada en este ejemplo. Los valores posibles para cada propiedad pueden ser diferentes para cada organización. Los **valores High**, **Moderate** y **Low** usados aquí son solo un ejemplo. Para tu organización, puedes ver las propiedades de clasificación fci de Windows Server con sus valores posibles en el Administrador de recursos del servidor de archivos en el servidor de archivos basado en Windows Server. Para obtener más información, vea [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).

Cuando termine, la directiva debe tener dos reglas nuevas que usen las propiedades **Document que contengan cualquiera de estos valores.** Esta condición no aparecerá en la interfaz de usuario, aunque aparecerán las demás condiciones, acciones y configuración.

Una regla bloquea el acceso al contenido donde la propiedad **Información de identificación personal** es igual a **Alto** o **Moderado**. Una segunda regla envía una notificación sobre el contenido donde la propiedad **Información de identificación personal** es igual a **Bajo**.

![Cuadro de diálogo de nueva directiva DLP que muestra dos reglas recién creadas](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>Después de crear la directiva DLP

Al seguir los pasos de las secciones anteriores, se creará una directiva DLP que detectará rápidamente el contenido con esa propiedad, pero solo si ese contenido se acaba de cargar (de modo que el contenido esté indexado) o si ese contenido es antiguo pero recién editado (para que el contenido se vuelva a indizar).

Para detectar contenido con esa propiedad en todas partes, tal vez le convenga solicitar de forma manual que la biblioteca, sitio o colección de sitios se vuelva a indexar para que la directiva DLP tenga conocimiento de todo el contenido que incluye esa propiedad. En SharePoint Online, el contenido se rastrea automáticamente según una programación de rastreo definida. El rastreador toma el contenido que ha cambiado desde el último rastreo y actualiza el índice. Si necesita que la directiva DLP proteja contenido antes del siguiente rastreo programado, puede llevar a cabo estos pasos.

> [!CAUTION]
> Volver a indexar un sitio puede provocar una carga masiva en el sistema de búsqueda. No vuelva a indizar el sitio a menos que el escenario lo requiera absolutamente.

Para obtener más información, vea [Solicitar manualmente el rastreo y una nueva indexación de un sitio, una biblioteca o una lista](https://go.microsoft.com/fwlink/p/?LinkID=627457).

### <a name="reindex-a-site-optional"></a>Reindexar un sitio (opcional)

1. En el sitio, elija **Configuración** (icono de engranaje en la parte superior derecha) \> **Configuración del sitio**.

2. En **Buscar,** elija **Buscar y disponibilidad sin conexión** \> **Reindexar sitio**.

## <a name="more-information"></a>Más información

- [Información general sobre las directivas de prevención de pérdida de datos](data-loss-prevention-policies.md)

- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)

- [Enviar notificaciones y mostrar sugerencias de directivas para directivas DLP](use-notifications-and-policy-tips.md)

- [Qué incluyen las plantillas de directiva DLP](what-the-dlp-policy-templates-include.md)

- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
