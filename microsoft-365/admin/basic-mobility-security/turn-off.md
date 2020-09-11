---
title: Desactivar la movilidad y la seguridad básicas
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Quitar grupos o directivas para desactivar la movilidad y la seguridad básicas.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430294"
---
# <a name="turn-off-basic-mobility-and-security"></a>Desactivar la movilidad y la seguridad básicas

Para desactivar eficazmente la movilidad y la seguridad básica, se quitan los grupos de personas definidas por grupos de seguridad de las directivas de administración de dispositivos o se quitan las directivas.

- Quite grupos de usuarios quitando grupos de seguridad de usuarios de las directivas de dispositivo que ha creado.
    
- Deshabilite la movilidad y la seguridad básicas para todos al quitar todas las directivas de dispositivos de seguridad y movilidad básicas.
    
Estas opciones eliminan la movilidad básica y el cumplimiento de la seguridad de los dispositivos de la organización. Desafortunadamente, no se puede simplemente "desaprovisionar" la movilidad y la seguridad básicas una vez que se ha configurado. 

>[!IMPORTANT]
>Tenga en cuenta el impacto en los dispositivos de los usuarios al quitar grupos de seguridad de usuarios de las directivas o quitar las directivas en sí. Por ejemplo, los perfiles de correo electrónico y los correos electrónicos en caché se pueden quitar, según el dispositivo. Para obtener más información, vea  [¿Qué sucede cuando se elimina una directiva o se quita un usuario de la Directiva?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Quitar grupos de seguridad de usuarios de las directivas básicas de dispositivos de seguridad y movilidad

1. En el explorador, escriba:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Seleccione una directiva de dispositivo y seleccione **Editar Directiva**. 

3. En la página  **implementación**   , seleccione **quitar**.
    
4. En  **grupos**, seleccione un grupo de seguridad.

5. Seleccione  **quitar**y seleccione **Guardar**.
    

## <a name="remove-basic-mobility-and-security-device-policies"></a>Quitar directivas de dispositivos de seguridad y movilidad básicas

1.  En el explorador, escriba:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Seleccione una directiva de dispositivo y, a continuación, seleccione  **eliminar Directiva**.
    
3.  En el cuadro de diálogo de advertencia, seleccione **sí**.

>[!NOTE] 
>Para obtener más pasos para desbloquear dispositivos si los dispositivos de la organización siguen estando en estado bloqueados, vea la entrada [de blog quitar el control de acceso de la administración de dispositivos móviles para Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).
