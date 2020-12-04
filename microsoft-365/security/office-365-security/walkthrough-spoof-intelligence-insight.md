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
description: Los administradores pueden obtener información sobre cómo funciona el conocimiento de inteligencia de suplantación de identidad. Pueden determinar rápidamente qué remitentes están enviando de forma legítima correo electrónico a sus organizaciones desde dominios que no pasan comprobaciones de autenticación de correo electrónico (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572746"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Tutorial: información sobre inteligencia de inteligencia contra la simulación en Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En Microsoft 365 organizaciones con defender para Office 365, puede usar la visión de inteligencia de inteligencia de suplantación para determinar rápidamente qué remitentes le envían de forma legítima un correo no autenticado (mensajes de dominios que no pasan las comprobaciones SPF, DKIM o DMARC).

Al permitir que los remitentes conocidos envíen mensajes falsos desde ubicaciones conocidas, puede reducir los falsos positivos (correo electrónico bueno marcado como malo). Mediante la supervisión de los remitentes suplantados permitidos, se proporciona una capa de seguridad adicional para evitar que los mensajes no seguros lleguen a la organización.

Para obtener más información sobre los informes y la información, consulte [Reports and Insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).

Este tutorial es uno de los varios para el centro de seguridad & cumplimiento. Para obtener información sobre Cómo desplazarse por los informes y la información, vea los tutoriales de la sección [temas relacionados](#related-topics) .

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página del **Panel de seguridad** , use <https://protection.office.com/searchandinvestigation/dashboard> .

  Puede ver la información de inteligencia de inteligencia de suplantación de más de un panel en el centro de seguridad & cumplimiento. Independientemente del panel que esté mirando, la visión proporciona los mismos detalles y le permite realizar rápidamente las mismas tareas.

- Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:
  - **Administración de organizaciones**
  - **Administrador de seguridad**
  - **Lector de seguridad**
  - **Lector global**

  **Nota**: agregar usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Puede habilitar y deshabilitar inteligencia simulada en directivas antiphishing en Microsoft defender para Office 365. Para obtener más información, vea [Configure anti-phishing policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).

- Para usar inteligencia simulada para supervisar y administrar a los remitentes que le envían mensajes sin autenticar, consulte [configurar inteligencia de identidades en Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abrir el conocimiento de inteligencia de infalsificación en el centro de seguridad & cumplimiento

1. En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Dashboard.**

2. En la fila **información** , busque uno de los siguientes elementos:

   - **Inteligencia de identidad habilitada**: la información se denomina **dominios falseados que no superaron la autenticación de los últimos 30 días**. Este valor es predeterminado.
   - La **inteligencia de identidad está deshabilitada**: la información de la **habilitación de la protección contra** la suplantación de identidad y al hacer clic en ella le permite habilitar la inteligencia de identidad.

3. El conocimiento del panel muestra la siguiente información:

   ![Captura de pantalla de la información sobre inteligencia de suplantación](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esta visión tiene dos modos:

   - **Modo Insight**: Si la inteligencia de identidad está habilitada, el conocimiento le muestra cuántos mensajes se vieron afectados por nuestras capacidades de inteligencia empresarial de suplantación en los últimos 30 días.

   - **Mode if**: Si la inteligencia de identidad está deshabilitada, la información muestra el número de mensajes que se *verían* afectados por nuestras capacidades de inteligencia de suplantación en los últimos 30 días.

   En cualquier caso, los dominios suplantados que se muestran en la información se separan en dos categorías: **pares de dominios sospechosos** y **pares de dominios no sospechosos**. Estas categorías se subdividen en tres diferentes recipientes para su revisión.

   Un **par de dominios** es una combinación de la dirección de y la infraestructura de envío:

   - La dirección de es la dirección de correo electrónico del remitente que se muestra en el cuadro de en clientes de correo electrónico. Esta dirección también se conoce como `5322.From` dirección.

   - La infraestructura de envío o remitente es el dominio de la organización de la búsqueda DNS inversa (registro PTR) de la dirección IP de envío. Si la dirección IP de envío no tiene registro PTR, el remitente se identifica mediante la IP de envío con la máscara de subred 255.255.255.0 en la notación CIDR (/24). Por ejemplo, si la dirección IP es 192.168.100.100, la dirección IP completa del remitente es 192.168.100.100/24.

   Los **pares de dominios sospechosos** incluyen:

   - **Suplantación de confianza alta**: según los patrones de envío históricos y la puntuación de reputación de los dominios, tenemos muy seguros que los dominios son suplantación de identidad y que los mensajes de estos dominios son más propensos a ser malintencionados.

   - **Simulación de confianza moderada**: según los patrones de envío históricos y la puntuación de reputación de los dominios, estamos muy seguros de que los dominios son suplantación de identidad y que los mensajes enviados desde estos dominios son legítimos. Los falsos positivos son más probables en esta categoría que la suplantación de confianza alta.

   - **Pares de dominios no sospechosos** (incluye la **suplantación de identidad recuperada**): el dominio no pudo comprobar la autenticación de correo electrónico explícita [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md). Sin embargo, el dominio pasó nuestras comprobaciones de autenticación de correo electrónico IMPLÍCITAS ([autenticación compuesta](email-validation-and-authentication.md#composite-authentication)). Como resultado, no se ha llevado a cabo ninguna acción contra la suplantación de identidad en el mensaje.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Ver información detallada sobre los pares de dominios sospechosos desde el conocimiento de inteligencia de suplantación

1. En el análisis de inteligencia de suplantación de identidad, haga clic en cualquiera de los pares de dominios (alta, moderada o rescatada).

   Aparece la página de **información de inteligencia empresarial de suplantación** . La página muestra una lista de remitentes que envían correo no autenticado a su organización.

   Esta información le ayudará a determinar si los mensajes suplantados están autorizados o si necesita emprender otras acciones.

   Puede ordenar la información por número de mensajes, fecha de la última detección de la suplantación de identidad, etc.

2. Seleccione un elemento de la tabla para abrir un panel de detalles que contenga información enriquecida sobre el par de dominios. La información incluye:
   - Por qué lo hemos detectado.
   - Lo que debe hacer.
   - Un resumen de dominio.
   - Datos WhoIs sobre el remitente.
   - Mensajes similares que hemos visto en su espacio empresarial del mismo remitente.

   Desde aquí, también puede Agregar o quitar el par de dominios de la lista de remitentes seguros de **AllowedToSpoof** .

   ![Captura de pantalla de un dominio en el panel de detalles de inteligencia empresarial de suplantación](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>Agregar o quitar un dominio de la lista de AllowedToSpoof

Agregue o quite un dominio de la lista AllowedToSpoof (remitente seguro) en el panel de detalles del par de inteligencia empresarial de suplantación de identidad (spoofing) para el par de dominios. Simplemente, establezca el botón de alternancia en consecuencia.

Permitir un par de dominios solo permite la combinación del dominio falso *y* la infraestructura de envío. No permite el correo electrónico del dominio falso desde ningún origen, ni tampoco permite el correo electrónico de la infraestructura de envío para cualquier dominio.

Por ejemplo, permite que el siguiente par de dominios envíe mensajes falsos a su organización:

- *Dominio falso*: gmail.com "
- *Infraestructura de envío* `tms.mx.com` :

Solo se permitirá la suplantación a correo electrónico de ese par de dominios. No se permiten otros remitentes que intenten imitar gmail.com. La inteligencia de identidad comprueba los mensajes de otros dominios de tms.mx.com.

## <a name="related-topics"></a>Temas relacionados

[Protección contra suplantación de identidad (phishing) en Microsoft 365](anti-spoofing-protection.md)
