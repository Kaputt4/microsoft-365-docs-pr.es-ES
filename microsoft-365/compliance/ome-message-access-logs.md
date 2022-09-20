---
title: Registro de actividades del portal de mensajes cifrados
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 07/21/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Los registros de acceso están disponibles para los mensajes cifrados recuperados a través del portal de mensajes cifrados.
ms.openlocfilehash: 5d2733a39aff86a3ca6b0dd93809920a073c03b5
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67824033"
---
# <a name="encrypted-message-portal-activity-log-by-microsoft-purview-advanced-message-encryption"></a>Registro de actividad del portal de mensajes cifrado por Cifrado avanzado de mensajes de Microsoft Purview

Los registros de acceso están disponibles para los mensajes encriptados a través del portal de mensajes encriptados que permite a su organización determinar cuándo los mensajes son leídos, y reenviados por sus destinatarios externos. Para asegurarse de que los registros están disponibles para los destinatarios externos, debe aplicar una plantilla de personalización de marca personalizada a los correos electrónicos protegidos enviados por su organización a destinatarios externos que exijan una experiencia de portal. Consulte [Incorporación de la marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md).

## <a name="enabling-message-access-audit-logs-in-powershell"></a>Habilitación de registros de auditoría de acceso a mensajes en PowerShell

El registro de acceso se puede habilitar mediante [Exchange Online módulo de PowerShell V2](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps). El parámetro *-EnablePortalTrackingLogs* de Set-IrmConfiguration especifica si se deben habilitar los registros de auditoría de acceso al portal de mensajes cifrados. Los valores admitidos son:

- $true: Activar la característica de auditoría.
- $false: Desactivar la característica de auditoría

Ejemplo: Set-IrmConfiguration -EnablePortalTrackingLogs $true

Para más información, consulte [Set-IRMConfiguration (ExchangePowerShell)](/powershell/module/exchange/set-irmconfiguration).

## <a name="message-access-audit-information"></a>Información de auditoría de acceso a mensajes

El registro de acceso contiene entradas para los mensajes enviados a través del portal de mensajes cifrados para los siguientes tipos de actividad:

- Marca de tiempo de inicio de sesión de usuario externo y método de autenticación
- El usuario externo lee mensajes o datos adjuntos
- Descarga de datos adjuntos
- respuestas de correo y reenvío

Para obtener más información sobre el esquema de registro de acceso a mensajes, vea [Buscar en el registro de auditoría en el portal de cumplimiento](search-the-audit-log-in-security-and-compliance.md#encrypted-message-portal-activities).

## <a name="search-for-events-in-the-message-access-logs"></a>Búsqueda de eventos en los registros de acceso a mensajes

Para ver los eventos capturados en los registros de acceso a mensajes:

1. En el portal de cumplimiento Microsoft Purview, en **Soluciones**, seleccione **Auditar**.
1. En **Buscar**, haga clic en la lista desplegable **Actividades** y escriba actividades del portal de mensajes cifrados.
1. En actividades del portal de mensajes cifrados, seleccione los tipos de eventos que se usarán en la búsqueda. Establezca el intervalo de fechas de la búsqueda (el valor predeterminado es la semana anterior), también puede agregar opcionalmente un usuario determinado en su organización para la búsqueda. Cuando esté listo, seleccione **Buscar**.
1. Seleccione un evento de la lista para ver las propiedades de auditoría.
