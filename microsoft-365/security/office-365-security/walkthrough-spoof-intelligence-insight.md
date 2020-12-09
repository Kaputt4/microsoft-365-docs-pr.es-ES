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
ms.openlocfilehash: 9139a2b4c3c7ed8262f3d75b445defb869371d07
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602114"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Tutorial: información sobre inteligencia de inteligencia contra la simulación en Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En Microsoft 365 organizaciones con defender para Office 365, puede usar la información de inteligencia de inteligencia de suplantación para determinar rápidamente qué remitentes externos envían de forma legítima un correo no autenticado (mensajes de dominios que no pasan las comprobaciones SPF, DKIM o DMARC).

Al permitir que los remitentes externos conocidos envíen mensajes falsos desde ubicaciones conocidas, puede reducir los falsos positivos (correo electrónico bueno marcado como malo). Mediante la supervisión de los remitentes suplantados permitidos, se proporciona una capa de seguridad adicional para evitar que los mensajes no seguros lleguen a la organización.

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

  **Nota**: agregar usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

- Puede habilitar y deshabilitar inteligencia simulada en directivas antiphishing en Microsoft defender para Office 365. La inteligencia de identidad está habilitada de forma predeterminada. Para obtener más información, vea [Configure anti-phishing policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).

- Para usar inteligencia simulada para supervisar y administrar a los remitentes que le envían mensajes sin autenticar, consulte [configurar inteligencia de identidades en Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abrir el conocimiento de inteligencia de infalsificación en el centro de seguridad & cumplimiento

1. En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Dashboard.**

2. En la fila **información** , busque uno de los siguientes elementos:

   - **Dominios posiblemente suplantados en los últimos siete días**: esta visión indica que la inteligencia de suplantación está habilitada (está habilitada de forma predeterminada).
   - **Habilitar la protección contra la suplantación de identidad**: esta información indica que la inteligencia de suplantación está deshabilitada y al hacer clic en la visión, podrá habilitar la inteligencia de identidad.

3. El conocimiento del panel muestra la siguiente información:

   ![Captura de pantalla de la información sobre inteligencia de suplantación](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esta visión tiene dos modos:

   - **Modo Insight**: Si la inteligencia de identidad está habilitada, el conocimiento le muestra cuántos mensajes se vieron afectados por nuestras capacidades de inteligencia empresarial de suplantación en los últimos siete días.
   - **Mode if**: Si la inteligencia de identidad está deshabilitada, la información muestra el número de mensajes que se *verían* afectados por nuestras capacidades de inteligencia de suplantación en los últimos siete días.

   En cualquier caso, los dominios suplantados que se muestran en la información se separan en dos categorías: **dominios sospechosos** y **dominios no sospechosos**.

   - Entre los **dominios sospechosos** se incluyen:

     - Suplantación de confianza alta: según los patrones de envío históricos y la puntuación de reputación de los dominios, tenemos muy seguros que los dominios son suplantación de identidad y que los mensajes de estos dominios son más propensos a ser malintencionados.

     - Simulación de confianza moderada: según los patrones de envío históricos y la puntuación de reputación de los dominios, estamos muy seguros de que los dominios son suplantación de identidad y que los mensajes enviados desde estos dominios son legítimos. Los falsos positivos son más probables en esta categoría que la suplantación de confianza alta.

   **Dominios no sospechosos**: el dominio no superó la autenticación explícita del correo electrónico comprueba [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)). Sin embargo, el dominio pasó nuestras comprobaciones de autenticación de correo electrónico IMPLÍCITAS ([autenticación compuesta](email-validation-and-authentication.md#composite-authentication)). Como resultado, no se ha llevado a cabo ninguna acción contra la suplantación de identidad en el mensaje.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Ver información detallada sobre dominios sospechosos desde el conocimiento de inteligencia de suplantación de identidad

1. En el análisis de inteligencia de suplantación, haga clic en **dominios sospechosos** o en **dominios no sospechosos** para ir a la página de **información de inteligencia empresarial de suplantación de identidad** . La página de información de **inteligencia empresarial de suplantación** contiene la siguiente información:

   - **Dominio falso**: dominio del usuario suplantado que se muestra en el cuadro **de** de clientes de correo electrónico. Esta dirección también se conoce como `5322.From` dirección.
   - **Infraestructura**: también conocida como _infraestructura de envío_. El dominio que se encuentra en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen. Si la dirección IP de origen no tiene registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).
   - **Recuento de mensajes**: número de mensajes de la infraestructura de envío a la organización que contienen el dominio falso especificado en los últimos 7 días.
   - **Último visto**: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el dominio falso.
   - **Tipo de imitación**: este valor es **externo**.
   - ¿Se **permite la suplantación?**: los valores que aparecen aquí son los siguientes:
     - **Sí**: los mensajes de la combinación de dominio de usuario suplantado y infraestructura de envío están permitidos y no se tratan como correo electrónico falsificado.
     - **No**: los mensajes de la combinación de dominio de usuario suplantado y infraestructura de envío se marcan como falseados. La acción se controla mediante la Directiva antiphishing predeterminada o las directivas antiphishing personalizadas (el valor predeterminado es **mover el mensaje a la carpeta de correo electrónico no deseado**).

     Para obtener más información, vea [Configure anti-phishing policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Seleccione un elemento de la lista para ver los detalles sobre el par de dominio/infraestructura de envío en un control flotante. La información incluye:
   - Por qué lo hemos detectado.
   - Lo que debe hacer.
   - Un resumen de dominio.
   - Datos WhoIs sobre el remitente.
   - Mensajes similares que hemos visto en su espacio empresarial del mismo remitente.

   Desde aquí, también puede Agregar o quitar el par dominio/infraestructura de envío de la lista de **permitidos para el remitente de suplantación de identidad** . Simplemente, establezca el botón de alternancia en consecuencia.

   ![Captura de pantalla de un dominio en el panel de detalles de inteligencia empresarial de suplantación](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Adición de un dominio a la lista de suplantación permitida

La adición de un dominio a la lista de suplantación de identidad del conocimiento de inteligencia de inhabilitación solo permite la combinación del dominio falso *y* la infraestructura de envío. No permite el correo electrónico del dominio falso desde ningún origen, ni tampoco permite el correo electrónico de la infraestructura de envío para cualquier dominio.

Por ejemplo, permite el siguiente dominio para la lista de suplantación de permisos:

- **Dominio**: gmail.com
- **Infraestructura**: TMS.mx.com

Solo se permitirá la suplantación a un correo electrónico de ese par de dominio/infraestructura de envío. No se permiten otros remitentes que intenten imitar gmail.com. La inteligencia de identidad comprueba los mensajes de otros dominios de tms.mx.com.

## <a name="related-topics"></a>Temas relacionados

[Protección contra suplantación de identidad (phishing) en Microsoft 365](anti-spoofing-protection.md)
