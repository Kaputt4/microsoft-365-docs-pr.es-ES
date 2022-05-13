---
title: Registro de actividades del portal de mensajes cifrados
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 05/12/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Los registros de acceso están disponibles para los mensajes cifrados recuperados a través del portal de mensajes cifrados.
ms.openlocfilehash: 50656d1695d8fc3d6e81de6afc03b3f4e3c5ccee
ms.sourcegitcommit: 54bc063818779e351ca24f04ba571f762d85751d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "65393229"
---
# <a name="encrypted-message-portal-activity-log-by-microsoft-purview-advanced-message-encryption-preview"></a>Registro de actividad del portal de mensajes cifrado mediante Microsoft Purview Cifrado avanzado de mensajes (versión preliminar)

Los registros de acceso están disponibles para los mensajes encriptados a través del portal de mensajes encriptados que permite a su organización determinar cuándo los mensajes son leídos, y reenviados por sus destinatarios externos. Para asegurarse de que los registros están disponibles para los destinatarios externos, debe aplicar una plantilla de personalización de marca personalizada a los correos electrónicos protegidos enviados por su organización a destinatarios externos que exijan una experiencia de portal. Consulte [Incorporación de la marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md).

## <a name="enabling-message-access-audit-logs-in-powershell"></a>Habilitación de registros de auditoría de acceso a mensajes en PowerShell

El registro de acceso se puede habilitar mediante Exchange Online PowerShell. El parámetro *-EnablePortalTrackingLogs* de Set-IrmConfiguration especifica si se deben habilitar los registros de auditoría de acceso al portal de mensajes cifrados. Los valores admitidos son:

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
