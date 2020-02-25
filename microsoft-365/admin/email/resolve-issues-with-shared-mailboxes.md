---
title: Resolver problemas con los buzones compartidos
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Pruebe estas soluciones si experimenta problemas con los buzones compartidos.
ms.openlocfilehash: b45c2eefa8cb4fb5fa34808223efbc1f0023161d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255168"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Resolver problemas con los buzones compartidos

Si ve mensajes de error al crear o usar un buzón compartido, Pruebe estas soluciones posibles. 

## <a name="error-when-creating-shared-mailboxes"></a>Error al crear buzones compartidos
<a name="bkmk_Fix"> </a>

Si ve el mensaje de error, la dirección del proxy **"SMTP: <nombre\>del buzón compartido" ya está en uso por las direcciones de proxy o\<legacyExchangeDN de "nombre>". Elija otra dirección de proxy**, significa que está intentando dar al buzón compartido un nombre que ya está en uso. Por ejemplo, supongamos que desea los buzones compartidos denominados info@domain1 y info@domain2. Puede realizar esto de dos maneras:

  - Use Windows PowerShell. Consulte esta publicación del blog para obtener instrucciones: [Crear buzones compartidos con el mismo Alias en diferentes dominios en Office 365](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Asigne al segundo buzón compartido un nombre distinto del inicio para evitar el error. A continuación, en el centro de administración, cambie el nombre del buzón compartido por el que desee.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Error al no tener permisos de envío al usar un buzón compartido

Si ha creado un buzón compartido y, a continuación, intenta enviarle un mensaje, es posible que obtenga esto:

**No se pudo enviar este mensaje. No tiene permiso para enviar el mensaje en nombre del usuario especificado.**

Este mensaje aparece cuando Office 365 experimenta un problema de latencia de replicación. Debe desaparecer en una hora o por lo tanto, cuando la información sobre su nuevo buzón compartido (o usuario agregado) se replique en todos nuestros centros de datos. Espere una hora y vuelva a intentar enviar un mensaje.

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Quitar una licencia de un buzón compartido](remove-license-from-shared-mailbox.md)


    

