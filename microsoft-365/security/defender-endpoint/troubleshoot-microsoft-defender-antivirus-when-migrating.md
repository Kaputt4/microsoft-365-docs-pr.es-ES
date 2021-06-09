---
title: Solucionar problemas del Antivirus de Windows Defender al migrar desde una solución de terceros
description: Solucionar errores comunes al migrar a Antivirus de Microsoft Defender
keywords: evento, código de error, registro, solución de problemas, antivirus de Microsoft Defender, antivirus de Windows Defender, migración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3fcc79e767edb533a20402a2f92ba4abc7d8386a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764596"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Solucionar problemas del Antivirus de Windows Defender al migrar desde una solución de terceros

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)


Puede encontrar ayuda aquí si encuentra problemas al migrar desde una solución de seguridad de terceros a Antivirus de Microsoft Defender.

## <a name="review-event-logs"></a>Revisar registros de eventos

Abra la aplicación Visor de eventos seleccionando el icono **Buscar** en la barra de tareas y buscando el *visor de eventos.*

Encontrará información Antivirus de Microsoft Defender en **Registros** de aplicaciones y servicios  >  **Microsoft**  >  **Windows**  >  **Windows Defender**. 

Desde allí, seleccione **Abrir debajo** de **Operativo**.

Al seleccionar un evento en el panel de detalles, se mostrará más información sobre un evento en el panel inferior, en las pestañas **General** **y** Detalles.

## <a name="microsoft-defender-antivirus-wont-start"></a>Antivirus de Microsoft Defender no se iniciará

Este problema puede manifestarse en forma de varios IDs de eventos diferentes, todos los cuales tienen la misma causa subyacente.

### <a name="associated-event-ids"></a>IDs de eventos asociados

 Id. de evento | Nombre de registro | Descripción | Origen
-|-|-|-
15 | Aplicación | Se Windows Defender el estado correctamente para SECURITY_PRODUCT_STATE_OFF. | Centro de seguridad
5007 | Microsoft-Windows-Windows Defender/Operational | Antivirus de Windows Defender La configuración ha cambiado.  Si se trata de un evento inesperado, debes revisar la configuración, ya que puede ser el resultado de malware.<br /><br />**Valor antiguo:** Default\IsServiceRunning = 0x0<br />**Nuevo valor:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft-Windows-Windows Defender/Operational | Antivirus de Windows Defender está deshabilitado el examen de spyware y otro software potencialmente no deseado. | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Cómo saber si Antivirus de Microsoft Defender no se iniciará porque está instalado un antivirus de terceros

En un dispositivo Windows 10, si no usa Microsoft Defender para Endpoint y tiene instalado un antivirus de terceros, Antivirus de Microsoft Defender se desactivará automáticamente. Si usa Microsoft Defender para Endpoint con un antivirus de terceros instalado, Antivirus de Microsoft Defender se iniciará en modo pasivo, con funcionalidad reducida.

> [!TIP]
> El escenario descrito solo se aplica a Windows 10. Otras versiones de Windows [tienen diferentes respuestas](microsoft-defender-antivirus-compatibility.md) a Antivirus de Microsoft Defender se ejecutan junto con software de seguridad de terceros.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Usar la aplicación Servicios para comprobar si Antivirus de Microsoft Defender está desactivado

Para abrir la aplicación Servicios, seleccione el icono **Buscar** de la barra de tareas y busque *servicios.* También puedes abrir la aplicación desde la línea de comandos escribiendo *services.msc*.

La información sobre Antivirus de Microsoft Defender aparecerá en la aplicación Servicios en **Windows Defender**  >  **Operativo**. El nombre del servicio antivirus *es Antivirus de Windows Defender servicio*.

Al comprobar la aplicación, es posible que veas que el servicio *de Antivirus de Windows Defender* está establecido en manual, pero cuando intentas iniciar este servicio manualmente, recibes una advertencia que indica que el servicio de servicio Antivirus de Windows Defender en el equipo local se inició y, a continuación, se *detuvo. Algunos servicios se detienen automáticamente si otros* servicios o programas no los usan.

Esto indica que Antivirus de Microsoft Defender se ha desactivado automáticamente para conservar la compatibilidad con un antivirus de terceros.

#### <a name="generate-a-detailed-report"></a>Generar un informe detallado

Puede generar un informe detallado sobre las directivas de  grupo activas actualmente abriendo un símbolo del sistema en modo Ejecutar como administrador y, a continuación, escriba el siguiente comando:

```powershell
GPresult.exe /h gpresult.html
```

Esto generará un informe ubicado en *./gpresult.html*. Abra este archivo y es posible que vea los siguientes resultados, en función de cómo Antivirus de Microsoft Defender se ha desactivado.

##### <a name="group-policy-results"></a>Resultados de la directiva de grupo

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Si la configuración de seguridad se implementa a través de la directiva de grupo (GPO) en el nivel de dominio o local, o a través de System Center configuration Manager (SCCM)

En el informe GPResults, bajo el título *Windows Components/Antivirus de Windows Defender*, puede ver algo como la siguiente entrada, que indica que Antivirus de Microsoft Defender está desactivado.

Directiva | Configuración | GPO ganador
-|-|-
Desactivar Antivirus de Windows Defender | Habilitado | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Si la configuración de seguridad se implementa mediante la preferencia de directiva de grupo (GPP)

Bajo el encabezado, Elemento del Registro (ruta de acceso *clave: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Nombre del valor: DisableAntiSpyware),* puede ver algo parecido a la siguiente entrada, que indica que Antivirus de Microsoft Defender está desactivado.

DisableAntiSpyware | -
-|-
GPO ganador | Win10-Workstations
Resultado: Correcto | 
**General** | 
Acción | Actualizar
**Propiedades** | 
Subárbol | HKEY_LOCAL_MACHINE
Ruta de acceso clave | SOFTWARE\Policies\Microsoft\Windows Defender
Nombre del valor | DisableAntiSpyware
Tipo de valor | REG_DWORD
Datos del valor | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Si la configuración de seguridad se implementa a través de la clave del Registro

El informe puede contener el siguiente texto, que indica que Antivirus de Microsoft Defender está desactivado:
 
> Registro (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hexadecimal)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Si la configuración de seguridad se establece en Windows o en la Windows de servidor

El administrador de imaginación puede haber establecido la directiva de seguridad **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, localmente a través de *GPEdit.exe*, *LGPO.exe*, o modificando el Registro en su secuencia de tareas. Puede configurar [un identificador de imagen de confianza](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) para Antivirus de Microsoft Defender.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Volver Antivirus de Microsoft Defender activar

Antivirus de Microsoft Defender se activará automáticamente si ningún otro antivirus está activo actualmente. Tendrás que desactivar completamente el antivirus de terceros para garantizar que Antivirus de Microsoft Defender se pueda ejecutar con funcionalidad completa.

> [!WARNING]
> Las soluciones que sugieren que edite los valores de inicio de Windows Defender para *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc* y *windefend* en HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services no son compatibles y pueden forzarle a volver *a* crear una imagen del sistema.

El modo pasivo está disponible si empiezas a usar Microsoft Defender para Endpoint y un antivirus de terceros junto con Antivirus de Microsoft Defender. El modo pasivo permite a Microsoft Defender examinar archivos y actualizarse, pero no corregirá las amenazas. Además, la supervisión del comportamiento a través de la Protección en tiempo [real](configure-real-time-protection-microsoft-defender-antivirus.md) no está disponible en modo pasivo, a menos que se implemente prevención de pérdida de datos de extremo [(DLP).](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)

Otra característica, conocida como [examen periódico limitado,](limited-periodic-scanning-microsoft-defender-antivirus.md)está disponible para los usuarios finales cuando Antivirus de Microsoft Defender se configura para desactivarse automáticamente. Esta característica permite Antivirus de Microsoft Defender archivos periódicamente junto con un antivirus de terceros, con un número limitado de detecciones.

> [!IMPORTANT]
> No se recomienda el examen periódico limitado en entornos empresariales. Las capacidades de detección, administración e informes disponibles al ejecutar Antivirus de Microsoft Defender en este modo se reducen en comparación con el modo activo.

### <a name="see-also"></a>Consulte también

* [Antivirus de Microsoft Defender compatibilidad](microsoft-defender-antivirus-compatibility.md)
* [Antivirus de Microsoft Defender en la aplicación Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md)