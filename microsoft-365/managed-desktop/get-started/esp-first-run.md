---
title: Experiencia de primera ejecución con piloto automático y la página de estado de inscripción
description: 'Cómo implementar la experiencia de ESP, la configuración usada y los cambios de configuración'
keywords: 'Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación'
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
---

# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Experiencia de primera ejecución con piloto automático y la página de estado de inscripción

Microsoft Managed Desktop usa [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) y la página de estado de inscripción [(ESP)](/windows/deployment/windows-autopilot/enrollment-status) de Microsoft Intune para proporcionar la mejor experiencia de primera ejecución posible a los usuarios.

## <a name="initial-deployment"></a>Implementación inicial

Para proporcionar la experiencia ESP, debe registrar dispositivos en el servicio de Escritorio administrado de Microsoft. Para obtener más información sobre el registro, consulta [Registrar nuevos dispositivos](../get-started/register-devices-self.md) tú mismo o [Pasos para que los partners registren dispositivos](../get-started/register-devices-partner.md).
Página de estado de inscripción y Piloto automático para la implementación aprovisionada previamente están habilitadas de forma predeterminada en Microsoft Managed Desktop.

## <a name="autopilot-profile-settings"></a>Configuración del perfil de Autopilot

Microsoft Managed Desktop usa esta configuración en el perfil de Autopilot que se usa para los dispositivos de los usuarios:

****

| Configuración | Valor |
| ----- | ----- |
| Modo de implementación | Controlado por el usuario |
| Unirse a Azure AD como | Unidos a Azure AD |
| Idioma (región) | Selección de usuario |
| Configurar automáticamente el teclado | No |
| Términos de licencia de software de Microsoft | Ocultar |
| Configuración de privacidad | Ocultar |
| Ocultar opciones de cuenta de cambio | Show |
| Tipo de cuenta de usuario| Estándar |
| Permitir la experiencia de desasociación de los guantes blancos (OOBE) | Sí |
| Aplicar plantilla de nombre de dispositivo | Sí |
| Escriba un nombre | `MMD-%RAND:11%` |

## <a name="enrollment-status-page-settings"></a>Configuración de la página de estado de inscripción

Microsoft Managed Desktop usa esta configuración para la experiencia de la página de estado de inscripción:

****

| Configuración | Valor |
| ----- | ----- |
| Mostrar el progreso de la configuración de la aplicación y del perfil | Sí |
| Mostrar un error cuando la instalación tarda más de un número determinado de minutos | 60 |
| Mostrar un mensaje personalizado cuando se produce un error de límite de tiempo | No |
| Permitir a los usuarios recopilar registros sobre errores de instalación| Sí |
| Mostrar la página sólo a los dispositivos aprovisionados por la experiencia lista para usar (OOBE) | Sí |
| Bloquear el uso del dispositivo hasta que todos los perfiles y aplicaciones estén instalados | Sí |
| Permitir a los usuarios restablecer el dispositivo si se produce un error de instalación | Sí |
| Permitir a los usuarios utilizar el dispositivo si se produce un error de instalación | Sí |
| Bloquear el uso del dispositivo hasta que se instalen estas aplicaciones necesarias si están asignadas al usuario o dispositivo.|Lugar de trabajo moderno: corrección de tiempo | Modern Workplace: biblioteca de cliente |

La experiencia de la página de estado de inscripción se produce en tres fases. Para obtener más información, consulte [Enrollment Status Page tracking information](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).

La experiencia continúa de la siguiente manera:

1. La experiencia de Autopilot se inicia y el usuario escribe sus credenciales.
2. El dispositivo abre la página Estado de inscripción y continúa con las fases preparación del dispositivo y configuración del dispositivo. El tercer paso (configuración de cuenta *) se omite* actualmente en la configuración de Escritorio administrado de Microsoft porque el ESP de usuario está deshabilitado. El dispositivo se reinicia.
3. Después de reiniciar, el dispositivo abre la Windows inicio de sesión con **Otro usuario**.
4. Los usuarios escriben sus credenciales de nuevo y se abre el escritorio.

> [!NOTE]
> Las aplicaciones de Win32 solo se implementan durante ESP si Windows 10 versión es 1903 o posterior.

![Página de inicio de la configuración de Autopilot que muestra las fases de "preparación del dispositivo" y "configuración del dispositivo".](../../media/mmd-autopilot-screenshot.png)

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>Requisitos previos adicionales para Autopilot para la implementación aprovisionada previamente

- El dispositivo debe tener una conexión de red cableada.
- Si tiene dispositivos registrados con el portal de Escritorio administrado de Microsoft antes de agosto de 2020, des registrar y volver a registrar los dispositivos.
- Los dispositivos deben tener una imagen de fábrica que incluya la actualización acumulativa de noviembre de 2020 [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) o [20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) instalada, o deben volver a crearse imágenes con la imagen de Escritorio administrado de Microsoft más reciente.
- Los dispositivos físicos deben admitir TPM 2.0 y la atestación del dispositivo. Las máquinas virtuales no son compatibles. El proceso de aprovisionamiento previo usa Windows autoaprovisionamiento de Autopilot, por lo que se requiere TPM 2.0. El proceso de atestación de TPM también requiere acceso a un conjunto de direcciones URL HTTPS que son únicas para cada proveedor de TPM. Para obtener más información, vea la entrada para Autopilot self-deploying mode and Autopilot pre-provisioned deployment in [Windows Autopilot networking requirements](/mem/autopilot/networking-requirements#tpm).

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>Secuencia de eventos en Autopilot para la implementación aprovisionada previamente

1. El administrador de TI vuelve a crear imágenes o restablece el dispositivo si es necesario.
2. El administrador de TI inicia el dispositivo, llega a la experiencia de salida y presiona la tecla Windows cinco veces.
3. El administrador de TI selecciona Windows aprovisionamiento de Autopilot y, a continuación, selecciona **Continuar**. En la Windows configuración de Autopilot, se mostrará información sobre el dispositivo.
4. El administrador de TI selecciona **Aprovisionar** para iniciar el proceso de aprovisionamiento.
5. El dispositivo inicia ESP y pasa por las fases de preparación y configuración del dispositivo. Durante la fase de configuración del dispositivo, verás la instalación de la **aplicación x de x** mostrada (según la configuración exacta del perfil ESP).
6. El paso de configuración de la cuenta se omite actualmente en la configuración de Escritorio administrado de Microsoft, ya que deshabilitamos ESP de usuario.
7. El dispositivo se reinicia.

Una vez reiniciado, el dispositivo mostrará la pantalla de estado verde, con un **botón Volver** a izar.

> [!IMPORTANT]
> Problemas conocidos:
>
> - ESP no se vuelve a ejecutar después del Autopilot para la función de reseal de implementación aprovisionada previamente.
> - Autopilot no cambia el nombre del dispositivo para la implementación aprovisionada previamente. Solo se cambiará el nombre del dispositivo después de pasar por el flujo de usuario de ESP.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Cambiar a Configuración de piloto automático y página de estado de inscripción

Si la configuración que usa Microsoft Managed Desktop no coincide exactamente con sus necesidades, puede presentar un vale de soporte técnico a través del [Portal de administración](https://portal.azure.com/). Estos son algunos ejemplos de los tipos de configuración que puede necesitar:

### <a name="autopilot-settings-change"></a>Cambiar la configuración de Autopilot

Es posible que quieras solicitar una plantilla de nombre de dispositivo diferente. Sin embargo, no puede cambiar el Modo de implementación, Unirse a Azure AD As, Privacidad Configuración o Tipo de cuenta de usuario.

### <a name="enrollment-status-page-settings-change"></a>Cambio en la configuración de la página de estado de inscripción

- Un número mayor de minutos para la configuración "Mostrar un error cuando la instalación tarda más de un número especificado de minutos".
- Se muestra el mensaje de error.
- Agregar o quitar aplicaciones en la configuración "Bloquear el uso del dispositivo hasta que se instalen estas aplicaciones necesarias si están asignadas al usuario o dispositivo".

## <a name="required-applications"></a>Aplicaciones necesarias

- Debes dirigirte a las aplicaciones de los grupos de *dispositivos* Modern Workplace Test, First, Fast y Broad. Las aplicaciones deben instalarse en el contexto "Sistema". Asegúrese de completar las pruebas con ESP en el grupo Prueba antes de asignarlas a todos los grupos.
- Ninguna aplicación debe requerir que el dispositivo se reinicie. Se recomienda que las aplicaciones se establezcan en "No hacer nada" al compilar el paquete de la aplicación si el dispositivo requiere un reinicio.
- Limite las aplicaciones necesarias solo a las aplicaciones principales que un usuario necesita inmediatamente al iniciar sesión en el dispositivo.
- Mantenga el tamaño total de todas las aplicaciones colectivamente por debajo de 1 GB para evitar tiempos de espera durante la fase de instalación de la aplicación.
- Lo ideal es que las aplicaciones no tengan dependencias. Si tienes aplicaciones que deben *tener* dependencias, asegúrate de configurarlas, probarlas y validarlas como parte de la evaluación de ESP.
- Microsoft Teams no se puede incluir en ESP.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. Acceder al [portal de administrador](access-admin-portal.md).
1. [Agregar y verificar los contactos de administración en el portal de administrador](add-admin-contacts.md).
1. [Ajustar la configuración después de la inscripción](conditional-access.md).
1. Implementar y asignar el [Portal de empresa de Intune](company-portal.md).
1. [Asignar las licencias](assign-licenses.md).
1. [Implementar las aplicaciones](deploy-apps.md).
1. [Configurar los dispositivos](set-up-devices.md).
1. Configure la experiencia de primera ejecución con Autopilot y la página Estado de inscripción (en este artículo).
1. [Habilitar las características de soporte técnico para el usuario](enable-support.md).
1. [Preparar a los usuarios para que usen los dispositivos](get-started-devices.md).
1. [Comenzar a usar el control de aplicaciones](get-started-app-control.md).
