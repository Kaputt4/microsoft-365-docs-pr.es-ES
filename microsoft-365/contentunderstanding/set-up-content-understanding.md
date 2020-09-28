---
title: Configurar SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Configurar la comprensión del contenido en Project Cortex
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294891"
---
# <a name="set-up-sharepoint-syntex"></a>Configurar SharePoint Syntex

Los administradores pueden usar el centro de administración de Microsoft 365 para instalar y Microsoft SharePoint Syntex. 

Antes de empezar, tenga en cuenta lo siguiente:

- ¿Qué sitios de SharePoint habilitará el procesamiento de formularios? Todos ellos, algunos o seleccione sitios?
- ¿Cuál será el nombre de su centro de contenido y quién es el administrador del sitio principal?

Puede cambiar la configuración después de la configuración inicial en el centro de administración de Microsoft 365.

El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

Antes de la instalación, asegúrese de planear la mejor manera de configurar y configurar la comprensión del contenido en su entorno. Por ejemplo, debe tener en cuenta los siguientes nombres de:

- Los sitios de SharePoint en los que desea habilitar el procesamiento de formularios: todos, algunos o determinados sitios
- El centro de contenido y el nombre del administrador del sitio principal

## <a name="requirements"></a>Requisitos 

> [!NOTE]
> Debe tener permisos de administrador global o de administrador de SharePoint para poder obtener acceso al centro de administración de 365 de Microsoft y configurar el conocimiento del contenido.

Como administrador, también puede realizar cambios en la configuración seleccionada en cualquier momento después de la instalación y en todo el contenido que comprenda la configuración de administración en el centro de administración de Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Para configurar SharePoint Syntex

1. En el centro de administración de Microsoft 365, seleccione **instalación**y, a continuación, ver la sección de conocimientos de la **organización** .

2. En la sección conocimientos de la **organización** , seleccione **automatizar el conocimiento del contenido**.<br/>

    ![Página de configuración de conocimientos de la organización](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. En la página **automatizar Syntex de SharePoint** , **haga clic en introducción para** recorrer el proceso de instalación.<br/>

    ![Inicio de la instalación](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. En la página activar el etiquetado de imágenes, elija si quiere permitir el [etiquetado de imágenes](image-tagging.md).

    ![Captura de pantalla de las opciones de etiquetado de imágenes](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. En la página **configurar procesamiento de formularios** , puede elegir si desea permitir que los usuarios puedan usar el generador de AI para crear modelos de procesamiento de formularios en bibliotecas de documentos de SharePoint específicas. Una opción de menú estará disponible en la cinta de la biblioteca de documentos para **crear un modelo de procesamiento de formularios** en las bibliotecas de documentos de SharePoint en las que esté habilitado.
 
     Para **qué bibliotecas de SharePoint se debe mostrar la opción para crear un modelo de procesamiento de formularios**, puede seleccionar:</br>
      - **Todas las bibliotecas de SharePoint** para que estén disponibles para todas las bibliotecas de SharePoint de la organización.</br>
      - **Solo las bibliotecas de los sitios seleccionados**y, a continuación, seleccione los sitios en los que desea que estén disponibles.</br>

   ![Configurar el procesamiento de formularios](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > La habilitación de esta opción en una biblioteca de documentos de SharePoint no afecta a los modelos existentes aplicados a la biblioteca o a la capacidad de aplicar documentos que comprenden los modelos a una biblioteca. 
    
6. En la página **crear centro de contenido** , puede crear un sitio del centro de contenido de SharePoint en el que los usuarios puedan crear y administrar los modelos de comprensión de documentos. </br>
    a. En **nombre del sitio**, escriba el nombre que desea asignar al sitio del centro de contenido.</br>
    b. La **dirección del sitio** mostrará la dirección URL del sitio, en función de lo que haya seleccionado para el nombre del sitio. Si desea cambiarla, haga clic en **Editar**.</br>

      ![Crear centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</br>

    Seleccione **Siguiente**.

7. En la página **revisar y finalizar** , puede mirar la configuración seleccionada y elegir realizar cambios. Si está satisfecho con las selecciones, seleccione **Activar**.

8. En la página Confirmación, haga clic en **listo**.

9. Volverá a la página de **comprensión automatizada del contenido** . En esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración. 

## <a name="assign-licenses"></a>Asignar licencias

Una vez configurados los Syntex de SharePoint, debe asignar licencias para los usuarios que van a usar las características de procesamiento de formularios y de descripción de documentos.

Para asignar licencias:

1. En el centro de administración de Microsoft 365, en **usuarios**, haga clic en **usuarios activos**.

2. Seleccione los usuarios a los que quiera conceder una licencia y haga clic en **administrar licencias de producto**.

3. Seleccione **asignar más**.

4. Seleccione **servicios de contenido inteligente**. En **aplicaciones**, asegúrese **de que servicio de datos común para servicios de contenido inteligente** y **servicios de contenido inteligente** están seleccionados.

    ![Licencias de SharePoint Syntex en el centro de administración de Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Haga clic en **Guardar cambios**.

## <a name="ai-builder-credits"></a>Créditos del generador de AI

Si tiene 300 o más licencias de Syntex de SharePoint para SharePoint Syntex en su organización, se le asignarán 1 millón los créditos del generador de AI. Si tiene menos de 300 licencias, debe adquirir créditos del generador de AI para poder usar el procesamiento de formularios.

Puede calcular la capacidad del generador de AI que más le conviene con la [calculadora del generador de AI](https://powerapps.microsoft.com/ai-builder-calculator).

1. Vaya al centro de administración de la [plataforma de energía](https://admin.powerplatform.microsoft.com/resources/capacity) para comprobar los créditos y el uso.

    > [!NOTE]
    > Habilitar esta opción en una biblioteca de documentos de SharePoint no afecta a los modelos existentes que se aplican a la biblioteca o a la capacidad de aplicar documentos que comprenden los modelos a una biblioteca. 
    
2. En la página **crear centro de contenido** , puede crear un sitio del centro de contenido de SharePoint para el que los usuarios puedan crear y administrar los modelos de comprensión de documentos. </br>
    a. En **nombre del sitio**, escriba el nombre que desee para el sitio del centro de contenido.</br>
    b. La **dirección del sitio** muestra la dirección URL del sitio, en función del nombre del sitio.</br>

    > [!NOTE] 
    > Aunque puede seleccionar cualquier idioma admitido, los modelos de comprensión de contenido solo se pueden crear para inglés.</br>

      ![Crear centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</br>

3. Seleccione **Siguiente**.

4. En la página **finalizar y revisar** , mire la configuración seleccionada y elija realizar cambios. Si está satisfecho con las selecciones, seleccione **Activar**.

5. Se muestra el **contenido que comprende** la página activada, confirmando que el sistema agregó sus preferencias de procesamiento de formulario y creó el sitio del centro de contenido. Seleccione **Listo**.

6. Volverá a la página de **comprensión automatizada del contenido** . En esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración. 

## <a name="see-also"></a>Consulte también

[Información general sobre el modelo de procesamiento de formularios](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Paso a paso: Cómo crear un documento que comprenda el modelo (vídeo)](https://www.youtube.com/watch?v=DymSHObD-bg)

