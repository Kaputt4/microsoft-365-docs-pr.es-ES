---
title: Administrar las opciones de configuración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager
description: Obtenga información sobre cómo habilitar la configuración de seguridad en Microsoft Endpoint Manager a través de Microsoft Defender para endpoint.
keywords: administración de dispositivos, configurar Microsoft Defender para dispositivos de punto de conexión, Microsoft Endpoint Manager
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
ms.openlocfilehash: e21346b48f65016465e669369aa14b3f4c85c23b
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63527104"
---
# <a name="manage-microsoft-defender-for-endpoint-configuration-settings-on-devices-with-microsoft-endpoint-manager"></a>Administrar las opciones de configuración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Administrar Microsoft Defender para endpoint en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



[!include[Prerelease information](../../includes/prerelease.md)]


> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)


Administración de seguridad para Microsoft Defender para endpoint es una funcionalidad para dispositivos que no están administrados por un Microsoft Endpoint Manager, ya sea Microsoft Intune o Microsoft Endpoint Configuration Manager, para recibir configuraciones de seguridad para Microsoft Defender directamente desde Endpoint Manager.


Para obtener más información sobre administración de configuración de seguridad, incluidos los requisitos previos, las plataformas admitidas y mucho más, consulte [Manage Microsoft Defender for Endpoint on devices with Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration).



[!INCLUDE [Prerequisites](../../includes/security-config-mgt-prerequisites.md)]

>[!NOTE]
>Esta funcionalidad se está implantando gradualmente. 

Para obtener más información sobre administración de configuración de seguridad, consulte [Manage Microsoft Defender for Endpoint on devices with Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration).

Si tiene problemas de inscripción, consulte [Solucionar problemas de incorporación de administración de configuración de seguridad](troubleshoot-security-config-mgt.md).

> [!NOTE]
> Esta funcionalidad no se aplica a los dispositivos que ya están inscritos en Microsoft Endpoint Manager (Intune o Configuration Manager). Los dispositivos inscritos en Intune seguirán recibiendo directivas a través de su canal de administración establecido.

## <a name="identify-onboarded-devices"></a>Identificar dispositivos incorporados

Siga estos pasos para validar que los puntos de conexión han completado correctamente el proceso de incorporación de Administración de seguridad para Microsoft Defender para endpoints.

1.  Comprueba que el dispositivo aparece en la sección Inventario de dispositivos de [Microsoft 365 Defender](https://security.microsoft.com/).

2.  En el [Azure Active Directory,](https://aad.portal.azure.com/#blade/Microsoft_AAD_Devices/DevicesMenuBlade/Devices/menuId/) compruebe que el dispositivo se ha inscrito correctamente.

3.  En el [Centro Microsoft Endpoint Manager administración](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/mDMDevicesPreview), compruebe que el dispositivo se ha inscrito correctamente si lo busca en la sección Dispositivos **> Todos los** dispositivos.


## <a name="offboard-devices"></a>Dispositivos offboard
Para los dispositivos de fuera de la placa que se han incorporado a través de Administración de seguridad para Microsoft Defender para endpoint, consulta [Dispositivos offboard desde el servicio Microsoft Defender para endpoints](offboard-machines.md).

>[!NOTE]
>El offboarding [deshabilitará la protección contra manipulaciones](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) si está habilitada.

## <a name="troubleshooting-security-management"></a>Solución de problemas de administración de seguridad 
Para solucionar problemas de la administración de seguridad de Microsoft Defender para problemas de inscripción de puntos de conexión, consulte Solucionar problemas de incorporación relacionados con administración de seguridad [para Microsoft Defender para endpoint](troubleshoot-security-config-mgt.md).

## <a name="related-topic"></a>Tema relacionado
- [Solucionar problemas de incorporación relacionados con administración de seguridad para Microsoft Defender para endpoint](troubleshoot-security-config-mgt.md)
- [Administrar Microsoft Defender para endpoint en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-mde-security-configuration-management)
