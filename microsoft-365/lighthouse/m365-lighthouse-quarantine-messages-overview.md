---
title: Introducción a los mensajes en cuarentena en Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: shcallaw
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, aprenda a administrar los mensajes en cuarentena.
ms.openlocfilehash: fcf9978ccbc72e1913e9015a8de40aa6da498394
ms.sourcegitcommit: 23a53b5c5e372a2a7ad5e175850224d3d464f6dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2022
ms.locfileid: "67055908"
---
# <a name="overview-of-quarantined-messages-in-microsoft-365-lighthouse"></a>Introducción a los mensajes en cuarentena en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse le permite ver información e información sobre los correos electrónicos en cuarentena en todos los inquilinos del cliente. Desde una sola vista, puede evaluar los correos electrónicos en cuarentena y realizar las acciones adecuadas. Los datos están disponibles si el inquilino ha implementado Exchange Online Protection (EOP) y Microsoft Defender para Office365 Plan 1 (MDO).

Puede acceder a la información seleccionando **Inicio** en el panel de navegación izquierdo o seleccionando Protección de **datos** en el panel de navegación izquierdo para abrir la página Mensajes en cuarentena.

## <a name="quarantined-messages-page"></a>Página mensajes en cuarentena

En esta página, puede ver estadísticas consolidadas en los inquilinos de los clientes, datos de tendencias para el tipo y volumen de datos de cuarentena e información relacionada con las colas de cuarentena en inquilinos de clientes individuales.

La sección **Estado de los mensajes** proporciona una vista consolidada entre los inquilinos aptos incorporados actualmente a Lighthouse. La vista incluye

- Total de mensajes en cuarentena
- Total de mensajes en espera de revisión
- Mensajes que se aproximan actualmente al límite de cuarentena predeterminado de 30 días y que están a punto de quitarse automáticamente (expiran)
- Mensajes que se han liberado de la cuarentena
- Número total de buzones afectados en todos los inquilinos

Los datos reflejan los últimos 30 días; sin embargo, puede usar el filtro **Intervalo de tiempo** para modificar la vista.

La sección **Motivo de cuarentena** contiene un desglose de los recuentos de cuarentena por Exchange Online Protection (EOP) y el tipo de directiva del plan 1 (MDO) de Microsoft Defender para Office365. Estos tipos incluyen

- Malware
- Suplantación de identidad (phishing)
- Suplantación de identidad de alta confianza
- Correo no deseado
- Email masivas

La lista de cuarentena es una vista ordenable de la información de cuarentena por inquilino. En esta vista, puede filtrar por la siguiente información:

- **Motivo de cuarentena:** Cualquiera, Malware, Phish, Phish de alta confianza, Spam, Bulk Email
- **Tipo de directiva:** Cualquiera, Antimalware, Anti-phishing, Anti-spam, Datos adjuntos seguros, Regla de transporte, Desconocido
- **A punto de expirar:** Cualquiera, Hoy, dentro de dos días, dentro de siete días

También puede ajustar las columnas y ordenar los datos en función del inquilino, el estado del mensaje y las fechas de expiración.

:::image type="content" source="../media/m365-lighthouse-data-protection/quarantine-email-page.png" alt-text="Página Mensajes de cuarentena en Microsoft 365 Lighthouse" lightbox="../media/m365-lighthouse-data-protection/quarantine-email-page.png":::

La opción **Copiar vínculo a mensajes en Microsoft** **365 Defender** proporciona un vínculo a Microsoft 365 Defender portal donde puede acceder a la cola de cuarentena de correo electrónico de su inquilino y administrarla. Debe autenticarse para poder realizar cualquier acción.

## <a name="related-content"></a>Contenido relacionado

[Mensajes de correo electrónico en cuarentena](../security/office-365-security/quarantine-email-messages.md) (artículo)\
[Recomendaciones de Microsoft para EOP y Defender para Office 365 configuración de seguridad](../security/office-365-security/recommended-settings-for-eop-and-office365.md) (artículo)\
[Introducción a Exchange Online Protection (EOP)](../security/office-365-security/exchange-online-protection-overview.md) (artículo)
