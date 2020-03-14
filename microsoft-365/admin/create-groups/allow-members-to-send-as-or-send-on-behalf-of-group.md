---
title: Permitir que los miembros envíen como o envíen en nombre de un grupo
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Obtenga información sobre cómo permitir a los miembros enviar correo electrónico como un grupo de Office 365 o enviar un correo electrónico en nombre de un grupo de Office 365.
ms.openlocfilehash: 0179dbd2e3093ce80929f6c5f9e689aece845a40
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633788"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Permitir que los miembros envíen como o envíen en nombre de un grupo

Un miembro de un grupo de Office 365 que tenga permisos para **Enviar como** o **enviar en nombre** de ahora puede enviar correo electrónico como grupo o en nombre del grupo. En este tema se explica cómo un administrador puede establecer estos permisos.
  
Por ejemplo, si Nuria Bowen forma parte del grupo **Training** Office 365 y tiene permisos **Enviar como** en el grupo, si envía un correo electrónico como grupo, parecerá que el grupo de **formación** envió el correo electrónico. 
  
El permiso **enviar en nombre** de permite a un usuario enviar correo electrónico en nombre de un grupo de Office 365. Por ejemplo, si Alex Wilber forma parte del grupo **marketing** Office 365 y tiene permisos **enviar en nombre** de y envía un correo electrónico como grupo, el correo electrónico parece enviado por **Alex Wilber en nombre de marketing**.

> [!IMPORTANT]
> Puede configurar **Enviar como** o **enviar en nombre** de un usuario determinado, pero no ambos. Si configura ambos, tendrá **como predeterminado enviar como**.

> [!TIP]
> Consulte los pasos en [Enviar correo electrónico desde o en nombre de un grupo de Office 365](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) para obtener información sobre cómo usar Outlook y Outlook en la web para enviar correo electrónico desde un grupo.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Permitir que los miembros envíen correo electrónico como un grupo

En esta sección se explica cómo permitir que los usuarios envíen correo electrónico como un grupo en el [centro de administración de Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) en Exchange Online.
  
1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>, vaya a **grupos**de **destinatarios** \> .
    
2. Seleccione **Editar**![icono](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) editar grupo en el grupo al que desea permitir que los usuarios lo envíen.   
    
3. Seleccione **delegación de grupo**.
    
4. En la sección **Enviar como** , seleccione el **+** signo para agregar los usuarios que desea enviar como grupo. 
    
    ![Seleccione el signo más para agregar los usuarios que quiera enviar como grupo de Office 365](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Escriba para buscar o seleccionar un usuario de la lista. Seleccione **Aceptar** y **Guardar**.
    
    ![Escriba para buscar o seleccionar un usuario de la lista](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Permitir que los miembros envíen correo electrónico en nombre de un grupo

En esta sección se explica cómo permitir que los usuarios envíen correo electrónico en nombre de un grupo en el centro de administración de Exchange (EAC) en Exchange Online.
  
1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administración de Exchange</a>, vaya a **grupos**de **destinatarios** \> .
    
2. Seleccione **Editar** ![el icono](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) editar grupo en el grupo que desea permitir que los usuarios envíen como. 
    
3. Seleccione **delegación de grupo**.
    
4. En la sección enviar en nombre de, seleccione **+** el signo para agregar los usuarios que desea enviar como grupo. 
    
    ![Seleccione el signo más para agregar los usuarios que quiera enviar como grupo de Office 365](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Escriba para buscar o seleccionar un usuario de la lista. Seleccione **Aceptar** y **Guardar**.
    
    ![Escriba para buscar o seleccionar un usuario de la lista](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Artículos relacionados

[Obtener más información sobre los grupos de Office 365](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
