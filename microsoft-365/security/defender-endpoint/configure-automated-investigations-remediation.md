---
title: Configurar capacidades automatizadas de investigación y corrección
description: Configure las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint.
keywords: configure, setup, automated, investigation, detection, alerts, remediation, response
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: f8416d480731c133e93a0a6e22e5b5b32913ba57
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327621"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Configurar las capacidades automatizadas de investigación y corrección en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Si su organización usa [Microsoft Defender para](/windows/security/threat-protection/) endpoint (Defender para [endpoint), las](/microsoft-365/security/defender-endpoint/automated-investigations) capacidades automatizadas de investigación y corrección pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad. Como se describe en [esta entrada de blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), estas capacidades imitan los pasos ideales que un analista de seguridad realiza para investigar y corregir las amenazas. [Obtenga más información sobre la investigación automatizada y la corrección](/microsoft-365/security/defender-endpoint/automated-investigations).

Para configurar la investigación y corrección automatizadas:

1. [Activar las características](#turn-on-automated-investigation-and-remediation); y
2. [Configurar grupos de dispositivos](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>Activar la investigación y corrección automatizadas

1. Como administrador global o administrador de seguridad, vaya al portal de Microsoft 365 Defender (<https://security.microsoft.com>) e inicie sesión.
2. En el panel de navegación, **elija Configuración**.
3. En la **sección General** , seleccione **Características avanzadas**.
4. Activa la investigación **automatizada y** **resuelve automáticamente las alertas**.

## <a name="set-up-device-groups"></a>Configurar grupos de dispositivos

1. En el portal Microsoft 365 Defender (<https://security.microsoft.com>), en la **página Configuración**, en **Permisos**, seleccione **Grupos de dispositivos**.
2. Selecciona **+ Agregar grupo de dispositivos**.
3. Crea al menos un grupo de dispositivos de la siguiente manera:
   - Especifica un nombre y una descripción para el grupo de dispositivos.
   - En la **lista Nivel de automatización**, seleccione un nivel, como **Full - remediate las amenazas automáticamente**. El nivel de automatización determina si las acciones de corrección se toman automáticamente o solo tras la aprobación. Para obtener más información, consulte [Automation levels in automated investigation and remediation](automation-levels.md).
   - En la **sección Miembros** , use una o más condiciones para identificar e incluir dispositivos.
   - En la **pestaña Acceso de** usuario, selecciona Azure Active Directory [grupos](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) que deben tener acceso al grupo de dispositivos que estás creando.
4. Selecciona **Listo** cuando termines de configurar el grupo de dispositivos.

## <a name="next-steps"></a>Siguientes pasos

- [Visite el Centro de acciones para ver las acciones de corrección pendientes y completadas](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Revisar y aprobar acciones pendientes](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Consulte también

- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
