---
title: Configuración de Microsoft Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom:
- admindeeplinkMAC
search.appverid: MET150
ms.localizationpriority: high
description: Configure Microsoft Syntex.
ms.openlocfilehash: b6a7309e9ae833f643930d9f308c1b748afeb0f5
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68659595"
---
# <a name="set-up-microsoft-syntex"></a>Configuración de Microsoft Syntex

Los administradores pueden usar la <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> para configurar Microsoft Syntex. 

Considere lo siguiente antes de empezar:

- ¿En qué sitios de SharePoint habilitará el procesamiento de documentos? ¿Todos ellos, algunos, o seleccionar sitios?
- ¿Qué nombre le pondrá a su centro de contenido de forma predeterminada?

Puede cambiar su configuración después de la configuración inicial en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>.

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make the following decisions:

- Los sitios de SharePoint en los que desea habilitar el procesamiento de documentos: todos ellos, algunos o sitios seleccionados
- El nombre y los administradores de su centro de contenido

## <a name="requirements"></a>Requirements 

> [!NOTE]
> Debe tener permisos de administrador global o administrador de SharePoint para poder acceder a la Centro de administración de Microsoft 365 y configurar Syntex.

Como administrador, también puede realizar cambios en la configuración seleccionada en cualquier momento después de la configuración, y a lo largo de la introducción al contenido de la configuración de administración en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>.

### <a name="custom-power-platform-environments"></a>Entornos de Power Platform personalizados

Si tiene previsto usar un entorno de Power Platform personalizado, deberá instalar la aplicación *AI Builder para Proyecto Cortex* en este entorno. Consulte [Administración de aplicaciones de Dynamics 365](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) para obtener más información y busque la aplicación *AI Builder para Proyecto Cortex* en la lista de aplicaciones de Dynamics 365.

También debe [asignar créditos de AI Builder](/power-platform/admin/capacity-add-on) al entorno personalizado para poder crear modelos de procesamiento de documentos. 

When using a custom environment, model creators must be assigned the Environment Maker security role and model users must be assigned the Basic User security role. See [Assign a security role to a user](/power-platform/admin/assign-security-roles) for more information.

Los usuarios que crean modelos en un [sitio del centro de contenido](/microsoft-365/contentunderstanding/create-a-content-center) deben ser miembros del sitio. Los usuarios que crean modelos localmente fuera del centro de contenido deben ser propietarios de los sitios.

### <a name="licensing"></a>Licencias

Para usar Syntex, su organización debe tener una suscripción a Syntex y cada usuario debe tener asignadas licencias. Las licencias de Syntex incluyen las siguientes aplicaciones, que deben asignarse:

- Syntex
- Syntex: tipo SPO
- Common Data Service para Syntex

Para usar modelos estructurados de procesamiento de documentos o procesamiento de documentos de forma libre, también necesita créditos de AI Builder. Para cada usuario con licencia de Syntex, se proporciona una asignación de créditos de AI Builder cada mes.

Para obtener más información sobre las licencias de Syntex, consulte [Licencias de Microsoft Syntex](syntex-licensing.md).

## <a name="to-set-up-syntex"></a>Para configurar Syntex

1. En el Centro de administración de Microsoft 365, seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=2171997" target="_blank">**Configuración**</a> y luego consulte la sección **Archivos y contenido**.

2. En la sección **Archivos y contenido**, seleccione **Automatizar la comprensión del contenido**. Tenga en cuenta que la disponibilidad de crédito actual del Generador de IA se muestra en la sección **De un vistazo**.<br/>

3. En la página para **Automatizar la comprensión del contenido**, haga clic en **Introducción** para recorrer el proceso de configuración. <br/>

    > [!div class="mx-imgBorder"]
    > ![Iniciar la instalación.](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. En la página **Configurar procesamiento de formularios** , puede elegir si desea permitir que los usuarios puedan crear modelos de procesamiento de documentos en bibliotecas de documentos específicas de SharePoint. En la cinta de opciones de la biblioteca de documentos estará disponible una opción de menú para **Crear un modelo de procesamiento de formularios** en las bibliotecas de documentos de SharePoint en las que esté habilitado.
 
     Para **Qué bibliotecas de SharePoint debe mostrar la opción de crear un modelo de procesamiento de formularios**, puede seleccionar:</br>
      - **Bibliotecas en todos los sitios de SharePoint** para que esté disponible en todas las bibliotecas de SharePoint de su organización.</br>
      - **Bibliotecas en los sitios de SharePoint seleccionados**, y a luego, seleccione los sitios en los que desea que esté disponible o cargue una lista de hasta 50 sitios.</br>
      - **No hay bibliotecas de SharePoint** si no quiere que esté disponible para ningún sitio (puede cambiar esto después de la configuración).

   > [!div class="mx-imgBorder"]
   > ![Configure las opciones del sitio de procesamiento de documentos.](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > La eliminación de un sitio después de que se haya incluido no afecta a los modelos existentes aplicados a las bibliotecas de ese sitio ni a la capacidad de aplicar modelos de procesamiento de documentos no estructurados a una biblioteca. 
    
    Si tiene varios entornos de Power Platform configurados, puede elegir con qué uno desea usar para el procesamiento de documentos. (Esta opción no aparecerá si solo tiene un entorno).

    ![Configure las opciones de Power Platform de procesamiento de documentos.](../media/content-understanding/setup-power-platform-env.png)

    Para el **entorno de Power Platform**, puede seleccionar:
    - **Usar el entorno predeterminado** para utilizar su entorno de Power Platform predeterminado.
    - **Usar un entorno personalizado** para utilizar un entorno personalizado. De la lista, elija el entorno que quiera utilizar. ([Ver los requisitos de un entorno personalizado](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).

    Haga clic en **Siguiente**.

5. En la página **Crear centro de contenido** , puede crear un sitio del Centro de contenido de SharePoint donde los usuarios puedan crear y administrar modelos de procesamiento de documentos no estructurados. Si anteriormente creó un centro de contenido desde el Centro de administración de SharePoint, esa información se mostrará aquí y solo podrá seleccionar **Siguiente**.

    1. Para el **Nombre del sitio**, escriba el nombre que quiere darle a su sitio de centro de contenido.
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![Crear el centro de contenido.](../media/content-understanding/admin-cu-create-cc.png)</br>

       Seleccione **Siguiente**.

6. En la página **Revisar y finalizar**, puede mirar el ajuste seleccionado y elegir hacer cambios. Si está de acuerdo con las selecciones, seleccione **Activar**.

7. En la página de confirmación, haga clic en **Listo**.

8. Volverá a su página **Automatizar la comprensión del contenido**. Desde esta página, puede seleccionar **administrar** para realizar cambios en las opciones de configuración. 

## <a name="assign-licenses"></a>Asignar licencias

Una vez que haya configurado Syntex, debe asignar licencias para los usuarios que usarán las características de Syntex.

Para asignar licencias:

1. En el Centro de administración de Microsoft 365, en **Usuarios**, seleccione <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Usuarios activos**</a>.

2. Seleccione los usuarios a los que quiere conceder licencias y haga clic en **Administrar licencias de productos**.

3. Elija **Aplicaciones** en el menú desplegable.

4. Seleccione **Mostrar aplicaciones para Syntex**. En **Aplicaciones**, asegúrese de que **Common Data Service para Syntex**, **Syntex** y **Syntex : tipo SPO** estén seleccionados.

    > [!div class="mx-imgBorder"]
    > ![Licencias de Syntex en el Centro de administración de Microsoft 365.](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Haga clic en **Guardar cambios**.

## <a name="see-also"></a>Consulte también

[Introducción al modelo de procesamiento de documentos en AI Builder](/ai-builder/form-processing-model-overview)

[Crear y administrar entornos en el Centro de administración de la Power Platform](/power-platform/admin/create-environment)
