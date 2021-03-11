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
description: Seguridad en Office 365, de EOP a Defender para Office 365 Planes 1 y 2, Estándar frente a configuraciones de seguridad estrictas, etc. Comprenda lo que tiene y cómo proteger sus propiedades.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1c6e768098cd59892c2572fb52497c873aef1a3
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711945"
---
# <a name="office-365-security-overview"></a>Introducción a la seguridad de Office 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)


Este artículo le presentará las nuevas propiedades de seguridad en la nube. Independientemente de si forma parte de un Centro de operaciones de seguridad, es un administrador de seguridad nuevo en el espacio o quiere un actualizador, vamos a empezar.

> [!CAUTION]
> Si **usas Outlook.com**, Microsoft **365 Family** o Microsoft **365 Personal** y  necesitas información sobre vínculos seguros o datos adjuntos ***seguros,*** haz clic en este vínculo: Seguridad Outlook.com avanzada para suscriptores de [Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2). 

## <a name="office-365-security-spelled-out"></a>Seguridad de Office 365 detallada

Cada suscripción a Office 365 incluye funciones de seguridad. Los objetivos y las acciones que puede realizar dependen del foco de estas diferentes suscripciones. En seguridad de Office 365, hay tres servicios de seguridad principales (o productos) vinculados al tipo de suscripción:

1. Exchange Online Protection (EOP)
1. Plan 1 de Microsoft Defender para Office 365 (Defender para Office P1)
1. Plan 2 de Microsoft Defender para Office 365 (Defender para Office P2)

> [!NOTE]
> Si compró la suscripción y necesita implantar características de seguridad en este *momento,* vaya a los pasos del artículo [Proteger contra amenazas.](protect-against-threats.md) Si es nuevo en su suscripción y desea conocer su licencia antes de comenzar, busque Facturación > Sus productos en el Centro de administración de [Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

La seguridad de Office 365 se basa en las protecciones principales que ofrece EOP. EOP está presente en cualquier suscripción en la que se puedan encontrar buzones de Exchange Online (recuerde que todos los productos de seguridad que se analizan aquí están basados en la nube).

Puede que esté acostumbrado a ver estos tres componentes de esta manera:

|EOP|Microsoft Defender para Office 365 P1|Microsoft Defender para Office 365 P2|
|---|---|---|
|Evita ataques amplios, basados en volumen y conocidos.|Protege el correo electrónico y la colaboración contra el malware de día cero, la suplantación de identidad y el riesgo de correo electrónico empresarial.|Agrega investigación, búsqueda y respuesta posteriores a la infracción, así como automatización y simulación (para entrenamiento).|
|

Pero en términos de arquitectura, empecemos pensando en cada pieza como capas acumulativas de seguridad, cada una con un énfasis en la seguridad. Más como esta:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP y Microsoft Defender para Office 365 y sus relaciones entre sí con énfasis en el servicio, incluida una nota para la autenticación de correo electrónico.":::

Aunque cada uno de estos servicios hace hincapié en un objetivo de entre Proteger, Detectar, Investigar y Responder, ***todos** _ los servicios pueden llevar a *_cabo_* _ cualquier * de los objetivos de proteger, detectar, investigar y responder.

El núcleo de la seguridad de Office 365 es la protección de EOP. Microsoft Defender para Office 365 P1 contiene EOP. Defender para Office 365 P2 contiene P1 y EOP. La estructura es acumulativa. Por eso, al configurar este producto, debe empezar por EOP y trabajar con Defender para Office 365.

Aunque la configuración de autenticación de correo electrónico tiene lugar en DNS público, es importante configurar esta característica para ayudar a defenderse de la suplantación. *Si tiene EOP,* ***debe configurar la [autenticación de correo electrónico](email-validation-and-authentication.md)***.

Si tiene un Office 365 E3 o una versión inferior, tiene EOP, pero con la opción de comprar Defender independiente para Office 365 P1 a través de la actualización. Si tiene Office 365 E5, ya tiene Defender para Office 365 P2.

> [!TIP]
> Si su suscripción no es Office 365 E3 o E5, puede comprobar si tiene la opción de actualizar a Microsoft Defender para Office 365 P1. Si está [interesado,](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) en esta página web se enumeran las suscripciones elegibles para la actualización de Microsoft Defender para Office 365 P1 (compruebe el final de la página para obtener la letra pequeña).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>La escala de seguridad de Office 365 de EOP a Microsoft Defender para Office 365

![EOP y Microsoft Defender para Office 365 y su énfasis en la seguridad, desde Proteger y detectar para investigar y responder. La configuración de autenticación de correo electrónico (al menos DKIM y DMARC) debe configurarse para EOP y para arriba.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Obtenga más información en estas páginas: [Exchange Online Protection](exchange-online-protection-overview.md)y Defender para Office [365](office-365-atp.md).

Lo que hace que agregar planes de Microsoft Defender para Office 365 sea una ventaja para la administración de amenazas de EOP pura puede ser difícil de saber a primera vista. Para ayudar a ordenar si una ruta de actualización es adecuada para su organización, veamos las capacidades de cada producto cuando se trata de:

- prevención y detección de amenazas
- investigación
- responder

a partir de **Exchange Online Protection:**
<p>

|Prevención y detección|Investigar|Respuesta|
|---|---|---|
|Las tecnologías incluyen:<ul><li>correo no deseado</li><li>phish</li><li>malware</li><li>correo masivo</li><li>inteligencia de suplantación</li><li>detección de suplantación</li><li>Cuarentena de administradores</li><li>Envíos de usuarios y administradores de falsos positivos y falsos negativos</li><li>Permitir/bloquear direcciones URL y archivos</li><li>Informes</li></u1>|<li>Búsqueda de registros de auditoría</li><li>Seguimiento de mensajes</li>|<li>Purga automática de hora cero (ZAP)</li><li>Refinamiento y pruebas de listas de permitir y bloquear</li>|
|

Si desea profundizar en EOP, **[vaya a este artículo](exchange-online-protection-overview.md)**.

Dado que estos productos son acumulativos, si evalúa Microsoft Defender para Office 365 P1 y decide suscribirse a él, agregará estas capacidades.

Ganancias **con Defender para Office 365, Plan 1** (hasta la fecha):
<p>

|Prevención y detección|Investigar|Respuesta|
|---|---|---|
|Las tecnologías incluyen todo en EOP más:<u1><li>Datos adjuntos seguros</li><li>Vínculos seguros<li>Protección de Microsoft Defender para Office 365 para cargas de trabajo (por ejemplo. SharePoint Online, Teams, OneDrive para la Empresa)</li><li>Protección con tiempo de clic en correo electrónico, clientes de Office y Teams</li><li>anti phishing en Defender para Office 365</li><li>Protección de suplantación de usuario y dominio</li><li>Alertas y API de integración siem para alertas</li>|<li>API de integración siem para detecciones</li><li>**Herramienta de detecciones en tiempo real**</li><li>Seguimiento de direcciones URL</li>|<li>Mismo</li></u1>

Por lo tanto, Microsoft Defender para Office 365 P1 se expande en **el** lado _ de prevención * de la casa y agrega formas adicionales de detección __*_**.

Microsoft Defender para Office 365 P1 también agrega **detecciones en** tiempo real para investigaciones. El nombre de esta herramienta de búsqueda de amenazas  está en negrita porque tenerla es un medio claro de saber que tiene Defender para Office 365 P1. No aparece en Defender para Office 365 P2.

Ganancias **con Defender para Office 365, Plan 2** (hasta la fecha):
<p>

|Prevención y detección|Investigar|Respuesta|
|---|---|---|
|Las tecnologías incluyen todo en EOP y Microsoft Defender para Office 365 P1 plus:<u1><li>Mismo</li>|<li>**Explorador de amenazas**</li><li>Rastreadores de amenazas</li><li>Vistas de campaña</li>|<li>Investigación y respuesta automatizadas (AIR)</li><li>AIR desde el Explorador de amenazas</li><li>AIR para usuarios en peligro</li><li>API de integración SIEM para investigaciones automatizadas</li>

Por lo tanto, Microsoft Defender para Office 365 P2 se expande en el lado de investigación y respuesta de la casa y agrega una nueva intensidad de búsqueda.  Automatización.

En Microsoft Defender para Office 365 P2, la herramienta de búsqueda principal se denomina **Explorador** de amenazas en lugar de detecciones en tiempo real. Si ve el Explorador de amenazas al navegar al Centro de seguridad, está en Microsoft Defender para Office 365 P2.

Para entrar en los detalles de Microsoft Defender para Office 365 P1 y P2, **[vaya a este artículo](office-365-atp.md)**.

> [!TIP]
> EOP y Microsoft Defender para Office 365 también son diferentes en lo que respecta a los usuarios finales. En EOP y Defender para Office 365 P1, el foco es el reconocimiento y, por lo tanto, esos dos servicios incluyen el complemento De informes de *Outlook* para que los usuarios puedan informar de los correos electrónicos que encuentran sospechosos, para su análisis posterior. <p> En Defender para Office 365 P2 (que contiene todo en EOP y P1), el foco cambia a más  aprendizaje para los usuarios finales, por lo que el Centro de operaciones de seguridad tiene acceso a una herramienta eficaz del simulador de amenazas y a las métricas del usuario final que proporciona. 

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Hoja de trucos de Microsoft Defender para Office 365 Plan 1 vs. Plan 2

Esta referencia rápida le ayudará a comprender qué funciones vienen con cada suscripción de Microsoft Defender para Office 365. Cuando se combina con sus conocimientos sobre las características de EOP, puede ayudar a los responsables de la toma de decisiones empresariales a determinar qué Es mejor Microsoft Defender para Office 365 para sus necesidades.

|Defender para Office 365 Plan 1|Defender para Office 365 Plan 2|
|---|---|
|Funcionalidades de configuración, protección y detección: <ul><li>[Archivos adjuntos seguros](atp-safe-attachments.md)</li><li>[Vínculos seguros](atp-safe-links.md)</li><li>[Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Protección contra suplantación de identidad en Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecciones en tiempo real](threat-explorer.md)</li></ul>|Capacidades del Plan 1 de Defender para Office 365 <p> --- además --- <p> Funcionalidades de automatización, investigación, corrección y educación: <ul><li>[Rastreadores de amenazas](threat-trackers.md)</li><li>[Explorador de amenazas](threat-explorer.md)</li><li>[Investigación y respuesta automatizadas](office-365-air.md)</li><li>[Simulador de ataque](attack-simulator.md)</li></ul>|
|

- Microsoft Defender para Office 365 Plan 2 se incluye en Office 365 E5, Office 365 A5 y Microsoft 365 E5.

- El Plan 1 de Microsoft Defender para Office 365 está incluido en Microsoft 365 Empresa Premium.

- Microsoft Defender para Office 365 Plan 1 y Defender para Office 365 Plan 2 están disponibles como complemento para determinadas suscripciones. Para obtener más información, este es otro vínculo Disponibilidad de características en los planes de [Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- La característica [Documentos seguros](safe-docs.md) solo está disponible para los usuarios con las licencias de Microsoft 365 E5 o Seguridad de Microsoft 365 E5 (no se incluye en los planes de Microsoft Defender para Office 365).

- Si la suscripción actual no incluye Microsoft Defender para Office 365 y lo [desea,](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)póngase en contacto con ventas para iniciar una prueba y descubra cómo puede funcionar Microsoft Defender para Office 365 en su organización.

> [!TIP]
> ***Sugerencia de Insider** _. Puede usar la tabla docs.microsoft.com de contenido para obtener información sobre EOP y Microsoft Defender para Office 365. Vuelva a esta página, Información general sobre seguridad de [Office 365](index.md)y verá la organización de la tabla de contenido en la barra lateral. Comienza con la implementación (incluida la migración) y, a continuación, continúa con la prevención, la detección, la investigación y la respuesta. <p> Esta estructura se divide de modo que los temas _ *Administración de seguridad** se siguen por temas de operaciones **de** seguridad. Si es un nuevo miembro de cualquiera de los roles de trabajo, use el vínculo de esta sugerencia y su conocimiento de la tabla de contenido para aprender el espacio. Recuerde usar *vínculos de comentarios* y calificar *artículos* a medida que vaya. Los comentarios nos ayudan a mejorar lo que le ofrecemos.

## <a name="where-to-go-next"></a>Dónde ir a continuación

Si eres administrador de seguridad, es posible que deba configurar DKIM o DMARC para el correo. Es posible que quieras realizar ajustes preestablecidos de seguridad "estrictos" para los usuarios prioritarios o buscar las novedades del producto. O bien, si estás con Operaciones de seguridad, es posible que quieras aprovechar las detecciones en tiempo real o el Explorador de amenazas para investigar y responder, o entrenar la detección de usuarios finales con Attack Simulator. En cualquier caso, estas son algunas recomendaciones adicionales sobre qué ver a continuación.

[Autenticación de correo electrónico, incluidos SPF, DKIM y DMARC (con vínculos a la configuración de los tres)](email-validation-and-authentication.md)

[Consulta los configs "dorados" recomendados específicos](recommended-settings-for-eop-and-office365-atp.md) y [usa sus presets recomendados para configurar rápidamente directivas de seguridad](preset-security-policies.md)

Información sobre las novedades de [Microsoft Defender para Office 365 (incluidos los desarrollos de EOP)](whats-new-in-office-365-atp.md)

[Usar el Explorador de amenazas o detecciones en tiempo real](threat-explorer.md)

Usar [el simulador de ataque en Microsoft Defender para Office 365](attack-simulator.md)
