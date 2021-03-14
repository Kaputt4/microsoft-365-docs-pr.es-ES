---
title: Seguridad de Office 365, Microsoft Defender para Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Seguridad en Office 365, desde EOP a Defender para Office 365 Planes 1 y 2, Configuraciones de seguridad estándar vs. estrictas y mucho más. Comprenda qué tiene y cómo proteger sus propiedades.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1c6e768098cd59892c2572fb52497c873aef1a3
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711945"
---
# <a name="office-365-security-overview"></a>Información general sobre la Seguridad de Office 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)


En este artículo, se presentan las nuevas propiedades de seguridad en la nube. Ya sea que forme parte de un Centro de operaciones de seguridad, es un Administrador de seguridad nuevo en el espacio o quiera hacer un repaso, puede empezar por aquí.

> [!CAUTION]
> Si usa **Outlook.com**, **Microsoft 365 Familia** o **Microsoft 365 Personal** y necesita información sobre *Vínculos seguros* o *Datos adjuntos seguros*, ***haga clic en este vínculo***: [Seguridad avanzada de Outlook.com para los suscriptores Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Detalles de la seguridad de Office 365

Todas las suscripciones de Office 365 cuentan con funcionalidades de seguridad. Los objetivos y acciones que puede realizar dependen del foco de las diferentes suscripciones. En la seguridad de Office 365, existen tres servicios (o productos) de seguridad principales vinculados al tipo de suscripción:

1. Exchange Online Protection (EOP)
1. Microsoft Defender para Office 365 Plan 1 (Defender para Office P1)
1. Microsoft Defender para Office 365 Plan 2 (Defender para Office P2)

> [!NOTE]
> Si compró la suscripción y necesita desplegar las características de seguridad *en este momento*, siga los pasos del artículo [Protegerse contra amenazas](protect-against-threats.md). Si es la primera vez que usa su suscripción y le gustaría conocer su licencia antes de empezar, examine Facturación > Sus productos en el [Centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

La seguridad de Office 365 se fundamenta sobre las principales protecciones que ofrece EOP. EOP está presente en todas las suscripciones en las que se puedan encontrar buzones de Exchange Online (recuerde, todos los productos de seguridad que se analizan aquí están basados en la nube).

Puede que esté acostumbrado a ver estos tres componentes de esta manera:

|EOP|Microsoft Defender para Office 365 P1|Microsoft Defender para Office 365 P2|
|---|---|---|
|Evita ataques generales conocidos basados en el volumen.|Protege al correo electrónico y a la colaboración de la vulnerabilidad de día cero contra los ataques de malware y suplantación de identidad (phish) que ponen en peligro al correo electrónico empresarial |Agrega investigación, búsqueda y respuesta después de la vulneración, así como automatización y simulación (para el aprendizaje).|
|

En cuanto a la arquitectura, podemos imaginar las piezas como capas acumulativas de seguridad, cada una con un énfasis de seguridad. Más resultados similares:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP y Microsoft Defender para Office 365 y sus relaciones entre sí con énfasis de servicio, incluida una nota para la autenticación de correo electrónico.":::

Aunque cada uno de estos servicios destaca un objetivo entre Proteger, Detectar, Investigar y Responder, ***todos** _ los servicios pueden llevar a cabo_ *_cualquiera_** de los objetivos de proteger, detectar, investigar y responder.

El núcleo de la seguridad de Office 365 es la protección EOP. Microsoft Defender para Office 365 P1 contiene EOP. Defender para Office 365 P2 contiene P1 y EOP. La estructura es acumulativa. Es por ello que, al configurar este producto, debería empezar con EOP y continuar hasta Defender para Office 365.

Aunque la configuración de la autenticación de correo electrónico se produce en un DNS público, es importante configurar esta característica para ayudar a evitar la suplantación electrónica. *Si tiene EOP,* ***debe [configurar la autenticación de correo electrónico](email-validation-and-authentication.md)***.

Si tiene Office 365 E3 o inferior, tiene EOP, pero con la opción de comprar Defender para Office 365 P1 de forma independiente a través de la actualización. Si tiene Office 365 E5, ya tiene Defender para Office 365 P2.

> [!TIP]
> Si su suscripción no es de Office 365 E3 ni E5, igualmente puede comprobar si tiene la opción de actualizar a Microsoft Defender para Office 365 P1. Si está interesado, [esta página web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) enumera las suscripciones elegibles para la actualización de Microsoft Defender para Office 365 P1 (verifique el final de la página para ver las condiciones).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>La escalera de seguridad de Office 365 desde EOP hasta Microsoft Defender para Office 365

![El énfasis de seguridad de EOP y Microsoft Defender para Office 365 incluye desde Proteger y Detectar, hasta Investigar y Responder. La configuración de autenticación del correo electrónico (al menos DKIM y DMARC) debe ajustarse para EOP y versiones posteriores.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Obtenga más información en estas páginas: [Exchange Online Protection](exchange-online-protection-overview.md) y [Defender para Office 365](office-365-atp.md).

La ventaja que representa agregar los planes de Microsoft Defender para Office 365 para la administración de amenazas exclusiva de EOP puede ser difícil de saber a primera vista. Para ayudarle a saber si una ruta de actualización es adecuada para su organización, revisemos las capacidades de cada producto en lo que respecta a:

- prevención y detección de amenazas
- investigación
- respuesta

comenzando por **Exchange Online Protection**:
<p>

|Prevención/detección|Investigación|Respuesta|
|---|---|---|
|Entre las tecnologías se incluyen:<ul><li>correo no deseado</li><li>suplantación de identidad</li><li>malware</li><li>correo masivo</li><li>inteligencia contra la suplantación de identidad</li><li>detección de suplantación</li><li>Cuarentena del administrador</li><li>Entregas de usuarios y administradores de Falsos positivos y Falsos negativos</li><li>Permitir/bloquear direcciones URL y archivos</li><li>Informes</li></u1>|<li>Búsqueda en el registro de auditoría</li><li>Seguimiento de mensajes</li>|<li>Purga automática (ZAP)</li><li>Refinamiento y pruebas de las listas de permitidos y bloqueados</li>|
|

Si desea profundizar en EOP, **[vaya a este artículo](exchange-online-protection-overview.md)**.

Como estos productos son acumulativos, si evalúa Microsoft Defender para Office 365 P1 y decide suscribirse, se le agregarán estas capacidades.

Ganancias con **Defender para Office 365, Plan 1** (hasta la fecha):
<p>

|Prevención/detección|Investigación|Respuesta|
|---|---|---|
|Las tecnologías incluyen todo lo de EOP además de:<u1><li>Datos adjuntos seguros</li><li>Vínculos seguros<li>Protección de Microsoft Defender para Office 365 para cargas de trabajo (p. ej. SharePoint Online y OneDrive para la Empresa)</li><li>Protección al momento del clic en correos electrónicos, clientes de Office y Teams</li><li>Protección contra phishing en Defender para Office 365</li><li>Protección contra la suplantación de usuario y de dominio</li><li>Alertas y API de integración SIEM para las alertas</li>|<li>API de integración SIEM para la detección</li><li>**Herramienta de detecciones en tiempo real**</li><li>Seguimiento de URL</li>|<li>Igual</li></u1>

Por lo tanto, Microsoft Defender para Office 365 P1 amplía el aspecto de la ***prevención** _ y añade formas adicionales de _*_detección_**.

Microsoft Defender para Office 365 P1 también añade **Detecciones en tiempo real** para hacer investigaciones. El nombre de esta herramienta de búsqueda de amenazas está en negrita porque tenerla es una forma de *saber* que tiene Defender para Office 365 P1. No está disponible en Defender para Office 365 P2.

Ganancias con **Defender para Office 365, Plan 2** (hasta la fecha):
<p>

|Prevención/detección|Investigación|Respuesta|
|---|---|---|
|Las tecnologías incluyen todo lo de EOP y Microsoft Defender para Office 365 P1, además de:<u1><li>Igual</li>|<li>**Explorador de amenazas**</li><li>Rastreadores de amenazas</li><li>Vistas de la campaña</li>|<li>Investigación y respuesta automatizadas (AIR)</li><li>AIR desde el Explorador de amenazas</li><li>AIR para usuarios en peligro</li><li>API de integración SIEM para investigaciones automatizadas</li>

Por lo tanto, Microsoft Defender para Office 365 P2 amplía el aspecto de ***investigación y respuesta*** y añade un nuevo punto de seguridad a la búsqueda. Automatización.

En Microsoft Defender para Office 365 P2, la herramienta principal de búsqueda se denomina **Explorador de amenazas** en lugar de Detecciones en tiempo real. Si ve el Explorador de amenazas al ir al Centro de seguridad, está en Microsoft Defender para Office 365 P2.

Para obtener más información sobre Microsoft Defender para Office 365 P1 y P2, **[vaya a este artículo](office-365-atp.md)**.

> [!TIP]
> EOP y Microsoft Defender para Office 365 también son diferentes en cuanto a los usuarios finales. En EOP y Defender para Office 365 P1, el foco está en la *conciencia*, por lo que ambos servicios incluyen el *Complemento de Outlook para denunciar mensajes* con el que los usuarios pueden informar de correos electrónicos sospechosos para su análisis. <p> En Defender para Office 365 P2 (que contiene todo lo de EOP y P1), el foco cambia a *profundizar el conocimiento* de los usuarios finales, por lo que el Centro de operaciones de seguridad tiene acceso a la eficaz herramienta del *Simulador de amenazas* y a las métricas del usuario final que proporciona.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Hoja de características clave de Microsoft Defender para Office 365 Plan 1 vs. Plan 2

Esta referencia rápida le ayudará a comprender qué funcionalidades se incluyen con cada suscripción de Microsoft Defender para Office 365. La combinación de sus conocimientos de las características de EOP puede ayudar a los responsables de tomar de decisiones empresariales a determinar qué versión de Microsoft Defender para Office 365 cubre mejor sus necesidades.

|Defender para Office 365 Plan 1|Defender para Office 365 Plan 2|
|---|---|
|Funcionalidades de configuración, protección y detección: <ul><li>[Archivos adjuntos seguros](atp-safe-attachments.md)</li><li>[Vínculos seguros](atp-safe-links.md)</li><li>[Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Protección contra phishing en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecciones en tiempo real](threat-explorer.md)</li></ul>|Capacidades del Plan 1 de Defender para Office 365 <p> --- además --- <p> Funcionalidades de automatización, investigación, corrección y educación: <ul><li>[Rastreadores de amenazas](threat-trackers.md)</li><li>[Explorador de amenazas](threat-explorer.md)</li><li>[Investigación y respuesta automatizadas](office-365-air.md)</li><li>[Simulador de ataque](attack-simulator.md)</li></ul>|
|

- El Plan 2 de Microsoft Defender para Office 365 está incluido en Office 365 E5, Office 365 A5 y Microsoft 365 E5.

- El Plan 1 de Microsoft Defender para Office 365 está incluido en Microsoft 365 Empresa Premium.

- El Plan 1 de Microsoft Defender para Office 365 y el Plan 2 de Microsoft Defender para Office 365 están disponibles como complementos para determinadas suscripciones. Para obtener más información, consulte [Disponibilidad de características en los planes de Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- La característica [Documentos seguros](safe-docs.md) solo está disponible para los usuarios con las licencias de Microsoft 365 E5 o Seguridad de Microsoft 365 E5 (no se incluye en los planes de Microsoft Defender para Office 365).

- Si su suscripción actual no incluye Microsoft Defender para Office 365 y quiere tenerlo, [contacte al departamento de ventas para iniciar un periodo de prueba](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) y descubra cómo funciona Microsoft Defender para Office 365 en su organización.

> [!TIP]
> ***Sugerencia de Insider** _. Puede usar la tabla de contenido de docs.microsoft.com para obtener información sobre EOP y sobre Microsoft Defender para Office 365. Vuelva a la página [Información general de seguridad de Office 365](index.md)y verá la tabla de contenido en la barra lateral. Comienza con la Implementación (lo que incluye la migración) y después continúa con la prevención, la detección, la investigación y la respuesta. <p> Esta estructura está dividida de modo que los temas de _ *Administración de seguridad** están seguidos por los temas de **Operaciones de seguridad**. Si es un miembro nuevo en cualquier rol de trabajo, use el vínculo de esta sugerencia y sus conocimientos de la tabla de contenido para ayudarle a conocer el espacio. No olvide usar los *vínculos de comentarios* y *calificar los artículos* sobre la marcha. Los comentarios nos ayudan a mejorar lo que le ofrecemos.

## <a name="where-to-go-next"></a>Acciones siguientes

Si es un Administrador de seguridad, es posible que deba configurar DKIM o DMARC para su correo. Es posible que desee implementar valores de seguridad "estrictos" para los usuarios con prioridad o bien, ver las novedades del producto. O, si forma parte de Operaciones de seguridad, es posible que desee aprovechar las Detecciones en tiempo real o el Explorador de amenazas para investigar y responder o bien, entrenar al usuario final en la detección con el Simulador de ataques. Cual sea el caso, estas son algunas recomendaciones adicionales sobre lo que puede hacer a continuación.

[Autenticación de correo electrónico, incluyendo SPF, DKIM y DMARC (con vínculos para configurar los tres)](email-validation-and-authentication.md)

[Ver las configuraciones recomendadas específicas](recommended-settings-for-eop-and-office365-atp.md) y [usar los valores recomendados preestablecidos para configurar las directivas de seguridad rápidamente](preset-security-policies.md)

Póngase al día con las [Novedades de Microsoft Defender para Office 365 (que incluye los desarrollos de EOP)](whats-new-in-office-365-atp.md)

[Usar el Explorador de amenazas o las Detecciones en tiempo real](threat-explorer.md)

Usar el [Simulador de ataques de Microsoft Defender para Office 365](attack-simulator.md)
