---
title: Comprender las suscripciones y licencias en Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Obtenga información sobre las suscripciones y licencias en Microsoft 365 para empresas.
ms.date: 07/01/2020
ms.openlocfilehash: ccfcb52548fb79267c550afba63c2f5a96b99ed1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928515"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Comprender las suscripciones y licencias en Microsoft 365 para empresas

Al comprar una suscripción a Microsoft 365 para empresas, se registra para obtener un conjunto de aplicaciones y servicios que paga mensualmente o anualmente. Las aplicaciones y servicios que reciba como parte de su suscripción dependen del producto que haya comprado, como Aplicaciones de Microsoft 365 para empresas o Microsoft 365 Empresa Standard. Puede ver lo que incluye cada producto en la página [de Microsoft 365](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) para pequeñas y medianas empresas.

Cuando compra una suscripción, debe especificar el número de licencias que necesita, en función de cuántos usuarios tiene en su organización. Después de comprar una suscripción, se crean cuentas para los usuarios de la organización y, a continuación, se asigna una licencia a cada persona. A medida que cambien las necesidades de su organización, puede comprar más licencias para dar cabida a nuevos usuarios o reasignar licencias a otros usuarios cuando alguien abandona la organización.

Si tiene más de una suscripción, puede asignar licencias a usuarios diferentes para cada suscripción. Por ejemplo, puede asignar todos los usuarios a todas las aplicaciones y servicios de Microsoft 365 como parte de una suscripción a Microsoft 365 Empresa Standard. También puede asignar un subconjunto de usuarios a Visio Online a través de una suscripción de Visio independiente.

## <a name="how-many-devices-can-people-install-office-on"></a>¿En cuántos dispositivos se puede instalar Office?

Si su suscripción incluye cualquiera de los siguientes productos, cada persona puede instalar Office en hasta cinco equipos PC o Mac, cinco tabletas y cinco teléfonos.

:::row:::
   :::column span="":::
        - Aplicaciones de Microsoft 365 para empresas - Aplicaciones de Microsoft 365 para empresas - Microsoft 365 Empresa Estándar - Microsoft 365 Empresa Premium - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>¿Qué sucede cuando asigna una licencia a alguien?

En la tabla siguiente, se muestra una lista con lo que sucede automáticamente al asignar una licencia a un usuario:
  
|**Si la suscripción tiene este servicio**|**Esto sucede automáticamente**|
|:-----|:-----|
|Exchange Online  <br/> |Se crea un buzón para el usuario. <br/> Para obtener información sobre el SLA para que esta tarea se complete, consulte ["Configuración...". en el Centro de administración de Microsoft 365.](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center) |
|SharePoint Online  <br/> |Se asignan al usuario permisos de edición para el sitio de grupo predeterminado de SharePoint Online.  <br/> |
|Skype Empresarial Online  <br/> |La persona tiene acceso a las características asociadas con la licencia.  <br/> |
|Aplicaciones de Microsoft 365 para empresas  <br/> |La persona puede descargar aplicaciones de Office en hasta cinco Equipos Mac o PC, cinco tabletas y cinco smartphones.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Información sobre las licencias para los buzones que no son de usuario

No es necesario asignar licencias a buzones de recursos, buzones de sala y buzones de correo compartido, excepto cuando se supere la cuota de almacenamiento de 50 gigabytes (GB). Para obtener más información sobre buzones que no son de usuario, vea los siguientes artículos:
  
- [Crear un buzón compartido](../../admin/email/create-a-shared-mailbox.md)
- [Quitar la licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md)
- [Buzones compartidos en Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes) para todos los demás planes de Microsoft 365.
- [Crear y administrar buzones de sala](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Administrar buzones de equipo](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>¿Quién puede asignar licencias?

Los distintos tipos de administradores pueden trabajar con las licencias de diferentes maneras, dependiendo de sus roles. Consulte la tabla siguiente para ver un resumen de las opciones más habituales. Para obtener una lista completa de los roles y los privilegios del administrador, vea [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  
|**Rol de administrador**|**Asignar una licencia**|**Desasignación de una licencia**|**Comprar más licencias**|**Eliminar una cuenta**|
|:-----|:-----|:-----|:-----|:-----|
|Administrador de facturación  <br/> |No  <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|Administrador global  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Administrador de licencias <br/> |Sí <br/>|Sí <br/> |No <br/> |No <br/> |
|Administrador de soporte técnico del servicio  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Administrador de usuarios  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |Sí  <br/> |

## <a name="related-content"></a>Contenido relacionado

[Comprar o quitar licencias de su suscripción empresarial](buy-licenses.md) (artículo)\
[Asignar licencias a usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo)\
[Cancelar asignación a licencias de usuarios](../../admin/manage/remove-licenses-from-users.md) (artículo)\
[Quitar una licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md) (artículo)