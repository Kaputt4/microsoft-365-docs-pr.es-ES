---
title: Seguridad de Office 365, Microsoft Defender para Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Seguridad en Office 365, de EOP a Defender para Office 365 Planes 1 y 2, configuraciones de seguridad estándar frente a estrictas, etc. Comprenda lo que tiene y cómo proteger sus propiedades.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 68570cedd0696510f2181edcea7ef149ace606e3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166422"
---
# <a name="office-365-security-overview"></a>Introducción a la seguridad de Office 365

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)


En este artículo se presentan las nuevas propiedades de seguridad en la nube. Independientemente de si forma parte de un Centro de operaciones de seguridad, es un administrador de seguridad nuevo en el espacio o quiere un actualizador, vamos a empezar.

> [!CAUTION]
> Si usa **Outlook.com,** Microsoft **365 Familia** o **Microsoft 365 Personal**  y necesita  vínculos seguros o datos adjuntos ***seguros,*** haga clic en este vínculo: Seguridad avanzada de Outlook.com para suscriptores de [Microsoft 365.](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)

## <a name="office-365-security-spelled-out"></a>Seguridad de Office 365 deletreada

Cada suscripción a Office 365 incluye funcionalidades de seguridad. Los objetivos y las acciones que puedes realizar dependen del foco de estas distintas suscripciones. En la seguridad de Office 365, hay tres servicios de seguridad (o productos) principales vinculados a su tipo de suscripción:

1. Exchange Online Protection (EOP)
1. Microsoft Defender para Office 365 Plan 1 (Defender para Office P1)
1. Microsoft Defender para Office 365 Plan 2 (Defender para Office P2)

> [!NOTE]
> Si compró su suscripción y necesita implantar características de seguridad en este *momento,* vaya directamente a los pasos del artículo Proteger [contra amenazas.](protect-against-threats.md) Si no tiene experiencia con su suscripción y quiere conocer su licencia antes de empezar, busque Facturación > Sus productos en el Centro de administración de [Microsoft 365.](https://admin.microsoft.com/AdminPortal/#/homepage)

La seguridad de Office 365 se basa en las protecciones principales que ofrece EOP. EOP está presente en cualquier suscripción en la que se puedan encontrar buzones de Exchange Online (recuerde que todos los productos de seguridad que se analizan aquí están basados en la nube).

Tal vez esté acostumbrado a ver estos tres componentes de esta manera:

|EOP|Microsoft Defender para Office 365 P1|Microsoft Defender para Office 365 P2|
|---|---|---|
|Impide ataques amplios, basados en volumen y conocidos.|Protege el correo electrónico y la colaboración contra el malware de día cero, la suplantación de identidad y el correo electrónico empresarial en peligro.|Agrega investigación, búsqueda y respuesta posteriores a la infracción, así como automatización y simulación (para formación).|
|

Pero en términos de arquitectura, empecemos pensando en cada elemento como capas acumulativas de seguridad, cada una con un énfasis de seguridad. Más parecido a esto:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP y Microsoft Defender para Office 365 y sus relaciones entre sí con énfasis en el servicio, incluida una nota para la autenticación de correo electrónico.":::

Aunque cada uno de estos servicios enfatiza un objetivo entre Proteger, Detectar, Investigar y Responder, ***todos** los _ los servicios pueden llevar a cabo _ *_cualquier_** de los objetivos de protección, detección, investigación y respuesta.

El núcleo de la seguridad de Office 365 es la protección de EOP. Microsoft Defender para Office 365 P1 contiene EOP. Defender para Office 365 P2 contiene P1 y EOP. La estructura es acumulativa. Por eso, al configurar este producto, debe empezar con EOP y trabajar con Defender para Office 365.

Aunque la configuración de autenticación de correo electrónico tiene lugar en DNS público, es importante configurar esta característica para ayudar a protegerse contra la suplantación de nombres. *Si tiene EOP, debe* ***configurar la [autenticación de correo electrónico.](email-validation-and-authentication.md)***

Si tiene un Office 365 E3 o una versión inferior, tiene EOP, pero con la opción de comprar Defender independiente para Office 365 P1 a través de la actualización. Si tiene Office 365 E5, ya tiene Defender para Office 365 P2.

> [!TIP]
> Si su suscripción no es office 365 E3 o E5, aún puede comprobar si tiene la opción de actualizar a Microsoft Defender para Office 365 P1. Si está [interesado,](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) esta página web enumera las suscripciones aptas para la actualización de Microsoft Defender para Office 365 P1 (compruebe el final de la página para obtener la impresión personalizada).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>El proceso de seguridad de Office 365 de EOP a Microsoft Defender para Office 365

![EOP y Microsoft Defender para Office 365 y su énfasis en la seguridad, desde Proteger y detectar para investigar y responder. La configuración de autenticación de correo electrónico (al menos DKIM y DMARC) debe configurarse para EOP y configurarse.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Obtenga más información sobre estas páginas: [Exchange Online Protection](exchange-online-protection-overview.md)y Defender para Office [365.](office-365-atp.md)

Lo que hace que agregar planes de Microsoft Defender para Office 365 sea una ventaja para la administración pura de amenazas de EOP puede ser difícil de saber a primera vista. Para ayudar a ordenar si una ruta de actualización es adecuada para su organización, veamos las capacidades de cada producto en lo que respecta a:

- evitar y detectar amenazas
- investigando
- responder

a partir **de Exchange Online Protection:**
<p>

|Impedir/detectar|Investigar|Respuesta|
|---|---|---|
|Las tecnologías incluyen:<ul><li>correo no deseado</li><li>phish</li><li>malware</li><li>correo masivo</li><li>inteligencia de suplantación de seguridad</li><li>detección de suplantación</li><li>Cuarentena de administradores</li><li>Envíos de usuarios y administradores de falsos positivos y falsos negativos</li><li>Permitir o bloquear direcciones URL y archivos</li><li>Informes</li></u1>|<li>Búsqueda de registros de auditoría</li><li>Seguimiento de mensajes</li>|<li>Purga automática de cero horas (ZAP)</li><li>Refinamiento y pruebas de listas de permitidos y bloqueados</li>|
|

Si quiere profundizar en EOP, **[vaya a este artículo.](exchange-online-protection-overview.md)**

Dado que estos productos son acumulativos, si evalúa Microsoft Defender para Office 365 P1 y decide suscribirse a él, agregará estas capacidades.

Mejoras con **Defender para Office 365, Plan 1** (hasta la fecha):
<p>

|Impedir/detectar|Investigar|Respuesta|
|---|---|---|
|Las tecnologías incluyen todo en EOP, además de:<u1><li>Datos adjuntos seguros</li><li>Vínculos seguros<li>Protección de Microsoft Defender para Office 365 para cargas de trabajo (por ejemplo, SharePoint Online, Teams, OneDrive para la Empresa)</li><li>Protección con el tiempo de clic en correo electrónico, clientes de Office y Teams</li><li>anti-phishing en Defender para Office 365</li><li>Protección de suplantación de usuario y dominio</li><li>Alertas y API de integración siem para alertas</li>|<li>API de integración de SIEM para detecciones</li><li>**Herramienta de detecciones en tiempo real**</li><li>Seguimiento de url</li>|<li>Mismo</li></u1>

Por lo tanto, Microsoft Defender para Office 365 P1 se expande en el lado **de** prevención * de la casa y agrega formas adicionales de detección __*_**.

Microsoft Defender para Office 365 P1 también agrega detecciones en tiempo **real** para investigaciones. El nombre de esta herramienta de búsqueda de amenazas  está en negrita porque tenerla es una forma clara de saber que tiene Defender para Office 365 P1. No aparece en Defender para Office 365 P2.

Mejoras con **Defender para Office 365, Plan 2** (hasta la fecha):
<p>

|Impedir/detectar|Investigar|Respuesta|
|---|---|---|
|Las tecnologías incluyen todo en EOP y Microsoft Defender para Office 365 P1 más:<u1><li>Mismo</li>|<li>**Explorador de amenazas**</li><li>Rastreadores de amenazas</li><li>Vistas de campaña</li>|<li>Investigación y respuesta automatizadas (AIR)</li><li>AIR desde el Explorador de amenazas</li><li>AIR para usuarios comprometidos</li><li>API de integración de SIEM para investigaciones automatizadas</li>

Por lo tanto, Microsoft Defender para Office 365 P2 se expande en el lado de investigación y respuesta de la casa y agrega una nueva intensidad de búsqueda.  Automatización.

En Microsoft Defender para Office 365 P2,  la herramienta de búsqueda principal se denomina Explorador de amenazas en lugar de detecciones en tiempo real. Si ve el Explorador de amenazas cuando navega al Centro de seguridad, está en Microsoft Defender para Office 365 P2.

Para entrar en los detalles de Microsoft Defender para Office 365 P1 y P2, vaya **[a este artículo.](office-365-atp.md)**

> [!TIP]
> EOP y Microsoft Defender para Office 365 también son diferentes en lo que respecta a los usuarios finales. En EOP y Defender para Office 365 P1, el foco es la concienciación y, por lo tanto, estos dos servicios incluyen el complemento de *Outlook* de mensaje de informe para que los usuarios puedan informar sobre correos electrónicos que encuentran sospechosos, para un análisis posterior. <p> En Defender para Office 365 P2 (que contiene todo en EOP y P1), el foco cambia a formación  adicional para los usuarios finales y, por lo tanto, el Centro de operaciones de seguridad tiene acceso a una herramienta eficaz del simulador de amenazas y a las métricas del usuario final que proporciona. 

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Hoja de trucos de Microsoft Defender para Office 365 Plan 1 frente a Plan 2

Esta referencia rápida le ayudará a comprender qué funcionalidades se incluyen con cada suscripción de Microsoft Defender para Office 365. Cuando se combina con su conocimiento de las características de EOP, puede ayudar a los responsables de la toma de decisiones empresariales a determinar qué Microsoft Defender para Office 365 es mejor para sus necesidades.

|Defender para Office 365 Plan 1|Defender para Office 365 Plan 2|
|---|---|
|Funcionalidades de configuración, protección y detección: <ul><li>[Archivos adjuntos seguros](atp-safe-attachments.md)</li><li>[Vínculos seguros](atp-safe-links.md)</li><li>[Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Protección contra suplantación de identidad en Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecciones en tiempo real](threat-explorer.md)</li></ul>|Capacidades de Defender para Office 365 Plan 1 <p> --- además --- <p> Funcionalidades de automatización, investigación, corrección y educación: <ul><li>[Rastreadores de amenazas](threat-trackers.md)</li><li>[Explorador de amenazas](threat-explorer.md)</li><li>[Investigación y respuesta automatizadas](office-365-air.md)</li><li>[Simulador de ataque](attack-simulator.md)</li></ul>|
|

- Microsoft Defender para Office 365 Plan 2 se incluye en Office 365 E5, Office 365 A5 y Microsoft 365 E5.

- El Plan 1 de Microsoft Defender para Office 365 está incluido en Microsoft 365 Empresa Premium.

- Microsoft Defender para Office 365 Plan 1 y Defender para Office 365 Plan 2 están disponibles como complemento para determinadas suscripciones. Para obtener más información, este es otro vínculo de disponibilidad de características en los planes de [Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- La característica [Documentos seguros](safe-docs.md) solo está disponible para los usuarios con las licencias de Microsoft 365 E5 o Seguridad de Microsoft 365 E5 (no se incluye en los planes de Microsoft Defender para Office 365).

- Si su suscripción actual no incluye Microsoft Defender para Office 365 y lo [desea,](https://go.microsoft.com/fwlink/p/?LinkId=518644)póngase en contacto con ventas para iniciar una prueba y descubra cómo puede funcionar Microsoft Defender para Office 365 en su organización.

> [!TIP]
> ***Sugerencia de Insider** _. Puede usar la tabla docs.microsoft.com contenido para obtener información sobre EOP y Microsoft Defender para Office 365. Vuelva a esta página, información general de seguridad de [Office 365,](https://docs.microsoft.com/microsoft-365/security/office-365-security)y observará que la organización de la tabla de contenido se encuentra en la barra lateral. Comienza con la implementación (incluida la migración) y, a continuación, continúa con la prevención, la detección, la investigación y la respuesta. <p> Esta estructura se divide para que los temas _ *Administración de seguridad** estén seguidos de los temas operaciones **de** seguridad. Si es un nuevo miembro de cualquiera de los roles de trabajo, use el vínculo de esta sugerencia y su conocimiento de la tabla de contenido para ayudar a aprender el espacio. Recuerde usar *vínculos de comentarios* y *artículos de tasa* a medida que vaya. Los comentarios nos ayudan a mejorar lo que le ofrecemos.

## <a name="where-to-go-next"></a>Dónde ir a continuación

Si es administrador de seguridad, es posible que deba configurar DKIM o DMARC para el correo. Es posible que quieras implantar valores preestablecidos de seguridad "estrictos" para los usuarios prioritarios o buscar las novedades del producto. O bien, si estás con Operaciones de seguridad, es posible que quieras aprovechar las detecciones en tiempo real o el Explorador de amenazas para investigar y responder, o entrenar la detección del usuario final con el Simulador de ataques. En ambos casos, estas son algunas recomendaciones adicionales sobre qué ver a continuación.

[Autenticación de correo electrónico, incluidos SPF, DKIM y DMARC (con vínculos a la configuración de los tres)](email-validation-and-authentication.md)

[Ver las configuraciones "dorados" recomendadas](recommended-settings-for-eop-and-office365-atp.md) específicas y [usar sus valores preestablecidos recomendados para configurar](preset-security-policies.md) las directivas de seguridad rápidamente

Ponerse al día sobre las novedades de [Microsoft Defender para Office 365 (incluidos los desarrollos de EOP)](whats-new-in-office-365-atp.md)

[Usar el Explorador de amenazas o las detecciones en tiempo real](threat-explorer.md)

Usar [el simulador de ataques en Microsoft Defender para Office 365](attack-simulator.md)
