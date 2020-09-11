---
title: Administración de las compras sin servicio (administradores)
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Los administradores pueden aprender a administrar las compras de autoservicio realizadas por los usuarios de su organización.
ms.openlocfilehash: f10f525f8efc6bc63e2fa042c299a6d03c77d0cb
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430003"
---
# <a name="manage-self-service-purchases-admin"></a>Administrar compras de autoservicio (administrador)

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Como administrador, puede ver las compras de autoservicio realizadas por las personas de su organización. Verá el nombre del producto, el nombre del comprador, las suscripciones adquiridas, la fecha de expiración, el precio de compra y los usuarios asignados para cada compra de servicio autónomo. Si la organización lo requiere, puede desactivar la opción de compra por parte del autoservicio por producto a través de PowerShell. Tiene las mismas directivas de administración y acceso de datos que los productos adquiridos a través de la compra de autoservicio o de forma centralizada.

También puede controlar si los usuarios de la organización pueden realizar compras sin servicio de asistencia. Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Ver suscripciones de autoservicio

1. En el centro de administración, vaya a la página **facturación**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de productos</a> .
2. Junto a **refinar resultados**, en la lista desplegable **tipo de cuenta** , elija **Self-Service**.
3. Para ver más detalles sobre una suscripción, seleccione una de la lista.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Ver quién tiene licencias para una suscripción de compra de autoservicio

1. En el centro de administración, vaya a **Billing**la  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de facturación.
2. Elija el icono filtrar y, a continuación, elija **autoservicio**.
3. Seleccione un producto para ver las licencias asignadas a los usuarios.
    > [!NOTE]
    > Si hay varias compras para un producto, dicho producto solo aparece una vez y la columna **cantidad disponible** muestra el total de todas las suscripciones que ha comprado para ese producto.
4. La lista de **usuarios** se agrupa por los nombres de las personas que realizaron compras sin servicio.
5. Para exportar una lista de usuarios con licencias para estas suscripciones, elija las suscripciones que quiere exportar y, después, elija **exportar usuarios**.

## <a name="disable-or-enable-self-service-purchases"></a>Deshabilitación o habilitación de compras sin servicio

Puede deshabilitar o habilitar las compras de autoservicio para los usuarios de su organización. El módulo de PowerShell **MSCommerce** incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras sin servicio y para qué productos.

Puede usar el módulo de PowerShell **MSCommerce** para:

- Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase** , ya sea que esté habilitado o deshabilitado por producto
- Ver una lista de los productos aplicables y si la compra de servicios automáticos está habilitada o deshabilitada
- Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo

Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizar licencias en una sola suscripción

Puede asignar licencias existentes o comprar suscripciones adicionales a través de acuerdos existentes para usuarios asignados a las compras de autoservicio. Después de asignar estas licencias adquiridas de forma centralizada, puede solicitar que los compradores cancelen sus suscripciones existentes.

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a> con su cuenta de administrador global o de administrador de facturación.
2. Vaya a la **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servicios de compra</a> de facturación.
3. Busque y seleccione el producto que desea comprar y, después, elija **comprar**.
4. Complete los pasos restantes para completar la compra.
5. Siga los pasos [que se indican en View of licenses for a Self-Service adquirid subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar una lista de usuarios a la que hacer referencia en el paso 6.
6. Asigne licencias a todos los usuarios que tengan una licencia en la otra suscripción. Para obtener los pasos completos, consulte [asignar licencias a usuarios](../../admin/manage/assign-licenses-to-users.md).
7. Póngase en contacto con la persona que compró la suscripción de compra de autoservicio y pídale que la cancele.

## <a name="take-over-a-self-service-purchase-subscription"></a>Asumir una suscripción de compra de autoservicio

Puede asumir una suscripción de compra de autoservicio realizada por un usuario de la organización. Cuando asume una suscripción de compra de autoservicio, tiene dos opciones:

1. Mover a los usuarios a una suscripción diferente y cancelar la suscripción original.
2. Cancelar la suscripción de compra de autoservicio y quitar las licencias de los usuarios asignados.

### <a name="move-users-to-a-different-subscription"></a>Mover usuarios a una suscripción diferente

Cuando se mueven usuarios a una suscripción diferente, la suscripción antigua se cancela automáticamente. El usuario que compró originalmente la suscripción de compra de autoservicio recibe un correo electrónico que indica que se canceló la suscripción.

> [!NOTE]
> Debe tener una licencia disponible para cada usuario que vaya a mover a la suscripción a la que va a mover usuarios.

1. En el centro de administración, vaya a la página **facturación**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de productos</a> .
2. En la pestaña **productos** , seleccione el icono filtrar y, a continuación, seleccione **autoservicio**.
3. Seleccione la suscripción que desea asumir.
4. En la sección **suscripciones y configuración** de la página Detalles de la suscripción, seleccione **asumir el control de esta suscripción**.
5. En el panel derecho, seleccione **mover usuarios**.
6. Seleccione el producto al que desea mover a los usuarios y, a continuación, seleccione **mover usuarios**.
7. En el cuadro **mover usuarios a** , seleccione **mover usuarios**. El proceso de traslado puede durar varios minutos. No cierre el explorador mientras se ejecuta el proceso.
8. Una vez finalizado el proceso de traslado, cierre el **Panel mover completado**.
9. En la página Detalles de la suscripción, el **Estado de suscripción** de la suscripción comprada de autoservicio se muestra como **eliminado**.

### <a name="cancel-a-self-service-purchase-subscription"></a>Cancelación de una suscripción de compra de autoservicio

Cuando decide cancelar una suscripción de compra de autoservicio, los usuarios con licencias pierden el acceso al producto. El usuario que compró originalmente la suscripción de compra de autoservicio recibe un correo electrónico que indica que se canceló la suscripción.

1. En el centro de administración, vaya a la página **facturación**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de productos</a> .
2. En la pestaña **productos** , seleccione el icono filtrar y, a continuación, seleccione **autoservicio**.
3. Seleccione la suscripción que desea cancelar.
4. En la sección **suscripciones y configuración** de la página Detalles de la suscripción, seleccione **asumir el control de esta suscripción**.
5. En el panel derecho, seleccione **Cancelar suscripción**.
6. Seleccione un motivo para su cancelación en la lista desplegable y, después, seleccione **Cancelar suscripción**.
7. En el cuadro **¿está seguro de que desea cancelar?** , seleccione **Cancelar suscripción**.
8. Cierre el panel derecho.
9. En la página Detalles de la suscripción, el estado de la **suscripción** aparece como **eliminado**.

## <a name="need-help-contact-us"></a>¿Necesita ayuda? Póngase en contacto con nosotros.

Para obtener preguntas comunes sobre las compras de autoservicio, consulte [preguntas más frecuentes](self-service-purchase-faq.md)sobre las compras sin ayuda.

Si tiene alguna pregunta o necesita ayuda con las compras de servicios de autoservicio, [póngase en contacto con el soporte técnico](../../admin/contact-support-for-business-products.md).