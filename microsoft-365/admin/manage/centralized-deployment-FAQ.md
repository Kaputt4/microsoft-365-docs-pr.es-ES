---
title: Preguntas frecuentes sobre implementación centralizada
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Revise las respuestas a preguntas frecuentes sobre la implementación centralizada en el centro de administración de Microsoft 365.
ms.openlocfilehash: c389ab07136b8a6e625db9ecfeff514a6899cd7d
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011740"
---
# <a name="centralized-deployment-faq"></a>Preguntas frecuentes sobre implementación centralizada

La implementación centralizada es la forma recomendada para que un administrador de Office 365 implemente complementos de Office (Word, Excel, PowerPoint y Outlook) para usuarios y grupos de una organización, siempre que la organización cumpla todos los requisitos para usar la implementación centralizada, tal como se describe en este artículo.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>¿Cómo sé si mi organización está configurada para la implementación centralizada?  

La implementación centralizada de complementos requiere que los usuarios usen las aplicaciones de Microsoft 365 para empresas (y que hayan iniciado sesión en Office con sus credenciales de inicio de sesión en la organización) y tengan buzones de Exchange Online. El directorio de suscripción debe estar o estar federado a Azure Active Directory.  
 
La implementación centralizada solo se admite para los buzones de correo en línea. No admite la implementación en buzones de Exchange locales.
 
Puede usar el  [Comprobador de compatibilidad de implementación centralizada de Office 365](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)para determinar si la suscripción es apta. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>¿Cómo se dirigen las asignaciones de usuario de complementos con una implementación centralizada?  

La implementación centralizada admite asignaciones a usuarios individuales, grupos y a todos los miembros del espacio empresarial. La implementación centralizada se puede usar para los usuarios de grupos de nivel superior o grupos sin grupos primarios, pero no para los usuarios de grupos anidados o grupos que tienen grupos primarios. La implementación centralizada también forma parte de la mayoría de los grupos de Azure Active Directory, incluidos los grupos de Office 365, las listas de distribución y los grupos de seguridad.  

Es mejor usar asignaciones de grupos en lugar de asignación de usuario individual para facilitar la administración.
 
Para obtener más información, vea [asignaciones de usuarios y grupos](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>¿Cuánto tiempo se tarda en mostrar los complementos para todos los usuarios?  

Un complemento puede tardar hasta 24 horas en mostrarse para todos los usuarios. Puede tardar la misma cantidad de tiempo en las actualizaciones de los complementos, los cambios de desactivación o desactivación, o la eliminación de complementos. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Como administrador, ¿cómo se administra el acceso del usuario a los complementos de mi organización?

Para facilitar la implementación de complementos a usuarios, grupos o a toda la organización, se recomienda que los administradores usen la implementación centralizada.

Para obtener más información acerca de la administración del acceso de usuarios, consulte </br>[Evite las descargas de complementos desactivando la tienda Office en todos los clientes (excepto Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) y </br>[Especifique los administradores y los usuarios que pueden instalar y administrar complementos para Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>¿La implementación centralizada proporciona a los administradores la flexibilidad necesaria para elegir el método de implementación para complementos de Outlook?  

Sí. La implementación centralizada proporciona a los administradores la flexibilidad de elegir uno de los tres métodos de implementación para los complementos de Outlook durante la implementación de complementos:

**Fija (predeterminada)**   el complemento se implementa automáticamente en los usuarios asignados y no puede quitarlos.  
 
**Disponible** Los usuarios pueden instalar el complemento en Outlook eligiendo Inicio > obtener más complementos > administración administrada por el administrador.   
 
**Opcional** El complemento se implementa automáticamente en los usuarios asignados, pero puede elegir quitarlos.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>¿Los administradores pueden actualizar los complementos de línea de negocio (LOB)?  

Sí. Los administradores pueden cargar un nuevo archivo de manifiesto para admitir los cambios de metadatos para los complementos LOB implementados por el administrador. El complemento se actualiza la próxima vez que se inicien las aplicaciones de Office. La aplicación web puede cambiar en cualquier momento.  
 
Para obtener más información, consulte [complemento de línea de negocio](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).  

## <a name="can-admins-turn-off-add-ins"></a>¿Pueden los administradores desactivar los complementos?  

Sí. Los administradores pueden activar o desactivar los complementos que implementan para todos los usuarios desde el centro de administración de Microsoft.

Para obtener más información, consulte [Estados de complementos](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>¿Los administradores pueden eliminar o quitar complementos?

Sí. Los administradores pueden eliminar complementos implementados para todos los usuarios desde el centro de administración de Microsoft.

Para obtener más información, vea [eliminar el complemento](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>¿Pueden los administradores implementar complementos de pago desde la tienda Office con una implementación centralizada? 

No. No puede implementar complementos de pago desde la tienda Office con la implementación centralizada en este momento.  
 
Le sugerimos que llegue al desarrollador de ISV para que el complemento de pago solicite un archivo de manifiesto o una dirección URL. A continuación, el administrador de inquilinos puede implementar el complemento como un complemento de LOB mediante una implementación centralizada.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>¿Qué rol de administración necesito para administrar los complementos de mi organización?  

Debe tener el rol de administrador global para administrar complementos. Si usted es la persona que compró su suscripción de Microsoft 365 para empresas, será el administrador global. 
 
Su suscripción incluye un conjunto de roles de administrador que puede asignar a otros usuarios de su organización. Cada rol de administrador se asigna a funciones empresariales comunes y proporciona a los usuarios de su organización permisos para realizar tareas específicas en el centro de administración de 365 de Microsoft.  
 
Para obtener más información, vea [asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).  