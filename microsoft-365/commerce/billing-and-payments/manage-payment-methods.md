---
title: Administrar métodos de pago
f1.keywords:
- CSH
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
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Obtenga información sobre cómo administrar los métodos de pago en el centro de administración de Microsoft 365.
ms.openlocfilehash: 0320f71180a5c2c127217ebf01854943409e6386
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403683"
---
# <a name="manage-payment-methods"></a>Administrar métodos de pago

::: moniker range="o365-21vianet"
> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).
::: moniker-end

Cuando compre productos o servicios empresariales de Microsoft, puede usar un método de pago existente o agregar uno nuevo. Puede usar una tarjeta de crédito o débito o una cuenta bancaria para pagar las cosas que compre.

Si la cuenta empresarial tiene un perfil de facturación y usted es el propietario de un perfil de facturación o un colaborador de Perfil de facturación, puede usar el perfil de facturación respaldado por un pago de tarjeta de crédito o factura para realizar compras o pagar facturas. Si es un administrador de facturas de facturación, solo puede usar un perfil de facturación para pagar las facturas. Para obtener más información acerca de los perfiles de facturación y los roles, consulte [Manage Billing profiles](manage-billing-profiles.md).

Si su cuenta de empresa no tiene un perfil de facturación, cualquier administrador global o de facturación puede administrar y usar cualquier cuenta bancaria que se agregue a la cuenta empresarial. Sin embargo, solo puede administrar o usar las tarjetas de crédito que agregue.

> [!NOTE]
> La opción para pagar con una cuenta bancaria no está disponible en algunos países o regiones.
>
> Debe usar una forma de pago emitida desde el mismo país que su inquilino.

## <a name="add-a-payment-method"></a>Agregar un método de pago.

Agregar un método de pago no asocia ninguna suscripción con él. Para asignar una única suscripción al método de pago, vea [cambiar un método de pago para una única suscripción](#change-a-payment-method-for-a-single-subscription). Para reemplazar todas las suscripciones que usan otro método de pago con la nueva, vea [reemplazar un método de pago](#replace-a-payment-method).

::: moniker range="o365-worldwide"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
::: moniker-end

::: moniker range="o365-germany"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

::: moniker range="o365-21vianet"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

2. Seleccione **Agregar o seleccionar un método de pago**.

3. En la página **Métodos de pago**, seleccione un método de pago con el menú desplegable.

4. Escriba la información de la nueva tarjeta o cuenta bancaria y, a continuación, seleccione **Agregar**.

## <a name="update-payment-method-details"></a>Actualizar detalles del método de pago

Puede cambiar el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de caducidad de un método de pago existente. Sin embargo, no puede cambiar la tarjeta o el número de cuenta. Si el número de cuenta ha cambiado, [reemplácelo con un método de pago diferente](#replace-a-payment-method)y, a continuación, [elimine el antiguo](#delete-a-payment-method).

::: moniker range="o365-worldwide"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
::: moniker-end

::: moniker range="o365-germany"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

::: moniker range="o365-21vianet"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

2. Seleccione la fila del método de pago que se va a actualizar. En el panel derecho, seleccione **Editar**.

3. Actualice la información de su método de pago, incluido el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de expiración y, después, seleccione **Guardar**.

## <a name="replace-a-payment-method"></a>Reemplazar un método de pago

Cuando se reemplaza un método de pago, se reemplaza para todas las suscripciones y perfiles de facturación que usan el mismo método de pago. Al reemplazar un método de pago no se elimina el método de pago existente. Sigue estando disponible para su selección y uso para otras suscripciones y perfiles de facturación.

Para cambiar el método de pago para una sola suscripción, vea [cambiar un método de pago para una sola suscripción](#change-a-payment-method-for-a-single-subscription).

::: moniker range="o365-worldwide"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
::: moniker-end

::: moniker range="o365-germany"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

::: moniker range="o365-21vianet"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

2. Seleccione la fila del método de pago que desea reemplazar. En el panel derecho se muestran todos los perfiles de facturación y las suscripciones individuales que usan el método de pago seleccionado.

3. En el panel derecho, seleccione **Reemplazar método de pago para todos los artículos**.

4. Para usar un método de pago existente, elija uno de la lista desplegable y seleccione **Reemplazar**.
    > [!NOTE]
    > Si tiene una suscripción asociada a un perfil de facturación, solo puede usar una tarjeta de crédito o débito para pagar por ella. Si tiene cuentas bancarias que aparecen en la página **Método de pago**, no están disponibles para seleccionarlas en la lista desplegable.

5. Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.

6. En el panel **Agregar método de pago**, escriba la información de la cuenta y seleccione **Guardar**. Debe usar un método de pago del mismo país que su espacio empresarial.

7. El nuevo método de pago ya está seleccionado en la lista desplegable. Seleccione **Reemplazar**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Cambio de un método de pago para una única suscripción

Puede cambiar el método de pago que se usa para pagar una sola suscripción.

::: moniker range="o365-worldwide"
1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
::: moniker-end

::: moniker range="o365-germany"
1. En el centro de administración, vaya a la página **Facturación** > **Sus productos**.
::: moniker-end

::: moniker range="o365-21vianet"
1. En el centro de administración, vaya a la página **Facturación** > **Sus productos**.
::: moniker-end

2. En la pestaña **suscripciones** , seleccione la suscripción por la que desea pagar con el método de pago alternativo.

3. En **facturación**, junto al método de pago, seleccione **Editar**.

4. Junto a su método de pago existente, seleccione **cambiar**.

5. En la lista desplegable, elija un método de pago alternativo o elija Agregar un método de pago.

6. Si agrega un método de pago, escriba los detalles de la tarjeta o la cuenta y, después, seleccione **Guardar**.

7. Compruebe que el método de pago seleccionado sea correcto y, a continuación, seleccione **Guardar**.

## <a name="delete-a-payment-method"></a>Eliminar un método de pago

Solo se puede eliminar un método de pago que no esté adjunto a una suscripción o a un perfil de facturación. Esto se aplica a todas las suscripciones, independientemente de su estado.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Eliminar un método de pago sin suscripciones o perfiles de facturación adjuntos

Si un método de pago no está asociado a ninguna suscripción o Perfil de facturación, puede eliminarlo inmediatamente.

::: moniker range="o365-worldwide"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
::: moniker-end

::: moniker range="o365-germany"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

::: moniker range="o365-21vianet"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

2. Busque el método de pago para eliminar, seleccione los tres puntos y, a continuación, seleccione **eliminar**.

3. En la parte inferior del panel derecho, seleccione **eliminar**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Eliminar un método de pago con suscripciones o perfiles de facturación adjuntos

Si se adjunta un método de pago a cualquier suscripción o Perfil de facturación, cámbielo por un método de pago existente o agregue uno nuevo y, a continuación, elimine el método de pago antiguo.

::: moniker range="o365-worldwide"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
::: moniker-end

::: moniker range="o365-germany"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

::: moniker range="o365-21vianet"
1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > **métodos de pago** pagos.
::: moniker-end

2. Seleccione la fila del método de pago que se va a eliminar. En el panel derecho se enumeran las suscripciones existentes que usan esa forma de pago.

3. En el panel derecho, seleccione **eliminar**.

4. Para usar un método de pago existente, elija uno en la lista desplegable, seleccione **siguiente**y, a continuación, seleccione **eliminar**.
    > [!NOTE]
    > Si tiene suscripciones asociadas a un perfil de facturación, solo puede usar una tarjeta de crédito para pagar por ellas. Si tiene cuentas bancarias que aparecen en la página de **métodos de pago** , no estarán disponibles para elegir en la lista desplegable.

5. Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.

6. Elija el tipo de método de pago que desea agregar, escriba la información de la cuenta y, a continuación, seleccione **Guardar**.

7. El nuevo método de pago ya está seleccionado en la lista desplegable. Seleccione **Siguiente**.

8. Seleccione **Eliminar**.

## <a name="troubleshoot-payment-methods"></a>Solucionar los problemas de los métodos de pago

|**Problema**|**Pasos para la solución de problemas**|
|:----------|:-----|
|**Obtengo un mensaje de error que dice que el explorador está configurado actualmente para bloquear las cookies.** |Configure el explorador para permitir cookies de terceros y vuelva a intentarlo. |
|**Se ha rechazado mi tarjeta de crédito o débito.** |Si paga con tarjeta de crédito o débito y se rechaza su tarjeta, recibirá un mensaje de correo electrónico en el que se indica que Microsoft no pudo procesar el pago. Compruebe que los detalles de la tarjeta &mdash; , la fecha de expiración, el nombre de la tarjeta y la dirección, incluidos el código postal, la ciudad, el estado y la ciudad &mdash; aparecen exactamente como en la tarjeta y en la instrucción. Puede actualizar la información de la tarjeta y enviar el pago inmediatamente mediante el vínculo **liquidar saldo** en la sección **facturación** de la página Detalles de la suscripción. Para obtener más información, consulte [¿Qué sucede si se ha rechazado mi tarjeta de crédito y el pago está vencido?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)  <br/><br/>  Si sigues viendo el mensaje "rechazado", ponte en contacto con tu banco. Es posible que la tarjeta no esté activa. Si ha recibido recientemente la tarjeta en el correo con una fecha de expiración actualizada, asegúrese de que esté activada. El Banco también puede decirle si su tarjeta no está aprobada para transacciones en línea, internacionales o recurrentes. |
|**Quiero actualizar una tarjeta o un número de cuenta bancaria.** |No puede cambiar la tarjeta o el número de cuenta en un método de pago existente. Si ha cambiado la tarjeta o el número de cuenta, [reemplácelo con un método de pago diferente](#replace-a-payment-method), que mueve todas las suscripciones activas del método de pago al nuevo y, a continuación, [elimine el método de pago antiguo](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Solo tengo una tarjeta o cuenta bancaria en mi cuenta y quiero quitarla.** |Si solo tiene un método de pago, debe [reemplazarlo por un nuevo método de pago](#replace-a-payment-method) para poder eliminarlo. |
|**No puedo agregar mi tarjeta o cuenta bancaria.**  |Debe usar una forma de pago emitida desde el mismo país que su inquilino. Si tiene problemas para escribir la información de la tarjeta o de la cuenta bancaria, puede [ponerse en contacto con el soporte técnico](../../admin/contact-support-for-business-products.md). |

## <a name="related-articles"></a>Artículos relacionados

[Pagar la suscripción de su empresa](pay-for-your-subscription.md)

[Administrar perfiles de facturación](manage-billing-profiles.md)

[Cambiar la frecuencia de pago](change-payment-frequency.md)