---
title: Resolver problemas con los buzones compartidos
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Pruebe estas soluciones si tiene problemas con buzones compartidos.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926491"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Resolver problemas con los buzones compartidos

Si ve mensajes de error al crear o usar un buzón compartido, pruebe estas posibles soluciones. 

## <a name="error-when-creating-shared-mailboxes"></a>Error al crear buzones compartidos
<a name="bkmk_Fix"> </a>

Si ve el mensaje de error, la dirección proxy "smtp:<shared mailbox name " ya está siendo utilizada por las direcciones proxy o **\> LegacyExchangeDN de " \<name> ". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use. Por ejemplo, supongamos que desea los buzones compartidos denominados info@domain1 y info@domain2. Puede realizar esto de dos maneras:

  - Use Windows PowerShell. Consulte esta entrada de blog para obtener instrucciones: Crear buzones [compartidos con el mismo alias en dominios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Asigne al segundo buzón compartido un nombre diferente del principio para evitar el error. A continuación, en el centro de administración, cambie el nombre del buzón compartido por el que desea que sea.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Error sobre no tener permisos de envío al usar un buzón compartido

Si creó un buzón compartido y, a continuación, intenta enviar un mensaje desde él, es posible que obtenga esto:

**No se pudo enviar este mensaje. No tiene permiso para enviar el mensaje en nombre del usuario especificado.**

Este mensaje aparece cuando Microsoft 365 está experimentando un problema de latencia de replicación. Debería desaparecer en una hora aproximadamente, cuando la información sobre el nuevo buzón compartido (o usuario agregado) se replique en todos nuestros centros de datos. Espere una hora y vuelva a intentarlo para enviar un mensaje.

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md)


    

