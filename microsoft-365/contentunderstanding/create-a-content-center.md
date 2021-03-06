---
title: Crear un centro de contenido en Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenga información sobre cómo crear un centro de contenido.
ms.openlocfilehash: 3544bbef7cf2f898733c7aaad620487098a2dd24
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515141"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Crear un centro de contenido en Microsoft SharePoint Syntex


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

Para crear y administrar modelos de comprensión de documentos, primero necesita un centro de contenido. El centro de contenido es la interfaz de creación de modelos y también contiene información sobre los modelos publicados de bibliotecas de documentos que se han aplicado.</br>

   ![Seleccione una biblioteca de documentos](../media/content-understanding/content-center-page.png)</br>

Puede crear un centro de contenido predeterminado durante la [configuración](set-up-content-understanding.md). Sin embargo, un administrador de SharePoint también puede optar por crear centros adicionales según sea necesario. Mientras que un único centro de contenido puede ser apropiado para entornos en los que quiera realizar una implementación de todas las actividades del modelo, es posible que quiera disponer de centros adicionales para los distintos departamentos de su organización, que pueden tener distintos requisitos de permisos y necesidades para sus modelos.

> [!NOTE]
> En un [entorno de Microsoft 365 Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo), si tiene un único centro de contenido predeterminado en su ubicación central, solo puede proporcionar una implementación de la actividad del modelo desde esa ubicación. Actualmente no puede obtener una implementación de la actividad del modelo fuera de los límites de la granja de servidores en entorno Multi-Geo. 


## <a name="create-a-content-center"></a>Crear un centro de contenido

Un administrador de SharePoint puede crear un sitio del centro de contenido del mismo modo en que puede [crear cualquier otro sitio de SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) a través del panel de aprovisionamiento del sitio del centro de administración.

Para crear un nuevo centro de contenido:

1. En el Centro de administración de Microsoft 365, vaya al Centro de administración de SharePoint.

2. En el nuevo Centro de administración de SharePoint, en **Sitios**, seleccione **Sitios activos**.

3. En la página **Sitios activos**, haga clic en **Crear** y seleccione **Otras opciones**.

4. En el menú **Elegir una plantilla**, seleccione **Centro de contenido**.

5. Para el nuevo sitio, proporcione un **Nombre del sitio**, **Administrador principal** e **Idioma**.</br>

   > [!NOTE] 
   > Puede seleccionar un sitio de centro de contenido para que se procese en cualquiera de los idiomas disponibles, pero tenga en cuenta que actualmente los modelos solo se pueden crear para archivos en inglés. Además, tenga en cuenta que, al igual que otras plantillas de sitio, el idioma predeterminado del sitio no se puede modificar una vez creado el sitio.</br>

6. Seleccione **Terminado**.
 
Después de crear un sitio del centro de contenido, verá que aparece en la página **Sitios activos** en el Centro de administración de SharePoint. 

### <a name="give-access-to-additional-users"></a>Conceder acceso a otros usuarios
 
Después de crear el sitio, puede conceder acceso a usuarios adicionales al sitio a través del [modelo de permisos del sitio de SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions) estándar.

## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Crear un centro de contenido](create-a-content-center.md)

[Información general sobre la comprensión de documentos](document-understanding-overview.md)

[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)

[Aplicar un modelo](apply-a-model.md)    
