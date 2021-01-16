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
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876845"
---
# <a name="turn-off-basic-mobility-and-security"></a>Desactivar la movilidad y la seguridad básicas

Para desactivar eficazmente la movilidad y la seguridad básicas, quita los grupos de personas definidos por los grupos de seguridad de las directivas de administración de dispositivos o quita las directivas en sí.

- Quita grupos de usuarios quitando los grupos de seguridad de usuario de las directivas de dispositivo que hayas creado.

- Deshabilite la movilidad y la seguridad básicas para todos los usuarios mediante la eliminación de todas las directivas de dispositivos de movilidad y seguridad básicas.

Estas opciones quitan la aplicación de movilidad y seguridad básica para los dispositivos de la organización. Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up. 

>[!IMPORTANT]
>Ten en cuenta el impacto en los dispositivos de los usuarios al quitar grupos de seguridad de usuarios de las directivas o quitar las propias directivas. Por ejemplo, los perfiles de correo electrónico y los correos electrónicos almacenados en caché pueden quitarse, según el dispositivo. Para obtener más información, consulta  [¿Qué sucede cuando eliminas una directiva o quitas un usuario de la directiva?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Quitar grupos de seguridad de usuario de las directivas de dispositivos de movilidad y seguridad básicas

1. En el tipo de explorador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecciona una directiva de dispositivo y selecciona **Editar directiva.** 

3. En la  **página Implementación,**   seleccione **Quitar**.

4. En  **Grupos,** seleccione un grupo de seguridad.

5. Seleccione  **Quitar** y, a continuación, **seleccione Guardar**.

## <a name="remove-basic-mobility-and-security-device-policies"></a>Quitar directivas de dispositivos de movilidad y seguridad básicas

1.  En el tipo de explorador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Seleccione una directiva de dispositivo y, a  **continuación, seleccione Eliminar directiva.**
    
3.  En el cuadro de diálogo Advertencia, seleccione **Sí**.

>[!NOTE]
>Para obtener más pasos para desbloquear dispositivos si los dispositivos de su organización aún están bloqueados, vea la entrada de blog Quitar el control de acceso de la administración de dispositivos móviles [para Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
