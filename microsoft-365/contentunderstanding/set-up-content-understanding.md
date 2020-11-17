---
title: Configurar SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Establecer la comprensión del contenido en el Project Cortex.
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087576"
---
# <a name="set-up-sharepoint-syntex"></a>Configurar SharePoint Syntex

Los administradores pueden usar el Centro de administración de Microsoft 365 para configurar [Microsoft SharePoint Syntex](index.md). 

Considere lo siguiente antes de empezar:

- Which SharePoint sites will you enable form processing? All of them, some, or select sites?
- ¿Qué nombre le pondrá a su centro de contenido predeterminado?

Puede cambiar su configuración después de la configuración inicial en el Centro de administración de Microsoft 365.

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:

- Los sitios de SharePoint que desea habilitar para el procesamiento de formularios: todos ellos, algunos, o sitios seleccionados
- Su centro de contenido y el nombre del administrador principal del sitio

## <a name="requirements"></a>Requirements 

> [!NOTE]
> Debe tener permisos de administrador global o de administrador de SharePoint para poder acceder al Centro de administración de Microsoft 365 y configurar la comprensión del contenido.

Como administrador, también puede realizar cambios en la configuración seleccionada en cualquier momento después de la configuración, y a lo largo de la comprensión del contenido de la configuración de administración en el Centro de administración de Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Para configurar SharePoint Syntex

1. En el Centro de administración de Microsoft 365, seleccione **Configuración** y luego vea la sección **Archivos y contenido**.

2. En la sección **Archivos y contenido**, seleccione **Automatizar la comprensión del contenido**.<br/>

3. En la página para **Automatizar la comprensión del contenido**, haga clic en **Introducción** para recorrer el proceso de configuración.<br/>

    > [!div class="mx-imgBorder"]
    > ![Iniciar la instalación](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.
 
     Para **Qué bibliotecas de SharePoint debe mostrar la opción de crear un modelo de procesamiento de formularios**, puede seleccionar:</br>
      - **Todas las bibliotecas de SharePoint** para que estén disponibles para todas las bibliotecas de SharePoint de su organización.</br>
      - **Sólo las bibliotecas de los sitios seleccionados**, y luego seleccione los sitios en los que desea que esté disponible o cargue una lista de hasta 50 sitios.</br>
      - **No hay bibliotecas de SharePoint** si no quiere que esté disponible para ningún sitio (puede cambiar esto después de la configuración).

   > [!div class="mx-imgBorder"]
   > ![Configurar el procesamiento del formulario](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Quitando un sitio después de incluirlo no afecta a los modelos existentes aplicados a las bibliotecas de ese sitio ni a la capacidad de aplicar modelos de comprensión de documentos a una biblioteca. 
    
5. En la página **Crear centro de contenido**, puede crear un sitio de centro de contenido de SharePoint en el que sus usuarios puedan crear y administrar modelos de comprensión de documentos.

    1. Para el **Nombre del sitio**, escriba el nombre que quiere darle a su sitio de centro de contenido.
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![Crear el centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</br>

       Seleccione **Siguiente**.

6. On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.

7. En la página de confirmación, haga clic en **Listo**.

8. You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings. 

## <a name="assign-licenses"></a>Asignar licencias

Una vez que haya configurado SharePoint Syntex, debe asignar licencias para los usuarios que utilizarán cualquier función de SharePoint Syntex.

Para asignar licencias:

1. En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.

2. Seleccione los usuarios a los que desea conceder licencias y haga clic en **Administrar licencias de productos**.

3. Seleccione **Asignar más**.

4. Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.

    > [!div class="mx-imgBorder"]
    > ![Licencias de SharePoint Syntex en el Centro de administración de Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Haga clic en **Guardar cambios**.

## <a name="ai-builder-credits"></a>Créditos de Generador de IA

If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.

Puede estimar la capacidad del Generador de IA que lo hace adecuado para usted con la calculadora del [Generador de IA](https://powerapps.microsoft.com/ai-builder-calculator).

Vaya al [Centro de administración de la Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar sus créditos y el uso.

## <a name="see-also"></a>Consulte también

[Visión general del modelo de procesamiento de formularios](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Paso a paso: cómo crear un modelo de comprensión de documentos (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

