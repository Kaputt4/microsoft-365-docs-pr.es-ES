---
title: Crear un nuevo tema en Temas de Microsoft Viva
description: Cómo crear un nuevo tema en Temas de Microsoft Viva.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 7d1dc1af6e845ccfe2fb0e8f5701a2cd3018c308
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687536"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a>Crear un nuevo tema en Temas de Microsoft Viva

En Temas de Viva, puede crear un nuevo tema si uno no se detecta a través de la indización o si la tecnología de inteligencia artificial no encontró suficiente evidencia para establecerlo como un tema.

> [!Note] 
> Aunque la información de un tema recopilado por AI está recortada en [seguridad,](topic-experiences-security-trimming.md)tenga en cuenta que la descripción del tema y la información de personas de un tema creado manualmente es visible para todos los usuarios que tienen permisos para ver el tema. 


## <a name="requirements"></a>Requisitos

Para crear un nuevo tema, debe:
- Tener una licencia de Viva Topics.
- Tener permisos para [**quién puede crear o editar temas**](./topic-experiences-user-permissions.md). Los administradores de conocimientos pueden conceder a los usuarios este permiso en la configuración de permisos del tema Temas de Viva. 

> [!Note] 
> Los usuarios que tienen permiso para administrar temas en el centro de temas (administradores de conocimientos) ya tienen permisos para crear y editar temas.

## <a name="to-create-a-topic"></a>Para crear un tema

Puede crear un tema nuevo desde dos ubicaciones:

- Página principal del centro de  temas: cualquier usuario con licencia con el permiso Quién puede crear o  editar temas (colaboradores) puede crear un nuevo tema desde el centro de temas seleccionando el menú Nuevo y **seleccionaNdo** página Tema . 

    ![Nuevo tema del centro de temas](../media/knowledge-management/new-topic.png)  

- Página Administrar temas: cualquier  usuario con licencia que tenga permiso Quién puede administrar temas (administradores de conocimientos) puede crear un nuevo tema desde la página Administrar temas en el Centro de temas seleccionando Página Nuevo **tema**. 

    ![Nuevo tema de administrar temas](../media/knowledge-management/new-topic-topic-center.png)  

### <a name="to-create-a-new-topic"></a>Para crear un tema nuevo:

1. Seleccione la opción para crear una nueva página de temas en la cinta de opciones de la página Administrar temas.

2.  En la **sección Nombre de este tema,** escriba el nombre del nuevo tema.

    ![Asigne a este tema un nombre](../media/knowledge-management/k-new-topic-page.png)  

3. En la **sección Nombres alternativos,** escriba cualquier otro nombre al que se pueda hacer referencia al tema. 

    ![Nombres alternativos](../media/knowledge-management/alt-names.png)  

4. En la **sección** Descripción, escriba un par de oraciones que describan el tema. 

    ![Descripción del tema](../media/knowledge-management/description.png)

4. En la **sección Personas** ancladas, puede "anclar" a una persona para que muestre que tiene una conexión con el tema (por ejemplo, un propietario de un recurso conectado). Comience escribiendo su nombre o dirección de correo electrónico en el cuadro Agregar un nuevo usuario y, **a** continuación, seleccione el usuario que desea agregar de los resultados de la búsqueda. También puede "desanclarlos" seleccionando el icono Quitar **de la** lista en la tarjeta de usuario. También puede arrastrar la persona a otro lugar de la lista.
 
    ![Personas ancladas](../media/knowledge-management/pinned-people.png)

5. En la **sección Archivos anclados y** páginas, puede agregar o "anclar" un archivo o página de sitio de SharePoint que esté asociado al tema.

   ![Páginas y archivos anclados](../media/knowledge-management/pinned-files-and-pages.png)
 
    Para agregar un nuevo archivo, seleccione **Agregar**, seleccione el sitio de SharePoint de los sitios Frecuentes o Seguidos y, a continuación, seleccione el archivo de la biblioteca de documentos del sitio.

    También puede usar la opción **De un vínculo** para agregar un archivo o página proporcionando la dirección URL. 

    > [!Note] 
    > Los archivos y las páginas que agregue deben encontrarse en el mismo inquilino de Microsoft 365. Si desea agregar un vínculo a un recurso externo en el tema, puede agregarlo a través del icono de lienzo en el paso 8.


6.  La **sección Sitios relacionados** muestra los sitios que tienen información sobre el tema. 

    ![Sección Sitios relacionados](../media/knowledge-management/related-sites.png)

    Puede agregar un sitio relacionado  seleccionando Agregar y, a continuación, buscando el sitio o seleccionándolo en la lista de sitios frecuentes o recientes.
    
    ![Seleccionar sitio](../media/knowledge-management/sites.png)

7. La **sección Temas relacionados** muestra las conexiones que existen entre los temas. Puede agregar una conexión a otro tema seleccionando el botón Conectarse a un tema relacionado y, **a** continuación, escribiendo el nombre del tema relacionado y seleccionándose en los resultados de la búsqueda. 

   ![Temas relacionados](../media/knowledge-management/related-topic.png)  

    A continuación, puede proporcionar una descripción de cómo están relacionados los temas y seleccionar **Actualizar**.

   ![Descripción de temas relacionados](../media/knowledge-management/related-topics-update.png) 

   El tema relacionado que agregó se mostrará como un tema conectado.

   ![Temas relacionados conectados](../media/knowledge-management/related-topics-final.png) 

   Para quitar un tema relacionado, seleccione el tema que desea quitar y, a continuación, seleccione el **icono Quitar** tema.
 
   ![Quitar tema relacionado](../media/knowledge-management/remove-related.png)  

   A continuación, **seleccione Quitar**.

   ![Confirmar quitar](../media/knowledge-management/remove-related-confirm.png) 

8. También puedes agregar elementos estáticos a la página (como texto, imágenes o vínculos) seleccionando el icono del lienzo, que puedes encontrar debajo de la breve descripción. Si lo selecciona, se abrirá el cuadro de herramientas de SharePoint desde el que puede elegir el elemento que desea agregar a la página.

   ![Icono de lienzo](../media/knowledge-management/webpart-library.png) 

9. Seleccione **Publicar** para guardar los cambios. 

Después de publicar la página, el nombre del tema, el nombre alternativo, la descripción y las personas ancladas se mostrarán a todos los usuarios con licencia que ven el tema. Los archivos, páginas y sitios específicos solo aparecerán en la página del tema si el visor tiene permisos de Office 365 para el elemento. 



## <a name="see-also"></a>Consulte también



