---
title: Administrar la detección de temas en Temas de Microsoft Viva
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
ms.openlocfilehash: 53e304dc69ccf2ca6fe01d29f0997c539406b0fe
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768979"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Administrar la detección de temas en Temas de Microsoft Viva

Puede administrar la configuración de detección de temas [en el centro Microsoft 365 administración.](https://admin.microsoft.com) Debe ser un administrador global o SharePoint administrador para realizar estas tareas.

## <a name="to-access-topics-management-settings"></a>Para acceder a la configuración de administración de temas:

1. En el Centro Microsoft 365 administración, haga clic **en Configuración** y, a continuación, en Configuración de **la organización.**
2. En la **pestaña Servicios,** haga clic en **Experiencias del tema**.

    ![Conectar personas al conocimiento](../media/admin-org-knowledge-options-completed.png) 

3. Seleccione la **pestaña Detección de** temas. Vea las secciones siguientes para obtener información sobre cada configuración.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Seleccionar SharePoint de temas

Puede cambiar los sitios SharePoint de la organización que se rastrearán para los temas.

Si desea incluir o excluir una lista específica de sitios, puede usar la siguiente plantilla .csv web:

``` csv
Site name,URL
```

Si añade sitios utilizando el selector de sitios, éstos se añaden a la lista existente de sitios a incluir o excluir. Si carga un archivo .csv, éste sobrescribe cualquier lista existente. Si ha incluido o excluido sitios específicos anteriormente, descargue la lista como un archivo .csv, realice cambios y cargue la nueva lista.

Para elegir sitios para la detección de temas

1. En la pestaña **Descubrimiento de temas** en **Seleccionar fuentes de temas de SharePoint**, seleccione **Editar**.
2. En la **página Seleccionar SharePoint** de temas, seleccione qué sitios SharePoint se rastrearán como orígenes de los temas durante la detección. Esto incluye:
    - **Todos los sitios:** todos SharePoint en el espacio empresarial. Esto captura los sitios actuales y futuros.
    - **Todos, excepto los sitios seleccionados:** escriba los nombres de los sitios que desea excluir.  También puede cargar una lista de sitios que desea excluir de la detección. Los sitios creados en el futuro se incluirán como fuentes para el descubrimiento de temas. 
    - **Solo sitios seleccionados:** escriba los nombres de los sitios que desea incluir. También puede cargar una lista de sitios. Los sitios creados en el futuro no se incluirán como fuentes para el descubrimiento de temas.
    - **No hay sitios:** los temas no se generarán ni actualizarán automáticamente con SharePoint contenido. Los temas existentes permanecen en el centro de temas.

    ![Captura de pantalla de SharePoint interfaz de usuario de orígenes de temas](../media/k-manage-select-topic-source.png)
   
3. Haga clic en **Guardar**.

## <a name="exclude-topics-by-name"></a>Excluir temas por nombre

Puede excluir temas de la detección cargando una lista mediante un archivo .csv. Si ha excluido previamente los temas, puede descargar el .csv, hacer cambios y volver a cargarlo.

1. En la pestaña **Descubrimiento de temas** en **Excluir temas**, seleccione **Editar**.
2. Haga **clic en Excluir temas por nombre**.
3. Si necesita crear una lista, descargue la plantilla .csv y agregue los temas que desea excluir (vea Trabajar con la *plantilla .csv a* continuación). Cuando el archivo esté listo, haga clic **en Examinar** y cargue el archivo. Si hay una lista existente, puede descargar el .csv que contiene la lista.
4. Haga clic en **Guardar**.

    ![Captura de pantalla de la interfaz de usuario de excluir temas](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Trabajar con la plantilla .csv plantilla

Puede copiar la plantilla csv siguiente:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

En la plantilla CSV, introduzca la siguiente información sobre los temas que desea excluir:

- **Nombre**: Escriba el nombre del tema que quiera excluir. Hay dos formas de hacerlo:
    - Coincidencia exacta: puede excluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).
    - Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.  Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como *Círculo* de arco, *Soldador de arco de* plasma o Arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que el texto se incluye como parte de una palabra, como *Arquitectura*.
- **Significa (opcional):** si desea excluir un acrónimo, escriba las palabras que el acrónimo representa.
- **MatchType-Exact/Partial:** escriba si el nombre que escribió era *un tipo de* coincidencia exacto *o* parcial.

    ![Excluir temas en plantilla CSV](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Consulte también

[Administrar la visibilidad del tema en Microsoft 365](topic-experiences-knowledge-rules.md)

[Administrar permisos de temas en Microsoft 365](topic-experiences-user-permissions.md)

[Cambie el nombre del centro de temas en Microsoft 365](topic-experiences-administration.md)
