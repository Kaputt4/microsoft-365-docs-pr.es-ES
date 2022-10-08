---
title: ¿Qué sucede con mis datos y mi acceso cuando termina mi suscripción?
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: sgautam, jmueller
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: Obtenga información sobre lo que sucede con sus datos cuando su suscripción de Microsoft 365 para empresas expira, está deshabilitada o la cancela.
ms.date: 09/16/2021
ms.openlocfilehash: 556d1b1128f774d455f01b9dffa0a74669248b76
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68189063"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>¿Qué sucede con mis datos y mi acceso cuando termina mi suscripción de Microsoft 365 para empresas?

If your subscription ends—either because it expires, or because you decide to cancel—your access to Microsoft 365 services, applications, and customer data go through multiple states before the subscription is fully turned off, or *deleted*. If you are aware of this progression, you'll be better equipped to return your subscription to an active state before it's too late, or—if you're leaving Microsoft 365—back up your data before it is ultimately deleted.

Lea esta información importante antes de ponerse en contacto con el [soporte técnico de Microsoft 365](../../admin/get-help-support.md).

> [!NOTE]
> Para algunas suscripciones, solo podrá cancelar durante un período de tiempo limitado después de comprar o renovar la suscripción. Si la ventana de cancelación ha pasado, desactive la facturación periódica para cancelar la suscripción al final de su término.
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>¿Qué ocurre con los datos cuando una suscripción expira?

- Si su suscripción expira, pasará por las siguientes fases: Expirada / Deshabilitada / Eliminada. La fase de Expirada se inicia inmediatamente después de que la suscripción haya alcanzado su fecha de finalización.
- Si desactiva la facturación periódica en la suscripción anual, esta pasa por las mismas fases que una suscripción expirada. La primera fase empieza en el aniversario de la suscripción anual, no a partir de la fecha en que desactivó la configuración de facturación periódica de la suscripción.
- Si cancela su suscripción mensual, se deshabilitará inmediatamente (en la fecha de cancelación). Esto significa que sus usuarios pierden el acceso a los activos de Microsoft 365 inmediatamente y solo los administradores tendrán acceso a los datos durante los próximos 90 días.

La siguiente tabla muestra qué sucederá cuando expira una suscripción de pago de Microsoft 365 para empresas.

| Activa | Expirada <br/>(30 días\*) | Deshabilitada <br/>(90 días\*) | Eliminada |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Datos accesibles para todos*                                               | *Datos accesibles para todos*                                                     | *Datos accesibles solo para administradores*                                             | **Los datos eliminados<br/>de Azure Active Directory se borran, si no están en uso por otros servicios** |
| Los usuarios tienen acceso normal a Microsoft 365, los archivos y las aplicaciones   | Los usuarios tienen acceso normal a Microsoft 365, los archivos y las aplicaciones              | Los usuarios no pueden acceder a Microsoft 365, los archivos o las aplicaciones                        | Los usuarios no pueden acceder a Microsoft 365, los archivos o las aplicaciones                                     |
| Los administradores tienen acceso normal a Microsoft 365, los datos y las aplicaciones de Office | Los administradores pueden acceder al centro de administración                                           | Los administradores pueden acceder al centro de administración, pero no pueden asignar licencias a usuarios       | Los administradores pueden acceder al centro de administración para comprar y administrar otras suscripciones             |
|                                                                        | Los administradores globales o de facturación pueden reactivar la suscripción en el centro de administración | Los administradores globales o de facturación pueden reactivar la suscripción en el centro de administración |                                                                                           |

*Para la mayoría de las ofertas, en la mayoría de los países y las regiones.
  
> [!NOTE]
>
> **What is "customer data"?** Customer data, as defined in the [Microsoft Online Service Terms](https://www.microsoft.com/en-us/licensing/product-licensing/products), refers to all data, including all text, sound, or image files that are provided to Microsoft by, or on behalf of, the customer through the customer's use of Microsoft 365 services. To learn more about the protection of customer data, see the [Get started with the Microsoft Service Trust Portal](../../compliance/get-started-with-service-trust-portal.md).

## <a name="what-happens-if-i-cancel-a-subscription"></a>¿Qué pasa si cancelo una suscripción?

If you cancel your subscription before its term end date, the subscription skips the Expired stage and moves directly into the Disabled stage, which is 90 days for most subscriptions, in most countries and regions. We recommend that you [back up your data](move-users-different-subscription.md) before canceling, but as an admin, you can still access and back up data for your organization while it is in the Disabled stage. Any customer data that you leave behind may be deleted after 90 days, and will be deleted no later than 180 days after cancellation.
  
Esto es lo que pasará con usted y sus usuarios si cancela una suscripción.
  
- **Admin access** Admins can still sign in and access the admin center, and buy other subscriptions as needed. As a global or billing admin, you have 90 days to [reactivate the subscription](reactivate-your-subscription.md) with all data intact.

- **User access** Your users won't be able to use services like OneDrive for Business, or access customer data—for example, email or documents on team sites. Office applications, like Word and Excel, will eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380).

Para obtener información sobre cómo cancelar la suscripción, vea [Cancelar su suscripción](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Si quiere que se eliminen los datos de su suscripción antes de que se termine la fase típica de Deshabilitada, puede [cerrar su cuenta](../close-your-account.md).
  
> [!NOTE]
>
> Si elimina explícitamente una suscripción, omite las fases Expirada y Deshabilitada, y los datos y el contenido de SharePoint Online, incluido OneDrive, se eliminan inmediatamente.

## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>¿Cuáles son mis opciones si mi suscripción está a punto de expirar?

While a subscription is active, you and your end users have normal access to your data, services like email and OneDrive for Business, and Office applications. As the admin, you'll receive a series of notifications via email and in the admin center as your subscription nears its expiration date.
  
Antes de que la suscripción llegue a su fecha de expiración, tendrá algunas opciones:
  
- **Habilite la facturación periódica para la suscripción.**
  - If **Recurring billing** is already turned on, you don't have to take any action. Your subscription is automatically billed, and you are charged for an additional year or month, depending on your current payment frequency. If for any reason you've turned **Recurring billing** off, you can always [turn Recurring billing back on](renew-your-subscription.md).
  - Si ha comprado Aplicaciones de Microsoft 365 para negocios con una tarjeta de prepago, puede [activar la Facturación periódica](renew-your-subscription.md) para su suscripción.
  - If you're an Open Volume Licensing customer with a prepaid, one-year subscription, contact your partner to purchase a new product key. You'll receive instructions via email to activate your key in the [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). To learn how to find a new partner, or the partner you've worked with in the past, see [Find your partner or reseller](../../admin/manage/find-your-partner-or-reseller.md).
  - Si tiene Aplicaciones de Microsoft 365 para negocios, consulte [Administrar la facturación periódica de su suscripción](renew-your-subscription.md).
- **Deje que la suscripción expire.**
  - If you're paying by credit card or invoice and you don't want to continue your subscription, [turn Recurring billing off](renew-your-subscription.md). Your subscription ends on its expiration date, and you can ignore all related email notifications.
  - Si es cliente del programa de Licencias por volumen abierto y trabaja con un asociado, simplemente no haga nada y la suscripción expirará.
  - Si es un cliente de Microsoft 365 Empresa Estándar que ha realizado un prepago de su suscripción y la ha activado con una clave de producto, simplemente no haga nada y la suscripción expirará.
- **Cancel before the subscription expires.** For details, see [Cancel your subscription](cancel-your-subscription.md).

## <a name="what-happens-after-my-subscription-expires"></a>¿Qué pasa después de que expira la suscripción?

If you let your subscription expire, it goes through multiple states before it is ultimately deleted. This gives you, as the admin, time to reactivate if you want to continue the service, or to back up your data if you decide you no longer want the subscription.
  
Esto es lo que puede ocurrir cuando su suscripción pase por cada estado.
  
### <a name="state-expired"></a>Estado: Expirada

**What to expect:** The Expired stage lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions. For Volume Licensing products, except for Microsoft Open, the Expired stage lasts 90 days.

En este estado, los usuarios tienen acceso normal al portal de Microsoft 365, las aplicaciones de Office y servicios como el correo electrónico y SharePoint Online.
  
As an admin, you still have access to the admin center. Don't worry—global or billing admins can [reactivate the subscription](reactivate-your-subscription.md) and continue using Microsoft 365. If you don't reactivate, [back up your data](move-users-different-subscription.md).
  
### <a name="state-disabled"></a>Estado: Deshabilitada

**What to expect:** If you don't reactivate your subscription while it is in the Expired stage, it moves into a Disabled stage, which lasts for 90 days for most subscriptions, in most countries and regions. For Volume Licensing products, the Disabled stage lasts 30 days.

In this state, your access decreases significantly. Your users can't sign in, or access services like email or SharePoint Online. Office applications eventually move into a read-only, reduced functionality mode and display [Unlicensed Product notifications](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380). You can still sign in and get to the admin center, but can't assign licenses to users. Your customer data, including all user data, email, and files on team sites, is available only to you and other admins.

As a global or billing admin, you can [reactivate the subscription](reactivate-your-subscription.md) and continue using Microsoft 365 with all of your customer data intact. If you choose not to reactivate, [back up your data](move-users-different-subscription.md).

### <a name="state-deleted"></a>Estado: Eliminada
  
**Qué es lo que va a pasar:** Si no reactiva la suscripción mientras está expirada o deshabilitada, la suscripción se eliminará.
  
Admins and users no longer have access to the services or Office applications that came with the subscription. All customer data—from user data to documents and email—is permanently deleted and is unrecoverable.
  
At this point, you can't reactivate the subscription. However, as a global or billing admin, you can still access the admin center to manage other subscriptions, or to buy new subscriptions to meet your business needs.
  
> [!NOTE]
>
> - Si agrega una nueva suscripción del mismo tipo de la que ha sido eliminada, no se restauran los datos asociados a la suscripción eliminada.
> - Si se suspende una licencia de Proveedor de soluciones en la nube de Microsoft, no hay ninguna fase de Expirada de 30 días y los servicios se deshabilitan inmediatamente. Los datos se eliminan después de 90 días si el espacio empresarial no se reactiva agregando una nueva licencia.

### <a name="what-happens-when-my-trial-ends"></a>¿Qué ocurre cuando termina la versión de prueba?

Cuando termine la versión de prueba, no podrá continuar usando Microsoft 365 de forma gratuita. Tiene varias opciones: 

- **Compre Microsoft 365.** Al expirar la prueba, entrará en la fase de Expirada, que le dará otros 30 días (para la mayoría de las pruebas, en la mayoría de los países y regiones) para comprar Microsoft 365. Para obtener información sobre cómo convertir su versión de prueba en una suscripción de pago, vea [Comprar una suscripción a partir de la evaluación gratuita](../try-or-buy-microsoft-365.md#buy-a-subscription-from-your-free-trial).
- **Extender la versión de prueba.** ¿Necesita más tiempo para probar Microsoft 365? En algunos casos, puede [extender su versión de prueba](../extend-your-trial.md).
- **Cancele la versión de prueba o déjela expirar.** Si decide no comprar Microsoft 365, puede dejar que su versión de prueba expire o [cancelarla](cancel-your-subscription.md). Asegúrese de realizar una copia de seguridad de los datos que desee conservar. Poco después de la fase de expiración de 30 días, la información y los datos de la cuenta de prueba se borran de forma permanente.

> [!NOTE]
>
> The information on this page is subject to the [Microsoft Policy Disclaimer and Change Notice](https://go.microsoft.com/fwlink/p/?LinkId=613651). Return to this site periodically to review any changes.

## <a name="related-content"></a>Contenido relacionado

[Cancelar su suscripción](./cancel-your-subscription.md) (artículo)\
[Renovar Microsoft 365 para empresas](./renew-your-subscription.md) (artículo)\
[Reactivar su suscripción](./reactivate-your-subscription.md) (artículo)
