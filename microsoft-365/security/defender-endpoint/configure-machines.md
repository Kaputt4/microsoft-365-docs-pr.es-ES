---
title: Asegurarse de que los dispositivos estén configurados de manera adecuada
description: Configure correctamente los dispositivos para aumentar la resistencia general frente a las amenazas y mejorar su capacidad para detectar y responder a los ataques.
keywords: onboard, administración de Intune, Microsoft Defender para Endpoint, Microsoft Defender, Windows Defender, reducción de superficie de ataque, ASR, línea base de seguridad
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 47c3cb5d680899a28e6467b24ef398a428851a07
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476167"
---
# <a name="ensure-your-devices-are-configured-properly"></a>Asegurarse de que los dispositivos estén configurados de manera adecuada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Con dispositivos configurados correctamente, puedes aumentar la resistencia general frente a amenazas y mejorar tu capacidad para detectar y responder a los ataques. La administración de la configuración de seguridad ayuda a garantizar que los dispositivos:

- Incorporación a Microsoft Defender para punto de conexión
- Cumplir o superar la configuración de línea base de seguridad de Defender for Endpoint
- Tener mitigaciones de superficie de ataques estratégicos en su lugar

Haga **clic en Administración de** configuración en el menú de navegación para abrir la página Administración de configuración de dispositivos.

:::image type="content" source="images/secconmgmt_main.png" alt-text="Página Administración de configuración de seguridad" lightbox="images/secconmgmt_main.png":::

*Página de administración de configuración de dispositivos*

Puedes realizar un seguimiento del estado de configuración en un nivel organizativo y tomar medidas rápidamente en respuesta a una cobertura de incorporación deficiente, problemas de cumplimiento y mitigaciones de superficies de ataque mal optimizadas a través de vínculos directos y profundos a páginas de administración de dispositivos en Microsoft Intune y <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.

Al hacerlo, se beneficia de:

- Visibilidad completa de los eventos en los dispositivos
- Inteligencia de amenazas sólida y tecnologías de aprendizaje de dispositivos eficaces para procesar eventos sin procesar e identificar la actividad de vulneración y los indicadores de amenazas
- Una pila completa de características de seguridad configuradas para detener eficazmente la instalación de implantes malintencionados, el secuestro de archivos y procesos del sistema, la exfiltración de datos y otras actividades de amenazas
- Mitigaciones optimizadas de superficie de ataque, maximizando las defensas estratégicas contra la actividad de amenazas al mismo tiempo que minimiza el impacto en la productividad

## <a name="enroll-devices-to-intune-management"></a>Inscribir dispositivos en la administración de Intune

La administración de configuración de dispositivos funciona estrechamente con la administración de dispositivos de Intune para establecer el inventario de los dispositivos de la organización y la configuración de seguridad de línea base. Podrás realizar un seguimiento y administrar problemas de configuración en dispositivos Windows Intune.

Antes de garantizar que los dispositivos estén configurados correctamente, inscríbalos en la administración de Intune. La inscripción de Intune es sólida y tiene varias opciones de inscripción para Windows dispositivos. Para obtener más información acerca de las opciones de inscripción de Intune, consulta cómo [configurar la inscripción para Windows dispositivos](/intune/windows-enroll).

> [!NOTE]
> Para inscribir Windows dispositivos en Intune, los administradores ya deben tener asignadas licencias. [Obtenga información sobre la asignación de licencias para la inscripción de dispositivos](/intune/licenses-assign).

> [!TIP]
> Para optimizar la administración de dispositivos a través de Intune, [conecta Intune a Defender para endpoint](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).

## <a name="obtain-required-permissions"></a>Obtener los permisos necesarios

De forma predeterminada, solo los usuarios a los que se haya asignado el rol Administrador global o administrador de servicio de Intune en Azure AD pueden administrar y asignar los perfiles de configuración del dispositivo necesarios para incorporar dispositivos e implementar la línea base de seguridad.

Si se le han asignado otros roles, asegúrese de que tiene los permisos necesarios:

- Permisos completos para configuraciones de dispositivos
- Permisos completos para las líneas base de seguridad
- Permisos de lectura para directivas de cumplimiento de dispositivos
- Permisos de lectura para la organización

:::image type="content" source="images/secconmgmt_intune_permissions.png" alt-text="Los permisos necesarios en intune" lightbox="images/secconmgmt_intune_permissions.png":::

*Permisos de configuración de dispositivos en Intune*

> [!TIP]
> Para obtener más información sobre cómo asignar permisos en Intune, [lea sobre cómo crear roles personalizados](/intune/create-custom-role#to-create-a-custom-role).

## <a name="in-this-section"></a>En esta sección

Tema|Descripción
:---|:---
[Obtener dispositivos incorporados a Defender for Endpoint](configure-machines-onboarding.md)|Realice un seguimiento del estado de incorporación de dispositivos administrados por Intune e incorpore más dispositivos a través de Intune. 
[Aumentar el cumplimiento de la línea base de seguridad de Defender for Endpoint](configure-machines-security-baseline.md)|Realizar un seguimiento del cumplimiento de línea base y el incumplimiento. Implemente la línea base de seguridad en más dispositivos administrados por Intune.
[Optimizar la implementación y las detecciones de reglas de ASR](configure-machines-asr.md)|Revise la implementación de reglas y ajuste las detecciones con herramientas de análisis de impacto <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">en Microsoft 365 Defender portal</a>.

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
