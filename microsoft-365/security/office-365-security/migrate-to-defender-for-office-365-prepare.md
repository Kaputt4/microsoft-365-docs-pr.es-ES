---
title: 'Migración a Microsoft Defender para Office 365 Fase 1: Preparación'
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
- m365solution-mdo-migration
ms.custom: migrationguides
description: Pasos previos para migrar desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365 protección.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7134d1e306de99b3af70a934ec9e9880ea98d268
ms.sourcegitcommit: 00948161a72d8cea8c2baba873743fc4a0e19f90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "66969844"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-1-prepare"></a>Migración a Microsoft Defender para Office 365: Fase 1: Preparación

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

<br>

|![Fase 1: Preparación.](../../media/phase-diagrams/prepare.png) <br> Fase 1: Preparación|[![Fase 2: Configuración](../../media/phase-diagrams/setup.png#lightbox)](migrate-to-defender-for-office-365-setup.md) <br> [Fase 2: Configuración](migrate-to-defender-for-office-365-setup.md)|[![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png#lightbox)](migrate-to-defender-for-office-365-onboard.md) <br> [Fase 3: Incorporación](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
|*¡Estás aquí!*|||

Bienvenido a **Fase 1: Preparación** de la **[migración a Microsoft Defender para Office 365](migrate-to-defender-for-office-365.md#the-migration-process)**! Esta fase de migración incluye los pasos siguientes. Primero debe hacer un inventario de la configuración en el servicio de protección existente, antes de realizar los cambios. De lo contrario, puede realizar los pasos restantes en cualquier orden:

1. [Inventario de la configuración en el servicio de protección existente](#inventory-the-settings-at-your-existing-protection-service)
2. [Comprobación de la configuración de protección existente en Microsoft 365](#check-your-existing-protection-configuration-in-microsoft-365)
3. [Comprobación de la configuración de enrutamiento de correo](#check-your-mail-routing-configuration)
4. [Traslado de características que modifican mensajes a Microsoft 365](#move-features-that-modify-messages-into-microsoft-365)
5. [Definición de experiencias de usuario masivas y de correo no deseado](#define-spam-and-bulk-user-experiences)
6. [Identificación y designación de cuentas prioritarias](#identify-and-designate-priority-accounts)

## <a name="inventory-the-settings-at-your-existing-protection-service"></a>Inventario de la configuración en el servicio de protección existente

Un inventario completo de la configuración, las reglas, las excepciones, etc. del servicio de protección existente es una buena idea, ya que es probable que no tenga acceso a la información después de cancelar la suscripción.

**Sin embargo, es muy importante que no vuelva a crear automáticamente ni arbitrariamente todas las personalizaciones existentes en Defender para Office 365.** En el mejor de los momentos, puede introducir configuraciones que ya no son necesarias, pertinentes o funcionales. En el peor de los casos, algunas de las personalizaciones anteriores podrían realmente crear problemas de seguridad en Defender para Office 365.

Las pruebas y la observación de las funcionalidades nativas y el comportamiento de Defender para Office 365 determinarán en última instancia las invalidaciones y la configuración que necesita. Es posible que le resulte útil clasificar la configuración del servicio de protección existente en las siguientes categorías:

- **Filtrado de conexión o contenido**: es probable que no necesite la mayoría de estas personalizaciones en Defender para Office 365.
- **Enrutamiento empresarial**: es probable que la mayoría de las personalizaciones que necesita volver a crear se incluyan en esta categoría. Por ejemplo, puede volver a crear esta configuración en Microsoft 365 como reglas de flujo de correo de Exchange (también conocidas como reglas de transporte), conectores y excepciones a la inteligencia de suplantación de identidad.

En lugar de mover la configuración antigua ciegamente a Microsoft 365, se recomienda un enfoque en cascada que implique una fase piloto con una pertenencia a usuarios cada vez mayor y un ajuste basado en la observación basado en el equilibrio de las consideraciones de seguridad con las necesidades empresariales de la organización.

## <a name="check-your-existing-protection-configuration-in-microsoft-365"></a>Comprobación de la configuración de protección existente en Microsoft 365

Como se indicó anteriormente, es imposible desactivar por completo todas las características de protección para el correo que se entrega en Microsoft 365, incluso cuando se usa un servicio de protección de terceros. Por lo tanto, no es inusual que una organización de Microsoft 365 tenga configuradas al menos algunas características de protección por correo electrónico. Por ejemplo:

- En el pasado, no usaba el servicio de protección de terceros con Microsoft 365. Es posible que haya usado y configurado algunas características de protección de Microsoft 365 que se están omitiendo actualmente. Sin embargo, esa configuración puede surtir efecto a medida que "activa el marcado" para habilitar las características de protección de Microsoft 365.
- Es posible que tenga adaptaciones en la protección de Microsoft 365 para falsos positivos (correo bueno marcado como incorrecto) o falsos negativos (correo incorrecto permitido) que lo hayan hecho a través del servicio de protección existente.

Revise las características de protección existentes en Microsoft 365 y considere la posibilidad de quitar o simplificar la configuración que ya no es necesaria. Una regla o configuración de directiva necesaria hace años podría poner en riesgo la organización y crear brechas involuntarias en la protección.

## <a name="check-your-mail-routing-configuration"></a>Comprobación de la configuración de enrutamiento de correo

- Si usa cualquier tipo de enrutamiento complejo (por ejemplo, transporte de [correo centralizado](/exchange/transport-options)), considere la posibilidad de simplificar el enrutamiento y documentarlo exhaustivamente. Los saltos externos, especialmente después de que Microsoft 365 ya haya recibido el mensaje, pueden complicar la configuración y la solución de problemas.

- El flujo de correo saliente y de retransmisión está fuera del ámbito de este artículo. Sin embargo, tenga en cuenta que es posible que tenga que realizar uno o varios de los pasos siguientes:
  - Compruebe que todos los dominios que usa para enviar correo electrónico tienen los registros SPF adecuados. Para más información, vea [Configurar SPF para evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md).
  - Se recomienda encarecidamente configurar el inicio de sesión de DKIM en Microsoft 365. Para obtener más información, consulte [Uso de DKIM para validar el correo electrónico saliente](use-dkim-to-validate-outbound-email.md).
  - Si no va a enrutar el correo directamente desde Microsoft 365, debe cambiar ese enrutamiento quitando o cambiando el conector de salida.

- El uso de Microsoft 365 para retransmitir correo electrónico desde los servidores de correo electrónico locales puede ser un proyecto complejo en sí mismo. Un ejemplo sencillo es un pequeño número de aplicaciones o dispositivos que envían la mayoría de sus mensajes a destinatarios internos y no se usan para envíos masivos. Consulte [esta guía](/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365) para obtener más información. Los entornos más amplios tendrán que ser más reflexivos. No se permiten el correo electrónico de marketing y los mensajes que los destinatarios podrían ver como correo no deseado.

- Defender para Office 365 no tiene una característica para agregar informes DMARC. Visite el [catálogo de Microsoft Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog) para ver los proveedores de terceros que ofrecen informes de DMARC para Microsoft 365.

## <a name="move-features-that-modify-messages-into-microsoft-365"></a>Traslado de características que modifican mensajes a Microsoft 365

Debe transferir a Microsoft 365 las personalizaciones o características que modifiquen los mensajes de cualquier manera. Por ejemplo, el servicio de protección existente agrega una etiqueta **Externa** al asunto o al cuerpo del mensaje de mensajes de remitentes externos. Cualquier característica de ajuste de vínculos también provocará problemas con algunos mensajes. Si usa esta característica hoy en día, debe priorizar el lanzamiento de vínculos seguros como alternativa para minimizar los problemas.

Si no desactiva las características de modificación de mensajes en el servicio de protección existente, puede esperar los siguientes resultados negativos en Microsoft 365:

- DKIM se romperá. No todos los remitentes se basan en DKIM, pero los que lo hacen no podrán realizar la autenticación.
- [La inteligencia de suplantación](anti-spoofing-protection.md) de identidad y el paso de ajuste más adelante en esta guía no funcionarán correctamente.
- Probablemente obtendrá un gran número de falsos positivos (un buen correo marcado como malo).

Para volver a crear la identificación del remitente externo en Microsoft 365, tiene las siguientes opciones:

- La [característica de llamada de remitente externo de Outlook](https://techcommunity.microsoft.com/t5/exchange-team-blog/native-external-sender-callouts-on-email-in-outlook/ba-p/2250098), junto con [las primeras sugerencias de seguridad de contactos](set-up-anti-phishing-policies.md#first-contact-safety-tip).
- Reglas de flujo de correo (también conocidas como reglas de transporte). Para obtener más información, consulte [Declinaciones de responsabilidades de mensajes de toda la organización, firmas, pies de página o encabezados en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers).

Microsoft está trabajando con el sector para admitir el estándar de cadena recibida autenticada (ARC) en un futuro próximo. Si desea dejar habilitadas las características de modificación de mensajes en el proveedor de puerta de enlace de correo actual, le recomendamos que se ponga en contacto con ellos para que admitan este estándar.

## <a name="account-for-any-active-phishing-simulations"></a>Cuenta para cualquier simulación de suplantación de identidad activa

Si tiene simulaciones de suplantación de identidad de terceros activas, debe evitar que los mensajes, vínculos y datos adjuntos se identifiquen como suplantación de identidad (phishing) por Defender para Office 365. Para obtener más información, consulte [Configuración de simulaciones de suplantación de identidad de terceros en la directiva de entrega avanzada](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy).

## <a name="define-spam-and-bulk-user-experiences"></a>Definición de experiencias de usuario masivas y de correo no deseado

- **Cuarentena frente a entrega a la carpeta de Email** no deseado: la respuesta natural y recomendada para los mensajes malintencionados y definitivamente peligrosos es poner en cuarentena los mensajes. Pero, ¿cómo desea que los usuarios controlen mensajes menos dañinos, como correo no deseado y correo masivo (también conocido como *correo gris*). ¿Deben entregarse estos tipos de mensajes a las carpetas de Email no deseados del usuario?

  Con nuestra configuración de seguridad estándar, generalmente entregamos estos tipos de mensajes menos peligrosos a la carpeta de Email no deseado. Este comportamiento es similar a muchas ofertas de correo electrónico de consumidor, donde los usuarios pueden comprobar si faltan mensajes en la carpeta de Email no deseados y pueden rescatarlos ellos mismos. O bien, si el usuario se registró intencionadamente para recibir un boletín o correo de marketing, puede optar por cancelar la suscripción o bloquear el remitente para su propio buzón.

  Sin embargo, muchos usuarios empresariales se usan para enviar poco (si existe) correo en su carpeta de Email no deseado. En su lugar, estos usuarios empresariales se usan para comprobar si faltan mensajes en una cuarentena. La cuarentena presenta problemas de notificaciones de cuarentena, frecuencia de notificación y los permisos necesarios para ver y liberar mensajes.

  - Se interrumpirá el correo identificado de claves de dominio (DKIM).
  - [La inteligencia de suplantación de identidad](anti-spoofing-protection.md) no funcionará correctamente.
  - Probablemente obtendrá un gran número de falsos positivos (un buen correo marcado como malo).

  En última instancia, es su decisión si desea impedir la entrega de correo electrónico a la carpeta junk Email en favor de la entrega en cuarentena. Pero una cosa es cierta: si la experiencia en Defender para Office 365 es diferente de la que están acostumbrados los usuarios, debe notificarlos y proporcionar entrenamiento básico. Incorpore aprendizajes del piloto y asegúrese de que los usuarios estén preparados para cualquier nuevo comportamiento para la entrega de correo electrónico.

- **Correo masivo deseado frente a correo masivo no deseado**: muchos sistemas de protección permiten a los usuarios permitir o bloquear el correo electrónico masivo por sí mismos. Esta configuración no se migra fácilmente a Microsoft 365, por lo que debe considerar la posibilidad de trabajar con VIP y su personal para volver a crear sus configuraciones existentes en Microsoft 365.

  En la actualidad, Microsoft 365 considera que algunos correos electrónicos masivos (por ejemplo, boletines de noticias) son seguros en función del origen del mensaje. El correo de estas fuentes "seguras" no está marcado actualmente como masivo (el nivel de queja masiva o BCL es 0 o 1), por lo que es difícil bloquear globalmente el correo de estos orígenes. Para la mayoría de los usuarios, la solución consiste en pedirles que cancelen la suscripción individualmente a estos mensajes masivos o que usen Outlook para bloquear al remitente. Sin embargo, a algunos usuarios no les gustará bloquear o cancelar la suscripción de mensajes masivos.

  Las reglas de flujo de correo que filtran el correo electrónico masivo pueden ser útiles cuando los usuarios vip no desean administrarlo ellos mismos. Para obtener más información, consulte [Uso de reglas de flujo de correo para filtrar el correo electrónico masivo](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-filter-bulk-mail).

## <a name="identify-and-designate-priority-accounts"></a>Identificación y designación de cuentas prioritarias

Si la característica está disponible, **las cuentas de prioridad** y **las etiquetas de usuario** pueden ayudar a identificar a los usuarios importantes de Microsoft 365 para que se destaquen en los informes. Para obtener más información, consulte [Etiquetas de usuario en Microsoft Defender para Office 365](user-tags.md) y [Administrar y supervisar cuentas de prioridad](/microsoft-365/admin/setup/priority-accounts).

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena**! Ha completado la fase **de preparación** de la [migración a Microsoft Defender para Office 365](migrate-to-defender-for-office-365.md#the-migration-process).

- Continúe con [la fase 2: Configuración](migrate-to-defender-for-office-365-setup.md).
