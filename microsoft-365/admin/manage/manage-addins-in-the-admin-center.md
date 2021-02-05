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
description: Obtenga información sobre el uso de complementos centralizados para implementar complementos en usuarios y grupos de su organización.
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114206"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Administrar complementos en el centro de administración

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Los complementos de Office le ayudan a personalizar los documentos y a simplificar la forma en que accede a la información en la Web (vea Empezar a usar [el complemento de Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 

Después de que un administrador implemente complementos para los usuarios de una organización, el administrador puede desactivar o activar los complementos, editar, eliminar y administrar el acceso a los complementos.

Para obtener más información acerca de la instalación de complementos desde el centro de administración, vea Implementar complementos [en el centro de administración.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)
  
## <a name="add-in-states"></a>Estados del complemento

Un complemento puede estar en estado **De on** o **desactivado.**
  
|**Estado**|**Cómo se produce el estado**|**Impacto**|
|:-----|:-----|:-----|
|**Active**  <br/> |El administrador carizó el complemento y lo asignó a usuarios o grupos.  <br/> |Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.  <br/> |
|**Desactivado**  <br/> |El administrador ha desactivado el complemento.  <br/> |Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.  <br/> Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.  <br/> |
|**Eliminado**  <br/> |El administrador ha eliminado el complemento.  <br/> |Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.  <br/> |
   
Considere la posibilidad de eliminar un complemento si ya no lo está usando nadie. Por ejemplo, desactivar un complemento puede tener sentido si un complemento se usa solo durante determinadas horas del año.

## <a name="delete-an-add-in"></a>Eliminar un complemento

También puede eliminar un complemento que se implementó.

1. En el centro de administración, vaya a la página **Servicios**  >  **& configuración.**

     > [!NOTE]
    > El centro de administración se está actualizando a la experiencia de implementación con aplicaciones integradas. Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo **a** Aplicaciones integradas  >  **de configuración.** En la parte superior de la **página Aplicaciones integradas,** elija **Complementos.**

2. Seleccione el complemento implementado.

3. Haga clic **en Eliminar complemento.** Quite el botón Complemento en la esquina inferior derecha.

4. Valide las selecciones y elija **Quitar complemento.**

## <a name="edit-add-in-access"></a>Editar el acceso al complemento

Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos.

1. En el centro de administración, vaya a la página **Servicios**  >  **& configuración.**

     > [!NOTE]
    > El centro de administración se está actualizando a la experiencia de implementación con aplicaciones integradas. Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo **a** Aplicaciones integradas  >  **de configuración.** En la parte superior de la **página Aplicaciones integradas,** elija **Complementos.**

2. Seleccione el complemento implementado.

3. Haga clic **en Editar** en Quién **tiene acceso.**

4. Guarde los cambios.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)

> [!NOTE]
> La instalación del complemento de Outlook se administra mediante un [proceso diferente.](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)

Como organización, es posible que desee impedir la descarga de nuevos complementos de Office desde la Tienda Office. Esto se puede usar junto con la implementación centralizada para garantizar que solo se implementen complementos aprobados por la organización para los usuarios de la organización.
  
**Para desactivar la adquisición de complementos**
  
1. En el centro de administración, vaya a la página **Configuración** \>[de servicios &amp;complementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).

     > [!NOTE]
    > El centro de administración se está actualizando a la experiencia de implementación con aplicaciones integradas. Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo **a** Aplicaciones integradas  >  **de configuración.** En la parte superior de la **página Aplicaciones integradas,** elija **Complementos.**
    
3. Seleccione **Aplicaciones y servicios propiedad del usuario.**
    
4. Desactive la opción para permitir que los usuarios accedan a la Tienda Office.

Esto impedirá que todos los usuarios adquieran los siguientes complementos de la tienda.
  
- Complementos para Word, Excel y PowerPoint 2016 desde:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Adquisiciones a partir de **AppSource**
    
- Complementos de Microsoft 365
    
Un usuario que intente acceder a la tienda verá el siguiente mensaje: Lo **sentimos, Microsoft 365** se ha configurado para impedir la adquisición individual de complementos de la Tienda Office.
  
La compatibilidad para desactivar la Tienda Office está disponible en las siguientes versiones:
  
- Windows: 16.0.9001 - Actualmente disponible.
    
- Mac: 16.10.18011401 - Disponible actualmente.
    
- iOS: 2.9.18010804 - Actualmente disponible.
    
- La web: disponible actualmente.
    
Esto no impide que un administrador use la implementación centralizada para asignar un complemento desde la Tienda Office.
  
Para impedir que un usuario inicie sesión con una cuenta de Microsoft, puede restringir el inicio de sesión para que use solo la cuenta de la organización. Para obtener más información, vea [Identidad, autenticación y autorización en Office 2016.](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)  

> [!NOTE]
> Impedir que los usuarios accedan a la tienda office también les impedirá realizar la instalación de prueba de complementos [de Office.](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Más información sobre la experiencia del usuario final con los complementos

Después de implementar un complemento, los usuarios finales pueden empezar a usarlo en sus aplicaciones de Office (vea Empezar a usar [el complemento de Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) El complemento aparece en todas las plataformas compatibles con el complemento.
  
Si el complemento es compatible con comandos de complemento, estos aparecerán en la cinta de opciones de Office. En el siguiente ejemplo, el comando **Buscar cita** aparece para el complemento **Citas**. 

![Cinta de Office con citas de búsqueda](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Si el complemento implementado no admite comandos de complemento o si desea ver todos los complementos implementados, puede verlos a través de Mis **complementos.** 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>En Word 2016, Excel 2016 o PowerPoint 2016

1. Seleccione **Insertar \> mis complementos.** 
    
2. Seleccione la pestaña **Gestionado por el administrador** en la ventana Complementos de Office. 
    
3. Haga doble clic en el complemento que ha implementado antes (en este ejemplo, **Citas** ). <br/>![Pestaña Administración de administración de la página Complementos de Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>En Outlook

1. En la **cinta de opciones** inicio, seleccione Obtener **complementos.**<br/>![Botón Tienda en Outlook](../../media/getaddinsicon.png)
  
2. Seleccione **Administrado por el administrador** en el panel de navegación izquierdo. 

## <a name="learn-more"></a>Obtén más información

[Implementar complementos en el centro de administración](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Obtenga más información sobre la creación y generación de [complementos de Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).
  
[Use cmdlets de PowerShell de implementación centralizada para administrar complementos.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Solución de problemas: el usuario no ve complementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Menores de edad y adquisición de complementos de Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
