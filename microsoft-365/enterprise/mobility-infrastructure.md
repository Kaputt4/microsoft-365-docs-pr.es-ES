---
title: 'Fase 5: administración de dispositivos móviles'
description: Microsoft 365 Enterprise incluye administración de dispositivos móviles con Microsoft Intune. Revise los requisitos y requisitos previos, configurar Intune con su recurso de Azure Active Directory, inscribirse iOS, Mac OS, Android y Windows dispositivos, implementar aplicaciones, crear un perfil de configuración, use una directiva de cumplimiento de normas y habilitar el acceso condicional para mobile administración de dispositivos con Microsoft 365 Enterprise.
keywords: Documentación de Microsoft 365 365 de Microsoft, Microsoft 365 Enterprise, administración de dispositivos móviles, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: 3afc28f0d21918c027a6a1622a40318e333f7ab4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871816"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Fase 5: Administración de dispositivos móviles Microsoft 365 Enterprise

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Esta característica se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

Microsoft 365 Enterprise incluye características para ayudar a administrar los dispositivos y sus aplicaciones, dentro de la organización. Microsoft Intune puede administrar iOS, Android, Mac OS y los dispositivos de Windows para proteger el acceso a los recursos de su organización, incluidos los datos. Intune se integra con Azure Active Directory (AD Azure) y permite los siguientes escenarios empresariales para Microsoft 365:

- Almacenar y compartir archivos, tanto dentro como fuera de la organización, para trabajar de forma fluida más allá de los límites organizativos
- Trabajar de forma segura desde cualquier lugar, en cualquier momento y con cualquier dispositivo para mejorar la productividad, a la vez que se mantiene un estilo de trabajo flexible
- Ofrecer tranquilidad con controles y visibilidad para garantizar la conformidad verificada del sector con normas de cumplimiento internacionales
- Proteger su información y reducir el riesgo de la pérdida de datos
- Detectar y proteger contra las amenazas externas
- Supervisar, informar y analizar la actividad para reaccionar rápidamente para proporcionar seguridad de la organización
- Proteger a los usuarios y sus cuentas

Para obtener más información, vea [Transformación Digital con Microsoft 365](http://transform.microsoft.com). 

En esta fase, inscribirse los dispositivos en Intune y crear y aplicar directivas para ayudar a mantener sus datos seguros y protegidos. La biblioteca completa de documentación Intune está [disponibles en línea](https://docs.microsoft.com/intune). También es recomendable revisar [Intune planeación de la implementación, Guía de diseño e implementación](https://docs.microsoft.com/intune/planning-guide) antes de empezar.

## <a name="step-1-plan-for-your-scenario"></a>Paso 1: Planeación para su escenario

Una de las razones principales para administrar los dispositivos móviles es seguro y proteger los recursos de su organización. [Maneras comunes de utilizar Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) se enumeran algunos ejemplos para el mundo real, incluida la protección de datos y correo electrónico de Office 365.

Intune le ofrece opciones para administrar el acceso a la organización con [Mobile Device Management (MDM) o administración de aplicación de Mobile (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions). MDM es cuando los usuarios "inscribirse" sus dispositivos en Intune. Una vez que se inscriben, son los dispositivos administrados y puede recibir cualquier directivas, reglas y configuración utilizada por la organización. Por ejemplo, puede instalar aplicaciones de características específicas, crear una directiva de contraseña, instalar una conexión VPN y mucho más.

Los usuarios con sus propios dispositivos personales es posible que no desea inscribirse sus dispositivos o administrarse mediante Intune y sus directivas. Pero, todavía tiene que proteger los recursos y los datos de la organización. En este escenario, puede proteger sus aplicaciones con MAM. Por ejemplo, puede usar una directiva MAM que solicita al usuario que escriba un NIP al obtener acceso a SharePoint en el dispositivo.

También determinará cómo va a administrar dispositivos personales o propiedad de la organización. Es posible que desee tratar los dispositivos de forma diferente, según su uso. Por ejemplo, puede ser conveniente diferentes planes de para los usuarios de recursos humanos (HR) o usuarios en ventas. [Escenarios de caso de uso de administración de identidad de dispositivo móvil](https://docs.microsoft.com/intune/planning-guide-scenarios) puede ayudarle a comenzar e incluye algunas instrucciones en estos escenarios diferentes.

## <a name="step-2-get-your-prerequisites"></a>Paso 2: Obtener los requisitos previos

A continuación, obtenga sus según los requisitos de los requisitos previos y los escenarios que creó en el paso anterior. [Implementar el plan](https://docs.microsoft.com/intune/planning-guide-onboarding) se enumeran todos los requisitos. Estos son los elementos importantes que necesita para Intune con Microsoft 365:

- **Suscripción Intune**: incluido con Microsoft 365 y proporciona acceso a Microsoft Intune en el [portal de Azure](https://portal.azure.com)
- **Suscripción a Office 365**: incluidos con Microsoft 365 y se usa para las aplicaciones de Office, incluido el correo electrónico
- **Premium de Azure Active Directory (AD)**: incluidos con Microsoft 365 y se usa para crear usuarios o grupos de seguridad. Estos grupos reciben directivas Intune que cree, como forzar una longitud de contraseña para desbloquear un dispositivo. Los grupos se crean en [fase 2: identidad](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) se puede usar.

Puede haber algunos requisitos adicionales, dependiendo de las necesidades de su organización. Por ejemplo, si va a administrar dispositivos iOS, necesitará un certificado de inserción de Apple MDM. Si está utilizando Exchange local, a continuación, necesitará el conector de Exchange local. Cuando llegue a esos pasos y se describen los siguientes requisitos adicionales.

## <a name="step-3-set-up-intune"></a>Paso 3: Configurar Intune

Intune usa muchas de las características de Azure AD, incluida su dominio, los usuarios y los grupos. También puede crear nuevos usuarios y grupos nuevos para ajustarse a las necesidades de su empresa. Por ejemplo, puede crear un grupo denominado **dispositivos iOS**o **recursos humanos todos los usuarios**.  Permite aprovechar los [Grupos dinámicos](https://docs.microsoft.com/intune/groups-add) que le permite crear usuarios o grupos de dispositivos basados en reglas simples o avanzadas.

Este paso se centra en la configuración de Intune y prepararse para administrar los dispositivos.

1. **[Confirmar que son compatibles con los dispositivos](https://docs.microsoft.com/intune/supported-devices-browsers)**. Confirme su iOS, Mac OS, se admiten los dispositivos Android, Galaxy y Windows Intune. Si su organización incluye dispositivos que no son compatibles, las directivas no se aplican a esos dispositivos.

2. **[Personalizar el nombre de dominio](https://docs.microsoft.com/intune/custom-domain-name-configure)**. De forma predeterminada, un dominio denominado algo así como **su domain.onmicrosoft.com** se crea automáticamente en Azure AD. **onmicrosoft.com** se pueden personalizar para la organización. Cuando se personaliza, también proporciona a los usuarios un dominio familiarizado cuando se conecta a Intune y el uso de recursos.

3. **[Inicie sesión en Intune](https://docs.microsoft.com/intune/account-sign-up)**. Al iniciar sesión, es posible que se le pida para escribir información acerca de la organización. Intune se incluye con Microsoft 365 y se puede abrir directamente desde el [portal de administración de Office 365](https://portal.office.com/). También puede abrir Intune directamente desde el [portal de Azure](https://portal.azure.com).

4. **[Elija la configuración de administración de dispositivos móviles](https://docs.microsoft.com/intune/mdm-authority-set)**. La primera vez que utilice Intune, debe habilitar la administración de dispositivos. Intune se puede usar como un servicio de nube, una implementación híbrida con Intune y System Center Configuration Manager o mediante la administración de dispositivos móviles para Office 365. Puede elegir que el programa de instalación funciona mejor para su organización.

5. **[Agregar usuarios](https://docs.microsoft.com/intune/users-add)** y **[Agregar grupos](https://docs.microsoft.com/intune/groups-add)**. 

   Manualmente, puede agregar usuarios o conectarse a Azure AD a los usuarios de la sincronización con Intune. También puede asignar roles de administrador a usuarios específicos. Los usuarios son necesarios a menos que los dispositivos están los dispositivos "userless", como dispositivos de quiosco.

   Grupos de Azure AD se usan para simplificar el modo de administrar usuarios en Intune y dispositivos. Uso de grupos, puede hacer muchas tareas diferentes. Por ejemplo, su organización desea requerir una aplicación específica en dispositivos Android. Puede crear un grupo de dispositivos Android e implementar una directiva con esta aplicación para el grupo.

    En Intune, puede agregar usuarios o grupos que se crean en [fase 2: identidad](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Asignación de licencias](https://docs.microsoft.com/intune/licenses-assign)**. Para que los usuarios o dispositivos a inscribirse en Intune, que necesitan una licencia en el dispositivo. Cada usuario o dispositivo userless requiere una licencia de Intune para tener acceso al servicio Intune. Estas licencias se incluyen con Microsoft 365 y se deben asignar en Intune.

## <a name="step-4-enroll-devices"></a>Paso 4: Inscribirse dispositivos

Para administrar dispositivos, los dispositivos deben inscribirse en Intune. Como administrador, podrá configurar las restricciones de inscripción y las directivas para los usuarios y dispositivos. Cada plataforma de dispositivo (iOS, Android, Windows y Mac OS) tiene una gran variedad de opciones. Puede hacer que los usuarios inscribirse a sí mismo. O bien, puede automatizar inscripción por lo que los usuarios inician sesión simplemente el dispositivo.

Inscripción es un paso clave al usar Intune. [Dispositivos de inscripción](https://docs.microsoft.com/intune/device-enrollment) se enumeran los pasos necesarios para los distintos dispositivos.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: iOS e inscripción dispositivo Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Paso 5: Agregar e implementar aplicaciones

Aplicaciones en dispositivos móviles a menudo son que la forma más rápida, los usuarios obtendrán acceso a los recursos corporativos. 

Existen desafíos al uso de las aplicaciones, ya que hay dispositivos diferentes, incluidos los dispositivos de personal y corporativo. Y desea proteger los recursos de su organización y sus datos mientras también asegurándose de que los usuarios son productivos.

Intune puede administrar las aplicaciones, incluyendo agregar aplicaciones, asignarlas a distintos usuarios o grupos y revise otros detalles de la clave. Por ejemplo, puede ver qué aplicaciones producirá un error al instalar, compruebe la versión de una aplicación y mucho más.

Cuando los usuarios reciben un dispositivo móvil, una de las primeras tareas es tener acceso a documentos y correo electrónico organizativa. Mediante Intune, se puede [crear e implementar la configuración de correo electrónico](https://docs.microsoft.com/intune/email-settings-configure) con aplicaciones de correo electrónico que se encuentren instaladas en los dispositivos. 

[Agregar aplicaciones](https://docs.microsoft.com/intune/app-management) muestran los pasos para agregar, implementar, supervisar, configurar y proteger las aplicaciones de dispositivos dentro de su org.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Directivas de cumplimiento de normas de dispositivo](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Paso 6: Activar acceso condicional y cumplimiento de normas

En los pasos anteriores, configurar el entorno y había habilitado Intune. Ahora, estará listo crear algunas directivas de uso de cumplimiento de normas y acceso condicional.

Cumplimiento de normas y acceso condicional son importantes a la administración de dispositivos. **[Las directivas de cumplimiento](https://docs.microsoft.com/intune/device-compliance-get-started)** se crean para ayudar a proteger los recursos de su organización. Cuando se crea una directiva de cumplimiento, que esté definiendo el estándar o "baseline" de lo que debe tener un dispositivo. Por ejemplo, puede elegir un nivel de amenaza aceptable (o inaceptable), bloquear dispositivos jailbroken, requieren una longitud de contraseña y mucho más. Si estos dispositivos no cumplen con las reglas, lo que significa que no son compatibles, puede bloquear el acceso a los recursos.

Esto "bloqueo" presenta **[acceso condicional](https://docs.microsoft.com/intune/conditional-access)**. Si se considera que un dispositivo no compatible, a continuación, puede bloquear el acceso a correo electrónico, SharePoint y mucho más.

Intune en el [portal de Azure](https://portal.azure.com) permite crear estas directivas y aplicarlos a los usuarios y dispositivos. Como procedimiento recomendado, inicie pequeña y usar un enfoque por fases. Por ejemplo, cree una directiva de iOS que bloquea jailbroken dispositivos. Aplicar la directiva de (llamado "asignar" en Intune) a un grupo piloto o de prueba. Después de la prueba inicial, agregue más usuarios al grupo piloto. Uso de un enfoque por fases, puede obtener comentarios desde una amplia variedad de tipos de usuario.

[Introducción a las directivas de cumplimiento de normas de dispositivo](https://docs.microsoft.com/intune/device-compliance-get-started) y [¿Qué es acceso condicional?](https://docs.microsoft.com/intune/conditional-access) le ayudarán a empezar a trabajar.

## <a name="step-7-apply-features-and-settings"></a>Paso 7: Aplicar la configuración y características

Estas características y configuración a menudo se considera el elemento "interesante" de Intune y es muy eficaces. Una vez que haya aplicó correctamente algunas directivas de cumplimiento de normas mediante acceso condicional, estará listo crear **perfiles de dispositivos**.

Intune en el [portal de Azure](https://portal.azure.com) le permite crear diferentes perfiles en función de la plataforma del dispositivo - iOS, Mac OS, Android y Windows. Por ejemplo, se puede:

- Use la protección de extremo en dispositivos de Windows 10 para habilitar diferentes opciones de BitLocker, incluido el cifrado.
- Usar la característica de aplicaciones restringidos en dispositivos iOS para crear una lista de aplicaciones aprobadas que se pueden instalar. O bien, crear una lista de aplicaciones prohibidas.
- Use la configuración de quiosco para elegir qué aplicaciones pueden usarse en dispositivos Android que se ejecuta en modo de pantalla completa.
- Aplicar una conexión Wi-Fi y sus valores, como el tipo de seguridad, en los dispositivos que ejecutan Mac OS.
- Y mucho más

[Qué son los perfiles de dispositivos de Microsoft Intune?](https://docs.microsoft.com/intune/device-profiles) es un buen momento para leer acerca de los perfiles, vea cómo crear un perfil y mucho más.

Recuerde, iniciar pequeña y usar un enfoque por fases. Asigne el perfil a un grupo piloto o de prueba. A continuación, asigne el perfil a más grupos pilotos.

## <a name="step-8-get-to-know-the-other-features"></a>Paso 8: Obtener saber el resto de características

Intune es un servicio potente e incluye muchas características. A continuación presentamos algunas otras tareas que puede realizar mediante Intune:

- Administrar actualizaciones de software y en [dispositivos](https://docs.microsoft.com/intune/windows-update-for-business-configure)de Windows & [PC](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)y dispositivos [iOS](https://docs.microsoft.com/intune/software-updates-ios)
- Activar [Windows Defender avanzada amenaza protección (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) en los dispositivos de Windows 10 y el uso de cumplimiento de normas y acceso condicional para proteger el acceso a recursos corporativos, como Exchange Online o de SharePoint
- Usar [atento](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)y otros socios de amenaza de defensa móvil
- Agregar un [socio entidad de certificación (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) para emitir y renovar certificados
- [Proporcionar instrucciones a los usuarios finales](https://docs.microsoft.com/intune/end-user-educate) en la aplicación de Portal de empresa, introducción de aplicaciones etc.
- Supervisar [aplicaciones](https://docs.microsoft.com/intune/apps-monitor), monitor [cumplimiento de dispositivo](https://docs.microsoft.com/intune/compliance-policy-monitor), [los perfiles de configuración](https://docs.microsoft.com/intune/compliance-policy-monitor)del monitor y telemetría más con los registros de auditoría. También puede conectar con el [Almacén de datos Intune](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) y usar Power BI para las necesidades de informes aún más.


## <a name="identity-and-device-access-recommendations"></a>Recomendaciones de acceso a dispositivos e identidades

Microsoft proporciona un conjunto de recomendaciones para el [acceso de identidad y el dispositivo](microsoft-365-policies-configurations.md) garantizar a una plantilla de seguridad y la productividad. Para el acceso de dispositivo, use las recomendaciones y la configuración en los siguientes artículos junto con los pasos de esta fase:

- [Requisitos previos](identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Aprenda a planeado para expertos de TI de Microsoft e implementan administración EMS y dispositivos con estos recursos:

- [Managing modern mobile productivity with Enterprise Mobility + Security (Administración de la productividad móvil moderna con Enterprise Mobility + Security)](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [Connecting to work on your Windows 10 device with Microsoft Intune (Conexión al trabajo con un dispositivo Windows 10 con Microsoft Intune)](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [Enabling mobile productivity for iOS, OS X, and Android devices at Microsoft (Permitir la productividad móvil para dispositivos iOS, OS X y Android en Microsoft)](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Cómo Contoso hizo Microsoft 365 Enterprise

Vea cómo servicios de nube de Contoso Corporation, una empresa multinacional ficticia pero representativa, [implementado la infraestructura de administración de su dispositivo móvil](contoso-mdm.md) con Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Paso siguiente

[Criterios de salida de infraestructura de administración de dispositivos móviles](mobility-infrastructure-exit-criteria.md)

