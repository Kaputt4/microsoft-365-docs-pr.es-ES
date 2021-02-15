---
title: Incorporar dispositivos Windows 10 mediante la directiva de grupo
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Usa la directiva de grupo para implementar el paquete de configuración en dispositivos Windows 10 para que se incorpore al servicio.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769510"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Incorporar dispositivos Windows 10 mediante la directiva de grupo 

**Se aplica a:**

- [Prevención de pérdida de datos (DLP) de Punto de conexión de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Directiva de grupo

> [!NOTE]
> Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debes estar en Windows Server 2008 R2 o posterior.

> Para Windows Server 2019, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.

## <a name="onboard-devices-using-group-policy"></a>Incorporar dispositivos mediante la directiva de grupo

1. Abre el archivo .zip del paquete de configuración de GP (*DeviceComplianceOnboardingPackage.zip*) que descargaste desde el Asistente para la incorporación de servicios. También puede obtener el paquete desde el Centro [de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. En el panel de navegación, selecciona **Configuración de** incorporación  >  **de dispositivos.**

3. En el **campo Método de** implementación, seleccione Directiva de **grupo.**

4. Haz **clic en Descargar paquete** y guarda el archivo .zip.

5. Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo. Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *DeviceComplianceLocalOnboardingScript.cmd*.

6. Abre la [Consola de administración de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) directivas de grupo (GPMC), haz clic con el botón derecho en el objeto de directiva de grupo (GPO) que quieras configurar y haz clic en **Editar.**

7. En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo, preferencias **y,** a continuación, configuración del Panel **de control.**

8. Haga clic con el **botón secundario en Tareas programadas**, elija **Nuevo** y, a continuación, haga clic en Tarea **inmediata (al menos Windows 7).**

9. En la **ventana** Tarea que se abre, vaya a la **pestaña** General. En **Opciones de seguridad,** **haga clic en Cambiar** usuario o grupo y escriba SISTEMA y, a continuación, haga clic en Comprobar nombres y, **a** continuación, **en Aceptar.** NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.

10. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con los **privilegios** más altos.

11. Vaya a la **pestaña Acciones** y haga clic **en Nuevo...** Asegúrese de **que la opción Iniciar un programa** esté seleccionada en el **campo** Acción. Escribe el nombre de archivo y la ubicación del archivo *compartido WindowsDefenderATPOnboardingScript.cmd.*

12. Haga **clic en Aceptar** y cierre las ventanas de GPMC abiertas.


## <a name="offboard-devices-using-group-policy"></a>Quitar dispositivos mediante la directiva de grupo
Por motivos de seguridad, el paquete usado para los dispositivos de descarga expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de baja expirados enviados a un dispositivo. Al descargar un paquete de descarga, se te notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y baja no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones impredecibles.

1. Obtenga el paquete de descarga del Centro [de cumplimiento de Microsoft.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. En el panel de navegación, seleccione **Configuración**  >  **//Incorporación de**  >  **dispositivos.**

3. En el **campo Método de** implementación, seleccione Directiva de **grupo.**

4. Haz **clic en Descargar paquete** y guarda el archivo .zip.

5. Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6. Abre la [Consola de administración de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) directivas de grupo (GPMC), haz clic con el botón derecho en el objeto de directiva de grupo (GPO) que quieras configurar y haz clic en **Editar.**

7. En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo, preferencias** **y,** a continuación, configuración del Panel **de control.**

8. Haga clic con el botón secundario **en Tareas programadas,** **elija Nuevo** y, a continuación, haga clic en **Tarea inmediata.**

9. En la **ventana** Tarea que se abre, vaya a la **pestaña** General. Elija la cuenta de usuario del SISTEMA local (BUILTIN\SYSTEM) en **Opciones de seguridad.**

10. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con los **privilegios** más altos.

11. Vaya a la **pestaña Acciones** y haga clic **en Nuevo...**. Asegúrese de **que la opción Iniciar un programa** esté seleccionada en el **campo** Acción. Escriba el nombre de archivo y la ubicación del archivo *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd.*

12. Haga **clic en Aceptar** y cierre las ventanas de GPMC abiertas.

> [!IMPORTANT]
> La baja hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo.


## <a name="monitor-device-configuration"></a>Supervisar la configuración de dispositivos
Con la directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos. La supervisión se puede realizar directamente en el portal o mediante las diferentes herramientas de implementación.

## <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos mediante el portal
1. Vaya al [Centro de cumplimiento de Microsoft.](https://compliance.microsoft.com/)
2. Haga clic **en Lista de** dispositivos.
3. Comprueba que los dispositivos aparezcan.

> [!NOTE]
> Los dispositivos pueden tardar varios días en aparecer en la **lista de dispositivos.** Esto incluye el tiempo que tardan las directivas en distribuirse al dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en empezar a informar.


## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](dlp-configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en dispositivos ATP de Microsoft Defender recién incorporados](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
