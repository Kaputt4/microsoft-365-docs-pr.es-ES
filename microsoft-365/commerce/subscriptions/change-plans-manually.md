---
title: Cambiar Microsoft 365 planes de negocio manualmente
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Cambie las suscripciones manualmente comprando una nueva suscripción y asegurándose de que ambas suscripciones estén enumeradas y activas.
ROBOTS: NOINDEX
ms.date: 03/17/2021
ms.openlocfilehash: f5a44b7a3c01883ed42ca4ed203b63ccf77f9b72
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536111"
---
# <a name="change-plans-manually"></a>Cambiar planes manualmente

## <a name="step-1-decide-how-to-change-plans"></a>Paso 1: Decidir cómo cambiar los planes

La mejor manera de cambiar todos los usuarios de un plan a otro es [usar la pestaña Actualizar](upgrade-to-different-plan.md). A veces esto no es posible. Cambie los planes manualmente en su lugar:

- Si la **pestaña** Actualización indica que no puede actualizar el plan actual.

- Si, al seleccionar la **pestaña Actualizar,** no aparece el plan que desea.

- Si no desea actualizar todos los usuarios de la misma manera. Algunas empresas necesitan usuarios diferentes suscritos a planes diferentes. Use un cambio manual para esto.

Para continuar con un cambio manual, lea [Paso 2: Comprar una nueva suscripción](#step-2-buy-a-new-subscription) en este tema.

> [!IMPORTANT]
> Si va a cambiar a un plan con menos servicios relacionados con datos que el plan actual (degradación), debe realizar manualmente una copia de seguridad de los datos que desee conservar. Para obtener más información, vea [Back up data before changing plans](back-up-data-before-switching-plans.md).

## <a name="step-2-buy-a-new-subscription"></a>Paso 2: Comprar una nueva suscripción

**¿Ya se ha comprado?** Si ya tiene una suscripción a la que desea mover usuarios, omita este paso y vaya al [Paso 3: Comprobar](#step-3-check-your-new-subscription-and-licenses) su nueva suscripción y licencias en este tema.

O

**Comprar una suscripción y licencias nuevas:** Siga los pasos de [Comprar otra suscripción Microsoft 365 para empresas](../try-or-buy-microsoft-365.md) para comprar una nueva suscripción.

Asegúrese de comprar una suscripción para la misma organización en la que están los usuarios ahora. Por ejemplo, compruebe las direcciones de correo electrónico de los usuarios que desea mover. Si sus direcciones de correo electrónico incluyen contoso.com, debe comprar una \@ nueva suscripción para contoso.com.
Incluye una licencia para cada usuario que quieras mover.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Paso 3: Comprobar su nueva suscripción y licencias

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.

2. **Comprobar que ambas suscripciones están enumeradas y activas** La suscripción desde la que se van a mover los usuarios y la suscripción a la que se van a mover los usuarios deben aparecer juntas. Si la nueva suscripción no está ahí cuando se comprueba por primera vez, inténtelo de nuevo más adelante. Compruebe que ambas suscripciones están activas. [La nueva suscripción no aparece o no está activa.](#the-new-subscription-isnt-listed-or-isnt-active)

3. **Compruebe que tiene suficientes licencias para cada usuario** Cada usuario necesita una licencia que coincida con su suscripción. Por lo tanto, si quieres mover diez usuarios a Microsoft 365 Empresa Premium, tendrás que asegurarte de que hay diez licencias disponibles.

4. **¿Necesita más licencias para la nueva suscripción?**
   Vaya a la **página Sus productos** y compre más [licencias.](../licenses/buy-licenses.md)

> [¿Qué pasa con las licencias antiguas?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>La nueva suscripción no aparece o no está activa

- **Si compraste dos suscripciones** y no aparecen en la lista aquí, es posible que se hayan comprado para distintas organizaciones (para dominios diferentes). Las suscripciones no pueden cruzar los límites de la organización.

- **Si sabe que tiene una suscripción adicional** y no aparece aquí, o no está activa, llame al soporte técnico de [Microsoft](../../business-video/get-help-support.md).

### <a name="what-about-the-old-licenses"></a>¿Qué pasa con las licencias antiguas?

Las licencias de la suscripción actual se quitarán más adelante; solo pagará las nuevas licencias de usuario a partir de ese momento.

## <a name="step-4-reassign-licenses"></a>Paso 4: Reasignar licencias

### <a name="reassign-a-license-for-one-user"></a>Reasignar una licencia para un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la **página Usuarios activos,** seleccione el usuario al que desea asignar una licencia.

3. En la **pestaña Licencias y aplicaciones,** expanda **Licencias**, seleccione los cuadros correspondientes a las licencias que desea asignar y, a continuación, seleccione **Guardar cambios**.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Reasignar licencias para varios usuarios a la vez

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione los círculos junto a los nombres de los usuarios para los que desea reemplazar las licencias existentes.

3. En la parte superior, seleccione los tres puntos (más acciones) y, a continuación, elija **Administrar licencias de productos**.

4. Seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.

5. Cambie la alternancia a **la posición On** para los productos que desea asignar a estos usuarios.

    > [!TIP]
    > - Para limitar los servicios que están disponibles para  el usuario, cambie a alternancias a la posición Desactivado para los servicios que desea quitar para ese usuario. Por ejemplo, si desea que el usuario tenga acceso a todos los servicios disponibles excepto Skype Empresarial Online, puede cambiar la alternancia del servicio Skype Empresarial Online a la posición **Desactivado.**
    > - Cualquier asignación de licencia anterior para los usuarios seleccionados se quitará.

6. En la parte inferior del panel **Reemplazar productos existentes**, seleccione **Reemplazar** \> **Cerrar**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Paso 5: Cancelar suscripciones o quitar licencias que ya no necesite (Opcional)

If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).

Si movió solo algunos usuarios a una suscripción diferente, quite las [licencias](../licenses/buy-licenses.md) que ya no necesite.

## <a name="call-support-to-help-you-change-plans"></a>Llamar al soporte técnico para ayudarle a cambiar los planes
[Llamar al soporte técnico de Microsoft](../../business-video/get-help-support.md)
