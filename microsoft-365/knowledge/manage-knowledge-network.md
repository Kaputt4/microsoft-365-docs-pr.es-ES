---
title: 'Administración de la red de administración de conocimientos (vista previa) '
description: Cómo configurar la administración del conocimiento.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: 87275dba78ab402a9ea9553198ce1a84072e3351
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540123"
---
# <a name="manage-your-knowledge-management-network-preview"></a>Administración de la red de administración de conocimientos (vista previa)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).


Después de [configurar la administración de conocimiento](set-up-knowledge-network.md), en cualquier momento, un administrador puede realizar ajustes en los valores de configuración a través del centro de administración 365 de Microsoft.

Por ejemplo, es posible que deba ajustar la configuración para cualquiera de las siguientes opciones:
- Agregar nuevos orígenes de SharePoint a los temas de mío.
- Cambiar los usuarios que tendrán acceso a los temas.
- Cambiar los usuarios que tienen permisos para realizar tareas en el centro de temas.
- Cambiar el nombre del centro de temas


## <a name="requirements"></a>Requirements 
Debe tener permisos de administrador global o de administrador de SharePoint para poder obtener acceso al centro de administración de 365 de Microsoft y administrar las tareas de conocimiento de la organización.


## <a name="to-access-knowledge-management-settings"></a>Para obtener acceso a la configuración de administración de conocimiento:

1. En el centro de administración de Microsoft 365, seleccione **instalación**y, a continuación, ver la sección de conocimientos de la **organización** .
2. En la sección conocimientos de la **organización** , haga clic en **conectar personas con el conocimiento**.<br/>

    ![Conectar a personas con el conocimiento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. En la página **conectar personas a los conocimientos** , seleccione **administrar** para abrir el panel Configuración de la red de **conocimientos** .<br/>

    ![información: configuración de la red](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>Cambiar el modo en que la red de conocimiento puede encontrar temas

Seleccione la pestaña **detección de temas** si desea actualizar las opciones para los orígenes de temas de SharePoint. Esta opción le permite seleccionar los sitios de SharePoint de su inquilino que se rastrearán y expondrán para temas.

1. En la pestaña **detección de temas** , en **seleccionar orígenes de temas de SharePoint**, seleccione **Editar**.
2. En la página **seleccionar orígenes de temas de SharePoint** , seleccione los sitios de SharePoint que se rastrearán como orígenes para los temas durante la detección. Esto incluye:</br>
    a. **Todos los sitios**: todos los sitios de SharePoint de su espacio empresarial. Esto captura los sitios actuales y futuros.</br>
    b. **Todos, excepto los sitios seleccionados**: escriba los nombres de los sitios que desea excluir.  También puede cargar una lista de sitios que desea excluir de la detección. Los sitios que se creen en el futuro se incluirán como orígenes para la detección de temas. </br>
    c. **Solo sitios seleccionados**: escriba los nombres de los sitios que desea incluir. También puede cargar una lista de sitios. Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas. </br>

    ![Elegir cómo buscar temas](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    Si tiene un número de sitios que desea excluir (si selecciona **todos, excepto los sitios seleccionados**) o incluir (si seleccionó **solo sitios seleccionados**), puede elegir cargar un archivo CSV con los nombres de sitio y las direcciones URL. Puede descargar la **plantilla del sitio download. csv** si desea usar el archivo de plantilla CSV.

3. Seleccione **Guardar**.

##  <a name="change-who-can-see-topics-in-your-organization"></a>Cambiar quién puede ver los temas de la organización

Seleccione la pestaña **detección de temas** si desea actualizar quién en su organización puede ver temas descubiertos en los resultados de la búsqueda y cuándo los temas están resaltados en contenido, como las páginas de SharePoint.

1. En la pestaña **detección de temas** , en **quién puede ver los temas de la red de conocimiento**, seleccione **Editar**.
2. En la página **quién puede ver los temas en la red de conocimiento** , elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas. Puede seleccionar:</br>
    a. **Todos en su organización**</br>
    b. **Solo personas seleccionadas o grupos de seguridad**</br>
    c. **No hay nadie**</br>

    ![Quién puede ver los temas](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. Seleccione **Guardar**.  
 
> [!Note] 
> Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de administración de conocimiento podrán ver los temas.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>Cambiar quién tiene permisos para realizar tareas en el centro de temas

Seleccione la pestaña **permisos de temas** si desea actualizar quién tiene permisos para hacer lo siguiente en la página centro de temas:

- Qué usuarios pueden crear y editar temas: crear temas nuevos que no se encontraron durante la detección o editar los detalles de la página del tema existente.
- Qué usuarios pueden administrar temas: confirmar o rechazar temas descubiertos.

Para actualizar quién tiene permisos para crear y editar temas:

1. En la ficha **permisos de tema** , en **quién puede crear y editar temas**, seleccione **Editar**.</br>
2. En la página **quién puede crear y editar temas** , puede seleccionar:</br>
    a. **Todos en su organización**</br>
    b. **Solo personas seleccionadas o grupos de seguridad**</br>

    ![Creación y edición de temas](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. Seleccione **Guardar**.</br>

Para actualizar quién tiene permisos para administrar temas:

1. En la ficha **permisos de tema** , en **¿quién puede administrar temas**?, seleccione **Editar**.</br>
2. En la página **quién puede administrar temas** , puede seleccionar:</br>
    a. **Todos en su organización**</br>
    b. **Personas o grupos de seguridad seleccionados**</br>

    ![Administrar temas](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. Seleccione **Guardar**.</br>


##  <a name="update-your-topic-center-name"></a>Actualizar el nombre del centro de temas

Seleccione la pestaña **centro de temas** si desea actualizar el nombre del centro de temas. 

1. En la pestaña **centro de temas** , en nombre del centro de **temas**, seleccione **Editar**.
2. En la página **Editar nombre del centro de temas** , en el cuadro Nombre del centro de **temas** , escriba el nuevo nombre del centro de temas.
3. Seleccione **Guardar**.

    ![Editar nombre del centro de temas](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>Consulte también



  






