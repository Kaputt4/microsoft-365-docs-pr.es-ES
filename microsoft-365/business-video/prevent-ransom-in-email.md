---
title: Crear reglas de correo electrónico para protegerse contra ransomware
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Aprenda a crear reglas de correo electrónico para evitar ransomware.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580503"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Crear reglas de correo electrónico para evitar ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 ayuda a proteger su negocio contra ransomware al impedir que se abran en Outlook archivos potencialmente peligrosos, como JavaScript, por lotes y ejecutables. Para aumentar este nivel de protección mediante la adición de reglas que bloquean o advierten de tipos de archivos adicionales, siga estos pasos.

## <a name="try-it"></a>¿Se atreve?

1. En el Centro de administración de [https://admin.microsoft.com](https://admin.microsoft.com) , elija Exchange **en** Centros **de administración**.
1. En el menú de la izquierda, elija **flujo de correo**.
1. En la pestaña reglas, elija la flecha situada junto al símbolo más (+) y, a continuación, **elija Crear una nueva regla**.
1. En la **página nueva regla,** escriba un nombre para la regla, desplácese hasta la parte inferior y, a continuación, elija **Más opciones**.
1. En **Aplicar esta regla si**, seleccione Cualquier dato **adjunto** y, a continuación, seleccione extensión de archivo incluye estas **palabras**.
1. En el cuadro de especificar **palabras** o frases, escriba las extensiones de archivo a las que desea que se aplique la regla, como las extensiones de archivo que pueden contener macros. Usa el símbolo más (+) para agregarlos uno a la vez.

    Para obtener más información acerca de los tipos de archivo, [lea Proteger contra ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).

1. Desplácese hacia abajo para revisar la lista y, a continuación, elija **Aceptar**.
1. En la **página nueva regla,** elija **agregar condición** y, a continuación, elija una condición en Hacer **lo siguiente.**
1. Tiene muchas opciones de regla entre las que elegir, pero en este ejemplo elegiremos notificar al **destinatario con un mensaje**.
1. Escriba el texto del mensaje para la notificación y, a continuación, elija **Aceptar**.
1. Opcional: en la página  **nueva regla,** elija Agregar excepción y escriba los detalles de las excepciones a la regla, como los mensajes de remitentes de confianza.
1. En la página nueva regla, elija **Guardar** y revise la información de resumen de regla proporcionada.