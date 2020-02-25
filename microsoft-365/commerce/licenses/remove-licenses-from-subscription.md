---
title: Eliminar licencias de la suscripción a Office 365 para empresas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 9c64d127-e2dd-4ecc-81f5-2f87e5a74803
description: Obtenga información sobre cómo quitar una licencia de su suscripción de Office 365 para empresas cuando la licencia ya está asignada a alguien.
ms.openlocfilehash: d1af1b5696d359daf6578e090180b79587952106
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246357"
---
# <a name="remove-licenses-from-your-office-365-for-business-subscription"></a>Eliminar licencias de la suscripción a Office 365 para empresas

No puede quitar una licencia de una suscripción si está asignada a un usuario. Si desea quitar una licencia que está asignada actualmente a alguien, debe [quitar-licenses-from-Users](../../admin/manage/remove-licenses-from-users.md)para poder quitar la licencia de la suscripción.

::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

## <a name="remove-licenses"></a>Remove licenses

1. En el centro de administración, vaya a **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Productos y servicios</a>.

2. En la página **productos & Services** , busque la suscripción de la que desea quitar licencias y, a continuación, seleccione **Agregar o quitar licencias**.

    [¿No ve el vínculo Agregar o quitar licencias?](#what-if-i-dont-see-the-addremove-licenses-link)

3. En el cuadro **total de licencias** , escriba el número total de licencias que necesita para esta suscripción y, después, seleccione **Enviar cambio**. Por ejemplo, si tiene 110 licencias y quiere quitar 5, escriba 105.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">suscripciones</a> de **facturación** \> .

2. En la página **suscripciones** , seleccione la suscripción de la que desea quitar licencias y, a continuación, seleccione **Agregar o quitar licencias**.

    [¿No ve el vínculo Agregar o quitar licencias?](#what-if-i-dont-see-the-addremove-licenses-link)

3. En el cuadro **Licencias totales**, escriba el número total de licencias que necesita para esta suscripción y, a continuación, seleccione **Enviar**. Por ejemplo, si tiene 110 licencias y quiere quitar 5, escriba 105.


::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">suscripciones</a> de **facturación** \> .

2. En la página **suscripciones** , seleccione la suscripción de la que desea quitar licencias y, a continuación, seleccione **Agregar o quitar licencias**.

    [¿No ve el vínculo Agregar o quitar licencias?](#what-if-i-dont-see-the-addremove-licenses-link)

3. En el cuadro **Licencias totales**, escriba el número total de licencias que necesita para esta suscripción y, a continuación, seleccione **Enviar**. Por ejemplo, si tiene 110 licencias y quiere quitar 5, escriba 105.

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>¿No ve el vínculo Agregar o quitar licencias?

En esta sección, se explican las razones por las que el vínculo **Agregar o quitar licencias** podría no estar disponible y qué puede hacer al respecto.
  
### <a name="a-credit-check-is-pending"></a>Pendiente de comprobación de crédito

Si hay pendiente una comprobación de crédito, verá un mensaje "Pendiente de comprobación de crédito" y no podrá quitar licencias hasta que la comprobación se haya completado. Si está pendiente una comprobación de crédito, consulte más adelante si se ha completado. Las comprobaciones de crédito suelen tardar unos dos días laborables.
  
Una vez completada la comprobación de crédito, debería ver el vínculo **Agregar o quitar licencias** en la sección **Usuarios**. Si es así, vaya a [quitar licencias de la suscripción de Office 365 para empresas](#remove-licenses-from-your-office-365-for-business-subscription).
  
### <a name="you-activated-the-subscription-using-a-product-key"></a>La suscripción se ha activado con una clave de producto

Si la suscripción se compró y se activó con una clave de producto de 25 caracteres, verá el texto "Pagado por adelantado". Si la suscripción se pagó por adelantado con una clave de producto, no puede quitar licencias porque ya se ha pagado por ellas. Sin embargo, podrá quitar las licencias adicionales cuando renueve la suscripción.
  
### <a name="you-bought-your-subscription-through-a-partner"></a>La suscripción se ha adquirido a través de un partner

Si la suscripción se compró a través de un CSP o un partner, no puede quitar licencias. Póngase en contacto con el CSP o use el vínculo del centro de servicios de licencias por volumen (VLSC) para ponerse en contacto con su partner para obtener ayuda.
  
## <a name="what-you-need-to-know-about-removing-licenses-from-users-in-office-365-for-business"></a>Información acerca de quitar licencias de usuarios en Office 365 para empresas

- Debe ser administrador global o administrador de administración de usuarios. Para obtener más información, vea [acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).

- Siga estos pasos para agregar una licencia a una cuenta de usuario existente. [Obtenga información sobre cómo agregar una cuenta de usuario y asignar una licencia al mismo tiempo](../../admin/add-users/add-users.md).

## <a name="articles-about-managing-licenses-for-your-subscription"></a>Artículos sobre la administración de licencias de la suscripción

- [Entender las suscripciones y licencias](subscriptions-and-licenses.md)

- [Quitar licencias de usuarios](../../admin/manage/remove-licenses-from-users.md)

- [Asignar licencias a usuarios](../../admin/manage/assign-licenses-to-users.md)

- [Comprar licencias para la suscripción](buy-licenses.md)

- [Comprar otra suscripción](../buy-another-subscription.md)

- [Comprar o editar un complemento](../buy-or-edit-an-add-on.md)

- [Administrar licencias de usuario de Yammer](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

## <a name="related-links"></a>Vínculos relacionados

[Cancelar la suscripción](../subscriptions/cancel-your-subscription.md)
