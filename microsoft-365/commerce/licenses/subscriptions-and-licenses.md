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
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- okr_smb
- AdminSurgePortfolio
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: Las aplicaciones y servicios que reciba dependerán del producto de Microsoft 365 que haya comprado, como Aplicaciones Microsoft 365 para negocios.
ms.date: 05/12/2022
ms.openlocfilehash: e2494fd52ea7edcab4a68ca69e024b0561aa1d5f
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730873"
---
# <a name="understand-subscriptions-and-licenses-in-microsoft-365-for-business"></a>Descripción de las suscripciones y licencias en Microsoft 365 para empresas

Al comprar una suscripción a Microsoft 365 para empresas, se registra para obtener un conjunto de aplicaciones y servicios que paga periódicamente. Las aplicaciones y servicios que reciba como parte de su suscripción dependen del producto que haya comprado, como Aplicaciones Microsoft 365 para negocios o Microsoft 365 Empresa Estándar. Puede ver lo que viene con cada producto en la página [Microsoft 365 para pequeñas y medianas empresas](https://www.microsoft.com/microsoft-365/business/compare-all-microsoft-365-business-products) .

Cuando compra una suscripción, debe especificar el número de licencias que necesita, en función de cuántos usuarios tiene en su organización. Después de comprar una suscripción, crea cuentas para los usuarios de su organización y, a continuación, asigna una licencia a cada persona. A medida que cambian las necesidades de la organización, puede comprar más licencias para dar cabida a nuevas personas o reasignar licencias a otros usuarios cuando alguien deje la organización.

Si tiene más de una suscripción, puede asignar licencias a usuarios diferentes para cada suscripción. Por ejemplo, puede asignar todos los usuarios a todas las aplicaciones y servicios de Microsoft 365 como parte de una suscripción de Microsoft 365 Empresa Estándar. También puede asignar un subconjunto de usuarios a Visio Online a través de una suscripción independiente de Visio.

## <a name="how-many-devices-can-people-install-office-on"></a>¿En cuántos dispositivos se puede instalar Office?

Si su suscripción incluye cualquiera de los siguientes productos, cada persona puede instalar Office en hasta cinco equipos o Mac, cinco tabletas y cinco teléfonos.

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
|---|---|
|Exchange Online|Se crea un buzón para el usuario. <br/> Para obtener información sobre el Acuerdo de Nivel de Servicio para que esta tarea se complete, consulte ["Configuración..." mensajes en el Centro de administración de Microsoft 365](https://support.microsoft.com/help/2635238/setting-up-messages-in-the-office-365-admin-center).|
|SharePoint Online|Se asignan al usuario permisos de edición para el sitio de grupo predeterminado de SharePoint Online.|
|Microsoft Teams|La persona tiene acceso a las características asociadas a la licencia.|
|Aplicaciones Microsoft 365 para empresas y Aplicaciones Microsoft 365 para negocios|La persona puede descargar aplicaciones de Office en hasta cinco Mac o PC, cinco tabletas y cinco smartphones.|

## <a name="understand-licenses-for-non-user-mailboxes"></a>Información sobre las licencias para los buzones que no son de usuario

You don't need to assign licenses to resource mailboxes, room mailboxes, and shared mailboxes, except when they are over their storage quota of 50 gigabytes (GB). For more about non-user mailboxes, see the following articles:
  
- [Crear un buzón compartido](../../admin/email/create-a-shared-mailbox.md)
- [Quitar la licencia de un buzón compartido](../../admin/email/remove-license-from-shared-mailbox.md)
- [Buzones compartidos en Exchange Online](/exchange/collaboration-exo/shared-mailboxes) para todos los demás planes de Microsoft 365.

## <a name="who-can-assign-licenses"></a>¿Quién puede asignar licencias?

Different types of admins can work with licenses in different ways, depending on their roles. The following table lists the most common options. For a complete list of admin roles and privileges, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  
|Rol de administrador|Asignación de una licencia|Anulación de la asignación de una licencia|Comprar más licencias|Eliminar una cuenta|
|---|:---:|:---:|:---:|:---:|
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
