---
title: Descripción de las suscripciones y licencias de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Obtenga información sobre las suscripciones y licencias de Microsoft 365 para la empresa.
ms.date: 07/01/2020
ms.openlocfilehash: 9f8576b00b942c4b38d6192770bd2128afb4b104
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015964"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Descripción de las suscripciones y licencias de Microsoft 365 para empresas

Al comprar una suscripción a Microsoft 365 para empresas, se registra para un conjunto de aplicaciones y servicios a los que paga con una base mensual o anual. Las aplicaciones y los servicios que reciba como parte de la suscripción dependen de qué producto haya adquirido, como Microsoft 365 apps for Business o Microsoft 365 Business Standard. Puede ver lo que incluye cada producto en la página [de Microsoft 365 para PYMES y pequeñas y](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1) medianas empresas.

Cuando compra una suscripción, debe especificar el número de licencias que necesita, en función de cuántos usuarios tiene en su organización. Una vez que compre una suscripción, cree cuentas para las personas de su organización y, a continuación, asigne una licencia a cada persona. A medida que cambien las necesidades de su organización, puede comprar más licencias para acomodar a nuevas personas o reasignar licencias a otros usuarios cuando alguien abandone la organización.

Si tiene más de una suscripción, puede asignar licencias a usuarios diferentes para cada suscripción. Por ejemplo, puede asignar a todos los usuarios a todas las aplicaciones y servicios de Microsoft 365 como parte de una suscripción de Microsoft 365 Business Standard. También puede asignar un subconjunto de usuarios a Visio online a través de una suscripción de Visio independiente.

## <a name="how-many-devices-can-people-install-office-on"></a>¿En cuántos dispositivos se puede instalar Office?

Si su suscripción incluye cualquiera de los siguientes productos, cada uno de los usuarios puede instalar Office en un máximo de cinco PC o Mac, cinco tabletas y cinco teléfonos.

:::row:::
   :::column span="":::
        -Microsoft 365 apps for Business-Microsoft 365 apps for Enterprise-Microsoft 365 Business Standard-Microsoft 365 Business Premium-Microsoft 365 a3-Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        -Microsoft 365 E3-Microsoft 365 E5-Office 365 a1 más-Office 365 a3-Office 365 A5-Office 365 E3-Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>¿Qué sucede cuando se asigna una licencia a un usuario?

En la tabla siguiente, se muestra una lista con lo que sucede automáticamente al asignar una licencia a un usuario:
  
|**Si la suscripción tiene este servicio**|**Esto sucede automáticamente**|
|:-----|:-----|
|Exchange Online  <br/> |Se crea un buzón para el usuario. <br/> Para obtener información sobre el SLA para completar esta tarea, consulte ["configurar..." mensajes en el centro de administración de Microsoft 365](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online  <br/> |Se asignan al usuario permisos de edición para el sitio de grupo predeterminado de SharePoint Online.  <br/> |
|Skype Empresarial Online  <br/> |La persona tiene acceso a las características asociadas con la licencia.  <br/> |
|Aplicaciones de Microsoft 365 para empresas  <br/> |La persona puede descargar las aplicaciones de Office en un máximo de cinco Mac o PC, cinco tabletas y cinco smartphones.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Información sobre las licencias para los buzones que no son de usuario

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Crear un buzón compartido](../../admin/email/create-a-shared-mailbox.md)
- [Quitar la licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md)
- [Buzones compartidos en Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes) para todos los demás planes de Microsoft 365.
- [Crear y administrar buzones de sala](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Administrar buzones de equipo](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>¿Quién puede asignar licencias?

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|**Rol de administrador**|**Asignar una licencia**|**Cancelar la asignación de una licencia**|**Comprar más licencias**|**Eliminar una cuenta**|
|:-----|:-----|:-----|:-----|:-----|
|Administrador de facturación  <br/> |No  <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|Administrador global  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Administrador de licencias <br/> |Sí <br/>|Sí <br/> |No <br/> |No <br/> |
|Administrador de soporte de servicio  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Administrador de usuarios  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |Sí  <br/> |

## <a name="related-content"></a>Contenido relacionado

[Comprar o quitar licencias de su suscripción de empresa](buy-licenses.md) (artículo) \
[Asignar licencias a usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo) \
[Cancelar la asignación de licencias de los usuarios](../../admin/manage/remove-licenses-from-users.md) (artículo) \
[Quitar una licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md) (artículo)