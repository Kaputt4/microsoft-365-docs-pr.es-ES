---
title: Configuración de funcionalidades automatizadas de investigación y corrección
description: Configure las funcionalidades automatizadas de investigación y corrección en Microsoft Defender para punto de conexión.
keywords: configurar, configurar, automatizar, investigar, detectar, alertas, corrección, respuesta
ms.service: microsoft-365-security
ms.subservice: mde
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
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
search.appverid: met150
ms.openlocfilehash: 428ceefa6b8921782864eac8f42105a44cc06c72
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67695745"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Configurar funcionalidades automatizadas de investigación y corrección en Microsoft Defender para punto de conexión

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para Empresas](../defender-business/mdb-overview.md)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Si su organización usa [Defender para punto de conexión](/windows/security/threat-protection/) (o [Defender para empresas](../defender-business/mdb-overview.md)), [las funcionalidades automatizadas de investigación y corrección](/microsoft-365/security/defender-endpoint/automated-investigations) pueden ahorrar tiempo y esfuerzo al equipo de operaciones de seguridad. Como se describe en [esta entrada de blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946), estas funcionalidades imitan los pasos ideales que un analista de seguridad realiza para investigar y corregir amenazas. [Obtenga más información sobre la investigación y la corrección automatizadas](/microsoft-365/security/defender-endpoint/automated-investigations).

Para configurar la investigación y corrección automatizadas:

1. [Active las características](#turn-on-automated-investigation-and-remediation); Y
2. [Configurar grupos de dispositivos](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>Activar la investigación y la corrección automatizadas

1. Como administrador global o administrador de seguridad, vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración**.

3. Seleccione **Puntos de conexión** y, después, **Características avanzadas**.

4. Active investigación **automatizada** y **resuelva automáticamente las alertas**.

## <a name="set-up-device-groups"></a>Configurar grupos de dispositivos

> [!NOTE]
> Este procedimiento no se aplica a Defender para empresas.

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en la página **Configuración**, en **Permisos**, seleccione **Grupos de dispositivos**.

2. Seleccione **+ Agregar grupo de dispositivos**.

3. Cree al menos un grupo de dispositivos, como se indica a continuación:

   - Especifique un nombre y una descripción para el grupo de dispositivos.
   - En la **lista Nivel de automatización**, seleccione un nivel, como **Completo: corrija automáticamente las amenazas**. El nivel de automatización determina si las acciones de corrección se realizan automáticamente o solo tras la aprobación. Para más información, consulte [Niveles de automatización en investigación y corrección automatizadas](automation-levels.md).
   - En la sección **Miembros** , use una o varias condiciones para identificar e incluir dispositivos.
   - En la pestaña **Acceso de usuario** , seleccione los [grupos de Azure Active Directory](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) que deben tener acceso al grupo de dispositivos que va a crear.

4. Seleccione **Listo** cuando haya terminado de configurar el grupo de dispositivos.

## <a name="next-steps"></a>Pasos siguientes

- [Visite el Centro de acciones para ver las acciones de corrección pendientes y completadas.](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Revisión y aprobación de acciones pendientes](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Vea también

- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
