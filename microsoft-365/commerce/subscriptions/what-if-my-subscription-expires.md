---
title: ¿Qué pasa con mis datos y mi acceso cuando termina mi suscripción?
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
- Adm_TOC
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Obtenga información sobre lo que ocurre con sus datos cuando expira la suscripción a Microsoft 365 para empresas, está deshabilitado o si cancela.
ms.openlocfilehash: 2852d2fc301d71131a0adb1c277974e2303dd395
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016082"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>¿Qué pasa con mis datos y mi acceso cuando termina la suscripción a Microsoft 365 para empresas?

Si su suscripción termina, ya sea porque expira o porque decide cancelarla, el acceso a los servicios, aplicaciones y datos de clientes de Microsoft 365 va a través de varios Estados antes de que la suscripción esté completamente desactivada o sin *aprovisionar*. Si tiene constancia de esta progresión, estará mejor preparado para devolver la suscripción a un estado activo antes de que sea demasiado tarde o, si está abandonando Microsoft 365, realice una copia de seguridad de los datos antes de que se eliminen en último término.

Lea esta información importante antes de ponerse en contacto [con el soporte técnico de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>¿Qué pasa con los datos cuando expira una suscripción? 

- Si su suscripción expira, pasa por las siguientes fases: caducada/deshabilitada/desaprovisionada. La fase expirada comienza inmediatamente después de que la suscripción ha alcanzado la fecha de finalización.
- Si desactiva la facturación recurrente en su suscripción anual, pasa por las mismas fases que una suscripción expirada. La primera etapa comienza es el aniversario de la suscripción anual, no a partir de la fecha en que se ha desactivado la configuración de facturación recurrente de la suscripción.
- Si cancela la suscripción mensual, se deshabilita inmediatamente (en la fecha de cancelación). Esto significa que los usuarios no tienen acceso a los activos de Microsoft 365 de forma inmediata y solo los administradores tienen acceso a los datos durante los próximos 90 días.

En la siguiente tabla se explica qué se puede esperar cuando expire una suscripción de pago de Microsoft 365 para empresas.

| **Active**                                                             | **Expirado <br/> (30 días \* )**                                                | **Deshabilitado <br/> (90 días \* )**                                               | **Desaprovisionada**                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Datos accesibles para todos los*                                               | *Datos accesibles para todos los*                                                     | *Datos accesibles solo para administradores*                                             | **Se quitan los datos eliminados <br/> de Azure Active Directory, si otros servicios no los usan** |
| Los usuarios tienen acceso normal a Microsoft 365, datos y aplicaciones de Office  | Los usuarios tienen acceso normal a Microsoft 365, archivos y aplicaciones.              | Los usuarios no pueden tener acceso a Microsoft 365, archivos o aplicaciones                        | Los usuarios no pueden tener acceso a Microsoft 365, archivos o aplicaciones                                     |
| Los administradores tienen acceso normal a las aplicaciones de Microsoft 365, datos y Office. | Los administradores pueden acceder al centro de administración                                           | Los administradores pueden tener acceso al centro de administración, pero no pueden asignar licencias a los usuarios.       | Los administradores pueden tener acceso al centro de administración para comprar y administrar otras suscripciones             |
|                                                                        | Los administradores globales o de facturación pueden reactivar la suscripción en el centro de administración | Los administradores globales o de facturación pueden reactivar la suscripción en el centro de administración |                                                                                           |

* En la mayoría de las ofertas, en la mayoría de países y regiones.
  
> [!NOTE]
> **¿Qué son los "datos del cliente"?** Los datos de cliente, tal y como se definen en los [términos del servicio de Microsoft online](https://go.microsoft.com/fwlink/p/?LinkId=613649), se refieren a todos los datos, incluidos los archivos de texto, sonido o imagen proporcionados a Microsoft por el cliente, o en nombre de éste, a través del uso que hace el cliente de los servicios de Microsoft 365. Para obtener más información acerca de la protección de los datos de los clientes, vea [Introducción al portal de confianza de servicios de Microsoft](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal).

## <a name="what-happens-if-i-cancel-a-subscription"></a>¿Qué pasa si cancelo una suscripción?

Si cancela la suscripción antes de la fecha de finalización del término, la suscripción omite el estado caducado y se mueve directamente al Estado deshabilitado, lo que es de 90 días para la mayoría de las suscripciones, en la mayoría de los países y las regiones. Le recomendamos que [realice una copia de seguridad](back-up-data-before-switching-plans.md) de sus datos antes de la cancelación, aunque, como administrador, aún podrá tener acceso a los datos de la organización y hacer una copia de seguridad de ellos mientras la suscripción se encuentre en el estado de deshabilitada. Cualquier dato de cliente que deje fuera de esta copia puede eliminarse 90 días después de la cancelación y se eliminará a más tardar 180 días después de la cancelación.
  
Esto es lo que pasará con usted y sus usuarios si cancela una suscripción.
  
- **Acceso de administrador** Los administradores todavía pueden iniciar sesión y acceder al centro de administración, y comprar otras suscripciones según sea necesario. Como administrador global o de facturación, tiene 90 días para [reactivar la suscripción](reactivate-your-subscription.md) con todos los datos intactos.

- **Acceso de usuario** Los usuarios no podrán usar servicios como OneDrive para la empresa u obtener acceso a datos de clientes (por ejemplo, correo electrónico o documentos de los sitios de grupo). Finalmente, las aplicaciones de Office, como Word y Excel, pasarán a un modo de solo lectura y de funcionalidad reducida y mostrarán [notificaciones de producto sin licencia](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).

Para obtener información sobre cómo cancelar, consulte [cancelar la suscripción](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Si desea que se eliminen los datos de la suscripción antes de que se termine el período típico de deshabilitación, puede [cerrar su cuenta](../close-your-account.md).
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>¿Cuáles son mis opciones si mi suscripción está a punto de caducar?

Mientras una suscripción está activa, usted y sus usuarios finales tienen acceso normal a sus datos, servicios como correo electrónico y OneDrive para la empresa, y aplicaciones de Office. Como administrador, recibirá una serie de notificaciones a través del correo electrónico y en el centro de administración a medida que la suscripción alcanza su fecha de expiración.
  
Antes de que la suscripción llegue a su fecha de expiración, tendrá algunas opciones:

::: moniker range="o365-worldwide"
  
- **Habilite la facturación recurrente para la suscripción.**

  - Si la **facturación recurrente** ya está activada, no es necesario realizar ninguna acción. La suscripción se factura automáticamente y se le cobrará por un año o mes adicional, según su frecuencia de pago actual. Si por algún motivo ha activado la **facturación recurrente** , siempre puede [volver a activar la facturación recurrente](renew-your-subscription.md).

  - Si ha comprado Microsoft 365 apps for Business con una tarjeta de prepago, puede [activar la facturación recurrente](renew-your-subscription.md) para su suscripción.

  - Si es un cliente de licencias por volumen abierto con una suscripción de un año de prepago, póngase en contacto con su partner para comprar una nueva clave de producto. Recibirá las instrucciones por correo electrónico para activar su clave en el [Centro de servicio de licencias por volumen](https://go.microsoft.com/fwlink/p/?LinkID=282016). Para obtener información sobre cómo encontrar un nuevo socio o el socio con el que ha trabajado anteriormente, vea [buscar su partner o revendedor](../../admin/manage/find-your-partner-or-reseller.md).

  - Si tiene aplicaciones de Microsoft 365 para empresas, vea [Manage Recurrent Billing for your subscription](renew-your-subscription.md).

- **Deja que la suscripción expire.**

  - Si está pagando con tarjeta de crédito o factura y no desea continuar la suscripción, [desactive la facturación Recurrent](renew-your-subscription.md). La suscripción termina en su fecha de expiración y puede omitir todas las notificaciones de correo electrónico relacionadas.

  - Si es un cliente de licencias por volumen abierto que trabaja con un partner, puede dejar que la suscripción expire al no realizar ninguna acción.

  - Si es un cliente de Office 365 pequeña empresa Premium y ha pagado por adelantado Office 365 y lo ha activado con una clave de producto, puede dejar que la suscripción expire al no realizar ninguna acción.

- **Cancele antes de que la suscripción expire.** Para obtener más información, consulte [cancelar la suscripción](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Administrar la facturación recurrente de la suscripción.**

  - Si la **facturación recurrente** ya está activada, no es necesario realizar ninguna acción. La suscripción se facturará automáticamente y se le cobrará por un año o mes adicional, según su frecuencia de pago actual. Si por algún motivo ha activado la **facturación recurrente** , siempre puede [volver a activar la facturación recurrente](renew-your-subscription.md).

  - Si ha comprado Microsoft 365 apps for Business con una tarjeta de prepago, puede [activar la facturación recurrente](renew-your-subscription.md) para su suscripción.

  - Si es un cliente de licencias por volumen abierto con una suscripción de un año de prepago, póngase en contacto con su partner para comprar una nueva clave de producto. Recibirá las instrucciones por correo electrónico para activar su clave en el [Centro de servicio de licencias por volumen](https://go.microsoft.com/fwlink/p/?LinkID=282016). Para obtener información sobre cómo encontrar un nuevo socio o el socio con el que ha trabajado anteriormente, vea [buscar su partner o revendedor](../../admin/manage/find-your-partner-or-reseller.md).

  - Si tiene aplicaciones de Microsoft 365 para empresas, consulte [renovar la suscripción](renew-your-subscription.md).

- **Deja que la suscripción expire.**

  - Si está pagando con tarjeta de crédito o factura y no desea continuar la suscripción, [desactive la facturación Recurrent](renew-your-subscription.md). La suscripción expirará en la fecha de expiración y podrá ignorar todas las notificaciones relacionadas que llegan por correo electrónico.

  - Si es un cliente de licencias por volumen abierto que trabaja con un partner, puede dejar que la suscripción expire al no realizar ninguna acción.

  - Si es un cliente de Office 365 pequeña empresa Premium y ha pagado por adelantado Office 365 y lo ha activado con una clave de producto, puede dejar que la suscripción expire al no realizar ninguna acción.

- **Cancele antes de que la suscripción expire.** Para obtener más información, consulte [cancelar la suscripción](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Renueva la suscripción.** Si la **facturación recurrente** ya está activada, no es necesario realizar ninguna acción. La suscripción se facturará automáticamente y se le cobrará por un año o mes adicional, según su frecuencia de pago actual. Si por algún motivo ha activado la **facturación recurrente** , siempre puede [volver a activar la facturación recurrente](renew-your-subscription.md).

- **Deja que la suscripción expire.** Si está pagando con tarjeta de crédito o factura y no desea continuar la suscripción, [desactive la facturación Recurrent](renew-your-subscription.md). La suscripción expirará en la fecha de expiración y podrá ignorar todas las notificaciones relacionadas que llegan por correo electrónico.

- **Cancele antes de que la suscripción expire.** Para obtener más información, consulte [cancelar la suscripción](cancel-your-subscription.md).

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>¿Qué pasa después de que expira la suscripción?
Si deja que la suscripción expire, esta pasa por varias fases antes de eliminarse de forma permanente. Esto le proporcionará, como administrador, tiempo para reactivar si desea continuar el servicio o realizar una copia de seguridad de los datos si decide que ya no desea la suscripción.
  
Esto es lo que puede pasar en cada fase por la que pasa la suscripción.
  
### <a name="state-expired"></a>Estado: caducado
  
::: moniker range="o365-worldwide"

 **Qué es lo que va a pasar:** el estado "expirada" dura 30 días para casi todas las suscripciones, incluidas las suscripciones compradas a través de [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), en la mayoría de los países y regiones. Para productos de licencias por volumen, excepto para Microsoft Open, el estado "expirada" dura 90 días.

::: moniker-end

::: moniker range="o365-germany"

 **Qué es lo que va a pasar:** el estado "expirada" dura 30 días para casi todas las suscripciones, incluidas las suscripciones compradas a través de [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), en la mayoría de los países y regiones. Para productos de licencias por volumen, excepto para Microsoft Open, el estado "expirada" dura 90 días.

::: moniker-end

::: moniker range="o365-21vianet"

 **Qué es lo que va a pasar:** el estado de expirada dura 30 días para casi todas las suscripciones, en la mayoría de los países y las regiones.

::: moniker-end

En este estado, los usuarios tienen acceso normal al portal de Microsoft 365, las aplicaciones de Office y los servicios, como el correo electrónico y SharePoint Online.
  
Como administrador, todavía tiene acceso al centro de administración. No se preocupe: los administradores globales o de facturación pueden [reactivar la suscripción](reactivate-your-subscription.md) y seguir usando Microsoft 365. Si no se reactiva, [realice una copia de seguridad de los datos](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Estado: deshabilitado
  
::: moniker range="o365-worldwide"

 **Qué es lo que va a pasar:** si no reactiva la suscripción mientras esta está en estado de expirada, la suscripción pasará a la fase de estado de deshabilitada, que dura 90 días para casi todas las suscripciones, en la mayoría de los países y las regiones. En el caso de los productos de licencias por volumen, el estado de deshabilitado dura 30 días.

::: moniker-end

::: moniker range="o365-germany"

 **Qué es lo que va a pasar:** si no reactiva la suscripción mientras esta está en estado de expirada, la suscripción pasará a la fase de estado de deshabilitada, que dura 90 días para casi todas las suscripciones, en la mayoría de los países y las regiones. En el caso de los productos de licencias por volumen, el estado de deshabilitado dura 30 días.

::: moniker-end

::: moniker range="o365-21vianet"

 **Qué es lo que va a pasar:** si no reactiva la suscripción mientras esta está en estado de expirada, la suscripción pasará a la fase de estado desactivado, que dura 90 días con casi todas las subscripciones para la mayoría de los países y las regiones.

::: moniker-end

::: moniker range="o365-worldwide"

En esta fase, el acceso se limita de forma significativa. Los usuarios no pueden iniciar sesión ni acceder a servicios como correo electrónico o SharePoint Online. Además, las aplicaciones de Office pasarán al modo de solo lectura y con funcionalidad limitada y mostrarán [notificaciones de producto sin licencia](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). Todavía puede iniciar sesión y acceder al centro de administración, pero no puede asignar licencias a los usuarios. Los datos de cliente, incluidos todos los datos de usuario, el correo electrónico y los archivos de los sitios de grupo, estarán disponibles solo para usted y para los demás administradores.

::: moniker-end

Como administrador global o de facturación, puede [reactivar la suscripción](reactivate-your-subscription.md) y seguir usando Microsoft 365 con todos los datos de cliente intactos. Si elige no reactivar, [haga una copia de seguridad de los datos](back-up-data-before-switching-plans.md).

### <a name="state-deprovisioned"></a>Estado: desaprovisioned
  
 **Qué es lo que va a pasar:** si no reactiva la suscripción mientras esta está en gracia o desactivada, la suscripción quedará con aprovisionamiento anulado.
  
Los administradores y usuarios ya no tienen acceso a los servicios ni aplicaciones de Office incluidos en la suscripción. Todos los datos de los clientes, desde los datos de usuario hasta los documentos y el correo electrónico, se eliminan permanentemente y no se recuperan.
  
A partir de ese momento, no podrá reactivar la suscripción. Sin embargo, como administrador global o de facturación, aún puede tener acceso al centro de administración para administrar otras suscripciones o para comprar nuevas suscripciones para satisfacer sus necesidades empresariales.
  
> [!NOTE]
> Si agrega una nueva suscripción del mismo tipo cuyo aprovisionamiento se ha anulado no se restauran los datos asociados a la suscripción con aprovisionamiento anulado.

### <a name="what-happens-when-my-trial-ends"></a>¿Qué ocurre cuando termina la versión de prueba?

Cuando finalice la versión de prueba, no podrá seguir usando Microsoft 365 de forma gratuita. Tiene algunas opciones:

::: moniker range="o365-worldwide"
- **Compre Microsoft 365.** Cuando la versión de prueba expire, pasa a un período de gracia, lo que le da otros 30 días (para la mayoría de los casos de prueba, en la mayoría de los países y regiones) para comprar Microsoft 365. Para obtener información sobre cómo convertir su versión de prueba en una suscripción de pago, vea [compre Your Trial version of Microsoft 365 for Business](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-germany"
- **Compre Microsoft 365.** Cuando la versión de prueba expire, pasa a un período de gracia, lo que le da otros 30 días (para la mayoría de los casos de prueba, en la mayoría de los países y regiones) para comprar Microsoft 365. Para obtener información sobre cómo convertir su versión de prueba en una suscripción de pago, vea [compre Your Trial version of Microsoft 365 for Business](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-21vianet"
- **Comprar Office 365.** Al expirar la prueba, entrará en un período de gracia que le dará otros 30 días (para la mayoría de las pruebas, en la mayoría de los países y regiones) para comprar Office 365. Para obtener información sobre cómo convertir su versión de prueba en una suscripción de pago, vea [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).

::: moniker-end

- **Extender la versión de prueba.** ¿Necesita más tiempo para probar Microsoft 365? En algunos casos, puede [ampliar la versión de prueba](../extend-your-trial.md).

- **Cancelar la versión de prueba o dejarla expirar.** Si decide no comprar Microsoft 365, puede dejar que la versión de prueba expire o [cancelarla](cancel-your-subscription.md). Realice una copia de seguridad de los datos que desee conservar. Poco después del período de gracia de 30 días, la información y los datos de su cuenta de prueba se eliminan de forma permanente.

> [!NOTE]
> La información de esta página está sujeta a [Aviso de cambio y exención de responsabilidades de la directiva de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=613651). Vuelva a este sitio periódicamente para revisar los cambios.

## <a name="related-articles"></a>Artículos relacionados 

[Cancelar la suscripción](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription)

[Renovar Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription)

[Reactivar la suscripción](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription)