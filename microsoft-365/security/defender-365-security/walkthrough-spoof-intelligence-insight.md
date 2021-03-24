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
description: Los administradores pueden aprender cómo funciona la información de inteligencia de suplantación. Pueden determinar rápidamente qué remitentes envían correo electrónico legítimamente a sus organizaciones desde dominios que no pasan comprobaciones de autenticación de correo electrónico (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2b48b8540fb71404a0636120a5884d381b08cd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070936"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Tutorial: información sobre la suplantación de inteligencia en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con Defender para Office 365, puede usar la información de inteligencia de suplantación de identidad para determinar rápidamente qué remitentes externos le envían legítimamente correo electrónico no autenticado (mensajes de dominios que no pasan comprobaciones de SPF, DKIM o DMARC).

Al permitir que los remitentes externos conocidos envíen mensajes falsos desde ubicaciones conocidas, puede reducir los falsos positivos (buen correo electrónico marcado como malo). Al supervisar los remitentes suplantados permitidos, proporciona un nivel de seguridad adicional para evitar que los mensajes no seguros lleguen a la organización.

Para obtener más información sobre informes e información, vea Informes e información en el Centro de [seguridad y & cumplimiento](reports-and-insights-in-security-and-compliance.md).

Este tutorial es uno de varios para el Centro de seguridad & cumplimiento. Para obtener información sobre cómo navegar por informes e información, consulte los tutoriales de la [sección Temas relacionados.](#related-topics)

> [!NOTE]
> La información de inteligencia suplantación muestra datos de los últimos 7 días. La [directiva de inteligencia](learn-about-spoof-intelligence.md) suplantación de identidad y el cmdlet [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) correspondiente en Exchange Online PowerShell muestran datos de los últimos 30 días. [Get-SpoofMailReport](/powershell/module/exchange/get-spoofmailreport) muestra datos durante un máximo de 90 días.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Panel de seguridad,** use <https://protection.office.com/searchandinvestigation/dashboard> .

  Puede ver la información de inteligencia de suplantación desde más de un panel en el Centro de seguridad & cumplimiento. Independientemente del panel que estés viendo, la información proporciona los mismos detalles y te permite realizar rápidamente las mismas tareas.

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - **Administración de organizaciones**
  - **Administrador de seguridad**
  - **Lector de seguridad**
  - **Lector global**

  Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Nota:** Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft  365 proporciona a los usuarios los permisos necesarios en el Centro de seguridad & cumplimiento y permisos para otras características de Microsoft 365. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

- Habilita y deshabilita la inteligencia de suplantación de identidad en directivas contra suplantación de identidad en Microsoft Defender para Office 365. La inteligencia de suplantación está habilitada de forma predeterminada. Para obtener más información, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

- Para usar la inteligencia de suplantación de identidad para supervisar y administrar remitentes que le envían mensajes no autenticados, vea [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Abra la información de inteligencia de suplantación en el Centro de seguridad & cumplimiento

1. En el Centro de seguridad & cumplimiento, vaya al Panel **de administración de** \> **amenazas.**

2. En la **fila Insights,** busque uno de los siguientes elementos:

   - **Probable suplantación** de dominio en los últimos siete días: esta información indica que la inteligencia suplantada está habilitada (está habilitada de forma predeterminada).
   - **Habilitar protección contra** suplantación: esta información indica que la inteligencia de suplantación está deshabilitada y hacer clic en la información le permite habilitar la inteligencia de suplantación.

3. La información del panel muestra información como esta:

   ![Captura de pantalla de información de inteligencia suplantación](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esta información tiene dos modos:

   - **Modo de información:** si la suplantación de inteligencia está habilitada, la información muestra cuántos mensajes se han afectado por nuestras capacidades de inteligencia suplantada en los últimos siete días.
   - **Modo de** suplantación: si la inteligencia suplantada está  deshabilitada, la información muestra cuántos mensajes se habrían visto afectados por nuestras capacidades de inteligencia suplantada en los últimos siete días.

   En cualquier caso, los dominios suplantados que se muestran en la información se separan en dos categorías: **dominios** sospechosos y **dominios no sospechosos.**

   - **Los dominios sospechosos** incluyen:

     - Suplantación de confianza alta: en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos muy seguros de que los dominios están suplantando la suplantación y es más probable que los mensajes de estos dominios sean malintencionados.

     - Suplantación de confianza moderada: en función de los patrones de envío históricos y la puntuación de reputación de los dominios, estamos moderadamente seguros de que los dominios están suplantando y que los mensajes enviados desde estos dominios son legítimos. Los falsos positivos son más probables en esta categoría que la suplantación de confianza alta.

   **Dominios no sospechosos:** el dominio no pudo comprobar la autenticación explícita de correo [electrónico SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)). Sin embargo, el dominio pasó nuestras comprobaciones implícitas de autenticación de correo electrónico ([autenticación compuesta](email-validation-and-authentication.md#composite-authentication)). Como resultado, no se ha realizado ninguna acción contra la suplantación en el mensaje.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>Ver información detallada sobre dominios sospechosos desde la información de inteligencia de suplantación

1. En la información de inteligencia suplantada, haga clic en **Dominios** sospechosos o Dominios no sospechosos para ir a la **página Spoof intelligence insight.**  La **página Spoof Intelligence insight** contiene la siguiente información:

   - **Dominio suplantado:** dominio del usuario suplantado que se muestra en el **cuadro** De de los clientes de correo electrónico. Esta dirección también se conoce como `5322.From` la dirección.
   - **Infraestructura:** también conocida como la _infraestructura de envío_. El dominio encontrado en una búsqueda DNS inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen. Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).
   - **Recuento de** mensajes: el número de mensajes de la infraestructura de envío a la organización que contienen el dominio suplantado especificado en los últimos 7 días.
   - **Vista por última** vez: la última fecha en la que se recibió un mensaje de la infraestructura de envío que contiene el dominio suplantado.
   - **Tipo de suplantación:** este valor es **Externo**.
   - **¿Se permite suplantación?**: Los valores que se ven aquí son:
     - **Sí:** los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se permiten y no se tratan como correo electrónico suplantado.
     - **No:** los mensajes de la combinación del dominio del usuario suplantado y la infraestructura de envío se marcan como suplantados. La acción está controlada por la directiva anti phishing predeterminada o las directivas personalizadas contra suplantación de identidad (el valor predeterminado es Mover mensaje a la carpeta **correo no deseado**).

     Para obtener más información, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

2. Seleccione un elemento de la lista para ver detalles sobre el par de infraestructura de dominio y envío en un menú desplegable. La información incluye:
   - Por qué lo capturamos.
   - Lo que necesita hacer.
   - Un resumen de dominio.
   - WhoIs datos sobre el remitente.
   - Mensajes similares que hemos visto en el inquilino del mismo remitente.

   Desde aquí, también puede elegir agregar o quitar el par de infraestructura dominio/envío de la lista permitido para **suplantación** de remitente. Simplemente establece la alternancia según corresponda.

   ![Captura de pantalla de un dominio en el panel de detalles de Spoof intelligence insight](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>Agregar un dominio a la lista Permitido para suplantación de dominio

Agregar un dominio a la lista De suplantación de dominio de la información de  inteligencia suplantada solo permite la combinación del dominio suplantado y la infraestructura de envío. No permite el correo electrónico del dominio suplantado desde ningún origen, ni permite el correo electrónico de la infraestructura de envío para ningún dominio.

Por ejemplo, permite el siguiente dominio a la lista Permitido suplantación de dominio:

- **Dominio**: gmail.com
- **Infraestructura**: tms.mx.com

Solo se permitirá la suplantación de correo electrónico de ese par de infraestructura de dominio/envío. Otros remitentes que intentan suplantar gmail.com no están permitidos. Los mensajes de otros dominios de tms.mx.com se comprueban mediante la inteligencia de suplantación.

## <a name="related-topics"></a>Temas relacionados

[Protección contra la suplantación en Microsoft 365](anti-spoofing-protection.md)