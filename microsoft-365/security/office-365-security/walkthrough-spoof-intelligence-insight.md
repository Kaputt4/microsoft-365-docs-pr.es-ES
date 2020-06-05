---
title: 'Tutorial: información sobre inteligencia de simulación'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo funciona el análisis de inteligencia de suplantación de identidad, incluido cómo determinar rápidamente qué remitentes envían de forma legítima un correo no autenticado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1b97d36c3434e7410f4cb3d19ef8eaee6f37e601
ms.sourcegitcommit: 86705d15231c987be2fcf5a295b9b6239fc46077
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "44566709"
---
# <a name="walkthrough---atp-spoof-intelligence-insight-in-microsoft-365"></a>Tutorial: información de inteligencia sobre la simulación de ATP en Microsoft 365

En Microsoft 365 organizaciones con la protección contra amenazas avanzada (ATP), puede usar la información de inteligencia de inteligencia de suplantación para determinar rápidamente qué remitentes le envían de forma legítima un correo no autenticado. Al permitirles enviar mensajes suplantados, puede reducir el riesgo de que los falsos positivos vayan a sus usuarios. También puede usar la información de inteligencia de inteligencia de suplantación para supervisar y administrar pares de dominios permitidos para proporcionar un nivel adicional de seguridad y evitar que lleguen mensajes no seguros a su organización.

Si no está familiarizado con [los informes y la información del centro de seguridad & cumplimiento](reports-and-insights-in-security-and-compliance.md), es posible que le resulte útil ver cómo puede navegar fácilmente desde un panel hasta una perspectiva y las acciones recomendadas.

Este tutorial es uno de los varios para el centro de seguridad & cumplimiento. Para obtener información sobre Cómo desplazarse por los informes y la información, vea los tutoriales de la sección temas relacionados.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página del **Panel de seguridad** , use <https://protection.office.com/searchandinvestigation/dashboard> .

  Puede ver la información de inteligencia de inteligencia de suplantación de más de un panel en el centro de seguridad & cumplimiento. Independientemente del panel que esté mirando, la visión proporciona los mismos detalles y le permite realizar rápidamente las mismas tareas.

- Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos. Para usar el conocimiento de inteligencia de suplantación de identidad, debe ser miembro de los grupos de roles de administración de la **organización**, **Administrador de seguridad**o lector de **seguridad** . Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Puede habilitar y deshabilitar la inteligencia de identidad en las directivas antiphishing de ATP. Para obtener más información, consulte [Configure ATP anti-phishing policies en Microsoft 365](configure-atp-anti-phishing-policies.md).

- En Microsoft 365 organizaciones con buzones de correo de Exchange Online y en Exchange Online Protection (EOP) independiente sin buzones de correo de Exchange Online, puede usar inteligencia de suplantación de identidad para supervisar y administrar a los remitentes que le envían mensajes sin autenticar. Para obtener más información, consulte [Configuración de inteligencia contra la suplantación de identidad en Microsoft 365 ](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abrir el conocimiento de inteligencia de infalsificación en el centro de seguridad & cumplimiento

1. En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Dashboard.**

2. En la fila **información** , busque uno de los siguientes elementos:

   - **Inteligencia de identidad habilitada**: la información se denomina **dominios falseados que no superaron la autenticación de los últimos 30 días**. Este valor es predeterminado.

   - La **inteligencia de identidad está deshabilitada**: la información de la **habilitación de la protección contra**la suplantación de identidad y al hacer clic en ella le permite habilitar la inteligencia de identidad.

3. El conocimiento del panel muestra la siguiente información:

   ![Captura de pantalla de la información sobre inteligencia de suplantación](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esta visión tiene dos modos:

   - **Modo Insight**. Si tiene una directiva de suplantación habilitada, la información le mostrará Cuántos correos se vieron afectados por nuestras capacidades de inteligencia empresarial de suplantación en los últimos 30 días.

   - **Mode if**. Si no tiene habilitada ninguna directiva de suplantación de identidad, la información le mostrará Cuántos correos se *verían* afectados por nuestras capacidades de inteligencia de suplantación en los últimos 30 días.

   En cualquier caso, los dominios suplantados que se muestran en la información se separan en dos categorías: **pares de dominios sospechosos** y **pares de dominios no sospechosos**. Estas categorías se subdividen en tres diferentes recipientes para su revisión.

   Un **par de dominios** es una combinación de la dirección de y la infraestructura de envío:

   - La dirección de es la dirección de correo electrónico del remitente que se muestra en los clientes de correo electrónico. Esta dirección identifica al autor del correo electrónico. Es decir, el buzón de la persona o el sistema responsables de escribir el mensaje. Esta dirección también se conoce como `5322.From` dirección.

   - La infraestructura de envío o remitente es el dominio de la organización de la búsqueda DNS inversa (registro PTR) de la dirección IP de envío. Si la dirección IP de envío no tiene registro PTR, el remitente se identifica mediante la IP de envío con la máscara de subred 255.255.255.0 en la notación CIDR (/24). Por ejemplo, si la dirección IP es 192.168.100.100, la dirección IP completa del remitente es 192.168.100.100/24.

   Los **pares de dominios sospechosos** incluyen:

   - **Suplantación de confianza alta**: Microsoft 365 recibió fuertes señales de que estos dominios son sospechosos, en función de los patrones de envío históricos y la puntuación de reputación de los dominios. Microsoft 365 es muy seguro que los dominios son suplantación de identidad y que los mensajes que se envían desde estos dominios tienen menos probabilidades de ser legítimos.

   - **Suplantación de confianza moderada**: Microsoft 365 recibió señales medianas que estos dominios son sospechosos, según los patrones de envío históricos y la puntuación de reputación de los dominios. Office 365 está moderadamente seguro de que los dominios son suplantación de identidad y que los mensajes enviados desde estos dominios son legítimos. Este cubo tiene una probabilidad mayor de contener falsos positivos (FPs) que el bucket de suplantación de confianza alta.

   - **Pares de dominios no sospechosos** (incluye **suplantación de identidad recuperada**): suplantación de identidad recuperada los dominios que no superaron la autenticación explícita [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), [DMARC](use-dmarc-to-validate-email.md)) pero pasaron las comprobaciones de autenticación de correo electrónico IMPLÍCITAS ([autenticación compuesta](email-validation-and-authentication.md#composite-authentication)). Como resultado, Microsoft 365 recuperar el correo en su nombre y no se ha llevado a cabo ninguna acción contra la suplantación de identidad en el mensaje.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Ver información detallada sobre los pares de dominios sospechosos desde el conocimiento de inteligencia de suplantación

1. En el análisis de inteligencia de suplantación de identidad, haga clic en cualquiera de los pares de dominios (alta, moderada o rescatada).

   Aparece la página **Suplantar visión de inteligencia empresarial** , que muestra una lista de remitentes que envían correo no autenticado a su organización. La información de esta página le ayudará a determinar si los mensajes falsos están autorizados o si necesita emprender otras acciones. Puede ordenar la información por número de mensajes, fecha de la última detección de la suplantación de identidad, etc. (Por ejemplo, haga clic en encabezados de columna, como **número de mensajes** o **última**vista).

2. Seleccione un elemento de la tabla para abrir un panel de detalles que contenga información enriquecida sobre el par de dominios, incluido por qué lo hemos capturado, lo que debe hacer, un resumen de dominio, datos WhoIs sobre el remitente y mensajes de correo electrónico similares que hemos visto en su espacio empresarial del mismo remitente. Desde aquí, también puede Agregar o quitar el par de dominios de la lista de remitentes seguros de **AllowedToSpoof** .

   ![Captura de pantalla de un dominio en el panel de detalles de inteligencia empresarial de suplantación](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Agregar o quitar un dominio de la lista de remitentes seguros de AllowedToSpoof

Puede Agregar o quitar un dominio de la lista de remitentes seguros de AllowedToSpoof al revisar el par de dominios en el panel de detalles de la información de inteligencia empresarial de suplantación. Simplemente, establezca el botón de alternancia en consecuencia.

Esto modifica la combinación única de par de dominios del dominio falso y de la infraestructura de envío y no proporciona cobertura para todo el dominio falso o la infraestructura de envío de forma aislada.

Por ejemplo, si agrega el siguiente par de dominios a la lista de permitidos del *remitente: "* gmail.com" y envía la *infraestructura* "TMS *. mx.com",* sólo se permitirá la suplantación de correo desde ese par de dominios. Otros remitentes que intentan imitar "gmail.com" y otros dominios que intentan simular "tms.mx.com" seguirán protegidos por inteligencia de suplantación de identidad.

## <a name="related-topics"></a>Temas relacionados

[Protección contra suplantación de identidad (phishing) en Microsoft 365](anti-spoofing-protection.md)
