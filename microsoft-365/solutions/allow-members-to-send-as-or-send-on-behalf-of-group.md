---
title: Permitir que los miembros envíen como o envíen en nombre de un grupo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
ms.custom: admindeeplinkEXCHANGE
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: Obtenga información sobre cómo permitir que los miembros del grupo envíen correo electrónico como un grupo de Microsoft 365 o envíen correo electrónico en nombre de un grupo de Microsoft 365.
ms.openlocfilehash: 73d5e8ea27294b78b6e4c626ac2adba15f000967
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67681219"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Permitir que los miembros envíen como o envíen en nombre de un grupo

Un miembro de un grupo de Microsoft 365 al que se le hayan concedido permisos **Enviar como** o **Enviar en nombre** puede enviar correo electrónico como grupo o en nombre del grupo. (No se pueden conceder estos permisos a los invitados del grupo).

En este artículo se explica cómo un administrador global o de Exchange puede establecer estos permisos.
  
Por ejemplo, si Megan Bowen forma parte del grupo **Entrenamiento** de Microsoft 365 y tiene permisos **Enviar como** en el grupo, si envía un correo electrónico como grupo, será similar al grupo **Entrenamiento** que envió el correo electrónico. 
  
El permiso **Enviar en nombre** permite a un usuario enviar correo electrónico en nombre de un grupo de Microsoft 365. Por ejemplo, si Alex Wilber forma parte del grupo **Marketing** de Microsoft 365 y tiene permisos **Enviar en nombre** y envía un correo electrónico como grupo, el correo electrónico parece que lo envió **Alex Wilber en nombre de Marketing**.

> [!IMPORTANT]
> Puede configurar **Enviar como** o **Enviar en nombre** de un usuario determinado, pero no ambos. Si configura ambos, el valor predeterminado será **Enviar como**.

> [!NOTE]
> **Enviar como** y **Enviar en nombre** no se admiten en Outlook para Mac en configuraciones híbridas de Exchange.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Permitir que los miembros envíen correo electrónico como grupo

En esta sección se explica cómo permitir que los usuarios envíen correo electrónico como grupo en el<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange (EAC)</a> en Exchange Online.
  
1. En el Centro de administración de Exchange, vaya a **Grupos de destinatarios**\>.<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a>
    
2. Seleccione el grupo que desea permitir que los usuarios envíen como. 
    
3. Seleccione **Configuración** > **Editar administrar delegados**.
    
4. En la sección **Agregar un delegado**, escriba la dirección de correo electrónico del usuario al que desea tener acceso **Enviar.**
  
5. Seleccione **Tipo de permiso** como **Enviar como** en la lista desplegable.

6.  Seleccione **Guardar cambios**.
    
    
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Permitir que los miembros envíen correo electrónico en nombre de un grupo

En esta sección se explica cómo permitir que los usuarios envíen correo electrónico en nombre de un grupo en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange (EAC)</a> en Exchange Online.
  
1. En el Centro de administración de Exchange, vaya a **Grupos de destinatarios**\>.<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a>
    
2. Seleccione el grupo del que desea permitir que los usuarios envíen en nombre de . 
    
3. Seleccione **Configuración** > **Editar administrar delegados**.
    
4. En la sección **Agregar un delegado**, escriba la dirección de correo electrónico del usuario al que desea tener acceso **Enviar.**
  
5. Seleccione **Tipo de permiso** como **Enviar en nombre en** la lista desplegable.

6.  Seleccione **Guardar cambios**.

## <a name="related-articles"></a>Artículos relacionados

[Enviar correo electrónico desde o en nombre de un grupo de Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Más información sobre los grupos de Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)
