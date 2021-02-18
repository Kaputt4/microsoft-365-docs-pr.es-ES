---
title: 'Tutorial: suplantación de información de inteligencia'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender cómo funciona la información de inteligencia de suplantación de seguridad. Pueden determinar rápidamente qué remitentes envían correo electrónico legítimamente a sus organizaciones desde dominios que no pasan comprobaciones de autenticación de correo electrónico (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 91cd26498b2a14166f1be10921b9d5b2ea8d583c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287976"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Tutorial: suplantación de información de inteligencia en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En las organizaciones de Microsoft 365 con Defender para Office 365, puede usar la información de inteligencia de suplantación de identidad para determinar rápidamente qué remitentes externos le envían legítimamente correo electrónico no autenticado (mensajes de dominios que no pasan comprobaciones SPF, DKIM o DMARC).

Al permitir que remitentes externos conocidos envíen mensajes suplantados desde ubicaciones conocidas, puede reducir los falsos positivos (correo electrónico bueno marcado como mal). Al supervisar los remitentes suplantados permitidos, se proporciona un nivel adicional de seguridad para evitar que los mensajes no seguros lleguen a la organización.

Para obtener más información acerca de informes e información, vea [Informes y perspectivas](reports-and-insights-in-security-and-compliance.md)en el Centro de & cumplimiento.

Este tutorial es uno de varios para el Centro de seguridad & cumplimiento. Para obtener información sobre cómo navegar por informes y perspectivas, consulta los tutoriales de la [sección Temas relacionados.](#related-topics)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Panel de** seguridad, use <https://protection.office.com/searchandinvestigation/dashboard> .

  Puede ver la información de inteligencia de suplantación desde más de un panel en el Centro de & cumplimiento. Independientemente del panel que estés viendo, la información proporciona los mismos detalles y te permite realizar rápidamente las mismas tareas.

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - **Administración de organizaciones**
  - **Administrador de seguridad**
  - **Lector de seguridad**
  - **Lector global**

  Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Nota:** agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft  365 proporciona a los usuarios los permisos necesarios en el Centro de seguridad & Cumplimiento y permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

- Habilita y deshabilita la inteligencia de suplantación de identidad en las directivas contra suplantación de identidad en Microsoft Defender para Office 365. La inteligencia de suplantación de seguridad está habilitada de forma predeterminada. Para obtener más información, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Para usar la inteligencia de suplantación de identidad para supervisar y administrar los remitentes que le envían mensajes no autenticados, consulte Configurar la inteligencia de suplantación de identidad en [Microsoft 365.](learn-about-spoof-intelligence.md)

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abrir la información de inteligencia de suplantación de seguridad en el Centro de & cumplimiento

1. En el Centro de & cumplimiento, vaya al Panel **de administración de** \> **amenazas.**

2. En la **fila Insights,** busque uno de los siguientes elementos:

   - **Dominios suplantados** probablemente en los últimos siete días: esta información indica que la inteligencia de suplantación de seguridad está habilitada (está habilitada de forma predeterminada).
   - **Habilitar la protección contra** la suplantación: esta información indica que la inteligencia de suplantación de seguridad está deshabilitada y al hacer clic en la información se permite habilitar la inteligencia de suplantación de seguridad.

3. La información del panel muestra información como esta:

   ![Captura de pantalla de información de inteligencia de suplantación de pantalla](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esta información tiene dos modos:

   - **Modo de información:** si la inteligencia de suplantación está habilitada, la información muestra cuántos mensajes se han afectado por nuestras capacidades de inteligencia de suplantación de voz en los últimos siete días.
   - **Modo de** suplantación: si la inteligencia de suplantación  de seguridad está deshabilitada, la información muestra cuántos mensajes se habrían visto afectados por nuestras capacidades de inteligencia de suplantación en los últimos siete días.

   En ambos casos, los dominios suplantados que se muestran en la información se separan en dos **categorías:** dominios sospechosos y **dominios no sospechosos.**

   - **Los dominios sospechosos** incluyen:

     - Suplantación de confianza alta: en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos muy seguros de que los dominios están suplantando la seguridad y que los mensajes de estos dominios son más propensos a ser malintencionados.

     - Suplantación de confianza moderada: en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos moderadamente seguros de que los dominios están suplantando la seguridad y de que los mensajes enviados desde estos dominios son legítimos. Los falsos positivos son más probables en esta categoría que la suplantación de identidad de confianza alta.

   **Dominios no sospechosos:** el dominio no superó las comprobaciones explícitas de autenticación de correo electrónico [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)). Sin embargo, el dominio pasó nuestras comprobaciones implícitas de autenticación de correo electrónico[(autenticación compuesta).](email-validation-and-authentication.md#composite-authentication) Como resultado, no se ha realizado ninguna acción contra la suplantación en el mensaje.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Ver información detallada sobre dominios sospechosos desde la información de inteligencia de suplantación de seguridad

1. En la información de inteligencia de  suplantación, haga clic en **Dominios** sospechosos o Dominios no sospechosos para ir a la página de información de **inteligencia de suplantación de** seguridad. La **página de información de inteligencia de** suplantación contiene la siguiente información:

   - **Dominio suplantado:** dominio del usuario suplantado que se muestra  en el cuadro De en los clientes de correo electrónico. Esta dirección también se conoce como `5322.From` dirección.
   - **Infraestructura:** también conocida como infraestructura _de envío._ El dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen. Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).
   - **Recuento de** mensajes: el número de mensajes de la infraestructura de envío a la organización que contienen el dominio suplantado especificado en los últimos 7 días.
   - **Última vez** que se vio: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el dominio suplantado.
   - **Tipo de suplantación** de seguridad : Este valor es **Externo**.
   - **¿Se permite la suplantación?**: Los valores que ve aquí son:
     - **Sí:** los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.
     - **No:** los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se marcan como suplantados. La acción se controla mediante la directiva contra suplantación de identidad predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado).**

     Para obtener más información, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Seleccione un elemento de la lista para ver los detalles sobre el par dominio/infraestructura de envío en un menú desplegable. La información incluye:
   - Por qué lo detectamos.
   - Lo que necesita hacer.
   - Un resumen de dominio.
   - Datos whoIs sobre el remitente.
   - Mensajes similares que hemos visto en su espacio empresarial del mismo remitente.

   Desde aquí, también puede elegir agregar o quitar el  par de infraestructura dominio/envío de la lista de permitidos de remitentes permitidos para suplantación de identidad. Simplemente establezca el botón de alternancia según corresponda.

   ![Captura de pantalla de un dominio en el panel de detalles de Spoof intelligence insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Agregar un dominio a la lista de permitidos para suplantación de nombres

Agregar un dominio a la lista de permitidos para suplantación de la información  de inteligencia de suplantación solo permite la combinación del dominio suplantado y la infraestructura de envío. No permite el correo electrónico del dominio suplantado de ningún origen, ni permite el correo electrónico de la infraestructura de envío para ningún dominio.

Por ejemplo, se permite el siguiente dominio a la lista De permitidos para suplantación de nombres:

- **Dominio:** gmail.com
- **Infraestructura:** tms.mx.com

Solo se permitirá la suplantación de correo electrónico de ese par de infraestructura de dominio/envío. Otros remitentes que intentan suplantar gmail.com no están permitidos. La inteligencia de suplantación de tms.mx.com comprueba los mensajes de otros dominios.

## <a name="related-topics"></a>Temas relacionados

[Protección contra la suplantación en Microsoft 365](anti-spoofing-protection.md)
