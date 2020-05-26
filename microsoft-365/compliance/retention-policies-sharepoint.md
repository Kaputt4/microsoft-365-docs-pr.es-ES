---
title: Más información sobre las directivas de retención para SharePoint y OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Más información sobre las directivas de retención que se aplican a SharePoint y OneDrive.
ms.openlocfilehash: f3c7d805309a86f05cdea8769693ec6de9c1bf51
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292503"
---
# <a name="learn-about-retention-policies-for-sharepoint-and-onedrive"></a>Más información sobre las directivas de retención para SharePoint y OneDrive

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La información de este artículo complementa[Más información sobre las directivas de retención](retention-policies.md)porque tiene información específica de SharePoint y OneDrive.

## <a name="how-a-retention-policy-works-with-sharepoint-and-onedrive"></a>Cómo funciona una directiva de retención con SharePoint y OneDrive

Las directivas de retención se aplican en el nivel de la colección de sitios. Si incluye una colección de sitios de SharePoint o una cuenta de OneDrive en una directiva de retención, se crea una biblioteca de suspensión para conservación, si no existe una. Puede ver esta biblioteca en la página **Contenidos del sitio** en el sitio de nivel superior de la colección de sitios. La mayoría de los usuarios no puede ver la biblioteca de suspensión para conservación porque solo es visible para los administradores de la colección de sitios.
  
Si una persona intenta cambiar o eliminar el contenido de un sitio que está sujeto a una directiva de retención, en primer lugar, la Directiva comprueba si el contenido se ha cambiado desde que se aplicó la Directiva. Si esta es la primera vez que se ha aplicado la Directiva, la Directiva de retención copia el contenido a la biblioteca de conservación de documentos y, a continuación, permite a la persona cambiar o eliminar el contenido original. El contenido de la colección de sitios puede copiarse en la biblioteca de suspensión para conservación, incluso si el contenido no coincide con la consulta usada por la Directiva de retención.
  
Un trabajo de temporizador limpia periódicamente la biblioteca de suspensión para conservación. Este trabajo compara todo el contenido de la biblioteca de suspensión para conservación con todas las consultas utilizadas por las directivas de retención del sitio. El contenido que es más antiguo que su período de retención configurado se elimina de la biblioteca de suspensión para conservación, y la ubicación original si todavía está allí. Este trabajo de temporizador se ejecuta cada 7 días, lo que significa que puede tomar hasta 7 días para que el contenido sea eliminado.
  
Este comportamiento se aplica al contenido que existe cuando se aplica la directiva de retención. Además, cualquier contenido nuevo que se cree o agregue a la colección de sitios después de que se incluya en la directiva se conservará después de la eliminación. Sin embargo, el contenido nuevo no se copia en la biblioteca de suspensión para conservación la primera vez que se edita, solo cuando se elimina. Para conservar todas las versiones de un archivo, debe activar el[control de versiones](#how-a-retention-policy-works-with-document-versions-in-a-site-collection).
  
Un usuario recibe un error si intenta eliminar una biblioteca, lista, carpeta o sitio que está sujeto a una directiva de retención. Un usuario puede eliminar una carpeta, si primero se mueven o eliminan los archivos en la carpeta que están sujetos a la directiva. Además, la biblioteca de retención de preservación se crea en esta etapa, y no cuando se crea la directiva de retención. Esto significa que para probar su directiva, primero debe editar o eliminar un documento de un sitio que esté sujeto a la directiva de retención, y luego navegar hasta la biblioteca de retención de preservación para ver la copia retenida.
  
Cuando se asigna una directiva de retención a una cuenta de OneDrive o un sitio de SharePoint, las rutas de acceso que realiza el contenido dependen de si la directiva de retención es retener y eliminar, solo retener o solo eliminar.

Cuando la directiva de retención es retener y eliminar:

![Diagrama del ciclo de vida de contenido en SharePoint y OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Si el contenido se ha modificado o eliminado** durante el periodo de retención, se crea en la biblioteca de suspensión para conservación una copia del contenido original tal como era cuando se asignó la directiva de retención. Allí, el trabajo del temporizador identifica los artículos cuyo período de retención ha expirado. Esos artículos se mueven a la segunda etapa de la Papelera de reciclaje, donde se borran permanentemente al final de los 93 días. La papelera de reciclaje de la segunda etapa no es visible para los usuarios finales (solo la papelera de reciclaje de primer nivel), pero los administradores de colecciones de sitios pueden ver y restaurar el contenido desde allí.

    > [!NOTE]
    > Para ayudar a evitar la pérdida accidental de datos, ya no se elimina permanentemente el contenido de la biblioteca de conservación de documentos. Ahora solo eliminamos de forma permanentemente el contenido de la Papelera de reciclaje. Todo el contenido de la biblioteca de suspensión para conservación pasa por la Papelera de reciclaje de segundo nivel.
    
2. **Si no se modifica ni elimina el contenido** durante el período de retención, el trabajo del temporizador mueve este contenido a la primera etapa de la Papelera de reciclaje al final del período de retención. Si un usuario elimina el contenido desde allí o vacía esta papelera de reciclaje (lo que también se conoce como purgar), el documento se mueve a la Papelera de reciclaje de segundo nivel. Un período de retención de 93 días abarca las papeleras de reciclaje de primera y segunda etapa. Al final de 93 días, el documento se elimina de forma permanente de donde se encuentre, ya sea en la papelera de reciclaje de primer nivel o de segundo nivel. La papelera de reciclaje no está indexada y, por lo tanto, no está disponible para la búsqueda. Como resultado, una búsqueda de eDiscovery no puede encontrar ningún contenido en la papelera de reciclaje para el que aplicar una retención.

Cuando la directiva de retención es de solo retención, o solo eliminación, las rutas de acceso de contenido son variaciones de retener y eliminar:

#### <a name="content-paths-for-retain-only-retention-policy"></a>Rutas de contenido para la directiva de retención de solo retención

1. **Si el contenido se modifica o se elimina** durante el período de retención, una copia del documento original se crea en la biblioteca de suspensión para conservación y se conserva hasta el final del período de retención, cuando la copia de la biblioteca de suspensión para conservación se mueve a la Papelera de reciclaje de segundo nivel y se elimina de forma permanente después de 93 días.

2. **Si el contenido no se modifica ni elimina** durante el período de retención, no sucede nada antes y después del período de retención; el documento permanece en su ubicación original.

#### <a name="content-paths-for-delete-only-retention-policy"></a>Rutas de contenido para la directiva de retención de solo eliminación

1. **Si el contenido se elimina** durante el período configurado: el documento es trasladado a la primera etapa de la Papelera de reciclaje. Si un usuario elimina el documento desde allí o vacía esta Papelera de reciclaje, el documento se mueve a la Papelera de reciclaje de segundo nivel. Un período de retención de 93 días abarca las Papeleras de reciclaje de primer nivel y de segundo nivel. Después de 93 días, el documento se elimina de forma permanente de donde se encuentre, ya sea en la Papelera de reciclaje de primer nivel o de segundo nivel. Si el contenido se modifica durante el período configurado, sigue la misma ruta de eliminación después del período configurado.

2. **Si el contenido no se elimina** durante el período configurado: al final del período configurado en la directiva de retención, el documento se traslada a la primera etapa de la Papelera de reciclaje. Si un usuario elimina el documento desde allí o vacía esta papelera de reciclaje (lo que también se conoce como purgar), el documento se mueve a la Papelera de reciclaje de segundo nivel. Un período de retención de 93 días abarca las Papeleras de reciclaje de primer nivel y de segundo nivel. Después de 93 días, el documento se elimina de forma permanente de donde se encuentre, ya sea en la Papelera de reciclaje de primer nivel o de segundo nivel. La papelera de reciclaje no está indexada y, por lo tanto, no está disponible para la búsqueda. Como resultado, una búsqueda de eDiscovery no puede encontrar ningún contenido en la papelera de reciclaje para el que aplicar una retención.
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>Funcionamiento de una directiva de retención con versiones de documentos de un sitio

El versionado es una característica de todas las bibliotecas de documentos en SharePoint y OneDrive. De forma predeterminada, el control de versiones retiene un mínimo de 500 versiones principales, aunque puede aumentar este límite. Para obtener más información, vea [Habilitar y configurar el control de versiones para una lista o biblioteca](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).
  
Una directiva de sólo retención conserva todas las versiones de un documento en una colección del sitio de SharePoint o en una cuenta de OneDrive. Cuando se edita por primera vez un documento que está sujeto a una directiva de retención o sólo de retención, se copia una versión del documento original en la biblioteca de retención de preservación. Cuando se elimina un documento que está sujeto a una directiva de retención o sólo de retención, todas las versiones se copian a la biblioteca de retención de preservación si la función de versiones está activada. Cada versión de un documento de la Biblioteca de conservación de documentos es un elemento independiente con un periodo de retención distinto:
  
- Si la directiva de retención se basa en la fecha de creación del contenido, cada versión tiene la misma fecha de vencimiento que el documento original. El documento original y sus versiones expiran al mismo tiempo.
    
- Si la directiva de retención se basa en la fecha de última modificación del contenido, cada versión contará con su propia fecha de expiración en función de cuándo se modificó el documento original para crear esa versión. Los documentos originales y sus versiones expiran independientemente los unos de los otros.

> [!NOTE]
> Las versiones preservadas de los documentos de SharePoint y OneDrive no se pueden buscar con las herramientas de eDiscovery.

### <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización 

**SharePoint**:

Cuando un usuario deja la organización, no se verá afectado el contenido creado por el usuario, ya que SharePoint se considera un entorno de colaboración, al contrario que el buzón de un usuario o la cuenta de OneDrive.

**OneDrive**:

Si un usuario abandona su organización, cualquier archivo que esté sujeto a una directiva de retención o que tenga una etiqueta de retención permanecerá durante la duración de la directiva o la etiqueta. Durante ese período de tiempo, todo el acceso para compartir sigue funcionando. Cuando expire el período de retención, el contenido se mueve a la Papelera de reciclaje de la Colección de sitios y no es accesible para nadie excepto el administrador. Si un documento está marcado con una directiva de retención como registro, no se eliminará hasta que finalice el período de retención, tras lo cual el contenido se eliminará de forma permanente. 

## <a name="how-to-configure-a-retention-policy-for-sharepoint-and-onedrive"></a>Cómo configurar una directiva de retención para SharePoint y OneDrive

Consulte [Crear y configurar directivas de retención ](create-retention-policies.md).

Para la página**Elegir ubicaciones **del asistente, seleccione una de las siguientes opciones:

- ** Aplicar la directiva sólo al contenido del correo electrónico de Exchange, las carpetas públicas, los grupos de Office 365, los documentos de OneDrive y SharePoint**

- **Permitirme elegir ubicaciones específicas** > **sitios de SharePoint** o **cuentas de OneDrive**

### <a name="sharepoint-locations"></a>Ubicaciones de SharePoint 

Su directiva de retención puede retener contenido en los sitios de comunicación de SharePoint, en los sitios de grupo no conectados por grupos de Office 365 y en los sitios clásicos. Los sitios de grupo conectados por los grupos de Office 365 no son compatibles con esta opción. En su lugar, use las ubicaciones de **los grupos de Office 365**. 

Si especifica sitios que no son compatibles, estos sitios son ignorados por la directiva de retención. 

Cuando especifica sus ubicaciones para los sitios de SharePoint, no necesita permisos para tener acceso al sitio y no se lleva a cabo ninguna validación en el momento en que especifica la dirección URL en la página **Editar ubicaciones**. Sin embargo, estos sitios se deben indexar y al final del asistente se comprueba que existan los sitios que usted especifica. 

Si se produce un error en esta comprobación, verá un mensaje que indica que no se pudo realizar la validación de la dirección URL que ha indicado y el asistente no creará la directiva de retención hasta que se supere la comprobación de validación.  Si ve este mensaje, vuelva al Asistente para cambiar la dirección URL o quitar el sitio.
