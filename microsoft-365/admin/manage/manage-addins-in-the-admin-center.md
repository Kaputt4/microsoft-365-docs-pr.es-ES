---
title: Administrar complementos en el centro de administración
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Obtenga información sobre el uso de complementos centralizados para implementar complementos en usuarios y grupos de la organización.
ms.openlocfilehash: f6e26af9bdc6379b89474c36173fa263fc1ab5aa
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731269"
---
# <a name="manage-add-ins-in-the-microsoft-365-admin-center"></a>Administración de complementos en el Centro de administración de Microsoft 365

Los complementos de Office le ayudan a personalizar sus documentos y a simplificar la forma en que accede a la información en la web. Consulte [Empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862). 

Después de que un administrador global o de Exchange implemente complementos para los usuarios de una organización, puede desactivar o activar los complementos, editar, eliminar y administrar el acceso a los complementos.

Para obtener más información sobre cómo instalar complementos desde el centro de administración, consulte [Implementación de complementos en el centro de administración](./manage-deployment-of-add-ins.md).
  
## <a name="add-in-states"></a>Estados del complemento

Un complemento puede estar en estado **Activado** o **Desactivado** .
  
| Estado | Cómo se produce el estado | Impacto |
|:-----|:-----|:-----|
|**Activo**  <br/> |Administración cargó el complemento y lo asignó a usuarios o grupos.  <br/> |Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.  <br/> |
|**Desactivado**  <br/> |El administrador ha desactivado el complemento.  <br/> |Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.  <br/> Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.  <br/> |
|**Eliminado**  <br/> |El administrador ha eliminado el complemento.  <br/> |Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.  <br/> |
   
Considere la posibilidad de eliminar un complemento si ya no lo usa nadie. Por ejemplo, desactivar un complemento podría tener sentido si un complemento se usa solo durante horas específicas del año.

## <a name="delete-an-add-in"></a>Eliminar un complemento

También puede eliminar un complemento que se implementó.

1. En el centro de administración, vaya a la página Aplicaciones **integradas** **de configuración** > .

2. Seleccione el complemento implementado y, a continuación, seleccione la pestaña **Configuración**.

3. En el panel **Configuración**, vaya a **Complementos de** **configuración** >  avanzada.

4. Vuelva a seleccionar el complemento de la lista.

5. Elija **Quitar complemento**. Quite el botón del complemento en la esquina inferior derecha.

6. Valide su selección y elija **Quitar**.

## <a name="edit-add-in-access"></a>Editar el acceso del complemento

Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos.

1. En el centro de administración, vaya a la página Aplicaciones **integradas** **de configuración** > .

2. Seleccione el complemento implementado.

3. Haga clic **Editar** bajo **Quién tiene acceso**.

4. Guarde los cambios.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)

> [!NOTE]
> La instalación del complemento de Outlook se administra mediante un [proceso diferente](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).

Como organización, es posible que desee impedir la descarga de nuevos complementos de Office desde la Tienda Office. Esto se puede usar junto con la implementación centralizada para asegurarse de que solo los complementos aprobados por la organización se implementan en los usuarios de la organización.
  
**Para desactivar la adquisición de complementos**
  
1. En el centro de administración, vaya a la página **Configuración** \> [de la organización](https://go.microsoft.com/fwlink/p/?linkid=2053743) .

2. Seleccione **Aplicaciones y servicios que pertenecen al usuario**.
    
3. Desactive la opción para permitir que los usuarios accedan a la Tienda Office.

    Esto impedirá que todos los usuarios adquieran los siguientes complementos del Store.
      
    - Complementos para Word, Excel y PowerPoint 2016 desde:
        
      - Windows
      - Mac
      - Oficina
        
        
    - Adquisiciones a partir de **AppSource**
        
    - Complementos dentro de Microsoft 365
        
    Un usuario que intente acceder a la tienda verá el siguiente mensaje: **Lo sentimos, Microsoft 365 se ha configurado para evitar la adquisición individual de complementos de la Tienda Office.**
  
La compatibilidad con la desactivación de la Tienda Office está disponible en las siguientes versiones:
  
- Windows: 16.0.9001: actualmente disponible.
    
- Mac: 16.10.18011401 - Actualmente disponible.
    
- iOS: 2.9.18010804: disponible actualmente.
    
- Web: disponible actualmente.
    
Esto no impide que un administrador use la implementación centralizada para asignar un complemento desde la Tienda Office.

> [!NOTE] 
> Los complementos como visualizador de datos de Visio, mapas de Bing y Personas Graph seguirán apareciendo en la cinta de opciones, incluso si un administrador ha deshabilitado la Tienda. Para quitar estos vínculos, los administradores deben deshabilitar la Tienda a través de directiva de grupo Objeto (GPO).
  
Para evitar que un usuario inicie sesión con una cuenta de Microsoft, puede restringir el inicio de sesión para que use solo la cuenta de la organización. Para obtener más información, vea [Identidad, autenticación y autorización en Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).  

> [!NOTE] 
> Impedir que los usuarios accedan a la tienda de Office también les impedirá [transferir localmente complementos de Office para realizar pruebas desde un recurso compartido de red](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Más información sobre la experiencia del usuario final con complementos

Después de implementar un complemento, los usuarios finales pueden empezar a usarlo en sus aplicaciones de Office. El complemento aparece en todas las plataformas compatibles con el complemento. Consulte [Empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862). 
  
If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in. 

![Cinta de Office con citas de búsqueda.](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Si el complemento implementado no admite comandos de complemento o si desea ver todos los complementos implementados, puede verlos a través **de Mis complementos**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>En Word 2016, Excel 2016 o PowerPoint 2016

1. Seleccione **Insertar \> mis complementos**. 
    
2. Seleccione la pestaña **Gestionado por el administrador** en la ventana Complementos de Office. 
    
3. Haga doble clic en el complemento que implementó anteriormente (en este ejemplo, **Citas**).

    ![Administración pestaña Administrado de la página Complementos de Office.](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>En Outlook

1. En la cinta **Inicio** , seleccione **Obtener complementos**.

    ![Botón Almacenar en Outlook.](../../media/getaddinsicon.png)
  
2. Seleccione **Gestionado por el administrador** en la barra de navegación izquierda. 

## <a name="related-content"></a>Contenido relacionado

[Menores y adquisición de complementos de Microsoft Store](./minors-and-acquiring-addins-from-the-store.md)

