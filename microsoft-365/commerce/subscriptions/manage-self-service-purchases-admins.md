---
title: Administración de compras de autoservicio (administradores)
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: prlachhw, pablom
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_ssp
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
description: Los administradores pueden aprender a administrar las compras de autoservicio realizadas por los usuarios de su organización.
ms.date: 05/24/2022
ms.openlocfilehash: 4ca3add92877e9219d88366e8104f5fb038ecccc
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68735889"
---
# <a name="manage-self-service-purchases-admin"></a>Administrar compras de autoservicio (administrador)

Como administrador, puede ver las compras de autoservicio realizadas por personas de su organización. Verá el nombre del producto, el nombre del comprador, las suscripciones compradas, la fecha de expiración, el precio de compra y los usuarios asignados para cada compra de autoservicio. Si la organización lo requiere, puede desactivar la compra de autoservicio por producto a través de PowerShell. Tiene las mismas directivas de acceso y administración de datos sobre los productos comprados a través de la compra de autoservicio o de forma centralizada.

También puede controlar si los usuarios de su organización pueden realizar compras de autoservicio. Para obtener más información, vea [Usar AllowSelfServicePurchase para el módulo de PowerShell MSCommerce](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Visualización de suscripciones de autoservicio

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Sus productos</a>.
::: moniker-end

2. En la pestaña **Productos** , seleccione el icono de filtro y, a continuación, seleccione **Autoservicio**.
3. Para ver más detalles sobre una suscripción, elija una de la lista.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Ver quién tiene licencias para una suscripción de compra de autoservicio

> [!NOTE]
> Como administrador, no puede asignar o cancelar la asignación de licencias para una suscripción de compra de autoservicio adquirida por un usuario de su organización. Puede [apoderarse de una suscripción de compra de autoservicio](#take-over-a-self-service-purchase-subscription) y, a continuación, asignar o cancelar la asignación de licencias.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.

::: moniker-end

2. Seleccione el icono de filtro y, a continuación, elija **Autoservicio**.
3. Seleccione un producto para ver las licencias asignadas a personas.
    > [!NOTE]
    > Si hay varias compras para un producto, ese producto solo aparece una vez y la columna **Cantidad disponible** muestra el total de todas las suscripciones compradas para ese producto.
4. La lista **Usuarios** se agrupa por los nombres de las personas que realizaron compras de autoservicio.
5. Para exportar una lista de usuarios con licencias para estas suscripciones, elija las suscripciones que desea exportar y, a continuación, elija **Exportar usuarios**.

## <a name="disable-or-enable-self-service-purchases"></a>Deshabilitación o habilitación de compras de autoservicio

Puede deshabilitar o habilitar compras de autoservicio para los usuarios de su organización. El módulo **de PowerShell MSCommerce** incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras de autoservicio y para qué productos.

Puede usar el módulo de PowerShell **MSCommerce** para:

- Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase** , tanto si está habilitado como deshabilitado por el producto
- Ver una lista de productos aplicables y si la compra de autoservicio está habilitada o deshabilitada
- Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo

> [!IMPORTANT]
> Cuando se usa la directiva **AllowSelfServicePurchase** , se habilitan o deshabilitan las compras de autoservicio y las pruebas de autoservicio. Para obtener una lista de los productos disponibles para la compra de autoservicio, consulte [Ver una lista de productos de compra de autoservicio y su estado](allowselfservicepurchase-powershell.md#view-a-list-of-self-service-purchase-products-and-their-status). Solo Project y Visio están disponibles para las suscripciones de prueba.

Para obtener más información, vea [Usar AllowSelfServicePurchase para el módulo de PowerShell MSCommerce](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralización de licencias en una sola suscripción

Puede asignar licencias existentes o comprar suscripciones adicionales a través de contratos existentes para los usuarios asignados a compras de autoservicio. Después de asignar estas licencias compradas centralmente, puede solicitar a los compradores que cancelen sus suscripciones existentes.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Servicios</a> de **compra de facturación**>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Servicios** de **compra de facturación**>.

::: moniker-end

2. Busque y elija el producto que desea comprar y, a continuación, elija **Comprar**.
3. Complete los pasos restantes para completar la compra.
4. Siga los pasos [descritos en Ver quién tiene licencias para una suscripción comprada de autoservicio](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar una lista de usuarios a los que hacer referencia en el paso siguiente.
5. Asigne licencias a todos los usuarios que tengan una licencia en la otra suscripción. Para ver los pasos [completos, consulte Asignación de licencias a usuarios](../../admin/manage/assign-licenses-to-users.md).
6. Póngase en contacto con la persona que compró la suscripción de compra de autoservicio y pídale [que la cancele](manage-self-service-purchases-users.md#cancel-a-subscription).

## <a name="take-over-a-self-service-purchase-subscription"></a>Hacerse cargo de una suscripción de compra de autoservicio

Puede hacerse cargo de una suscripción de compra de autoservicio realizada por un usuario de su organización. Al asumir una suscripción de compra de autoservicio, tiene dos opciones:

1. Mueva los usuarios a otra suscripción y cancele la suscripción original.
2. Cancele la suscripción de compra de autoservicio y quite las licencias de los usuarios asignados.

### <a name="move-users-to-a-different-subscription"></a>Mover usuarios a una suscripción diferente

Al mover usuarios a otra suscripción, la suscripción anterior se cancela automáticamente. El usuario que compró originalmente la suscripción de compra de autoservicio recibe un correo electrónico que indica que la suscripción se canceló.

> [!NOTE]
> Debe tener una licencia disponible para cada usuario al que se va a mover en la suscripción a la que va a mover usuarios.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Facturación** > **de sus productos** .

::: moniker-end

2. En la pestaña **Productos** , seleccione el icono de filtro y, a continuación, seleccione **Autoservicio**.
3. Seleccione la suscripción que desea asumir.
4. En la página de detalles de la suscripción, en la sección **Suscripciones y configuración** , seleccione **Tomar el control de esta suscripción**.
5. En el panel derecho, seleccione **Mover usuarios**.
6. Seleccione el producto al que desea mover los usuarios y, a continuación, seleccione **Mover usuarios**.
7. En el cuadro **Mover usuarios a** , seleccione **Mover usuarios**. El proceso de traslado puede tardar varios minutos. No cierre el explorador mientras se ejecuta el proceso.
8. Cuando finalice el proceso de movimiento, cierre el **panel Mover completado**.
9. En la página de detalles de la suscripción, el **estado de** suscripción de la suscripción comprada de autoservicio se muestra como **Eliminado**.

### <a name="cancel-a-self-service-purchase-subscription"></a>Cancelación de una suscripción de compra de autoservicio

Cuando decide cancelar una suscripción de compra de autoservicio, los usuarios con licencias pierden el acceso al producto. El usuario que compró originalmente la suscripción de compra de autoservicio recibe un correo electrónico que indica que la suscripción se canceló.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **Facturación** > **de sus productos** .

::: moniker-end

2. En la pestaña **Productos** , seleccione el icono de filtro y, a continuación, seleccione **Autoservicio**.
3. Seleccione la suscripción que quiere cancelar.
4. En la página de detalles de la suscripción, en la sección **Suscripciones y configuración** , seleccione **Tomar el control de esta suscripción**.
5. En el panel derecho, seleccione **Cancelar suscripción**.
6. Seleccione un motivo para la cancelación en la lista desplegable y, a continuación, seleccione **Cancelar suscripción**.
7. En el cuadro **¿Está seguro de que desea cancelar?** , seleccione **Cancelar suscripción**.
8. Cierre el panel derecho.
9. En la página de detalles de la suscripción, el **estado de la suscripción** se muestra como **Eliminado**.

## <a name="need-help-contact-us"></a>¿Necesita ayuda? Contáctenos.

Para obtener preguntas comunes sobre las compras de autoservicio, consulte [Preguntas más frecuentes sobre compras de autoservicio](self-service-purchase-faq.yml).

Si tiene preguntas o necesita ayuda con las compras de autoservicio, [póngase en contacto con el soporte técnico](../../admin/get-help-support.md).
