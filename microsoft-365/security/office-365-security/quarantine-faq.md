---
title: Preguntas más frecuentes sobre la cuarentena
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Este tema contiene preguntas frecuentes y respuestas sobre la cuarentena hospedada.
ms.openlocfilehash: c61d2e3a9a6bcb847bf7e850e4bb13a7f1160d59
ms.sourcegitcommit: 550ea6f093ec35182e7c65a2811e9bfb07ec7d01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2019
ms.locfileid: "38039009"
---
# <a name="quarantine-faq"></a>Preguntas más frecuentes sobre la cuarentena

Este tema contiene preguntas frecuentes y respuestas sobre la cuarentena hospedada. Las respuestas son válidas para clientes de Microsoft Exchange Online y de Exchange Online Protection.
  
 **P. ¿Cómo puedo administrar los mensajes de malware en cuarentena en cuarentena?**
  
Debe usar el centro de seguridad &amp; y cumplimiento para ver y trabajar con mensajes que se enviaron a cuarentena porque contienen malware. Para obtener más información, vea [cuarentena de mensajes de correo electrónico en Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
 **P. ¿Cómo se configura el servicio para enviar mensajes de correo no deseado en cuarentena a la cuarentena?**
  
R. De manera predeterminada los mensajes de contenido filtrado se envían a los destinatarios de la carpeta de correo electrónico no deseado. Sin embargo, los administradores pueden configurar las directivas de filtro de contenido para enviar mensajes de correo no deseado en cuarentena a la cuarentena. Para obtener más información acerca de las diferentes acciones que pueden realizarse en los mensajes con filtrado de contenido, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
  
 **P. ¿Cuenta el servicio con administración de usuario final y administrador de los mensajes de correo no deseado puestos en cuarentena?**
  
R. Como administrador, puede buscar y ver detalles de los mensajes de correo electrónico en cuarentena en el Centro de administración de Exchange (EAC). Tras encontrar el mensaje, puede publicarlo a usuarios específicos y, opcionalmente, identificarlo como falso positivo (deseado) al equipo de análisis de correo no deseado de Microsoft. Para más información, vea [Buscar y liberar mensajes en cuarentena como un administrador](find-and-release-quarantined-messages-as-an-administrator.md).
  
Como usuario final, puede administrar sus propios mensajes de correo no deseado en cuarentena a través de: 
  
- La interfaz de usuario de cuarentena de correo no deseado. Para más información, vea [Find and Release Quarantined Messages (End Users)](https://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).
        
 **Q. ¿Cómo puede conceder acceso al correo no deseado en cuarentena a mis usuarios finales?**
  
A. Para poder tener acceso a la cuarentena de correo no deseado del usuario final, los usuarios finales deben tener un identificador de usuario y una contraseña de Office 365 válidos. Los clientes de EOP que protegen los buzones locales deben ser usuarios de correo electrónico válidos creados mediante la sincronización de directorios o el EAC. Para obtener más información acerca de la administración de usuarios, los administradores de EOP pueden hacer referencia a [administrar usuarios de correo en EOP](manage-mail-users-in-eop.md). Para clientes independientes de EOP, se recomienda usar la sincronización de directorios y habilitar el bloqueo perimetral basado en directorios; para obtener más información, vea [usar bloqueo perimetral basado en directorios para rechazar mensajes enviados a destinatarios no válidos](https://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).
  
 **P. ¿Se puede enviar otra cosa que no sea correo no deseado a la cuarentena?**
  
R. Sí. Los mensajes que coinciden con una regla de flujo de correo (también denominada regla de transporte) junto con los mensajes identificados como phish también se pueden enviar a la cuarentena de administrador, si esa es la acción configurada. La cuarentena del usuario final es únicamente para correo no deseado.
  
 **P. ¿Durante cuánto tiempo se guardan los mensajes en cuarentena?**
  
A. De forma predeterminada, los mensajes en cuarentena de correo no deseado se mantienen en cuarentena durante 30 días, mientras que los mensajes en cuarentena que coinciden con una regla de flujo de correo se mantienen en cuarentena durante un máximo de 30 días en función del período de retención establecido en la Directiva de filtro de contenido predeterminada. Finalizado este tiempo, los mensajes se eliminan y ya no se pueden recuperar. No se puede configurar el período de retención de los mensajes en cuarentena que coinciden con una regla de flujo de correo. Sin embargo, es posible reducir el período de retención de los mensajes de correo no deseado en cuarentena mediante la configuración **Mantener el correo no deseado durante (días)** en las directivas de filtro de contenido. Para obtener más información, vea [Configurar las directivas de filtro de correo no deseado](configure-your-spam-filter-policies.md).
  
 **Q. ¿Puedo liberar o informar de más de un mensaje en cuarentena a la vez?**
  
A. Sí, se pueden liberar hasta 100 mensajes al mismo tiempo en el portal de cuarentena. Además, los administradores pueden crear un script de Windows PowerShell remoto para realizar esta tarea. Use el cmdlet [Get-QuarantineMessage](https://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para buscar los mensajes y el cmdlet [Release-QuarantineMessage](https://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) para liberarlos. 
  
 **P. ¿Se admiten caracteres comodín al buscar mensajes en cuarentena? ¿Puedo buscar mensajes en cuarentena para un dominio específico?**
  
A. No se admiten caracteres comodín al especificar los criterios de búsqueda en el Centro de administración de Exchange. Por ejemplo, al buscar un remitente, debe especificar la dirección de correo electrónico completa.
  
Con Windows PowerShell remoto, los administradores pueden especificar el cmdlet [Get-QuarantineMessage](https://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para buscar los mensajes en cuarentena de un dominio específico (por ejemplo, contoso.com): 
  
```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

Los resultados se pueden transmitir al cmdlet [Release-QuarantineMessage](https://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx). Incluya el parámetro -ReleaseToAll para liberar el mensaje a todos los destinatarios. Una vez que se libera un mensaje, no puede volver a liberarse. 
  
```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


