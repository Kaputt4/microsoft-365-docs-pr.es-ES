---
title: Asegurarse de que los dispositivos estén configurados de manera adecuada
description: Configure correctamente los dispositivos para aumentar la resistencia general frente a las amenazas y mejorar la capacidad de detectar y responder a ataques.
keywords: onboard, Intune management, Microsoft Defender para punto de conexión, Microsoft Defender, Windows Defender, attack surface reduction, ASR, security baseline
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ad0cc865362578597620fa4658c83c79dc7ebf02
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67702982"
---
# <a name="ensure-your-devices-are-configured-properly"></a>Asegurarse de que los dispositivos estén configurados de manera adecuada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Con los dispositivos configurados correctamente, puede aumentar la resistencia general frente a amenazas y mejorar la capacidad de detectar y responder a ataques. La administración de configuración de seguridad ayuda a garantizar que los dispositivos:

- Incorporación a Microsoft Defender para punto de conexión
- Cumplir o superar la configuración de línea base de seguridad de Defender para punto de conexión
- Tener mitigaciones estratégicas de la superficie expuesta a ataques en su lugar

Haga clic en **Administración de configuración** en el menú de navegación para abrir la página Administración de configuración de dispositivos.

:::image type="content" source="images/secconmgmt_main.png" alt-text="Página Administración de configuración de seguridad" lightbox="images/secconmgmt_main.png":::

*Página administración de configuración de dispositivos*

Puede realizar un seguimiento del estado de configuración a nivel organizativo y tomar medidas rápidamente en respuesta a problemas de cobertura de incorporación deficiente, problemas de cumplimiento y mitigaciones de superficie de ataque mal optimizadas mediante vínculos directos y profundos a páginas de administración de dispositivos en Microsoft Intune y <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.

Al hacerlo, se beneficia de lo siguiente:

- Visibilidad completa de los eventos en los dispositivos
- Inteligencia de amenazas sólida y potentes tecnologías de aprendizaje de dispositivos para procesar eventos sin procesar e identificar la actividad de vulneración y los indicadores de amenazas
- Una pila completa de características de seguridad configuradas para detener eficazmente la instalación de implantes malintencionados, el secuestro de archivos y procesos del sistema, la filtración de datos y otras actividades de amenazas
- Mitigaciones optimizadas de la superficie expuesta a ataques, maximizando las defensas estratégicas frente a la actividad de amenazas y minimizando el impacto en la productividad

## <a name="enroll-devices-to-intune-management"></a>Inscribir dispositivos en la administración de Intune

La administración de configuración de dispositivos funciona estrechamente con Intune administración de dispositivos para establecer el inventario de los dispositivos de la organización y la configuración de seguridad de línea base. Podrá realizar un seguimiento y administrar los problemas de configuración en dispositivos Windows administrados Intune.

Antes de asegurarse de que los dispositivos están configurados correctamente, inscríbases en Intune administración. Intune inscripción es sólida y tiene varias opciones de inscripción para dispositivos Windows. Para obtener más información sobre Intune opciones de inscripción, consulte [Configuración de la inscripción para dispositivos Windows](/intune/windows-enroll).

> [!NOTE]
> Para inscribir dispositivos Windows en Intune, ya se deben haber asignado licencias a los administradores. [Obtenga información sobre la asignación de licencias para la inscripción de dispositivos](/intune/licenses-assign).

> [!TIP]
> Para optimizar la administración de dispositivos a través de Intune, [conecte Intune a Defender para punto de conexión](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).

## <a name="obtain-required-permissions"></a>Obtener los permisos necesarios

De forma predeterminada, solo los usuarios a los que se ha asignado el rol Administrador global o Administrador de servicios de Intune en Azure AD pueden administrar y asignar los perfiles de configuración del dispositivo necesarios para la incorporación de dispositivos y la implementación de la línea de base de seguridad.

Si se le han asignado otros roles, asegúrese de que tiene los permisos necesarios:

- Permisos completos para las configuraciones de dispositivos
- Permisos completos para líneas base de seguridad
- Permisos de lectura para directivas de cumplimiento de dispositivos
- Permisos de lectura para la organización

:::image type="content" source="images/secconmgmt_intune_permissions.png" alt-text="Los permisos necesarios en intune" lightbox="images/secconmgmt_intune_permissions.png":::

*Permisos de configuración del dispositivo en Intune*

> [!TIP]
> Para obtener más información sobre la asignación de permisos en Intune, [lea sobre la creación de roles personalizados](/intune/create-custom-role#to-create-a-custom-role).

## <a name="in-this-section"></a>En esta sección

Tema|Descripción
:---|:---
[Incorporación de dispositivos a Defender para punto de conexión](configure-machines-onboarding.md)|Realice un seguimiento del estado de incorporación de dispositivos administrados por Intune e incorpore más dispositivos a través de Intune. 
[Aumento del cumplimiento de la línea base de seguridad de Defender para punto de conexión](configure-machines-security-baseline.md)|Realice un seguimiento del cumplimiento y el incumplimiento de la línea base. Implemente la línea base de seguridad en más dispositivos administrados Intune.
[Optimizar la implementación y las detecciones de reglas de ASR](configure-machines-asr.md)|Revise la implementación de reglas y ajuste las detecciones mediante herramientas de análisis de impacto en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
