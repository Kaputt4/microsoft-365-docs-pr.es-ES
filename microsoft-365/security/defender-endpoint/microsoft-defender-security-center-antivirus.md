---
title: Microsoft Defender Antivirus en la aplicación Seguridad de Windows
description: Con Microsoft Defender Antivirus ahora incluido en la aplicación Seguridad de Windows, puede revisar, comparar y realizar tareas comunes.
keywords: wdav, antivirus, firewall, seguridad, windows, antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 621dcf9e1b24f0223180198337c82c3ece6dd5c8
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68627003"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Microsoft Defender Antivirus en la aplicación Seguridad de Windows

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

En Windows 10, versión 1703 y posteriores, la aplicación Windows डिफेन्डर forma parte de la Seguridad de Windows.

La configuración que anteriormente formaba parte del cliente Windows डिफेन्डर y la configuración principal de Windows se ha combinado y movido a la nueva aplicación, que se instala de forma predeterminada como parte de Windows 10, versión 1703.

> [!IMPORTANT]
> Deshabilitar el Seguridad de Windows app service no deshabilita Microsoft Defender Antivirus ni [Windows डिफेन्डर Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). Se deshabilitan automáticamente cuando se instala un antivirus o un producto de firewall de terceros y se mantienen actualizados.
> Si deshabilita la Seguridad de Windows app service o configura sus opciones de समूह नीति asociadas para evitar que se inicie o se ejecute, la aplicación Seguridad de Windows podría mostrar información obsoleta o imprecisa sobre los productos antivirus o de firewall que haya instalado en el dispositivo.
> También puede impedir que Microsoft Defender Antivirus se habilite si tiene un antivirus de terceros antiguo o obsoleto, o si desinstala cualquier producto antivirus de terceros que haya instalado anteriormente.
> Esto reducirá significativamente la protección de su dispositivo y podría conducir a una infección por malware.

Consulta el [artículo Seguridad de Windows](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) para obtener más información sobre otras características de seguridad de Windows que se pueden supervisar en la aplicación.

La aplicación Seguridad de Windows es una interfaz de cliente en Windows 10, versión 1703 y posteriores. No es el portal web Microsoft 365 Defender el que se usa para revisar y administrar [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Revisar la configuración de protección contra virus y amenazas en la aplicación Seguridad de Windows

:::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Configuración de protección contra virus y amenazas en Seguridad de Windows aplicación" lightbox="../../media/wdav-protection-settings-wdsc.png":::

1. Abra la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando **Seguridad de Windows** en el menú inicio.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda).

En las secciones siguientes se describe cómo realizar algunas de las tareas más comunes al revisar o interactuar con la protección contra amenazas proporcionada por Microsoft Defender Antivirus en la aplicación Seguridad de Windows.

> [!NOTE]
> Si estas opciones se configuran e implementan mediante समूह नीति, la configuración descrita en esta sección se atenuará y no estará disponible para su uso en puntos de conexión individuales. Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows. En el tema [Configurar la interacción del usuario final con Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) se describe cómo se puede configurar la configuración de invalidación de directiva local.

## <a name="run-a-scan-with-the-windows-security-app"></a>Ejecución de un examen con la aplicación Seguridad de Windows

1. Abra la aplicación Seguridad de Windows buscando **seguridad** en el menú Inicio y, a continuación, seleccione **Seguridad de Windows**.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda).

3. Seleccione **Examen rápido**. O bien, para ejecutar un examen completo, seleccione **Opciones de examen** y, a continuación, seleccione una opción, como **Examen completo**.

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Revise la versión de actualización de inteligencia de seguridad y descargue las actualizaciones más recientes en la aplicación Seguridad de Windows.

:::image type="content" source="../../media/wdav-wdsc-defs.png" alt-text="Número de versión de Inteligencia de seguridad" lightbox="../../media/wdav-wdsc-defs.png":::

1. Abra la aplicación Seguridad de Windows buscando *seguridad* en el menú Inicio y, a continuación, seleccione **Seguridad de Windows**.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda).

3. Seleccione **Virus & actualizaciones de protección contra amenazas**. La versión instalada actualmente se muestra junto con información sobre cuándo se descargó. Puede comprobar su versión actual con la versión más reciente disponible para la descarga manual o revisar el registro de cambios de esa versión. Consulte [Actualizaciones de inteligencia de seguridad para Microsoft Defender Antivirus y otros antimalware de Microsoft](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus).

4. Seleccione **Buscar actualizaciones** para descargar nuevas actualizaciones de protección (si hay alguna).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Asegúrese de que Microsoft Defender Antivirus está habilitado en la aplicación de Seguridad de Windows

1. Abra la aplicación Seguridad de Windows buscando *seguridad* en el menú Inicio y, a continuación, seleccione **Seguridad de Windows**.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda).

3. Seleccione **Virus & configuración de protección contra amenazas**.

4. Cambie el conmutador **Protección en tiempo real** a **Activado**.

    > [!NOTE]
    > Si desactiva la **protección en tiempo real** , se volverá a activar automáticamente después de un breve retraso. Esto es para asegurarse de que está protegido contra malware y amenazas.
    > Si instala otro producto antivirus, Microsoft Defender Antivirus se deshabilita automáticamente y se indica como tal en la aplicación Seguridad de Windows. Aparecerá una configuración que le permitirá habilitar el [examen periódico limitado](limited-periodic-scanning-microsoft-defender-antivirus.md).

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Agregar exclusiones para Microsoft Defender Antivirus en la aplicación Seguridad de Windows

1. Abra la aplicación Seguridad de Windows buscando *seguridad* en el menú Inicio y, a continuación, seleccione **Seguridad de Windows**.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda).

3. En **Configuración de antivirus y protección contra amenazas**, seleccione **Administrar la configuración**.

4. En **Exclusiones**, seleccione **Agregar o quitar exclusiones**.

5. Seleccione el icono más (**+**) para elegir el tipo y establecer las opciones para cada exclusión.

En la tabla siguiente se resumen los tipos de exclusión y lo que sucede:

|Tipo de exclusión|Definido por|Qué ocurre|
|---|---|---|
|**Archivo**|Ubicación <br/>Ejemplo: `c:\sample\sample.test`|Microsoft Defender Antivirus omite el archivo específico.|
|**Folder**|Ubicación <br/>Ejemplo: `c:\test\sample`|Microsoft Defender Antivirus omite todos los elementos de la carpeta especificada.|
|**Tipo de archivo**|Extensión de archivo <br/>Ejemplo: `.test`|Microsoft Defender Antivirus omite todos los archivos con la `.test` extensión en cualquier lugar del dispositivo.|
|**Proceso**|Ruta de acceso del archivo ejecutable <br>Ejemplo: `c:\test\process.exe`|Microsoft Defender Antivirus omite el proceso específico y los archivos abiertos por ese proceso.|

Para obtener más información, consulte los siguientes recursos:

- [Configuración y validación de exclusiones basadas en la extensión de archivo y la ubicación de la carpeta](./configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configuración de exclusiones para archivos abiertos por procesos](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-for-cloud-app"></a>Revisión del historial de detección de amenazas en la aplicación Windows डिफेन्डर for Cloud

1. Abra la aplicación Seguridad de Windows buscando *seguridad* en el menú Inicio y, a continuación, seleccione **Seguridad de Windows**.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda).

3. Seleccione **Historial de protección**. Se muestran los elementos recientes.

## <a name="set-ransomware-protection-and-recovery-options"></a>Establecer opciones de recuperación y protección contra ransomware

1. Abra la aplicación Seguridad de Windows buscando *seguridad* en el menú Inicio y, a continuación, seleccione **Seguridad de Windows**.

2. Seleccione el icono **Protección contra amenazas de Virus &** (o el icono de escudo en la barra de menús de la izquierda).

3. En **Protección contra ransomware**, seleccione **Administrar protección contra ransomware**.

4. Para cambiar la configuración de **acceso a carpetas controladas** , consulte [Protección de carpetas importantes con acceso controlado a carpetas](/microsoft-365/security/defender-endpoint/controlled-folders).

5. Para configurar las opciones de recuperación de ransomware, seleccione **Configurar** en **Recuperación de datos ransomware** y siga las instrucciones para vincular o configurar su cuenta de OneDrive para que pueda recuperarse fácilmente de un ataque de ransomware.

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md)
