---
title: Crear reglas de correo electrónico para protegerse contra ransomware
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
description: Obtenga información sobre cómo crear reglas de correo electrónico para evitar ransomware.
ms.openlocfilehash: 3b45af71aa26beb31e21f5db662091f46343f97d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926119"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Crear reglas de correo electrónico para evitar ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 ayuda a proteger su empresa contra ransomware al impedir que se abran archivos potencialmente peligrosos, como JavaScript, lotes y ejecutables, en Outlook. Para aumentar este nivel de protección mediante la adición de reglas que bloquean o advierten sobre tipos de archivos adicionales, siga estos pasos.

## <a name="try-it"></a>¿Se atreve?

1. Desde el centro de administración en [https://admin.microsoft.com](https://admin.microsoft.com) , elija **Exchange** en Centros **de administración.**
1. En el menú de la izquierda, elija flujo **de correo.**
1. En la pestaña reglas, elija la flecha situada junto al símbolo más (+) y, a continuación, **elija Crear una nueva regla.**
1. En la **nueva página de** reglas, escriba un nombre para la regla, desplácese hasta la parte inferior y, a continuación, elija Más **opciones.**
1. En **Aplicar esta regla si**, seleccione Cualquier dato **adjunto** y, a continuación, seleccione la extensión de archivo incluye **estas palabras.**
1. En el cuadro **debajo** de especificar palabras o frases, escriba las extensiones de archivo a las que desea aplicar la regla, como las extensiones de archivo que pueden contener macros. Use el símbolo más (+) para agregarlos de uno en uno.

    Obtenga más información sobre los tipos de archivo leyendo [Proteger contra ransomware.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)

1. Desplácese hacia abajo para revisar la lista y, a continuación, elija **Aceptar**.
1. En la **página de nueva** regla, elija agregar **condición** y, a continuación, elija una condición en Hacer **lo siguiente.**
1. Tiene muchas opciones de regla entre las que elegir, pero en este ejemplo elegiremos notificar al **destinatario con un mensaje.**
1. Escriba el texto del mensaje para la notificación y, a continuación, elija **Aceptar.**
1. Opcional: en la página  **de** nueva regla, elija Agregar excepción y escriba los detalles de las excepciones a la regla, como los mensajes de remitentes de confianza.
1. En la página de nueva regla, elija **Guardar** y revise la información de resumen de la regla proporcionada.