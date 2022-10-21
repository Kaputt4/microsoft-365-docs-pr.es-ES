---
title: Creación de un centro de contenido en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.custom: admindeeplinkSPO
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo crear un centro de contenido en Microsoft Syntex.
ms.openlocfilehash: aa74e6bb350074586ba233f9d88d41da2505f8ce
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660409"
---
# <a name="create-a-content-center-in-microsoft-syntex"></a>Creación de un centro de contenido en Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; Todos los modelos &ensp; | &ensp; personalizados &#10003; Todos los modelos precompilados</sup>

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>
--->

Para crear y administrar modelos empresariales, primero necesita un centro de contenido. El centro de contenido es la interfaz de creación de modelos y también contiene información sobre los modelos publicados de bibliotecas de documentos que se han aplicado.

   ![Seleccione una biblioteca de documentos.](../media/content-understanding/content-center-page.png)

Puede crear un centro de contenido predeterminado durante la [configuración](set-up-content-understanding.md). Sin embargo, un administrador de SharePoint también puede optar por crear centros adicionales según sea necesario. Aunque un único centro de contenido puede ser adecuado para entornos para los que desea una sustitución de toda la actividad del modelo, es posible que desee tener centros adicionales para varios departamentos dentro de la organización, que podrían tener necesidades y requisitos de permisos diferentes para sus modelos.

Además, si quiere probar Syntex, puede crear un centro de contenido con las instrucciones de este artículo sin comprar licencias. Los usuarios sin licencia pueden crear modelos, pero no pueden aplicarlos a una biblioteca de documentos.

> [!NOTE]
> En un [entorno de Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md), si tiene un único centro de contenido predeterminado en su ubicación central, solo puede proporcionar una implementación de la actividad del modelo desde esa ubicación. Actualmente no puede obtener una implementación de la actividad del modelo fuera de los límites de la granja de servidores en entorno Multi-Geo. 

## <a name="create-a-content-center"></a>Crear un centro de contenido

Un administrador de SharePoint puede crear un sitio del centro de contenido del mismo modo en que puede [crear cualquier otro sitio de SharePoint](/sharepoint/create-site-collection) a través del panel de aprovisionamiento del sitio del centro de administración.

Para crear un nuevo centro de contenido:

1. En el Centro de administración de Microsoft 365, vaya a los <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**sitios activos** del Centro  >  de **administración de SharePoint**</a>.

2. En la página **Sitios activos** , seleccione **Crear** y, a continuación, seleccione **Otras opciones**.

3. En el menú **Elegir una plantilla** , seleccione **Centro de contenido**.

4. Para el nuevo sitio, proporcione un **nombre de sitio**, **un administrador principal** y un **idioma**.</br>

   > [!NOTE] 
   > Puede seleccionar un sitio de centro de contenido para que se procese en cualquiera de los idiomas disponibles, pero tenga en cuenta que actualmente los modelos solo se pueden crear para archivos en inglés. Además, tenga en cuenta que, al igual que otras plantillas de sitio, el idioma predeterminado del sitio no se puede modificar una vez creado el sitio.

5. Seleccione **Terminado**.
 
Después de crear un sitio del centro de contenido, verá que aparece en <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**sitios activos**</a> en el Centro de administración de SharePoint. 

### <a name="give-access-to-additional-users"></a>Conceder acceso a otros usuarios
 
Después de crear el sitio, puede conceder acceso a usuarios adicionales al sitio a través del [modelo de permisos del sitio de SharePoint](/sharepoint/modern-experience-sharing-permissions) estándar.

### <a name="roll-up-of-models-in-the-default-content-center"></a>Acumulación de modelos en el centro de contenido predeterminado

En Syntex, el primer centro de contenido creado durante la instalación es el *centro de contenido predeterminado*. Si se crean centros de contenido posteriores, sus modelos se muestran en la vista del centro de contenido predeterminada.

![Captura de pantalla de la biblioteca de modelos en el centro de contenido predeterminado.](../media/content-understanding/model-library-default-content-center.png)

La biblioteca **Modelos** de la vista del centro de contenido predeterminada agrupa los modelos creados por el centro de contenido para obtener una vista de resumen de todos los modelos que se han creado.

> [!NOTE]
> No se puede cambiar el centro de contenido predeterminado designado. Siempre es el primer centro de contenido creado durante la instalación. 

## <a name="see-also"></a>Vea también

[Introducción a los tipos de modelo](model-types-overview.md)


