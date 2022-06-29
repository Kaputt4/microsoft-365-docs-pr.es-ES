---
title: Configurar dispositivos administrados
f1.keywords:
- NOCSH
ms.author: v-kcirillo
author: cirilk
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Cómo configurar dispositivos administrados
ms.openlocfilehash: 990b6a042e57a7964918e7e339bdfc3987c3c477
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66490265"
---
# <a name="set-up-managed-devices"></a>Configurar dispositivos administrados

Un dispositivo "administrado" es uno que está bajo control y supervisado por la organización y, por lo tanto, se actualiza periódicamente y es seguro. Tener dispositivos bajo control administrado es un objetivo crítico. Para controlar estos dispositivos, se inscriben en un administrador de dispositivos con Intune y Azure Active Directory Premium, que se incluyen con Microsoft Business Premium. 

Un equipo Windows 10 se considera administrado después de que los usuarios hayan completado los dos pasos siguientes:

1. Configure directivas de protección de datos y dispositivos en el [wizardsetup](../business/set-up.md).

2. Conectó el equipo a [Azure Active Directory](../business/set-up-windows-devices.md) con su nombre de usuario y contraseña Microsoft 365. 

## <a name="enroll-devices-in-microsoft-endpoint-manager"></a>Inscribir dispositivos en Microsoft Endpoint Manager

Ahora puede inscribir dispositivos en Endpoint Manager, vaya a https://endpoint.microsoft.com y seleccione **Dispositivos** > **Inscribir dispositivos**. 

:::image type="content" source="media/m365bp-endpoint-manager-enroll-devices.png" alt-text="Usar Microsoft Endpoint Manager para inscribir los dispositivos."::: 

Siga las instrucciones de inscripción de dispositivos específicas que se indican a continuación.

### <a name="for-windows-enrollment"></a>Inscripción de Windows:

1. Seleccione **Windows** > **Inscripción de Windows**. 

2. En los métodos de inscripción enumerados, seleccione **Inscripción automática**.

### <a name="for-ios-enrollment"></a>Para la inscripción de iOS:

1. Seleccione **iOS** > **Inscripción iOS**.

2. En la lista de directivas, seleccione una directiva para ver sus detalles.

3. Seleccione **Propiedades** para administrar la directiva.

4. Seleccione **Configuración** > **System Security** y configure los detalles de seguridad en Intune.

5. Examine los perfiles de configuración. 

6. Cree un perfil e insértela en los dispositivos de su organización, según sea necesario.

### <a name="for-android-enrollment"></a>Inscripción de Android:

1. Seleccione **Android** > **Inscripción de Android**.

2. Elija **Managed Google Play** y conceda permiso a Microsoft para enviar información a Google.

## <a name="next-objective"></a>Siguiente objetivo

Use las siguientes instrucciones para [abordar los dispositivos](m365bp-onboard-devices-mdb.md).

