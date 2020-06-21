---
title: Entrega dinámica y vista previa con datos adjuntos seguros de ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Cuando configure las directivas de datos adjuntos seguros de ATP, elija Entrega dinámica para evitar retrasos en los mensajes y permitir que los usuarios puedan obtener una vista previa de los datos adjuntos mientras se examinan.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b22112617ecba191c7ee8d7daab0de3cde1bf8c3
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819357"
---
# <a name="dynamic-delivery-and-previewing-with-atp-safe-attachments"></a>Entrega dinámica y vista previa con datos adjuntos seguros de ATP

## <a name="basic-features-of-dynamic-delivery"></a>Características básicas de la entrega dinámica

La entrega dinámica es una opción que se puede seleccionar para [Datos adjuntos seguros de ATP](atp-safe-attachments.md). Lea este artículo para obtener información sobre la entrega dinámica y las funciones de vista previa de datos adjuntos en [Datos adjuntos seguros de ATP en Office 365](atp-safe-attachments.md).

Cuando se [configuran directivas de Datos adjuntos seguros de ATP ](set-up-atp-safe-attachments-policies.md) para su organización, hay varias opciones sobre cómo se manejan los datos adjuntos de correo. Estas incluyen **Bloquear**, **Reemplazar** y **Entrega dinámica**. Dependiendo de cómo estén configuradas las directivas de datos adjuntos seguros de ATP, los destinatarios del correo podrían experimentar un retraso mínimo en la entrega del correo mientras se analizan sus datos adjuntos. Para evitar retrasos en los mensajes, elija **Entrega dinámica**.

## <a name="how-dynamic-delivery-works"></a>Cómo funciona la Entrega dinámica

La Entrega dinámica elimina los retrasos del correo electrónico enviando el cuerpo de un mensaje de correo al destinatario con un marcador de posición para cada dato adjunto. El marcador de posición permanece hasta que [Datos adjuntos seguros de ATP](atp-safe-attachments.md) analiza la copia de los datos y determina que son seguros.

- A medida que se comprueba cada dato adjunto, pasará a estar disponible para abrir o descargar.

- Si los datos adjuntos se determinan como malintencionados, se envían a cuarentena, donde alguien del equipo de seguridad de su organización (como un administrador global o un administrador de seguridad) puede [administrar los mensajes en cuarentena en Office 365](manage-quarantined-messages-and-files.md).

La mayoría de los documentos PDF y de Office se pueden ver en la vista previa en modo seguro mientras se realiza el análisis de ATP. Si un dato adjunto no es compatibles con la vista previa de Entrega dinámica, los destinatarios del correo ven un marcador de posición de datos adjuntos hasta que se complete el análisis de Datos adjuntos seguros de ATP.

> [!TIP]
> Si está usando un dispositivo móvil y los PDF no se representan en primer lugar en el previsualizador de entrega dinámica, intente iniciar sesión con el explorador móvil.

Con la Entrega dinámica, los usuarios pueden leer y responder a sus mensajes de correo inmediatamente, mientras se analizan los datos adjuntos.

ATP el análisis de datos adjuntos seguros se realiza en la misma región en la que residen los datos de Microsoft 365. Para más información sobre la geografía de centros de datos, consulte [¿Dónde se encuentran los datos?](https://products.office.com/where-is-your-data-located?geo=All)

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>¿Qué ocurre cuando alguien reenvía un correo electrónico que contiene datos adjuntos?

Supongamos que una organización usa la Entrega dinámica para su [directiva de Datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md) y alguien recibe un correo que contiene datos adjuntos. Ahora suponga que la persona reenvía el mensaje de correo a otro usuario. ¿Qué ocurre? Depende de si los destinatarios adicionales están incluidos en las directivas de Datos adjuntos seguros de ATP.

- Si un destinatario está cubierto por una directiva de Datos adjuntos seguros de ATP con la opción de Entrega dinámica, el destinatario ve el marcador de posición, con la capacidad de tener una vista previa de los archivos compatibles.

- Si un destinatario no se encuentra incluido en la directiva de Datos adjuntos seguros de ATP, el correo y los datos adjuntos se enviarán sin análisis de Datos adjuntos seguros de ATP ni marcadores de posición de datos adjuntos.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>¿Qué se necesita para que funcione la Entrega dinámica?

- La organización debe tener la [Protección contra amenazas avanzada de Office 365](office-365-atp.md)

- Se deben definir directivas para Datos adjuntos seguros de ATP con la opción de Entrega dinámica (consulte [Configurar directivas de Datos adjuntos seguros de ATP en Office 365](set-up-atp-safe-attachments-policies.md))

- El correo de la organización debe estar alojado en Office 365. Aunque [se puede usar la Protección contra amenazas avanzada de Office 365 con cualquier agente de transferencia de correo SMTP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (como Exchange Server), la opción de Entrega dinámica para Datos adjuntos seguros de ATP requiere que el correo electrónico de su organización esté alojado en Office 365. Si su correo electrónico no se hospeda en Office 365, elija otra [opción de directiva de Datos adjuntos seguros de ATP](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), como **Bloquear**.

## <a name="additional-considerations"></a>Consideraciones adicionales

Hay ciertos escenarios en los que la Entrega dinámica no es compatible. Entre ellas se incluyen las siguientes:

- Mensajes de correo que están en carpetas públicas

- Mensajes de correo que se enrutan y vuelven al buzón del usuario con reglas personalizadas

- Mensajes de correo que se mueven (de forma automática o manual) fuera del buzón alojado y a otras ubicaciones, incluidas carpetas archivadas

- Mensajes de correo eliminados

- La carpeta de búsqueda del buzón de un usuario que está en un estado de error

- Entornos en los que un administrador de Exchange Online ha habilitado Exclaimer. Para resolver esto, consulte [Los mensajes con datos adjuntos no se entregan cuando se usa la Entrega dinámica de ATP y Exclaimer](https://support.microsoft.com/help/4014438)

- Mensajes cifrados con [Extensiones seguras multipropósito de correo electrónico en Internet (S/MIME)](s-mime-for-message-signing-and-encryption.md))

- En casos en los que no se admite la Entrega dinámica, los Datos adjuntos seguros de ATP no analizarán mensajes de correo. Sin embargo, se comprobará la entrega de mensajes de correo con datos adjuntos que contengan direcciones URL, dependiendo de cómo estén configuradas las [directivas de Vínculos seguros de ATP](set-up-atp-safe-links-policies.md). En estos casos, se comprueban las direcciones URL de los mensajes de correo y los archivos de Office.
