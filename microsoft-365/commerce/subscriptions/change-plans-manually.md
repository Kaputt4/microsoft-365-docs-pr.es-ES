---
title: Cambiar microsoft 365 para planes empresariales manualmente
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
- AdminSurgePortfolio
search.appverid: MET150
description: Cambie las suscripciones manualmente comprando una nueva suscripción y asegurándose de que ambas están enumeradas y activas.
ROBOTS: NOINDEX
ms.date: 03/17/2021
ms.openlocfilehash: 4acc53fd99b9e2c624445f8f724f73766666f13d
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68736329"
---
# <a name="manually-change-microsoft-plans"></a>Cambiar manualmente los planes de Microsoft

## <a name="step-1-decide-how-to-change-plans"></a>Paso 1: Decidir cómo cambiar los planes

La mejor manera de cambiar todos los usuarios de un plan a otro es [usar la pestaña Actualizar](upgrade-to-different-plan.md). A veces esto no es posible. Cambie los planes manualmente en su lugar:

- Si la pestaña **Actualizar** indica que no puede actualizar el plan actual.

- Si, al seleccionar la pestaña **Actualizar** , no aparece el plan que desea.

- Si no desea actualizar todos los usuarios de la misma manera. Algunas empresas necesitan usuarios diferentes suscritos a planes diferentes. Use un cambio manual para esto.

Para continuar con un cambio manual, lea [Paso 2: Comprar una nueva suscripción](#step-2-buy-a-new-subscription) en este tema.

> [!IMPORTANT]
> Si va a cambiar a un plan con menos servicios relacionados con datos que el plan actual (degradación), debe realizar manualmente una copia de seguridad de los datos que desee conservar. Para obtener más información, consulte [Copia de seguridad de datos antes de cambiar de plan](move-users-different-subscription.md).

## <a name="step-2-buy-a-new-subscription"></a>Paso 2: Comprar una nueva suscripción

**¿Ya has comprado?** Si ya tiene una suscripción a la que desea mover usuarios, omita este paso y vaya al [Paso 3: Comprobar la nueva suscripción y las licencias](#step-3-check-your-new-subscription-and-licenses) en este tema.

O

**Compre una nueva suscripción y licencias:** Siga los pasos descritos en [Comprar otra suscripción de Microsoft 365 para empresas](../try-or-buy-microsoft-365.md) para comprar una nueva suscripción.

Asegúrese de comprar una suscripción para la misma organización en la que se encuentran los usuarios. Por ejemplo, compruebe las direcciones de correo electrónico de los usuarios que desea mover. Si sus direcciones de correo electrónico incluyen \@contoso.com, debe comprar una nueva suscripción para contoso.com.
Incluya una licencia para cada usuario que quiera mover.

## <a name="step-3-check-your-new-subscription-and-licenses"></a>Paso 3: Comprobación de la nueva suscripción y las licencias

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.

2. **Compruebe que ambas suscripciones están enumeradas y activas.** La suscripción de la que va a mover usuarios y la suscripción a la que va a mover usuarios deben aparecer juntas. Si la nueva suscripción no está allí cuando se comprueba por primera vez, inténtelo de nuevo más tarde. Compruebe que ambas suscripciones están activas. [La nueva suscripción no aparece o no está activa](#the-new-subscription-isnt-listed-or-isnt-active).

3. **Compruebe que tiene suficientes licencias para cada usuario** . Cada usuario necesita una licencia que coincida con su suscripción. Por lo tanto, si desea mover diez usuarios a Microsoft 365 Empresa Premium, deberá asegurarse de que hay diez licencias disponibles.

4. **¿Necesita más licencias para la nueva suscripción?**
   Vaya a la página **Sus productos** y [compre más licencias](../licenses/buy-licenses.md).

> [¿Y las antiguas licencias?](#what-about-the-old-licenses)

### <a name="the-new-subscription-isnt-listed-or-isnt-active"></a>La nueva suscripción no aparece o no está activa

- **Si compró dos suscripciones y no aparecen aquí**, es posible que se hayan comprado para distintas organizaciones (para dominios diferentes). Las suscripciones no pueden cruzar los límites de la organización.

- **Si sabe que tiene una suscripción adicional** y no aparece aquí o no está activa, [llame al soporte técnico de Microsoft](../../admin/get-help-support.md).

### <a name="what-about-the-old-licenses"></a>¿Y las antiguas licencias?

Las licencias de la suscripción actual se quitarán más adelante; solo pagará las nuevas licencias de usuario a partir de ese momento.

## <a name="step-4-reassign-licenses"></a>Paso 4: Reasignación de licencias

Al actualizar de un plan de Office 365 a un plan de Microsoft 365, debe cambiar las asignaciones de licencia para todos los usuarios. Las licencias no se asignan automáticamente al cambiar los planes manualmente.

### <a name="reassign-a-license-for-one-user"></a>Reasignación de una licencia para un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la página **Usuarios activos** , seleccione el usuario al que desea asignar una licencia.

3. En la pestaña **Licencias y aplicaciones** , expanda **Licencias**, seleccione los cuadros de las licencias que desea asignar y, a continuación, seleccione **Guardar cambios**.

### <a name="reassign-licenses-for-multiple-users-at-once"></a>Reasignar licencias para varios usuarios a la vez

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione los círculos junto a los nombres de los usuarios para los que desea reemplazar las licencias existentes.

3. En la parte superior, seleccione los tres puntos (más acciones) y, a continuación, elija **Administrar licencias de productos**.

4. Seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.

5. Cambie el botón de alternancia a la posición **Activado** para los productos que desea asignar a estos usuarios.

    > [!TIP]
    > - Para limitar qué servicios están disponibles para el usuario, cambie a la posición **Desactivado** de los servicios que desea quitar para ese usuario. Por ejemplo, si desea que el usuario tenga acceso a todos los servicios disponibles excepto Skype Empresarial En línea, puede cambiar el botón de alternancia del servicio Skype Empresarial Online a la posición **Desactivado**.
    > - Cualquier asignación de licencia anterior para los usuarios seleccionados se quitará.

6. En la parte inferior del panel **Reemplazar productos existentes**, seleccione **Reemplazar** \> **Cerrar**.

## <a name="step-5-cancel-subscriptions-or-remove-licenses-that-you-no-longer-need-optional"></a>Paso 5: Cancelar suscripciones o quitar licencias que ya no necesite (opcional)

If you moved all users from one subscription to another, and you no longer need the original subscription, you can [cancel the subscription](cancel-your-subscription.md).

Si ha movido solo algunos usuarios a una suscripción diferente, [quite las licencias](../licenses/buy-licenses.md) que ya no necesite.

## <a name="call-support-to-help-you-change-plans"></a>Llamar al soporte técnico para ayudarle a cambiar los planes

[Llame al soporte técnico de Microsoft](../../admin/get-help-support.md).
