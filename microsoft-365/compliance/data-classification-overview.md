---
title: Obtenga información sobre la clasificación de datos.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: El panel de clasificación de datos le permite ver la cantidad de información confidencial que se ha encontrado y clasificado en la organización.
ms.openlocfilehash: 2e9d9a2581a5a2dd94dbfa32e3105486999f4b6b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153131"
---
# <a name="learn-about-data-classification"></a>Obtenga información sobre la clasificación de datos.

Como administrador de Microsoft 365 o administrador de cumplimiento, puede evaluar y etiquetar el contenido de la organización para controlar el lugar al que se dirige, protegerlo sin importar su ubicación y garantizar que se conserve y elimine en función de las necesidades de su organización. Para ello, puede aplicar [etiquetas de confidencialidad](sensitivity-labels.md) y [etiquetas de retención](retention.md#retention-labels) y clasificar la información según el tipo de confidencialidad. Hay varias formas de llevar a cabo la detección, la evaluación y el etiquetado, pero es posible que el resultado final sea un gran número de documentos y mensajes de correo electrónico marcados y clasificados con una o ambas etiquetas. Después de aplicar las etiquetas de retención y de confidencialidad, le interesará ver cómo se utilizan las etiquetas en el espacio empresarial y qué se hace con esos elementos. La página de clasificación de datos ofrece información sobre ese contenido, en particular:

- el número de elementos que se han clasificado como tipo de información sensible y cuáles son esas clasificaciones;
- las etiquetas principales de confidencialidad aplicadas en Microsoft 365 y Azure Information Protection;
- las etiquetas principales de retención aplicadas
- un resumen de las actividades que los usuarios llevan a cabo con el contenido confidencial;
- las ubicaciones de los datos confidenciales y retenidos.

También puede administrar estas características en la página de clasificación de datos:

- [clasificadores que se pueden entrenar](classifier-learn-about.md)
- [tipos de información confidencial](sensitive-information-type-learn-about.md)
- [coincidencias exactas de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [explorador de contenido](data-classification-content-explorer.md)
- [explorador de actividad](data-classification-activity-explorer.md)

Puede encontrar la clasificación de los datos en el **Centro de cumplimiento de Microsoft 365** o en el **Centro de seguridad de Microsoft 365** > **Clasificación** > **Clasificación de datos**.

Participe en un recorrido en vídeo de nuestras características de clasificación de datos.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

La clasificación de datos analizará su contenido confidencial y el contenido etiquetado antes de crear ninguna directiva. Esto se denomina **administración de cambios de zero**. Esto le permite ver el impacto que las etiquetas de confidencialidad y retención están teniendo en su entorno para que pueda comenzar con la evaluación de sus necesidades de protección y directivas de gobernanza de datos.

## <a name="prerequisites"></a>Requisitos previos

### <a name="permissions"></a>Permissions

 Para obtener acceso a la página de clasificación de datos, una cuenta debe tener asignada una suscripción en cualquiera de estos roles o grupos de roles.

**Grupos de roles de Microsoft 365**

- Administrador global
- Administrador de cumplimiento
- Administrador de seguridad
- Administrador de datos de cumplimiento

> [!NOTE]
> Como procedimiento recomendado, use siempre el rol con privilegios mínimos para conceder acceso a la clasificación de datos de Microsoft 365.

## <a name="sensitive-information-types-used-most-in-your-content"></a>Tipos de información confidencial más usados en el contenido.

Microsoft 365 dispone de un gran número de definiciones de tipos de información confidencial, como, por ejemplo, para elementos que contengan números de la seguridad social o números de tarjetas de crédito. Para obtener más información sobre los tipos de información confidencial, consulte [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md).

En la tarjeta del tipo de información confidencial se muestran los tipos de información confidencial principales que se han encontrado y etiquetado en la organización.

![tipos principales de información confidencial.](../media/data-classification-sens-info-types-card.png)

Para averiguar cuántos elementos hay en una categoría de clasificación determinada, mueva el puntero sobre la barra de la categoría.

![detalle de los tipos principales de información confidencial.](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> Si la tarjeta muestra el mensaje "No se encontraron datos con información confidencial" significa que no hay ningún elemento de la organización que se haya clasificado como un tipo de información confidencial o que no se ha rastreado ningún elemento. Para comenzar a usar las etiquetas, consulte:
>- [Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md)
>- [Introducción a las directivas de retención y las etiquetas de retención](get-started-with-retention.md)
>- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a>Etiquetas principales de confidencialidad que se aplican al contenido

Al aplicar una etiqueta de confidencialidad a un elemento a través de Microsoft 365 o de Azure Information Protection (AIP), ocurren dos cosas:

- Se incrusta en el documento una etiqueta que indica el valor que tiene el elemento para la organización y que acompañará al documento a cualquier lugar al que vaya.
- La presencia de la etiqueta habilita varios comportamientos de protección, como por ejemplo, la marca de agua o el cifrado obligatorios. Con la protección del punto de conexión habilitada, podrá incluso evitar que un elemento abandone el control de la organización.

Para obtener más información sobre las etiquetas de confidencialidad, vea: [Información general de etiquetas de confidencialidad](sensitivity-labels.md).

Las etiquetas de confidencialidad deben habilitarse para los archivos de SharePoint y OneDrive para que los datos correspondientes aparezcan en la página de clasificación de datos. Para más información, vea [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

La tarjeta de la etiqueta de confidencialidad muestra el número de elementos (correo electrónico o documento) por nivel de confidencialidad.

![captura de pantalla de marcador de posición del desglose del contenido según la clasificación de las etiquetas de confidencialidad.](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> Si no ha creado ni publicado ninguna etiqueta de confidencialidad o si el contenido no tiene ninguna etiqueta de confidencialidad aplicada, esta tarjeta mostrará el mensaje "No se ha detectado ninguna etiqueta de confidencialidad". Para empezar a usar las etiquetas de confidencialidad, consulte:
>- [Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) o, para AIP, [Configuración de la directiva de Information Protection de Azure](/azure/information-protection/configure-policy)

## <a name="top-retention-labels-applied-to-content"></a>Etiquetas principales de retención que se aplican al contenido

Las etiquetas de retención se usan para administrar la retención y la eliminación de contenido en la organización. Cuando se aplican, pueden usarse para controlar por cuánto tiempo se conservará un documento antes de ser eliminado, si debería revisarse antes de ser eliminado, cuándo expira su periodo de retención o si debería marcarse como un registro. Para obtener más información, consulte [Información sobre las etiquetas y directivas de retención](retention.md).

La tarjeta de etiquetas principales de retención aplicadas muestra el número de elementos que tienen una etiqueta de retención determinada.

![captura de pantalla de marcador de posición de etiquetas principales de retención aplicadas.](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> Si esta tarjeta muestra el mensaje "No se detectó ninguna etiqueta de retención", significa que no se ha creado ni publicado ninguna etiqueta de retención o que no se han aplicado etiquetas de retención a ningún contenido. Para empezar a usar las etiquetas de retención, vea:
>- [Introducción a las directivas y etiquetas de retención](get-started-with-retention.md)

## <a name="top-activities-detected"></a>Actividades principales detectadas

Esta tarjeta ofrece un breve resumen de las acciones más comunes que llevan a cabo los usuarios con los elementos etiquetados como confidenciales. Puede usar el [Explorador de actividad](data-classification-activity-explorer.md) para ver los detalles de las diferentes actividades de las que Microsoft 365 realiza el seguimiento en el contenido etiquetado y en el contenido que se encuentra en los puntos de conexión de Windows 10.

> [!NOTE]
> Si esta tarjeta muestra el mensaje "No se ha detectado ninguna actividad", significa que no ha habido ninguna actividad en los archivos o que no está activada la auditoría de usuarios y administradores. Para activar los registros de auditoría, vea:
>- [Buscar el registro de auditoría en el Centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a>Datos con etiquetas de confidencialidad y retención por ubicación

El informe de la clasificación de datos tiene la finalidad de ofrecer información sobre el número de elementos etiquetados y su ubicación. Estas tarjetas le permiten saber cuántos elementos etiquetados hay en Exchange, SharePoint y OneDrive, entre otros.

> [!NOTE]
> Si esta tarjeta muestra el mensaje "No se ha detectado ninguna ubicación", significa que no se ha creado ni publicado ninguna etiqueta de confidencialidad o que no hay ningún contenido con una etiqueta de retención aplicada. Para empezar a usar las etiquetas de confidencialidad, consulte:
>- [Etiquetas de confidencialidad](sensitivity-labels.md)

## <a name="public-preview-release-notes"></a>Notas de la versión preliminar pública 

> [!NOTE]
> **Recuento de buzones de Exchange**: observará que aparece una pequeña información sobre herramientas al profundizar en los buzones de Exchange. Esto sirve para llamar la atención sobre el hecho de que el recuento total mostrado sobre el tipo de información confidencial, etiquetas de confidencialidad y retención puede no coincidir exactamente con el número de elementos que se encuentran en el interior del buzón de correo. Esto se debe a la profunda exploración de la carpeta para obtener la vista en vivo del contenido, el cual es clasificado, mientras se calcula el recuento agregado. Información que el usuario debería notar incluso al echar un vistazo

> [!NOTE]
> **La representación de documentos cifrados**: los archivos de SharePoint, Exchange y OneDrive cifrados no se representan en el explorador de contenido. Este es un problema de confidencialidad que requiere de un equilibrio entre la necesidad de ver el contenido del archivo en el explorador de contenido y la necesidad de mantener el contenido cifrado. Con los permisos concedidos por los grupos de roles del **visor de listas del explorador de contenido** y el **visor del explorador de contenido**, obtendrá una vista de la lista de los archivos, los metadatos y un vínculo que puede usar para obtener acceso al contenido a través del cliente web. Información que el usuario debería notar incluso al echar un vistazo

> [!NOTE]
> **Caracteres admitidos en los nombres de etiquetas de retención en la búsqueda de SharePoint**: la búsqueda de SharePoint no admite nombres de etiquetas de retención con `-`. o `_` en ellos. Por ejemplo, `Label-MIP` y `Label_MIP` no son admitidos. La búsqueda en SharePoint admite el uso de esos caracteres en los nombres de las etiquetas de confidencialidad y en los nombres de los tipos de información confidencial.

> [!NOTE]
> **OneDrive permanece en versión preliminar**: gracias por sus valiosos comentarios sobre la integración de OneDrive durante nuestro programa de versión preliminar. Mientras trabajamos en las especificaciones, es posible que se puedan producir datos/flujos incoherentes. Seguiremos mostrando OneDrive en la versión preliminar hasta que todas las correcciones estén en su sitio. Agradecemos su apoyo continuo.

## <a name="see-also"></a>Vea también

- [Ver actividad de la etiqueta](data-classification-activity-explorer.md)
- [Ver contenido etiquetado](data-classification-content-explorer.md)
- [Más información sobre las etiquetas de confidencialidad](sensitivity-labels.md)
- [Más información sobre las directivas y las etiquetas de retención](retention.md)
- [Obtener más información acerca de los tipos de información confidencial](sensitive-information-type-learn-about.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Obtenga información sobre los clasificadores entrenables (versión preliminar)](classifier-learn-about.md)

Para obtener información sobre cómo usar la clasificación de datos para cumplir con las normativas de privacidad de datos, vea [Implementar Information Protection para las normativas de privacidad de datos con Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).