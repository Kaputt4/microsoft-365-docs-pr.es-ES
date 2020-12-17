---
title: Configurar experiencias de tema en Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo configurar experiencias de tema en Microsoft 365
ms.openlocfilehash: e11f0b75556a4a8ac0ffa40269d7166258128daf
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698560"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a>Configurar experiencias de tema en Microsoft 365

Puede usar el centro de administración de Microsoft 365 para instalar y configurar las experiencias de los [temas](topic-experiences-overview.md). 

Es importante planear la mejor forma de configurar y configurar temas en el entorno. Asegúrese de leer las [experiencias del tema del plan](plan-topic-experiences.md) antes de comenzar con los procedimientos de este artículo.

Debe ser administrador global o administrador de SharePoint para tener acceso al centro de administración de Microsoft 365 y configurar las experiencias de los temas.

## <a name="set-up-topic-experiences"></a>Configurar experiencias de tema

Para configurar experiencias de tema en Microsoft 365

1. En el [centro de administración de Microsoft 365](https://admin.microsoft.com), seleccione **instalación** y, a continuación, ver la sección **archivos y contenido** .
2. En la sección **archivos y contenido** , haga clic en **conectar personas con el conocimiento**.

    ![Conectar a personas con el conocimiento](../media/admin-org-knowledge-options.png) 

3. En la página **conectar personas a los conocimientos** , **haga clic en introducción para** guiarlo en el proceso de configuración.

    ![Introducción](../media/k-get-started.png) 

4. En la página **elegir el modo en que la red de conocimiento puede buscar temas** , se configurará la detección de temas. En la sección **seleccionar orígenes de temas de SharePoint** , seleccione los sitios de SharePoint que se rastrearán como orígenes para los temas durante la detección. Elija entre:
    - **Todos los sitios**: todos los sitios de SharePoint de la organización. Esto incluye los sitios actuales y futuros.
    - **Todos, excepto los sitios seleccionados**: escriba los nombres de los sitios que desea excluir.  También puede cargar una lista de sitios que desea excluir de la detección. Los sitios creados en el futuro se incluirán como orígenes para la detección de temas. 
    - **Solo sitios seleccionados**: escriba los nombres de los sitios que desea incluir. También puede cargar una lista de sitios. Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas.
    - **Sin sitios**: no incluye ningún sitio de SharePoint.

    ![Elegir cómo buscar temas](../media/ksetup1.png) 
   
5. En la sección **excluir temas por nombre** , puede Agregar nombres de temas que desea excluir del descubrimiento de temas. Use esta configuración para evitar que la información confidencial se incluya como temas. Las opciones son:
    - **No excluir temas** 
    - **Excluir temas por nombre**

    ![Excluir temas](../media/topics-excluded-by-name.png) 

    (Los administradores de conocimiento también pueden excluir temas del centro de temas después de la detección).

    #### <a name="how-to-exclude-topics-by-name"></a>Cómo excluir temas por nombre    

    Si necesita excluir temas, después de seleccionar **excluir temas por nombre**, seleccione Descargar la plantilla. csv y actualizarla con la lista de temas que desea excluir de los resultados de la detección.

    ![Excluir temas en la plantilla CSV](../media/exclude-topics-csv.png) 

    En la plantilla CSV, escriba la siguiente información sobre los temas que desea excluir:

    - **Name**: escriba el nombre del tema que desea excluir. Puede realizar esto de dos maneras:
        - Coincidencia exacta: puede incluir el acrónimo o el nombre exacto (por ejemplo, *contoso* o *ATL*).
        - Coincidencia parcial: puede excluir todos los temas que contengan una palabra específica.  Por ejemplo, *arco* excluirá todos los temas que contengan la palabra *Arc* , como *círculo arco*, *soldadura de arco de plasma* o arco de *formación*. Tenga en cuenta que no se excluirán los temas en los que se incluya el texto como parte de una palabra, como la *arquitectura*.
    - **Significa (opcional)**: Si desea excluir un acrónimo, escriba las palabras que representa el acrónimo.
    - **MatchType-Exact/Partial**: escriba si el nombre que ha escrito es un tipo de coincidencia *exacta* o *parcial* .

    Después de completar y guardar el archivo. csv, seleccione **examinar** para buscarlo y seleccionarlo.
    
    Seleccione **Siguiente**.

6. En la página **quién puede ver los temas y dónde puede** verlos, configurará la visibilidad de los temas. En los **temas quién puede ver en la red de conocimiento** , elija quién tendrá acceso a los detalles del tema, como temas resaltados, tarjetas de temas, respuestas de temas en la búsqueda y páginas de temas. Puede seleccionar:
    - **Todos los usuarios de mi organización**
    - **Solo personas seleccionadas o grupos de seguridad**
    - **No hay nadie**

    ![Quién puede ver los temas](../media/ksetup2.png)  

 > [!Note] 
 > Aunque esta configuración le permite seleccionar cualquier usuario de su organización, solo los usuarios que tengan licencias de temas que tengan asignada una licencia podrán ver los temas.

7. En la página **permisos para la administración de temas** , elija quién podrá crear, editar o administrar temas. En la sección **quién puede crear y editar temas** , puede seleccionar:
    - **Todos los usuarios de mi organización**
    - **Solo personas seleccionadas o grupos de seguridad**
    - **No hay nadie**

    ![Permisos para la administración de temas, que pueden crear y editar temas](../media/ksetup3.png) 

8. En la sección **quién puede administrar temas** , puede seleccionar:
    - **Todos los usuarios de mi organización**
    - **Solo personas seleccionadas o grupos de seguridad**

    ![Permisos para la administración de temas](../media/km-setup-create-edit-topics.png) 

    Seleccione **Siguiente**.

9. En la página **crear centro de temas** , puede crear el sitio del centro de temas en el que se pueden ver las páginas de temas y administrar los temas. En el cuadro **nombre del sitio** , escriba un nombre para el centro de temas. Opcionalmente, puede escribir una descripción breve en el cuadro **Descripción** . 

Seleccione **Siguiente**.

   ![Crear centro de conocimiento](../media/ksetup4.png)  

10. En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios. Si está de acuerdo con las selecciones, seleccione **Activar**.

11. Se mostrará la página de **información de red activada** , confirmando que el sistema empezará a analizar los sitios seleccionados para ver los temas y crear el sitio del centro de conocimiento. Seleccione **Listo**.

12. Se le devolverá a la página **conectar personas a la información** . Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración. 

    ![Configuración aplicada](../media/ksetup7.png)    

## <a name="assign-licenses"></a>Asignar licencias

Una vez que haya configurado las experiencias de los temas, debe asignar licencias para los usuarios que vayan a usar las experiencias de los temas. Solo los usuarios con una licencia pueden ver información sobre temas como las sugerencias, las tarjetas de temas, las páginas de temas y el centro de temas. 

Para asignar licencias:

1. En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.

2. Seleccione los usuarios a los que desea conceder licencias y haga clic en **Administrar licencias de productos**.

3. Seleccione **Asignar más**.

4. En **licencias**, seleccione **experiencias del tema**.

5. En **aplicaciones**, asegúrese de que la **búsqueda de conectores de gráficos con** experiencias de índice y **tema** estén seleccionadas.

    > [!div class="mx-imgBorder"]
    > ![Licencias de SharePoint Syntex en el Centro de administración de Microsoft 365](../media/topic-experiences-licenses.png)

6. Haga clic en **Guardar cambios**.

## <a name="manage-topic-experiences"></a>Administrar experiencias de temas

Una vez que haya configurado las experiencias de los temas, puede cambiar la configuración que eligió durante la instalación en el [centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement). Consulte las siguientes referencias:

- [Administrar la detección de temas en Microsoft 365](topic-experiences-discovery.md)
- [Administrar la visibilidad de los temas en Microsoft 365](topic-experiences-knowledge-rules.md)
- [Administrar los permisos de temas en Microsoft 365](topic-experiences-user-permissions.md)
- [Cambiar el nombre del centro de temas en Microsoft 365](topic-experiences-administration.md)

## <a name="see-also"></a>Vea también

[Información general sobre las experiencias de temas](topic-experiences-overview.md)
