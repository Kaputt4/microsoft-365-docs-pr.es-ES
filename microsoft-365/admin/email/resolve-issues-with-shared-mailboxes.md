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
description: Es posible que reciba errores al configurar buzones compartidos. Pruebe estas soluciones si tiene problemas con buzones compartidos.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706135"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Resolver problemas con los buzones compartidos

Si ve mensajes de error al crear o usar un buzón compartido, pruebe estas posibles soluciones. 

## <a name="error-when-creating-shared-mailboxes"></a>Error al crear buzones compartidos
<a name="bkmk_Fix"> </a>

Si ve el mensaje de error, la dirección proxy "smtp:<nombre de buzón compartido" ya está siendo usada por las direcciones proxy o **\> LegacyExchangeDN de " \<name> ". Elija otra dirección de proxy,** significa que está intentando dar al buzón compartido un nombre que ya está en uso. Por ejemplo, supongamos que desea los buzones compartidos denominados info@domain1 y info@domain2. Hay dos formas de hacerlo:

  - Use Windows PowerShell. Vea esta entrada de blog para obtener instrucciones: [Crear buzones compartidos con el mismo alias en dominios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Asigne al segundo buzón compartido un nombre diferente del inicio para evitar el error. A continuación, en el Centro de administración, cambie el nombre del buzón compartido a lo que desea que sea.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Error sobre no tener permisos de envío al usar un buzón compartido

Si creó un buzón compartido y, a continuación, intenta enviar un mensaje desde él, puede obtener esto:

**No se pudo enviar este mensaje. No tiene permiso para enviar el mensaje en nombre del usuario especificado.**

Este mensaje aparece cuando Microsoft 365 está experimentando un problema de latencia de replicación. Debería desaparecer en una hora aproximadamente, cuando la información sobre el nuevo buzón compartido (o usuario agregado) se replique en todos nuestros centros de datos. Espere una hora y vuelva a intentar enviar un mensaje.

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)


    

