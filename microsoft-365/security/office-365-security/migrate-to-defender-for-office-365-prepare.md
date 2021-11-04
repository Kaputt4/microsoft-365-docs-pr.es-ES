---
title: 'Migrar a Microsoft Defender para Office 365 fase 1: Preparar'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: migrationguides
description: Pasos de requisitos previos para migrar desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365 protección.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c079fbe808b59ef95663ae8a5af6b3913db49eb9
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60779129"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-1-prepare"></a>Migrar a Microsoft Defender para Office 365: Fase 1: Preparar

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

<br>

|![Fase 1: Preparar.](../../media/phase-diagrams/prepare.png) <br> Fase 1: Preparación|[![Fase 2: Configuración](../../media/phase-diagrams/setup.png)](migrate-to-defender-for-office-365-setup.md) <br> [Fase 2: Configuración](migrate-to-defender-for-office-365-setup.md)|[![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)](migrate-to-defender-for-office-365-onboard.md) <br> [Fase 3: Incorporación](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
|*¡Estás aquí!*|||

Bienvenido a **la fase 1: Preparar** la migración a Microsoft Defender para **[Office 365](migrate-to-defender-for-office-365.md#the-migration-process)**! Esta fase de migración incluye los siguientes pasos. Primero debe realizar un inventario de la configuración en el servicio de protección existente, antes de realizar cualquier cambio. De lo contrario, puede realizar los pasos restantes en cualquier orden:

1. [Inventario de la configuración en el servicio de protección existente](#inventory-the-settings-at-your-existing-protection-service)
2. [Compruebe la configuración de protección existente en Microsoft 365](#check-your-existing-protection-configuration-in-microsoft-365)
3. [Comprobar la configuración de enrutamiento de correo](#check-your-mail-routing-configuration)
4. [Mover características que modifican mensajes a Microsoft 365](#move-features-that-modify-messages-into-microsoft-365)
5. [Definir experiencias de usuario masivo y correo no deseado](#define-spam-and-bulk-user-experiences)
6. [Identificar y designar cuentas de prioridad](#identify-and-designate-priority-accounts)

## <a name="inventory-the-settings-at-your-existing-protection-service"></a>Inventario de la configuración en el servicio de protección existente

Un inventario completo de la configuración, las reglas, las excepciones, etc. del servicio de protección existente es una buena idea, ya que probablemente no tendrá acceso a la información después de cancelar la suscripción.

**Pero es muy importante que no vuelva a crear automáticamente o arbitrariamente todas las personalizaciones existentes en Defender para Office 365.** En el mejor de los casos, puede introducir opciones de configuración que ya no son necesarias, relevantes o funcionales. Peor aún, algunas de las personalizaciones anteriores podrían crear problemas de seguridad en Defender para Office 365.

Las pruebas y la observación de las capacidades nativas y el comportamiento de Defender para Office 365 determinarán en última instancia las invalidaciones y la configuración que necesites. Puede resultar útil clasificar la configuración del servicio de protección existente en las siguientes categorías:

- **Filtrado de conexión** o contenido: es probable que no necesite la mayoría de estas personalizaciones en Defender para Office 365.
- **Enrutamiento empresarial:** es probable que la mayoría de las personalizaciones que necesite volver a crear caigan en esta categoría. Por ejemplo, puede volver Microsoft 365 esta configuración Exchange reglas de flujo de correo (también conocidas como reglas de transporte), conectores y excepciones para suplantación de inteligencia.

En lugar de mover la configuración antigua a Microsoft 365, se recomienda un enfoque de cascada que implica una fase piloto con una pertenencia de usuario cada vez mayor y una optimización basada en la observación basada en el equilibrio de las consideraciones de seguridad con las necesidades empresariales de la organización.

## <a name="check-your-existing-protection-configuration-in-microsoft-365"></a>Compruebe la configuración de protección existente en Microsoft 365

Como hemos indicado anteriormente, es imposible desactivar por completo todas las características de protección para el correo que se entrega en Microsoft 365, incluso cuando se usa un servicio de protección de terceros. Por lo tanto, no es inusual que una Microsoft 365 tenga al menos algunas características de protección de correo electrónico configuradas. Por ejemplo:

- En el pasado, no usaba el servicio de protección de terceros con Microsoft 365. Es posible que haya usado y configurado algunas características de protección Microsoft 365 que se están ignorando actualmente. Pero esa configuración puede tener efecto a medida que "se gira el marcado" para habilitar las características de protección en Microsoft 365.
- Es posible que tenga adaptaciones Microsoft 365 protección contra falsos positivos (correo bueno marcado como malo) o falsos negativos (correo no permitido) que lo han hecho a través del servicio de protección existente.

Revise las características de protección existentes en Microsoft 365 considere la posibilidad de quitar o simplificar la configuración que ya no es necesaria. Una configuración de regla o directiva que se requería hace años podría poner en riesgo a la organización y crear vacíos involuntarias en la protección.

## <a name="check-your-mail-routing-configuration"></a>Comprobar la configuración de enrutamiento de correo

- Si usa cualquier tipo de enrutamiento complejo (por ejemplo, Transporte de correo [centralizado),](/exchange/transport-options)debe considerar la posibilidad de simplificar el enrutamiento y documentarlo exhaustivamente. Los saltos externos, especialmente Microsoft 365 que ya ha recibido el mensaje, pueden complicar la configuración y la solución de problemas.

- El flujo de correo saliente y de retransmisión está fuera del ámbito de este artículo. Sin embargo, tenga en cuenta que es posible que deba realizar uno o varios de los siguientes pasos:
  - Compruebe que todos los dominios que use para enviar correo electrónico tengan los registros SPF adecuados. Para más información, vea [Configurar SPF para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).
  - Se recomienda encarecidamente configurar el inicio de sesión dkim en Microsoft 365. Para obtener más información, vea [Use DKIM to validate outbound email](use-dkim-to-validate-outbound-email.md).
  - Si no está enrutando correo directamente desde Microsoft 365, debe cambiar ese enrutamiento quitando o cambiando el conector saliente.

- El Microsoft 365 para retransmitir correo electrónico desde los servidores de correo electrónico locales puede ser un proyecto complejo en sí mismo. Un ejemplo sencillo es un pequeño número de aplicaciones o dispositivos que envían la mayoría de sus mensajes a destinatarios internos y no se usan para envíos masivos de correo. Consulte [esta guía para](/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365) obtener más información. Los entornos más amplios tendrán que ser más cuidadosos. El correo electrónico de marketing y los mensajes que podrían ser vistos como correo no deseado por los destinatarios no están permitidos.

- Defender para Office 365 no tiene una característica para agregar informes DMARC. Visite el [catálogo de Microsoft Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog) para ver proveedores de terceros que ofrecen informes DMARC para Microsoft 365.

## <a name="move-features-that-modify-messages-into-microsoft-365"></a>Mover características que modifican mensajes a Microsoft 365

Debe transferir cualquier personalización o características que modifiquen los mensajes de cualquier forma a Microsoft 365. Por ejemplo, el servicio de protección existente agrega una **etiqueta Externa** al asunto o al cuerpo del mensaje de los mensajes de remitentes externos.

Si no deshabilita esta funcionalidad en el servicio de protección existente, puede esperar los siguientes resultados negativos en Microsoft 365:

- DKIM se romperá.
- [La inteligencia de suplantación](anti-spoofing-protection.md) no funcionará correctamente.
- Probablemente obtenga un número alto de falsos positivos (correo bueno marcado como malo).

Para volver a crear esta funcionalidad Microsoft 365, tiene las siguientes opciones:

- La Outlook de llamada de remitente [externo,](https://techcommunity.microsoft.com/t5/exchange-team-blog/native-external-sender-callouts-on-email-in-outlook/ba-p/2250098)junto con las sugerencias de seguridad [de primer contacto.](set-up-anti-phishing-policies.md#first-contact-safety-tip)
- Reglas de flujo de correo (también conocidas como reglas de transporte). Para obtener más información, vea Avisos de declinación de responsabilidades [de mensajes, firmas,](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)pies de página o encabezados de toda la organización en Exchange Online .

## <a name="account-for-any-active-phishing-simulations"></a>Cuenta de cualquier simulación de suplantación de identidad activa

Si tienes simulaciones de suplantación de identidad de terceros activas, debes evitar que Defender identifique los mensajes, vínculos y datos adjuntos como suplantación de identidad para Office 365. Para obtener más información, vea [Configure third-party phishing simulations in the advanced delivery policy](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy).

## <a name="define-spam-and-bulk-user-experiences"></a>Definir experiencias de usuario masivo y correo no deseado

- **Cuarentena frente a entregar a la** carpeta correo no deseado: la respuesta natural y recomendada para los mensajes malintencionados y definitivamente arriesgados es poner en cuarentena los mensajes. Pero, ¿cómo desea que los usuarios controle mensajes menos dañinos, como correo no deseado y correo masivo (también conocido como *correo gris*). ¿Estos tipos de mensajes deben entregarse a las carpetas de correo no deseado del usuario?

  Con nuestra configuración de seguridad estándar, generalmente entregamos estos tipos de mensajes menos riesgosos a la carpeta correo no deseado. Este comportamiento es similar a muchas ofertas de correo electrónico de consumidores, donde los usuarios pueden comprobar si faltan mensajes en su carpeta de correo no deseado y pueden rescatarse ellos mismos. O bien, si el usuario se suscribió intencionadamente a un boletín o correo de marketing, puede optar por cancelar la suscripción o bloquear el remitente de su propio buzón.

  Sin embargo, muchos usuarios empresariales se usan para enviar poco (si hay alguno) en su carpeta correo no deseado. En su lugar, estos usuarios empresariales se usan para comprobar una cuarentena de los mensajes que faltan. La cuarentena presenta problemas de notificaciones de cuarentena, frecuencia de notificación y permisos necesarios para ver y liberar mensajes.

  - Se interrumpirá el correo identificado de claves de dominio (DKIM).
  - [La inteligencia de suplantación](anti-spoofing-protection.md) no funcionará correctamente.
  - Probablemente obtenga un número alto de falsos positivos (correo bueno marcado como malo).

  En última instancia, es su decisión si desea impedir la entrega de correo electrónico a la carpeta correo no deseado en favor de la entrega a la cuarentena. Sin embargo, una cosa es cierta: si la experiencia de Defender para Office 365 es diferente a la que están acostumbrados los usuarios, debe notificarles y proporcionar formación básica. Incorpore los aprendizajes del piloto y asegúrese de que los usuarios están preparados para cualquier nuevo comportamiento para la entrega de correo electrónico.

- **Correo masivo deseado frente al correo masivo** no deseado: muchos sistemas de protección permiten a los usuarios permitir o bloquear el correo masivo por sí mismos. Esta configuración no se migra fácilmente a Microsoft 365, por lo que debe considerar trabajar con VIP y su personal para volver a crear las configuraciones existentes en Microsoft 365.

  Hoy en Microsoft 365 considera que algunos correos masivos (por ejemplo, boletines) son seguros en función del origen del mensaje. El correo de estos orígenes "seguros" actualmente no está marcado como masivo (el nivel de queja masiva o BCL es 0 o 1), por lo que es difícil bloquear globalmente el correo de estos orígenes. Para la mayoría de los usuarios, la solución es pedirles que cancelen la suscripción individual de estos mensajes masivos o que usen Outlook para bloquear al remitente. Sin embargo, a algunos usuarios no les gustará bloquear o cancelar la suscripción de mensajes masivos.

  Las reglas de flujo de correo que filtran correo electrónico masivo pueden ser útiles cuando los usuarios VIP no desean administrar esto por sí mismos. Para obtener más información, vea [Usar reglas de flujo de correo para filtrar correo masivo.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-filter-bulk-mail.md)

## <a name="identify-and-designate-priority-accounts"></a>Identificar y designar cuentas de prioridad

Si la característica está disponible **para** usted, las cuentas de prioridad y las etiquetas de usuario pueden ayudar a identificar los usuarios Microsoft 365 importantes para que se destajen en los informes.  Para obtener más información, vea [Etiquetas de usuario en Microsoft Defender para Office 365](user-tags.md) y Administrar y supervisar cuentas de [prioridad.](/microsoft-365/admin/setup/priority-accounts)

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase **de preparación** de la migración a Microsoft Defender [para Office 365](migrate-to-defender-for-office-365.md#the-migration-process)!

- Continúe con [la fase 2: Configuración](migrate-to-defender-for-office-365-setup.md).
