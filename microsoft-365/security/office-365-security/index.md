---
title: Office 365 Security, Microsoft defender para Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Seguridad en Office 365, de EOP a defender para Office 365 planes 1 y 2, configuraciones de seguridad estándar frente a estrictas y mucho más. Comprenda lo que tiene y cómo proteger sus propiedades.
ms.openlocfilehash: 008488149a403fdafef9de0b0f64a9a43616debe
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357760"
---
# <a name="office-365-security-overview"></a>Introducción a la seguridad de Office 365

En este artículo se presentan sus nuevas propiedades de seguridad en la nube. Tanto si forma parte de un centro de operaciones de seguridad, es un administrador de seguridad que tiene un nuevo espacio o desea un actualizador, comencemos.

> [!CAUTION]
> Si está usando **Outlook.com**, **Microsoft 365 Family** o **Microsoft 365 personal**, y necesita *vínculos seguros* o información de *datos adjuntos seguros* , ***haga clic en este vínculo** _: [Advanced Outlook.com Security for Microsoft 365 Subscribers](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Office 365 Security spelled out

Todas las suscripciones a Office 365 incluyen capacidades de seguridad. Los objetivos y las acciones que puede realizar dependen del foco de estas suscripciones diferentes. En la seguridad de Office 365, hay tres principales servicios (o productos) de seguridad asociados a su tipo de suscripción:

1. Exchange Online Protection (EOP)
1. Microsoft defender para Office 365 plan 1 (defender para Office P1)
1. Microsoft defender para Office 365 plan 2 (defender para Office P2)

> [!NOTE]
> Si compró la suscripción y necesita implementar las características de seguridad _right ahora *, vaya a los pasos del artículo [proteger contra amenazas](protect-against-threats.md) . Si no está familiarizado con su suscripción y le gustaría conocer su licencia antes de empezar, explore la facturación > sus productos en el [centro de administración de Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

Office 365 Security se basa en las protecciones principales que ofrece EOP. EOP está presente en cualquier suscripción en la que se puedan encontrar buzones de correo de Exchange Online (Recuerde que todos los productos de seguridad que se describen aquí están basados en la nube).

Es posible que esté acostumbrado a ver estos tres componentes tratados de esta manera:

|EOP|Microsoft defender para Office 365 P1|Microsoft defender para Office 365 P2|
|---|---|---|
|Evita los ataques de gran volumen, basados en volumen y conocidos.|Protege el correo electrónico y la colaboración de malware de día cero, phish y compromiso de correo electrónico empresarial.|Agrega investigación, caza y respuesta posteriores a la infracción, así como automatización y simulación (para formación).|
|

Pero, en términos de arquitectura, comencemos a pensar en cada una de las partes como capas acumulativas de seguridad, cada una con un énfasis en la seguridad. Más similar a esto:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP y Microsoft defender para Office 365 y sus relaciones entre sí con énfasis en el servicio, incluida una nota para la autenticación de correo electrónico.":::

Aunque cada uno de estos servicios enfatiza un objetivo entre la protección, la detección, la investigación y la respuesta, ***All** _ los servicios pueden llevar a cabo _*_cualquiera_*_ de los objetivos de protección, detección, investigación y respuesta.

El núcleo de la seguridad de Office 365 es la protección EOP. Microsoft defender para Office 365 P1 contiene EOP. Defender para Office 365 P2 contiene P1 y EOP. La estructura es acumulativa. Por eso, al configurar este producto, debe empezar con EOP y trabajar con defender para Office 365.

Aunque la configuración de la autenticación de correo electrónico tiene su propio DNS público, es importante configurar esta característica para ayudar a defender contra la suplantación de identidad. _Si tiene EOP, * ***debe configurar la [autenticación de correo electrónico](email-validation-and-authentication.md)**_.

Si tiene un Office 365 E3, o inferior, tiene EOP, pero con la opción de comprar un defensor independiente para Office 365 P1 a través de la actualización. Si tiene Office 365 E5, ya tiene defender para Office 365 P2.

> [!TIP]
> Si su suscripción no es de Office 365 E3 o E5, puede seguir comprobando si tiene la opción de actualizar a Microsoft defender para Office 365 P1. Si está interesado, [esta página web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) muestra las suscripciones elegibles para la actualización de Microsoft defender para Office 365 P1 (consulte el final de la página para obtener la impresión precisa).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>La escalera de seguridad de Office 365 de EOP a Microsoft defender para Office 365

![EOP y Microsoft defender para Office 365 y su énfasis en la seguridad, al ir de proteger y detectar para investigar y responder. La configuración de autenticación de correo electrónico (por lo menos DKIM y DMARC) debe configurarse para EOP y superior.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Obtenga información sobre estas páginas: [Exchange Online Protection](exchange-online-protection-overview.md)y [Defender para Office 365](office-365-atp.md).

Lo que hace que se agregue Microsoft defender para Office 365 planes una ventaja para la administración de amenazas pura de EOP puede ser difícil de apreciar a primera vista. Para ayudar a ordenar si una ruta de actualización es adecuada para su organización, veamos las capacidades de cada producto cuando se trata de:

- prevención y detección de amenazas
- investigar
- actuar

a partir de _ * Exchange Online Protection * *:
<p>

|Prevenir o detectar|Investigar|Respuesta|
|---|---|---|
|Entre las tecnologías se incluyen:<ul><li>correo no deseado</li><li>conseguir</li><li>software</li><li>correo masivo</li><li>inteligencia de identidad</li><li>detección de suplantación</li><li>Cuarentena de administrador</li><li>Administradores y envíos de usuarios de falsos positivos y falsos negativos</li><li>Permitir o bloquear para direcciones URL y archivos</li><li>Informes</li></u1>|<li>Búsqueda de registros de auditoría</li><li>Seguimiento de mensajes</li>|<li>Depuración automática de cero horas (ZAP)</li><li>Refinamiento y pruebas de las listas de permitidos y bloqueados</li>|
|

Si desea profundizar en EOP, vaya **[a este artículo](exchange-online-protection-overview.md)**.

Como estos productos son acumulativos, si evalúa Microsoft defender para Office 365 P1 y decide suscribirse a él, agregará estas capacidades.

Ganancias con **defender para Office 365, plan 1** (hasta la fecha):
<p>

|Prevenir o detectar|Investigar|Respuesta|
|---|---|---|
|Las tecnologías incluyen todo en EOP más:<u1><li>Datos adjuntos seguros</li><li>Vínculos seguros<li>Protección 365 de Microsoft defender para Office para cargas de trabajo (por ejemplo, SharePoint Online, Teams, OneDrive para la empresa)</li><li>Protección del tiempo de clic en el correo electrónico, los clientes de Office y los equipos</li><li>anti-phishing en defender para Office 365</li><li>Protección de suplantación de usuarios y dominios</li><li>Alertas e integración de la API de SIEM para alertas</li>|<li>API de integración de SIEM para detecciones</li><li>**Herramienta de detección de tiempo real**</li><li>Seguimiento de dirección URL</li>|<li>Mismo</li></u1>

Por lo tanto, Microsoft defender para Office 365 P1 se expande en el lado **_prevención_* de la casa y agrega otras formas de _*_detección_*_.

Microsoft defender para Office 365 P1 también agrega _ *detecciones en tiempo real** para investigaciones. El nombre de esta herramienta de búsqueda de amenazas está en negrita porque es evidente que es *consciente* de que tiene defender para Office 365 P1. No aparece en defender para Office 365 P2.

Ganancias con **defender para Office 365, plan 2** (hasta la fecha):
<p>

|Prevenir o detectar|Investigar|Respuesta|
|---|---|---|
|Las tecnologías incluyen todo en EOP y Microsoft defender para Office 365 P1 Plus:<u1><li>Mismo</li>|<li>**Explorador de amenazas**</li><li>Rastreadores de amenazas</li><li>Vistas de campañas</li>|<li>Investigación y respuesta automatizadas (AIR)</li><li>AIR del explorador de amenazas</li><li>AIR para usuarios comprometidos</li><li>API de integración de SIEM para investigaciones automatizadas</li>

Por lo tanto, Microsoft defender para Office 365 P2 amplía el **_investigación y la respuesta_* en la parte de la casa, y agrega una nueva resistencia de la caza. Automatización.

En Microsoft defender para Office 365 P2, la herramienta principal de búsqueda se denomina _ *Threat Explorer** en lugar de detecciones en tiempo real. Si ve el explorador de amenazas cuando se desplaza al centro de seguridad, se encuentra en Microsoft defender para Office 365 P2.

Para obtener información detallada de Microsoft defender para Office 365 P1 y P2, vaya **[a este artículo](office-365-atp.md)**.

> [!TIP]
> EOP y Microsoft defender para Office 365 también son diferentes en lo que se refiere a los usuarios finales. En EOP y defender para Office 365 P1, el foco es *conciencia*, por lo que estos dos servicios incluyen el *complemento de Outlook de mensaje de informe* para que los usuarios puedan informar de los correos electrónicos que encuentren sospechosos, para analizarlos posteriormente. <p> En defender para Office 365 P2 (que incluye todo lo que hay en EOP y P1), el foco se desplaza a un *entrenamiento adicional* para los usuarios finales y, por lo tanto, el centro de operaciones de seguridad tiene acceso a una potente herramienta de *simulación de amenazas* y a las métricas del usuario final que proporciona.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft defender para Office 365 plan 1 frente a plan 2 hoja de trampas

Esta referencia rápida le ayudará a comprender las funcionalidades que se incluyen con cada suscripción de Microsoft defender para Office 365. Cuando se combina con su conocimiento de las características de EOP, puede ayudar a los responsables de la toma de decisiones empresariales a determinar lo que Microsoft defender para Office 365 es mejor para sus necesidades.

|Defender para Office 365 plan 1|Defender para Office 365 plan 2|
|---|---|
|Funcionalidades de configuración, protección y detección: <ul><li>[Archivos adjuntos seguros](atp-safe-attachments.md)</li><li>[Vínculos seguros](atp-safe-links.md)</li><li>[ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Protección contra suplantación de identidad (phishing) en defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecciones en tiempo real](threat-explorer.md)</li></ul>|Capacidades de defender para Office 365 plan 1<br/>--- además ---<br/>Funcionalidades de automatización, investigación, corrección y educación:</li><li>[Rastreadores de amenazas](threat-trackers.md)</li><li>[Explorador de amenazas](threat-explorer.md)</li><li>[Investigación y respuesta automatizadas](office-365-air.md)</li><li>[Simulador de ataque](attack-simulator.md)</li></ul>|
|

- Microsoft defender para Office 365 plan 2 se incluye en Office 365 E5, Office 365 A5 y Microsoft 365 E5.

- El Plan 1 de Microsoft Defender para Office 365 está incluido en Microsoft 365 Empresa Premium.

- Microsoft defender para Office 365 plan 1 y defender para Office 365 plan 2 están disponibles como complementos para determinadas suscripciones. Para obtener más información, he aquí otra disponibilidad de la característica de vínculos [en los planes de Microsoft defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- La característica [Documentos seguros](safe-docs.md) solo está disponible para los usuarios con las licencias de Microsoft 365 E5 o Seguridad de Microsoft 365 E5 (no se incluye en los planes de Microsoft Defender para Office 365).

- Si su suscripción actual no incluye Microsoft defender para Office 365 y lo desea, [póngase en contacto con sales para iniciar una prueba](https://go.microsoft.com/fwlink/p/?LinkId=518644)y descubra cómo Microsoft defender para Office 365 puede funcionar en su organización.

> [!TIP]
> ***Consejo Insider** _. Puede usar la tabla de contenido docs.microsoft.com para obtener información sobre EOP y Microsoft defender para Office 365. Vuelva a esta página, [Office 365 Security Overview](https://docs.microsoft.com/microsoft-365/security/office-365-security), y verá que la organización de la tabla de contenido está en la barra lateral. Comienza con la implementación (incluida la migración) y, a continuación, sigue en prevención, detección, investigación y respuesta. <p> Esta estructura se divide para que los temas _ *Security Administration** sigan los temas de **operaciones de seguridad** . Si es un miembro nuevo de cualquier rol de trabajo, use el vínculo de esta sugerencia y su conocimiento de la tabla de contenido para ayudarle a aprender el espacio. Recuerde usar *vínculos de comentarios* y *calificar artículos* a medida que avanza. Los comentarios nos ayudarán a mejorar lo que le ofrecemos.

## <a name="where-to-go-next"></a>Dónde ir junto

Si es un administrador de seguridad, es posible que deba configurar DKIM o DMARC para el correo. Es posible que desee implementar ajustes preestablecidos de seguridad ' STRICT ' para los usuarios con prioridad o buscar las novedades del producto. O bien, si tiene un OPS de seguridad, puede que desee aprovechar las detecciones en tiempo real o el explorador de amenazas para investigar y responder, o entrenar la detección del usuario final con el simulador de ataques. En cualquier caso, estas son algunas recomendaciones adicionales para lo que se debe considerar a continuación.

[Autenticación de correo electrónico, que incluye SPF, DKIM y DMARC (con vínculos al programa de instalación de los tres)](email-validation-and-authentication.md)

[Consulte las configuraciones de "Golden" específicas recomendadas](recommended-settings-for-eop-and-office365-atp.md) y [use sus valores predeterminados recomendados para configurar las directivas de seguridad rápidamente](preset-security-policies.md) .

Ponerse al día sobre las novedades [de Microsoft defender para Office 365 (incluidos los progresos de EOP)](whats-new-in-office-365-atp.md)

[Usar el explorador de amenazas o detecciones en tiempo real](threat-explorer.md)

Usar el [simulador de ataques en Microsoft defender para Office 365](attack-simulator.md)
