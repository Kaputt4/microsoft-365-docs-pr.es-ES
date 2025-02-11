---
title: Resolver problemas con los buzones compartidos
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Es posible que se produzcan errores al configurar buzones compartidos. Pruebe estas soluciones si experimenta problemas con los buzones compartidos.
ms.openlocfilehash: 1658aa8f2fcb49dba600970bab7b406d928913eb
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68719892"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Resolver problemas con los buzones compartidos

Si ve mensajes de error al crear o usar un buzón compartido, pruebe estas posibles soluciones. 

## <a name="error-when-creating-shared-mailboxes"></a>Error al crear buzones compartidos

Si ve el mensaje de error, **las direcciones proxy o LegacyExchangeDN de "\<name>" ya usan la dirección de proxy "smtp:<nombre\> de buzón compartido". Elija otra dirección de proxy**, lo que significa que está intentando asignar al buzón compartido un nombre que ya esté en uso. Por ejemplo, supongamos que desea los buzones compartidos denominados info@domain1 y info@domain2. Hay dos formas de hacerlo:

- Use Exchange Online PowerShell. Consulte esta entrada de blog para obtener instrucciones: [Creación de buzones compartidos con el mismo alias en dominios diferentes](https://blog.quadrotech-it.com/blog/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365/)

- Asigne al segundo buzón compartido un nombre diferente del inicio para evitar el error. A continuación, en el centro de administración, cambie el nombre del buzón compartido por el que quiera que sea.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Error al no tener permisos de envío al usar un buzón compartido

Si ha creado un buzón compartido y, a continuación, intenta enviar un mensaje desde él, puede obtener lo siguiente:

**No se pudo enviar este mensaje. No tiene permiso para enviar el mensaje en nombre del usuario especificado.**

Este mensaje aparece cuando Microsoft 365 experimenta un problema de latencia de replicación. Debería desaparecer en una hora aproximadamente, cuando la información sobre el nuevo buzón compartido (o el usuario agregado) se replica en todos nuestros centros de datos. Espere una hora e inténtelo de nuevo para enviar un mensaje.

## <a name="related-content"></a>Contenido relacionado

[Acerca de los buzones compartidos](about-shared-mailboxes.md) (artículo)\
[Crear un buzón compartido](create-a-shared-mailbox.md) (artículo)\
[Configurar un buzón compartido](configure-a-shared-mailbox.md) (artículo)\
[Convertir un buzón de usuario en un buzón compartido](convert-user-mailbox-to-shared-mailbox.md) (artículo)\
[Quitar la licencia de un buzón compartido](remove-license-from-shared-mailbox.md) (artículo)
