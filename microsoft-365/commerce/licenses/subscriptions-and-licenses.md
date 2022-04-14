---
title: Descripción de las suscripciones y licencias en Microsoft 365 para empresas
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: Las aplicaciones y servicios que reciba dependerán de la Microsoft 365 producto que haya comprado, como Aplicaciones Microsoft 365 para negocios.
ms.date: 07/01/2020
ms.openlocfilehash: fca1e5239745e28c32c200c76cc229aedeccf2a4
ms.sourcegitcommit: e13c8fc28c68422308c9d356109797cfcf6f77be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64841687"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Descripción de las suscripciones y licencias en Microsoft 365 para empresas

Al comprar una suscripción a Microsoft 365 para empresas, se registra para obtener un conjunto de aplicaciones y servicios que paga mensualmente o anualmente. Las aplicaciones y servicios que reciba como parte de su suscripción dependen del producto que haya comprado, como Aplicaciones Microsoft 365 para negocios o Microsoft 365 Empresa Estándar. Puede ver lo que viene con cada producto en la [página Microsoft 365 para pequeñas y medianas empresas](https://products.office.com/compare-all-microsoft-office-products?&activetab=tab:primaryr1).

Cuando compra una suscripción, debe especificar el número de licencias que necesita, en función de cuántos usuarios tiene en su organización. Después de comprar una suscripción, crea cuentas para los usuarios de su organización y, a continuación, asigna una licencia a cada persona. A medida que cambian las necesidades de la organización, puede comprar más licencias para dar cabida a nuevas personas o reasignar licencias a otros usuarios cuando alguien deje la organización.

Si tiene más de una suscripción, puede asignar licencias a usuarios diferentes para cada suscripción. Por ejemplo, puede asignar todos los usuarios a todas las aplicaciones y servicios Microsoft 365 como parte de una suscripción de Microsoft 365 Empresa Estándar. También puede asignar un subconjunto de usuarios a Visio Online a través de una suscripción Visio independiente.

## <a name="how-many-devices-can-people-install-office-on"></a>¿En cuántos dispositivos se puede instalar Office?

Si su suscripción incluye cualquiera de los siguientes productos, cada persona puede instalar Office en hasta cinco pc o Mac, cinco tabletas y cinco teléfonos.

:::row:::
   :::column span="":::
        - Aplicaciones Microsoft 365 para negocios - Aplicaciones Microsoft 365 para empresas - Microsoft 365 Empresa Estándar - Microsoft 365 Empresa Premium       - Microsoft 365 A3 - Microsoft 365 A5
   :::column-end:::
   :::column span="":::
        - Microsoft 365 E3 - Microsoft 365 E5 - Office 365 A1 Plus - Office 365 A3 - Office 365 A5 - Office 365 E3 - Office 365 E5
   :::column-end:::
:::row-end:::

## <a name="what-happens-when-you-assign-a-license-to-someone"></a>¿Qué ocurre cuando se asigna una licencia a alguien?

En la tabla siguiente, se muestra una lista con lo que sucede automáticamente al asignar una licencia a un usuario:
  
|Si la suscripción tiene este servicio|Esto sucede automáticamente|
|:-----|:-----|
|Exchange Online|Se crea un buzón para el usuario. <br/> Para obtener información sobre el Acuerdo de Nivel de Servicio para que esta tarea se complete, consulte ["Configuración..." mensajes en el Centro de administración de Microsoft 365](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center). |
|SharePoint Online|Se asignan al usuario permisos de edición para el sitio de grupo predeterminado de SharePoint Online.|
|Skype Empresarial Online|La persona tiene acceso a las características asociadas a la licencia.|
|Aplicaciones Microsoft 365 para empresas y Aplicaciones Microsoft 365 para negocios|La persona puede descargar Office aplicaciones en hasta cinco Mac o PC, cinco tabletas y cinco smartphones.|

## <a name="understand-licenses-for-non-user-mailboxes"></a>Información sobre las licencias para los buzones que no son de usuario

No es necesario asignar licencias a buzones de recursos, buzones de sala y buzones de correo compartido, excepto cuando se supere la cuota de almacenamiento de 50 gigabytes (GB). Para obtener más información sobre buzones que no son de usuario, vea los siguientes artículos:
  
- [Crear un buzón compartido](../../admin/email/create-a-shared-mailbox.md)
- [Quitar la licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md)
- [Buzones compartidos en Exchange Online](/exchange/collaboration-exo/shared-mailboxes) para todos los demás planes de Microsoft 365.

## <a name="who-can-assign-licenses"></a>Quién puede asignar licencias?

Los distintos tipos de administradores pueden trabajar con las licencias de diferentes maneras, dependiendo de sus roles. Consulte la tabla siguiente para ver un resumen de las opciones más habituales. Para obtener una lista completa de los roles y los privilegios del administrador, vea [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  
|Rol de administrador|Asignación de una licencia|Anulación de la asignación de una licencia|Comprar más licencias|Eliminar una cuenta|
|:-----|:-----|:-----|:-----|:-----|
|Administrador de facturación|No|No|Sí|No|
|Administrador global|Sí|Sí|Sí|Sí|
|Administrador de licencias|Sí|Sí|No|No|
|Administrador de soporte técnico del servicio|No|No|No|No|
|Administrador de usuarios|Sí|Sí|No|Sí|

## <a name="related-content"></a>Contenido relacionado

[Comprar o quitar licencias para su suscripción empresarial](buy-licenses.md) (artículo)\
[Asignar licencias a los usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo)\
[Cancelar asignación a licencias de usuarios](../../admin/manage/remove-licenses-from-users.md) (artículo)\
[Quitar la licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md) (artículo)
