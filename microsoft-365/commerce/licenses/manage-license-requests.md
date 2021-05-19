---
title: Administrar solicitudes de licencia
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Obtenga información sobre cómo revisar y aprobar o denegar solicitudes de licencia de los usuarios para su suscripción Microsoft 365 para empresas.
ms.date: 08/07/2020
ms.openlocfilehash: 6cbfd81f4f6deba642729f1fef0b826b07a99f56
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535679"
---
# <a name="manage-license-requests"></a>Administrar solicitudes de licencia

> [!NOTE]
> La información de este artículo solo se aplica a los productos comprados por autoservicio. Para obtener más información, consulta [Preguntas más frecuentes sobre la compra de autoservicio.](../subscriptions/self-service-purchase-faq.yml)

Si deshabilita las compras de autoservicio en su organización, puede usar solicitudes de licencias para administrar el proceso de solicitud de licencia para los usuarios. Cuando un usuario intenta realizar una compra de autoservicio para un producto que ha bloqueado, puede enviar una solicitud de licencia a usted, el administrador. Cuando realicen una solicitud, pueden agregar los nombres de otros usuarios que también necesitan licencias para el producto.

> [!NOTE]
> Si bloqueas que los usuarios realicen compras de autoservicio, Microsoft no les envía correos electrónicos de marketing. Además, si están usando una versión de prueba de un producto, no ven avisos para comprarlo. Para obtener más información, vea [Manage self-service purchases (Admin).](../subscriptions/manage-self-service-purchases-admins.md)

Para ver y administrar solicitudes de licencia, el administrador usa la **pestaña Solicitudes** de la **página Licencias.** La lista muestra el nombre del producto solicitado, el nombre de la persona que solicita una licencia, la fecha solicitada y el estado de la solicitud. Los administradores pueden filtrar la lista para mostrar las solicitudes que están pendientes o completadas. Las solicitudes se mantienen durante 30 días.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser un administrador global para realizar las tareas de este artículo. Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Usar su propio proceso de solicitud

Si su organización tiene su propio proceso de solicitud, puede usarlo en su lugar. Se crea un mensaje que se muestra a los usuarios cuando solicitan una licencia.

> [!IMPORTANT]
> Si usa su propio proceso de solicitud, no se mostrará ninguna solicitud en la **pestaña** Solicitudes. Las solicitudes existentes desde antes de agregar el mensaje siguen apareciendo hasta que las aprueba o rechaza.

1. En el Centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de facturación</a> y, a continuación, seleccione la **pestaña** Solicitudes.
2. Seleccione **Usar el proceso de solicitud existente en su lugar**.
3. En el panel derecho, en el **cuadro Mensaje,** escriba el mensaje que desea que los usuarios vean cuando soliciten una licencia. Si también desea incluir un vínculo a la directiva de la organización u otra documentación, escriba la dirección URL en el cuadro de texto Vincular a la documentación **(opcional).**
4. Seleccione **Guardar**.

Cuando vuelva a la **lista Solicitudes,** verá el mensaje **You're using your own license request process**. Para realizar cambios en el mensaje que se envía a los usuarios, seleccione **Usar el proceso de solicitud existente en su lugar**.

## <a name="stop-using-your-own-request-process"></a>Dejar de usar su propio proceso de solicitud

1. En el Centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de facturación</a> y, a continuación, seleccione la **pestaña** Solicitudes.
2. Seleccione **Usar el proceso de solicitud existente en su lugar**.
3. En el panel derecho, desactive la casilla Usar el proceso de solicitud **de** mi organización.
4. Seleccione **Guardar**.

## <a name="approve-or-deny-a-license-request"></a>Aprobar o denegar una solicitud de licencia

1. En el Centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de facturación</a> y, a continuación, seleccione la **pestaña** Solicitudes.
2. Seleccione la fila que contiene la solicitud que desea revisar. El panel derecho muestra detalles sobre qué usuarios desean licencias para el producto.
3. Para denegar toda la solicitud, seleccione **No aprobar** y, en el cuadro de diálogo, seleccione **No aprobar**.
4. Para denegar algunos usuarios para la solicitud, pero aprobar otros, seleccione la X por el nombre de los usuarios que desea quitar. Sus nombres se mueven en **No asignar a estos usuarios**.
5. Si tiene más de un producto, en **Seleccionar un** producto, seleccione el que desea usar para asignar licencias.
6. Para denegar el acceso de los usuarios a determinadas aplicaciones y servicios, **expanda** Activar o desactivar aplicaciones y servicios y desactive las casillas de las que desea excluir.
7. En la parte inferior del panel, escriba un mensaje opcional en el cuadro de texto.
8. Cuando haya terminado, seleccione **Aprobar**. El panel derecho muestra los detalles de la solicitud.
9. Cierre el panel derecho.
    Los usuarios reciben un correo electrónico que indica que su solicitud fue aprobada o denegada.

## <a name="related-content"></a>Contenido relacionado

[Asignar licencias a los usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo)\
[Mover usuarios a una suscripción](../subscriptions/move-users-different-subscription.md) diferente (artículo)\
[Comprar o quitar licencias de suscripción](buy-licenses.md) (artículo)
