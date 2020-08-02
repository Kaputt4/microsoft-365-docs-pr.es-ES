---
title: 'Configuración de la administración de conocimiento (versión preliminar) '
description: Cómo configurar la administración del conocimiento.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
ms.openlocfilehash: d4bc45bd1c88d4043df661972399dc6740dbed84
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540135"
---
# <a name="set-up-knowledge-management-preview"></a>Configuración de la administración de conocimiento (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

Puede usar el centro de administración de Microsoft 365 para instalar y configurar la [Administración del conocimiento](knowledge-management-overview.md). 

> [!Important]
> Es importante planear la mejor forma de configurar y configurar la administración del conocimiento en su entorno. Por ejemplo, tendrá que tener en cuenta lo siguiente:
- Los sitios de SharePoint que desea analizar para los temas.
- Los usuarios a los que desea que los temas sean visibles.
- Los usuarios a los que desea conceder permisos para administrar temas en el centro de temas.
- Los usuarios a los que desea conceder permisos para crear o editar temas en el centro de temas.
- El nombre que desea dar al centro de temas.

> [!Note]
> Puede que le resulte útil crear grupos de seguridad para asignar a los usuarios los permisos necesarios para ver temas, administrar temas y crear y editar temas.

Un administrador también puede [realizar cambios en la configuración seleccionada en cualquier momento después](manage-knowledge-network.md) de la instalación mediante la configuración de administración de conocimiento en el centro de administración de Microsoft 365.

## <a name="requirements"></a>Requirements 
Debe tener permisos de administrador global o de administrador de SharePoint para poder obtener acceso al centro de administración de 365 de Microsoft y configurar las tareas de conocimiento de la organización.

## <a name="set-up-your-knowledge-network"></a>Configurar la red de conocimientos

La configuración de la red de conocimientos le guiará a través de lo siguiente:

- Detección de temas: selección de los temas y orígenes del tema que se deben excluir de la detección.
- Visibilidad del tema: seleccionar quién puede ver los temas como puntos destacados, en las páginas de búsqueda y de temas.
- Topic Permissions: seleccionar quién puede crear, editar y administrar temas.
- Centro de temas: cree su centro de temas.
- Revisión: Compruebe y aplique la configuración.

Para configurar la red de conocimientos:

1. En el centro de administración de Microsoft 365 (admin.microsoft.com), seleccione **instalación**y, a continuación, ver la sección de conocimientos de la **organización** .
2. En la sección conocimientos de la **organización** , haga clic en **conectar personas con el conocimiento**.<br/>

    ![Conectar a personas con el conocimiento](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. En la página **conectar personas a los conocimientos** , **haga clic en introducción para** guiarlo en el proceso de configuración.<br/>

    ![Introducción](../media/content-understanding/k-get-started.png) </br>

4. En la página **elegir el modo en que la red de conocimiento puede buscar temas** , se configurará la detección de temas. En la sección **seleccionar orígenes de temas de SharePoint** , seleccione los sitios de SharePoint que se rastrearán como orígenes para los temas durante la detección. Esto incluye:</br>
    a. **Todos los sitios**: todos los sitios de SharePoint de su espacio empresarial. Esto captura los sitios actuales y futuros.</br>
    b. **Todos, excepto los sitios seleccionados**: escriba los nombres de los sitios que desea excluir.  También puede cargar una lista de sitios que desea excluir de la detección. Los sitios creados en el futuro se incluirán como orígenes para la detección de temas. </br>
    c. **Solo sitios seleccionados**: escriba los nombres de los sitios que desea incluir. También puede cargar una lista de sitios. Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas. </br>

    ![Elegir cómo buscar temas](../media/content-understanding/ksetup1.png) </br>
   
5. En la sección **excluir temas por nombre** , puede elegir incluir los nombres de los temas que no desea que se incluyan en los resultados detectados. Use esta opción para evitar que se incluyan temas confidenciales como parte de la red de conocimiento. Las opciones son:</br>
    a. **No excluir temas** </br>
    b. **Excluya el tema que contenga estos términos**: Si tiene temas que no desea que se muestren a los usuarios como parte de la red de conocimiento.
   -Descargar la plantilla proporcionada.
   -Escriba los nombres de los temas que desea excluir. Debe indicar el tipo de coincidencia como exacto o parcial. Coincidencia exacta significa que los temas que se ajustan al término exacto se excluirán. La coincidencia parcial es más estricta y significa que se excluirán los temas que contengan el término. Por ejemplo, si escribe *doc* como nombre de tema, se excluirá el *ensamblado de doc* mientras que el *acoplador* no. Los nombres de los temas no distinguen mayúsculas de minúsculas.  
        -Seleccione  **+**   para importar el archivo CSV completado. A continuación, seleccione **cargar**. Verá una marca de verificación verde si el archivo se ha procesado correctamente. Seleccione **Siguiente**.</br>


6. En la página **quién puede ver los temas y dónde pueden verlos** , configurará la visibilidad de los temas. En los **temas quién puede ver en la red de conocimiento** , elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas. Puede seleccionar:</br>
    a. **Todos en su organización**</br>
    b. **Solo personas seleccionadas o grupos de seguridad**</br>
    c. **No hay nadie**</br>

    ![Quién puede ver los temas](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de administración de conocimiento podrán ver los temas. 

7. En la página **permisos para la administración de temas** , elija quién podrá crear, editar o administrar temas. En la sección **quién puede crear y editar temas** , puede seleccionar:</br>
    a. **Todos en su organización**</br>
    b. **Solo personas seleccionadas o grupos de seguridad**</br>
8. En la sección **quién puede administrar temas** , puede seleccionar:</br>
    a. **Todos en su organización**</br>
    b. **Personas o grupos de seguridad seleccionados**</br>

    ![Permisos para la administración de temas](../media/content-understanding/ksetup3.png) </br>

    Seleccione **Siguiente**.</br>
9. En la página **crear centro de temas** , puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y administrar los temas.  En el cuadro **nombre del centro de temas** , escriba un nombre para el centro de temas. Opcionalmente, puede escribir una breve descripción en el cuadro **Descripción del sitio** . </br>

Seleccione **Siguiente**.</br>

   ![Crear centro de conocimiento](../media/content-understanding/ksetup4.png) </br> 

10. En la página **revisar y finalizar** , puede mirar la configuración seleccionada y elegir realizar cambios. Si está satisfecho con las selecciones, seleccione **Activar**.

    ![Finalizar y revisar](../media/content-understanding/ksetup5.png) </br> 

11. Se mostrará la página de **información de red activada** , confirmando que el sistema empezará a analizar los sitios seleccionados para ver los temas y crear el sitio del centro de conocimiento. Seleccione **Listo**.</br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. Se le devolverá a la página **conectar personas a la información** . En esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración. 

    ![Configuración aplicada](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> Después de la instalación, un administrador puede [realizar cambios en la configuración de administración de conocimiento](manage-knowledge-network.md) que haya seleccionado en cualquier momento volviendo a esta p? gina.


## <a name="see-also"></a>Consulte también



  






