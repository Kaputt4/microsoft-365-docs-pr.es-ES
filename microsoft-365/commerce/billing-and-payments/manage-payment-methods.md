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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Obtenga información sobre cómo administrar los métodos de pago en el centro de administración de Microsoft 365.
ms.openlocfilehash: 61c6d0b4fb21762eaeee96d8923eda7702fc70bb
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341594"
---
# <a name="manage-payment-methods"></a>Administrar métodos de pago

Cuando compre productos o servicios empresariales de Microsoft, puede usar un método de pago existente o agregar uno nuevo. Puede usar una tarjeta de crédito o débito o una cuenta bancaria para pagar las cosas que compre. Pero solo puede administrar los métodos de pago que agregue.

> [!NOTE]
> La opción para pagar con una cuenta bancaria no está disponible en algunos países o regiones.
>
> Debe usar una forma de pago emitida desde el mismo país que su inquilino.

## <a name="update-payment-method-details"></a>Actualizar detalles del método de pago

Puede cambiar el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de caducidad de un método de pago existente. Sin embargo, no puede cambiar la tarjeta o el número de cuenta. Si el número de cuenta ha cambiado, [reemplácelo con un método de pago diferente](#replace-a-payment-method)y, a continuación, [elimine el antiguo](#delete-a-payment-method).

1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
2. Seleccione la fila del método de pago que se va a actualizar. En el panel derecho, seleccione **Editar**.
3. Actualice la información del método de pago (el nombre de la tarjeta de crédito o débito, la dirección de facturación o la fecha de caducidad) y, a continuación, seleccione **Guardar**.

## <a name="replace-a-payment-method"></a>Reemplazar un método de pago

Cuando se reemplaza un método de pago, se reemplaza para todas las suscripciones y perfiles de facturación que usan el mismo método de pago. Al reemplazar un método de pago no se elimina el método de pago existente. Sigue estando disponible para su selección y uso para otras suscripciones y perfiles de facturación.

Para cambiar el método de pago para una sola suscripción, vea [cambiar un método de pago para una sola suscripción](#change-a-payment-method-for-a-single-subscription).

1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
2. Seleccione la fila del método de pago que desea reemplazar. El panel derecho muestra todos los perfiles de facturación y suscripciones individuales que usan el método de pago seleccionado.
3. En el panel derecho, seleccione **reemplazar el método de pago para todos los elementos**.
4. Para usar un método de pago existente, elija uno en la lista desplegable y, a continuación, seleccione **reemplazar**.
    > [!NOTE]
    > Si tiene suscripciones asociadas a un perfil de facturación, solo puede usar una tarjeta de crédito o débito para pagar por ellas. Si tiene cuentas bancarias que aparecen en la página de **métodos de pago** , no estarán disponibles para seleccionar en la lista desplegable.
5. Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.
6. En el panel **Agregar un método de pago** , escriba la información de la cuenta y, después, seleccione **Guardar**. Debe usar un método de pago del mismo país que el inquilino.
7. El nuevo método de pago ya está seleccionado en la lista desplegable. Seleccione **Reemplazar**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Cambio de un método de pago para una única suscripción

Puede cambiar el método de pago que se usa para pagar una sola suscripción.

1. En el centro de administración, vaya a la página productos de **facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& Services</a> .
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

1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
2. Busque el método de pago para eliminar, seleccione los tres puntos y, a continuación, seleccione **eliminar**.
3. En la parte inferior del panel derecho, seleccione **eliminar**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Eliminar un método de pago con suscripciones o perfiles de facturación adjuntos

Si se adjunta un método de pago a cualquier suscripción o Perfil de facturación, cámbielo por un método de pago existente o agregue uno nuevo y, a continuación, elimine el método de pago antiguo.

1. En el centro de administración, vaya a la página facturas de **facturación** > **&** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">métodos de pago</a> pagos.
2. Seleccione la fila del método de pago que se va a eliminar. En el panel derecho se enumeran las suscripciones existentes que usan esa forma de pago.
3. En el panel derecho, seleccione **eliminar**.
4. Para usar un método de pago existente, elija uno en la lista desplegable, seleccione **siguiente**y, a continuación, seleccione **eliminar**.
    > [!NOTE]
    > Si tiene suscripciones asociadas a un perfil de facturación, solo puede usar una tarjeta de crédito para pagar por ellas. Si tiene cuentas bancarias que aparecen en la página de **métodos de pago** , no estarán disponibles para elegir en la lista desplegable.
5. Para agregar un nuevo método de pago, seleccione **Agregar método de pago**.
6. Elija el tipo de método de pago que desea agregar, escriba la información de la cuenta y, a continuación, seleccione **Guardar**.
7. El nuevo método de pago ya está seleccionado en la lista desplegable. Seleccione **Siguiente**.
8. Seleccione **eliminar**.

## <a name="troubleshoot-payment-methods"></a>Solucionar problemas de métodos de pago

|**Problema**|**Pasos para la solución de problemas**|
|:----------|:-----|
|**Obtengo un mensaje de error que dice que el explorador está configurado actualmente para bloquear las cookies.** |Configure el explorador para permitir cookies de terceros y vuelva a intentarlo. |
|**Se ha rechazado mi tarjeta de crédito o débito.** |Si paga con tarjeta de crédito o débito y se rechaza su tarjeta, recibirá un mensaje de correo electrónico en el que se indica que Microsoft no pudo procesar el pago. Compruebe que los detalles &mdash; de la tarjeta, la fecha de expiración, el nombre de la tarjeta y la dirección, incluidos el código postal, la ciudad, el estado y la ciudad son idénticos a los que aparecen en la tarjeta y en la instrucción. Puede actualizar la información de la tarjeta y enviar el pago inmediatamente mediante el vínculo **liquidar saldo** en la sección **facturación** de la página Detalles de la suscripción. Para obtener más información, consulte [¿Qué sucede si se ha rechazado mi tarjeta de crédito y el pago está vencido?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)  <br/><br/>  Si sigues viendo el mensaje "rechazado", ponte en contacto con tu banco. Es posible que la tarjeta no esté activa. Si ha recibido recientemente la tarjeta en el correo con una fecha de expiración actualizada, asegúrese de que esté activada. El Banco también puede decirle si su tarjeta no está aprobada para transacciones en línea, internacionales o recurrentes. |
|**Quiero actualizar una tarjeta o un número de cuenta bancaria.** |No puede cambiar la tarjeta o el número de cuenta en un método de pago existente. Si ha cambiado la tarjeta o el número de cuenta, [reemplácelo con un método de pago diferente](#replace-a-payment-method), que mueve todas las suscripciones activas del método de pago al nuevo y, a continuación, [elimine el método de pago antiguo](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Solo tengo una tarjeta o cuenta bancaria en mi cuenta y quiero quitarla.** |Si solo tiene un método de pago, debe [reemplazarlo por un nuevo método de pago](#replace-a-payment-method) para poder eliminarlo. |
|**No puedo agregar mi tarjeta o cuenta bancaria.**  |Debe usar una forma de pago emitida desde el mismo país que su inquilino. Si tiene problemas para escribir la información de la tarjeta o de la cuenta bancaria, puede [ponerse en contacto con el soporte técnico](../../admin/contact-support-for-business-products.md). |

## <a name="related-articles"></a>Artículos relacionados

[Pagar la suscripción de su empresa](pay-for-your-subscription.md)

[Administrar perfiles de facturación](manage-billing-profiles.md)

[Cambiar la frecuencia de pago](change-payment-frequency.md)