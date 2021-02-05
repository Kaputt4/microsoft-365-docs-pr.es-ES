---
title: Administrar la detección de temas en temas de Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Obtenga información sobre cómo administrar la detección de temas en Temas de Microsoft Viva.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107770"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Administrar la detección de temas en temas de Microsoft Viva

Puede administrar la configuración de detección de temas en el [Centro de administración de Microsoft 365.](https://admin.microsoft.com) Debe ser administrador global o administrador de SharePoint para realizar estas tareas.

## <a name="to-access-topics-management-settings"></a>Para obtener acceso a la configuración de administración de temas:

1. En el Centro de administración de Microsoft 365, haga clic **en Configuración** y, a continuación, en Configuración de **la organización.**
2. En la **pestaña Servicios,** haga clic en **Experiencias del tema.**

    ![Conectar a las personas con el conocimiento](../media/admin-org-knowledge-options-completed.png) 

3. Seleccione la **pestaña Detección de** temas. Consulta las siguientes secciones para obtener información sobre cada configuración.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Seleccionar orígenes de temas de SharePoint

Puede cambiar los sitios de SharePoint de su organización que se rastrearán para obtener temas.

Si desea incluir o excluir una lista específica de sitios, puede usar la siguiente plantilla .csv:

``` csv
Site name,URL
```

Si agrega sitios mediante el selector de sitios, se agregan a la lista existente de sitios para incluirlos o excluirlos. Si carga un archivo .csv, sobrescribirá cualquier lista existente. Si ya ha incluido o excluido sitios específicos, puede descargar la lista como un archivo .csv, realizar cambios y cargar la nueva lista.

Para elegir sitios para la detección de temas

1. En la **pestaña Detección** de temas, en Seleccionar orígenes de temas de **SharePoint,** **seleccione Editar**.
2. En la página Seleccionar orígenes de temas **de SharePoint,** seleccione los sitios de SharePoint que se rastrearán como orígenes de los temas durante la detección. Esto incluye:
    - **Todos los sitios:** todos los sitios de SharePoint del espacio empresarial. Esto captura los sitios actuales y futuros.
    - **Todos, excepto los sitios seleccionados:** escriba los nombres de los sitios que desea excluir.  También puede cargar una lista de sitios en los que quiera no participar en la detección. Los sitios creados en el futuro se incluirán como orígenes para la detección de temas. 
    - **Solo los sitios seleccionados:** escriba los nombres de los sitios que desea incluir. También puede cargar una lista de sitios. Los sitios creados en el futuro no se incluirán como orígenes para la detección de temas.
    - **Ningún sitio:** los temas no se generarán ni actualizarán automáticamente con contenido de SharePoint. Los temas existentes permanecen en el centro de temas.

    ![Captura de pantalla de la interfaz de usuario de orígenes de temas de SharePoint](../media/k-manage-select-topic-source.png)
   
3. Haga clic en **Guardar**.

## <a name="exclude-topics-by-name"></a>Excluir temas por nombre

Puede excluir temas de la detección cargando una lista con un archivo .csv. Si ya ha excluido temas, puede descargar el archivo .csv, realizar cambios y cargarlo de nuevo.

1. En la **pestaña Detección** de temas, en **Excluir temas,** **seleccione Editar**.
2. Haga **clic en Excluir temas por nombre.**
3. Si necesitas crear una lista, descarga la plantilla .csv y agrega los temas que quieras excluir (consulta Trabajar con la *plantilla .csv a* continuación). Cuando el archivo esté listo, haga clic **en Examinar** y cargue el archivo. Si hay una lista existente, puede descargar el archivo .csv que contiene la lista.
4. Haga clic en **Guardar**.

    ![Captura de pantalla de la interfaz de usuario de los temas excluidos](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Trabajar con la plantilla .csv

Puede copiar la plantilla csv siguiente:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

En la plantilla CSV, escriba la siguiente información sobre los temas que desea excluir:

- **Nombre:** escriba el nombre del tema que desea excluir. Puede realizar esto de dos maneras:
    - Coincidencia exacta: puede incluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).
    - Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.  Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como el círculo de *arco,* el arco de *plasma y* el arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que se incluye el texto como parte de una palabra, como *Arquitectura*.
- **Significa (opcional):** si desea excluir un acrónimo, escriba las palabras que significa el acrónimo.
- **MatchType-Exact/Partial**: Escriba si el nombre que escribió fue *un tipo de* coincidencia exacta *o* parcial.

    ![Excluir temas de la plantilla CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Ver también

[Administrar la visibilidad de temas en Microsoft 365](topic-experiences-knowledge-rules.md)

[Administrar permisos de tema en Microsoft 365](topic-experiences-user-permissions.md)

[Cambiar el nombre del centro de temas en Microsoft 365](topic-experiences-administration.md)
