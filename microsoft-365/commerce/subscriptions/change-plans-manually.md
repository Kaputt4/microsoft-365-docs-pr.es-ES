---
title: Cambiar manualmente los planes de Microsoft 365 para empresas
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
- commerce
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: Para cambiar las suscripciones manualmente, compre una nueva suscripción y asegúrese de que ambas suscripciones están en la lista y activa.
ms.openlocfilehash: 89786b30403a60bd0551351602d6fccc07f3d1a1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636588"
---
# <a name="change-plans-manually"></a>Cambiar planes manualmente

## <a name="step-1-decide-how-to-change-plans"></a>Paso 1: decidir cómo cambiar los planes

La mejor forma de cambiar todos los usuarios de un plan a otro es [usar la pestaña actualizar](upgrade-to-different-plan.md). A veces esto no es posible. Cambie los planes manualmente en su lugar:

- Si la ficha **actualización** indica que no se puede actualizar el plan actual.

- Si selecciona la ficha **Actualizar** , el plan que desea no aparece en la lista.

- Si no desea actualizar todos los usuarios de la misma manera. Algunas empresas necesitan diferentes usuarios suscritos a diferentes planes. Use un cambio manual para esto.

Para continuar con un cambio manual, lea el [paso 2: comprar una nueva suscripción](#step-2-buy-a-new-subscription) en este tema.

> [!IMPORTANT]
> Si va a cambiar a un plan con menos servicios relacionados con datos que su plan actual (degradar), debe realizar manualmente una copia de seguridad de los datos que desee conservar. Para obtener más información, vea [copia de seguridad de datos antes de cambiar O365 para planes de empresa](back-up-data-before-switching-plans.md).

## <a name="step-2-buy-a-new-subscription"></a>Paso 2: comprar una nueva suscripción

**¿Ya ha comprado?** Si ya tiene una suscripción a la que desea mover usuarios, omita este paso y vaya al [paso 3: Compruebe la nueva suscripción y las licencias](#step-3-check-your-new-subscription-and-licenses) en este tema.

O

**Compre una suscripción y licencias nuevas:** Siga los pasos de [comprar otra suscripción de Microsoft 365 para empresas](../buy-another-subscription.md) para comprar una nueva suscripción.

Asegúrese de comprar una suscripción para la misma organización en la que se encuentran ahora los usuarios. Por ejemplo, compruebe las direcciones de correo electrónico de los usuarios que desea mover. Si sus direcciones de correo \@electrónico incluyen contoso.com, debe comprar una nueva suscripción para contoso.com.
Incluya una licencia para cada usuario que quiera mover.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Paso 3: comprobar la nueva suscripción y las licencias

1. En el centro de administración, vaya a **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Productos y servicios</a>.

2. **Comprobar que ambas suscripciones se muestran y están activas** La suscripción desde la que va a mover a los usuarios y la suscripción a la que está moviendo los usuarios deben aparecer juntas. Si la nueva suscripción no está ahí cuando compruebe por primera vez, inténtelo de nuevo más tarde. Compruebe que ambas suscripciones están activas. [La nueva suscripción no aparece o no está activa](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Comprobar que tiene licencias suficientes para cada usuario** Cada usuario necesita una licencia que coincida con su suscripción. Por lo tanto, si desea pasar diez usuarios a Office 365 Enterprise E5, tendrá que asegurarse de que dispone de diez licencias.

4. **¿Necesita más licencias para la nueva suscripción?**
   Vaya a la página **productos & Services** y [compre más licencias](../licenses/buy-licenses.md).

> [¿Qué sucede con las licencias antiguas?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>La nueva suscripción no aparece o no está activa

- **Si ha comprado dos suscripciones y no se enumeran aquí**, es posible que se hayan adquirido para organizaciones diferentes (para diferentes dominios). Las suscripciones no pueden cruzar los límites de la organización.

- **Si sabe que tiene una suscripción adicional**y no aparece aquí, o no está activa, [llame al soporte técnico de Microsoft](../../admin/contact-support-for-business-products.md).

### <a name="what-about-the-old-licenses"></a>¿Qué sucede con las licencias antiguas?

Las licencias de la suscripción actual se quitarán más adelante; solo pagará por las nuevas licencias de usuario desde entonces.

## <a name="step-4-reassign-licenses"></a>Paso 4: reasignar licencias

### <a name="reassign-a-license-for-one-user"></a>Reasignar una licencia para un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la página **usuarios activos** , seleccione el usuario al que desea asignar una licencia.

3. En la pestaña **licencias y aplicaciones** de te, expanda **licencias**, seleccione las casillas para las licencias que desea asignar y, a continuación, seleccione **Guardar cambios**.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Reasignación de licencias para varios usuarios a la vez

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione los círculos que se encuentra junto a los nombres de los usuarios para los que desea reemplazar las licencias existentes.

3. En la parte superior, seleccione **más opciones** (**...**) y, a continuación, elija **administrar licencias de producto**.

4. Seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.

5. Cambie el botón de alternancia a la posición **activado** para los productos que desea asignar a estos usuarios.

    > [!TIP]
    > - Para limitar los servicios que están disponibles para el usuario, cambie a la posición **desactivado** para los servicios que desea quitar para ese usuario. Por ejemplo, si desea que el usuario tenga acceso a todos los servicios disponibles excepto Skype empresarial online, puede cambiar el cambio del servicio Skype empresarial online a la posición **desactivado** .
    > - Cualquier asignación de licencia anterior para los usuarios seleccionados se quitará.

6. En la parte inferior del panel **Reemplazar productos existentes**, seleccione **Reemplazar** \> **Cerrar**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Paso 5: cancelar las suscripciones o quitar las licencias que ya no necesita (opcional)

If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).

Si movió solo algunos usuarios a una suscripción diferente, [elimine las licencias](../licenses/remove-licenses-from-subscription.md) que ya no necesite.

## <a name="call-support-to-help-you-change-plans"></a>Llamar al soporte técnico para ayudarle a cambiar de plan
[Llamar al soporte técnico de Microsoft](../../admin/contact-support-for-business-products.md)