---
title: Actualización a un plan de negocio diferente
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: nalinkla, jmueller
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- SaRA
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: La manera más fácil de actualizar los planes es usar la pestaña Actualizar en el Centro de administración. Sin embargo, no siempre se admite la pestaña Actualizar.
ms.date: 04/21/2021
ms.openlocfilehash: b62a1c33c80d63d9065923c97049a8e88e9cc4ec
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68733205"
---
# <a name="upgrade-to-a-different-microsoft-plan"></a>Actualización a otro plan de Microsoft

Cuando su empresa cambia o necesita más características, puede actualizar los planes. La manera más fácil de hacerlo es usar la pestaña **Actualizar** en el Centro de administración. Sin embargo, el uso de la pestaña **Actualizar** no se admite en todas las situaciones. En algunos casos, es posible que pueda cambiar los planes manualmente.

## <a name="use-the-upgrade-tab"></a>Usar la pestaña Actualizar

Cuando se usa la pestaña **Actualizar** , se le guía por el proceso de compra de un nuevo plan. A todos los usuarios se les asignan automáticamente licencias en el nuevo plan y su plan anterior se cancela automáticamente.

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. Seleccione la suscripción que desea actualizar.
3. En la página de detalles de la suscripción, en **Detalles y actualizaciones del producto**, seleccione **Ver actualizaciones recomendadas para su organización**.
4. Busque el plan al que desea actualizar y, a continuación, seleccione el botón **Actualizar** .
5. Escriba el número de licencias que necesita, elija si desea pagar cada mes o por todo el año y, a continuación, seleccione **Ir a la compra**.
    > [!NOTE]
    > Asegúrese de comprar suficientes licencias para cubrir a todos los usuarios.
6. En la página siguiente, compruebe la dirección **Vendido a** , la información **Facturada** a y **Elementos en este orden**. Puede cambiar el método de pago predeterminado en este paso. Si necesita realizar cambios, seleccione **Cambiar** junto a la sección aplicable.
7. Cuando haya terminado, seleccione **Realizar pedido**.

Cuando finalice la compra, puede tardar unos minutos en finalizar la actualización. Podrá empezar a usar inmediatamente la nueva suscripción. Seleccione **Comprobar estado de actualización** para comprobar el progreso de la actualización. Recibirá una notificación cuando se complete la actualización. La notificación se muestra en la página **Sus productos** , junto a la nueva suscripción.

## <a name="the-upgrade-tab-is-empty"></a>La pestaña Actualizar está vacía

Si la pestaña **Actualizar** está vacía, verá una explicación de por qué no se puede actualizar en este momento. Puede intentar [cambiar los planes manualmente](change-plans-manually.md). Para obtener más información, consulte [¿Por qué no puedo actualizar los planes?](#why-cant-i-upgrade-plans).

## <a name="i-dont-see-the-plan-i-want"></a>No veo el plan que quiero

Al usar la pestaña **Actualizar** , los planes a los que puede actualizar se muestran en función de los servicios del plan actual. Solo puede usar la pestaña **Actualizar** para pasar a un plan que tenga los mismos servicios relacionados con los datos o a una versión superior. Esto garantiza que los usuarios no pierdan datos relacionados con esos servicios durante el cambio.

Si desea pasar a un plan con menos servicios, puede [cambiar los planes manualmente](change-plans-manually.md) o [llamar al soporte técnico](../../admin/get-help-support.md) para obtener ayuda.

## <a name="i-only-want-to-upgrade-some-of-my-users-how-do-i-do-that"></a>Solo quiero actualizar algunos de mis usuarios. Cómo hacer eso?

Si solo desea actualizar algunos usuarios a otro plan, pero primero necesita comprar la nueva suscripción, consulte [Cambiar planes manualmente](change-plans-manually.md). Si ya tiene la suscripción a la que desea actualizar los usuarios, consulte [Traslado de usuarios a otra suscripción](move-users-different-subscription.md).

## <a name="why-some-changes-take-longer"></a>Por qué algunos cambios tardan más tiempo

**Número de usuarios asignados:** Si tiene un gran número de usuarios asignados, la actualización tardará más tiempo en moverlos al nuevo plan.

**Comprobaciones de crédito al cambiar de plan:** Si paga por factura o alcanza un determinado nivel de costo, es posible que se requiera una comprobación de crédito. Una comprobación de crédito puede tardar hasta dos días laborables en completarse. Los usuarios tendrán acceso completo a su plan actual hasta que los muevas al nuevo. Recibirá una notificación si se requiere una comprobación de crédito.

## <a name="why-cant-i-upgrade-plans"></a>¿Por qué no puedo actualizar los planes?

Si no ve ningún plan en la pestaña **Actualizar** , significa que el plan no se puede actualizar automáticamente. En algunos casos, es posible que pueda resolver el problema para que pueda ver los planes disponibles para la actualización, o puede actualizar o cambiar los planes manualmente, en su lugar.

### <a name="why-are-there-no-plans-listed-to-upgrade"></a>¿Por qué no aparece ningún plan para actualizar?

#### <a name="you-cant-upgrade-subscriptions-now-because-you-have-more-users-than-licenses"></a>Ahora no puede actualizar las suscripciones porque tiene más usuarios que licencias

Para actualizar los planes automáticamente, a todos los usuarios se les deben asignar licencias válidas. Si ha asignado más licencias que las que ha comprado, verá una alerta en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias</a> que indica que tiene un conflicto de licencias que debe resolverse. [Obtenga información sobre cómo resolver conflictos de licencia](../../commerce/licenses/buy-licenses.md). Después de resolver los conflictos de licencia, debería ver los planes que aparecen en la pestaña **Actualizar** . Si no es así, puede [cambiar los planes manualmente](change-plans-manually.md) o [llamar al soporte técnico](../../admin/get-help-support.md).

#### <a name="you-cant-upgrade-subscriptions-right-now-because-this-subscription-isnt-fully-set-up-or-the-service-isnt-available"></a>No puede actualizar las suscripciones en este momento porque esta suscripción no está totalmente configurada o el servicio no está disponible.

Por ejemplo, si uno de los servicios tiene un incidente, no podrá actualizar hasta que todos los servicios estén en buen estado. Para ver si hay problemas de aprovisionamiento o mantenimiento del servicio, en el centro de administración, vaya a la página **Mantenimiento** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">Estado del servicio</a>.

Si encuentra que un servicio no está completamente preparado o un problema de estado del servicio, espere unas pocas horas para que el servicio se encuentre disponible y vuelva a intentarlo. Si todavía tiene un problema, [llame al soporte técnico](../../admin/get-help-support.md).

#### <a name="you-cant-upgrade-plans-because-another-plan-is-in-the-process-of-being-upgraded-or-is-pending-a-credit-check"></a>No puede actualizar los planes porque otro plan está en proceso de actualización o está pendiente de una comprobación de crédito.

Espere hasta que se complete la comprobación de crédito antes de actualizar los planes. Las comprobaciones de crédito pueden tardar hasta dos días laborables.

#### <a name="currently-this-subscription-is-not-eligible-to-upgrade"></a>Actualmente, esta suscripción no es apta para actualizar

Puede [cambiar los planes manualmente](change-plans-manually.md) o [llamar al soporte técnico](../../admin/get-help-support.md).

#### <a name="i-see-a-different-message-than-whats-listed-here"></a>Veo un mensaje diferente al que aparece aquí

Puede [cambiar los planes manualmente](change-plans-manually.md) o [llamar al soporte técnico](../../admin/get-help-support.md).

### <a name="additional-reasons-you-cant-upgrade"></a>Motivos adicionales por los que no se puede actualizar

#### <a name="you-have-two-or-more-plans-for-the-same-product"></a>Tiene dos o más planes para el mismo producto

Solo puede usar la pestaña **Actualizar** si todos los usuarios se suscriben al mismo plan. Por ejemplo, si tiene dos planes de Microsoft 365 Empresa Estándar, no podrá actualizar automáticamente uno de ellos a otro plan.

#### <a name="you-have-a-prepaid-plan"></a>Tiene un plan de prepago.

Si ha pagado por su suscripción por adelantado, es posible que pueda [cambiar los planes manualmente](change-plans-manually.md). Sin embargo, no recibirá un crédito por el tiempo que queda sin usar en la suscripción actual si actualiza los planes antes de que expire el plan actual.

También puede [llamar al soporte técnico](../../admin/get-help-support.md) para obtener ayuda.

#### <a name="you-have-a-government-or-non-profit-plan"></a>Tiene un plan para la administración pública o para una institución sin ánimo de lucro

Si tiene un plan gubernamental o sin fines de lucro, puede [cambiar los planes manualmente](change-plans-manually.md) o [llamar al soporte técnico](../../admin/get-help-support.md) para obtener ayuda.

#### <a name="the-subscription-that-you-want-to-upgrade-from-has-a-temporary-issue"></a>La suscripción desde la que desea actualizar tiene un problema temporal.

Es posible que no vea ningún plan en la pestaña **Actualizar** porque el servicio está en proceso de actualizar un gran volumen de planes. Inténtelo de nuevo aproximadamente una hora después de su primer intento.

#### <a name="the-plan-that-you-want-to-upgrade-to-isnt-a-supported-option"></a>El plan al que desea actualizar no es una opción compatible.

Al actualizar los planes, los planes a los que puede actualizar se muestran en función de los servicios del plan actual. Solo puede actualizar a un plan que tenga los mismos servicios relacionados con datos, como Exchange Online o SharePoint Online, o a una versión superior de ellos. Esto garantiza que los usuarios no\'pierdan datos relacionados con esos servicios durante la actualización.

Si el plan no es apto para actualizar los planes automáticamente, es posible que pueda [cambiar los planes manualmente](change-plans-manually.md) en su lugar. También puede [llamar al soporte técnico](../../admin/get-help-support.md) para obtener ayuda.

#### <a name="your-subscription-has-an-add-on"></a>La suscripción tiene un complemento

Si tiene un complemento con su suscripción, es posible que pueda [cambiar los planes manualmente](change-plans-manually.md).

#### <a name="your-subscription-has-an-unpaid-balance"></a>La suscripción tiene un saldo no pagado

Para resolver esto, busque la suscripción en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a> y seleccione el vínculo **Pagar ahora** en la sección **Facturación** . Una vez realizado el pago, vuelva a comprobar la pestaña **Actualizar** .

## <a name="what-does-upgrading-a-plan-do-to-my-service-and-billing"></a>¿Qué hace la actualización de un plan a mi servicio y facturación?

Al actualizar los planes automáticamente mediante el botón **Cambiar planes** (o la pestaña **Actualizar** en el nuevo centro de administración), los servicios y la facturación se ven afectados.

### <a name="access-to-services"></a>Acceso a servicios

**Los administradores** no podrán usar el centro de administración mientras se actualiza el plan. Esto puede tardar hasta una hora.
  
Los **usuarios** no experimentarán ninguna interrupción del servicio. Seguirán teniendo el servicio existente hasta que la actualización se complete por completo.
  
### <a name="users-and-licenses"></a>Usuarios y licencias

Los usuarios de la suscripción antigua se transferirán automáticamente a la nueva suscripción.

Si la suscripción anterior incluye varios servicios y ha cambiado a cuál de estos servicios están asignados los usuarios, es posible que quiera tomar nota de esto antes de actualizar los planes para poder volver a crear estos cambios posteriormente. Todos los usuarios tendrán acceso a todos los servicios de la nueva suscripción. Por ejemplo, si previamente compró Microsoft 365 Empresa Premium para los 100 usuarios, pero desasignó el servicio SharePoint Online de 50 de ellos, este cambio no se conservaría después de actualizar los planes.

Si tiene más de una suscripción antes de actualizar los planes y tiene a los usuarios licencias asignadas a más de una suscripción, este patrón de asignación se mantendrá tanto como sea posible en la nueva suscripción.
Todos los datos de usuario se conservarán durante la actualización, incluidos los buzones de Exchange y documentos de SharePoint Online, listas y otra información.
  
### <a name="billing"></a>Facturación

El día que se complete la actualización del plan, se desactivará la facturación de la suscripción anterior y se activará la facturación de la nueva suscripción. Obtendrá un crédito prorrateado correspondiente a los servicios no usados en la suscripción anterior. Recibirá una nueva factura que incluye el crédito de la suscripción anterior en un plazo de 30 días a partir de la actualización a la nueva suscripción.
  
> [!NOTE]
> El tiempo que lleva a su cuenta acreditar su pago depende del método que se usó para pagar la suscripción.
  
**¿Actualizar desde una suscripción de prepago antes de que expire?** Si el costo total de la nueva suscripción es superior o igual al valor restante de su suscripción de prepago, no perderá tiempo de prepago. En la página de finalización de la compra verá un crédito para el tiempo que no haya usado. Pero, si el coste total de su nueva suscripción es inferior al valor restante de la suscripción de prepago actual, perderá parte de su tiempo sin usar. Se le notificará antes de realizar la compra y puede esperar a actualizar hasta que esté más cerca de la fecha de expiración de la suscripción de prepago.

## <a name="call-support-to-help-you-upgrade-plans"></a>Llamar al soporte técnico para ayudarle a actualizar los planes

[Llame al soporte técnico de Microsoft](../../admin/get-help-support.md).

## <a name="related-content"></a>Contenido relacionado

[Cambiar los planes manualmente](change-plans-manually.md) (artículo)\
[Copia de seguridad de datos antes de cambiar Microsoft 365 para planes empresariales](move-users-different-subscription.md) (artículo)
