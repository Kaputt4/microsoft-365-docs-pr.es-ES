---
title: Administración de dispositivos móviles para trabajadores de primera línea
author: lanachin
ms.author: v-lanachin
ms.reviewer: mabolan
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: microsoft-365-frontline
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información general sobre la administración de dispositivos móviles para los trabajadores de primera línea de su organización.
ms.collection:
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 3e80da42f723bb00da15a054b930a76831f8413c
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785890"
---
# <a name="manage-mobile-devices-for-frontline-workers"></a>Administración de dispositivos móviles para trabajadores de primera línea

## <a name="overview"></a>Información general

En todos los sectores, los trabajadores de primera línea constituyen un gran segmento del personal. Los roles de personal de primera línea incluyen asociados comerciales, trabajadores de fábrica, técnicos de campo y servicio, personal sanitario y muchos más.

Dado que el personal es en gran medida móvil y, a menudo, basado en turnos, la administración de los dispositivos que usan los trabajadores de primera línea es fundamental. Algunas preguntas que se deben tener en cuenta:

- ¿Los trabajadores usan dispositivos propiedad de la empresa o sus propios dispositivos personales?
- ¿Los dispositivos propiedad de la empresa se comparten entre los trabajadores o se asignan a un individuo?
- ¿Los trabajadores llevan los dispositivos a casa o los dejan en el lugar de trabajo?

Es importante establecer una base de referencia segura y compatible para administrar los dispositivos de los empleados, tanto si son dispositivos compartidos como si son dispositivos propios de los trabajadores. En este artículo se proporciona información general sobre escenarios comunes de dispositivos de personal de primera línea y funcionalidades de administración para ayudar a capacitar a los empleados a la vez que protegen los datos de la empresa.

## <a name="my-staff"></a>Mi personal

Con la característica [Mi personal](/azure/active-directory/roles/my-staff-configure) en Azure Active Directory (Azure AD), puede delegar tareas comunes de administración de usuarios a los administradores de primera línea a través del portal de Mi personal. Los administradores de primera línea pueden realizar restablecimientos de contraseña o administrar números de teléfono para los trabajadores de primera línea directamente desde la tienda o la fábrica, sin tener que redirigir las solicitudes al departamento de soporte técnico, operaciones o TI.

Mi personal también permite a los jefes de primera línea registrar los números de teléfono de los miembros del equipo para el inicio de sesión por SMS. Si la [ Autenticación basada en SMS](/azure/active-directory/authentication/howto-authentication-sms-signin) está habilitada en su organización, los trabajadores de primera línea pueden iniciar sesión en Teams y otras aplicaciones usando solo sus números de teléfono y un código de acceso de un solo uso enviado a través de SMS. Esto hace que el inicio de sesión de los trabajadores de primera línea sea sencillo, seguro y rápido.

## <a name="shared-devices"></a>Dispositivos compartidos

Muchos trabajadores de primera línea usan dispositivos móviles compartidos para realizar el trabajo. Los dispositivos compartidos son dispositivos propiedad de la empresa que se comparten entre los empleados entre tareas, turnos o ubicaciones.

Este es un ejemplo de un escenario típico. Una organización tiene un conjunto de dispositivos en bases de carga que se comparten entre todos los empleados. Al principio de un turno, un empleado toma un dispositivo del grupo e inicia sesión en Teams y otras aplicaciones empresariales esenciales para su rol. Al final de su turno, cierran la sesión y devuelven el dispositivo al grupo. Incluso dentro del mismo turno, un trabajador puede devolver un dispositivo cuando finaliza una tarea o sale a comer y, a continuación, recoger uno diferente cuando vuelva a registrarse.

Los dispositivos compartidos presentan desafíos de seguridad únicos. Por ejemplo, los empleados pueden tener acceso a los datos de la empresa o del cliente que no deberían estar disponibles para otros usuarios en el mismo dispositivo.

En esta sección se proporciona información general sobre las funcionalidades disponibles para administrar dispositivos compartidos para los trabajadores de primera línea.

### <a name="shared-device-mode"></a>Modo de dispositivo compartido

[Modo de dispositivo compartido](/azure/active-directory/develop/msal-shared-devices) es una característica de Azure AD que permite configurar los dispositivos que compartirán los empleados. Esta característica habilita el inicio de sesión único (SSO) y el cierre de sesión en todo el dispositivo para Microsoft Teams y todas las demás aplicaciones que admiten el modo de dispositivo compartido. Puede integrar esta funcionalidad en las aplicaciones de línea de negocio (LOB) mediante la Biblioteca de autenticación de Microsoft (MSAL).

Aquí se muestra cómo funciona el modo de dispositivo compartido, usando Teams como ejemplo. Cuando un empleado inicia sesión en Teams al inicio de su turno, inicia sesión automáticamente en todas las demás aplicaciones que admiten el modo de dispositivo compartido en el dispositivo. Al final de su turno, cuando cierran sesión en Teams, se cierra la sesión globalmente de todas las demás aplicaciones que admiten el modo de dispositivo compartido. Después del cierre de sesión, ya no se puede acceder a los datos del empleado y a los datos de la empresa en Teams (incluidas las aplicaciones hospedadas en él) y en todas las demás aplicaciones que admiten el modo de dispositivo compartido. El dispositivo está listo para el siguiente empleado y se puede entregar de forma segura.

Usa una solución de administración de dispositivos móviles (MDM) como Microsoft Intune en Microsoft Endpoint Manager para preparar un dispositivo que se va a compartir instalando la [aplicación Microsoft Authenticator](https://support.microsoft.com/account-billing/how-to-use-the-microsoft-authenticator-app-9783c865-0308-42fb-a519-8cf666fe0acc) y activando el modo compartido. Teams y todas las demás aplicaciones que admiten el modo de dispositivo compartido usan la configuración del modo compartido para administrar usuarios en el dispositivo. La solución MDM que use también debe realizar una limpieza del dispositivo cuando se produzca el cierre de sesión.

El modo de dispositivo compartido se admite actualmente en dispositivos Android. Estos son algunos recursos que le ayudarán a empezar.

#### <a name="enroll-android-devices-into-shared-device-mode"></a>Inscribir dispositivos Android en modo de dispositivo compartido

Para administrar e inscribir dispositivos Android en modo de dispositivo compartido mediante Intune, los dispositivos deben ejecutar la versión 8.0 o posterior del sistema operativo Android y tener conectividad de Google Mobile Services (GMS). Para más información, vea:

- [Configuración de la inscripción de Intune para dispositivos dedicados de Android Enterprise](/mem/intune/enrollment/android-kiosk-enroll)
- [Inscribir dispositivos dedicados de Android Enterprise en modo de dispositivo compartido de Azure AD](https://techcommunity.microsoft.com/t5/intune-customer-success/enroll-android-enterprise-dedicated-devices-into-azure-ad-shared/ba-p/1820093)

También puede optar por implementar la aplicación Microsoft Managed Home Screen para adaptar la experiencia a los usuarios en sus dispositivos Android dedicados inscritos en Intune. Managed Home Screen actúa como un iniciador para que otras aplicaciones aprobadas se ejecuten encima de él, y le permite personalizar dispositivos y restringir a qué empleados pueden acceder. Por ejemplo, puede definir cómo aparecen las aplicaciones en la pantalla principal, agregar el logotipo de la empresa, establecer papel tapiz personalizado y permitir que los empleados establezcan un PIN de sesión. Incluso puede configurar el cierre de sesión para que se produzca automáticamente después de un período de inactividad especificado.  Para más información, vea:

- [Configurar la aplicación Microsoft Managed Home Screen para Android Enterprise](/mem/intune/apps/app-configuration-managed-home-screen-app)
- [Cómo configurar Microsoft Managed Home Screen en dispositivos dedicados en el modo de pantalla completa con varias aplicaciones](https://techcommunity.microsoft.com/t5/intune-customer-success/how-to-setup-microsoft-managed-home-screen-on-dedicated-devices/ba-p/1388060)

#### <a name="for-developers-creating-apps-for-shared-device-mode"></a>Para desarrolladores que crean aplicaciones para el modo de dispositivo compartido

Si eres un desarrollador, consulta los siguientes recursos para obtener más información sobre cómo integrar la aplicación con el modo de dispositivo compartido:

- [Modo de dispositivo compartido para dispositivos Android](/azure/active-directory/develop/msal-android-shared-devices)
- [Modo de dispositivo compartido para dispositivos iOS](/azure/active-directory/develop/msal-ios-shared-devices)

## <a name="personal-devices-byod"></a>Dispositivos personales (BYOD)

Algunas organizaciones usan un modelo Bring Your Own Device (BYOD) en el que los trabajadores de primera línea usan sus propios dispositivos móviles para acceder a Teams y otras aplicaciones empresariales. Esta es una introducción a algunas formas de administrar el acceso y el cumplimiento en dispositivos personales.

### <a name="enroll-android-and-ios-personal-devices"></a>Inscripción de dispositivos Android e iOS personales

Además de los dispositivos propiedad de la empresa, puede [inscribir](/mem/intune/enrollment/device-enrollment) los dispositivos de propiedad personal de los usuarios en la administración en Intune. Para la inscripción BYOD, agregue usuarios de dispositivos en el Centro de administración de Microsoft Endpoint Manager, configure su experiencia de inscripción y configure directivas de Intune. Los usuarios completan la inscripción ellos mismos en la aplicación Portal de empresa de Intune que está instalada en su dispositivo.

En algunos casos, los usuarios pueden sentirse reacios a inscribir sus dispositivos personales en la administración. Si la inscripción de dispositivos no es una opción, puede elegir un enfoque de administración de aplicaciones móviles (MAM) y usar [ directivas de protección de aplicaciones](/mem/intune/apps/app-protection-policies) para administrar aplicaciones que contienen datos corporativos. Por ejemplo, puede aplicar directivas de protección de aplicaciones a las aplicaciones móviles de Teams y Office para evitar que los datos de la empresa se copien en las aplicaciones personales del dispositivo.

Para obtener más información, consulte ["Dispositivos personales frente a dispositivos propiedad de la organización" en la guía de planeación de Intune](/mem/intune/fundamentals/intune-planning-guide#personal-devices-vs-organization-owned-devices) y la [Guía de implementación: Inscribir dispositivos en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment).

## <a name="related-articles"></a>Artículos relacionados

- [Administración de trabajadores de primera línea](/azure/active-directory/fundamentals/frontline-worker-management)
