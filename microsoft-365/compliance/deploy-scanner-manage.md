---
title: Ejecución del analizador de Microsoft Purview Information Protection
f1.keywords: ''
ms.author: libarson
author: libarson
manager: aashishr
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: normal
ms.collection:
- purview-compliance
- tier3
description: Instrucciones para ejecutar el escáner desde Microsoft Purview Information Protection para detectar, clasificar y proteger archivos en almacenes de datos.
ms.openlocfilehash: e1e8ab8fcfe2e156d2602a2c5d72511ebf769040
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631359"
---
# <a name="running-the-information-protection-scanner"></a>Ejecución del analizador de protección de la información

Una vez que haya confirmado [los requisitos del sistema](deploy-scanner-prereqs.md) y [haya configurado e instalado el escáner](deploy-scanner-configure-install.md), [ejecute un examen de detección](#run-a-discovery-cycle-and-view-reports-for-the-scanner) para empezar.

Siga otros pasos detallados a continuación para administrar los exámenes en adelante.

- [Detener un examen](#stopping-a-scan)
- [Volver a examinar archivos](#rescanning-files)

Para obtener más información, consulte [Más información sobre el escáner de Microsoft Purview Information Protection](deploy-scanner.md).

> [!TIP]
> Aunque la mayoría de los clientes realizarán estos procedimientos en el portal de administración, es posible que tenga que trabajar solo en PowerShell.
>
> Por ejemplo, si trabaja en un entorno sin acceso a Azure Portal, como [los servidores de escáner de Azure China 21Vianet](/microsoft-365/admin/services-in-china/parity-between-azure-information-protection#manage-azure-information-protection-content-scan-jobs), autentíquese en el módulo de PowerShell [AzureInformationProtection](/powershell/module/azureinformationprotection) y, a continuación, continúe con las instrucciones de este artículo solo para PowerShell.
>
## <a name="run-a-discovery-cycle-and-view-reports-for-the-scanner"></a>Ejecutar un ciclo de detección y ver informes del escáner

Use el siguiente procedimiento después de [configurar e instalar el escáner](deploy-scanner-configure-install.md) para obtener una comprensión inicial del contenido.

Realice estos pasos de nuevo según sea necesario cuando cambie el contenido.

1. Inicie un examen en el trabajo de examen de contenido.

    Realice una de las siguientes acciones para iniciar un trabajo de examen de contenido:

    - **Use el portal de cumplimiento Microsoft Purview.**  En el panel **Analizador de protección de la información: trabajos de examen de contenido** , seleccione los trabajos de examen de contenido y, a continuación, seleccione la opción **Examinar ahora** . La opción **Examinar ahora** solo aparece una vez que se selecciona un trabajo de examen de contenido. 
        
    - **Use un comando de PowerShell.** Ejecute `Start-AIPScan` para iniciar el examen.

1. Espere a que el escáner complete su ciclo. El examen se completa cuando el escáner se ha rastreado a través de todos los archivos de los almacenes de datos especificados.

    Realice una de las siguientes acciones para supervisar el progreso del escáner:

    - **Use el portal de cumplimiento Microsoft Purview.**  En el panel **Analizador de protección de la información: trabajos de examen de contenido** , seleccione **Actualizar**.

        Espere hasta que vea los valores de la columna **LAST SCAN RESULTS** y la columna **LAST SCAN (END TIME).**
        
    - **Use un comando de PowerShell.** Ejecute `Get-AIPScannerStatus` para supervisar el cambio de estado.

1. Una vez completado el examen, revise los informes almacenados en el **% directorio *localappdata*%\Microsoft\MSIP\Scanner\Reports**.

    - Los .txt archivos de resumen incluyen el tiempo necesario para examinar, el número de archivos escaneados y cuántos archivos tenían una coincidencia para los tipos de información.

    - Los archivos .csv tienen más detalles para cada archivo. Esta carpeta almacena hasta 60 informes para cada ciclo de examen y todos, excepto el informe más reciente, se comprimen para ayudar a minimizar el espacio en disco necesario. 

        Cuando se completa un examen, se crea un `Summary_<x>.txt` archivo con el resumen del examen.

> [!NOTE]
> Los escáneres envían información de datos recopilada a Microsoft Purview Information Protection cada cinco minutos, para que pueda ver los resultados casi en tiempo real desde el portal de administración. Para obtener más información, consulte [Análisis y informes centrales para Azure Information Protection](/azure/information-protection/reports-aip).
>
> El portal de administración solo muestra información sobre el último examen. Si necesita ver los resultados de los exámenes anteriores, vuelva a los informes almacenados en el equipo del escáner, en la carpeta %*localappdata*%\Microsoft\MSIP\Scanner\Reports.
>

[Las configuraciones iniciales](deploy-scanner-configure-install.md#configure-the-scanner-settings) le indican que establezca los **tipos de información que se detectarán** **solo en Directiva**. Esta configuración significa que solo los archivos que cumplen las condiciones que ha configurado para la clasificación automática se incluyen en los informes detallados.

Si no ve ninguna etiqueta aplicada, compruebe que la configuración de la etiqueta incluye la clasificación automática en lugar de la recomendada, o habilite **Tratar el etiquetado recomendado como automático** (disponible en la versión 2.7.x.x del escáner y versiones posteriores).

Si los resultados siguen sin ser los esperados, es posible que deba volver a configurar las condiciones que especificó para las etiquetas. Si ese es el caso, vuelva a configurar las condiciones según sea necesario y repita este procedimiento hasta que esté satisfecho con los resultados. A continuación, actualice la configuración automáticamente y, opcionalmente, la protección.

### <a name="changing-log-levels-or-locations"></a>Cambio de niveles de registro o ubicaciones

Cambie el nivel de registro mediante el parámetro *ReportLevel* con [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration).

No se puede cambiar la ubicación o el nombre de la carpeta del informe. Si desea almacenar informes en otra ubicación, considere la posibilidad de usar una unión de directorio para la carpeta.

Por ejemplo, use el comando [Mklink](/windows-server/administration/windows-commands/mklink) : `mklink /j D:\Scanner_reports C:\Users\aipscannersvc\AppData\Local\Microsoft\MSIP\Scanner\Reports`

Si ha realizado estos pasos después de una configuración e instalación iniciales, continúe con [Configurar el analizador para aplicar la clasificación y la protección](deploy-scanner-configure-install.md#configure-the-scanner-to-apply-classification-and-protection).

## <a name="stopping-a-scan"></a>Detener un examen

Para detener un examen en ejecución antes de que se complete, use cualquiera de los métodos siguientes:

- **portal de cumplimiento Microsoft Purview.** Seleccione **Detener examen**:

- **Ejecute un comando de PowerShell.** Ejecute el comando siguiente:

    ```PowerShell
    Stop-AIPScan
    ```

## <a name="rescanning-files"></a>Volver a examinar archivos

Para el [primer ciclo de examen](#run-a-discovery-cycle-and-view-reports-for-the-scanner), el analizador inspecciona todos los archivos de los almacenes de datos configurados. Para los exámenes posteriores, solo se inspeccionan los archivos nuevos o modificados.

Es útil volver a inspeccionar todos los archivos cuando desee que los informes incluyan todos los archivos, cuando tenga cambios que quiera aplicar en todos los archivos y cuando el analizador se ejecute en modo de detección.

**Para ejecutar manualmente un reescaneo completo en el portal de cumplimiento Microsoft Purview**:

1. Vaya al panel **Analizador de protección de la información: trabajos de examen de contenido** en el portal de cumplimiento Microsoft Purview.

2. Seleccione el trabajo de examen de contenido de la lista y, a continuación, seleccione la opción **Volver a examinar todos los archivos** :

Cuando se completa un examen completo, el tipo de examen cambia automáticamente a incremental para que, para los exámenes posteriores, solo se examinen de nuevo los archivos nuevos o modificados.

> [!TIP]
> Si ha realizado cambios en el trabajo de [examen de contenido](deploy-scanner-configure-install.md#create-a-content-scan-job), el portal de cumplimiento le pedirá que omita un nuevo análisis completo. Para asegurarse de que se produce el nuevo análisis, asegúrese de seleccionar **No** en el símbolo del sistema que aparece.
>

### <a name="trigger-a-full-rescan-by-modifying-your-settings"></a>Desencadenar un nuevo análisis completo modificando la configuración

Las versiones anteriores del escáner escanean todos los archivos cada vez que el escáner detecta una configuración nueva o cambiada para el etiquetado automático y recomendado. El analizador actualiza automáticamente la directiva cada cuatro horas.

En las versiones del escáner 2.8.85.0 o posteriores, el analizador de protección de la información omite el examen completo para la configuración actualizada para garantizar un rendimiento coherente. Asegúrese de [ejecutar un reescaneo completo manualmente](#rescanning-files) según sea necesario.

Por ejemplo, si ha cambiado la configuración de la **directiva de confidencialidad** de **Aplicar = Desactivado** a **Aplicar = Activado**, asegúrese de ejecutar un nuevo análisis completo para aplicar las etiquetas en todo el contenido.

> [!NOTE]
> En la versión [2.7.101.0](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history#general-availability-versions-that-are-no-longer-supported) del analizador y versiones inferiores, es posible que quiera actualizar la directiva antes de cada cuatro horas, como durante las pruebas. En tales casos, elimine manualmente el contenido del directorio **%LocalAppData%\Microsoft\MSIP\mip\mip\<processname>** y reinicie el servicio Azure Information Protection.
>
> Si también ha cambiado la configuración de cifrado de las etiquetas de confidencialidad, espere 15 minutos más desde que guardó la configuración de cifrado actualizada antes de reiniciar el servicio Azure Information Protection.
>

## <a name="next-steps"></a>Pasos siguientes

También puede usar PowerShell para clasificar y proteger de forma interactiva los archivos del equipo de escritorio. Para obtener más información sobre este y otros escenarios que usan PowerShell, consulte [Uso de PowerShell con el cliente de etiquetado unificado de Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell).
