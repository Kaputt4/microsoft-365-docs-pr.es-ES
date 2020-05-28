---
title: Resolver problemas con los buzones compartidos
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Pruebe estas soluciones si experimenta problemas con los buzones compartidos.
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400021"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Resolver problemas con los buzones compartidos

Si ve mensajes de error al crear o usar un buzón compartido, Pruebe estas soluciones posibles. 

## <a name="error-when-creating-shared-mailboxes"></a>Error al crear buzones compartidos
<a name="bkmk_Fix"> </a>

Si ve el mensaje de error, la dirección del proxy **"SMTP: <nombre del buzón compartido \> " ya está siendo usada por las direcciones de proxy o legacyExchangeDN de " \<name> ". Elija otra dirección de proxy**, significa que está intentando dar al buzón compartido un nombre que ya está en uso. Por ejemplo, supongamos que desea los buzones compartidos denominados info@domain1 y info@domain2. Puede realizar esto de dos maneras:

  - Use Windows PowerShell. Vea esta entrada de blog para obtener instrucciones: [crear buzones compartidos con el mismo alias en dominios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Asigne al segundo buzón compartido un nombre distinto del inicio para evitar el error. A continuación, en el centro de administración, cambie el nombre del buzón compartido por el que desee.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Error al no tener permisos de envío al usar un buzón compartido

Si ha creado un buzón compartido y, a continuación, intenta enviarle un mensaje, es posible que obtenga esto:

**No se pudo enviar este mensaje. No tiene permiso para enviar el mensaje en nombre del usuario especificado.**

Este mensaje aparece cuando Microsoft 365 experimenta un problema de latencia de replicación. Debe desaparecer en una hora o por lo tanto, cuando la información sobre su nuevo buzón compartido (o usuario agregado) se replique en todos nuestros centros de datos. Espere una hora y vuelva a intentar enviar un mensaje.

## <a name="related-articles"></a>Artículos relacionados

[Acerca de los buzones compartidos](about-shared-mailboxes.md)

[Crear un buzón compartido](create-a-shared-mailbox.md)

[Configurar un buzón compartido](configure-a-shared-mailbox.md)

[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md)

[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md)


    

