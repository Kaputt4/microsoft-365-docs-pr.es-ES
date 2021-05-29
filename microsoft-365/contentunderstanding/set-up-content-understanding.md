---
title: Configurar SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Establecer la comprensión del contenido en el Project Cortex.
ms.openlocfilehash: 7589003505aafb480872b14a09c383cfbe0dff40
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683558"
---
# <a name="set-up-sharepoint-syntex"></a>Configurar SharePoint Syntex

Los administradores pueden usar el Centro de administración de Microsoft 365 para configurar [Microsoft SharePoint Syntex](index.md). 

Considere lo siguiente antes de empezar:

- ¿En qué sitios de SharePoint se va a habilitar el procesamiento de formularios? ¿Todos ellos, algunos, o seleccionar sitios?
- ¿Qué nombre le pondrá a su centro de contenido de forma predeterminada?

Puede cambiar su configuración después de la configuración inicial en el Centro de administración de Microsoft 365.

Antes de la configuración, asegúrese de planear la mejor forma de configurar la comprensión del contenido en su entorno. Por ejemplo, necesita tomar las siguientes decisiones:

- Los sitios de SharePoint en los que desea habilitar el procesamiento de formularios: todos, algunos o sitios seleccionados
- El nombre y los administradores de su centro de contenido

## <a name="requirements"></a>Requirements 

> [!NOTE]
> Debe tener permisos de administrador global o de administrador de SharePoint para poder acceder al centro de administración de Microsoft 365 y configurar SharePoint Syntex.

Como administrador, también puede realizar cambios en la configuración seleccionada en cualquier momento después de la configuración, y a lo largo de la comprensión del contenido de la configuración de administración en el Centro de administración de Microsoft 365.

Si tiene previsto usar un entorno de Power Platform personalizado, deberá [instalar la aplicación *Generador de IA para Proyecto Cortex* en este entorno](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) y [asignar los créditos de Generador de AI](/power-platform/admin/capacity-add-on) a esta antes de poder crear modelos de procesamiento de formularios.

### <a name="licensing"></a>Licencias

Para usar SharePoint Syntex, su organización debe tener una suscripción a SharePoint Syntex y cada usuario debe tener asignadas las siguientes licencias:

- SharePoint Syntex
- SharePoint Syntex: tipo SPO
- Servicio de datos comunes para SharePoint Syntex

Si cancela su suscripción a SharePoint Syntex (o la versión de prueba expira), los usuarios ya no podrán crear ni ejecutar modelos de procesamiento de formularios o comprensión de documentos y la plantilla del centro de contenido ya no estará disponible. Además, los informes de almacén de términos, la importación de taxonomía SKOS y la inserción de tipo de contenido ya no estarán disponibles. No se eliminará ningún contenido ni se modificarán los permisos del sitio.

### <a name="ai-builder-credits"></a>Créditos de Generador de IA

Si tiene 300 o más licencias de SharePoint Syntex en su organización, se le asignará un millón de créditos del Generador de IA. Si tiene menos de 300 licencias, debe comprar créditos del Generador de IA para poder utilizar el procesamiento de formularios.

Puede estimar la capacidad del Generador de IA que lo hace adecuado para usted con la calculadora del [Generador de IA](https://powerapps.microsoft.com/ai-builder-calculator).

Si planea utilizar un entorno de Power Platform personalizado, debe [asignar créditos a ese entorno](/power-platform/admin/capacity-add-on).

Vaya al [Centro de administración de la Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar sus créditos y el uso.

## <a name="to-set-up-sharepoint-syntex"></a>Para configurar SharePoint Syntex

1. En el Centro de administración de Microsoft 365, seleccione **Configuración** y luego vea la sección **Archivos y contenido**.

2. En la sección **Archivos y contenido**, seleccione **Automatizar la comprensión del contenido**. Tenga en cuenta que la disponibilidad de crédito actual del Generador de IA se muestra en la sección **De un vistazo**.<br/>

3. En la página para **Automatizar la comprensión del contenido**, haga clic en **Introducción** para recorrer el proceso de configuración. <br/>

    > [!div class="mx-imgBorder"]
    > ![Iniciar la instalación](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. En la página **Configurar el procesamiento** de formularios, puede elegir si desea que los usuarios puedan crear modelos de procesamiento de formularios en bibliotecas de documentos específicos de SharePoint. En la cinta de opciones de la biblioteca de documentos estará disponible una opción de menú para **Crear un modelo de procesamiento de formularios** en las bibliotecas de documentos de SharePoint en las que esté habilitado.
 
     Para **Qué bibliotecas de SharePoint debe mostrar la opción de crear un modelo de procesamiento de formularios**, puede seleccionar:</br>
      - **Bibliotecas en todos los sitios de SharePoint** para que esté disponible en todas las bibliotecas de SharePoint de su organización.</br>
      - **Bibliotecas en los sitios de SharePoint seleccionados**, y a luego, seleccione los sitios en los que desea que esté disponible o cargue una lista de hasta 50 sitios.</br>
      - **No hay bibliotecas de SharePoint** si no quiere que esté disponible para ningún sitio (puede cambiar esto después de la configuración).

   > [!div class="mx-imgBorder"]
   > ![Configurar las opciones del sitio de procesamiento de formularios](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Quitando un sitio después de incluirlo no afecta a los modelos existentes aplicados a las bibliotecas de ese sitio ni a la capacidad de aplicar modelos de comprensión de documentos a una biblioteca. 
    
    Si tiene varios entornos de Power Platform configurados, puede elegir cuál desea usar para el procesamiento de formularios. (Esta opción no aparecerá si solo tiene un entorno).

    ![Configurar las opciones de Power Platform de procesamiento de formularios](../media/content-understanding/setup-power-platform-env.png)

    Para el **entorno de Power Platform**, puede seleccionar:
    - **Usar el entorno predeterminado** para utilizar su entorno de Power Platform predeterminado.
    - **Usar un entorno personalizado** para utilizar un entorno personalizado. De la lista, elija el entorno que quiera utilizar. ([Ver los requisitos de un entorno personalizado](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).

    Haga clic en **Siguiente**.

5. En la página **Crear centro de contenido**, puede crear un sitio de centro de contenido de SharePoint en el que sus usuarios puedan crear y administrar modelos de comprensión de documentos.

    1. Para el **Nombre del sitio**, escriba el nombre que quiere darle a su sitio de centro de contenido.
    
    1. La **Dirección del sitio** mostrará el URL de su sitio, basado en lo que usted seleccionó para el nombre del sitio. Si desea cambiar la configuración, haga clic en **Editar**.

       > [!div class="mx-imgBorder"]
       > ![Crear el centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</br>

       Seleccione **Siguiente**.

6. En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios. Si está de acuerdo con las selecciones, seleccione **Activar**.

7. En la página de confirmación, haga clic en **Listo**.

8. Volverá a su página **Automatizar la comprensión del contenido**. Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración. 

## <a name="assign-licenses"></a>Asignar licencias

Una vez que haya configurado SharePoint Syntex, debe asignar licencias para los usuarios que utilizarán cualquier función de SharePoint Syntex.

Para asignar licencias:

1. En el Centro de administración de Microsoft 365, en **Usuarios**, haga clic en **Usuarios activos**.

2. Seleccione los usuarios a los que quiere conceder licencias y haga clic en **Administrar licencias de productos**.

3. Elija **Aplicaciones** en el menú desplegable.

4. Seleccione **Mostrar aplicaciones para SharePoint Syntex**. En **Aplicaciones**, asegúrese de estén seleccionadas las opciones **Servicio de datos común para SharePoint Syntex**, **SharePoint Syntex** y **SharePoint Syntex: tipo SPO**.

    > [!div class="mx-imgBorder"]
    > ![Licencias de SharePoint Syntex en el Centro de administración de Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Haga clic en **Guardar cambios**.

## <a name="see-also"></a>Consulte también

[Visión general del modelo de procesamiento de formularios](/ai-builder/form-processing-model-overview)

[Paso a paso: cómo crear un modelo de comprensión de documentos (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

[Crear y administrar entornos en el Centro de administración de la Power Platform](/power-platform/admin/create-environment)
