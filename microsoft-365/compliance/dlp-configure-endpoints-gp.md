---
title: Dispositivos de Windows 10 incorporados mediante la Directiva de grupo
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
description: Use la Directiva de grupo para implementar el paquete de configuración en dispositivos Windows 10 para que estén integrados en el servicio.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769510"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>Dispositivos de Windows 10 incorporados mediante la Directiva de grupo 

**Se aplica a:**

- [Prevención de pérdida de datos (DLP) de Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
- Directiva de grupo

> [!NOTE]
> Para usar actualizaciones de la Directiva de grupo (GP) para implementar el paquete, debe estar en Windows Server 2008 R2 o posterior.

> En el caso de Windows Server 2019, es posible que necesite reemplazar AUTHORITY\Well-Known-System-Account de NT con NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de la Directiva de grupo.

## <a name="onboard-devices-using-group-policy"></a>Dispositivos incorporados que usan la Directiva de grupo

1. Abra el archivo package. zip de configuración de GP ( *DeviceComplianceOnboardingPackage.zip* ) que ha descargado desde el Asistente de incorporación de servicios. También puede obtener el paquete del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. En el panel de navegación, seleccione incorporación de dispositivos de **configuración**  >  **Device Onboarding** .

3. En el campo **método de implementación** , seleccione Directiva de **Grupo** .

4. Haga clic en **Descargar paquete** y guarde el archivo. zip.

5. Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que pueda obtener acceso el dispositivo. Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *DeviceComplianceLocalOnboardingScript. cmd* .

6. Abra la [consola de administración de directivas de grupo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar** .

7. En el **Editor de administración de directivas de grupo** , vaya a **configuración del equipo** , **preferencias** y configuración del **Panel de control** .

8. Haga clic con el botón secundario en **tareas programadas** , seleccione **nuevo** y, a continuación, haga clic en **tarea inmediata (como mínimo, Windows 7)** .

9. En la ventana de **tareas** que se abre, vaya a la pestaña **General** . En **Opciones de seguridad** , haga clic en **cambiar usuario o grupo** y escriba sistema y, a continuación, haga clic en **Comprobar nombres** y, después, en **Aceptar** . NT AUTHORITY\SYSTEM aparece como la cuenta de usuario con la que se ejecutará la tarea.

10. Seleccione **ejecutar tanto si un usuario inició sesión como si no** y active la casilla de verificación **ejecutar con los privilegios más altos** .

11. Vaya a la ficha **acciones** y haga clic en **nuevo...** Asegúrese de que la acción **iniciar un programa** está seleccionada en el campo **acción** . Escriba el nombre de archivo y la ubicación del archivo *WindowsDefenderATPOnboardingScript. cmd* compartido.

12. Haga clic en **Aceptar** y cierre todas las ventanas de GPMC abiertas.


## <a name="offboard-devices-using-group-policy"></a>Dispositivos desincorpora con la Directiva de grupo
Por motivos de seguridad, el paquete que se usa para desincorpora dispositivos expirará 30 días después de la fecha en que se descargó. Los paquetes de retirada expirados enviados a un dispositivo se rechazarán. Al descargar un paquete de descarga, recibirá una notificación de la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.

> [!NOTE]
> Las directivas de incorporación y retirada no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario se producirán colisiones impredecibles.

1. Obtenga el paquete de descarga del [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/compliancesettings/deviceonboarding).

2. En el panel de navegación, seleccione **configuración**  >  **//Device incorporación** de la  >  **descarga** .

3. En el campo **método de implementación** , seleccione Directiva de **Grupo** .

4. Haga clic en **Descargar paquete** y guarde el archivo. zip.

5. Extraiga el contenido del archivo. zip en una ubicación compartida de solo lectura a la que pueda obtener acceso el dispositivo. Debe tener un archivo denominado *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

6. Abra la [consola de administración de directivas de grupo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar** .

7. En el **Editor de administración de directivas de grupo** , vaya a **configuración del equipo,** **preferencias** y configuración del **Panel de control** .

8. Haga clic con el botón secundario en **tareas programadas** , seleccione **nuevo** y, a continuación, haga clic en **tarea inmediata** .

9. En la ventana de **tareas** que se abre, vaya a la pestaña **General** . Elija la cuenta de usuario del sistema local (BUILTIN\SYSTEM) en **Opciones de seguridad** .

10. Seleccione **ejecutar tanto si un usuario inició sesión como si no** y active la casilla **ejecutar con los privilegios más altos** .

11. Vaya a la ficha **acciones** y haga clic en **nuevo...** Asegúrese de que la acción **iniciar un programa** está seleccionada en el campo **acción** . Escriba el nombre de archivo y la ubicación del archivo Shared  *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* .

12. Haga clic en **Aceptar** y cierre todas las ventanas de GPMC abiertas.

> [!IMPORTANT]
> La retirada hace que el dispositivo deje de enviar datos del sensor al portal, pero datos del dispositivo.


## <a name="monitor-device-configuration"></a>Supervisar la configuración del dispositivo
Con la Directiva de grupo no existe una opción para supervisar la implementación de directivas en los dispositivos. La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.

## <a name="monitor-devices-using-the-portal"></a>Supervisar dispositivos con el portal
1. Vaya al [centro de cumplimiento de Microsoft](https://compliance.microsoft.com/).
2. Haga clic en lista de **dispositivos** .
3. Compruebe que aparecen dispositivos.

> [!NOTE]
> Los dispositivos pueden tardar varios días en comenzar a mostrarse en la **lista de dispositivos** . Esto incluye el tiempo que tarda la distribución de las directivas en el dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en iniciar la generación de informes.


## <a name="related-topics"></a>Temas relacionados
- [Dispositivos con Windows 10 en placa mediante el administrador de configuración de Microsoft Endpoint](dlp-configure-endpoints-sccm.md)
- [Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles](dlp-configure-endpoints-mdm.md)
- [Dispositivos de Windows 10 incorporados que usan un script local](dlp-configure-endpoints-script.md)
- [Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados](dlp-configure-endpoints-vdi.md)
- [Ejecutar una prueba de detección en los dispositivos ATP de Microsoft defender recién integrados](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
