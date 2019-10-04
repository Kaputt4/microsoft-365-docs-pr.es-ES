---
title: 'Fase 5: administración de dispositivos móviles'
description: Microsoft 365 Enterprise incluye la administración de dispositivos móviles con Microsoft Intune. Revise los requisitos y requisitos previos, configure Intune con el recurso de Azure Active Directory, inscriba dispositivos iOS, macOS, Android y Windows, implemente aplicaciones, cree un perfil de configuración, use una directiva de cumplimiento y habilite el acceso condicional para dispositivos móviles Administración de dispositivos con Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, administración de dispositivos móviles, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: dd73f32ff3c830104777aeefb1271178031a5b0d
ms.sourcegitcommit: d4aa94716b33e6c270ae7adfbdc4c19cf4a0087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "37386147"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Fase 5: administración de dispositivos móviles para Microsoft 365 Enterprise

![Fase 5: administración de dispositivos móviles](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Esta característica se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

Microsoft 365 Enterprise incluye características que ayudan a administrar los dispositivos y sus aplicaciones dentro de su organización. Con Microsoft Intune, puede administrar dispositivos iOS, Android, macOS y Windows para proteger el acceso a los recursos de la organización, incluidos los datos. 

En esta fase, los dispositivos se inscriben en Intune y se crean y se aplican las directivas para ayudar a proteger y proteger los datos. La biblioteca completa de la documentación de Intune está [disponible en línea](https://docs.microsoft.com/intune). También se recomienda revisar la [Guía de planeación, diseño e implementación de Intune](https://docs.microsoft.com/intune/planning-guide) antes de empezar.

## <a name="step-1-plan-for-your-scenario"></a>Paso 1: planear su escenario

Una de las principales razones para administrar dispositivos móviles es proteger y proteger los recursos de la organización. [Formas comunes de usar Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) enumera algunos ejemplos del mundo real, incluidos la protección del correo electrónico y los datos de Office 365.

Intune le ofrece opciones para administrar el acceso a su organización mediante el uso de la administración de dispositivos móviles (MDM) o la administración de aplicaciones móviles (MAM). MDM es cuando los usuarios "inscriben" sus dispositivos en Intune. Una vez inscritos, son dispositivos administrados y pueden recibir directivas, reglas y opciones de configuración usadas por la organización. Por ejemplo, puede instalar aplicaciones específicas, crear una directiva de contraseñas, instalar una conexión VPN, etc.

Es posible que los usuarios con sus propios dispositivos personales no deseen inscribir sus dispositivos o ser administrados por Intune y sus directivas. Sin embargo, debe proteger los recursos y los datos de la organización. En este escenario, puede proteger sus aplicaciones con MAM. Por ejemplo, puede usar una directiva de MAM que requiera que un usuario escriba un PIN cuando obtenga acceso a SharePoint en el dispositivo.

También determinará cómo va a administrar los dispositivos personales o de propiedad de la organización. Es posible que quiera tratar los dispositivos de forma diferente, en función de su uso. Por ejemplo, puede que desee tener distintos planes para los usuarios de recursos humanos (HR) o usuarios en ventas. [Identificar los escenarios de uso de administración de dispositivos móviles](https://docs.microsoft.com/intune/planning-guide-scenarios) puede ayudarle a empezar e incluye alguna orientación en estos distintos escenarios.

## <a name="step-2-get-your-prerequisites"></a>Paso 2: obtener los requisitos previos

A continuación, obtenga los requisitos previos en función de sus requisitos y escenarios creados en el paso anterior. [Implementar el plan](https://docs.microsoft.com/intune/planning-guide-onboarding) enumera todos los requisitos. Estos son los elementos más importantes que necesita para Intune con Microsoft 365:

- **Suscripción de Intune**: incluida con Microsoft 365 y le da acceso a Microsoft Intune en [Azure portal](https://portal.azure.com)
- **Suscripción de office 365**: se incluye con Microsoft 365 y se usa para las aplicaciones de Office, incluido el correo electrónico.
- **Azure Active Directory (Azure ad) Premium**: incluido con Microsoft 365, y se usa para crear grupos de seguridad o usuarios. Estos grupos reciben directivas de Intune que crea, como forzar una longitud de contraseña para desbloquear un dispositivo. Los grupos que se crean en la [fase 2:](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) se puede usar Identity.

Puede haber algunos requisitos adicionales, según las necesidades de su organización. Por ejemplo, si va a administrar dispositivos iOS, necesitará un certificado de inserción de MDM de Apple. Si está usando el Exchange local, necesitará el conector de Exchange local. Estos requisitos adicionales se describen a continuación cuando llegue a estos pasos.

## <a name="step-3-set-up-intune"></a>Paso 3: configurar Intune

Intune usa muchas características de Azure AD, incluido el dominio, los usuarios y los grupos. También puede crear nuevos usuarios y grupos nuevos que se ajusten a las necesidades de su empresa. Por ejemplo, puede crear un grupo denominado **dispositivos iOS**o **todos los usuarios de recursos humanos**.  Aproveche los [grupos dinámicos](https://docs.microsoft.com/intune/groups-add) que le permiten crear grupos de usuarios o dispositivos basados en reglas sencillas o avanzadas.

Este paso se centra en la configuración de Intune y en su preparación para que administre sus dispositivos.

1. **[Confirmar que los dispositivos son compatibles](https://docs.microsoft.com/intune/supported-devices-browsers)**. Compruebe que los dispositivos iOS, macOS, Android, Galaxy y Windows sean compatibles con Intune. Si su organización incluye dispositivos que no son compatibles, las directivas no se aplican a esos dispositivos.

2. **[Personalizar el nombre de dominio](https://docs.microsoft.com/intune/custom-domain-name-configure)**. De forma predeterminada, se crea automáticamente un dominio con un nombre similar a **your-domain.onmicrosoft.com** en Azure ad. **onmicrosoft.com** se puede personalizar para su organización. Cuando Personaliza, también proporciona a los usuarios un dominio conocido cuando se conecta a Intune y a usar recursos.

3. **[Inicie sesión en Intune](https://docs.microsoft.com/intune/account-sign-up)**. Al iniciar sesión, es posible que se le pida que escriba la información sobre su organización. Intune se incluye con Microsoft 365 y se puede abrir directamente desde el [centro de administración de microsoft 365](https://admin.microsoft.com). También puede abrir Intune directamente desde [Azure portal](https://portal.azure.com).

4. **[Elija la configuración de administración de dispositivos móviles](https://docs.microsoft.com/intune/mdm-authority-set)**. La primera vez que use Intune, debe habilitar la administración de dispositivos. Intune se puede usar como un servicio solo de nube, un híbrido con Intune y el administrador de configuración de System Center, o mediante la administración de dispositivos móviles para Office 365. Puede elegir el programa de instalación que mejor se adapte a su organización.

5. **[Agregar usuarios](https://docs.microsoft.com/intune/users-add)** y **[agregar grupos](https://docs.microsoft.com/intune/groups-add)**. 

   Puede Agregar usuarios de forma manual o usar la identidad híbrida y Azure AD Connect para sincronizar sus cuentas de usuario locales con Intune. También puede conceder roles de administrador a usuarios específicos. Los usuarios son necesarios a menos que los dispositivos sean dispositivos "de usuario", como los dispositivos de quiosco.

   Los grupos de Azure AD se usan para simplificar la administración de dispositivos y usuarios en Intune. Mediante el uso de grupos, puede realizar muchas tareas diferentes. Por ejemplo, su organización desea requerir una aplicación específica en dispositivos Android. Puede crear un grupo de dispositivos Android e implementar una directiva con esta aplicación en el grupo.

    En Intune, puede Agregar usuarios o grupos que cree en la [fase 2: identidad](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Asignar licencias](https://docs.microsoft.com/intune/licenses-assign)**. Para que los usuarios o dispositivos se inscriban en Intune, necesitan una licencia de Microsoft 365 con el servicio Intune habilitado para obtener acceso al servicio Intune. Asigna licencias de 365 de Microsoft, que tienen el servicio de Microsoft Intune habilitado de forma predeterminada en el centro de administración de Microsoft 365 o con PowerShell.

## <a name="step-4-enroll-devices"></a>Paso 4: inscribir dispositivos

Para administrar dispositivos, los dispositivos deben estar inscritos en Intune. Como administrador, configurará directivas y restricciones de inscripción para los usuarios y los dispositivos. Cada plataforma de dispositivos (iOS, Android, macOS y Windows) tiene una variedad de opciones. Puede hacer que los usuarios se inscriban a sí mismos. O bien, puede automatizar la inscripción para que los usuarios solo inicien sesión en el dispositivo.

La inscripción es un paso clave al usar Intune. [Inscribir dispositivos](https://docs.microsoft.com/intune/device-enrollment) muestra los pasos para los distintos dispositivos.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía del entorno de pruebas: inscripción de dispositivos iOS y Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Paso 5: agregar e implementar aplicaciones

Las aplicaciones de dispositivos móviles suelen ser la forma más rápida de que los usuarios obtengan acceso a los recursos corporativos. 

Hay desafíos al usar aplicaciones, ya que hay diferentes dispositivos, incluidos dispositivos personales y dispositivos corporativos. Además, desea proteger los recursos de la organización y sus datos al tiempo que se asegura de que los usuarios sean productivos.

Intune puede administrar aplicaciones, incluidas agregar aplicaciones, asignarlas a diferentes usuarios o grupos y revisar otros detalles clave. Por ejemplo, puede ver qué aplicaciones no se pueden instalar, comprobar la versión de una aplicación y mucho más.

Cuando los usuarios obtienen un dispositivo móvil, una de las primeras tareas es obtener acceso a los documentos y el correo electrónico de la organización. Con Intune, puede [crear e implementar la configuración del correo electrónico](https://docs.microsoft.com/intune/email-settings-configure) con aplicaciones de correo electrónico que están preinstaladas en los dispositivos. 

El artículo [Add apps](https://docs.microsoft.com/intune/apps/apps-add) enumera los pasos para agregar, implementar, supervisar, configurar y proteger aplicaciones en dispositivos de la organización.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía del entorno de pruebas: directivas de cumplimiento de dispositivos](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Paso 6: activar el cumplimiento y el acceso condicional

En los pasos anteriores, se configura el entorno y se habilita Intune. Ahora está listo para crear directivas mediante el cumplimiento normativo y el acceso condicional.

El cumplimiento y el acceso condicional son importantes para la administración de dispositivos. [Las directivas de cumplimiento](https://docs.microsoft.com/intune/device-compliance-get-started) se crean para ayudar a proteger los recursos de la organización. Al crear una directiva de cumplimiento, está definiendo el estándar o la "línea de base" de lo que debe tener un dispositivo. Por ejemplo, puede elegir un nivel de amenaza aceptable (o inaceptable), bloquear los dispositivos liberados, requerir una longitud de contraseña y mucho más. Si estos dispositivos no cumplen sus reglas, lo que significa que no son compatibles, puede bloquear el acceso a los recursos.

Este "bloqueo" presenta el [acceso condicional](https://docs.microsoft.com/intune/conditional-access). Si un dispositivo se considera no compatible, puede bloquear el acceso al correo electrónico, SharePoint y mucho más.

Intune en el [portal de Azure](https://portal.azure.com) le permite crear estas directivas y aplicarlas a sus usuarios y dispositivos. Como práctica recomendada, comience con una pequeña y use un enfoque por fases. Por ejemplo, cree una directiva de iOS que bloquee los dispositivos liberados. Aplicar (denominado "asignar" en Intune) la Directiva a un grupo piloto o de prueba. Después de las pruebas iniciales, agregue más usuarios al grupo piloto. Con un enfoque por fases, puede obtener comentarios de una amplia gama de tipos de usuarios.

Consulte Introducción a [las directivas de cumplimiento de dispositivos](https://docs.microsoft.com/intune/device-compliance-get-started) y [más información sobre el acceso condicional y Intune?](https://docs.microsoft.com/intune/conditional-access) para ayudarle a empezar.

## <a name="step-7-apply-features-and-settings"></a>Paso 7: aplicar características y configuración

Estas características y configuraciones a menudo se consideran la parte "interesante" de Intune y son muy eficaces. Una vez que haya aplicado correctamente algunas directivas de cumplimiento mediante el acceso condicional, estará listo para crear **perfiles de dispositivo**.

Intune en el [portal de Azure](https://portal.azure.com) le permite crear perfiles diferentes en función de la plataforma de dispositivo: iOS, MacOS, Android y Windows. Por ejemplo, puede:

- Use Endpoint Protection en dispositivos con Windows 10 para habilitar diferentes opciones de BitLocker, incluido el cifrado.
- Use la característica de aplicaciones restringidas en dispositivos iOS para crear una lista de aplicaciones aprobadas que se pueden instalar. O bien, cree una lista de aplicaciones prohibidas.
- Use la configuración de quiosco para elegir las aplicaciones que se pueden usar en dispositivos Android que se ejecutan en el modo de pantalla completa.
- Aplique una conexión Wi-Fi y su configuración, incluido el tipo de seguridad, en dispositivos que ejecuten macOS.

[Aplicar características y configuración en los dispositivos con perfiles de dispositivo](https://docs.microsoft.com/intune/device-profiles) es un buen punto de partida para leer los perfiles, ver cómo crear un perfil y mucho más.

Recuerde, comience con poco y use un enfoque por fases. Asignar el perfil a un grupo piloto o de prueba. A continuación, asigne el perfil a más grupos piloto.

## <a name="step-8-get-to-know-the-other-features"></a>Paso 8: Conozca las otras características

Intune es un eficaz servicio e incluye muchas características. Estas son algunas de las tareas que puede realizar con Intune:

- Administrar software y actualizaciones en[equipos](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)con [dispositivos](https://docs.microsoft.com/intune/windows-update-for-business-configure) & de Windows y dispositivos [iOS](https://docs.microsoft.com/intune/software-updates-ios)
- Activar la [protección contra amenazas avanzada (ATP) de Microsoft defender](https://docs.microsoft.com/intune/advanced-threat-protection) en los dispositivos con Windows 10 y usar el cumplimiento y el acceso condicional para proteger el acceso a los recursos corporativos, como SharePoint o Exchange Online.
- Uso de [guardia](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)y otros Partners de amenazas para la defensa móvil
- Adición de una [entidad de certificación (CA) de asociados](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) para emitir y renovar certificados
- [Proporcionar instrucciones a los usuarios finales](https://docs.microsoft.com/intune/end-user-educate) de la aplicación portal de empresa, obtener aplicaciones y mucho más
- Supervise los [perfiles de configuración y cumplimiento de dispositivos](https://docs.microsoft.com/intune/compliance-policy-monitor)y [aplicaciones](https://docs.microsoft.com/intune/apps-monitor) , y más telemetría usando los registros de auditoría. También puede conectarse al almacén de [datos de Intune](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) y usar Power BI para más necesidades de informes.


## <a name="identity-and-device-access-recommendations"></a>Recomendaciones de acceso a dispositivos e identidades

Microsoft proporciona un conjunto de recomendaciones para el [acceso a identidades y dispositivos](microsoft-365-policies-configurations.md) para asegurar la seguridad y la productividad de los empleados. Para el acceso a los dispositivos, use las recomendaciones y la configuración de los siguientes artículos junto con los pasos de esta fase:

- [Requisitos previos](identity-access-prerequisites.md)
- [Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Obtenga información sobre cómo los expertos de TI de Microsoft [administran dispositivos con EMS](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR8).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Cómo Contoso hizo Microsoft 365 Enterprise

Vea cómo contoso Corporation, una empresa multinacional ficticia pero representativa, [implementó la infraestructura de administración de dispositivos móviles con los](contoso-mdm.md) servicios en la nube de Microsoft 365.

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Siguiente paso

[Criterios de salida de la infraestructura de administración de dispositivos móviles](mobility-infrastructure-exit-criteria.md)

