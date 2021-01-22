---
title: Administrar vínculos seguros
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo administrar vínculos seguros para proteger su empresa de sitios malintencionados.
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928026"
---
# <a name="manage-safe-links"></a>Administrar vínculos seguros

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender para Office 365 , anteriormente denominado ATP de Microsoft 365, o Protección contra amenazas avanzada, ayuda a proteger su empresa contra sitios malintencionados cuando las personas hacen clic en vínculos en aplicaciones de Office.

## <a name="try-it"></a>¿Se atreve?

1. Vaya al Centro [de administración](https://admin.microsoft.com)y seleccione **Configurar.**
1. Desplácese hacia abajo para **aumentar la protección contra amenazas avanzadas.** Seleccione **Ver,** **Administrar y,** a continuación, **Vínculos seguros de ATP.**
1. En **Directivas que se aplican a toda la organización,** elija la **directiva** predeterminada y, a continuación, seleccione el **icono** Editar.
1. Escriba una dirección URL que desee bloquear.
1. Seleccione **Usar vínculos seguros en aplicaciones de Office, Office para iOS y Android;** seleccione **No realizar un seguimiento de cuándo los usuarios hacen clic en vínculos seguros;** y seleccione **No permitir a los usuarios hacer clic a través de vínculos seguros a la dirección URL original.** Es posible que ya se seleccionen si configura la directiva predeterminada. Seleccione **Guardar**.
1. En **Directivas que se aplican a destinatarios específicos,** elija Regla de vínculos seguros **recomendada** y, a continuación, seleccione el **icono** Editar.
1. Seleccione **la** configuración, desplácese hacia abajo, escriba la dirección URL que no desea que se active y, a continuación, seleccione el **icono** Agregar.
1. Seleccione **aplicado y,** a continuación, seleccione el nombre de dominio. Seleccione los dominios adicionales a los que desee aplicar la regla. Seleccione **agregar**, **aceptar** y, a continuación, **guardar**.

Los vínculos seguros de ATP ya están configurados. Espere hasta 30 minutos para que los cambios entren en vigor.

Cuando un usuario recibe un correo electrónico con vínculos, se examinan los vínculos. Si los vínculos se consideran seguros, se podrán hacer clic en ellos. Sin embargo, si el vínculo está en la lista de bloqueados, los usuarios verán un mensaje que indica que se ha bloqueado.