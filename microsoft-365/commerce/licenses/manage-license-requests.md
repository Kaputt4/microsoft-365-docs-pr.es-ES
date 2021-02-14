---
title: Administrar solicitudes de licencia
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Obtenga información sobre cómo revisar y aprobar o denegar solicitudes de licencia de los usuarios para su suscripción a Microsoft 365 para empresas.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597663"
---
# <a name="manage-license-requests"></a>Administrar solicitudes de licencia

> [!NOTE]
> La información de este artículo solo se aplica a los productos comprados de autoservicio. Para obtener más información, consulte [preguntas más frecuentes sobre la compra de autoservicio.](../subscriptions/self-service-purchase-faq.md)

Si deshabilita las compras de autoservicio en su organización, puede usar las solicitudes de licencias para administrar el proceso de solicitud de licencia para los usuarios. Cuando un usuario intenta realizar una compra de autoservicio para un producto que ha bloqueado, puede enviar una solicitud de licencia a usted, el administrador. Cuando realicen una solicitud, podrán agregar los nombres de otros usuarios que también necesiten licencias para el producto.

> [!NOTE]
> Si bloqueas a los usuarios para que no realicen compras de autoservicio, Microsoft no les envía correos electrónicos de marketing. Además, si usan una versión de prueba de un producto, no verán solicitudes para comprarlo. Para obtener más información, consulta [Administrar compras de autoservicio (administrador).](../subscriptions/manage-self-service-purchases-admins.md)

Para ver y administrar solicitudes de licencia, el administrador usa la **pestaña** Solicitudes en la **página Licencias.** La lista muestra el nombre del producto solicitado, el nombre de la persona que solicita una licencia, la fecha solicitada y el estado de la solicitud. Los administradores pueden filtrar la lista para mostrar las solicitudes que están pendientes o completadas. Las solicitudes se mantienen durante 30 días.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador global para realizar las tareas de este artículo. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Usar su propio proceso de solicitud

Si su organización tiene su propio proceso de solicitud, puede usarlo en su lugar. Crea un mensaje que se muestra a los usuarios cuando solicitan una licencia.

> [!IMPORTANT]
> Si usa su propio proceso de solicitud, no se mostrará ninguna solicitud en la **pestaña** Solicitudes. Las solicitudes existentes de antes de agregar el mensaje seguirán apareciendo hasta que las apruebe o rechace.

1. En el centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación y, a continuación, seleccione la **pestaña** Solicitudes.
2. Seleccione **Usar el proceso de solicitud existente en su lugar.**
3. En el panel derecho, en **el** cuadro Mensaje, escriba el mensaje que desea que los usuarios vean cuando soliciten una licencia. Si también desea incluir un vínculo a la directiva de su organización u otra documentación, escriba la dirección URL en el cuadro de texto Vínculo a documentación **(opcional).**
4. Seleccione **Guardar**.

Cuando vuelva a la **lista de solicitudes,** verá el mensaje **Que está usando su propio proceso de solicitud de licencia.** Para realizar cambios en el mensaje que se envía a los usuarios, **seleccione Usar el proceso de solicitud existente en su lugar.**

## <a name="stop-using-your-own-request-process"></a>Dejar de usar su propio proceso de solicitud

1. En el centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación y, a continuación, seleccione la **pestaña** Solicitudes.
2. Seleccione **Usar el proceso de solicitud existente en su lugar.**
3. En el panel derecho, desactive la casilla **Usar el proceso** de solicitud de mi organización.
4. Seleccione **Guardar**.

## <a name="approve-or-deny-a-license-request"></a>Aprobar o denegar una solicitud de licencia

1. En el centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación y, a continuación, seleccione la **pestaña** Solicitudes.
2. Seleccione la fila que contiene la solicitud que desea revisar. En el panel derecho se muestran los detalles sobre los usuarios que desean licencias para el producto.
3. Para denegar toda la solicitud, seleccione **No aprobar** y, en el cuadro de diálogo, seleccione **No aprobar.**
4. Para denegar a algunos usuarios la solicitud, pero aprobar otros, seleccione la X por el nombre de los usuarios que desea quitar. Sus nombres se mueven en **No asignar a estos usuarios.**
5. Si tiene más de un producto, en **Seleccionar** un producto, seleccione el que desea usar para asignar licencias.
6. Para denegar a los usuarios el acceso a determinadas aplicaciones y servicios, expanda Activar o desactivar aplicaciones y servicios **y** desactive las casillas de los que desea excluir.
7. En la parte inferior del panel, escriba un mensaje opcional en el cuadro de texto.
8. Cuando haya terminado, seleccione **Aprobar**. En el panel derecho se muestran los detalles de la solicitud.
9. Cierre el panel derecho.
    Los usuarios reciben un correo electrónico que indica que su solicitud se ha aprobado o denegado.

## <a name="related-content"></a>Contenido relacionado

[Asignar licencias a usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo)\
[Mover usuarios a una suscripción diferente](../subscriptions/move-users-different-subscription.md) (artículo)\
[Comprar o quitar licencias de suscripción](buy-licenses.md) (artículo)