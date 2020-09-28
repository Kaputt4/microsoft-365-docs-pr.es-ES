---
title: Experiencia de primera ejecución con AutoPilot y la página de estado de inscripción
description: Cómo implementar la experiencia de ESP, la configuración usada y las excepciones
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d4083e48033787ca46ad2374ea461b4a77d21e0d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296009"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Experiencia de primera ejecución con AutoPilot y la página de estado de inscripción

Microsoft Managed Desktop usa tanto [Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) como la página de [Estado de inscripción (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) de Microsoft Intune para proporcionar la mejor experiencia de primera ejecución posible a los usuarios.

La página de estado de inscripción se encuentra actualmente en versión preliminar pública.

## <a name="initial-deployment"></a>Implementación inicial

Para proporcionar la experiencia de ESP, debe registrar los dispositivos en el servicio de escritorio administrado de Microsoft. Para obtener más información sobre el registro, vea [registrar nuevos dispositivos usted](../get-started/register-devices-self.md) o [pasos para que los partners registren dispositivos](../get-started/register-devices-partner.md).

Una vez que los dispositivos estén registrados con el servicio, puede habilitar ESP para los dispositivos de escritorio administrados por Microsoft mediante el archivado de un vale de soporte técnico a través del [portal de administración](https://portal.azure.com/). La configuración ESP se implementará inicialmente en el grupo de prueba cuando se archiva el vale. Se implementa en los otros grupos de implementación subsiguientes (primero, rápido y amplio) cada 24 horas. Para pausar la implementación, archivo otro que pregunte a las operaciones que hay que conservar.

## <a name="autopilot-profile-settings"></a>Configuración del perfil de AutoPilot

Microsoft Managed Desktop usa esta configuración en el perfil de AutoPilot usado para los dispositivos de los usuarios:


|Configuración  |Valor  |
|---------|---------|
|Modo de implementación |  Controlada por el usuario       |
|Unirse a Azure AD como     |  Unido a Azure AD       |
|Idioma (región)     | Predeterminada del sistema operativo        |
|Configurar automáticamente el teclado     | No        |
|Términos de licencia del software de Microsoft     |  Ocultar       |
|Configuración de privacidad     | Ocultar        |
|Ocultar opciones de cuenta de cambio     | Show        |
|Tipo de cuenta de usuario     |  Estándar       |
|Permitir OOBE de la guantera blanca     |  Sí       |
|Aplicar plantilla de nombre de dispositivo     | Sí        |
|Escriba un nombre     | MMD-% RAND: 7%        |



## <a name="enrollment-status-page-settings"></a>Configuración de la página de estado de inscripción

Microsoft Managed Desktop usa esta configuración para la experiencia de la página de estado de inscripción:


|Configuración  |Valor  |
|---------|---------|
|Mostrar el progreso de configuración de la aplicación y el perfil     | Sí        |
|Mostrar un error cuando la instalación tarda más tiempo que el número de minutos especificado     |  60       |
|Mostrar mensaje personalizado cuando se produzca un error de límite de tiempo     |  Sí       |
|Mensaje de error     | Sí, se está tardando un poco más en configurar el dispositivo de lo esperado. Haga clic a continuación para empezar y vamos a finalizar la configuración en segundo plano.        |
|Permitir a los usuarios recopilar registros sobre errores de instalación     |  Sí       |
|Mostrar solo la página en los dispositivos aprovisionados por la configuración rápida (OOBE)     | Sí        |
|Bloquear el uso del dispositivo hasta que se instalen todas las aplicaciones y perfiles     |  Sí       |
|Permitir que los usuarios restablezcan dispositivos si se produce un error de instalación     |  Sí       |
|Permitir que los usuarios usen el dispositivo si se produce un error de instalación     |  Sí       |
|Bloquear el uso del dispositivo hasta que se instalen las aplicaciones necesarias si están asignadas al usuario o dispositivo     |  Corrección de tiempo de trabajo moderna       |



La experiencia de la página de estado de inscripción se produce en tres fases. Para obtener más información, consulte información de seguimiento de la [Página estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).

La experiencia continúa de la siguiente manera:

1. La experiencia de AutoPilot se inicia y el usuario escribe sus credenciales.
2. El dispositivo abre la página de estado de inscripción y avanza a través de la preparación de dispositivos y las fases de configuración del dispositivo. El tercer paso (configuración de la cuenta) se *omite actualmente* en la configuración de escritorio administrada de Microsoft porque el usuario ESP está deshabilitado. El dispositivo se reinicia.
3. Después de reiniciar, el dispositivo abre la página de inicio de sesión de Windows con **otro usuario**.
4. Los usuarios vuelven a escribir sus credenciales y se abre el escritorio.

> [!NOTE]
> Las aplicaciones Win32 solo se implementan durante ESP si la versión de Windows 10 es la 1903 o posterior.

![Página de inicio de la configuración de AutoPilot que muestra las fases "preparación de dispositivos" y "configuración de dispositivo".](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>Aprovisionamiento de la guantera blanca

Microsoft Managed Desktop no es compatible actualmente con la característica "guante blanca" de Windows AutoPilot.

## <a name="exceptions"></a>Exceptions

Si la configuración que usa el escritorio administrado por Microsoft no se ajusta exactamente a sus necesidades, puede archivar una solicitud para una excepción. Para ello, vea los detalles en [solicitar una excepción](../service-description/customizing.md#request-an-exception). A continuación se muestran algunos ejemplos de los tipos de excepciones que puede necesitar:

### <a name="autopilot-exception"></a>Excepción de piloto automático

Es posible que desee solicitar una plantilla de nombre de dispositivo diferente. Sin embargo, no puede cambiar el modo de implementación, unirse a Azure como, configuración de privacidad o tipo de cuenta de usuario.

### <a name="enrollment-status-page-exception"></a>Excepción de página de estado de inscripción

- Un número de minutos mayor para la configuración "Mostrar un error cuando la instalación tarde más que el número de minutos especificado".
- Mensaje de error que se muestra
- Agregar o quitar aplicaciones en el parámetro "bloquear el uso del dispositivo hasta que se instalen estas aplicaciones si están asignadas al usuario/dispositivo".

## <a name="required-applications"></a>Aplicaciones necesarias

- Debe dirigirse a las aplicaciones de la prueba moderna de los *grupos de dispositivos* del área de trabajo, primera, rápida y amplia. Las aplicaciones deben instalarse en el contexto "sistema". Asegúrese de completar las pruebas con ESP en el grupo de prueba antes de asignarlos a todos los grupos.
- Ninguna aplicación debe requerir el reinicio del dispositivo. Se recomienda que las aplicaciones se establezcan en "no hacer nada" al compilar el paquete de la aplicación si necesitarán un reinicio.
- Limite las aplicaciones necesarias solo a las aplicaciones principales que necesita un usuario inmediatamente cuando inician sesión en el dispositivo.
- Mantenga el tamaño total de todas las aplicaciones de forma colectiva en 1 GB para evitar Tiempos de espera durante la fase de instalación de la aplicación.
- Idealmente, las aplicaciones no deben tener ninguna dependencia. Si tiene aplicaciones que *deben* tener dependencias, asegúrese de configurarlas, probarlas y validarlas como parte de la evaluación de ESP.
- No se puede incluir en la versión preliminar pública de ESP ninguna aplicación que requiera el contexto de "usuario" (por ejemplo, Teams).