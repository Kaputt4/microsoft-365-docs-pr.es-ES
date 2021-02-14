---
title: Preguntas frecuentes sobre la implementación centralizada
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
description: Revise las respuestas a preguntas frecuentes sobre la implementación centralizada desde el Centro de administración de Microsoft 365.
ms.openlocfilehash: 555496f15663b6607ebc785498bdc94b5e51b9c9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948693"
---
# <a name="centralized-deployment-faq"></a>Preguntas frecuentes sobre la implementación centralizada

La implementación centralizada es la forma recomendada para que un administrador de Office 365 implemente complementos de Office (Word, Excel, PowerPoint y Outlook) para usuarios y grupos dentro de una organización, siempre que la organización cumpla todos los requisitos para usar la implementación centralizada, como se describe en este artículo.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>¿Cómo sé si mi organización está configurada para la implementación centralizada?  

La implementación centralizada de complementos requiere que los usuarios usen Aplicaciones de Microsoft 365 para empresas (y que inicien sesión en Office con sus credenciales de inicio de sesión de la organización) y tengan buzones de Exchange Online. El directorio de suscripción debe estar en Azure Active Directory o federada.  
 
La implementación centralizada solo es compatible con buzones en línea. No admite la implementación en buzones de Exchange locales.

Puede usar el Herramienta de comprobación de compatibilidad [de implementación](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)centralizada para determinar si su suscripción   es apta. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>¿Cómo se apuntan las asignaciones de usuarios de complementos con la implementación centralizada?  

La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del espacio empresarial. La implementación centralizada se puede usar para usuarios de grupos de nivel superior o grupos sin grupos primarios, pero no para usuarios de grupos anidados o grupos que tienen grupos primarios. La implementación centralizada también forma parte de la mayoría de los grupos de Azure Active Directory, incluidos los grupos de Office 365, las listas de distribución y los grupos de seguridad.  

Es mejor usar asignaciones de grupos en lugar de asignaciones de usuarios individuales para facilitar la administración.
 
Para obtener más información, vea [Asignaciones de usuarios y grupos.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments)  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>¿Cuánto tiempo se deben mostrar los complementos para todos los usuarios?  

Un complemento puede tardar hasta 24 horas en mostrarse para todos los usuarios. Las actualizaciones de complementos, los cambios de activar o desactivar, o las eliminaciones de complementos pueden tardar el mismo tiempo. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Como administrador, ¿cómo puedo administrar el acceso de los usuarios a los complementos de mi organización?

Para facilitar la implementación de complementos a usuarios, grupos o a toda la organización, se recomienda que los administradores usen la implementación centralizada.

Para obtener más información acerca de la administración del acceso de usuarios, vea:
 - [Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Especifique los administradores y los usuarios que pueden instalar y administrar complementos para Outlook](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>¿La implementación centralizada proporcionará a los administradores la flexibilidad para elegir el método de implementación para los complementos de Outlook?  

Sí. La implementación centralizada proporciona a los administradores la flexibilidad de elegir uno de los tres métodos de implementación para los complementos de Outlook durante la implementación de complementos:

**Fijo (predeterminado)**   El complemento se implementa automáticamente en los usuarios asignados y no pueden quitarlo.  
 
**Disponible** Los usuarios pueden instalar el complemento en Outlook eligiendo Inicio > Obtener más complementos > **administrados por el administrador.**
 
**Opcional** El complemento se implementa automáticamente en los usuarios asignados, pero pueden elegir quitarlo.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>¿Pueden los administradores actualizar complementos de línea de negocio (LOB)?  

Sí. Los administradores pueden cargar un nuevo archivo de manifiesto para admitir los cambios de metadatos de los complementos de LOB implementados por el administrador. El complemento se actualiza la próxima vez que se inician las aplicaciones de Office. La aplicación web puede cambiar en cualquier momento.  
 
Para obtener más información, vea complemento de línea [de negocio.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security)  

## <a name="can-admins-turn-off-add-ins"></a>¿Pueden los administradores desactivar los complementos?  

Sí. Los administradores pueden activar o desactivar los complementos que implementan para todos los usuarios desde el Centro de administración de Microsoft.

Para obtener más información, vea [Estados de complementos.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states)  

##  <a name="can-admins-delete-or-remove-add-ins"></a>¿Pueden los administradores eliminar o quitar complementos?

Sí. Los administradores pueden eliminar los complementos que implementaron para todos los usuarios del Centro de administración de Microsoft.

Para obtener más información, [vea Eliminar un complemento.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in) 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>¿Pueden los administradores implementar complementos de pago desde la Tienda Office mediante la implementación centralizada? 

No. No puede implementar complementos de pago desde la Tienda Office con la implementación centralizada en este momento.  
 
Se recomienda comunicarse con el desarrollador de ISV para que el complemento de pago solicite un archivo de manifiesto o una dirección URL. A continuación, el administrador de inquilinos puede implementar el complemento como un complemento de LOB mediante la implementación centralizada.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>¿Qué rol de administrador necesito para administrar complementos para mi organización?  

El administrador global es el rol recomendado con acceso completo al ciclo de vida de administración de complementos. Otros roles de administrador tienen un acceso limitado al ciclo de vida de implementación de complementos. Si es la persona que compró su suscripción a Microsoft 365 para empresas, es el administrador global. 
 
La suscripción incluye un conjunto de roles de administrador que puede asignar a otros usuarios de su organización. Cada rol de administrador se asigna a funciones empresariales comunes y concede a los usuarios de su organización permisos para realizar tareas específicas en el Centro de administración de Microsoft 365.  
 
Para obtener más información, vea [Asignar roles de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)  


