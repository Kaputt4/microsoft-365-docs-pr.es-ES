---
title: 'Cuaderno de estrategias de prueba: Microsoft Defender para punto de conexión'
description: Use esta guía para sacar el máximo partido a su evaluación gratuita de 90 días. Vea cómo Defender para punto de conexión puede ayudar a prevenir, detectar, investigar y responder a amenazas avanzadas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: 07/07/2022
ms.prod: m365-security
ms.technology: mde
ms.localizationpriority: medium
ms.reviewer: ''
f1.keywords: NOCSH
ms.openlocfilehash: 2b7a4d47d07fd609fb9dd424f2a8b89af2ed0b9b
ms.sourcegitcommit: 9fdb5c5b9eaf0c8a8d62b579a5fb5a5dc2d29fa9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2022
ms.locfileid: "66714830"
---
# <a name="trial-playbook-microsoft-defender-for-endpoint"></a>Cuaderno de estrategias de prueba: Microsoft Defender para punto de conexión

¡Bienvenido al cuaderno de estrategias de prueba del plan 2 de Microsoft Defender para punto de conexión!

Este cuaderno de estrategias es una guía sencilla para ayudarle a sacar el máximo partido a su evaluación gratuita. Con los pasos sugeridos de este artículo del equipo de Microsoft Defender, aprenderá cómo Defender para punto de conexión puede ayudarle a prevenir, detectar, investigar y responder a amenazas avanzadas.

## <a name="what-is-defender-for-endpoint"></a>¿Qué es Defender para punto de conexión?

[Defender para punto de conexión](microsoft-defender-endpoint.md) es una plataforma de seguridad de puntos de conexión empresariales que usa la siguiente combinación de tecnología integrada en Windows y el sólido servicio en la nube de Microsoft: 

- **Sensores de comportamiento de punto de conexión**: incrustados en Windows, estos sensores recopilan y procesan señales de comportamiento del sistema operativo y envían datos de sensor a la instancia privada, aislada y en la nube de Defender para punto de conexión.

- **Análisis de seguridad en la nube**: con macrodatos, aprendizaje de dispositivos y óptica única de Microsoft en todo el ecosistema de Windows, productos en la nube empresarial (como Microsoft 365) y recursos en línea, las señales de comportamiento se traducen en conclusiones, detecciones y respuestas recomendadas a amenazas avanzadas.

- **Inteligencia sobre amenazas**: generada por los cazadores y equipos de seguridad de Microsoft, y aumentada por la inteligencia sobre amenazas proporcionada por los asociados, la inteligencia de amenazas permite a Defender para punto de conexión identificar herramientas, técnicas y procedimientos del atacante y generar alertas cuando se observan en los datos del sensor recopilados.

<center><h2>Microsoft Defender para punto de conexión</center></h2>
<table>
<tr>
<td><a href="microsoft-defender-endpoint.md#tvm"><center><img src="images/logo-mdvm.png" alt="Vulnerability Management"> <br><b> Administración de vulnerabilidades de Defender</b></center></a></td>
<td><a href="microsoft-defender-endpoint.md#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Reducción de la superficie expuesta a ataques</b></center></a></td>
<td><center><a href="microsoft-defender-endpoint.md#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Protección de última generación</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Detección y respuesta de puntos de conexión</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Investigación y corrección automatizadas</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Expertos en amenazas de Microsoft</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="microsoft-defender-endpoint.md#apis"><center><b>Configuración y administración centralizadas, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="microsoft-defender-endpoint.md#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

**Comencemos**

## <a name="set-up-your-trial"></a>Configuración de la prueba

1. [Confirme el estado de la licencia](#step-1-confirm-your-license-state).
2. [Configure el control de acceso basado en rol y conceda permisos al equipo de seguridad](#step-2-set-up-role-based-access-control-and-grant-permissions-to-your-security-team).
3. [Visite el portal de Microsoft 365 Defender](#step-3-visit-the-microsoft-365-defender-portal).
4. [Incorporación de puntos de conexión mediante cualquiera de las herramientas de administración admitidas](#step-4-onboard-endpoints-using-any-of-the-supported-management-tools).
5. [Configure las funcionalidades](#step-5-configure-capabilities).
6. [Experimente Microsoft Defender para punto de conexión a través de ataques simulados](#step-6-experience-microsoft-defender-for-endpoint-through-simulated-attacks).
7. [Configure el laboratorio de evaluación de Microsoft Defender para punto de conexión](#step-7-set-up-the-microsoft-defender-for-endpoint-evaluation-lab).

## <a name="step-1-confirm-your-license-state"></a>Paso 1: Confirmar el estado de la licencia

Para asegurarse de que la suscripción de Defender para punto de conexión está aprovisionada correctamente, puede comprobar el estado de la licencia en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)) o Azure Active Directory ([https://portal.azure.com](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)).

[Compruebe el estado de la licencia](production-deployment.md#check-license-state).

## <a name="step-2-set-up-role-based-access-control-and-grant-permissions-to-your-security-team"></a>Paso 2: Configuración del control de acceso basado en rol y concesión de permisos al equipo de seguridad

Microsoft recomienda usar el concepto de privilegios mínimos. Defender para punto de conexión usa roles integrados en Azure Active Directory. [Revise los distintos roles disponibles](/azure/active-directory/roles/permissions-reference) y elija los roles adecuados para el equipo de seguridad. Es posible que algunos roles deban aplicarse temporalmente y quitarse una vez completada la prueba.

Use [Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure) para administrar los roles a fin de proporcionar auditoría, control y revisión de acceso adicionales para los usuarios con permisos de directorio.

Defender for Endpoint admite dos maneras de administrar permisos:

- Administración básica de permisos: establezca los permisos en acceso completo o de solo lectura. Los usuarios con roles de administrador global o administrador de seguridad en Azure Active Directory tienen acceso completo. El rol Lector de seguridad tiene acceso de solo lectura y no concede acceso para ver el inventario de máquinas o dispositivos.
- Control de acceso basado en rol (RBAC): establezca permisos granulares mediante la definición de roles, la asignación de grupos de usuarios de Azure AD a los roles y la concesión de acceso a los grupos de usuarios a los grupos de dispositivos. Para obtener más información, consulte [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md).

## <a name="step-3-visit-the-microsoft-365-defender-portal"></a>Paso 3: Visitar el portal de Microsoft 365 Defender

El portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) es donde puede acceder a las funcionalidades de Defender para punto de conexión.

1. [Revise lo que debe esperar](../defender/microsoft-365-defender-portal.md) en el portal de Microsoft 365 Defender.

2. Vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión.

3. En el panel de navegación, consulte la sección **Puntos de conexión** para acceder a las funcionalidades. 

## <a name="step-4-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Paso 4: Incorporación de puntos de conexión mediante cualquiera de las herramientas de administración admitidas 

En esta sección se describen los pasos generales para incorporar dispositivos (puntos de conexión).

1. [Vea este vídeo](https://www.microsoft.com/videoplayer/embed/RE4bGqr) para obtener una introducción rápida al proceso de incorporación y obtener información sobre las herramientas y métodos disponibles.

2. Revise las [opciones de la herramienta de incorporación de dispositivos](onboarding.md) y seleccione la opción más adecuada para su entorno. 

## <a name="step-5-configure-capabilities"></a>Paso 5: Configuración de funcionalidades 

Después de incorporar dispositivos (puntos de conexión), configurará las distintas funcionalidades, como la detección y respuesta de puntos de conexión, la protección de próxima generación y la reducción de la superficie expuesta a ataques.

Use [esta tabla](onboarding.md) para elegir los componentes que se van a configurar. Se recomienda configurar todas las funcionalidades disponibles, pero puede omitir las que no se aplican.

## <a name="step-6-experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Paso 6: Experiencia Microsoft Defender para punto de conexión a través de ataques simulados

Es posible que quiera experimentar Defender para punto de conexión antes de incorporar más de unos pocos dispositivos al servicio. Para ello, puede ejecutar simulaciones de ataque controladas en algunos dispositivos de prueba. Después de ejecutar los ataques simulados, puede revisar cómo Defender for Endpoint expone la actividad malintencionada y explorar cómo permite una respuesta eficaz.

Para ejecutar cualquiera de las simulaciones proporcionadas, necesita al menos [un dispositivo incorporado](onboard-configure.md).

1. Acceda a los tutoriales. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, en **Puntos de conexión**, elija **Tutoriales**.

2. Lea el documento del tutorial proporcionado con cada escenario de ataque. Cada documento incluye requisitos del sistema operativo y de la aplicación e instrucciones detalladas específicas de un escenario de ataque.

3. [Ejecute una simulación](attack-simulations.md).

## <a name="step-7-set-up-the-microsoft-defender-for-endpoint-evaluation-lab"></a>Paso 7: Configuración del laboratorio de evaluación de Microsoft Defender para punto de conexión   

El laboratorio de evaluación de Microsoft Defender para punto de conexión está diseñado para eliminar las complejidades de la configuración de dispositivos y entornos para que pueda centrarse en evaluar las funcionalidades de la plataforma, ejecutar simulaciones y ver las características de prevención, detección y corrección en acción. Con la experiencia de configuración simplificada en el laboratorio de evaluación, puede centrarse en ejecutar sus propios escenarios de prueba y en las simulaciones pre-creadas para ver cómo funciona Defender para punto de conexión.

- [Vea la introducción al vídeo](https://www.microsoft.com/videoplayer/embed/RE4qLUM) del laboratorio de evaluación.
- [Introducción al laboratorio](evaluation-lab.md) 


## <a name="see-also"></a>Vea también

- [Documentación técnica de Defender para punto de conexión](microsoft-defender-endpoint.md)
- [Biblioteca de contenido técnico de Seguridad de Microsoft](https://www.microsoft.com/security/content-library/Home/Index)
- [Demostración de Defender para punto de conexión](https://cdx.transform.microsoft.com/experience-detail/d5eca65d-13a3-464d-9171-c24cf9dd6050)

