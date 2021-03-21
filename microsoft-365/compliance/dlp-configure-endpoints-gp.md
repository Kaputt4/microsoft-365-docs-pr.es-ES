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
ms.openlocfilehash: b786d011a46f69e7bcac846e726e2aeb3031ae08
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918026"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Incorporación de dispositivos Windows 10 con la directiva de grupo 

**Se aplica a:**

- [Prevención de pérdida de datos del extremo de Microsoft 365 (DLP)](./endpoint-dlp-learn-about.md)
- Directiva de grupo

> [!NOTE]
> Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debes estar en Windows Server 2008 R2 o posterior.

> Para Windows Server 2019, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.

## <a name="onboard-devices-using-group-policy"></a>Incorporación de dispositivos mediante directiva de grupo

1. Abra el archivo .zip del paquete de configuración de GP (*DeviceComplianceOnboardingPackage.zip*) que descargó del Asistente para incorporación de servicios. También puede obtener el paquete desde el [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. En el panel de navegación, seleccione **Configuración de** incorporación  >  **de dispositivos**.

3. En el **campo Método de** implementación, seleccione Directiva de **grupo**.

4. Haga **clic en Descargar paquete** y guarde el archivo .zip.

5. Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *DeviceComplianceLocalOnboardingScript.cmd*.

6. Abra la [Consola de administración de directivas de](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

7. En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo , luego Preferencias **y,** a continuación, **Configuración del panel de control.**

8. Haga clic con el botón secundario en **Tareas programadas**, elija **Nuevo** y, a continuación, haga clic en Tarea inmediata **(al menos Windows 7).**

9. En la **ventana Tarea** que se abre, vaya a la **pestaña General.** En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA y, a continuación, haga clic en Comprobar nombres **y, a** continuación, en **Aceptar**. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.

10. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.

11. Vaya a la **pestaña Acciones** y haga clic **en Nuevo...** Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción. Escriba el nombre de archivo y la ubicación del archivo *compartido WindowsDefenderATPOnboardingScript.cmd.*

12. Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.


## <a name="offboard-devices-using-group-policy"></a>Dispositivos offboard con directiva de grupo
Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtenga el paquete de offboarding del [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).

2. En el panel de navegación, seleccione **Configuración**  >  **//Incorporación de**  >  **dispositivos Offboarding**.

3. En el **campo Método de** implementación, seleccione Directiva de **grupo**.

4. Haga **clic en Descargar paquete** y guarde el archivo .zip.

5. Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6. Abra la [Consola de administración de directivas de](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

7. En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo, preferencias** **y,** a continuación, **configuración del panel de control.**

8. Haga clic con el botón secundario **en Tareas programadas**, **elija Nuevo** y, a continuación, haga clic en **Tarea inmediata**.

9. En la **ventana Tarea** que se abre, vaya a la **pestaña General.** Elija la cuenta de usuario del SISTEMA local (BUILTIN\SYSTEM) en **Opciones de seguridad**.

10. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.

11. Vaya a la **pestaña Acciones** y haga clic **en Nuevo...**. Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción. Escriba el nombre de archivo y la ubicación del archivo  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartido.

12. Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.

> [!IMPORTANT]
> El offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo.


## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo
Con la directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos. La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

## <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos con el portal
1. Vaya al [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com/).
2. Haga clic **en Lista dispositivos.**
3. Compruebe que aparecen dispositivos.

> [!NOTE]
> Los dispositivos pueden tardar varios días en aparecer en la **lista Dispositivos.** Esto incluye el tiempo que tardan las directivas en distribuirse en el dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en iniciar la presentación de informes.


## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10 con Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows 10 mediante un script local](dlp-configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](dlp-configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en un dispositivo ATP de Microsoft Defender recién incorporado](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)