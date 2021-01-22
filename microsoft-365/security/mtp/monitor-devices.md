---
title: Informes de supervisión & dispositivos- Centro de seguridad
description: Describe cómo puede mantener los dispositivos seguros, actualizados y detectar posibles amenazas en su organización
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, dispositivos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930503"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Supervisión e informes de dispositivos en el Centro de seguridad de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Mantenga los dispositivos seguros, actualizados y detecte posibles amenazas en el Centro de seguridad de Microsoft 365.

## <a name="view-device-alerts"></a>Ver alertas de dispositivo

Obtén alertas actualizadas sobre la actividad de infracción y otras amenazas en tus dispositivos desde Microsoft Defender para puntos de conexión (disponible con una licencia E5). El Centro de seguridad de Microsoft 365 supervisa estas alertas de forma eficaz en un nivel alto mediante el flujo de trabajo que prefiera.

### <a name="monitor-high-impact-alerts"></a>Supervisar alertas de alto impacto

Cada alerta de Microsoft Defender para puntos de conexión tiene una gravedad correspondiente (alta, media, baja o informativo). Indica un posible impacto en la red si se deja desatendida.  

Usa la **tarjeta de gravedad de alerta de dispositivo** para centrarse específicamente en las alertas que son más graves y pueden requerir respuesta inmediata. Desde esta tarjeta, puede ver más información en el portal del Centro de seguridad de Microsoft Defender.

![Tarjeta de gravedad de alertas de dispositivo](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Comprender los orígenes de alertas

Microsoft Defender para endpoint aprovecha los datos de una amplia gama de sensores de seguridad y orígenes de inteligencia para generar alertas. Por ejemplo, puede usar información de detección del Antivirus de Microsoft Defender y antimalware de terceros. También puede usar su propia inteligencia de amenazas personalizada proporcionada a través de la API de servicio web.

La **tarjeta de orígenes de detección** de alertas de dispositivo muestra la distribución de alertas por origen. Realizar un seguimiento de la actividad relacionada con determinados orígenes, especialmente los orígenes personalizados. También puedes usar la tarjeta para centrarte en las alertas procedentes de sensores que no están configurados para bloquear automáticamente la actividad malintencionada o los componentes.

![Tarjeta de orígenes de detección de alertas de dispositivo](../../media/device-alert-detection-sources.png)

Desde esta tarjeta, puede ver más información en el portal del Centro de seguridad de Microsoft Defender.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Comprender los tipos de amenazas que desencadenan alertas

Microsoft Defender para endpoint ordena cada alerta en una categoría que representa una determinada etapa de la cadena de ataques o el tipo de componente de amenaza. Por ejemplo, una actividad de amenaza detectada puede clasificarse como "movimiento lateral" para indicar que se ha intentado llegar a otros dispositivos de la red. Es probable que la actividad se haya producido después de que los atacantes obtuvieron una posición inicial. Cuando se detecta, un componente de amenaza puede clasificarse ampliamente como malware o específicamente como un tipo de amenaza específico. Los detalles incluyen ransomware, robo de credenciales u otros tipos de software malintencionado o no deseado.

La **tarjeta categorías de amenazas de** dispositivo muestra la distribución de alertas en estas categorías. Use esta información para identificar la actividad de amenazas, como los intentos de robo de credenciales, que suelen tener un mayor impacto que los intentos de ingeniería social. También puede supervisar amenazas potencialmente destructivas como ransomware.

![Tarjeta de categorías de amenazas de dispositivo](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Supervisar alertas activas

La **tarjeta de estado de alerta** de dispositivo indica el número de alertas que no se han resuelto y que pueden requerir atención. Desde esta tarjeta, puede ver más información en el portal del Centro de seguridad de Microsoft Defender.

![Tarjeta de estado de alerta de dispositivo](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Supervisar la clasificación de alertas resueltas

Al resolver una alerta de Microsoft Defender para puntos de conexión, el personal de seguridad puede especificar si se ha comprobado una alerta como:

* Una alerta real que identifica la actividad de infracción real o los componentes de amenaza
* Una alerta falsa que ha detectado actividad normal incorrectamente

La **tarjeta de clasificación de alertas** de dispositivo muestra si las alertas resueltas se han clasificado como alertas verdaderas o falsas. Desde esta tarjeta, puede ver más información en el portal del Centro de seguridad de Microsoft Defender.

Nota: En algunos casos, la información de clasificación no está disponible para determinadas alertas.

![Tarjeta de clasificación de alertas de dispositivo](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Supervisar la determinación de alertas resueltas

Además de clasificar si una alerta es verdadera o falsa durante la resolución, el personal de seguridad puede proporcionar una determinación. Una determinación indica el tipo de actividad normal o malintencionada que se encontró al validar la alerta.

La **tarjeta de determinación de alertas** de dispositivo muestra la determinación proporcionada para cada alerta.

* **APT:** amenaza persistente avanzada, que indica que la actividad detectada o el componente de amenaza forma parte de una infracción sofisticada diseñada para obtener una posición en la red afectada.  
* **Malware:** código o archivo malintencionado
* **Personal de seguridad:** actividad normal realizada por el personal de seguridad
* **Pruebas de seguridad:** actividad o componentes diseñados para simular amenazas reales y se espera que activen sensores de seguridad y generen alertas
* **Software no deseado:** aplicaciones y otro software que no se consideran malintencionados, pero que infringen la directiva o estándares de uso aceptables.
* **Otros:** cualquier otra determinación que no se encuentra dentro de los tipos proporcionados

Desde esta tarjeta, puede ver más información en el Centro de seguridad de Microsoft Defender.

![Tarjeta de determinación de alertas de dispositivo](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Comprender qué dispositivos están en riesgo

**La protección de** dispositivos muestra el nivel de riesgo para los dispositivos. El nivel de riesgo se basa en factores como el tipo y la gravedad de las alertas en el dispositivo.

![Tarjeta de protección de dispositivos](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Supervisar y notificar el estado de los dispositivos administrados por Intune

Los siguientes informes contienen datos de dispositivos inscritos en Intune. No se incluyen los datos de dispositivos no inscritos. Solo los administradores globales pueden ver estas tarjetas.

Los datos del dispositivo inscritos en Intune incluyen:

* Cumplimiento de dispositivos
* Dispositivos con malware activo
* Tipos de malware en dispositivos
* Malware en dispositivos
* Dispositivos con detecciones de malware
* Usuarios con detecciones de malware

### <a name="monitor-device-compliance"></a>Supervisar el cumplimiento de dispositivos

**El cumplimiento de** dispositivos muestra cuántos dispositivos inscritos en Intune cumplen con las directivas de configuración.

![Tarjeta de cumplimiento de dispositivos](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Detectar dispositivos con detecciones de malware

**Las detecciones de malware de** dispositivo proporcionan el número de dispositivos inscritos en Intune con malware que no se ha resuelto por completo. La falta de resolución puede deberse a acciones pendientes, un reinicio, un examen completo, acciones manuales del usuario o si la acción de corrección no se completó correctamente.

![Tarjeta de detecciones de malware de dispositivo](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Comprender los tipos de malware detectados

**Los tipos de malware en dispositivos** muestran diferentes tipos de malware que se han detectado en dispositivos inscritos en Intune. Puede investigar cada tipo en el Centro de seguridad de Microsoft 365.

![Tipos de malware en tarjetas de dispositivos](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Comprender el malware específico detectado en los dispositivos

**El malware de los** dispositivos proporciona una lista del malware específico detectado en los dispositivos.

![Tarjeta de malware en dispositivos](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Comprender qué dispositivos tienen más malware

**Los dispositivos con detecciones de** malware muestran qué dispositivos tienen más detecciones de malware. en el Centro de seguridad de Microsoft 365, puede investigar si el malware está activo, quién usa el dispositivo y su estado de administración en Intune.

![Dispositivos con tarjeta de detección de malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Comprender qué usuarios tienen dispositivos con más malware

**Los usuarios con detecciones de malware** muestran los usuarios con dispositivos que tenían la mayoría de las detecciones de malware. En el Centro de seguridad de Microsoft 365, puede ver cuántos dispositivos se asignan a cada usuario y más información sobre cada dispositivo y el tipo de malware.

![Usuarios con tarjeta de detección de malware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>Supervisar y administrar la implementación y las detecciones de reglas de reducción de superficie de ataque

Las reglas de Reducción de superficie de ataque [(ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) ayudan a evitar acciones y aplicaciones que suelen usar malware que busca vulnerabilidades de seguridad para infectar dispositivos. Estas reglas controlan cuándo y cómo se pueden ejecutar los archivos ejecutables. Por ejemplo, puede impedir que JavaScript o VBScript inicien un archivo ejecutable descargado, bloqueen llamadas API Win32 de macros de Office o bloqueen procesos que se ejecuten desde unidades USB.

![Tarjeta de reducciones de superficie de ataque](../../media/attack-surface-reduction-rules.png)

La tarjeta **Reglas de reducción de la superficie expuesta a ataques** ofrece información general sobre la implementación de reglas en los dispositivos.

La barra superior de la tarjeta muestra el número total de dispositivos que se encuentran en los siguientes modos de implementación:

* **Modo de bloqueo:** dispositivos con al menos una regla configurada para bloquear la actividad detectada
* **Modo auditoría:** dispositivos sin reglas establecidas para bloquear la actividad detectada, pero tiene al menos una regla configurada para auditar la actividad detectada.  
* **Desactivado:** dispositivos con todas las reglas ASR desactivadas

La parte inferior de esta tarjeta muestra la configuración por regla en los dispositivos. Cada barra indica el número de dispositivos que están configurados para bloquear, auditar o tener la regla completamente desactivada.

### <a name="view-asr-detections"></a>Ver detecciones de ASR

Para ver información detallada sobre las detecciones de reglas ASR en la red, selecciona **Ver** detecciones en la tarjeta de reglas de reducción **de superficie de ataque.** Se **abrirá la pestaña** Detecciones en la página del informe detallado.

![Pestaña Detecciones](../../media/detections-tab.png)

El gráfico de la parte superior de la página muestra las detecciones a lo largo del tiempo apilando las detecciones que se bloquearon o auditó. En la tabla de la parte inferior se muestran las detecciones más recientes. Use la siguiente información de la tabla para comprender la naturaleza de las detecciones:

* **Archivo detectado:** el archivo, normalmente un script o documento, cuyo contenido desencadenó la actividad de ataque sospechosa
* **Regla:** nombre que describe las actividades de ataque que la regla está diseñada para capturar. Leer sobre las reglas ASR existentes
* **Aplicación de** origen: la aplicación que cargó o ejecutó el contenido que desencadena la actividad de ataque sospechosa. Podría ser una aplicación legítima, como un explorador web, una aplicación de Office o una herramienta del sistema como PowerShell
* **Publisher:** el proveedor que publicó la aplicación de origen

### <a name="review-device-asr-rule-settings"></a>Revisar la configuración de la regla ASR del dispositivo

En la página **Informe de reglas de reducción de** superficie de ataque, ve a la **pestaña** Configuración para revisar la configuración de la regla para dispositivos individuales. Selecciona un dispositivo para obtener información detallada sobre si cada regla está en modo de bloqueo, modo auditoría o desactivada por completo.

![Pestaña Configuración](../../media/configuration-tab.png)

Microsoft Intune proporciona funcionalidad de administración para las reglas de ASR. Si quieres actualizar la configuración, selecciona Introducción en **Configurar** dispositivos en la pestaña para abrir la administración de dispositivos en Intune. 

### <a name="exclude-files-from-asr-rules"></a>Excluir archivos de reglas ASR

El Centro de seguridad de Microsoft 365 recopila los nombres de los archivos que puede que desee excluir de las detecciones mediante reglas de reducción de superficie de ataque. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) Al excluir archivos, puedes reducir las detecciones de falsos positivos e implementar con más confianza reglas de reducción de superficie de ataque en modo de bloqueo.

Las exclusiones se administran en Microsoft Intune, pero el Centro de seguridad de Microsoft 365 proporciona una herramienta de análisis que le ayudará a comprender los archivos. Para empezar a recopilar archivos para exclusión, ve a la pestaña Agregar **exclusiones** en la página informe de reglas de **reducción de superficie de** ataque.

>[!NOTE]  
>La herramienta analiza las detecciones por todas las reglas de reducción de superficie de ataque, pero solo algunas [reglas admiten exclusiones.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)

![Pestaña Agregar exclusiones](../../media/add-exclusions-tab.png)

En la tabla se enumeran todos los nombres de archivo detectados por las reglas de reducción de superficie de ataque. Puedes seleccionar archivos para revisar el impacto de excluirlos:

* Número de detecciones menos
* Cuántos dispositivos menos informan de las detecciones

Para obtener una lista de los archivos seleccionados con sus rutas de acceso completas para exclusión, seleccione **Obtener rutas de exclusión.**

Los registros de la regla ASR Bloquear robo de credenciales del subsistema de autoridad de seguridad **local de Windows (lsass.exe)** capturan la aplicación de **origenlsass.exe**. Es un archivo del sistema normal, pero capturado como el archivo detectado. Como resultado, la lista generada de rutas de exclusión incluirá este archivo. Para excluir el archivo que desencadenó esta regla en lugar **delsass.exe,** usa la ruta de acceso a la aplicación de origen en lugar del archivo detectado.

Para localizar la aplicación de [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) origen, ejecute la siguiente consulta de búsqueda avanzada para esta regla específica (identificada por el identificador de regla 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Comprobar los archivos para la exclusión

Antes de excluir un archivo de ASR, te recomendamos que inspecciones el archivo para determinar si realmente no es malintencionado.

Para revisar un archivo, use la página [de información del archivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) en el Centro de seguridad de Microsoft Defender. La página proporciona información sobre la prevalencia y la relación de detección del antivirus VirusTotal. También puede usar la página para enviar el archivo para un análisis detallado.

Para localizar un archivo detectado en el Centro de seguridad de Microsoft Defender, busque todas las detecciones de ASR mediante la siguiente consulta de búsqueda avanzada:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Use **SHA1** o **InitiatingProcessSHA1** en los resultados para buscar el archivo mediante la barra de búsqueda universal en el Centro de seguridad de Microsoft Defender.
