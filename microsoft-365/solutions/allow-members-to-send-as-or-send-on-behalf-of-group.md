---
title: Permitir que los miembros envíen como o envíen en nombre de un grupo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
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
description: Obtenga información sobre cómo permitir que los miembros del grupo envíen correo electrónico como Microsoft 365 grupo o envíen correo electrónico en nombre de un Microsoft 365 grupo.
ms.openlocfilehash: e3742b645d1efb2acb4bd14d109314947d781246
ms.sourcegitcommit: b6676f2dd7c42b0b5eb3ca2790b13e10177a5758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62009038"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Permitir que los miembros envíen como o envíen en nombre de un grupo

Un miembro de un Microsoft 365 a quien  se  le hayan concedido permisos Enviar como o Enviar en nombre puede enviar correo electrónico como grupo o en nombre del grupo. (No se pueden conceder estos permisos a los invitados del grupo).

En este artículo se explica cómo un administrador global Exchange puede establecer estos permisos.
  
Por ejemplo, si Megan Bowen  forma parte del grupo  Microsoft 365 de aprendizaje y tiene permisos Enviar como en el grupo, si envía un correo electrónico como grupo, parecerá que el grupo de aprendizaje envió el correo electrónico.  
  
El **permiso Enviar en nombre** permite que un usuario envíe correo electrónico en nombre de un Microsoft 365 grupo. Por ejemplo, si Alex Wilber forma parte del grupo **Marketing** Microsoft 365 y tiene permisos Enviar en nombre y envía un correo electrónico como grupo, el correo electrónico parece que lo envió **Alex Wilber en** nombre de Marketing . 

> [!IMPORTANT]
> Puede configurar **Enviar como** o Enviar en **nombre** de un usuario determinado, pero no ambos. Si configura ambos, se establecerá de forma predeterminada **en Enviar como**.

> [!NOTE]
> **Enviar como** y **Enviar en nombre no** se admiten en Outlook para Mac en configuraciones Exchange híbridas.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Permitir que los miembros envíen correo electrónico como grupo

En esta sección se explica cómo permitir a los usuarios enviar correo electrónico como grupo en el Centro de administración de Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">(EAC)</a> en Exchange Online.
  
1. En el centro Exchange administración, vaya a **Grupos de** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**destinatarios**</a>.
    
2. Seleccione **Editar icono** editar ![ grupo.  ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) en el grupo que desea permitir que los usuarios envíen como. 
    
3. Seleccione **delegación de grupo**.
    
4. En la **sección Enviar como,** seleccione el signo para agregar los **+** usuarios que desea enviar como grupo. 
    
    ![Captura de pantalla del cuadro de diálogo Enviar como.](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Escriba para buscar o seleccionar un usuario de la lista. Seleccione **Aceptar** y **Guardar**.
    
    ![Escriba para buscar o seleccionar un usuario de la lista.](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Permitir que los miembros envíen correo electrónico en nombre de un grupo

En esta sección se explica cómo permitir a los usuarios enviar correo electrónico en nombre de un grupo en el Centro de administración de Exchange <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">(EAC)</a> en Exchange Online.
  
1. En el centro Exchange administración, vaya a **Grupos de** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**destinatarios**</a>.
    
2. Seleccione **Editar icono** editar ![ grupo.](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) en el grupo que desea permitir que los usuarios envíen como. 
    
3. Seleccione **delegación de grupo**.
    
4. En la sección Enviar en nombre, seleccione el signo para agregar los **+** usuarios que desea enviar como grupo. 
    
    ![Captura de pantalla del envío en nombre del cuadro de diálogo.](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Escriba para buscar o seleccionar un usuario de la lista. Seleccione **Aceptar** y **Guardar**.
    
    ![Escriba para buscar o seleccionar un usuario de la lista.](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Artículos relacionados

[Enviar correo electrónico desde o en nombre de un Microsoft 365 grupo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)

[Recomendaciones de planeación de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Obtenga más información sobre Microsoft 365 grupos](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)
