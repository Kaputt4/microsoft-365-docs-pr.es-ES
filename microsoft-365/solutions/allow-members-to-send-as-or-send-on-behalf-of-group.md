---
title: Permitir que los miembros envíen como o envíen en nombre de un grupo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Obtenga información sobre cómo permitir a los miembros enviar correo electrónico como un grupo de Microsoft 365 o enviar correo electrónico en nombre de un grupo de Microsoft 365.
ms.openlocfilehash: 6dff559eceec1b719f31d577d7fff8f604636a47
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663588"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Permitir que los miembros envíen como o envíen en nombre de un grupo

Un miembro de un grupo de Microsoft  365 al que se hayan concedido permisos Enviar como o Enviar en nombre de puede enviar correo electrónico como grupo o en nombre del grupo.  En este artículo se explica cómo un administrador global o de Exchange puede establecer estos permisos.
  
Por ejemplo, si Megan Bowen forma parte del grupo De  aprendizaje de **Microsoft** 365 y tiene permisos enviar como  en el grupo, si envía un correo electrónico como el grupo, parecerá que el grupo de aprendizaje envió el correo electrónico. 
  
El **permiso Enviar en nombre** de permite a un usuario enviar correo electrónico en nombre de un grupo de Microsoft 365. Por ejemplo, si Alex Wilber forma parte del grupo **marketing**  de Microsoft 365, tiene permisos enviar en nombre de y envía un correo electrónico como el grupo, el correo electrónico parece que lo envió **Alex Wilber** en nombre de Marketing .

> [!IMPORTANT]
> Puede configurar **Enviar como o** Enviar **en** nombre de un usuario determinado, pero no ambos. Si configura ambos, el valor predeterminado será **Enviar como**.

> [!TIP]
> Consulte Enviar correo electrónico desde o en nombre de un grupo de [Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) para obtener información sobre cómo usar Outlook y Outlook en la Web para enviar correo electrónico desde un grupo.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Permitir que los miembros envíen correo electrónico como un grupo

En esta sección se explica cómo permitir a los usuarios enviar correo electrónico como un grupo en el Centro de administración de [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) en Exchange Online.
  
1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange,</a>vaya a Grupos de  \> **destinatarios.**
    
2. Seleccione **el icono** Editar grupo en el grupo que desea permitir que los usuarios envíen ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) como.   
    
3. Seleccione **delegación de grupo.**
    
4. En la **sección Enviar como,** seleccione el signo para agregar los **+** usuarios que desea enviar como grupo. 
    
    ![Captura de pantalla del cuadro de diálogo Enviar como](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Escriba para buscar o seleccionar un usuario de la lista. Seleccione **Aceptar** y **Guardar.**
    
    ![Escriba para buscar o seleccionar un usuario de la lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Permitir que los miembros envíen correo electrónico en nombre de un grupo

En esta sección se explica cómo permitir a los usuarios enviar correo electrónico en nombre de un grupo en el Centro de administración de Exchange (EAC) en Exchange Online.
  
1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange,</a>vaya a Grupos de  \> **destinatarios.**
    
2. Seleccione **el icono** Editar grupo en el grupo al que desea permitir que los usuarios envíen ![ ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) mensajes. 
    
3. Seleccione **delegación de grupo.**
    
4. En la sección Enviar en nombre de, seleccione el signo para agregar los usuarios **+** que desea enviar como grupo. 
    
    ![Captura de pantalla del envío en nombre del cuadro de diálogo](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Escriba para buscar o seleccionar un usuario de la lista. Seleccione **Aceptar** y **Guardar.**
    
    ![Escriba para buscar o seleccionar un usuario de la lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Artículos relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear un plan de gobierno de colaboración](collaboration-governance-first.md)

[Más información sobre los grupos de Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
