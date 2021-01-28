---
title: Cambiar manualmente los planes de Microsoft 365 para empresas
f1.keywords:
- NOCSH
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
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ROBOTS: NOINDEX
description: Cambie las suscripciones manualmente comprando una nueva suscripción y asegurándose de que ambas se muestran y están activas.
ms.openlocfilehash: 1127a48ff23c528e3218bae4ccfd063df5e3c26d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029391"
---
# <a name="change-plans-manually"></a>Cambiar planes manualmente

## <a name="step-1-decide-how-to-change-plans"></a>Paso 1: Decidir cómo cambiar planes

La mejor manera de cambiar todos los usuarios de un plan a otro [es usar la pestaña Actualizar](upgrade-to-different-plan.md). A veces esto no es posible. Cambie los planes manualmente en su lugar:

- Si la **pestaña** Actualización indica que no puede actualizar el plan actual.

- Si, al seleccionar la pestaña **Actualizar,** el plan que desea no aparece en la lista.

- Si no desea actualizar todos los usuarios de la misma manera. Algunas empresas necesitan que diferentes usuarios se suscriban a diferentes planes. Use un cambio manual para esto.

Para continuar con un cambio manual, lea [el Paso 2: Comprar una nueva suscripción](#step-2-buy-a-new-subscription) en este tema.

> [!IMPORTANT]
> Si va a cambiar a un plan con menos servicios relacionados con datos que el plan actual (degradación), debe realizar manualmente una copia de seguridad de los datos que desee conservar. Para obtener más información, vea [Copia de seguridad de datos antes de cambiar planes.](back-up-data-before-switching-plans.md)

## <a name="step-2-buy-a-new-subscription"></a>Paso 2: Comprar una nueva suscripción

**¿Ya se ha comprado?** Si ya tiene una suscripción a la que quiere mover usuarios, omita este paso y vaya al paso [3:](#step-3-check-your-new-subscription-and-licenses) Compruebe la nueva suscripción y las licencias en este tema.

OR

**Compre una nueva suscripción y licencias:** Siga los pasos descritos en Comprar otra suscripción de [Microsoft 365](../buy-another-subscription.md) para empresas para comprar una nueva suscripción.

Asegúrese de comprar una suscripción para la misma organización en la que se encuentran ahora los usuarios. Por ejemplo, compruebe las direcciones de correo electrónico de los usuarios que desea mover. Si sus direcciones de correo electrónico contoso.com, debe comprar una \@ nueva suscripción para contoso.com.
Incluya una licencia para cada usuario que desee mover.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Paso 3: Comprobar la nueva suscripción y las licencias

1. En el Centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.

2. **Comprobar que ambas suscripciones están enumeradas y activas** La suscripción desde la que mueve los usuarios y la suscripción a la que va a mover los usuarios deben aparecer juntas. Si la nueva suscripción no está ahí cuando se comprueba por primera vez, inténtelo de nuevo más tarde. Comprueba que ambas suscripciones están activas. [La nueva suscripción no aparece o no está activa.](#the-new-subscription-isnt-listed-or-isnt-active)

3. **Compruebe que tiene suficientes licencias para cada usuario** Cada usuario necesita una licencia que coincida con su suscripción. Por lo tanto, si desea mover diez usuarios a Microsoft 365 Empresa Premium, deberá asegurarse de que hay diez licencias disponibles.

4. **¿Necesita más licencias para la nueva suscripción?**
   Vaya a la **página Sus productos** y compre más [licencias.](../licenses/buy-licenses.md)

> [¿Qué pasa con las licencias antiguas?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>La nueva suscripción no aparece en la lista o no está activa

- **Si compró dos suscripciones y** no aparecen en la lista aquí, es posible que se hayan comprado para distintas organizaciones (para dominios diferentes). Las suscripciones no pueden cruzar los límites de la organización.

- **Si sabe que tiene una suscripción adicional** y no aparece aquí, o no está activa, llame al soporte técnico de [Microsoft.](../../admin/contact-support-for-business-products.md)

### <a name="what-about-the-old-licenses"></a>¿Qué pasa con las licencias antiguas?

Las licencias de la suscripción actual se quitarán más adelante; Solo tendrá que pagar las licencias de usuario nuevas a partir de ese momento.

## <a name="step-4-reassign-licenses"></a>Paso 4: Reasignar licencias

### <a name="reassign-a-license-for-one-user"></a>Reasignar una licencia para un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la **página Usuarios activos,** seleccione el usuario al que desea asignar una licencia.

3. En la **pestaña Licencias y aplicaciones,** expanda **Licencias,** seleccione las casillas de las licencias que desea asignar y, a continuación, **seleccione Guardar cambios.**

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Reasignar licencias para varios usuarios a la vez

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione los círculos junto a los nombres de los usuarios para los que desea reemplazar las licencias existentes.

3. En la parte superior, **seleccione Más opciones** (**...**) y, a continuación, elija Administrar licencias **de producto.**

4. Seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.

5. Cambie el botón de alternancia a **la posición On** de los productos que desea asignar a estos usuarios.

    > [!TIP]
    > - Para limitar los servicios que están disponibles para  el usuario, cambie a la posición Desactivado para los servicios que desea quitar para ese usuario. Por ejemplo, si desea que el usuario tenga acceso a todos los servicios disponibles excepto Skype Empresarial Online, puede cambiar el botón de alternancia del servicio Skype Empresarial Online a la posición **Desactivado.**
    > - Cualquier asignación de licencia anterior para los usuarios seleccionados se quitará.

6. En la parte inferior del panel **Reemplazar productos existentes**, seleccione **Reemplazar** \> **Cerrar**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Paso 5: Cancelar suscripciones o quitar licencias que ya no necesite (opcional)

If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).

Si movió solo algunos usuarios a una suscripción diferente, quite las [licencias](../licenses/remove-licenses-from-subscription.md) que ya no necesite.

## <a name="call-support-to-help-you-change-plans"></a>Llamar al soporte técnico para ayudarle a cambiar los planes
[Llamar al soporte técnico de Microsoft](../../admin/contact-support-for-business-products.md)
