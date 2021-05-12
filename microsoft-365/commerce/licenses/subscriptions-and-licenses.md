---
title: Comprender las suscripciones y licencias en Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Obtenga información sobre las suscripciones y licencias en Microsoft 365 para empresas.
ms.date: 07/01/2020
ms.openlocfilehash: a8ec5b0716a5ceaa02526520e76dc390a6fba0f7
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331495"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Comprender las suscripciones y licencias en Microsoft 365 para empresas

Cuando compras una suscripción a Microsoft 365 para empresas, te registras para un conjunto de aplicaciones y servicios que pagas mensualmente o anualmente. Las aplicaciones y servicios que recibe como parte de la suscripción dependen del producto que haya comprado, como Aplicaciones Microsoft 365 para negocios o Microsoft 365 Empresa Estándar. Puede ver lo que incluye cada producto en la [Microsoft 365 para pequeñas y medianas empresas.](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1)

Cuando compra una suscripción, debe especificar el número de licencias que necesita, en función de cuántos usuarios tiene en su organización. Después de comprar una suscripción, crea cuentas para los usuarios de la organización y, a continuación, asigna una licencia a cada persona. A medida que cambien las necesidades de la organización, puede comprar más licencias para dar cabida a personas nuevas o reasignar licencias a otros usuarios cuando alguien abandone la organización.

Si tiene más de una suscripción, puede asignar licencias a usuarios diferentes para cada suscripción. Por ejemplo, puede asignar todos los usuarios a todos los Microsoft 365 y servicios como parte de una Microsoft 365 Empresa Estándar suscripción. También puede asignar un subconjunto de usuarios a Visio Online a través de una suscripción Visio independiente.

## <a name="how-many-devices-can-people-install-office-on"></a>¿En cuántos dispositivos se puede instalar Office?

Si la suscripción incluye cualquiera de los siguientes productos, cada persona puede instalar Office hasta cinco equipos pc o Mac, cinco tabletas y cinco teléfonos.

:::row:::
   :::column span="":::
        - Aplicaciones Microsoft 365 para negocios - Aplicaciones Microsoft 365 para empresas - Microsoft 365 Empresa Estándar - Microsoft 365 Empresa Premium - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>¿Qué sucede cuando asigna una licencia a alguien?

En la tabla siguiente, se muestra una lista con lo que sucede automáticamente al asignar una licencia a un usuario:
  
|**Si la suscripción tiene este servicio**|**Esto sucede automáticamente**|
|:-----|:-----|
|Exchange Online  <br/> |Se crea un buzón para el usuario. <br/> Para obtener información sobre el SLA para que esta tarea se complete, vea ["Setting up..." mensajes en el centro Microsoft 365 administración.](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center) |
|SharePoint Online  <br/> |Se asignan al usuario permisos de edición para el sitio de grupo predeterminado de SharePoint Online.  <br/> |
|Skype Empresarial Online  <br/> |La persona tiene acceso a las características asociadas con la licencia.  <br/> |
|Aplicaciones de Microsoft 365 para empresas  <br/> |La persona puede descargar Office aplicaciones en hasta cinco Mac o PC, cinco tabletas y cinco smartphones.  <br/> |

## <a name="understand-licenses-for-non-user-mailboxes"></a>Información sobre las licencias para los buzones que no son de usuario

No es necesario asignar licencias a buzones de recursos, buzones de sala y buzones de correo compartido, excepto cuando se supere la cuota de almacenamiento de 50 gigabytes (GB). Para obtener más información sobre buzones que no son de usuario, vea los siguientes artículos:
  
- [Crear un buzón compartido](../../admin/email/create-a-shared-mailbox.md)
- [Quitar la licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md)
- [Buzones compartidos en Exchange Online](/exchange/collaboration-exo/shared-mailboxes) para todos los demás Microsoft 365 planes.
- [Crear y administrar buzones de sala](/exchange/recipients-in-exchange-online/manage-room-mailboxes)
- [Administrar buzones de equipo](/exchange/recipients-in-exchange-online/manage-equipment-mailboxes)

## <a name="who-can-assign-licenses"></a>Quién Puede asignar licencias?

Los distintos tipos de administradores pueden trabajar con las licencias de diferentes maneras, dependiendo de sus roles. Consulte la tabla siguiente para ver un resumen de las opciones más habituales. Para obtener una lista completa de los roles y los privilegios del administrador, vea [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  
|**Rol de administrador**|**Asignar una licencia**|**Unassign a license**|**Comprar más licencias**|**Eliminar una cuenta**|
|:-----|:-----|:-----|:-----|:-----|
|Administrador de facturación  <br/> |No  <br/> |No  <br/> |Sí  <br/> |No  <br/> |
|Administrador global  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Administrador de licencias <br/> |Sí <br/>|Sí <br/> |No <br/> |No <br/> |
|Administrador de soporte técnico del servicio  <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Administrador de usuarios  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |Sí  <br/> |

## <a name="related-content"></a>Contenido relacionado

[Comprar o quitar licencias para su suscripción empresarial](buy-licenses.md) (artículo)\
[Asignar licencias a los usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo)\
[Cancelar asignación a licencias de usuarios](../../admin/manage/remove-licenses-from-users.md) (artículo)\
[Quitar una licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md) (artículo)
