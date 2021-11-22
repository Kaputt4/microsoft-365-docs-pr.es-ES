---
title: Paso 2. Inscripción de dispositivos para la administración con Intune
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-jun2020
keywords: ''
description: ''
ms.openlocfilehash: 466bb739085625a8992595a2d518e6f1cbdeb4a4
ms.sourcegitcommit: 2ea2105d40b60a87fc9aa30f392a73a3a9db6d99
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2021
ms.locfileid: "61129531"
---
# <a name="step-2-enroll-devices-into-management-with-intune"></a>Paso 2. Inscripción de dispositivos para la administración con Intune

Existen varias maneras de proteger el punto de conexión, un término que se usa a menudo para hacer referencia a la entidad combinada, incluidos los dispositivos, las aplicaciones y la identidad del usuario. Las directivas de seguridad deben aplicarse de forma coherente y confiable no solo en las aplicaciones, sino también en el propio dispositivo. Inscribir el dispositivo para la administración y registrarse con un proveedor de identidades en la nube, como Azure Active Directory, es un buen comienzo.

Tanto si un dispositivo es un dispositivo BYOD de propiedad personal como un dispositivo de propiedad corporativa y totalmente administrado, es conveniente tener visibilidad sobre los puntos de conexión que acceden a los recursos de la organización para asegurarse de que solo permite dispositivos en buen estado y compatibles. Esto incluye el estado y la confiabilidad de las aplicaciones móviles y de escritorio que se ejecutan en los puntos de conexión. Es necesario asegurarse de que esas aplicaciones estén en buen estado y sean compatibles, y que evitan que los datos corporativos se filtren a aplicaciones o servicios de consumidor a través de intenciones malintencionadas o medios accidentales.

El proceso de inscripción de dispositivos establece una relación entre el usuario, el dispositivo y el servicio Microsoft Intune. El uso de Microsoft Intune como un servicio independiente le permite usar una única consola de administración basada en la Web para administrar equipos Windows, macOS y las plataformas de dispositivos móviles más populares.

En este artículo, se recomiendan métodos para inscribir dispositivos en la administración mediante Intune. Para obtener más información sobre estos métodos y cómo implementar cada uno de ellos, consulte [Guía de implementación: Inscribir dispositivos en Microsoft Intune](/microsoft-365/security/defender/eval-overview?view=o365-worldwide).

![Pasos para administrar dispositivos](../media/devices/intune-mdm-steps-1.png#lightbox)

## <a name="windows-enrollment"></a>Inscripción de Windows
Existen varias opciones para inscribir dispositivos Windows 10 y Windows 11. Los métodos más comunes incluyen estos dos:

- Azure Active Directory (Azure AD): une el dispositivo con Azure Active Directory y permite que los usuarios inicien sesión en Windows con sus credenciales de Azure AD. Si la inscripción automática está habilitada, el dispositivo se inscribe automáticamente en Intune. La ventaja de la inscripción automática es un proceso de un solo paso para el usuario. De lo contrario, tendrán que inscribirse por separado a través de la inscripción solo de MDM y volver a escribir sus credenciales. Los usuarios se inscriben de esta manera durante la configuración rápida inicial de Windows o desde Configuración. El dispositivo se marca como un dispositivo de propiedad corporativa en Intune.
- Autopilot: automatiza la unión a Azure AD e inscribe nuevos dispositivos corporativos en Intune. Este método simplifica la experiencia lista para usar y elimina la necesidad de aplicar imágenes de sistema operativo personalizadas a los dispositivos. Cuando los administradores usan Intune para administrar dispositivos Autopilot, pueden administrar directivas, perfiles, aplicaciones y mucho más una vez inscritos. Existen cuatro tipos de implementación de Autopilot: modo de implementación automática (para quioscos, señalización digital o un dispositivo compartido); modo controlado por el usuario (para usuarios tradicionales); Windows Autopilot, para la implementación aprovisionada previamente, permite a los partners o al personal de TI aprovisionar previamente un equipo que ejecuta Windows 10 o Windows 11 para que esté completamente configurado y listo para la empresa; y Autopilot, para dispositivos existentes le permite implementar, de manera sencilla, la versión más reciente de Windows en los dispositivos existentes.

Para ver opciones adicionales, incluida la inscripción de dispositivos Windows BYOD, consulte [Todos los métodos de inscripción para dispositivos Windows](/mem/intune/enrollment/windows-enrollment-methods).

## <a name="iosipados-and-ipados-enrollment"></a>Inscripción de iOS/iPadOS e iPadOS

En el caso de los dispositivos de propiedad del usuario (BYOD), puede permitir que los usuarios inscriban sus dispositivos personales para la administración de Intune mediante uno de los métodos siguientes.
- La inscripción de dispositivos es lo que se puede considerar una inscripción BYOD típica. Proporciona a los administradores una amplia gama de opciones de administración.
- La inscripción de usuarios es un proceso de inscripción más simplificado que proporciona a los administradores un subconjunto de opciones de administración de dispositivos. Esta característica está actualmente en versión preliminar.

Para las organizaciones que compran dispositivos para sus usuarios, Intune admite los siguientes métodos de inscripción de dispositivos propiedad de la empresa de iOS/iPadOS:
- Inscripción automática de dispositivos (ADE) de Apple
- Apple School Manager
- Inscripción del Asistente de configuración de Apple Configurator
- Inscripción directa de Apple Configurator

Para obtener más información, consulte [Inscripción de dispositivos iOS/iPadOS en Intune](/mem/intune/enrollment/ios-enroll).

## <a name="android-enrollment"></a>Inscripción de Android 

Existen varias opciones para la inscripción de Android en función del tipo de dispositivo, el tipo de inscripción que le gustaría admitir, así como aspectos como la versión de Android que usa o incluso el fabricante (en particular, Samsung). La mayoría de las organizaciones usan perfiles de Android Work para sus usuarios finales, en particular, en escenarios BYOD. 

Con un perfil de trabajo de Android, la información del usuario final se separa de forma distinta de contenedores de datos, así como lo hacen las aplicaciones independientes para uso personal y profesional. Esta es una manera ideal para que los usuarios inscriban su dispositivo a la vez que mantienen la privacidad de sus propios datos y la seguridad de los datos corporativos. 

Sin embargo, si su organización se encuentra probando dispositivos Android, puede optar por usar lo que se denomina dispositivo totalmente administrado (afinidad de usuario) o dedicado (sin afinidad de usuario).

Para obtener más información sobre la inscripción de Android, así como la inscripción automatizada de Android, consulte [Inscripción de dispositivos Android](/mem/intune/enrollment/android-enroll).

## <a name="macos-enrollment"></a>Inscripción de macOS

La inscripción para macOS puede ser un tema complicado para muchas organizaciones de TI. A menos que la mayoría de los usuarios sean usuarios de Mac, es posible que no administre estos tipos de dispositivos en gran medida. Si tiene un pequeño número de usuarios de macOS, se recomienda la inscripción solo de Intune. Si tiene un gran número de usuarios de macOS, se recomienda la inscripción de Intune + Jamf.  
- Inscripción solo de Intune: esto es para la administración básica de dispositivos macOS. Requerirá un proceso manual muy similar a la mayoría de las demás opciones de inscripción basadas en el usuario. Sin embargo, si tiene un pequeño número de dispositivos Mac, este proceso puede ser más fácil que configurar una infraestructura automatizada completa solo para esos pocos usuarios. Con la inscripción solo de Intune, tiene la capacidad de implementar elementos como certificados, configuraciones de contraseña y aplicaciones. También puede configurar directivas de cumplimiento y habilitar el acceso condicional, así como la capacidad de aplicar el cifrado y el borrado del dispositivo. 
- Inscripción de Intune y Jamf: para aquellos que buscan la compatibilidad más profunda con la administración de Mac, con Jamf + Intune para el acceso condicional, tenemos una excelente solución que combina las amplias funcionalidades de administración de Mac de Jamf con el cumplimiento de Intune para habilitar el acceso condicional. En este escenario, usted sigue administrando completamente el dispositivo con Jamf, a la vez que puede tomar esas señales de Jamf para aumentar la seguridad.

Para obtener más información sobre la inscripción de macOS, consulte [Configurar la inscripción para dispositivos macOS en Intune](/mem/intune/enrollment/macOS-enroll).

## <a name="next-steps"></a>Pasos siguientes

Vaya al paso [3. Configuración de directivas de cumplimiento para dispositivos con Intune](manage-devices-with-intune-compliance-policies.md).

