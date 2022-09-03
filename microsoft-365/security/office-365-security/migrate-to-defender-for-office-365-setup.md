---
title: 'Migración a Microsoft Defender para Office 365 fase 2: instalación'
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
- highpri
ms.custom: migrationguides
description: Realice los pasos necesarios para empezar a migrar desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365 protección.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 71ce240865a21eddf89a2ae2676d31d63525442b
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67596388"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-2-setup"></a>Migración a Microsoft Defender para Office 365: fase 2: instalación

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

<br>

|[![Fase 1: Preparación.](../../media/phase-diagrams/prepare.png#lightbox)](migrate-to-defender-for-office-365-prepare.md) <br> [Fase 1: Preparación](migrate-to-defender-for-office-365-prepare.md)|![Fase 2: Configurar.](../../media/phase-diagrams/setup.png) <br> Fase 2: Configuración|[![Fase 3: Incorporación.](../../media/phase-diagrams/onboard.png#lightbox)](migrate-to-defender-for-office-365-onboard.md) <br> [Fase 3: Incorporación](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
||*¡Estás aquí!*||

Bienvenido a **Fase 2: Configuración** de la **[migración a Microsoft Defender para Office 365](migrate-to-defender-for-office-365.md#the-migration-process)**! Esta fase de migración incluye los pasos siguientes:

1. [Creación de grupos de distribución para usuarios piloto](#step-1-create-distribution-groups-for-pilot-users)
2. [Configuración del envío de usuarios para informes de mensajes de usuario](#step-2-configure-user-submission-for-user-message-reporting)
3. [Mantener o crear la regla de flujo de correo SCL=-1](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)
4. [Configuración del filtrado mejorado para conectores](#step-4-configure-enhanced-filtering-for-connectors)
5. [Creación de directivas de protección piloto](#step-5-create-pilot-protection-policies)

## <a name="step-1-create-distribution-groups-for-pilot-users"></a>Paso 1: Creación de grupos de distribución para usuarios piloto

Los grupos de distribución son necesarios en Microsoft 365 para los siguientes aspectos de la migración:

- **Excepciones para la regla de flujo de correo SCL=-1**: quiere que los usuarios piloto obtengan todo el efecto de Defender para Office 365 protección, por lo que necesita que Defender para Office 365 analicen sus mensajes entrantes. Para ello, defina los usuarios piloto en los grupos de distribución adecuados en Microsoft 365 y configure estos grupos como excepciones a la regla de flujo de correo SCL=-1.

  Como se describe en [Onboard Step 2: (Optional) Exempt pilot users from filtering by your existing protection service (Incorporar paso 2: (opcional) Eximir a los usuarios piloto del filtrado por el servicio de protección existente](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service), debe considerar la posibilidad de excluir a estos mismos usuarios piloto del examen por el servicio de protección existente. Eliminar la posibilidad de filtrar por el servicio de protección existente y confiar exclusivamente en Defender para Office 365 es la mejor y más cercana representación de lo que va a suceder una vez completada la migración.

- **Pruebas de características específicas de protección Defender para Office 365**: incluso para los usuarios piloto, no desea activar todo a la vez. El uso de un enfoque preconfigurado para las características de protección que están en vigor para los usuarios piloto facilitará la solución de problemas y el ajuste. Teniendo en cuenta este enfoque, se recomiendan los siguientes grupos de distribución:
  - **Un grupo piloto de datos adjuntos seguros**: por ejemplo, **MDOPilot\_SafeAttachments**
  - **Un grupo piloto de Vínculos seguros**: por ejemplo, **MDOPilot\_SafeLinks**
  - **Un grupo piloto para la configuración de directivas antispam y antispam estándar**: por ejemplo, **MDOPilot\_SpamPhish\_Standard**
  - **Un grupo piloto para la configuración estricta de directivas antispam y anti phishing**: por ejemplo, **MDOPilot\_SpamPhish\_Strict**

Para mayor claridad, usaremos estos nombres de grupo específicos a lo largo de este artículo, pero puede usar su propia convención de nomenclatura.

Cuando esté listo para comenzar las pruebas, agregue estos grupos como excepciones a [la regla de flujo de correo SCL=-1](#step-3-maintain-or-create-the-scl-1-mail-flow-rule). A medida que cree directivas para las distintas características de protección de Defender para Office 365, usará estos grupos como condiciones que definen a quién se aplica la directiva.

**Notas**:

- Los términos Estándar y Estricto proceden de nuestra [configuración de seguridad recomendada](recommended-settings-for-eop-and-office365.md), que también se usan en [las directivas de seguridad preestablecidas](preset-security-policies.md). Lo ideal sería indicarle que defina los usuarios piloto en las directivas de seguridad preestablecidas Estándar y Estricta, pero no podemos hacerlo. ¿Por qué? Porque no puede personalizar la configuración en las directivas de seguridad preestablecidas (en particular, las acciones que se realizan en los mensajes). Durante las pruebas de migración, querrá ver qué Defender para Office 365 haría en los mensajes, comprobar que es lo que quiere que suceda y, posiblemente, ajustar las configuraciones de directiva para permitir o evitar esos resultados.

  Por lo tanto, en lugar de usar directivas de seguridad preestablecidas, va a crear manualmente directivas personalizadas con una configuración muy similar a, pero en algunos casos es diferente de, la configuración de las directivas de seguridad preestablecidas Estándar y Estricta.

- Si desea experimentar con configuraciones que difieren **significativamente** de nuestros valores recomendados Estándar o Estricto, debe considerar la posibilidad de crear y usar grupos de distribución adicionales y específicos para los usuarios piloto en esos escenarios. Puede usar el Analizador de configuración para ver la seguridad de la configuración. Para obtener instrucciones, consulte [Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365](configuration-analyzer-for-security-policies.md).

  Para la mayoría de las organizaciones, el mejor enfoque es empezar con directivas que se alineen estrechamente con nuestra configuración estándar recomendada. Después de tanta observación y comentarios como pueda hacer en el período de tiempo disponible, puede pasar a una configuración más agresiva más adelante. La protección de suplantación y la entrega a la carpeta de Email no deseado frente a la entrega en cuarentena pueden requerir personalización.

  Si usa directivas personalizadas, asegúrese de que se apliquen _antes_ de las directivas que contienen la configuración recomendada para la migración. Si un usuario se identifica en varias directivas del mismo tipo (por ejemplo, anti-phishing), solo se aplica una directiva de ese tipo al usuario (en función del valor de prioridad de la directiva). Para obtener más información, vea [Orden y prioridad de la protección por correo electrónico](how-policies-and-protections-are-combined.md).

## <a name="step-2-configure-user-submission-for-user-message-reporting"></a>Paso 2: Configurar el envío de usuarios para informes de mensajes de usuario

La capacidad de los usuarios para identificar falsos positivos o falsos negativos de Defender para Office 365 es una parte importante de la migración.

Puede especificar un buzón de Exchange Online para recibir mensajes que los usuarios informan como malintencionados o no malintencionados. Para obtener más instrucciones, consulte [Configuración de mensajes notificados por el usuario](user-submission.md). Este buzón puede recibir copias de los mensajes que los usuarios enviaron a Microsoft, o bien el buzón puede interceptar mensajes sin informar de ellos a Microsoft (el equipo de seguridad puede analizar y enviar manualmente los mensajes). Sin embargo, este enfoque de interceptación no permite que el servicio ajuste y aprenda automáticamente.

También debe confirmar que todos los usuarios del piloto tienen instalada en Outlook una aplicación de informes de mensajes compatible con el envío de usuarios. Estas aplicaciones incluyen:

- [Complemento Mensaje de informe](enable-the-report-message-add-in.md)
- [Complemento de suplantación de identidad de informe](enable-the-report-phish-add-in.md)
- Herramientas de informes de terceros compatibles como se describe [aquí](user-submission.md#third-party-reporting-tools-options).

No subestime la importancia de este paso. Los datos de envíos de usuarios le proporcionarán el bucle de comentarios que necesita para comprobar una buena experiencia de usuario final coherente antes y después de la migración. Estos comentarios le ayudan a tomar decisiones de configuración de directiva informadas, así como a proporcionar informes respaldados por datos a la administración de que la migración se realizó sin problemas.

En lugar de basarse en datos respaldados por la experiencia de toda la organización, más de una migración ha dado lugar a especulaciones emocionales basadas en una única experiencia negativa del usuario. Además, si ha estado ejecutando simulaciones de phishing, puede usar los comentarios de los usuarios para informarles cuando vean algo de riesgo que podría requerir investigación.

## <a name="step-3-maintain-or-create-the-scl-1-mail-flow-rule"></a>Paso 3: Mantener o crear la regla de flujo de correo SCL=-1

Dado que el correo electrónico entrante se enruta a través de otro servicio de protección que se encuentra delante de Microsoft 365, es muy probable que ya tenga una regla de flujo de correo (también conocida como regla de transporte) en Exchange Online que establezca el nivel de confianza de correo no deseado (SCL) de todo el correo entrante en el valor -1 (omitir el filtrado de correo no deseado). La mayoría de los servicios de protección de terceros fomentan esta regla de flujo de correo SCL=-1 para los clientes de Microsoft 365 que quieran usar sus servicios.

Si usa algún otro mecanismo para invalidar la pila de filtrado de Microsoft (por ejemplo, una lista de direcciones IP permitidas), se recomienda cambiar al uso de una regla de flujo de correo SCL=-1 **siempre y cuando** todo el correo entrante de Internet en Microsoft 365 provenga del servicio de protección de terceros (ningún correo fluye directamente desde Internet a Microsoft 365).

La regla de flujo de correo SCL=-1 es importante durante la migración por los siguientes motivos:

- Puede usar [el Explorador de amenazas](email-security-in-microsoft-defender.md) para ver qué características de la pila de Microsoft *habrían* actuado en los mensajes sin afectar a los resultados del servicio de protección existente.
- Puede ajustar gradualmente quién está protegido por la pila de filtrado de Microsoft 365 configurando excepciones a la regla de flujo de correo SCL=-1. Las excepciones serán los miembros de los grupos de distribución piloto que se recomiendan más adelante en este artículo.

  Antes o durante la transición del registro MX a Microsoft 365, deshabilitará esta regla para activar la protección completa de la pila de protección de Microsoft 365 para todos los destinatarios de su organización.

Para obtener más información, consulte [Uso de reglas de flujo de correo para establecer el nivel de confianza de correo no deseado (SCL) en los mensajes de Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

**Notas**:

- Si tiene previsto permitir que el correo de Internet fluya a través del servicio de protección existente **y** directamente a Microsoft 365 al mismo tiempo, debe restringir la regla de flujo de correo SCL=-1 (correo que omite el filtrado de correo no deseado) al correo que solo pasa por el servicio de protección existente. No quiere que el correo de Internet no filtrado se desembarque en los buzones de usuario de Microsoft 365.

  Para identificar correctamente el correo que ya ha examinado el servicio de protección existente, puede agregar una condición a la regla de flujo de correo SCL=-1. Por ejemplo:

  - **Para los servicios de protección basada en la nube**: puede usar un valor de encabezado y encabezado único para su organización. Microsoft 365 no examina los mensajes que tienen el encabezado. Microsoft 365 examina los mensajes sin el encabezado
  - **Para dispositivos o servicios de protección locales**: puede usar direcciones IP de origen. Microsoft 365 no examina los mensajes de las direcciones IP de origen. Microsoft 365 examina los mensajes que no proceden de las direcciones IP de origen.

- No dependa exclusivamente de los registros MX para controlar si el correo se filtra. Los remitentes pueden omitir fácilmente el registro MX y enviar correo electrónico directamente a Microsoft 365.

## <a name="step-4-configure-enhanced-filtering-for-connectors"></a>Paso 4: Configuración del filtrado mejorado para conectores

Lo primero que hay que hacer es configurar [el filtrado mejorado para conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) (también conocido como *omitir lista*) en el conector que se usa para el flujo de correo desde el servicio de protección existente a Microsoft 365. Puede usar el [informe Mensajes entrantes](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports) para ayudar a identificar el conector.

El filtrado mejorado para conectores es necesario por Defender para Office 365 para ver de dónde proceden realmente los mensajes de Internet. El filtrado mejorado para conectores mejora en gran medida la precisión de la pila de filtrado de Microsoft (especialmente la [inteligencia de suplantación de identidad](anti-spoofing-protection.md), así como las funcionalidades posteriores a la vulneración en [el Explorador de amenazas](threat-explorer.md) y la [investigación automatizada & Respuesta (AIR).](automated-investigation-response-office.md)

Para habilitar correctamente el filtrado mejorado para conectores, debe agregar las direcciones IP **públicas** de \*\***todos los\*\*** servicios de terceros o los hosts del sistema de correo electrónico local que enrutan el correo entrante a Microsoft 365.

Para confirmar que el filtrado mejorado para conectores funciona, compruebe que los mensajes entrantes contienen uno o ambos encabezados:

- `X-MS-Exchange-SkipListedInternetSender`
- `X-MS-Exchange-ExternalOriginalInternetSender`

## <a name="step-5-create-pilot-protection-policies"></a>Paso 5: Creación de directivas de protección piloto

Al crear directivas de producción, incluso si no se aplican a todos los usuarios, puede probar características posteriores a la vulneración, como [el Explorador de amenazas](threat-explorer.md), y probar la integración de Defender para Office 365 en los procesos del equipo de respuesta de seguridad.

> [!IMPORTANT]
> Las directivas se pueden limitar a usuarios, grupos o dominios. No se recomienda combinar los tres en una directiva, ya que solo los usuarios que coincidan con los tres estarán dentro del ámbito de la directiva. Para las directivas piloto, se recomienda usar grupos o usuarios. Para las directivas de producción, se recomienda usar dominios. Es muy importante comprender que **solo** el dominio de correo electrónico principal del usuario determina si el usuario está dentro del ámbito de la directiva. Por lo tanto, si cambia el registro MX del dominio secundario de un usuario, asegúrese de que su dominio principal también esté cubierto por una directiva.

### <a name="create-pilot-safe-attachments-policies"></a>Creación de directivas de datos adjuntos seguros piloto

[Datos adjuntos seguros](safe-attachments.md) es la característica de Defender para Office 365 más fácil de habilitar y probar antes de cambiar el registro MX. Los datos adjuntos seguros tienen las siguientes ventajas:

- Configuración mínima.
- Muy baja probabilidad de falsos positivos.
- Comportamiento similar a la protección contra malware, que siempre está activada y no se ve afectada por la regla de flujo de correo SCL=-1.

Cree una directiva de datos adjuntos seguros para los usuarios piloto.

Para obtener la configuración recomendada, consulte [Configuración de directivas de datos adjuntos seguros recomendados](recommended-settings-for-eop-and-office365.md#safe-attachments-policy-settings). Tenga en cuenta que las recomendaciones Estándar y Estricta son las mismas. Para crear la directiva, consulte [Configuración de directivas de datos adjuntos seguros](set-up-safe-attachments-policies.md). Asegúrese de usar el grupo **MDOPilot\_SafeAttachments** como condición de la directiva (a quién se aplica la directiva).

> [!NOTE]
> La directiva de seguridad preestablecida **de protección integrada** proporciona protección de datos adjuntos seguros a todos los destinatarios que no están definidos en ninguna directiva de datos adjuntos seguros. Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

### <a name="create-pilot-safe-links-policies"></a>Creación de directivas piloto de vínculos seguros

> [!NOTE]
> No se admiten los vínculos de ajuste o reescritura ya ajustados o reescritos. Si el servicio de protección actual ya encapsula o vuelve a escribir vínculos en mensajes de correo electrónico, debe desactivar esta característica para los usuarios piloto. Una manera de asegurarse de que esto no sucede es excluir el dominio de dirección URL del otro servicio en la directiva vínculos seguros.

Cree una directiva de vínculos seguros para los usuarios piloto. Las posibilidades de falsos positivos en Vínculos seguros también son bastante bajas, pero debe considerar la posibilidad de probar la característica en un número menor de usuarios piloto que los datos adjuntos seguros. Dado que la característica afecta a la experiencia del usuario, debe tener en cuenta un plan para educar a los usuarios.

Para obtener la configuración recomendada, consulte [Configuración de directivas de vínculos seguros recomendados](recommended-settings-for-eop-and-office365.md#safe-links-settings). Tenga en cuenta que las recomendaciones Estándar y Estricta son las mismas. Para crear la directiva, consulte [Configuración de directivas de vínculos seguros](set-up-safe-links-policies.md). Asegúrese de usar el grupo **MDOPilot\_SafeLinks** como condición de la directiva (a quién se aplica la directiva).

> [!NOTE]
> La directiva de seguridad preestablecida **de protección integrada** proporciona protección de vínculos seguros a todos los destinatarios que no están definidos en ninguna directiva de vínculos seguros. Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

### <a name="create-pilot-anti-spam-policies"></a>Creación de directivas piloto contra correo no deseado

Cree dos directivas contra correo no deseado para los usuarios piloto:

- Directiva que usa la configuración estándar. Use el grupo **MDOPilot\_SpamPhish\_Standard** como condición de la directiva (a quién se aplica la directiva).
- Directiva que usa la configuración estricta. Use el grupo **MDOPilot\_SpamPhish\_Strict** como condición de la directiva (a quién se aplica la directiva). Esta directiva debe tener una prioridad más alta (menor número) que la directiva con la configuración Estándar.

Para obtener la configuración estándar y estricta recomendada, consulte [Configuración recomendada de directivas contra correo no deseado](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings). Para crear las directivas, consulte [Configuración de directivas contra correo no deseado](configure-your-spam-filter-policies.md).

### <a name="create-pilot-anti-phishing-policies"></a>Creación de directivas piloto contra suplantación de identidad

Cree dos directivas anti-phishing para los usuarios piloto:

- Directiva que usa la configuración Estándar, con la excepción de las acciones de detección de suplantación, como se describe a continuación. Use el grupo **MDOPilot\_SpamPhish\_Standard** como condición de la directiva (a quién se aplica la directiva).
- Directiva que usa la configuración estricta, con la excepción de las acciones de detección de suplantación, como se describe a continuación. Use el grupo **MDOPilot\_SpamPhish\_Strict** como condición de la directiva (a quién se aplica la directiva). Esta directiva debe tener una prioridad más alta (menor número) que la directiva con la configuración Estándar.

Para las detecciones de suplantación de identidad, la acción Estándar recomendada es **Mover mensaje a las carpetas de Email no deseado de los destinatarios** y la acción estricta recomendada es **Poner en cuarentena el mensaje**. Use la información de inteligencia de suplantación de identidad para observar los resultados. Las invalidaciones se explican en la sección siguiente. Para obtener más información, consulte [Información de inteligencia contra la suplantación de identidad en EOP](learn-about-spoof-intelligence.md).

En el caso de las detecciones de suplantación, omita las acciones estándar y estrictas recomendadas para las directivas piloto. En su lugar, use el valor **No aplicar ninguna acción** para la siguiente configuración:

- **Si el mensaje se detecta como un usuario suplantado**
- **Si el mensaje se detecta como dominio suplantado**
- **Si la inteligencia del buzón detecta un usuario suplantado**

Use la información de suplantación para observar los resultados. Para obtener más información, vea [Información de suplantación en Defender para Office 365](impersonation-insight.md).

Ajustará la protección contra suplantación (ajustará los bloques y permite) y activará cada acción de protección de suplantación para poner en cuarentena o mover los mensajes a la carpeta Junk Email (en función de las recomendaciones Estándar o Estricta). Puede observar los resultados y ajustar su configuración según sea necesario.

Para obtener más información, consulte los siguientes temas:

- [Protección contra la suplantación de identidad](anti-spoofing-protection.md)
- [Configuración de suplantación en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Configure las directivas contra phishing en Defender para Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena**! Ha completado la fase de **instalación** de la [migración a Microsoft Defender para Office 365](migrate-to-defender-for-office-365.md#the-migration-process).

- Pase a [la fase 3: Incorporación](migrate-to-defender-for-office-365-onboard.md).
