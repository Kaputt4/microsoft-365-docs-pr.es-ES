---
title: Administrar complementos en el centro de administración
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Obtenga información sobre el uso de complementos centralizados para implementar complementos para usuarios y grupos de la organización.
ms.openlocfilehash: a27fc3744ab0dfc9256afbb6e08e881d2d35fb48
ms.sourcegitcommit: a84a7a9bda2b616a24af03b89a84f5e75ebfc0c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2021
ms.locfileid: "53578378"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Administrar complementos en el centro de administración

Office complementos le ayudarán a personalizar los documentos y simplificar la forma en que tiene acceso a la información en la web (vea Empezar a usar el complemento [Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)web ). 

Después de que un administrador implemente complementos para los usuarios de una organización, el administrador puede desactivar o activar los complementos, editar, eliminar y administrar el acceso a los complementos.

Para obtener más información acerca de la instalación de complementos desde el Centro de administración, vea [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).
  
## <a name="add-in-states"></a>Estados del complemento

Un complemento puede estar en el **estado On** o **Off.**
  
| Estado | Cómo se produce el estado | Impacto |
|:-----|:-----|:-----|
|**Activo**  <br/> |El administrador carizó el complemento y lo asignó a usuarios o grupos.  <br/> |Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.  <br/> |
|**Desactivado**  <br/> |El administrador ha desactivado el complemento.  <br/> |Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.  <br/> Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.  <br/> |
|**Eliminado**  <br/> |El administrador ha eliminado el complemento.  <br/> |Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.  <br/> |
   
Considere la posibilidad de eliminar un complemento si ya nadie lo está usando. Por ejemplo, desactivar un complemento puede tener sentido si un complemento se usa solo durante determinadas horas del año.

## <a name="delete-an-add-in"></a>Eliminar un complemento

También puede eliminar un complemento que se implementó.

1. En el Centro de administración, vaya a la **página Configuración** servicios  >  **& complementos.**

    > [!NOTE]
    > También puede implementar complementos en el Centro de administración a través de [Aplicaciones integradas.](test-and-deploy-microsoft-365-apps.md) Las aplicaciones integradas son visibles para los administradores Exchange global y de usuario. Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a **Configuración**  >  **aplicaciones integradas.** En la parte superior de la página Aplicaciones **integradas,** elija Complementos . 

2. Seleccione el complemento implementado.

3. Haga clic **en Eliminar complemento**. Quite el botón Complemento de la esquina inferior derecha.

4. Valide su selección y elija **Quitar complemento**.

## <a name="edit-add-in-access"></a>Editar el acceso del complemento

Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos.

1. En el Centro de administración, vaya a la **página Configuración** servicios  >  **& complementos.**

    > [!NOTE]
    > También puede implementar complementos en el Centro de administración a través de [Aplicaciones integradas.](test-and-deploy-microsoft-365-apps.md) Las aplicaciones integradas son visibles para los administradores Exchange global y de usuario. Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a **Configuración**  >  **aplicaciones integradas.** En la parte superior de la página Aplicaciones **integradas,** elija Complementos . 


2. Seleccione el complemento implementado.

3. Haga clic **en Editar** en Quién **tiene Access**.

4. Guarde los cambios.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)

> [!NOTE]
> Outlook instalación del complemento se administra mediante un [proceso diferente.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)

Como organización, es posible que quieras impedir la descarga de nuevos Office complementos de la Office Store. Esto se puede usar junto con la implementación centralizada para garantizar que solo los complementos aprobados por la organización se implementen en los usuarios de la organización.
  
**Para desactivar la adquisición de complementos**
  
1. En el centro de administración, vaya a la página **Configuración** \>[de servicios &amp;complementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).

    > [!NOTE]
    > También puede implementar complementos en el Centro de administración a través de [Aplicaciones integradas.](test-and-deploy-microsoft-365-apps.md) Las aplicaciones integradas son visibles para los administradores Exchange global y de usuario. Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo a **Configuración**  >  **aplicaciones integradas.** En la parte superior de la página Aplicaciones **integradas,** elija Complementos . 

    
3. Seleccione **Aplicaciones y servicios que pertenecen al usuario**.
    
4. Desactive la opción para permitir que los usuarios accedan a la Tienda Office.

    Esto impedirá que todos los usuarios adquieran los siguientes complementos de la tienda.
      
    - Complementos para Word, Excel y PowerPoint 2016 desde:
        
      - Windows
      - Mac
      - Office
        
        
    - Adquisiciones a partir de **AppSource**
        
    - Complementos dentro de Microsoft 365
        
    Un usuario que intente acceder a la tienda verá el siguiente mensaje: Lo sentimos, Microsoft 365 se ha configurado para impedir la adquisición individual de Office complementos de la **Tienda.**
  
La compatibilidad para desactivar la tienda Office está disponible en las siguientes versiones:
  
- Windows: 16.0.9001: Actualmente disponible.
    
- Mac: 16.10.18011401- Actualmente disponible.
    
- iOS: 2.9.18010804: disponible actualmente.
    
- La web: disponible actualmente.
    
Esto no impide que un administrador use la implementación centralizada para asignar un complemento desde Office Store.

> [!NOTE] 
> Los complementos como Visio Data Visualizer, mapas de Bing y People Graph se mostrarán en la cinta de opciones, incluso si un administrador ha deshabilitado la Tienda. Para quitar estos vínculos, los administradores deben deshabilitar el almacén a través del objeto de directiva de grupo (GPO).
  
Para evitar que un usuario inicie sesión con una cuenta de Microsoft, puede restringir el inicio de sesión para usar solo la cuenta de la organización. Para obtener más información, vea [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).  

> [!NOTE] 
> Impedir que los usuarios accedan a la tienda de office también impedirá que puedan realizar la instalación Office complementos para realizar [pruebas desde un recurso compartido de red.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Más información sobre la experiencia del usuario final con complementos

Después de implementar un complemento, los usuarios finales pueden empezar a usarlo en sus aplicaciones de Office (vea [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). El complemento aparece en todas las plataformas compatibles con el complemento.
  
Si el complemento es compatible con comandos de complemento, estos aparecerán en la cinta de opciones de Office. En el siguiente ejemplo, el comando **Buscar cita** aparece para el complemento **Citas**. 

![Office cinta de opciones con citas de búsqueda](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Si el complemento implementado no admite comandos de complemento o si desea ver todos los complementos implementados, puede verlos a través de **Mis complementos**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>En Word 2016, Excel 2016 o PowerPoint 2016

1. Seleccione **Insertar \> mis complementos**. 
    
2. Seleccione la pestaña **Gestionado por el administrador** en la ventana Complementos de Office. 
    
3. Haga doble clic en el complemento que implementó anteriormente (en este ejemplo, **Citations**).

    ![Pestaña Administración administrada de la Office complementos](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>En Outlook

1. En la **cinta de** opciones Inicio, seleccione **Obtener complementos**.

    ![Botón Tienda en Outlook](../../media/getaddinsicon.png)
  
2. Seleccione **Gestionado por el administrador** en la barra de navegación izquierda. 

## <a name="related-content"></a>Contenido relacionado

[Implementar complementos en el Centro](./manage-deployment-of-add-ins.md) de administración (artículo)\
Obtenga más información sobre cómo crear [y crear Office complementos](/office/dev/add-ins/overview/office-add-ins) (artículo)\
[Usar cmdlets de PowerShell de implementación centralizada para administrar complementos](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (artículo)\
[Solución de problemas: el usuario no ve complementos](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artículo)\
[Menores y la adquisición de complementos](./minors-and-acquiring-addins-from-the-store.md) de la Microsoft Store (artículo)
