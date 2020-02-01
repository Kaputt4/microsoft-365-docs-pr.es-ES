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
search.appverid:
- MET150
description: Los administradores pueden aprender a administrar las compras de autoservicio realizadas por los usuarios de su organización.
ms.openlocfilehash: 5db942b42f398e8951da43add7013569af52c53f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594114"
---
# <a name="manage-self-service-purchases-admin"></a>Administración de compras sin servicio (administración)

Como administrador, puede ver las compras de autoservicio realizadas por las personas de su organización. Puede ver el producto, el nombre del comprador, las suscripciones adquiridas, la fecha de expiración, el precio de compra y los usuarios asignados para cada compra de servicio autónomo. Si es necesario para su organización, puede desactivar las compras de autoservicio por producto a través de PowerShell. Tiene las mismas directivas de administración y acceso de datos que los productos adquiridos a través de la compra de autoservicio o de forma centralizada.

También puede controlar si los usuarios de la organización pueden realizar compras sin servicio de asistencia. Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Ver suscripciones de autoservicio

1. En el centro de administración, vaya a la página productos de **facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& Services</a> .

2. Junto a **refinar resultados**, en la lista desplegable **tipo de cuenta** , elija **Self-Service**.

3. Para ver más detalles sobre una suscripción, seleccione una de la lista.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Ver quién tiene licencias para una suscripción de compra de autoservicio

1. En el centro de administración, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .

2. Elija el icono filtrar y, a continuación, elija **autoservicio**.

3. Seleccione un producto para ver las licencias asignadas a los usuarios.

    > [!NOTE]
    > Si hay varias compras para un producto, dicho producto solo aparece una vez y la columna **cantidad disponible** muestra el total de todas las suscripciones que ha comprado para ese producto.

4. La lista de **usuarios** se agrupa por los nombres de las personas que realizaron compras sin servicio.

5. Para exportar una lista de usuarios con licencias para estas suscripciones, elija las suscripciones que quiere exportar y, después, elija **exportar usuarios**.

## <a name="disable-or-enable-self-service-purchases"></a>Deshabilitación o habilitación de compras sin servicio

Puede deshabilitar o habilitar las compras de autoservicio para los usuarios de su organización. El módulo de PowerShell **MSCommerce** incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras sin servicio y para qué productos.

Puede usar el módulo de PowerShell **MSCommerce** para:

- Ver el estado predeterminado del valor **** &mdash; del parámetro AllowSelfServicePurchase si está habilitado o deshabilitado por el producto.
- Ver una lista de los productos aplicables y si la compra de servicios automáticos está habilitada o deshabilitada
- Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo

Para obtener más información, vea [usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizar licencias en una sola suscripción

Puede asignar licencias existentes o comprar suscripciones adicionales a través de acuerdos existentes para usuarios asignados a las compras de autoservicio. Después de asignar estas licencias adquiridas de forma centralizada, puede solicitar que los compradores cancelen sus suscripciones existentes.

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a> con su cuenta de administrador global o de administrador de facturación.

2. Vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servicios de compra</a> de **facturación** > .

3. Busque y seleccione el producto que desea comprar y, después, elija **comprar**.

4. Complete los pasos restantes para completar la compra.

5. Siga los pasos [que se indican en View of licenses for a Self-Service adquirid subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar una lista de usuarios a la que hacer referencia en el paso 6.

6. Asigne licencias a todos los usuarios que tengan una licencia en la otra suscripción. Para obtener los pasos completos, consulte [asignar licencias a usuarios](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

7. Póngase en contacto con la persona que compró la suscripción de compra de autoservicio y pídale que la cancele.

## <a name="need-help-contact-us"></a>¿Necesita ayuda? Póngase en contacto con nosotros.

Para obtener preguntas comunes sobre las compras de autoservicio, consulte [preguntas más frecuentes](self-service-purchase-faq.md)sobre las compras sin ayuda.

Si tiene alguna pregunta o necesita ayuda con las compras de servicios de autoservicio, [póngase en contacto con el soporte técnico](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).