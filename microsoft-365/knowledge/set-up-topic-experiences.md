---
title: Configurar temas de Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Obtenga información sobre cómo configurar temas de Microsoft Viva
ms.openlocfilehash: 19395cf3a9ecc991f08f375425803cb81a2a1d35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930226"
---
# <a name="set-up-microsoft-viva-topics"></a>Configurar temas de Microsoft Viva

Puede usar el Centro Microsoft 365 administración para configurar y configurar [Temas](topic-experiences-overview.md). 

Es importante planear la mejor forma de configurar y configurar temas en el entorno. Asegúrese de leer [Plan for Microsoft Viva Topics](plan-topic-experiences.md) antes de comenzar los procedimientos de este artículo.

Debe estar suscrito a [Viva Topics](https://www.microsoft.com/microsoft-viva/topics) y ser administrador global o administrador de SharePoint para tener acceso al centro de administración de Microsoft 365 y configurar Temas.

Si has configurado SharePoint [para requerir dispositivos administrados,](/sharepoint/control-access-from-unmanaged-devices)asegúrate de configurar Temas desde un dispositivo administrado.

## <a name="video-demonstration"></a>Vídeo de demostración

En este vídeo se muestra el proceso de configuración de temas en Microsoft 365.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a>Asignar licencias

Debe asignar licencias para los usuarios que usarán Temas. Solo los usuarios con una licencia pueden ver información sobre temas como resaltados, tarjetas de temas, páginas de temas y el centro de temas. 

Para asignar licencias:

1. En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.

2. Selecciona los usuarios que quieres licenciar y haz clic **en Licencias y aplicaciones.**

3. En **Licencias,** seleccione **Temas de Viva**.

4. En **Aplicaciones,** asegúrese de que Graph conectores de búsqueda con **Index (Temas de Viva)** y **Temas de Viva** estén seleccionados.

   > [!div class="mx-imgBorder"]
   > ![Licencias de Temas de Microsoft Viva en el Centro Microsoft 365 administración](../media/topic-experiences-licenses.png)

5. Haga clic en **Guardar cambios**.

Los usuarios pueden tardar hasta una hora en obtener acceso a temas después de asignar las licencias.

## <a name="set-up-topics"></a>Configurar Temas

Para configurar temas

1. En el [Microsoft 365 de administración,](https://admin.microsoft.com)seleccione **Configurar** y, a continuación, vea la sección Archivos **y** contenido.
2. En la **sección Archivos y contenido,** haga **clic Conectar para que los usuarios lo den a conocer.**

    ![Conectar personas al conocimiento](../media/admin-org-knowledge-options.png) 

3. En la **página Conectar personas al conocimiento,** haga clic en Introducción para que le guía por el proceso de configuración. 

    ![Introducción](../media/k-get-started.png) 

4. En la página Elegir cómo pueden encontrarse los temas de **Viva Topics,** configurará la detección de temas. En la **sección Seleccionar SharePoint** temas, seleccione qué sitios SharePoint se rastrearán como orígenes de los temas durante la detección. Elija entre:
    - **Todos los sitios**: Todos los sitios de SharePoint de su organización. Esto incluye los sitios actuales y futuros.
    - **Todos, excepto los sitios seleccionados:** escriba los nombres de los sitios que desea excluir.  También puede cargar una lista de sitios que desea excluir de la detección. Los sitios creados en el futuro se incluirán como orígenes para la detección de temas. 
    - **Solo sitios seleccionados:** escriba los nombres de los sitios que desea incluir. También puede cargar una lista de sitios. Los sitios creados en el futuro no se incluirán como fuentes para el descubrimiento de temas.
    - **Ningún sitio**: No incluya ningún sitio de SharePoint.

    ![Elegir cómo buscar temas](../media/ksetup1.png) 
   
5. En la **sección Excluir temas por** nombre, puede agregar nombres de los temas que desea excluir de la detección de temas. Use esta configuración para evitar que la información confidencial se incluya como temas. Las opciones son:
    - **No excluir ningún tema** 
    - **Excluir temas por nombre**

    ![Excluir temas](../media/topics-excluded-by-name.png) 

    (Los administradores de conocimientos también pueden excluir los temas del centro de temas después de la detección).

    #### <a name="how-to-exclude-topics-by-name"></a>Cómo excluir temas por nombre    

    Si necesita excluir temas, después de seleccionar Excluir temas por su **nombre,** descargue la plantilla .csv y actualícelo con la lista de temas que desea excluir de los resultados de detección.

    ![Excluir temas en plantilla CSV](../media/exclude-topics-csv.png) 

    En la plantilla CSV, introduzca la siguiente información sobre los temas que desea excluir:

    - **Nombre**: Escriba el nombre del tema que quiera excluir. Hay dos formas de hacerlo:
        - Coincidencia exacta: puede incluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).
        - Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.  Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como *Círculo* de arco, *Soldador de arco de* plasma o Arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que el texto se incluye como parte de una palabra, como *Arquitectura*.
    - **Significa (opcional):** si desea excluir un acrónimo, escriba las palabras que el acrónimo representa.
    - **MatchType-Exact/Partial:** escriba si el nombre que escribió era *un tipo de* coincidencia exacto *o* parcial.

    Después de completar y guardar el archivo .csv, seleccione **Examinar** para buscarlo y seleccionarlo.
    
    Seleccione **Siguiente**.

6. En la **Quién puede ver los temas y dónde pueden verlos,** configurará la visibilidad de los temas. En **la Quién** puede ver la configuración de temas, elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas. Puede seleccionar:
    - **Todos los miembros de mi organización**
    - **Solo personas o grupos de seguridad seleccionados**
    - **Nadie**

    ![Quién puede ver temas](../media/ksetup2.png)  

    > [!Note] 
    > Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de Experiencias de tema asignadas podrán ver temas.

7. En la **página Permisos para la** administración de temas, elige quién podrá crear, editar o administrar temas. En la **Quién puede crear y editar temas,** puede seleccionar:
    - **Todos los miembros de mi organización**
    - **Solo personas o grupos de seguridad seleccionados**
    - **Nadie**

    ![Permisos para la administración de temas, que pueden crear y editar temas](../media/ksetup3.png) 

8. En la **Quién puede administrar temas,** puede seleccionar:
    - **Todos los miembros de mi organización**
    - **Solo personas o grupos de seguridad seleccionados**

    ![Permisos para la administración de temas](../media/km-setup-create-edit-topics.png) 

    Seleccione **Siguiente**.

9. En la **página Crear centro de** temas, puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y los temas se pueden administrar. En el **cuadro Nombre del** sitio, escriba un nombre para el centro de temas. Opcionalmente, puede escribir una breve descripción en el **cuadro** Descripción. 

   Seleccione **Siguiente**.

   ![Crear centro de conocimiento](../media/ksetup4.png)  

10. En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios. Si está de acuerdo con las selecciones, seleccione **Activar**.

11. Se mostrará la página Temas **de Viva** activada, lo que confirma que el sistema empezará a analizar los sitios seleccionados para los temas y a crear el sitio del centro de temas. Seleccione **Listo**.

12. Se le devolverá a la página de **Conectar a la página de** conocimientos. Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración. 

    ![Configuración aplicada](../media/ksetup7.png)    

Tenga en cuenta que la primera vez que se habilita la detección de temas, puede tardar hasta dos semanas en que todos los temas sugeridos aparezcan en la vista Administrar temas. La detección de temas continúa a medida que se realizan nuevas actualizaciones o contenido. Es normal que haya variaciones en el número de temas sugeridos en su organización mientras Viva Topics evalúa nueva información.

## <a name="manage-topic-experiences"></a>Administrar experiencias de temas

Una vez configurados los temas, puede cambiar la configuración que eligió durante la instalación en el [centro Microsoft 365 administración.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement) Vea las referencias siguientes:

- [Administrar la detección de temas en Temas de Microsoft Viva](topic-experiences-discovery.md)
- [Administrar visibilidad de temas en Temas de Microsoft Viva](topic-experiences-knowledge-rules.md)
- [Administrar permisos de temas en Temas de Microsoft Viva](topic-experiences-user-permissions.md)
- [Cambiar el nombre del centro de temas en Temas de Microsoft Viva](topic-experiences-administration.md)

## <a name="see-also"></a>Consulte también

[Introducción a las experiencias del tema](topic-experiences-overview.md)
