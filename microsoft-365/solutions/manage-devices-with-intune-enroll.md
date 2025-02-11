---
title: Step 2. Enroll devices into management with Intune
ms.author: bcarter
author: brendacarter
f1.keywords:
- enroll devices into management
- enroll devices to Intune
- Intune mobile device platforms
manager: dougeby
audience: ITPro
description: Use Intune y Autopilot para inscribir dispositivos en la administración con el fin de asegurarse de que las aplicaciones que se ejecutan en ellos son compatibles y para evitar pérdidas de datos corporativos.
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
keywords: ''
ms.openlocfilehash: 0c6e49b3a654f29b76016487f88126ae77a2630c
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986606"
---
# <a name="step-2-enroll-devices-to-intune"></a>Paso 2. Inscribir dispositivos en Intune

Existen varias maneras de proteger el punto de conexión, un término que se usa a menudo para hacer referencia a la entidad combinada, incluidos los dispositivos, las aplicaciones y la identidad del usuario. Las directivas de seguridad deben aplicarse de forma coherente y confiable no solo en las aplicaciones, sino también en el propio dispositivo. Inscribir el dispositivo en Intune y registrarse con un proveedor de identidades en la nube, como Azure Active Directory, es un buen comienzo.

Tanto si un dispositivo es un dispositivo BYOD de propiedad personal como un dispositivo de propiedad corporativa y totalmente administrado, es conveniente tener visibilidad sobre los puntos de conexión que acceden a los recursos de la organización para asegurarse de que solo permite dispositivos en buen estado y compatibles. Esto incluye el estado y la confiabilidad de las aplicaciones móviles y de escritorio que se ejecutan en los puntos de conexión. Es necesario asegurarse de que esas aplicaciones estén en buen estado y sean compatibles, y que evitan que los datos corporativos se filtren a aplicaciones o servicios de consumidor a través de intenciones malintencionadas o medios accidentales.

El proceso de inscripción de dispositivos establece una relación entre el usuario, el dispositivo y el servicio Microsoft Intune. El uso de Microsoft Intune como un servicio independiente le permite usar una única consola de administración basada en la Web para administrar equipos Windows, macOS y las plataformas de dispositivos móviles más populares.

This article recommends methods for enrolling devices to Intune. For more information about these methods and how to deploy each one, see [Deployment guidance: Enroll devices in Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment).

![Pasos para administrar dispositivos](../media/devices/intune-mdm-steps-1.png#lightbox)

Utilice la orientación de este artículo junto con esta versión ilustrada de las opciones de inscripción para cada plataforma. 

[![Una representación visual de las opciones de inscripción en Intune por plataforma](../media/devices/msft-intune-enrollment-options-thumb-landscape.png)](https://download.microsoft.com/download/e/6/2/e6233fdd-a956-4f77-93a5-1aa254ee2917/msft-intune-enrollment-options.pdf) <br/> [PDF](https://download.microsoft.com/download/e/6/2/e6233fdd-a956-4f77-93a5-1aa254ee2917/msft-intune-enrollment-options.pdf) | [Visio](https://download.microsoft.com/download/e/6/2/e6233fdd-a956-4f77-93a5-1aa254ee2917/msft-intune-enrollment-options.vsdx) <br/> Actualizado en junio de 2022



## <a name="windows-enrollment"></a>Inscripción de Windows
Existen varias opciones para inscribir dispositivos Windows 10 y Windows 11. Los métodos más comunes incluyen estos dos:

- Azure Active Directory (Azure AD): une el dispositivo con Azure Active Directory y permite que los usuarios inicien sesión en Windows con sus credenciales de Azure AD. Si la inscripción automática está habilitada, el dispositivo se inscribe automáticamente en Intune. La ventaja de la inscripción automática es que consiste en un proceso de un solo paso para el usuario. En caso contrario, tendrán que inscribirse por separado a través de la inscripción solo MDM y volver a escribir sus credenciales. Los usuarios se inscriben de esta manera durante la configuración rápida de Windows o desde Configuración. El dispositivo se marca como un dispositivo de propiedad corporativa en Intune.
- Autopilot: automatiza la unión a Azure AD e inscribe nuevos dispositivos corporativos en Intune. Este método simplifica la experiencia lista para usar y elimina la necesidad de aplicar imágenes de sistema operativo personalizadas a los dispositivos. Cuando los administradores usan Intune para administrar dispositivos Autopilot, pueden administrar directivas, perfiles, aplicaciones y mucho más una vez inscritos. Existen cuatro tipos de implementación de Autopilot: modo de implementación automática (para quioscos, señalización digital o un dispositivo compartido); modo controlado por el usuario (para usuarios tradicionales); Windows Autopilot, para la implementación aprovisionada previamente, permite a los partners o al personal de TI aprovisionar previamente un equipo que ejecuta Windows 10 o Windows 11 para que esté completamente configurado y listo para la empresa; y Autopilot, para dispositivos existentes le permite implementar, de manera sencilla, la versión más reciente de Windows en los dispositivos existentes.

Para obtener más opciones, incluida la inscripción de dispositivos Windows BYOD, consulte [Inscribir dispositivos Windows en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-windows).

## <a name="ios-and-ipados-enrollment"></a>Inscripción de iOS y iPadOS

En el caso de los dispositivos de propiedad del usuario (BYOD), puede permitir que los usuarios inscriban sus dispositivos personales con Intune mediante uno de los métodos siguientes.
- La inscripción de dispositivos es lo que puede considerar como una inscripción BYOD típica. Proporciona a los administradores una amplia gama de opciones de administración.
- User enrollment is a more streamlined enrollment process that provides admins with a subset of device management options. This feature is currently in preview.

Para las organizaciones que compran dispositivos para sus usuarios, Intune admite los siguientes métodos de inscripción de dispositivos propiedad de la empresa de iOS/iPadOS:
- Inscripción de dispositivo automatizada (ADE) de Apple
- Apple School Manager
- Inscripción de Apple Configurator mediante el Asistente de configuración
- Inscripción directa de Apple Configurator

Para obtener más información, consulte [Inscribir dispositivos iOS y iPadOS en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados).

## <a name="android-enrollment"></a>Inscripción de Android 

There are several options for Android Enrollment depending on the type of device, the type of enrollment you’d like to support, as well as things like the Android version you are using or even the manufacturer (particularly Samsung). Most organizations use Android Work profiles for their end users, particular in BYOD scenarios. 

Con un perfil de trabajo Android, la información del usuario final se separa de forma distinta con contenedores de datos y aplicaciones independientes para uso personal y profesional. Esta es una manera ideal para que los usuarios inscriban su dispositivo a la vez que mantienen la privacidad de sus propios datos y la seguridad de los datos corporativos. 

Sin embargo, si su organización proporciona dispositivos Android, puede optar por usar lo que se denomina dispositivo totalmente administrado (afinidad de usuario) o dedicado (sin afinidad de usuario).

Para obtener más información sobre la inscripción de Android, consulte [Inscribir dispositivos Android en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android).

## <a name="macos-enrollment"></a>Inscripción de macOS

La inscripción para macOS puede ser un tema complicado para muchas organizaciones de TI. A menos que la mayoría de los usuarios sean usuarios de Mac, es posible que no administre estos tipos de dispositivos en gran medida. Si tiene un pequeño número de usuarios de macOS, se recomienda la inscripción solo de Intune. Si tiene un gran número de usuarios de macOS, se recomienda la inscripción de Intune + Jamf.  
- Inscripción solo de Intune: esto es para la administración básica de dispositivos macOS. Requerirá un proceso manual muy similar a la mayoría de las demás opciones de inscripción basadas en el usuario. Sin embargo, si tiene un pequeño número de dispositivos Mac, este proceso puede ser más fácil que configurar una infraestructura automatizada completa solo para esos pocos usuarios. Con la inscripción solo de Intune, tiene la capacidad de implementar elementos como certificados, configuraciones de contraseña y aplicaciones. También puede configurar directivas de cumplimiento y habilitar el acceso condicional, así como la capacidad de aplicar el cifrado y el borrado del dispositivo. 
- Inscripción a Intune y Jamf: para aquellos que buscan un soporte completo para la administración de Mac, con Jamf + Intune para acceso condicional, tenemos una gran solución que combina las numerosas capacidades de administración de Mac de Jamf con el cumplimiento de Intune para habilitar el acceso condicional. En este escenario, usted sigue administrando completamente el dispositivo con Jamf, a la vez que puede tomar esas señales de Jamf para aumentar la seguridad.

Para obtener más información sobre la inscripción de macOS, consulte [Inscribir dispositivos macOS en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-macos).

## <a name="next-steps"></a>Pasos siguientes

Vaya al paso [3. Configuración de directivas de cumplimiento para dispositivos con Intune](manage-devices-with-intune-compliance-policies.md).

