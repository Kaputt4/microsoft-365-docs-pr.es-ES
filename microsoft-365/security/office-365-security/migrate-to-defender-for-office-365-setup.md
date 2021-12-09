---
title: 'Migrar a Microsoft Defender para Office 365 fase 2: Configuración'
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
description: Realice los pasos necesarios para empezar a migrar desde un dispositivo o servicio de protección de terceros a Microsoft Defender para Office 365 protección.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89924fbd30631c42c9a39be7384e642c2755746
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61370661"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-2-setup"></a>Migrar a Microsoft Defender para Office 365- Fase 2: Configuración

**Se aplica a:**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

<br>

|[![Fase 1: Preparar.](../../media/phase-diagrams/prepare.png)](migrate-to-defender-for-office-365-prepare.md) <br> [Fase 1: Preparación](migrate-to-defender-for-office-365-prepare.md)|![Fase 2: Configurar.](../../media/phase-diagrams/setup.png) <br> Fase 2: Configuración|[![Fase 3: Incorporación.](../../media/phase-diagrams/onboard.png)](migrate-to-defender-for-office-365-onboard.md) <br> [Fase 3: Incorporación](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
||*¡Estás aquí!*||

Bienvenido a **la fase 2: Configuración** de la migración a Microsoft Defender para **[Office 365](migrate-to-defender-for-office-365.md#the-migration-process)**! Esta fase de migración incluye los siguientes pasos:

1. [Crear grupos de distribución para usuarios piloto](#step-1-create-distribution-groups-for-pilot-users)
2. [Configurar el envío de usuarios para informes de mensajes de usuario](#step-2-configure-user-submission-for-user-message-reporting)
3. [Mantener o crear la regla de flujo de correo SCL=-1](#step-3-maintain-or-create-the-scl-1-mail-flow-rule)
4. [Configurar filtrado mejorado para conectores](#step-4-configure-enhanced-filtering-for-connectors)
5. [Crear directivas de protección piloto](#step-5-create-pilot-protection-policies)

## <a name="step-1-create-distribution-groups-for-pilot-users"></a>Paso 1: Crear grupos de distribución para usuarios piloto

Los grupos de distribución son Microsoft 365 para los siguientes aspectos de la migración:

- Excepciones para la regla de flujo de correo **SCL=-1:** desea que los usuarios piloto obtengan el efecto completo de Defender para la protección de Office 365, por lo que necesita que Defender examinará sus mensajes entrantes Office 365. Para ello, defina los usuarios piloto en los grupos de distribución adecuados de Microsoft 365 y configure estos grupos como excepciones a la regla de flujo de correo SCL=-1.

  Como se describe en [Onboard Step 2: (Optional) Exempt pilot users from filtering by your existing protection service](migrate-to-defender-for-office-365-onboard.md#step-2-optional-exempt-pilot-users-from-filtering-by-your-existing-protection-service), you should consider exempting these same pilot users from scanning by your existing protection service. Eliminar la posibilidad de filtrar por el servicio de protección existente y confiar exclusivamente en Defender para Office 365 es la mejor y más cercana representación de lo que va a suceder una vez completada la migración.

- **Pruebas de características específicas** de protección Office 365 Defender: incluso para los usuarios piloto, no quieres activar todo a la vez. El uso de un enfoque por fases para las características de protección que están en vigor para los usuarios piloto facilitará la solución de problemas y el ajuste. Con este enfoque en mente, se recomiendan los siguientes grupos de distribución:
  - **Un Caja fuerte piloto de datos adjuntos:** por ejemplo, **MDOPilot \_ SafeAttachments**
  - **Un Caja fuerte piloto vínculos:** por ejemplo, **MDOPilot \_ SafeLinks**
  - **Un grupo piloto para la configuración de** directiva de antispam y anti phishing estándar: por ejemplo, **MDOPilot \_ SpamPhish \_ Standard**
  - **Un grupo piloto para la configuración** estricta de directivas contra correo no deseado y contra suplantación de identidad (por ejemplo, **MDOPilot \_ SpamPhish \_ Strict)**

Para mayor claridad, usaremos estos nombres de grupo específicos en este artículo, pero puede usar su propia convención de nomenclatura.

Cuando esté listo para comenzar las pruebas, agregue estos grupos como excepciones a la regla de flujo de correo [SCL=-1](#step-3-maintain-or-create-the-scl-1-mail-flow-rule). A medida que cree directivas para las distintas características de protección de Defender para Office 365, usará estos grupos como condiciones que definan a quién se aplica la directiva.

**Notas**:

- Los términos Standard y Strict provienen de nuestra [configuración de seguridad recomendada,](recommended-settings-for-eop-and-office365.md)que también se usan en las directivas [de seguridad preestablecidas.](preset-security-policies.md) Lo ideal sería definir los usuarios piloto en las directivas de seguridad preestablecidas Estándar y Estricta, pero no podemos hacerlo. ¿Por qué? Debido a que no puede personalizar la configuración de las directivas de seguridad preestablecidas (en particular, las acciones que se toman en los mensajes o el ajuste de la configuración de protección de suplantación). Durante las pruebas de migración, querrás ver qué haría Defender para Office 365 en los mensajes, comprobar que eso es lo que quieres que suceda y, posiblemente, ajustar las configuraciones de directiva para permitir o impedir esos resultados.

  Por lo tanto, en lugar de usar directivas de seguridad preestablecidas, vas a crear manualmente directivas personalizadas con una configuración muy similar a, pero en algunos casos es diferente de la configuración de las directivas de seguridad preestablecidas Estándar y Estricta.

- Si desea experimentar con  configuraciones que difieren significativamente de nuestros valores recomendados Estándar o Estricto, debe considerar la posibilidad de crear y usar grupos de distribución adicionales y específicos para los usuarios piloto en esos escenarios. Puede usar el Analizador de configuración para ver la seguridad de la configuración. Para obtener instrucciones, consulte [Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365](configuration-analyzer-for-security-policies.md).

  Para la mayoría de las organizaciones, el mejor enfoque es empezar con directivas que se alineen estrechamente con nuestra configuración estándar recomendada. Después de tantas observaciones y comentarios como puedas hacer en el período de tiempo disponible, puedes pasar a una configuración más agresiva más adelante. La protección de suplantación y la entrega a la carpeta correo no deseado frente a la entrega a la cuarentena pueden requerir personalización.

  Si usa directivas personalizadas, asegúrese de  que se aplican antes de las directivas que contienen nuestra configuración recomendada para la migración. Si un usuario se identifica en varias directivas del mismo tipo (por ejemplo, contra la suplantación de identidad), solo se aplica una directiva de ese tipo al usuario (en función del valor de prioridad de la directiva). Para obtener más información, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="step-2-configure-user-submission-for-user-message-reporting"></a>Paso 2: Configurar el envío de usuarios para informes de mensajes de usuario

La capacidad de los usuarios para identificar falsos positivos o falsos negativos de Defender para Office 365 es una parte importante de la migración.

Puede especificar un buzón de Exchange Online para recibir mensajes que los usuarios informan como malintencionados o no malintencionados. Para obtener más instrucciones, vea [Configuración de mensajes notificados por el usuario.](user-submission.md) Este buzón puede recibir copias de los mensajes que los usuarios enviaron a Microsoft o el buzón puede interceptar mensajes sin notificarlos a Microsoft (el equipo de seguridad puede analizar y enviar manualmente los mensajes). Sin embargo, este enfoque de interceptación no permite al servicio ajustar y aprender automáticamente.

También debes confirmar que todos los usuarios del piloto tienen instalada una aplicación de informes de mensajes compatible en Outlook que sea compatible con el envío de usuarios. Estas aplicaciones incluyen:

- [El complemento Mensaje de informe](enable-the-report-message-add-in.md)
- [El complemento Detección de suplantación de identidad de informes](enable-the-report-phish-add-in.md)
- Herramientas de informes de terceros compatibles como se describe [aquí](user-submission.md#third-party-reporting-tools).

No subestime la importancia de este paso. Los datos de los envíos de usuario le darán el bucle de comentarios que necesita para comprobar una buena y coherente experiencia del usuario final antes y después de la migración. Estos comentarios le ayudan a tomar decisiones de configuración de directivas fundamentadas, así como a proporcionar informes con respaldo de datos a su administración que la migración se ha hecho sin problemas.

En lugar de basarse en datos que están a favor de la experiencia de toda la organización, más de una migración ha provocado especulaciones emocionales basadas en una única experiencia negativa del usuario. Además, si ha estado ejecutando simulaciones de suplantación de identidad (phishing), puede usar los comentarios de los usuarios para informarles cuando ven algo arriesgado que puede requerir investigación.

## <a name="step-3-maintain-or-create-the-scl-1-mail-flow-rule"></a>Paso 3: Mantener o crear la regla de flujo de correo SCL=-1

Dado que el correo electrónico entrante se enruta a través de otro servicio de protección que se encuentra delante de Microsoft 365, es muy probable que ya tenga una regla de flujo de correo (también conocida como regla de transporte) en Exchange Online que establece el nivel de confianza de correo no deseado (SCL) de todo el correo entrante en el valor -1 (omitir el filtrado de correo no deseado). La mayoría de los servicios de protección de terceros fomentan esta regla de flujo de correo SCL=-1 para Microsoft 365 clientes que desean usar sus servicios.

Si usa algún otro mecanismo para invalidar la pila de filtrado de Microsoft (por ejemplo, una lista de direcciones  IP permitidos), le recomendamos que cambie a usar una regla de flujo de correo SCL=-1 siempre que todo el correo entrante de Internet en Microsoft 365 proviene del servicio de protección de terceros (ningún correo fluye directamente de Internet a Microsoft 365).

La regla de flujo de correo SCL=-1 es importante durante la migración por los siguientes motivos:

- Puede usar el [Explorador de amenazas](email-security-in-microsoft-defender.md) para  ver qué características de la pila de Microsoft habrían actuado en los mensajes sin afectar a los resultados del servicio de protección existente.
- Puede ajustar gradualmente quién está protegido por la Microsoft 365 de filtrado mediante la configuración de excepciones a la regla de flujo de correo SCL=-1. Las excepciones serán los miembros de los grupos de distribución piloto que recomendamos más adelante en este artículo.

  Antes o durante el recorte del registro MX a Microsoft 365, deshabilitará esta regla para activar la protección completa de la pila de protección de Microsoft 365 para todos los destinatarios de la organización.

Para obtener más información, vea [Use mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online](https://docs.microsoft.comexchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

**Notas**:

- Si tiene previsto permitir que el correo  de Internet fluya a través del servicio de protección existente y directamente a Microsoft 365 al mismo tiempo, debe restringir la regla de flujo de correo SCL=-1 (correo que omite el filtrado de correo no deseado) al correo que solo ha pasado por el servicio de protección existente. No desea que el correo de Internet sin filtrar se desembarque en buzones de usuario en Microsoft 365.

  Para identificar correctamente el correo que ya ha examinado el servicio de protección existente, puede agregar una condición a la regla de flujo de correo SCL=-1. Por ejemplo:

  - **Para los servicios de protección basados** en la nube: puede usar un encabezado y un valor de encabezado que sea exclusivo de su organización. Los mensajes que tienen el encabezado no se examinan Microsoft 365. Los mensajes sin el encabezado se examinan Microsoft 365
  - **Para dispositivos o servicios** de protección locales: puede usar direcciones IP de origen. Los mensajes de las direcciones IP de origen no se examinan Microsoft 365. Los mensajes que no son de las direcciones IP de origen se examinan Microsoft 365.

- No confíe exclusivamente en los registros MX para controlar si el correo se filtra. Los remitentes pueden omitir fácilmente el registro MX y enviar correo electrónico directamente a Microsoft 365.

## <a name="step-4-configure-enhanced-filtering-for-connectors"></a>Paso 4: Configurar el filtrado mejorado para conectores

Lo primero que debe hacer es configurar el filtrado mejorado para conectores [(también](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) conocido como listado de *omitir)* en el conector que se usa para el flujo de correo desde el servicio de protección existente a Microsoft 365. Puede usar el informe [Mensajes entrantes para](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports) ayudar a identificar el conector.

Defender requiere el filtrado mejorado para conectores para Office 365 para ver de dónde provenían realmente los mensajes de Internet. El filtrado mejorado para conectores mejora en gran medida la precisión de la pila de [](threat-explorer.md) filtrado de Microsoft (especialmente la inteligencia de suplantación, [](anti-spoofing-protection.md)así como las capacidades posteriores a la infracción en el Explorador de amenazas y la investigación automatizada & Response [(AIR).](automated-investigation-response-office.md)

Para habilitar correctamente el filtrado mejorado para conectores, debe agregar las direcciones **IP** \* \* **\* \*** públicas de todos los servicios de terceros o hosts del sistema de correo electrónico local que enrute el correo entrante a Microsoft 365.

Para confirmar que el filtrado mejorado para conectores funciona, compruebe que los mensajes entrantes contienen uno o ambos de los siguientes encabezados:

- `X-MS-Exchange-SkipListedInternetSender`
- `X-MS-Exchange-ExternalOriginalInternetSender`

## <a name="step-5-create-pilot-protection-policies"></a>Paso 5: Crear directivas de protección piloto

Al crear directivas de producción, incluso si no se aplican a todos [](threat-explorer.md) los usuarios, puedes probar características posteriores a la infracción como el Explorador de amenazas y probar la integración de Defender para Office 365 en los procesos del equipo de respuesta de seguridad.

> [!IMPORTANT]
> Las directivas se pueden establecer en el ámbito de usuarios, grupos o dominios. No se recomienda mezclar las tres en una directiva, ya que solo los usuarios que coincidan con los tres estarán dentro del ámbito de la directiva. Para las directivas piloto, se recomienda usar grupos o usuarios. Para las directivas de producción, se recomienda usar dominios. Es muy importante comprender  que solo el dominio de correo electrónico principal del usuario determina si el usuario está dentro del ámbito de la directiva. Por lo tanto, si cambia el registro MX para el dominio secundario de un usuario, asegúrese de que su dominio principal también está cubierto por una directiva.

### <a name="create-pilot-safe-attachments-policies"></a>Crear directivas piloto Caja fuerte datos adjuntos

[Caja fuerte datos adjuntos](safe-attachments.md) es la característica defender para Office 365 más fácil de habilitar y probar antes de cambiar el registro MX. Caja fuerte datos adjuntos tiene las siguientes ventajas:

- Configuración mínima.
- Probabilidad extremadamente baja de falsos positivos.
- Comportamiento similar a la protección contra malware, que siempre está en y no se ve afectado por la regla de flujo de correo SCL=-1.

Cree una directiva Caja fuerte datos adjuntos para los usuarios piloto.

Para obtener la configuración recomendada, vea [Recommended Caja fuerte Attachments policy settings](recommended-settings-for-eop-and-office365.md#safe-attachments-policy-settings). Tenga en cuenta que las recomendaciones Estándar y Estricto son las mismas. Para crear la directiva, vea [Configurar Caja fuerte de datos adjuntos](set-up-safe-attachments-policies.md). Asegúrese de usar el grupo **MDOPilot \_ SafeAttachments** como condición de la directiva (a quién se aplica la directiva).

> [!IMPORTANT]
> Hoy en día, no hay ninguna directiva Caja fuerte datos adjuntos predeterminada. Antes de cambiar cualquier registro MX, se recomienda tener una directiva de datos adjuntos Caja fuerte que proteja toda la organización.

### <a name="create-pilot-safe-links-policies"></a>Crear directivas de vínculos Caja fuerte piloto

> [!NOTE]
> No se admite el ajuste o reescritura de vínculos ya ajustados o reescritos. Si el servicio de protección actual ya encapsula o reescribe vínculos en mensajes de correo electrónico, debe desactivar esta característica para los usuarios piloto. Una forma de asegurarse de que esto no sucede es excluir el dominio de dirección URL del otro servicio en la directiva Caja fuerte vínculos.
>
> Caja fuerte protección de vínculos para aplicaciones Office compatibles es una configuración global que se aplica a todos los usuarios con licencia. Puede activarlo o desactivarlo globalmente, no para usuarios específicos. Para obtener más información, [vea Configure Caja fuerte Links protection for Office 365 apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal).

Cree una directiva Caja fuerte links para los usuarios piloto. Las posibilidades de falsos positivos en Caja fuerte Links también son bastante bajas, pero deberías considerar la posibilidad de probar la característica en un número menor de usuarios piloto que Caja fuerte datos adjuntos. Dado que la característica afecta a la experiencia del usuario, debe considerar un plan para educar a los usuarios.

Para obtener la configuración recomendada, vea [Recommended Caja fuerte Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-settings). Tenga en cuenta que las recomendaciones Estándar y Estricto son las mismas. Para crear la directiva, vea [Set up Caja fuerte Links policies](set-up-safe-links-policies.md). Asegúrese de usar el grupo **MDOPilot \_ SafeLinks** como condición de la directiva (a quién se aplica la directiva).

> [!IMPORTANT]
> Hoy en día, no hay ninguna directiva Caja fuerte links predeterminada. Antes de cambiar cualquier registro MX, se recomienda tener una directiva de vínculos Caja fuerte que proteja toda la organización.

### <a name="create-pilot-anti-spam-policies"></a>Crear directivas piloto contra correo no deseado

Crear dos directivas contra correo no deseado para usuarios piloto:

- Directiva que usa la configuración estándar. Use el **grupo MDOPilot \_ SpamPhish \_ Standard** como condición de la directiva (a quién se aplica la directiva).
- Una directiva que usa la configuración Estricta. Use el **grupo MDOPilot \_ SpamPhish \_ Strict** como condición de la directiva (a quién se aplica la directiva). Esta directiva debe tener una prioridad mayor (número inferior) que la directiva con la configuración estándar.

Para obtener la configuración estándar y estricta recomendada, consulte [Configuración de directiva contra correo no deseado recomendada.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings) Para crear las directivas, vea [Configure anti-spam policies](configure-your-spam-filter-policies.md).

### <a name="create-pilot-anti-phishing-policies"></a>Crear directivas piloto contra suplantación de identidad

Crear dos directivas contra la suplantación de identidad (phishing) para usuarios piloto:

- Una directiva que usa la configuración estándar, a excepción de las acciones de detección de suplantación como se describe a continuación. Use el **grupo MDOPilot \_ SpamPhish \_ Standard** como condición de la directiva (a quién se aplica la directiva).
- Una directiva que usa la configuración Strict, a excepción de las acciones de detección de suplantación como se describe a continuación. Use el **grupo MDOPilot \_ SpamPhish \_ Strict** como condición de la directiva (a quién se aplica la directiva). Esta directiva debe tener una prioridad mayor (número inferior) que la directiva con la configuración estándar.

Para las detecciones de suplantación, la acción estándar recomendada es Mover mensaje a las **carpetas** de correo no deseado de los destinatarios y la acción estricta recomendada es Poner en cuarentena **el mensaje**. Use la información de inteligencia suplantación para observar los resultados. Las invalidaciones se explican en la siguiente sección. Para obtener más información, consulte [Información de inteligencia contra la suplantación de identidad en EOP](learn-about-spoof-intelligence.md).

Para las detecciones de suplantación, ignore las acciones Standard y Strict recomendadas para las directivas piloto. En su lugar, use el valor **No aplicar ninguna acción** para la siguiente configuración:

- **Si el mensaje se detecta como un usuario suplantado**
- **Si el mensaje se detecta como dominio suplantado**
- **Si la inteligencia de buzones detecta un usuario suplantado**

Use la información de suplantación para observar los resultados. Para obtener más información, vea [Impersonation insight in Defender for Office 365](impersonation-insight.md).

Ajustarás la protección contra suplantación (ajustará los permisos y los bloques) y activarás cada acción de protección de suplantación para poner en cuarentena o mover los mensajes a la carpeta correo no deseado (según las recomendaciones Estándar o Estricta). Puede observar los resultados y ajustar su configuración según sea necesario.

Para obtener más información, consulte los siguientes temas:

- [Protección contra la suplantación de identidad](anti-spoofing-protection.md)
- [Configuración de suplantación en directivas contra suplantación de identidad](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
- [Configurar directivas contra suplantación de](configure-mdo-anti-phishing-policies.md)identidad en Defender para Office 365 .

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase **de instalación** de la migración a Microsoft Defender [para Office 365](migrate-to-defender-for-office-365.md#the-migration-process)!

- Continúe con [la fase 3: Incorporación](migrate-to-defender-for-office-365-onboard.md).
