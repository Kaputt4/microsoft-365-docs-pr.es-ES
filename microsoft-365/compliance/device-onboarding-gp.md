---
title: Incorporación Windows 10 y Windows 11 dispositivos mediante directiva de grupo
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: Use la directiva de grupo para implementar el paquete de configuración en Windows 10 y Windows 11 dispositivos para que se incorpore al servicio.
ms.openlocfilehash: fbba73fcf15ee9f71c4caacc57155a64e6cb9e9c
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950928"
---
# <a name="onboard-windows-10-devices-and-windows-11-using-group-policy"></a>Incorporación Windows 10 dispositivos y Windows 11 mediante la directiva de grupo 

**Se aplica a:**

- [Microsoft 365 prevención de pérdida de datos de punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
- Directiva de grupo

> [!NOTE]
> Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debe estar en Windows Server 2008 R2 o posterior.

> Para Windows Server 2019, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.

## <a name="onboard-devices-using-group-policy"></a>Incorporar dispositivos con la directiva de grupo

1. Abra el [Centro de cumplimiento](https://compliance.microsoft.com).

2. En el panel de navegación, **seleccione Configuración** Incorporación  >  **de dispositivos**.

3. En el **campo Método de** implementación, seleccione Directiva de **grupo**.

4. Haga **clic en Descargar paquete** y guarde el .zip archivo.

5. Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *DeviceComplianceLocalOnboardingScript.cmd*.

6. Abra la [Consola de administración de directivas de](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

7. En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo , luego Preferencias **y,** a continuación, **Configuración del panel de control.**

8. Haga clic con el botón secundario en **Tareas programadas**, elija **Nuevo** y, a continuación, haga clic en Tarea inmediata **(al menos Windows 7).**

9. En la **ventana Tarea** que se abre, vaya a la **pestaña General.** En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA y, a continuación, haga clic en Comprobar nombres **y, a** continuación, en **Aceptar**. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.

10. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.

11. Vaya a la **pestaña Acciones** y haga clic **en Nuevo...** Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción. Escriba el nombre de archivo y la ubicación del archivo *compartido WindowsDefenderATPOnboardingScript.cmd.*

12. Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.

## <a name="offboard-devices-using-group-policy"></a>Dispositivos offboard con directiva de grupo
Por motivos de seguridad, el paquete usado para dispositivos externos expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.

1. Obtenga el paquete de offboarding del [Centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).

2. En el panel de navegación, **seleccione Configuración**  >  **//Device onboarding**  >  **Offboarding**.

3. En el **campo Método de** implementación, seleccione Directiva de **grupo**.

4. Haga **clic en Descargar paquete** y guarde el .zip archivo.

5. Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

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
1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a>.
2. Haga clic **en Lista dispositivos.**
3. Compruebe que aparecen dispositivos.

> [!NOTE]
> Los dispositivos pueden tardar varios días en aparecer en la **lista Dispositivos.** Esto incluye el tiempo que tardan las directivas en distribuirse en el dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en iniciar la presentación de informes.


## <a name="related-topics"></a>Temas relacionados
- [Incorporación Windows 10 y Windows 11 dispositivos con Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [Incorporación Windows 10 y Windows 11 dispositivos con herramientas de administración de dispositivos móviles](device-onboarding-mdm.md)
- [Incorporación Windows 10 y Windows 11 dispositivos con un script local](device-onboarding-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](device-onboarding-vdi.md)
- [Ejecutar una prueba de detección en un Microsoft Defender recién incorporado para dispositivos de punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)