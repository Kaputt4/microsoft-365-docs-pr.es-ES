---
title: Desactivar Movilidad y seguridad básicas
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
description: Quite grupos o directivas para desactivar La movilidad y la seguridad básicas.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023874"
---
# <a name="turn-off-basic-mobility-and-security"></a>Desactivar Movilidad y seguridad básicas

Para desactivar de forma eficaz la movilidad y la seguridad básicas, quitas grupos de personas definidos por grupos de seguridad de las directivas de administración de dispositivos o quitas las propias directivas.

- Quita grupos de usuarios quitando grupos de seguridad de usuario de las directivas de dispositivo que creaste.

- Deshabilite la movilidad y la seguridad básicas para todos los usuarios quitando todas las directivas de dispositivos de movilidad y seguridad básicas.

Estas opciones quitan el cumplimiento básico de movilidad y seguridad para dispositivos de la organización. Desafortunadamente, no puedes simplemente "desaprovisionar" La movilidad y la seguridad básicas después de configurarla. 

>[!IMPORTANT]
>Tenga en cuenta el impacto en los dispositivos de los usuarios al quitar grupos de seguridad de usuarios de las directivas o quitar las propias directivas. Por ejemplo, los perfiles de correo electrónico y los correos electrónicos almacenados en caché pueden quitarse, según el dispositivo. Para obtener más información, consulta  [¿Qué sucede cuando eliminas una directiva o quitas a un usuario de la directiva?](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Quitar grupos de seguridad de usuarios de directivas de dispositivos de movilidad básica y seguridad

1. En el tipo de explorador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecciona una directiva de dispositivo y selecciona **Editar directiva**. 

3. En la  **página Implementación,**   seleccione **Quitar**.

4. En  **Grupos**, seleccione un grupo de seguridad.

5. Seleccione  **Quitar** y seleccione **Guardar**.

## <a name="remove-basic-mobility-and-security-device-policies"></a>Quitar directivas básicas de dispositivos de movilidad y seguridad

1.  En el tipo de explorador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Seleccione una directiva de dispositivo y, a continuación,  **seleccione Eliminar directiva**.
    
3.  En el cuadro de diálogo Advertencia, seleccione **Sí**.

>[!NOTE]
>Para obtener más pasos para desbloquear dispositivos si los dispositivos de la organización siguen en estado [bloqueado,](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)consulta la entrada de blog Quitar control de acceso de Administración de dispositivos móviles para Office 365 .
