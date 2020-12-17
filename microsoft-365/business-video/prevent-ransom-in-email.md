---
title: Crear reglas de correo electrónico para ransomware
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo crear reglas de correo electrónico para evitar el ransomware.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702447"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Crear reglas de correo electrónico para evitar ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 ayuda a proteger su empresa contra ransomware evitando que se abran en Outlook archivos potencialmente peligrosos, como JavaScript, Batch y ejecutables. Para aumentar este nivel de protección agregando reglas que bloqueen o avisen de tipos adicionales de archivos, siga estos pasos.

## <a name="try-it"></a>¿Se atreve?

1. Desde el centro de administración de [https://admin.microsoft.com](https://admin.microsoft.com) , elija **Exchange** en **centros de administración**.
1. En el menú de la izquierda, seleccione **flujo de correo**.
1. En la ficha reglas, elija la flecha situada junto al símbolo de signo más (+) y, a continuación, elija **crear una nueva regla**.
1. En la página **nueva regla** , escriba un nombre para la regla, desplácese hasta la parte inferior y, a continuación, elija **más opciones**.
1. En **aplicar esta regla si**, seleccione **cualquier dato adjunto** y, a continuación, seleccione la **extensión de archivo incluye estas palabras**.
1. En el cuadro situado debajo de **especificar palabras o frases**, escriba las extensiones de archivo a las que desea aplicar la regla, como las extensiones de archivo que pueden contener macros. Use el símbolo más (+) para agregarlas de una en una.

    Obtenga más información sobre los tipos de archivo leyendo [proteger contra ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).

1. Desplácese hacia abajo para revisar la lista y, a continuación, elija **Aceptar**.
1. En la página **nueva regla** , elija **Agregar condición** y, a continuación, elija una condición en **hacer lo siguiente**.
1. Tiene muchas opciones de regla para elegir, pero en este ejemplo elegiremos **notificar al destinatario con un mensaje**.
1. Escriba el texto del mensaje de la notificación y, a continuación, elija **Aceptar**.
1. Opcional: en la página **nueva regla** , elija **Agregar excepción** y escriba los detalles de las excepciones a la regla, como los mensajes de los remitentes de confianza.
1. En la página nueva regla, elija **Guardar** y revise la información de Resumen de la regla que se proporciona.