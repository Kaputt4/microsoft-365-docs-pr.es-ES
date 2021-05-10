---
title: ¿Qué sucede con mis datos y mi acceso cuando termina mi suscripción?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Obtenga información sobre lo que sucede con sus datos cuando su suscripción de Microsoft 365 para empresas expira, está deshabilitada o la cancela.
ms.openlocfilehash: 45f331fd14abb2f851c8ff84e729b8443a60b59b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297277"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>¿Qué sucede con mis datos y mi acceso cuando termina mi suscripción de Microsoft 365 para empresas?

Si su suscripción finaliza, ya sea porque expira o porque decide cancelarla, el acceso a los servicios, aplicaciones y datos de clientes de Microsoft 365 pasa por varios estados antes de que la suscripción se desactive por completo o se *elimine*. Si está al tanto de esta progresión, estará más preparado para devolver su suscripción a un estado activo antes de que sea tarde o, si decide abandonar Microsoft 365, realizar una copia de seguridad de sus datos antes de que se eliminen finalmente.

Lea esta información importante antes de ponerse en contacto con el [soporte técnico de Microsoft 365](../../business-video/get-help-support.md).
  
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
> **¿Qué son los "datos del cliente"?** Los datos del cliente, tal y como se indica en los [Términos de Microsoft Online Services](https://go.microsoft.com/fwlink/p/?LinkId=613649), hacen referencia a todos los datos, incluidos todos los archivos de texto, sonido e imagen que el cliente, o alguien en su nombre, proporciona a Microsoft a través del uso de los servicios de Microsoft 365. Para obtener más información acerca de la protección de los datos del cliente, vea [Introducción al Portal de confianza de servicios de Microsoft](../../compliance/get-started-with-service-trust-portal.md).

## <a name="what-happens-if-i-cancel-a-subscription"></a>¿Qué pasa si cancelo una suscripción?

Si cancela su suscripción antes de la fecha de finalización del período, la suscripción salta la fase de Expirada y pasa directamente a la fase de Deshabilitada, que dura 90 días para casi todas las suscripciones, en la mayoría de los países y las regiones. Le recomendamos que [realice una copia de seguridad de sus datos](back-up-data-before-switching-plans.md) antes de la cancelación, aunque, como administrador, aún podrá tener acceso a los datos de la organización y hacer una copia de seguridad de ellos mientras la suscripción se encuentre en la fase de Deshabilitada. Cualquier dato de cliente que deje fuera de esta copia puede eliminarse 90 días después de la cancelación y se eliminará a más tardar 180 días después de la cancelación.
  
Esto es lo que pasará con usted y sus usuarios si cancela una suscripción.
  
- **Acceso de administrador** Los administradores aún podrán iniciar sesión y acceder al centro de administración, así como comprar otras suscripciones según sea necesario. Como administrador global o de facturación, tiene 90 días para [reactivar la suscripción](reactivate-your-subscription.md) con todos los datos intactos.

- **Acceso de usuario** Los usuarios no podrán usar servicios como OneDrive para la Empresa, ni tendrán acceso a los datos de clientes, como el correo electrónico o los documentos de los sitios de grupo. Las aplicaciones de Office, como Word y Excel, pasarán al modo de solo lectura con funcionalidad reducida y mostrarán [Notificaciones de producto sin licencia](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx).

Para obtener información sobre cómo cancelar la suscripción, vea [Cancelar su suscripción](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Si quiere que se eliminen los datos de su suscripción antes de que se termine la fase típica de Deshabilitada, puede [cerrar su cuenta](../close-your-account.md).
  
> [!NOTE]
> Si elimina explícitamente una suscripción, omite las fases Expirada y Deshabilitada, y los datos y el contenido de SharePoint Online, incluido OneDrive, se eliminan inmediatamente.

## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>¿Cuáles son mis opciones si mi suscripción está a punto de expirar?

Mientras una suscripción está activa, usted y sus usuarios finales tienen acceso normal a sus datos, los servicios como el correo electrónico y OneDrive para la Empresa, y otras aplicaciones de Office. Como administrador, recibirá una serie de notificaciones a través del correo electrónico en el Centro de administración cuando se aproxime la fecha de expiración de la suscripción.
  
Antes de que la suscripción llegue a su fecha de expiración, tendrá algunas opciones:
  
- **Habilite la facturación periódica para la suscripción.**

  - Si la **Facturación periódica** ya está activada, no tiene que hacer nada. La suscripción se facturará automáticamente y se le cobrará por un año o mes adicional, según su frecuencia de pago actual. Si, por algún motivo, ha desactivado la **Facturación periódica**, siempre puede [volver a activar la Facturación periódica](renew-your-subscription.md).

  - Si ha comprado Aplicaciones de Microsoft 365 para negocios con una tarjeta de prepago, puede [activar la Facturación periódica](renew-your-subscription.md) para su suscripción.

  - Si es un cliente del programa de Licencias por volumen abierto con una suscripción prepago de un año, póngase en contacto con su asociado para comprar una clave de producto nueva. Recibirá las instrucciones por correo electrónico para activar su clave en el [Centro de servicio de licencias por volumen](https://go.microsoft.com/fwlink/p/?LinkID=282016). Para obtener información sobre cómo encontrar un nuevo asociado o uno con el que ha trabajado anteriormente, vea [Busque su asociado o revendedor](../../admin/manage/find-your-partner-or-reseller.md).

  - Si tiene Aplicaciones de Microsoft 365 para negocios, consulte [Administrar la facturación periódica de su suscripción](renew-your-subscription.md).

- **Deje que la suscripción expire.**

  - Si está pagando con tarjeta de crédito o factura y no quiere continuar la suscripción, [desactive la Facturación periódica](renew-your-subscription.md). La suscripción terminará en la fecha de expiración y podrá ignorar todas las notificaciones relacionadas que lleguen por correo electrónico.

  - Si es cliente del programa de Licencias por volumen abierto y trabaja con un asociado, simplemente no haga nada y la suscripción expirará.

  - Si es un cliente de Microsoft 365 Empresa Estándar que ha realizado un prepago de su suscripción y la ha activado con una clave de producto, simplemente no haga nada y la suscripción expirará.

- **Cancele antes de que la suscripción expire.** Para más información, consulte [Cancelar su suscripción](cancel-your-subscription.md).

## <a name="what-happens-after-my-subscription-expires"></a>¿Qué pasa después de que expira la suscripción?

Si deja que la suscripción expire, esta pasará por varias fases antes de eliminarse de forma permanente. Esto, como administrador, le da tiempo de reactivarla si desea continuar con el servicio o de realizar una copia de seguridad de sus datos si decide que ya no desea la suscripción.
  
Esto es lo que puede ocurrir cuando su suscripción pase por cada estado.
  
### <a name="state-expired"></a>Estado: Expirada

 **Qué es lo que va a pasar**: La fase de Expirada dura 30 días para casi todas las suscripciones, incluidas las suscripciones compradas a través de [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), en la mayoría de los países y regiones. Para los productos de licencias por volumen, excepto Microsoft Open, la fase de Expirada dura 90 días.

En este estado, los usuarios tienen acceso normal al portal de Microsoft 365, las aplicaciones de Office y servicios como el correo electrónico y SharePoint Online.
  
Como administrador, tendrá acceso al centro de administración. No se preocupe, los administradores globales o de facturación pueden [reactivar la suscripción](reactivate-your-subscription.md) y seguir usando Microsoft 365. Si no la reactiva, [realice una copia de seguridad de sus datos](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Estado: Deshabilitada

 **Qué es lo que va a pasar**: Si no reactiva la suscripción mientras esta está en la fase de Expirada, la suscripción pasará a la fase de Deshabilitada, que dura 90 días para casi todas las suscripciones, en la mayoría de los países y las regiones. Para productos de licencias por volumen, el estado Expirada dura 30 días.

En esta fase, el acceso se limita de forma significativa. Sus usuarios no podrán iniciar sesión ni tener acceso a servicios como el correo electrónico o SharePoint Online. Además, las aplicaciones de Office pasarán al modo de solo lectura con funcionalidad limitada y mostrarán [Notificaciones de producto sin licencia](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). Aún podrá iniciar sesión y entrar en el centro de administración, pero no podrá asignar licencias a usuarios. Los datos de cliente, incluidos todos los datos de usuario, el correo electrónico y los archivos de los sitios de grupo, estarán disponibles solo para usted y para los demás administradores.

Como administrador global o de facturación, puede [reactivar la suscripción](reactivate-your-subscription.md) y continuar usando Microsoft 365 con todos los datos de cliente intactos. Si decide no reactivarla, [realice una copia de seguridad de sus datos](back-up-data-before-switching-plans.md).

### <a name="state-deleted"></a>Estado: Eliminada
  
 **Qué es lo que va a pasar:** Si no reactiva la suscripción mientras está expirada o deshabilitada, la suscripción se eliminará.
  
Los administradores y usuarios ya no tienen acceso a los servicios ni aplicaciones de Office incluidos en la suscripción. Todos los datos del cliente, desde los datos de usuarios hasta los documentos y correos electrónicos, se eliminarán de forma permanente y no se podrán recuperar de ninguna manera.
  
A partir de ese momento, no podrá reactivar la suscripción. Sin embargo, como administrador global o de facturación, todavía podrá acceder al Centro de administración para administrar otras suscripciones o para comprar nuevas suscripciones que satisfagan las necesidades de su negocio.
  
> [!NOTE]
> - Si agrega una nueva suscripción del mismo tipo de la que ha sido eliminada, no se restauran los datos asociados a la suscripción eliminada.
> - Si se suspende una licencia de Proveedor de soluciones en la nube de Microsoft, no hay ninguna fase de Expirada de 30 días y los servicios se deshabilitan inmediatamente. Los datos se eliminan después de 90 días si el espacio empresarial no se reactiva agregando una nueva licencia.

### <a name="what-happens-when-my-trial-ends"></a>¿Qué ocurre cuando termina la versión de prueba?

Cuando termine la versión de prueba, no podrá continuar usando Microsoft 365 de forma gratuita. Tiene varias opciones:

- **Compre Microsoft 365.** Al expirar la prueba, entrará en la fase de Expirada, que le dará otros 30 días (para la mayoría de las pruebas, en la mayoría de los países y regiones) para comprar Microsoft 365. Para obtener información sobre cómo convertir su versión de prueba en una suscripción de pago, vea [Comprar una suscripción a partir de la evaluación gratuita](../try-or-buy-microsoft-365.md#buy-a-subscription-from-your-free-trial).

- **Extender la versión de prueba.** ¿Necesita más tiempo para probar Microsoft 365? En algunos casos, puede [extender su versión de prueba](../extend-your-trial.md).

- **Cancele la versión de prueba o déjela expirar.** Si decide no comprar Microsoft 365, puede dejar que su versión de prueba expire o [cancelarla](cancel-your-subscription.md). Asegúrese de realizar una copia de seguridad de los datos que desee conservar. Poco después de la fase de Expirada de 30 días, la información y los datos de su cuenta de prueba se eliminan de forma permanente.

> [!NOTE]
> La información de esta página está sujeta a [Aviso de cambio y exención de responsabilidades de la directiva de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=613651). Vuelva a este sitio de forma periódica para revisar cualquier cambio.

## <a name="related-content"></a>Contenido relacionado

[Cancelar su suscripción](./cancel-your-subscription.md) (artículo)\
[Renovar Microsoft 365 para empresas](./renew-your-subscription.md) (artículo)\
[Reactivar su suscripción](./reactivate-your-subscription.md) (artículo)
