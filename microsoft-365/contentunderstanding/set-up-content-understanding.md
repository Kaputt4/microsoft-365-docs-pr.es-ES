---
title: 'Configurar la comprensión del contenido (versión preliminar) '
description: Cómo configurar Project Cortex.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fca80e45dfa45ee5da9521854c6eebfbd87d8859
ms.sourcegitcommit: 91c82a79962387205c4dd4dd8d61322b79fed55f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "46539913"
---
# <a name="set-up-content-understanding-preview"></a>Configurar la comprensión del contenido (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

Los administradores pueden usar el centro de administración de Microsoft 365 para instalar y configurar la comprensión de contenido. 

Antes de la instalación, asegúrese de planear la mejor manera de configurar y configurar la comprensión del contenido en su entorno. Por ejemplo, tendrá que tener en cuenta lo siguiente:
- ¿Qué sitios de SharePoint habilitará el procesamiento de formularios? Todos ellos, algunos o seleccione sitios?
- Nombre del centro de contenido y ¿quién es el administrador del sitio principal?

Un administrador también puede realizar cambios en la configuración seleccionada en cualquier momento después de la instalación a través del contenido que comprende la configuración de administración en el centro de administración de Microsoft 365.


## <a name="requirements"></a>Requirements 
Debe tener permisos de administrador global o de administrador de SharePoint para poder obtener acceso al centro de administración de 365 de Microsoft y configurar el conocimiento del contenido.


## <a name="to-set-up-content-understanding"></a>Para configurar la comprensión del contenido

1. En el centro de administración de Microsoft 365, seleccione **instalación**y, a continuación, ver la sección de conocimientos de la **organización** .
2. En la sección conocimientos de la **organización** , seleccione **automatizar el conocimiento del contenido**.<br/>

    ![Página de configuración de conocimientos de la organización](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. En la página **automatizar la comprensión** del contenido **, haga clic en introducción para** guiarlo por el proceso de instalación.<br/>

    ![Inicio de la instalación](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. En la página **configurar procesamiento de formularios** , puede elegir si desea permitir que los usuarios puedan usar el generador de AI para crear modelos de procesamiento de formularios en bibliotecas de documentos de SharePoint específicas. Una opción de menú estará disponible en la cinta de la biblioteca de documentos para **crear un modelo de procesamiento de formularios** en las bibliotecas de documentos de SharePoint en las que esté habilitado.
 
     Para **qué bibliotecas de SharePoint se debe mostrar la opción para crear un modelo de procesamiento de formularios**, puede seleccionar:</br>
    - **Todas las bibliotecas de SharePoint** para que estén disponibles para todas las bibliotecas de SharePoint en su espacio empresarial.</br>
    - **Solo las bibliotecas de los sitios seleccionados**y, a continuación, seleccione los sitios en los que desea que estén disponibles.</br>
    - **Sin bibliotecas de SharePoint** si actualmente no desea que esté disponible para ningún sitio (puede cambiarlo después de la instalación).
</br>

   ![Configurar el procesamiento de formularios](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > La habilitación de esta opción en una biblioteca de documentos de SharePoint no afecta a los modelos existentes aplicados a la biblioteca o a la capacidad de aplicar documentos que comprenden los modelos a una biblioteca. 

    
5. En la página **crear centro de contenido** , puede crear un sitio del centro de contenido de SharePoint en el que los usuarios puedan crear y administrar los modelos de comprensión de documentos. </br>
    a. En **nombre del sitio**, escriba el nombre que desea asignar al sitio del centro de contenido.</br>
    b. La **dirección del sitio** mostrará la dirección URL del sitio, en función de lo que haya seleccionado para el nombre del sitio.</br>

    > [!Note] 
    > Aunque puede seleccionar cualquier idioma admitido, tenga en cuenta que el contenido que comprende los modelos solo se puede crear para inglés.</br>

      ![Crear centro de contenido](../media/content-understanding/admin-cu-create-cc.png)</br>


    Seleccione **Siguiente**.
6. En la página **finalizar y revisar** , puede mirar la configuración seleccionada y elegir realizar cambios. Si está satisfecho con las selecciones, seleccione **Activar**.



7. Se mostrará el **contenido que comprende** la página activada, confirmando que el sistema ha agregado sus preferencias de procesamiento de formularios y ha creado el sitio del centro de contenido. Seleccione **Listo**.

8. Volverá a la página de **comprensión automatizada del contenido** . En esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración. 

## <a name="see-also"></a>Consulte también



  






