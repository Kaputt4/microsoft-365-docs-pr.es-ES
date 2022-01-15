---
title: Administrar dispositivos con Intune
ms.author: bcarter
author: brendacarter
f1.keywords:
- enroll devices into Intune
- manage device endpoints
- zero trust deployment stack
- device management with zero trust
manager: dougeby
audience: ITPro
ms.topic: article
description: Inscriba los dispositivos de punto de conexión en Microsoft Intune como parte de la arquitectura de seguridad de Confianza cero, protegiendo contra ransomware mientras crea protección para trabajadores remotos.
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-managedevices
- m365solution-overview
ms.custom: ''
keywords: ''
ms.openlocfilehash: 70824645edbf7c56a77aed76ec8fd07784bc43da
ms.sourcegitcommit: 23166424125b80b2d615643f394a3c023cba641d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2022
ms.locfileid: "62049317"
---
# <a name="manage-devices-with-intune-overview"></a>Información general para administrar dispositivos con Intune

Un componente básico de la seguridad a nivel empresarial incluye la administración y protección de dispositivos. Tanto si va a crear una arquitectura de seguridad de Confianza cero, proteger su entorno contra ransomware o crear protecciones para admitir trabajadores remotos, la administración de dispositivos forma parte de la estrategia. Aunque Microsoft 365 incluye varias herramientas y metodologías para administrar y proteger dispositivos, esta guía explica las recomendaciones de Microsoft en Microsoft Intune. Esta es la guía adecuada para ti si:

- Tienes pensado inscribir dispositivos en Intune a través de Azure AD Join (que incluye Unión a Azure AD híbrido).
- Tienes pensado inscribir manualmente dispositivos en Intune.
- Permites dispositivos BYOD con planes para implementar la protección de aplicaciones y datos o inscribes estos dispositivos en la administración.

Por otro lado, si tu entorno incluye planes para la administración conjunta, incluidos Microsoft Endpoint Configuration Manager, consulta la [Documentación de administración conjunta](/mem/configmgr/comanage/) para desarrollar la mejor ruta de acceso para su organización. Si tu entorno incluye planes para PC en la nube Windows 365, consulta la [Documentación de Windows 365 Enterprise](/windows-365/enterprise/) para desarrollar la mejor ruta de acceso para tu organización. 

## <a name="why-manage-endpoints"></a>¿Por qué administrar puntos de conexión?
La empresa moderna tiene una diversidad increíble de puntos de conexión que acceden a sus datos. Esta configuración crea una gran superficie expuesta a ataques y, como resultado, los puntos de conexión pueden convertirse fácilmente en el vínculo más débil de la estrategia de seguridad de Confianza cero. 

Principalmente controlado por la necesidad a medida que el mundo cambia a un modelo de trabajo remoto o híbrido, los usuarios trabajan desde cualquier lugar, desde cualquier dispositivo, más que en cualquier momento de la historia. Los atacantes están ajustando rápidamente sus tácticas para aprovechar este cambio. Muchas organizaciones se enfrentan a recursos restringidos a medida que se enfrentan a estos nuevos desafíos empresariales. Prácticamente de la noche a la mañana, las empresas han acelerado la transformación digital. En pocas palabras, la forma de trabajar de las personas ha cambiado. Ya no esperamos acceder a la infinidad de recursos corporativos solo desde la oficina y desde dispositivos propiedad de la empresa.

Obtener visibilidad de los puntos de conexión que acceden a los recursos corporativos es el primer paso de la estrategia de los dispositivos de Confianza cero. Normalmente, las empresas son proactivas en la protección de los equipos frente a vulnerabilidades y ataques, mientras que los dispositivos móviles a menudo pasan a ser no supervisados y sin protecciones. Para asegurarse de no exponer los datos a riesgos, es necesario supervisar todos los puntos de conexión en busca de riesgos y emplear controles de acceso granulares para ofrecer el nivel adecuado de acceso en función de la directiva de la organización. Por ejemplo, si un dispositivo personal es descodificado, puede bloquear el acceso para asegurarse de que las aplicaciones empresariales no se exponen a vulnerabilidades conocidas.

Esta serie de artículos te guían a través de un proceso recomendado para administrar los dispositivos que acceden a los recursos. Si sigues los pasos recomendados, tu organización logrará una protección muy sofisticada para los dispositivos y los recursos a los que acceden.


## <a name="implementing-the-layers-of-protection-on-and-for-devices"></a>Implementación de las capas de protección en los dispositivos y para ellos

La protección de los datos y las aplicaciones en los dispositivos y para los propios dispositivos es un proceso de varias capas. Hay algunas protecciones que puedes obtener en dispositivos no administrados. Después de inscribir dispositivos en la administración, puedes implementar controles más sofisticados. Cuando se implementa la protección contra amenazas en los puntos de conexión, obtienes aún más información y la capacidad de corregir automáticamente algunos ataques. Por último, si tu organización ha puesto el trabajo en identificar datos confidenciales, aplicar etiquetas y clasificación, y configurar directivas de prevención de pérdida de datos, puedes obtener una protección aún más pormenorizada de los datos en los puntos de conexión.

En el diagrama siguiente se muestran los bloques de creación para lograr una posición de seguridad de Confianza cero para Microsoft 365 y otras aplicaciones SaaS que se introducen en este entorno. Los elementos relacionados con los dispositivos se numeran del 1 al 7. Estas son las capas de protección que administran los dispositivos que se coordinan con otros administradores para realizar la tarea. 

![Pila de implementación de Confianza cero de Microsoft 365](../media/devices/m365-zero-trust-deployment-stack-devices.png#lightbox)

En esta ilustración: 


|&nbsp;|Paso |Descripción  |Requisitos de licencias  |
|---------|---------|---------|---------|
|1     | Configurar el punto de partida de directivas de acceso de dispositivos e identidad de Confianza cero       | Trabaja con el administrador de identidades para [Implementar la protección de datos de directivas de protección de aplicaciones (APP) de nivel 2](manage-devices-with-intune-app-protection.md). Estas directivas no requieren que administres dispositivos. Las directivas de APP se configuran en Intune. El administrador de identidades configura una directiva de acceso condicional para requerir las aplicaciones aprobadas.          |E3, E5, F1, F3, F5    |
|2     | Inscribir dispositivos en la administración       | Esta tarea requiere más planeamiento y tiempo para implementar. Aunque tiene una selección de herramientas y métodos para lograrlo, [Paso 3. Inscribir dispositivos en la administración](manage-devices-with-intune-enroll.md) le guía a través del proceso de uso de Intune con Autopilot e inscripción automatizada.      | E3, E5, F1, F3, F5        |
|3     | Configurar directivas de cumplimiento        |  Debes asegurarte de que los dispositivos que acceden a las aplicaciones y los datos cumplen los requisitos mínimos; por ejemplo, están protegidos con código PIN o contraseña, y el sistema operativo está actualizado. Las directivas de cumplimiento son la manera de definir los requisitos que los dispositivos deben cumplir. [Paso 3. Configurar directivas de cumplimiento](manage-devices-with-intune-compliance-policies.md) ayuda a configurar estas directivas.        |   E3, E5, F3, F5      |
|4     | Configurar directivas de acceso a dispositivos e identidades de Enterprise (recomendado) de Confianza cero        |Ahora que los dispositivos están inscritos, puedes trabajar con el administrador de identidades para [ajustar las directivas de acceso condicional para requerir dispositivos correctos y compatibles](manage-devices-with-intune-require-compliance.md).          | E3, E5, F3, F5        |
|5     |Implementar perfiles de configuración      | En lugar de las directivas de cumplimiento de dispositivos que simplemente marcan un dispositivo como compatible o no en función de los criterios que configures, los perfiles de configuración cambian realmente la configuración de los valores de un dispositivo. Puede usar directivas de configuración para proteger los dispositivos frente a ciberamenazas. Vea el [Paso 5. Implementar perfiles de configuración](manage-devices-with-intune-configuration-profiles.md).        | E3, E5, F3, F5        |
|6      |Supervisar el riesgo del dispositivo y el cumplimiento de las líneas base de seguridad         | En este paso, conectará Intune a Microsoft Defender para punto de conexión. Con esta integración, puedes supervisar el riesgo del dispositivo como una condición de acceso. Se bloquearán los dispositivos que se encuentren en un estado de riesgo. También puedes supervisar el cumplimiento de las líneas base de seguridad. Vea el [Paso 6. Supervisar el riesgo del dispositivo y el cumplimiento de las líneas base de seguridad](manage-devices-with-intune-monitor-risk.md).       | E5, F5        |
|7      |Implementar la prevención de pérdida de datos (DLP) con funcionalidades de protección de la información   | Si tu organización ha puesto el trabajo en identificar datos confidenciales y etiquetar documentos, puedes trabajar con el administrador de protección de la información para [proteger información confidencial y documentos en sus dispositivos](manage-devices-with-intune-dlp-mip.md).         | Complemento de cumplimiento de E5, F5        |
| | | | |

## <a name="coordinating-endpoint-management-with-zero-trust-identity-and-device-access-policies"></a>Coordinación de la administración de puntos de conexión con directivas de acceso de dispositivos e identidad de Cero confianza

Esta guía está estrechamente coordinada con las [directivas de acceso de dispositivos e identidad de Confianza cero](../security/office-365-security/microsoft-365-policies-configurations.md). Trabajarás con tu equipo de identidad para llevar a cabo la protección que configuras con Intune en directivas de acceso condicional en Azure AD. 

Esta es una ilustración del conjunto de directivas recomendado con llamadas a los pasos para el trabajo que realizará en Intune/MEM y las directivas de acceso condicional relacionadas que ayudarás a coordinar en Azure AD. 

[![Directivas de acceso de dispositivos e identidad de Confianza cero](../media/devices/identity-device-overview-steps.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-overview-steps.png)


En esta ilustración:
- En el paso 1, [Implementar directivas de protección de aplicaciones de nivel 2](manage-devices-with-intune-app-protection.md), configuras el nivel recomendado de protección de datos con directivas de APP. A continuación, trabajas con el equipo de identidad para configurar la regla de acceso condicional relacionada para requerir el uso de esta protección.
- En los pasos 2, 3 y 4, inscribes los dispositivos en la administración con Intune/MEM, defines directivas de cumplimiento de dispositivos y, a continuación, coordinas con el equipo de identidades para configurar la regla de acceso condicional relacionada para permitir solo el acceso a los dispositivos compatibles. 

<!---
## Managing change with users
--->

## <a name="learning-for-administrators"></a>Aprendizaje para administradores
Los siguientes recursos ayudan a los administradores a aprender conceptos sobre el uso de MEM e Intune.

[Simplifica la administración de dispositivos con Microsoft Endpoint Manager](/learn/modules/simplify-device-management-with-microsoft-endpoint-manager/) Descripción: Obtén información sobre la administración moderna y el Microsoft Endpoint Manager y cómo las herramientas de administración empresarial de Microsoft 365 pueden simplificar la administración de todos los dispositivos.

[Configurar Microsoft Intune](/learn/modules/set-up-microsoft-intune/) Descripción: Microsoft Intune, que forma parte de Microsoft Endpoint Manager, te ayuda a proteger los dispositivos, las aplicaciones y los datos que usan las personas de tu organización para ser productivos. Después de completar este módulo, habrás configurado Microsoft Intune. La configuración incluye revisar las configuraciones admitidas, registrarse en Intune, agregar usuarios y grupos, asignar licencias a usuarios, conceder permisos de administrador y establecer la entidad de MDM.
