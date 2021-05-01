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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
ms.reviewer: jamitche
search.appverid:
- MET150
description: Obtenga información sobre cómo administrar los métodos de pago en el Centro de administración de Microsoft 365.
ms.date: 04/02/2021
ms.openlocfilehash: 4b35b7b8e874915e5f9c792686ff0e368292c802
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107044"
---
# <a name="manage-payment-methods"></a>Administrar métodos de pago

Cuando compra productos o servicios empresariales de Microsoft, puede usar un método de pago existente o agregar uno nuevo. Puede usar una tarjeta de crédito, débito o una cuenta bancaria para pagar sus compras.

Si su cuenta empresarial tiene un perfil de facturación y usted es el propietario de un perfil de facturación o colaborador de perfil de facturación, puede usar el perfil de facturación con respaldo en el pago con tarjeta de crédito o factura para realizar compras o pagar facturas. Si es administrador de facturación, solo puede usar un perfil de facturación para pagar facturas. Para obtener más información sobre los perfiles de facturación y los roles, consulte [Administrar perfiles de facturación](manage-billing-profiles.md).

Si su cuenta empresarial no tiene un perfil de facturación, cualquier administrador global o de facturación puede administrar y usar cualquier cuenta bancaria que se haya agregado a la cuenta empresarial. Sin embargo, solo puede administrar o usar las tarjetas de crédito que agregue.

> [!NOTE]
> La opción de pagar con una cuenta bancaria no está disponible en algunos países o regiones.
>
> Debe usar un método de pago emitido desde el mismo país que su espacio empresarial.

## <a name="before-you-begin"></a>Antes de empezar

Para poder realizar las tareas de este artículo, debe ser un administrador global o de facturación. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Agregar un método de pago

Al agregar un método de pago no se asocia ninguna suscripción. Para asignar una única suscripción al método de pago, vea [Cambiar un método de pago para una única suscripción](#change-a-payment-method-for-a-single-subscription). Para reemplazar todas las suscripciones que usan otro método de pago por la nueva, vea [Reemplazar un método de pago](#replace-a-payment-method).

1. En el Centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Seleccione **Agregar o seleccionar un método de pago**.
3. En la página **Métodos de pago**, seleccione un método de pago con el menú desplegable.
4. Escriba la información de la nueva tarjeta de crédito o cuenta bancaria y, después, seleccione **Agregar**.

## <a name="update-payment-method-details"></a>Actualizar detalles del método de pago

Puede cambiar el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de expiración de un método de pago existente. Sin embargo, no puede cambiar el número de tarjeta o cuenta. Si el número de cuenta ha cambiado, [reemplácelo con un método de pago diferente](#replace-a-payment-method) y, después, [elimine el antiguo método](#delete-a-payment-method).

1. En el Centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Seleccione la fila del método de pago que se va a actualizar. En el panel derecho, seleccione **Editar**.
3. Actualice la información de su método de pago, incluido el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de expiración y, después, seleccione **Guardar**.

## <a name="replace-a-payment-method"></a>Reemplazar un método de pago

Cuando se reemplaza un método de pago, se reemplaza por todas las suscripciones y los perfiles de facturación que usan el mismo método de pago. Si se reemplaza un método de pago, no se elimina el método de pago existente. Seguirá estando disponible para seleccionar y usar para otras suscripciones y perfiles de facturación.

Para cambiar el método de pago de una única suscripción, vea [Cambiar un método de pago para una única suscripción](#change-a-payment-method-for-a-single-subscription).

1. En el centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Seleccione la fila del método de pago que desea reemplazar. En el panel derecho se muestran todos los perfiles de facturación y las suscripciones individuales que usan el método de pago seleccionado.
3. En el panel derecho, seleccione **Reemplazar método de pago para todos los artículos**.
4. Para usar un método de pago existente, elija uno de la lista desplegable y seleccione **Reemplazar**.
    > [!NOTE]
    > Si tiene una suscripción asociada a un perfil de facturación, solo puede usar una tarjeta de crédito o débito para pagar por ella. Si tiene cuentas bancarias que aparecen en la página **Método de pago**, no están disponibles para seleccionarlas en la lista desplegable.
5. Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.
6. En el panel **Agregar método de pago**, escriba la información de la cuenta y seleccione **Guardar**. Debe usar un método de pago del mismo país que su espacio empresarial.
7. El nuevo método de pago ya está seleccionado en la lista desplegable. Seleccione **Reemplazar**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Cambiar un método de pago para una sola suscripción

Puede cambiar el método de pago que se usa para pagar una sola suscripción.

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la pestaña **Productos**, busque la suscripción por la que quiere pagar con el método de pago alternativo.
3. Seleccione **Más acciones** (tres puntos) y, después, seleccione **Reemplazar método de pago**.
4. En el panel **Reemplazar método de pago**, de la lista desplegable, elija un método de pago alternativo o elija agregar un método de pago.
5. Si agrega un método de pago, escriba la tarjeta o los detalles de la cuenta y, después, **Guardar**.
6. Compruebe que el método de pago seleccionado es el correcto y, a continuación, **Reemplazar**.

## <a name="delete-a-payment-method"></a>Eliminar un método de pago

Solo puede eliminar un método de pago que no esté adjunto a una suscripción o a un perfil de facturación. Esto se aplica a todas las suscripciones, independientemente de su estado.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Eliminar un método de pago que no esté asociado a suscripciones o perfiles de facturación.

Si un método de pago no está asociado a ninguna suscripción o perfil de facturación, puede eliminarlo inmediatamente.

1. En el Centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Busque el método de pago que desea eliminar, seleccione los tres puntos y, después, **Eliminar**.
3. En la parte inferior del panel derecho, seleccione **Borrar**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Eliminar un método de pago asociado a suscripciones o perfiles de facturación

Si un método de pago está asociado a cualquier suscripción o perfil de facturación, primero debe reemplazarlo con un método de pago existente, o agregue uno nuevo y, después, elimine el método de pago antiguo.

1. En el Centro de administración, vaya a la página **Facturación** > **Facturas y pagos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Métodos de pago</a>.
2. Seleccione la fila del método de pago que desea eliminar. En el panel derecho se enumeran las suscripciones existentes que usan ese método de pago.
3. En el panel derecho, seleccione **Borrar**.
4. Para usar un método de pago existente, elija uno de la lista desplegable, seleccione **Siguiente** y, después, **Eliminar**.
    > [!NOTE]
    > Si tiene suscripciones asociadas a un perfil de facturación, solo puede usar una tarjeta de crédito para pagarlas. Si tiene cuentas bancarias que aparecen en la página **Métodos de pago**, no están disponibles para seleccionarlas en la lista desplegable.
5. Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.
6. Elija el tipo de método de pago que desea agregar, escriba la información de la cuenta y, a continuación, **Guardar**.
7. El nuevo método de pago ya está seleccionado en la lista desplegable. Seleccione **Siguiente**.
8. Seleccione **Eliminar**.

## <a name="troubleshoot-payment-methods"></a>Solucionar los problemas de los métodos de pago

| Problema | Pasos para la solución de problemas |
|:----------|:-----|
|**Recibo un mensaje de error que indica "El explorador actualmente está configurado para bloquear las cookies".** |Configure el explorador para permitir cookies de terceros y vuelva a intentarlo. |
|**Mi tarjeta de crédito o débito fue rechazada.** |Si paga mediante tarjeta de crédito o débito y se rechaza la tarjeta, recibirá un correo electrónico en el que se indica que Microsoft no pudo procesar el pago. Primero, compruebe que los detalles de la tarjeta &mdash;el número, la fecha de expiración, el titular de la tarjeta y la dirección, incluida la ciudad, el estado y el código postal&mdash; coinciden exactamente con los de la tarjeta y su estado de cuenta. Puede actualizar la información de la tarjeta y efectuar inmediatamente el pago mediante el vínculo **Liquidar saldo** de la sección **Facturación** de la página de detalles de la suscripción. Para obtener más información, consulte [¿Qué debo hacer si tengo un saldo pendiente?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Si continúa viendo el mensaje "rechazado", póngase en contacto con el banco. Es posible que la tarjeta no esté activada. Si recientemente recibió la tarjeta por correo con la fecha de expiración actualizada, asegúrese de que está activada. Su banco también puede decirle si su tarjeta no está aprobada para cargos en línea, internacionales o recurrentes. |
|**Quiero actualizar el número de una tarjeta o cuenta bancaria.** |No puede cambiar el número de tarjeta o cuenta en un método de pago existente. Si ha cambiado el número de su tarjeta o cuenta, [reemplácelo por un método de pago](#replace-a-payment-method)diferente, que transfiera todas las suscripciones activas al nuevo método de pago y, después, [elimine el método de pago antiguo](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Solo tengo una tarjeta o cuenta bancaria en mi cuenta y quiero quitarla.** |Si solo tiene un método de pago, debe [cambiarlo por un nuevo método de pago](#replace-a-payment-method) antes de poder eliminarlo. |
|**No puedo agregar mi tarjeta de crédito o cuenta bancaria.**  |Debe usar un método de pago emitido desde el mismo país que su espacio empresarial. Si tiene problemas para escribir su tarjeta de crédito o cuenta bancaria, póngase en contacto con el [soporte técnico](../../admin/contact-support-for-business-products.md). |

## <a name="related-content"></a>Contenido relacionado

[Pagar la suscripción empresarial](pay-for-your-subscription.md) (artículo)\
[Administrar perfiles de facturación](manage-billing-profiles.md) (artículo)\
[Cambiar la frecuencia de facturación](change-payment-frequency.md) (artículo)