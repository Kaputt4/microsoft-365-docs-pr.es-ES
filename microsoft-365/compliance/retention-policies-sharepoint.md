---
title: Obtenga más información sobre la retención para SharePoint y OneDrive
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
description: Obtenga más información acerca de cómo funciona la retención para SharePoint y OneDrive.
ms.openlocfilehash: 3c1b2564b0ba9d96d22ab9d3b78da500b54363e2
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315793"
---
# <a name="learn-about-retention-for-sharepoint-and-onedrive"></a>Obtenga más información sobre la retención para SharePoint y OneDrive

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

La información de este artículo complementa[Obtenga más información sobre las directivas de retención](retention.md)porque tiene información específica de SharePoint y OneDrive.

## <a name="how-retention-works-for-sharepoint-and-onedrive"></a>Obtenga información acerca de cómo funciona la retención para SharePoint y OneDrive.

Para admitir la retención, SharePoint y OneDrive crean una biblioteca de conservación de documentos si no existe una. Puede ver esta biblioteca en la página **Contenidos del sitio** en el sitio de nivel superior de la colección de sitios. La mayoría de los usuarios no puede ver la biblioteca de suspensión para conservación porque solo es visible para los administradores de la colección de sitios.
  
Si alguien intenta cambiar o eliminar un documento que está sujeto a la configuración de retención, se comprueba si el contenido se ha cambiado desde que se aplicó la configuración de retención. Si este es el primer cambio desde que se aplicaron los ajustes de retención, el contenido se copia a la biblioteca de retención de preservación, lo que permite a la persona cambiar o eliminar el contenido original. El contenido de una colección de sitios puede copiarse a la biblioteca de conservación de documentos, independientemente de la configuración de retención.
  
Un trabajo de temporizador limpia periódicamente la biblioteca de suspensión para conservación. Este trabajo compara todo el contenido de la biblioteca de conservación de documentos con todas las consultas empleadas en la configuración de retención para este contenido. El contenido que es más antiguo que su período de retención configurado se elimina de la biblioteca de suspensión para conservación, y la ubicación original si todavía está allí. Este trabajo de temporizador se ejecuta cada siete días, lo que significa que el contenido puede tardar hasta siete días en eliminarse.
  
Este comportamiento se aplica al contenido que existe cuando se aplica la configuración de retención. Además, en el caso de las directivas de retención, el contenido nuevo que se cree o se agregue a la colección de sitios después de que se incluya en la directiva se conservará después de la eliminación. Sin embargo, el contenido nuevo no se copia en la biblioteca de suspensión para conservación la primera vez que se edita, solo cuando se elimina. Para conservar todas las versiones de un archivo, debe activar el[control de versiones](#how-retention-works-with-document-versions-in-a-site-collection).
  
Un usuario recibe un error si intenta eliminar una biblioteca, lista, carpeta o sitio que está sujeto a una directiva de retención. Un usuario puede eliminar una carpeta, si primero se mueven o eliminan los archivos en la carpeta que están sujetos a la directiva. Asimismo, en esta fase se crea una biblioteca de conservación de documentos y no cuando se crea una directiva de retención o se aplica una etiqueta de retención. Esto significa que para probar la retención, en primer lugar debe editar o eliminar un documento de un sitio sujeto a una directiva de retención o que tenga una etiqueta de retención aplicada y, a continuación, vaya a la biblioteca de conservación de documentos para ver la copia retenida.
  
Cuando se asigna el contenido de una cuenta de OneDrive o un sitio de SharePoint a la configuración de retención, dependen de si la configuración de retención debe retener, eliminar, solo retener o eliminar.

Cuando la configuración de retención se debe conservar y eliminar:

![Diagrama del ciclo de vida de contenido en SharePoint y OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Si el contenido se ha modificado o eliminado** durante el periodo de retención, se crea en la biblioteca de suspensión para conservación una copia del contenido original tal como era cuando se asignó la directiva de retención. Allí, el trabajo del temporizador identifica los artículos cuyo período de retención ha expirado. Esos artículos se mueven a la segunda etapa de la Papelera de reciclaje, donde se borran permanentemente al final de los 93 días. La papelera de reciclaje de la segunda etapa no es visible para los usuarios finales (solo la papelera de reciclaje de primer nivel), pero los administradores de colecciones de sitios pueden ver y restaurar el contenido desde allí.

    > [!NOTE]
    > Para ayudar a evitar la pérdida accidental de datos, ya no se elimina permanentemente el contenido de la biblioteca de conservación de documentos. Ahora solo eliminamos de forma permanentemente el contenido de la Papelera de reciclaje. Todo el contenido de la biblioteca de suspensión para conservación pasa por la Papelera de reciclaje de segundo nivel.
    
2. **Si no se modifica ni elimina el contenido** durante el período de retención, el trabajo del temporizador mueve este contenido a la primera etapa de la Papelera de reciclaje al final del período de retención. Si un usuario elimina el contenido desde allí o vacía esta papelera de reciclaje (lo que también se conoce como purgar), el documento se mueve a la Papelera de reciclaje de segundo nivel. Un período de retención de 93 días abarca las Papeleras de reciclaje de primer y de segundo nivel. Después de 93 días, el documento se elimina de forma permanente de la ubicación donde se encuentre, ya sea en la Papelera de reciclaje de primer nivel o en la de segundo nivel. La papelera de reciclaje no está indexada y, por lo tanto, no está disponible para la búsqueda. Como resultado, una búsqueda de eDiscovery no puede encontrar ningún contenido en la papelera de reciclaje para el que aplicar una retención.

Cuando los ajustes de retención son sólo de retención o sólo de borrado, las rutas de contenido son variaciones de retención y borrado:

### <a name="content-paths-for-retain-only-retention-settings"></a>Rutas de contenido para la configuración de la retención de sólo lectura

1. **Si el contenido se modifica o se elimina** durante el período de retención, una copia del documento original se crea en la biblioteca de suspensión para conservación y se conserva hasta el final del período de retención, cuando la copia de la biblioteca de suspensión para conservación se mueve a la Papelera de reciclaje de segundo nivel y se elimina de forma permanente después de 93 días.

2. **Si el contenido no se modifica ni elimina** durante el período de retención, no sucede nada antes y después del período de retención; el documento permanece en su ubicación original.

### <a name="content-paths-for-delete-only-retention-settings"></a>Rutas de contenido para la configuración de retención de solo eliminación

1. **Si el contenido se elimina** durante el período configurado: el documento es trasladado a la primera etapa de la Papelera de reciclaje. Si un usuario elimina el documento desde allí o vacía esta Papelera de reciclaje, el documento se mueve a la Papelera de reciclaje de segundo nivel. Un período de retención de 93 días abarca las Papeleras de reciclaje de primer nivel y de segundo nivel. Después de 93 días, el documento se elimina de forma permanente de donde se encuentre, ya sea en la Papelera de reciclaje de primer nivel o de segundo nivel. Si el contenido se modifica durante el período configurado, sigue la misma ruta de eliminación después del período configurado.

2. **Si el contenido no se elimina** durante el período configurado: al final del período configurado en la directiva de retención, el documento se traslada a la primera etapa de la Papelera de reciclaje. Si un usuario elimina el documento desde allí o vacía esta papelera de reciclaje (lo que también se conoce como purgar), el documento se mueve a la Papelera de reciclaje de segundo nivel. Un período de retención de 93 días abarca las Papeleras de reciclaje de primer nivel y de segundo nivel. Después de 93 días, el documento se elimina de forma permanente de donde se encuentre, ya sea en la Papelera de reciclaje de primer nivel o de segundo nivel. La papelera de reciclaje no está indexada y, por lo tanto, no está disponible para la búsqueda. Como resultado, una búsqueda de eDiscovery no puede encontrar ningún contenido en la papelera de reciclaje para el que aplicar una retención.

## <a name="how-retention-works-with-document-versions-in-a-site-collection"></a>Funcionamiento de una directiva de retención con versiones de documentos de un sitio

El versionado es una característica de todas las bibliotecas de documentos en SharePoint y OneDrive. De forma predeterminada, el control de versiones retiene un mínimo de 500 versiones principales, aunque puede aumentar este límite. Para obtener más información, consulte [Habilitar y configurar el control de versiones para una lista o biblioteca](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37) y [Cómo funciona el control de versiones en las listas y bibliotecas](https://support.microsoft.com/office/how-versioning-works-in-lists-and-libraries-0f6cd105-974f-44a4-aadb-43ac5bdfd247).
  
La configuración de conserva solo retiene todas las versiones de un documento en una colección de sitios de SharePoint o en una cuenta de OneDrive. Cuando se edita por primera vez un documento que está sujeto a una retención o que solo contiene configuraciones, se copia una versión del documento original a la biblioteca de conservación de documentos. Cuando se elimina un documento que está sujeto a una configuración de retención o de solo retención, todas las versiones se copian en la biblioteca de conservación de documentos si se habilita el control de versiones. Cada versión de un documento de la Biblioteca de conservación de documentos es un elemento independiente con un periodo de retención distinto:
  
- Si el período de retención se basa en el momento de la creación del contenido, cada versión tiene la misma fecha de caducidad que el documento original Todos los documentos originales y todas las versiones expiran al mismo tiempo.

- Si el período de retención se basa en la fecha en que se modificó el contenido por última vez, cada versión tiene su propia fecha de caducidad según la fecha en que se modificó el documento original para crear esa versión. Los documentos originales y sus versiones expiran en forma independiente uno del otro.

> [!NOTE]
> Las versiones preservadas de los documentos de SharePoint y OneDrive no se pueden buscar con las herramientas de eDiscovery.

En el caso de los elementos que están sujetos a las directivas de retención (o a una suspensión legal), los límites del control de versiones de la biblioteca de documentos se omiten hasta que se alcanza el período de retención del documento. En este escenario, las versiones antiguas no se purgan automáticamente y los usuarios no pueden eliminar versiones.

Este no es el caso de las etiquetas de retención cuando una directiva de retención no se aplica al sitio. En su lugar, se tienen en cuenta los límites del control de versiones, por lo que las versiones anteriores se eliminan automáticamente para dar lugar a nuevas versiones, pero los usuarios todavía no pueden eliminar versiones.

## <a name="when-a-user-leaves-the-organization"></a>Cuando un usuario deja la organización

**SharePoint**:

Cuando un usuario deja la organización, no se verá afectado el contenido creado por el usuario, ya que SharePoint se considera un entorno de colaboración, al contrario que el buzón de un usuario o la cuenta de OneDrive.

**OneDrive**:

Si un usuario abandona su organización, cualquier archivo que esté sujeto a una directiva de retención o que tenga una etiqueta de retención permanecerá durante la duración de la directiva o la etiqueta. Durante ese período de tiempo, todo el acceso para compartir sigue funcionando. Cuando expire el período de retención, el contenido se mueve a la papelera de reciclaje de la colección de sitios y no es accesible para nadie excepto el administrador. Si un documento está marcado con una etiqueta de retención como registro, el documento no se eliminará hasta que finalice el período de retención, tras lo cual el contenido se eliminará de forma permanente.

## <a name="configuration-guidance"></a>Instrucciones de configuración

Si está listo para configurar la retención en Microsoft 365, consulte [Introducción a las directivas y las etiquetas de retención](get-started-with-retention.md).
