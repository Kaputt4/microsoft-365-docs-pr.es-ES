---
title: Actualizar a un plan de negocio diferente
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
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
ms.custom:
- SaRA
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
description: Obtenga información sobre cómo actualizar a una nueva suscripción.
monikerRange: o365-worldwide
ms.openlocfilehash: 7739da2d56fa0d37dd64b22b2959ad6dca198e75
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046221"
---
# <a name="upgrade-to-a-different-plan"></a>Actualizar a un plan diferente 

Cuando cambie su empresa o necesite más características, puede actualizar los planes. La forma más sencilla de hacerlo es usar la pestaña **actualización** en el centro de administración. Sin embargo, no se admite el uso de la pestaña **actualización** en todas las situaciones. En algunos casos, es posible que pueda cambiar de plan manualmente.

> [!NOTE]
> Este artículo se aplica al nuevo centro de administración. Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio. Para ver el artículo sobre el centro de administración anterior, consulte [cambiar a otro Microsoft 365 para el plan de negocios](switch-to-a-different-plan.md).

## <a name="use-the-upgrade-tab"></a>Usar la pestaña actualización

Cuando se usa la pestaña **Actualizar** , se le guiará por el proceso de compra de un nuevo plan. A todos los usuarios se les asignan automáticamente licencias en el nuevo plan y se cancela el plan antiguo.

1. En el centro de administración, vaya a la página **facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de productos</a> .

2. Seleccione la suscripción que desea actualizar.

3. En la página Detalles de la suscripción, seleccione **Actualizar**.

4. Busque el plan al que desea realizar la actualización y, a continuación, seleccione el botón **Actualizar** .

5. Escriba el número de licencias que necesita, elija si desea pagar por meses o por todo el año y, a continuación, seleccione **ir a desproteger**.

    > [!NOTE]
    > Asegúrese de comprar licencias suficientes para abarcar a todos los usuarios.

6. En la página siguiente, Compruebe la dirección **vendido a** , la información **facturada** y **los elementos en este orden**. Puede cambiar el método de pago predeterminado en este paso. Si necesita realizar cambios, seleccione **cambiar** junto a la sección correspondiente.

7. Cuando haya terminado, seleccione **realizar pedido**.

Cuando termine la desprotección, puede tardar unos minutos en concluir la actualización. Podrá empezar a usar inmediatamente la nueva suscripción. Seleccione **comprobar el estado** de la actualización para comprobar el progreso de la actualización. Recibirá una notificación cuando se complete la actualización. La notificación se muestra en la página **sus productos** , junto a la nueva suscripción.

## <a name="the-upgrade-tab-is-empty"></a>La pestaña de actualización está vacía

Si la pestaña de **actualización** está vacía, verá una explicación de por qué no puede actualizar en este momento. Puede intentar cambiar los [planes manualmente](change-plans-manually.md). Para obtener más información, consulte [¿por qué no puedo actualizar planes?](#why-cant-i-upgrade-plans).

## <a name="i-dont-see-the-plan-i-want"></a>No veo el plan que quiero

Cuando se usa la pestaña **Actualizar** , los planes a los que se puede actualizar se muestran en función de los servicios de su plan actual. Solo puede usar la pestaña de **actualización** para desplazarse a un plan que tenga los mismos servicios relacionados con datos o a una versión superior. Esto garantiza que los usuarios no perderán los datos relacionados con estos servicios durante el cambio.

Si desea pasar a un plan con menos servicios, puede [cambiar los planes manualmente](change-plans-manually.md)o [llamar al soporte técnico](../../admin/contact-support-for-business-products.md) para obtener ayuda.

## <a name="why-some-changes-take-longer"></a>¿Por qué algunos cambios tardan más

**Número de usuarios asignados:** Si tiene un gran número de usuarios asignados, se tardará más en realizar la actualización para moverlos al nuevo plan.

**Comprobaciones de crédito al cambiar de plan:** Si paga mediante factura o llega a un determinado nivel de costo, puede que sea necesaria una comprobación de crédito. Una comprobación de crédito puede tardar hasta dos días laborables en completarse. Los usuarios tendrán acceso total a su plan actual hasta que los mueva a la nueva. Recibirá una notificación si es necesaria una comprobación de crédito.

## <a name="why-cant-i-upgrade-plans"></a>¿Por qué no puedo actualizar planes?

Si no ve ningún plan en la ficha **Actualizar** , significa que su plan no se puede actualizar automáticamente. En algunos casos, es posible que pueda resolver el problema para que pueda ver los planes disponibles para la actualización, o puede que pueda actualizar o cambiar los planes manualmente en su lugar.

 ### <a name="why-are-there-no-plans-listed-to-upgrade"></a>¿Por qué no se muestran planes para la actualización?

#### <a name="you-cant-upgrade-subscriptions-now-because-you-have-more-users-than-licenses"></a>No puede actualizar las suscripciones ahora porque tiene más usuarios que licencias.

Para actualizar los planes de forma automática, todos los usuarios deben tener asignadas licencias válidas. Si ha asignado más licencias que las que ha comprado, verá una alerta en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias</a> que indica que tiene un conflicto de licencias que debe resolverse. [Obtenga información sobre cómo resolver conflictos de licencia](../../admin/manage/resolve-license-conflicts.md). Una vez resueltos los conflictos de licencias, verá los planes que aparecen en la ficha **actualización** . Si no es así, puede [cambiar los planes manualmente](change-plans-manually.md)o [llamar al soporte técnico](../../admin/contact-support-for-business-products.md).

#### <a name="you-cant-upgrade-subscriptions-right-now-because-this-subscription-isnt-fully-set-up-or-the-service-isnt-available"></a>No puede actualizar las suscripciones ahora porque esta suscripción no está totalmente configurada o el servicio no está disponible.

Por ejemplo, si uno de los servicios tiene un incidente, no podrá realizar la actualización hasta que todos los servicios estén en buen estado. Para ver si hay problemas de aprovisionamiento o de estado del servicio, en el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">Estado del servicio</a> de **mantenimiento** \> .

Si encuentra que un servicio no está completamente preparado o un problema de estado del servicio, espere unas pocas horas para que el servicio se encuentre disponible y vuelva a intentarlo. Si todavía tiene un problema, [llame al soporte técnico](../../admin/contact-support-for-business-products.md).

#### <a name="you-cant-upgrade-plans-because-another-plan-is-in-the-process-of-being-upgraded-or-is-pending-a-credit-check"></a>No puede actualizar planes porque hay otro plan en curso de actualización o está pendiente de una comprobación de crédito.

Espere hasta que se haya completado la comprobación de crédito antes de actualizar los planes. Las comprobaciones de crédito pueden tardar hasta dos días laborables.

#### <a name="currently-this-subscription-is-not-eligible-to-upgrade"></a>Actualmente, esta suscripción no es apta para la actualización.

Puede [cambiar los planes manualmente](change-plans-manually.md) o [llamar a soporte técnico](../../admin/contact-support-for-business-products.md).

#### <a name="i-see-a-different-message-than-whats-listed-here"></a>Veo un mensaje distinto de lo que se ha incluido aquí.

Puede [cambiar los planes manualmente](change-plans-manually.md) o [llamar a soporte técnico](../../admin/contact-support-for-business-products.md).

### <a name="additional-reasons-you-cant-upgrade"></a>Otros motivos por los que no se puede actualizar

#### <a name="you-have-two-or-more-plans-for-the-same-product"></a>Tiene dos o más planes para el mismo producto

Solo puede usar la pestaña **Actualizar** si todos los usuarios se suscriben al mismo plan. Por ejemplo, si tiene dos planes estándar de Microsoft 365 Business, no podrá actualizar automáticamente uno de ellos a otro plan.

#### <a name="you-have-a-prepaid-plan"></a>Tiene un plan de prepago.

Si ha pagado por adelantado la suscripción, es posible que pueda cambiar de [plan manualmente](change-plans-manually.md). Sin embargo, no recibirá ningún crédito por el tiempo sin usar restante en su suscripción actual si actualiza los planes antes de que expire el plan actual.

También puede [llamar al soporte técnico](../../admin/contact-support-for-business-products.md) para obtener ayuda.

#### <a name="you-have-a-government-or-non-profit-plan"></a>Tiene un plan para la administración pública o para una institución sin ánimo de lucro

Si tiene un plan de administración pública o sin ánimo de lucro, puede [cambiar los planes manualmente](change-plans-manually.md) o [llamar al soporte técnico](../../admin/contact-support-for-business-products.md) para obtener ayuda.

#### <a name="the-subscription-that-you-want-to-upgrade-from-has-a-temporary-issue"></a>La suscripción desde la que desea actualizar tiene un problema temporal

Es posible que no vea ningún plan en la pestaña de **actualización** porque el servicio está en proceso de actualización de un gran volumen de planes. Inténtelo de nuevo aproximadamente una hora después de su primer intento.

#### <a name="the-plan-that-you-want-to-upgrade-to-isnt-a-supported-option"></a>El plan al que desea actualizar no es una opción admitida

Al actualizar los planes, se muestran los planes a los que puede actualizar en función de los servicios de su plan actual. Solo se puede actualizar a un plan que tenga los mismos servicios relacionados con datos, como Exchange online o SharePoint Online, o a una versión posterior de ellos. Esto garantiza que los usuarios\'no pierdan los datos relacionados con estos servicios durante la actualización.

Si el plan no es elegible para actualizar los planes automáticamente, es posible que pueda [cambiar los planes manualmente](change-plans-manually.md)en su lugar. También puede [llamar al soporte técnico](../../admin/contact-support-for-business-products.md) para obtener ayuda.

#### <a name="your-subscription-has-an-add-on"></a>La suscripción tiene un complemento

Si tiene un complemento con su suscripción, es posible que pueda [cambiar de plan manualmente](change-plans-manually.md).

#### <a name="your-subscription-has-an-unpaid-balance"></a>Su suscripción tiene un saldo no pagado

Para solucionar esto, busque la suscripción en la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">sus productos</a> y seleccione el vínculo **pagar ahora** en la sección **facturación** . Una vez realizado el pago, vuelva a comprobar la pestaña de **actualización** .

## <a name="what-does-upgrading-a-plan-do-to-my-service-and-billing"></a>¿Qué hace la actualización de un plan a mi servicio y facturación?

Al actualizar los planes automáticamente mediante el botón **cambiar de plan** (o la pestaña **actualización** del nuevo centro de administración), los servicios y la facturación se ven afectados.

### <a name="access-to-services"></a>Acceso a servicios

 Los **administradores** no podrán usar el centro de administración mientras se esté actualizando el plan. Esto puede tardar hasta una hora.
  
 Los **usuarios** no experimentarán ninguna interrupción del servicio. Seguirán teniendo el servicio existente hasta que la actualización se complete por completo.
  
### <a name="users-and-licenses"></a>Usuarios y licencias

Los usuarios de la suscripción antigua se transferirán automáticamente a la nueva suscripción.
  
Si su suscripción antigua incluye varios servicios y, si ha cambiado los servicios a los que están asignados, es posible que desee tener esto antes de actualizar los planes para poder volver a crear los cambios posteriormente. Todos los usuarios tendrán acceso a todos los servicios de la nueva suscripción. Por ejemplo, si adquirió anteriormente Microsoft 365 Business Premium para los 100 de los usuarios, pero sin asignar el servicio de SharePoint Online de 50, este cambio no se mantendrá después de actualizar los planes.
  
Si tiene más de una suscripción antes de actualizar los planes, y para que los usuarios tengan asignadas licencias a más de una suscripción, este patrón de asignación se mantendrá lo máximo posible en la nueva suscripción.
  
Todos los datos de usuario se conservarán durante la actualización, incluidos los buzones de Exchange y los documentos, listas y otra información de SharePoint Online.
  
### <a name="billing"></a>Facturación

El día en que la actualización del plan haya finalizado, la facturación en su suscripción antigua se desactivará y se activará la facturación de la nueva suscripción. Obtendrá un crédito prorrateado correspondiente a los servicios no usados en la suscripción anterior. Recibirá una factura nueva que incluye el crédito por su suscripción antigua en un plazo de 30 días a partir de la actualización a la nueva suscripción.
  
> [!NOTE]
> El tiempo que lleva a su cuenta acreditar su pago depende del método que se usó para pagar la suscripción.
  
**¿Va a actualizar desde una suscripción de prepago antes de que expire?** Si el costo total de la nueva suscripción es superior o igual al valor restante de su suscripción de prepago, no perderá tiempo de prepago. En la página de finalización de la compra verá un crédito para el tiempo que no haya usado. Pero, si el coste total de su nueva suscripción es inferior al valor restante de la suscripción de prepago actual, perderá parte de su tiempo sin usar. Se le notificará antes de que lo proteja y puede esperar a que se actualice hasta más cerca de la fecha de expiración de la suscripción de prepago.

## <a name="call-support-to-help-you-upgrade-plans"></a>Llamar al soporte técnico para ayudarle a actualizar los planes

[Llamar al soporte técnico de Microsoft](../../admin/contact-support-for-business-products.md)

## <a name="related-articles"></a>Artículos relacionados

[Cambiar planes manualmente](change-plans-manually.md)

[Copia de seguridad de datos antes de cambiar Microsoft 365 para planes de empresa](back-up-data-before-switching-plans.md)
