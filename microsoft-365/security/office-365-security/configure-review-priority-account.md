---
title: Configuración y revisión de cuentas de prioridad en Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 3/21/2022
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Obtenga información sobre cómo identificar personas críticas en una organización y agregar la etiqueta de cuenta de prioridad para proporcionarles protección adicional.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d48b1ec6c3ee0ba5f73d99b097303a8c989d545e
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759544"
---
# <a name="configure-and-review-priority-accounts-in-microsoft-defender-for-office-365"></a>Configuración y revisión de cuentas de prioridad en Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En todas las organizaciones, hay personas críticas, como ejecutivos, líderes, administradores u otros usuarios que tienen acceso a información confidencial, propietaria o de alta prioridad. Puede etiquetar estos usuarios dentro de Microsoft Defender para Office 365 como cuentas prioritarias, lo que permite a los equipos de seguridad priorizar su enfoque en estas personas críticas. Con la protección diferenciada para las cuentas de prioridad, los usuarios etiquetados como cuentas de prioridad recibirán un mayor nivel de protección contra amenazas.

Las cuentas de prioridad son objetivo de los atacantes con más frecuencia y, por lo general, se atacan con técnicas más sofisticadas. La protección diferenciada para las cuentas de prioridad se centra en este conjunto de usuarios específico y proporciona un mayor nivel de protección mediante modelos de aprendizaje automático mejorados. Esta diferenciación en el aprendizaje y el control de mensajes proporciona el nivel más alto de protección para estas cuentas y ayuda a mantener una tasa baja de falsos positivos, ya que una alta tasa de falsos positivos también puede tener un impacto negativo en estos usuarios.

## <a name="configure-priority-account-protection"></a>Configuración de la protección de la cuenta de prioridad

La protección de la cuenta de prioridad está activada de forma predeterminada para los usuarios críticos identificados previamente. Sin embargo, el administrador de seguridad de su organización también puede activar la protección de la cuenta de prioridad siguiendo estos pasos:

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Configuración** \> **Correo electrónico & protección** de **la cuenta de prioridad** de colaboración\>. 

2. Active **La protección de la cuenta de prioridad**. 

    > [!div class="mx-imgBorder"]
    > ![Active La protección de la cuenta de prioridad.](../../media/mdo-priority-account-protection.png)

> [!NOTE]
> No se recomienda deshabilitar o desactivar la protección de la cuenta de prioridad.  

### <a name="enable-the-priority-account-tag"></a>Habilitación de la etiqueta de cuenta de prioridad

Microsoft Defender para Office 365 admite cuentas de prioridad como etiquetas que se pueden usar como filtros en alertas, informes e investigaciones.

Para obtener más información, consulte [Etiquetas de usuario en Microsoft Defender para Office 365](user-tags.md).

## <a name="review-differentiated-protection-in-threat-protection-status-report-threat-explorer-and-email-entity-page"></a>Revisión de la protección diferenciada en el informe de estado de protección contra amenazas, el Explorador de amenazas y la página de entidad de correo electrónico

### <a name="threat-protection-status-report"></a>Informe de estado de protección contra amenazas

El informe de estado de protección contra amenazas es una vista única que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por Microsoft Defender para Office 365. 

Para ver el informe en el portal de Microsoft 365 Defender, vaya a **Informes** \> **por correo electrónico & colaboración** \> **Correo electrónico & informes de colaboración**. En la página **Informes de colaboración de & por correo electrónico** , busque **Estado de protección contra amenazas** y, a continuación, seleccione **Ver detalles**. Vaya a la **vista Spam**, **la vista Phish** o **la vista Malware** y, a continuación, use el icono de filtro para seleccionar **Protección de la cuenta de prioridad**.

### <a name="threat-explorer"></a>Explorador de amenazas 

El filtro de contexto del Explorador de amenazas ayuda a buscar correos electrónicos en los que la protección de la cuenta de prioridad estaba implicada en la detección del mensaje. Esto permite que los equipos de operaciones de seguridad puedan ver el valor proporcionado por esta protección. Todavía puede filtrar los mensajes por etiqueta de cuenta de prioridad para buscar todos los mensajes del conjunto específico de usuarios. 

Para ver la protección adicional, en el portal de Microsoft 365 Defender, vaya a **Correo electrónico &** **explorador** de colaboración\>, seleccione **Contexto** en la lista desplegable y, a continuación, active la casilla situada junto a **Protección de la cuenta de prioridad**. 

> [!div class="mx-imgBorder"]
> ![Filtro de contexto en el Explorador de amenazas.](../../media/threat-explorer-context-filter.png)

### <a name="email-entity-page"></a>Página de la entidad de correo electrónico

La página de la entidad de correo electrónico está disponible en el portal de Microsoft 365 Defender en <https://security.microsoft.com> **Correo electrónico &** **explorador** de colaboración\>. En **el Explorador**, seleccione el asunto de un correo electrónico que está investigando. Se mostrará una barra dorada en la parte superior del control flotante de correo electrónico para ese correo. Seleccione esta opción para ver la nueva página.

Las pestañas de la parte superior de la página de entidad le permitirán investigar el correo electrónico de forma eficaz. Haga clic en la pestaña **Análisis** . La protección de la cuenta de prioridad aparece ahora en **Detalles de detección de amenazas**. 

## <a name="more-information"></a>Más información

- [Etiquetas de usuario en Microsoft Defender para Office 365](user-tags.md)
- [Administrar y supervisar cuentas prioritarias](../../admin/setup/priority-accounts.md)
