---
title: Administrar compras de autoservicio (administradores)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Los administradores pueden aprender a administrar las compras de autoservicio realizadas por los usuarios de su organización.
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920185"
---
# <a name="manage-self-service-purchases-admin"></a>Administrar compras de autoservicio (administrador)

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

Como administrador, puede ver las compras de autoservicio realizadas por personas de su organización. Verá el nombre del producto, el nombre del comprador, las suscripciones compradas, la fecha de expiración, el precio de compra y los usuarios asignados para cada compra de autoservicio. Si la organización lo requiere, puede desactivar las compras de autoservicio por producto a través de PowerShell. Tiene las mismas directivas de administración de datos y acceso a los productos comprados a través de la compra de autoservicio o de forma centralizada.

También puede controlar si los usuarios de su organización pueden realizar compras de autoservicio. Para obtener más información, [vea Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Ver suscripciones de autoservicio

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Autoservicio.**
3. Para ver más detalles sobre una suscripción, elija una de la lista.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Ver quién tiene licencias para una suscripción de compra de autoservicio

1. En el Centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación.
2. Seleccione el icono de filtro y, a continuación, **elija Autoservicio.**
3. Seleccione un producto para ver las licencias asignadas a personas.
    > [!NOTE]
    > Si hay varias compras para un producto, ese producto  solo aparece una vez y la columna Cantidad disponible muestra el total de todas las suscripciones compradas para ese producto.
4. La **lista** de usuarios se agrupa por los nombres de las personas que realizaron compras de autoservicio.
5. Para exportar una lista de usuarios con licencias para estas suscripciones, elija las suscripciones que desea exportar y, a continuación, **elija Exportar usuarios**.

## <a name="disable-or-enable-self-service-purchases"></a>Deshabilitar o habilitar compras de autoservicio

Puede deshabilitar o habilitar compras de autoservicio para los usuarios de su organización. El módulo de PowerShell de **MSCommerce** incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras de autoservicio y para qué productos.

Puede usar el módulo **MSCommerce** PowerShell para:

- Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase,** ya sea que esté habilitado o deshabilitado por el producto
- Ver una lista de productos aplicables y si la compra de autoservicio está habilitada o deshabilitada
- Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo

Para obtener más información, [vea Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizar licencias en una sola suscripción

Puede asignar licencias existentes o comprar suscripciones adicionales a través de acuerdos existentes para usuarios asignados a compras de autoservicio. Después de asignar estas licencias compradas de forma centralizada, puede solicitar que los compradores cancelen sus suscripciones existentes.

1. En el Centro de administración, vaya a la página **Servicios de compra** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">facturación.</a>
2. Busque y elija el producto que desea comprar y, a continuación, elija **Comprar**.
3. Complete los pasos restantes para completar la compra.
4. Siga los pasos de [Ver](#view-who-has-licenses-for-a-self-service-purchase-subscription) quién tiene licencias para una suscripción comprada por autoservicio para exportar una lista de usuarios a los que hacer referencia en el paso siguiente.
5. Asignar licencias a todos los usuarios que tienen una licencia en la otra suscripción. Para ver los pasos [completos, vea Asignar licencias a los usuarios.](../../admin/manage/assign-licenses-to-users.md)
6. Póngase en contacto con la persona que compró la suscripción de compra de autoservicio y pídale que [la cancele.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Asumir una suscripción de compra de autoservicio

Puede hacerse cargo de una suscripción de compra de autoservicio realizada por un usuario de su organización. Al asumir una suscripción de compra de autoservicio, tiene dos opciones:

1. Mueva los usuarios a una suscripción diferente y cancele la suscripción original.
2. Cancele la suscripción de compra de autoservicio y quite las licencias de los usuarios asignados.

### <a name="move-users-to-a-different-subscription"></a>Mover usuarios a una suscripción diferente

Al mover usuarios a una suscripción diferente, la suscripción antigua se cancela automáticamente. El usuario que compró originalmente la suscripción de compra de autoservicio recibe un correo electrónico que indica que se canceló la suscripción.

> [!NOTE]
> Debe tener una licencia disponible para cada usuario al que se está moviendo en la suscripción a la que va a mover usuarios.

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Autoservicio.**
3. Selecciona la suscripción que quieras asumir.
4. En la página detalles de la suscripción, en la sección **Suscripciones y** configuración, seleccione Tomar el control de **esta suscripción.**
5. En el panel derecho, seleccione **Mover usuarios**.
6. Seleccione el producto al que desea mover los usuarios y, a continuación, **seleccione Mover usuarios**.
7. En el **cuadro Mover usuarios a,** seleccione **Mover usuarios**. El proceso de movimiento puede tardar varios minutos. No cierre el explorador mientras se ejecuta el proceso.
8. Cuando finalice el proceso de movimiento, cierre el **panel Mover completado**.
9. En la página de detalles de la suscripción, el estado **de** suscripción de la suscripción comprada por autoservicio se muestra como **Eliminado**.

### <a name="cancel-a-self-service-purchase-subscription"></a>Cancelar una suscripción de compra de autoservicio

Cuando decide cancelar una suscripción de compra de autoservicio, los usuarios con licencias pierden el acceso al producto. El usuario que compró originalmente la suscripción de compra de autoservicio recibe un correo electrónico que indica que se canceló la suscripción.

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Autoservicio.**
3. Seleccione la suscripción que desea cancelar.
4. En la página detalles de la suscripción, en la sección **Suscripciones y** configuración, seleccione Tomar el control de **esta suscripción.**
5. En el panel derecho, seleccione **Cancelar suscripción**.
6. Seleccione un motivo para la cancelación en la lista desplegable y, a continuación, **seleccione Cancelar suscripción**.
7. En el **cuadro ¿Está seguro de que desea cancelar?** seleccione **Cancelar suscripción**.
8. Cierre el panel derecho.
9. En la página de detalles de la suscripción, el **estado de suscripción** se muestra como **Eliminado**.

## <a name="need-help-contact-us"></a>¿Necesita ayuda? Póngase en contacto con nosotros.

Para obtener preguntas comunes acerca de las compras de autoservicio, consulta Preguntas más frecuentes sobre compras [de autoservicio.](self-service-purchase-faq.md)

Si tiene preguntas o necesita ayuda con las compras de autoservicio, póngase [en contacto con el soporte técnico](../../admin/contact-support-for-business-products.md).