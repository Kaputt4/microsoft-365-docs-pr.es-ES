---
title: Antivirus de Microsoft Defender en la aplicación Seguridad de Windows aplicación
description: Con Antivirus de Microsoft Defender en la aplicación Seguridad de Windows, puedes revisar, comparar y realizar tareas comunes.
keywords: wdav, antivirus, firewall, seguridad, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccb0d4cf168bbb4d3c1575c1e6611829909d0817
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275413"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Antivirus de Microsoft Defender en la aplicación Seguridad de Windows aplicación

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En Windows 10 versión 1703 y posteriores, la aplicación Windows Defender forma parte del Seguridad de Windows.

Configuración que anteriormente formaban parte del cliente de Windows Defender y del Windows Configuración principal se han combinado y movido a la nueva aplicación, que se instala de forma predeterminada como parte de Windows 10, versión 1703.

> [!IMPORTANT]
> Deshabilitar el servicio Seguridad de Windows centro no deshabilita Antivirus de Microsoft Defender o [Firewall de Windows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). Estos se deshabilitan automáticamente cuando se instala un antivirus de terceros o un producto de firewall y se mantienen actualizados.
>
> Si deshabilita el servicio del Centro de Seguridad de Windows o configura sus opciones de directiva de grupo asociadas para evitar que se inicie o ejecute, la aplicación Seguridad de Windows puede mostrar información obsoleta o inexacta acerca de los productos antivirus o firewall que haya instalado en el dispositivo.
> También puede impedir Antivirus de Microsoft Defender habilitarse si tiene un antivirus de terceros antiguo o obsoleto, o si desinstala productos antivirus de terceros que haya instalado anteriormente.
> Esto disminuirá significativamente la protección del dispositivo y podría provocar una infección de malware.

Consulta el [Seguridad de Windows para obtener](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) más información sobre otras Windows de seguridad que se pueden supervisar en la aplicación.

La Seguridad de Windows es una interfaz de cliente en Windows 10 versión 1703 y posteriores. No es el portal Centro de seguridad de Microsoft Defender web que se usa para revisar y administrar [Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Revisar la configuración de protección contra virus y amenazas en la Seguridad de Windows aplicación

![Captura de pantalla de la etiqueta Protección contra virus y amenazas en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

1. Abra la Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio de **Defender**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).
   
En las secciones siguientes se describe cómo realizar algunas de las tareas más comunes al revisar o interactuar con la protección contra amenazas proporcionada por Antivirus de Microsoft Defender en la Seguridad de Windows aplicación.

> [!NOTE]
> Si estas opciones de configuración se configuran e implementan mediante la directiva de grupo, la configuración descrita en esta sección será gris y no estará disponible para su uso en puntos de conexión individuales. Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows. El [tema Configure end-user interaction with Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md) describe cómo se puede configurar la configuración de invalidación de directiva local.

## <a name="run-a-scan-with-the-windows-security-app"></a>Ejecutar un examen con la Seguridad de Windows aplicación

1. Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. Seleccione **Examen rápido**. O bien, para ejecutar un examen completo, seleccione **Opciones de** examen y, a continuación, seleccione una opción, como **Examen completo**.

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Revisa la versión de actualización de inteligencia de seguridad y descarga las actualizaciones más recientes en la aplicación Seguridad de Windows seguridad

![Información del número de versión de inteligencia de seguridad](images/defender/wdav-wdsc-defs.png)

1. Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. Seleccione **Actualizaciones de protección contra & virus**. La versión instalada actualmente se muestra junto con información sobre cuándo se descargó. Puede comprobar la versión actual con la versión más reciente disponible para la descarga manual o revisar el registro de cambios de esa versión. Vea [Security intelligence updates for Antivirus de Microsoft Defender and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).

4. Seleccione **Buscar actualizaciones para** descargar nuevas actualizaciones de protección (si las hay).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Asegúrate Antivirus de Microsoft Defender está habilitado en la Seguridad de Windows aplicación

1. Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. Seleccione **Configuración de protección contra & virus**.

4. Alterna el **conmutador de protección en tiempo** real a **On**.

    > [!NOTE]
    > Si desactiva la **protección en tiempo** real, se volverá a activar automáticamente después de un breve retraso. Esto es para asegurarse de que está protegido contra malware y amenazas.
    > Si instalas otro producto antivirus, Antivirus de Microsoft Defender se deshabilita automáticamente y se indica como tal en la Seguridad de Windows aplicación. Aparecerá una configuración que le permitirá habilitar el [examen periódico limitado.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Agregar exclusiones para Antivirus de Microsoft Defender en la Seguridad de Windows aplicación

1. Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. En Administrar **configuración,** seleccione **Virus & configuración de protección contra amenazas**.

4. En la **configuración Exclusiones,** seleccione **Agregar o quitar exclusiones**. 

5. Seleccione el icono más ( **+** ) para elegir el tipo y establecer las opciones para cada exclusión. 

En la tabla siguiente se resumen los tipos de exclusión y lo que sucede:

|Tipo de exclusión  |Definido por  |Qué ocurre  |
|---------|---------|---------|
|**Archivo** |Ubicación <br/>Ejemplo: `c:\sample\sample.test` |El archivo específico se omite Antivirus de Microsoft Defender. |
|**Folder**    |Ubicación <br/>Ejemplo: `c:\test\sample`       |Todos los elementos de la carpeta especificada se omiten Antivirus de Microsoft Defender.         |
|**Tipo de archivo**   |Extensión de archivo <br/>Ejemplo: `.test` |Todos los archivos con la extensión en cualquier lugar del dispositivo `.test` se omiten Antivirus de Microsoft Defender.         |
|**Proceso**     |Ruta de acceso de archivo ejecutable <br>Ejemplo: `c:\test\process.exe`         |El proceso específico y los archivos abiertos por ese proceso se omiten Antivirus de Microsoft Defender.         |

Para obtener más información, consulte los siguientes recursos:
- [Configurar y validar exclusiones en función de la extensión de archivo y la ubicación de la carpeta](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [Configurar exclusiones para archivos abiertos por procesos](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>Revisar el historial de detección de amenazas en la Windows Defender centro de seguridad

1. Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. Seleccione **Historial de protección**. Se enumeran los elementos recientes.

## <a name="set-ransomware-protection-and-recovery-options"></a>Establecer opciones de protección y recuperación de ransomware

1. Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. En **Protección contra ransomware,** seleccione **Administrar protección contra ransomware**.

4. Para cambiar **la configuración de acceso controlado a** carpetas, vea Proteger [carpetas importantes con acceso controlado a carpetas.](/microsoft-365/security/defender-endpoint/controlled-folders)

5. Para configurar las opciones  de recuperación de ransomware, selecciona Configurar en Recuperación de datos ransomware y sigue las instrucciones para vincular o configurar tu cuenta de OneDrive para que puedas recuperarte fácilmente de un ataque de ransomware. 

## <a name="see-also"></a>Consulte también
- [Antivirus de Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)