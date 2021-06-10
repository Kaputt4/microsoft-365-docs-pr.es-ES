---
title: Preguntas frecuentes sobre la implementación centralizada
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Revise las respuestas a preguntas frecuentes sobre la implementación centralizada desde el centro Microsoft 365 administración.
ms.openlocfilehash: 60d7a91da738803976b6823009450124d7b57814
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579307"
---
# <a name="centralized-deployment-faq"></a>Preguntas frecuentes sobre la implementación centralizada

La implementación centralizada es la forma recomendada para que un administrador de Office 365 implemente complementos de Office (Word, Excel, PowerPoint y Outlook) en usuarios y grupos de una organización, siempre que la organización cumpla todos los requisitos para usar la implementación centralizada, tal como se describe en este artículo.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>¿Cómo sé si mi organización está configurada para la implementación centralizada?  

La implementación centralizada de complementos requiere que los usuarios estén usando Aplicaciones Microsoft 365 para empresas (y que inicien sesión en Office con sus credenciales de inicio de sesión de la organización) y tengan Exchange Online buzones de correo. El directorio de suscripción debe estar en, o federado para, Azure Active Directory.  
 
La implementación centralizada solo es compatible con buzones en línea. No admite la implementación en buzones de correo Exchange local.

Puede usar el Control de compatibilidad [de](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)implementación centralizada   para determinar si la suscripción es apta. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>¿Cómo se apuntan las asignaciones de usuario de complementos con implementación centralizada?  

La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del espacio empresarial. La implementación centralizada se puede usar para usuarios de grupos de nivel superior o grupos sin grupos primarios, pero no para usuarios de grupos anidados o grupos que tienen grupos primarios. La implementación centralizada también forma parte de la mayoría de Azure Active Directory, incluidos Office 365, listas de distribución y grupos de seguridad.  

Es mejor usar asignaciones de grupos en lugar de asignaciones de usuario individuales para facilitar la administración.
 
Para obtener más información, vea [Asignaciones de usuario y grupo.](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>¿Cuánto tiempo se necesita para que los complementos se muestren para todos los usuarios?  

Un complemento puede tardar hasta 24 horas en aparecer para todos los usuarios. Puede tardar la misma cantidad de tiempo en actualizaciones de complementos, cambios desde activar o desactivar, o eliminaciones de complementos. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Como administrador, ¿cómo puedo administrar el acceso de usuario a los complementos de mi organización?

Para facilitar la implementación de complementos a usuarios, grupos o a toda la organización, se recomienda que los administradores usen la implementación centralizada.

Para obtener más información acerca de cómo administrar el acceso de usuarios, vea:
 - [Impedir descargas de complementos desactivando la Tienda Office en todos los clientes (excepto Outlook)](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Especifique qué administradores y usuarios pueden instalar y administrar complementos para Outlook](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>¿La implementación centralizada proporcionará a los administradores la flexibilidad para elegir el método de implementación para Outlook complementos?  

Sí. La implementación centralizada proporciona a los administradores la flexibilidad de elegir uno de los tres métodos de implementación para Outlook complementos durante la implementación del complemento:

**Fijo (predeterminado)**   El complemento se implementa automáticamente en los usuarios asignados y no pueden quitarlo.  
 
**Disponible** Los usuarios pueden instalar el complemento en Outlook seleccionando Inicio > Obtener más complementos > **administrados por el administrador.**
 
**Opcional** El complemento se implementa automáticamente en los usuarios asignados, pero pueden elegir quitarlo.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>¿Pueden los administradores actualizar los complementos de línea de negocio (LOB)  

Sí. Los administradores pueden cargar un nuevo archivo de manifiesto para admitir los cambios de metadatos de los complementos de LOB implementados por el administrador. El complemento se actualiza la próxima vez que se inicien Office aplicaciones. La aplicación web puede cambiar en cualquier momento.  
 
Para obtener más información, [vea line-of-business add-in](./manage-addins-in-the-admin-center.md).  

## <a name="can-admins-turn-off-add-ins"></a>¿Pueden los administradores desactivar los complementos?  

Sí. Los administradores pueden activar o desactivar los complementos que implementan para todos los usuarios desde el Centro de administración de Microsoft.

Para obtener más información, vea [Estados del complemento](./manage-addins-in-the-admin-center.md#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>¿Pueden los administradores eliminar o quitar complementos?

Sí. Los administradores pueden eliminar los complementos que implementaron para todos los usuarios del Centro de administración de Microsoft.

Para obtener más información, [vea Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>¿Pueden los administradores implementar complementos de pago desde Office store mediante la implementación centralizada? 

No. No puedes implementar complementos de pago desde la Tienda Office con la implementación centralizada en este momento.  
 
Te recomendamos que te llegues al desarrollador de ISV para que el complemento de pago solicite un archivo de manifiesto o una dirección URL. A continuación, el administrador del espacio empresarial puede implementar el complemento como complemento de LOB mediante la implementación centralizada.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>¿Qué rol de administrador necesito para administrar complementos para mi organización?  

Administración global es el rol recomendado con acceso completo al ciclo de vida de administración de complementos. Otros roles de administrador tienen un acceso limitado al ciclo de vida de implementación del complemento. Si eres la persona que compró tu suscripción Microsoft 365 para empresas, eres el administrador global. 
 
La suscripción viene con un conjunto de roles de administrador que puede asignar a otros usuarios de la organización. Cada rol de administrador se asigna a funciones empresariales comunes y proporciona a los usuarios de la organización permisos para realizar tareas específicas en el centro de administración Microsoft 365 administración.  
 
Para obtener más información, vea [Asignar roles de administrador](../add-users/assign-admin-roles.md?view=o365-worldwide). 