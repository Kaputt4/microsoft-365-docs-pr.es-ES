---
title: Incorporar dispositivos Windows 10 y Windows 11 mediante la directiva de grupo
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
description: Use directiva de grupo para implementar el paquete de configuración en dispositivos Windows 10 y Windows 11 para que se incorporen al servicio.
ms.openlocfilehash: 6c8c70d1bfdf3de0bc3848069a22b8610d445e42
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66623261"
---
# <a name="onboard-windows-10-devices-and-windows-11-using-group-policy"></a>Incorporación de dispositivos Windows 10 y Windows 11 mediante directiva de grupo 

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)
- Directiva de grupo

> [!NOTE]
> Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debe estar en Windows Server 2008 R2 o posterior.

> Para Windows Server 2019, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.

## <a name="onboard-devices-using-group-policy"></a>Incorporar dispositivos con la directiva de grupo

1. Abra el [Centro de cumplimiento](https://compliance.microsoft.com).

2. En el panel de navegación, seleccione **Configuración** > **Incorporación de dispositivos**.

3. En el campo **Método de implementación** , seleccione **Directiva de grupo**.

4. Haga clic en **Descargar paquete** y guarde el archivo .zip.

5. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo. Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *DeviceComplianceLocalOnboardingScript.cmd*.

6. Abra la [consola de administración de directiva de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón derecho en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

7. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo**, **Preferencias** y, a continuación, **Configuración del panel de control**.

8. Haga clic con el botón derecho en **Tareas programadas**, seleccione **Nuevo** y, a continuación, haga clic en **Tarea inmediata (al menos Windows 7).**

9. En la ventana **Tarea** que se abre, vaya a la pestaña **General** . En **Opciones de seguridad** , haga clic en **Cambiar usuario o grupo** y escriba SYSTEM y, a continuación, haga clic en **Comprobar nombres** y, a continuación, **en Aceptar**. NT AUTHORITY\SYSTEM aparece como la cuenta de usuario como se ejecutará la tarea.

10. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla **Ejecutar con los privilegios más altos** .

11. Vaya a la pestaña **Acciones** y haga clic en **Nuevo...** Asegúrese de que **Iniciar un programa** está seleccionado en el campo **Acción** . Escriba el nombre de archivo y la ubicación del archivo *Compartido WindowsDefenderATPOnboardingScript.cmd* .

12. Haga clic en **Aceptar** y cierre las ventanas de GPMC abiertas.

## <a name="offboard-devices-using-group-policy"></a>Dispositivos fuera del panel que usan directiva de grupo
Por motivos de seguridad, el paquete usado para dispositivos fuera del panel expirará 30 días después de la fecha en que se descargó. Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo. Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo; de lo contrario, esto provocará colisiones imprevisibles.

1. Obtenga el paquete de offboarding de [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/compliancesettings/deviceonboarding).

2. En el panel de navegación, seleccione **Configuración** > **//Incorporación de** >  dispositivos **Offboarding**.

3. En el campo **Método de implementación** , seleccione **Directiva de grupo**.

4. Haga clic en **Descargar paquete** y guarde el archivo .zip.

5. Extraiga el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda acceder el dispositivo. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

6. Abra la [consola de administración de directiva de grupo](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón derecho en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.

7. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo,** **Preferencias** y, a continuación, **Configuración del panel de control**.

8. Haga clic con el botón derecho en **Tareas programadas**, seleccione **Nuevo** y, a continuación, haga clic en **Tarea inmediata**.

9. En la ventana **Tarea** que se abre, vaya a la pestaña **General** . Elija la cuenta de usuario de SYSTEM local (BUILTIN\SYSTEM) en **Opciones de seguridad**.

10. Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla **Ejecutar con los privilegios más altos** .

11. Vaya a la pestaña **Acciones** y haga clic en **Nuevo...**. Asegúrese de que **Iniciar un programa** está seleccionado en el campo **Acción** . Escriba el nombre de archivo y la ubicación del archivo  *compartido DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .

12. Haga clic en **Aceptar** y cierre las ventanas de GPMC abiertas.

> [!IMPORTANT]
> La eliminación hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo.


## <a name="monitor-device-configuration"></a>Supervisión de la configuración del dispositivo
Con directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos. La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

## <a name="monitor-devices-using-the-portal"></a>Supervisión de dispositivos mediante el portal
1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento de Microsoft Purview</a>.
2. Haga clic en **Lista de dispositivos** .
3. Compruebe que aparecen los dispositivos.

> [!NOTE]
> Los dispositivos pueden tardar varios días en aparecer en la **lista Dispositivos**. Esto incluye el tiempo que tardan las directivas en distribuirse al dispositivo, el tiempo que tarda el usuario en iniciar sesión y el tiempo que tarda el punto de conexión en iniciar la generación de informes.


## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10 y Windows 11 mediante Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [Incorporar dispositivos Windows 10 y Windows 11 con herramientas de Administración de dispositivos móviles](device-onboarding-mdm.md)
- [Incorporar dispositivos Windows 10 y Windows 11 mediante un script local](device-onboarding-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](device-onboarding-vdi.md)
- [Ejecución de una prueba de detección en dispositivos Microsoft Defender para punto de conexión recién incorporados](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solución de problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
