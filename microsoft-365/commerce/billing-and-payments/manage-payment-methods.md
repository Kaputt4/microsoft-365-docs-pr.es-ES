---
title: Administrar métodos de pago
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Obtenga información sobre cómo administrar los métodos de pago en el Centro de administración de Microsoft 365.
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114854"
---
# <a name="manage-payment-methods"></a>Administrar métodos de pago

::: moniker range="o365-21vianet"
> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).
::: moniker-end

Al comprar productos o servicios empresariales de Microsoft, puede usar un método de pago existente o agregar uno nuevo. Puede usar una tarjeta de crédito o débito, o una cuenta bancaria para pagar las cosas que compre.

Si tu cuenta empresarial tiene un perfil de facturación y eres el propietario de un perfil de facturación o colaborador de perfil de facturación, puedes usar el perfil de facturación que está a favor de una tarjeta de crédito o pago de factura para realizar compras o pagar facturas. Si es un administrador de facturación, solo puede usar un perfil de facturación para pagar facturas. Para obtener más información sobre los perfiles y roles de facturación, vea [Administrar perfiles de facturación.](manage-billing-profiles.md)

Si su cuenta empresarial no tiene un perfil de facturación, cualquier administrador global o de facturación puede administrar y usar cualquier cuenta bancaria que se agrega a la cuenta empresarial. Sin embargo, solo puede administrar o usar tarjetas de crédito que agregue.

> [!NOTE]
> La opción de pagar con una cuenta bancaria no está disponible en algunos países o regiones.
>
> Debe usar un método de pago emitido desde el mismo país que su espacio empresarial.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador global o de facturación para realizar las tareas de este artículo. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Agregar un método de pago.

Agregar un método de pago no asocia ninguna suscripción a él. Para asignar una única suscripción al método de pago, vea Cambiar un método [de pago para una única suscripción.](#change-a-payment-method-for-a-single-subscription) Para reemplazar todas las suscripciones que usan otro método de pago por el nuevo, vea [Reemplazar un método de pago.](#replace-a-payment-method)

1. En el Centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Seleccione **Agregar o seleccionar un método de pago**.
3. En la página **Métodos de pago**, seleccione un método de pago con el menú desplegable.
4. Escriba la información de la nueva tarjeta o cuenta bancaria y, a continuación, **seleccione Agregar**.

## <a name="update-payment-method-details"></a>Actualizar detalles del método de pago

Puede cambiar el nombre en la tarjeta de crédito o débito, la dirección de facturación o la fecha de expiración de un método de pago existente. Sin embargo, no puede cambiar el número de tarjeta o cuenta. Si el número de cuenta ha cambiado, [reemplácelo por](#replace-a-payment-method)un método de pago diferente y, a continuación, [elimine el antiguo.](#delete-a-payment-method)

1. En el Centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Seleccione la fila del método de pago que se va a actualizar. En el panel derecho, seleccione **Editar**.
3. Actualice la información de su método de pago, incluido el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de expiración y, después, seleccione **Guardar**.

## <a name="replace-a-payment-method"></a>Reemplazar un método de pago

Cuando reemplaza un método de pago, lo reemplaza para todas las suscripciones y perfiles de facturación que usan el mismo método de pago. Reemplazar un método de pago no elimina el método de pago existente. Sigue estando disponible para que la selecciones y la uses para otras suscripciones y perfiles de facturación.

Para cambiar el método de pago de una única suscripción, vea Cambiar un [método de pago para una sola suscripción.](#change-a-payment-method-for-a-single-subscription)

1. En el centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Seleccione la fila del método de pago que desea reemplazar. En el panel derecho se muestran todos los perfiles de facturación y las suscripciones individuales que usan el método de pago seleccionado.
3. En el panel derecho, seleccione **Reemplazar método de pago para todos los artículos**.
4. Para usar un método de pago existente, elija uno de la lista desplegable y seleccione **Reemplazar**.
    > [!NOTE]
    > Si tiene una suscripción asociada a un perfil de facturación, solo puede usar una tarjeta de crédito o débito para pagar por ella. Si tiene cuentas bancarias que aparecen en la página **Método de pago**, no están disponibles para seleccionarlas en la lista desplegable.
5. Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.
6. En el panel **Agregar método de pago**, escriba la información de la cuenta y seleccione **Guardar**. Debe usar un método de pago del mismo país que su espacio empresarial.
7. El nuevo método de pago ya está seleccionado en la lista desplegable. Seleccione **Reemplazar**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Cambiar un método de pago para una única suscripción

Puede cambiar el método de pago usado para pagar una sola suscripción.

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña** Productos, busque la suscripción que desea pagar con el método de pago alternativo.
3. Seleccione **Más acciones** (tres puntos) y, a continuación, seleccione Reemplazar método de **pago.**
4. En el **panel Reemplazar método de** pago, en la lista desplegable, elija un método de pago alternativo o elija agregar un método de pago.
5. Si agrega un método de pago, escriba los detalles de la tarjeta o la cuenta y, a continuación, **seleccione Guardar**.
6. Compruebe que el método de pago seleccionado es correcto y, a continuación, **seleccione Reemplazar**.

## <a name="delete-a-payment-method"></a>Eliminar un método de pago

Solo puede eliminar un método de pago que no esté adjunto a una suscripción o perfil de facturación. Esto se aplica a todas las suscripciones, independientemente de su estado.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Eliminar un método de pago sin suscripciones ni perfiles de facturación adjuntos

Si un método de pago no está asociado a ninguna suscripción o perfil de facturación, puedes eliminarlo inmediatamente.

1. En el Centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Busque el método de pago que desea eliminar, seleccione los tres puntos y, a continuación, **seleccione Eliminar**.
3. En la parte inferior del panel derecho, seleccione **Eliminar**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Eliminar un método de pago con suscripciones o perfiles de facturación adjuntos

Si se adjunta un método de pago a cualquier suscripción o perfil de facturación, reemplázalo primero por un método de pago existente o agrega uno nuevo y, a continuación, elimina el método de pago antiguo.

1. En el Centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Seleccione la fila para el método de pago que desea eliminar. En el panel derecho se enumeran las suscripciones existentes que usan ese método de pago.
3. En el panel derecho, seleccione **Eliminar**.
4. Para usar un método de pago existente, elija uno en la lista desplegable, seleccione **Siguiente** y, a continuación, **seleccione Eliminar**.
    > [!NOTE]
    > Si tiene suscripciones asociadas a un perfil de facturación, solo puede usar una tarjeta de crédito para pagar por ellas. Si tiene cuentas bancarias en la página **Métodos** de pago, no estarán disponibles para elegir en la lista desplegable.
5. Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.
6. Elija el tipo de método de pago que desea agregar, escriba la información de la cuenta y, a continuación, **seleccione Guardar**.
7. El nuevo método de pago ya está seleccionado en la lista desplegable. Seleccione **Siguiente**.
8. Seleccione **Eliminar**.

## <a name="troubleshoot-payment-methods"></a>Solucionar los problemas de los métodos de pago

| Problema | Pasos para la solución de problemas |
|:----------|:-----|
|**Aparece un mensaje de error que dice: "El explorador está configurado actualmente para bloquear cookies".** |Configure el explorador para permitir cookies de terceros y vuelva a intentarlo. |
|**Se rechazó mi tarjeta de crédito o débito.** |Si paga con tarjeta de crédito o débito y su tarjeta se rechaza, recibirá un correo electrónico que indica que Microsoft no pudo procesar el pago. Comprueba de nuevo que el número de tarjeta de detalles de la tarjeta, la fecha de expiración, el nombre de la tarjeta y la dirección, incluida la ciudad, el estado y el código postal aparecen exactamente igual que en la tarjeta y la &mdash; &mdash; declaración. Puede actualizar la información de la tarjeta y enviar inmediatamente  el pago mediante el vínculo Liquidar **saldo** en la sección Facturación de la página de detalles de la suscripción. Para obtener más información, consulte [¿Qué debo hacer si tengo un saldo pendiente?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Si sigue ve el mensaje "rechazado", póngase en contacto con su banco. Es posible que la tarjeta no esté activa. Si ha recibido recientemente la tarjeta en el correo con una fecha de expiración actualizada, asegúrese de que está activada. El banco también puede saber si su tarjeta no está aprobada para transacciones en línea, internacionales o periódicas. |
|**Quiero actualizar un número de tarjeta o cuenta bancaria.** |No puede cambiar el número de tarjeta o cuenta en un método de pago existente. Si su tarjeta o número de cuenta ha cambiado, reemplácelo por un método de pago diferente, que mueve todas las suscripciones activas del método de pago al nuevo y, [a](#replace-a-payment-method)continuación, elimine el método de [pago antiguo.](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached) |
|**Solo tengo una tarjeta o cuenta bancaria en mi cuenta y quiero quitarla.** |Si solo tiene un método de pago, debe [reemplazarlo por](#replace-a-payment-method) un nuevo método de pago para poder eliminarlo. |
|**No puedo agregar mi tarjeta o cuenta bancaria.**  |Debe usar un método de pago emitido desde el mismo país que su espacio empresarial. Si tiene problemas para escribir la información de su tarjeta o cuenta bancaria, puede ponerse [en contacto con el soporte técnico.](../../admin/contact-support-for-business-products.md) |

## <a name="related-content"></a>Contenido relacionado

[Pagar la suscripción empresarial](pay-for-your-subscription.md) (artículo)\
[Administrar perfiles de facturación](manage-billing-profiles.md) (artículo)\
[Cambiar la frecuencia de facturación](change-payment-frequency.md) (artículo)
