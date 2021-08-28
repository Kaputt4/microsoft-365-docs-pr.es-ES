---
title: Crear un nuevo tema en Temas Microsoft Viva
ms.author: chucked
author: chuckedmonson
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
description: Obtenga información sobre cómo crear un nuevo tema en Temas Microsoft Viva.
ms.openlocfilehash: af4a56b98cd3e372cee242bb98742ba488a1f2b4
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58572664"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a>Crear un nuevo tema en Temas Microsoft Viva

En Temas de Viva, puede crear un nuevo tema si uno no se detecta a través de la indización o si la tecnología de inteligencia artificial no encontró suficiente evidencia para establecerlo como un tema.

> [!Note] 
> Aunque la información de un tema recopilado por AI está recortada en [seguridad,](topic-experiences-security-trimming.md)tenga en cuenta que la descripción del tema y la información de personas de un tema creado manualmente es visible para todos los usuarios que tienen permisos para ver el tema. 


## <a name="requirements"></a>Requisitos

Para crear un nuevo tema, debe:
- Tener una licencia de Temas Microsoft Viva.
- Tener permisos para [**Quién crear o editar temas**](./topic-experiences-user-permissions.md). Los administradores del conocimientos pueden conceder a los usuarios este permiso en la configuración de permisos del tema de Temas Viva. 

> [!Note] 
> Los usuarios que tienen permiso para administrar temas en el centro de temas (administradores de conocimientos) ya tienen permisos para crear y editar temas.

## <a name="to-create-a-topic"></a>Para crear un tema

Puede crear un tema nuevo desde dos ubicaciones:

- Página principal del centro de temas: cualquier usuario con licencia con **el Quién** puede crear o editar el  permiso de temas (colaboradores) puede crear un nuevo tema desde el centro de temas seleccionando el menú Nuevo y **seleccionaNdo** página Tema . 

    ![Nuevo tema del centro de temas.](../media/knowledge-management/new-topic.png)  

- Página Administrar temas: cualquier usuario con licencia que tenga **Quién** puede administrar el permiso de temas (administradores de conocimientos) puede crear un nuevo tema desde la página Administrar temas en el Centro de temas seleccionando Página nuevo **tema**. 

    ![Nuevo tema de administrar temas.](../media/knowledge-management/new-topic-topic-center.png)  

### <a name="to-create-a-new-topic"></a>Para crear un tema:

1. Seleccione la opción para crear una Página de tema en la cinta de opciones de la página Administrar temas.

2.  En la sección **Dé un nombre a este tema**, escriba el nombre del nuevo tema.

    ![Asigne a este tema el nombre.](../media/knowledge-management/k-new-topic-page.png)  

3. En la sección **Nombres alternativos**, escriba cualquier otro nombre con el que se pueda hacer referencia al tema. 

    ![Nombres alternativos.](../media/knowledge-management/alt-names.png)  

4. En la **sección** Descripción, escriba un par de oraciones que describan el tema. 

    ![Descripción del tema.](../media/knowledge-management/description.png)

4. En la **sección Personas** ancladas, puede "anclar" a una persona para que muestre que tiene una conexión con el tema (por ejemplo, un propietario de un recurso conectado). Para empezar, escriba su nombre o dirección de correo electrónico en el cuadro para **agregar un nuevo usuario** y, después, seleccione el usuario que quiera agregar en los resultados de la búsqueda. También puede "desanclarlos" seleccionando el icono Quitar **de la** lista en la tarjeta de usuario. También puede arrastrar la persona a otro lugar de la lista.
 
    ![Personas ancladas.](../media/knowledge-management/pinned-people.png)

5. En la sección de **Archivos y páginas anclados**, agregue o "ancle" un archivo o página de sitio de SharePoint asociada con el tema.

   ![Archivos anclados y páginas.](../media/knowledge-management/pinned-files-and-pages.png)
 
    Para agregar un nuevo archivo, seleccione **Agregar**, seleccione el sitio SharePoint de los sitios Frecuentes o Seguidos y, a continuación, seleccione el archivo de la biblioteca de documentos del sitio.

    También puede usar la opción **Desde un vínculo** para agregar un archivo o una página proporcionando la dirección URL. 

    > [!Note] 
    > Los archivos y las páginas que agregue deben encontrarse en el mismo Microsoft 365 inquilino. Si desea agregar un vínculo a un recurso externo en el tema, puede agregarlo a través del icono de lienzo en el paso 8.


6.  En la sección **Sitios relacionados** se muestran los sitios con información sobre el tema. 

    ![Sección Sitios relacionados.](../media/knowledge-management/related-sites.png)

    Puede agregar un sitio relacionado  seleccionando Agregar y, a continuación, buscando el sitio o seleccionándolo en la lista de sitios frecuentes o recientes.
    
    ![Seleccione sitio.](../media/knowledge-management/sites.png)

7. La **sección Temas relacionados** muestra las conexiones que existen entre los temas. Para agregar una conexión a otro tema, seleccione el **Conectar a** un botón de tema relacionado y, a continuación, escriba el nombre del tema relacionado y selecciónelo en los resultados de la búsqueda. 

   ![Temas relacionados.](../media/knowledge-management/related-topic.png)  

    A continuación, puede proporcionar una descripción de cómo están relacionados los temas y seleccionar **Actualizar**.

   ![Descripción de temas relacionados.](../media/knowledge-management/related-topics-update.png) 

   El tema relacionado que agregó se mostrará como un tema conectado.

   ![Temas relacionados conectados.](../media/knowledge-management/related-topics-final.png) 

   Para quitar un tema relacionado, seleccione el tema que desea quitar y, a continuación, seleccione el **icono Quitar** tema.
 
   ![Quitar tema relacionado.](../media/knowledge-management/remove-related.png)  

   A continuación, **seleccione Quitar**.

   ![Confirme quitar.](../media/knowledge-management/remove-related-confirm.png) 

8. También puedes agregar elementos estáticos a la página (como texto, imágenes o vínculos) seleccionando el icono del lienzo, que puedes encontrar debajo de la breve descripción. Si lo selecciona, se abrirá SharePoint cuadro de herramientas desde el que puede elegir el elemento que desea agregar a la página.

   ![Icono de lienzo.](../media/knowledge-management/webpart-library.png) 

9. Seleccione **Publicar** para guardar los cambios. 

Después de publicar la página, se mostrarán el nombre del tema, el nombre alternativo, la descripción y las personas ancladas a todos los usuarios con licencia que visualicen el tema. Los archivos, páginas y sitios específicos solo aparecerán en la página del tema si la persona que lo mira tiene permisos de Office 365 para el elemento. 



## <a name="see-also"></a>Consulte también



