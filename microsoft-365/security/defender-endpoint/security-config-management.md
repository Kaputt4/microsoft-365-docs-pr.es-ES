---
title: Administrar las opciones de configuración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager
description: Obtenga información sobre cómo habilitar la configuración de seguridad en Microsoft Endpoint Manager a través de Microsoft Defender para punto de conexión.
keywords: administración de dispositivos, configuración de dispositivos Microsoft Defender para punto de conexión, Microsoft Endpoint Manager
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c19352d584bedc5acd94f9984242a2c50d2fcf3
ms.sourcegitcommit: 85799f0efc06037c1ff309fe8e609bbd491f9b68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66573929"
---
# <a name="manage-microsoft-defender-for-endpoint-configuration-settings-on-devices-with-microsoft-endpoint-manager"></a>Administrar las opciones de configuración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Administración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)


Administración de seguridad para Microsoft Defender para punto de conexión es una funcionalidad para que los dispositivos que no están administrados por un Endpoint Manager de Microsoft reciban configuraciones de seguridad para Microsoft Defender directamente desde Endpoint Manager.


Para obtener más información sobre la administración de configuración de seguridad, incluidos los requisitos previos, las plataformas admitidas, etc., consulte [Administración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration).

Vea este vídeo para obtener información sobre cómo usar Microsoft Endpoint Manager para administrar la configuración de seguridad para Microsoft Defender para punto de conexión.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLVq]

[!INCLUDE [Prerequisites](../../includes/security-config-mgt-prerequisites.md)]

>[!NOTE]
>Esta funcionalidad se está implementando gradualmente. 

Para obtener más información sobre la administración de configuración de seguridad, consulte [Administración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration).

Si tiene problemas de inscripción, consulte [Solución de problemas de incorporación de Security Configuration Management](troubleshoot-security-config-mgt.md).

> [!NOTE]
> Esta funcionalidad no se aplica a los dispositivos que ya están inscritos en Microsoft Endpoint Manager (ya sea Intune o Configuration Manager). Los dispositivos inscritos en Intune seguirán recibiendo directivas a través de su canal de administración establecido.

## <a name="identify-onboarded-devices"></a>Identificación de dispositivos incorporados

Siga estos pasos para validar que los puntos de conexión han completado correctamente la administración de seguridad para Microsoft Defender para punto de conexión proceso de incorporación.

1.  Compruebe que el dispositivo aparece en la sección Inventario de dispositivos de [Microsoft 365 Defender](https://security.microsoft.com/).

2.  En el [portal de Azure Active Directory](https://aad.portal.azure.com/#blade/Microsoft_AAD_Devices/DevicesMenuBlade/Devices/menuId/), compruebe que el dispositivo se ha inscrito correctamente.

3.  En el [Centro de microsoft Endpoint Manager Administración](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/mDMDevicesPreview), compruebe que el dispositivo se ha inscrito correctamente buscándolo en la sección **Dispositivos > Todos los dispositivos**.


## <a name="offboard-devices"></a>Dispositivos fuera del panel
Para dispositivos fuera del panel que se han incorporado a través de Security Management para Microsoft Defender para punto de conexión, consulte [Dispositivos fuera del panel del servicio de Microsoft Defender para punto de conexión](offboard-machines.md).

>[!NOTE]
>La desactivación [deshabilitará la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) si está habilitada.

## <a name="troubleshooting-security-management"></a>Solución de problemas de administración de seguridad 
Para solucionar problemas de administración de seguridad para Microsoft Defender para punto de conexión problemas de inscripción, consulte [Solución de problemas de incorporación relacionados con la administración de seguridad para Microsoft Defender para punto de conexión](troubleshoot-security-config-mgt.md).

## <a name="related-topic"></a>Tema relacionado
- [Solución de problemas de incorporación relacionados con la administración de seguridad para Microsoft Defender para punto de conexión](troubleshoot-security-config-mgt.md)
- [Administración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-mde-security-configuration-management)
