---
title: Administrar complementos en el centro de administración
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Aprenda a implementar complementos para los usuarios y grupos de su organización mediante la implementación centralizada en el centro de administración.
ms.openlocfilehash: 10bca6776173c07a28b097f44c641c3e65a0cf6c
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948705"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Administrar complementos en el centro de administración

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Los complementos de Office ayudan a personalizar los documentos y simplificar la forma de obtener acceso a la información en la web (vea [empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

Una vez que un administrador implementa complementos para los usuarios de una organización, el administrador puede activar o desactivar el complemento, editar, eliminar y administrar el acceso a los complementos.

Para obtener más información acerca de la instalación de complementos desde el centro de administración, consulte [deploy Add-Ins in the admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).
  
## <a name="add-in-states"></a>Estados del complemento

Un complemento puede estar en el estado **activado** o **desactivado** .
  
|**Estado**|**Cómo se produce el estado**|**Impacto**|
|:-----|:-----|:-----|
|**Active**  <br/> |El administrador ha cargado el complemento y lo ha asignado a usuarios o grupos.  <br/> |Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.  <br/> |
|**Desactivado**  <br/> |El administrador ha desactivado el complemento.  <br/> |Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.  <br/> Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.  <br/> |
|**Eliminado**  <br/> |El administrador ha eliminado el complemento.  <br/> |Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.  <br/> |
   
Considere la posibilidad de eliminar un complemento si no lo está usando ya. Por ejemplo, la desactivación de un complemento puede tener sentido si se usa un complemento sólo durante determinados períodos del año.

## <a name="delete-an-add-in"></a>Eliminar un complemento

También puede eliminar un complemento que se ha implementado.

1. En el centro de administración, vaya a **Settings**la página de los  >  **Complementos &** de los servicios de configuración.

2. Seleccione el complemento implementado.

3. Haga clic en **eliminar complemento**. Quite el botón del complemento en la esquina inferior derecha.

4. Valide las selecciones y elija **quitar complemento**.

## <a name="edit-add-in-access"></a>Editar el acceso del complemento

Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos.

1. En el centro de administración, vaya a **Settings**la página de los  >  **Complementos &** de los servicios de configuración.

2. Seleccione el complemento implementado.

3. Haga clic en **Editar** en la sección **¿quién tiene acceso**?

4. Guarde los cambios.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedir las descargas del complemento desactivando la tienda Office en todos los clientes (excepto Outlook)

> [!NOTE]
> La instalación de complementos de Outlook se administra mediante un [proceso diferente](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Como organización, puede que quiera impedir la descarga de nuevos complementos de Office desde la tienda Office. Esto puede usarse junto con la implementación centralizada para garantizar que solo los complementos aprobados por la organización se implementan para los usuarios de la organización.
  
**Para desactivar la adquisición de complementos**
  
1. En el centro de administración, vaya a la página **Configuración** \>[de servicios &amp;complementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Seleccione **aplicaciones y servicios de propiedad del usuario**.
    
4. Desactive la opción para permitir que los usuarios tengan acceso a la tienda Office.

Esto impedirá que todos los usuarios adquieran los siguientes complementos de la tienda.
  
- Complementos para Word, Excel y PowerPoint 2016 desde:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Adquisiciones que comienzan dentro de **AppSource**
    
- Complementos en Microsoft 365
    
Un usuario que intente obtener acceso a la tienda verá el siguiente mensaje: **lo sentimos, Microsoft 365 se ha configurado para impedir la adquisición individual de complementos de la tienda Office.**
  
La compatibilidad para desactivar la tienda Office está disponible en las siguientes versiones:
  
- Windows: 16.0.9001: actualmente disponible.
    
- Mac: 16.10.18011401: actualmente disponible.
    
- iOS: 2.9.18010804-actualmente disponible.
    
- El Web actualmente disponible.
    
Esto no impide que un administrador use la implementación centralizada para asignar un complemento de la tienda Office.
  
Para evitar que un usuario inicie sesión con una cuenta de Microsoft, puede restringir el inicio de sesión para usar solo la cuenta de la organización. Para obtener más información, vea [identidad, autenticación y autorización en Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).  

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Más información sobre la experiencia del usuario final con los complementos

Después de implementar un complemento, los usuarios finales pueden empezar a usarlo en sus aplicaciones de Office (consulte [empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). El complemento aparece en todas las plataformas admitidas por el complemento.
  
Si el complemento es compatible con comandos de complemento, estos aparecerán en la cinta de opciones de Office. En el siguiente ejemplo, el comando **Buscar cita** aparece para el complemento **Citas**. 

![Cinta de Office con citas de búsqueda](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Si el complemento implementado no es compatible con los comandos de complemento o si desea ver todos los complementos implementados, puede verlos a través **de mis complementos**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>En Word 2016, Excel 2016 o PowerPoint 2016

1. Seleccione **Insertar \> mis complementos**. 
    
2. Seleccione la pestaña **Gestionado por el administrador** en la ventana Complementos de Office. 
    
3. Haga doble clic en el complemento que ha implementado antes (en este ejemplo, **Citas** ). <br/>![Pestaña administrada de administración de la página de complementos de Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>En Outlook

1. En la cinta de opciones **Inicio** , seleccione **obtener complementos**.<br/>![Botón Tienda en Outlook](../../media/getaddinsicon.png)
  
2. Seleccione **administrada por el administrador** en el panel de navegación izquierdo. 

## <a name="learn-more"></a>Más información

[Implementar complementos en el centro de administración](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Obtenga más información sobre la creación y generación de [complementos de Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).
  
[Use cmdlets de PowerShell de implementación centralizada para administrar complementos](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).
  
[Solución de problemas: el usuario no ve complementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Menores y adquisición de complementos de Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)