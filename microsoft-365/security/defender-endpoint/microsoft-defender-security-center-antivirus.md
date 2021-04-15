---
title: Antivirus de Microsoft Defender en la aplicación Seguridad de Windows
description: Con Antivirus de Microsoft Defender ahora incluido en la aplicación Seguridad de Windows, puedes revisar, comparar y realizar tareas comunes.
keywords: wdav, antivirus, firewall, seguridad, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7635209c03dfc0367df16bfb650a4e52d2b2b3f8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765328"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Antivirus de Microsoft Defender en la aplicación Seguridad de Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En Windows 10, versión 1703 y versiones posteriores, la aplicación Windows Defender forma parte de la seguridad de Windows.

La configuración que anteriormente formaba parte del cliente de Windows Defender y la configuración principal de Windows se han combinado y movido a la nueva aplicación, que se instala de forma predeterminada como parte de Windows 10, versión 1703.

> [!IMPORTANT]
> Deshabilitar el servicio de Windows Security Center no deshabilita el Antivirus de Microsoft Defender ni [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). Estos se deshabilitan automáticamente cuando se instala un antivirus de terceros o un producto de firewall y se mantienen actualizados.
>
> Si deshabilitas el servicio del Centro de seguridad de Windows o configuras la configuración de la directiva de grupo asociada para evitar que se inicie o ejecute, la aplicación seguridad de Windows puede mostrar información obsoleta o inexacta sobre los productos de antivirus o firewall que haya instalado en el dispositivo.
> También puede impedir que Antivirus de Microsoft Defender se habilite si tiene un antivirus de terceros antiguo o obsoleto, o si desinstala cualquier producto antivirus de terceros que haya instalado anteriormente.
> Esto disminuirá significativamente la protección del dispositivo y podría provocar una infección de malware.

Consulta el [artículo Seguridad de Windows](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) para obtener más información sobre otras características de seguridad de Windows que se pueden supervisar en la aplicación.

La aplicación Seguridad de Windows es una interfaz de cliente en Windows 10, versión 1703 y versiones posteriores. No es el portal web del Centro de seguridad de Microsoft Defender que se usa para revisar y administrar [Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Revisar la configuración de protección contra virus y amenazas en la aplicación Seguridad de Windows

![Captura de pantalla de la etiqueta & de protección contra amenazas de virus en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

1. Abre la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio de **Defender**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).
   
En las secciones siguientes se describe cómo realizar algunas de las tareas más comunes al revisar o interactuar con la protección contra amenazas proporcionada por Antivirus de Microsoft Defender en la aplicación seguridad de Windows.

> [!NOTE]
> Si estas opciones de configuración se configuran e implementan mediante la directiva de grupo, la configuración descrita en esta sección será gris y no estará disponible para su uso en puntos de conexión individuales. Los cambios realizados a través de un objeto de directiva de grupo deben implementarse primero en puntos de conexión individuales antes de que la configuración se actualice en Configuración de Windows. En [el tema Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) se describe cómo se puede configurar la configuración de invalidación de directiva local.

## <a name="run-a-scan-with-the-windows-security-app"></a>Ejecutar un examen con la aplicación Seguridad de Windows

1. Abra la aplicación Seguridad de Windows buscando en el menú inicio **seguridad** y, a continuación, **seleccionando Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. Seleccione **Examen rápido**. O bien, para ejecutar un examen completo, seleccione **Opciones de** examen y, a continuación, seleccione una opción, como **Examen completo**.

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Revisa la versión de actualización de inteligencia de seguridad y descarga las actualizaciones más recientes en la aplicación Seguridad de Windows

![Información del número de versión de inteligencia de seguridad](images/defender/wdav-wdsc-defs.png)

1. Abra la aplicación Seguridad de Windows buscando en el menú inicio *seguridad* y, a continuación, **seleccionando Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. Seleccione **Actualizaciones de protección contra & virus**. La versión instalada actualmente se muestra junto con información sobre cuándo se descargó. Puede comprobar la versión actual con la versión más reciente disponible para la descarga manual o revisar el registro de cambios de esa versión. Vea [Actualizaciones de inteligencia de seguridad para Antivirus de Microsoft Defender y otros antimalware de Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates).

4. Seleccione **Buscar actualizaciones para** descargar nuevas actualizaciones de protección (si las hay).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Asegurarse de que Antivirus de Microsoft Defender está habilitado en la aplicación Seguridad de Windows

1. Abra la aplicación Seguridad de Windows buscando en el menú inicio *seguridad* y, a continuación, **seleccionando Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. Seleccione **Configuración de protección contra & virus**.

4. Alterna el **conmutador de protección en tiempo** real a **On**.

    > [!NOTE]
    > Si desactiva la **protección en tiempo** real, se volverá a activar automáticamente después de un breve retraso. Esto es para asegurarse de que está protegido contra malware y amenazas.
    > Si instalas otro producto antivirus, Antivirus de Microsoft Defender se deshabilita automáticamente y se indica como tal en la aplicación seguridad de Windows. Aparecerá una configuración que le permitirá habilitar el [examen periódico limitado.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Agregar exclusiones para Antivirus de Microsoft Defender en la aplicación seguridad de Windows

1. Abra la aplicación Seguridad de Windows buscando en el menú inicio *seguridad* y, a continuación, **seleccionando Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. En Administrar **configuración,** seleccione **Virus & configuración de protección contra amenazas**.

4. En la **configuración Exclusiones,** seleccione **Agregar o quitar exclusiones**. 

5. Seleccione el icono más ( **+** ) para elegir el tipo y establecer las opciones para cada exclusión. 

En la tabla siguiente se resumen los tipos de exclusión y lo que sucede:

|Tipo de exclusión  |Definido por  |Qué ocurre  |
|---------|---------|---------|
|**Archivo** |Ubicación <br/>Ejemplo: `c:\sample\sample.test` |El antivirus de Microsoft Defender omite el archivo específico. |
|**Folder**    |Ubicación <br/>Ejemplo: `c:\test\sample`       |Antivirus de Microsoft Defender omite todos los elementos de la carpeta especificada.         |
|**Tipo de archivo**   |Extensión de archivo <br/>Ejemplo: `.test` |Antivirus de Microsoft Defender omite todos los archivos con la extensión en cualquier lugar `.test` del dispositivo.         |
|**Proceso**     |Ruta de acceso de archivo ejecutable <br>Ejemplo: `c:\test\process.exe`         |El antivirus de Microsoft Defender omite el proceso específico y los archivos abiertos por ese proceso.         |

Para obtener más información, consulte los siguientes recursos:
- [Configurar y validar exclusiones en función de la extensión de archivo y la ubicación de la carpeta](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [Configurar exclusiones para archivos abiertos por procesos](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>Revisar el historial de detección de amenazas en la Windows Defender centro de seguridad

1. Abra la aplicación Seguridad de Windows buscando en el menú inicio *seguridad* y, a continuación, **seleccionando Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. Seleccione **Historial de protección**. Se enumeran los elementos recientes.

## <a name="set-ransomware-protection-and-recovery-options"></a>Establecer opciones de protección y recuperación de ransomware

1. Abra la aplicación Seguridad de Windows buscando en el menú inicio *seguridad* y, a continuación, **seleccionando Seguridad de Windows**.

2. Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).

3. En **Protección contra ransomware,** seleccione **Administrar protección contra ransomware**.

4. Para cambiar **la configuración de acceso controlado a** carpetas, vea Proteger [carpetas importantes con acceso controlado a carpetas.](/microsoft-365/security/defender-endpoint/controlled-folders)

5. Para configurar las opciones  de recuperación de ransomware, selecciona Configurar en Recuperación de datos ransomware y sigue las instrucciones para vincular o configurar tu cuenta de OneDrive para que puedas recuperarte fácilmente de un ataque de ransomware. 

## <a name="see-also"></a>Vea también
- [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md)