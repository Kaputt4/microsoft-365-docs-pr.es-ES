---
title: Administración de solicitudes de licencia
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- MACBillingLicensesRequests
- AdminSurgePortfolio
search.appverid: MET150
description: Obtenga información sobre cómo revisar y aprobar o denegar solicitudes de licencia de los usuarios para su suscripción de Microsoft 365 para empresas.
ms.date: 04/22/2022
ms.openlocfilehash: dfe8410ce894e19489664396866917e4c5bb3dd4
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66044255"
---
# <a name="manage-license-requests"></a>Administración de solicitudes de licencia

> [!NOTE]
> La información de este artículo solo se aplica a los productos comprados de autoservicio. Para obtener más información, consulte [Preguntas más frecuentes sobre compras de autoservicio](../subscriptions/self-service-purchase-faq.yml).

Si deshabilita las compras de autoservicio en su organización, puede usar solicitudes de licencias para administrar el proceso de solicitud de licencia para los usuarios. Cuando un usuario intenta realizar una compra de autoservicio para un producto que ha bloqueado, puede enviarle una solicitud de licencia, el administrador. Cuando realizan una solicitud, pueden agregar los nombres de otros usuarios que también necesitan licencias para el producto.

> [!NOTE]
> Si impide que los usuarios realicen compras de autoservicio, Microsoft no les envía correos electrónicos de marketing. Además, si usan una versión de prueba de un producto, no ven mensajes para comprarlo. Para obtener más información, consulte [Administración de compras de autoservicio (administrador).](../subscriptions/manage-self-service-purchases-admins.md)

Para ver y administrar las solicitudes de licencia, el administrador usa la pestaña **Solicitudes** de la página **Licencias** . En la lista se muestra el nombre del producto solicitado, el nombre de la persona que solicita una licencia, la fecha solicitada y el estado de la solicitud. Los administradores pueden filtrar la lista para mostrar las solicitudes pendientes o completadas. Las solicitudes se mantienen durante 30 días.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador global para realizar las tareas de este artículo. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Uso de su propio proceso de solicitud

Si su organización tiene su propio proceso de solicitud, puede usarlo en su lugar. Se crea un mensaje que se muestra a los usuarios cuando solicitan una licencia.

> [!IMPORTANT]
> Si usa su propio proceso de solicitud, no se mostrará ninguna solicitud en la pestaña **Solicitudes** . Las solicitudes existentes desde antes de agregar el mensaje seguirán apareciendo hasta que las apruebe o rechace.

1. En el Centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias</a> de **facturación** >  y seleccione la pestaña **Solicitudes**.
2. Seleccione **Usar el proceso de solicitud existente en su lugar**.
3. En el panel derecho, en el cuadro **Mensaje** , escriba el mensaje que quiere que vean los usuarios cuando soliciten una licencia. Si también desea incluir un vínculo a la directiva de su organización u otra documentación, escriba la dirección URL en el cuadro de texto **Vínculo a la documentación (opcional** ).
4. Haga clic en **Guardar**.

Cuando vuelva a la lista **de solicitudes** , verá el mensaje **You're using your own license request process (Está usando su propio proceso de solicitud de licencia**). Para realizar cambios en el mensaje que se envía a los usuarios, seleccione **Usar el proceso de solicitud existente en su lugar**.

## <a name="stop-using-your-own-request-process"></a>Dejar de usar su propio proceso de solicitud

1. En el Centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias</a> de **facturación** >  y seleccione la pestaña **Solicitudes**.
2. Seleccione **Usar el proceso de solicitud existente en su lugar**.
3. En el panel derecho, desactive la casilla **Usar el proceso de solicitud de mi organización** .
4. Haga clic en **Guardar**.

## <a name="approve-or-deny-a-license-request"></a>Aprobación o denegación de una solicitud de licencia

1. En el Centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias</a> de **facturación** >  y seleccione la pestaña **Solicitudes**.
2. Seleccione la fila que contiene la solicitud que desea revisar. En el panel derecho se muestran detalles sobre qué usuarios quieren licencias para el producto.
3. Para denegar toda la solicitud, seleccione **No aprobar** y, en el cuadro de diálogo, seleccione **No aprobar**.
4. Para denegar la solicitud a algunos usuarios, pero aprobar otros, seleccione la X por el nombre de los usuarios que desea quitar. Sus nombres se mueven en **No asignar a estos usuarios**.
5. Si tiene más de un producto, en **Seleccionar un producto**, seleccione el que desea usar para asignar licencias.
6. Para denegar a los usuarios el acceso a determinadas aplicaciones y servicios, expanda **Activar o desactivar aplicaciones y servicios** y desactive las casillas de las que quiera excluir.
7. En la parte inferior del panel, escriba un mensaje opcional en el cuadro de texto.
8. Cuando haya terminado, seleccione **Aprobar**. En el panel derecho se muestran los detalles de la solicitud.
9. Cierre el panel derecho.
    Los usuarios reciben un correo electrónico que indica que su solicitud se ha aprobado o denegado.

## <a name="related-content"></a>Contenido relacionado

[Asignar licencias a los usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo)\
[Mover usuarios a otra suscripción](../subscriptions/move-users-different-subscription.md) (artículo)\
[Comprar o quitar licencias de suscripción](buy-licenses.md) (artículo)\
[Preguntas más frecuentes sobre compras de autoservicio](../subscriptions/self-service-purchase-faq.yml)
