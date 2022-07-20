---
title: Configurar dispositivos administrados
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection:
- M365-Campaigns
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: Cómo configurar dispositivos administrados
ms.openlocfilehash: a4298bcdc284f1957a1afa73cbc7ae8e3f15e7d1
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "66895017"
---
# <a name="set-up-managed-devices"></a>Configurar dispositivos administrados

Un dispositivo "administrado" es uno que está bajo control y supervisado por la organización y, por lo tanto, se actualiza periódicamente y es seguro. Tener dispositivos bajo control administrado es un objetivo crítico. Para controlar estos dispositivos, inscríbalos en un administrador de dispositivos con Microsoft Intune y Azure Active Directory, ambos incluidos con Microsoft Business Premium.

1. Configure directivas de protección de datos y dispositivos en el [wizardsetup](../business/set-up.md).

2. Conectó el equipo a [Azure Active Directory](../business/set-up-windows-devices.md) con su nombre de usuario y contraseña Microsoft 365. 

## <a name="enroll-devices-in-intune"></a>Inscribir dispositivos para administrarlos en Intune

1. Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Seleccione **Dispositivos** > **Inscribir dispositivos**. 

   :::image type="content" source="media/m365bp-endpoint-manager-enroll-devices.png" alt-text="Usar Microsoft Endpoint Manager para inscribir los dispositivos."::: 

3. Siga las instrucciones de inscripción de dispositivos específicas que se indican a continuación.

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

Use las siguientes instrucciones para [incorporar dispositivos a las funcionalidades de Microsoft Defender para Empresas](m365bp-onboard-devices-mdb.md).

