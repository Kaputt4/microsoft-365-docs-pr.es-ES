---
title: Supervisión de dispositivos & el centro de seguridad de informes
description: Describe cómo puede mantener los dispositivos protegidos, actualizarse y detectar posibles amenazas en la organización.
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, monitor, informe, dispositivos
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9b84ca774e1b9bd0bca51b8ee21f6a06f2fde5b4
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430626"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Supervisión y generación de informes de dispositivos en el centro de seguridad 365 de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Mantenga los dispositivos protegidos, actualizados y detecte posibles amenazas en el centro de seguridad de Microsoft 365.

## <a name="view-device-alerts"></a>Ver alertas de dispositivos

Obtén las alertas actualizadas sobre la actividad de infracciones y otras amenazas en tus dispositivos de ATP de Microsoft defender (disponible con una licencia E5). El centro de seguridad 365 de Microsoft supervisa con eficacia estas alertas en un nivel alto usando el flujo de trabajo preferido.

### <a name="monitor-high-impact-alerts"></a>Supervisar alertas de alto impacto

Cada alerta de ATP de Microsoft defender tiene una gravedad correspondiente (alta, media, baja o informativa). Indica un posible impacto en la red si se deja desatendida.  

Use la tarjeta de **gravedad de alertas de dispositivos** para centrarse específicamente en las alertas más graves y que puedan requerir respuesta inmediata. Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Microsoft defender.

![Tarjeta de gravedad de alertas de dispositivos](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Comprender los orígenes de las alertas

ATP de Microsoft defender aprovecha los datos de una amplia gama de sensores de seguridad y orígenes de inteligencia para generar alertas. Por ejemplo, puede usar la información de detección de antivirus de Microsoft defender y antimalware de terceros. También puede usar su propia inteligencia de amenazas personalizada que se proporciona a través de la API del servicio Web.

La tarjeta orígenes de **detección de alertas de dispositivo** muestra la distribución de las alertas por origen. Realizar un seguimiento de la actividad relacionada con determinados orígenes, especialmente con los orígenes personalizados. También puede usar la tarjeta para centrarse en las alertas procedentes de sensores que no están configurados para bloquear automáticamente la actividad o los componentes malintencionados.

![Tarjeta de origen de detección de alertas de dispositivo](../../media/device-alert-detection-sources.png)

Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Microsoft defender.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Descripción de los tipos de amenazas que desencadenan alertas

Microsoft defender ATP ordena cada alerta en una categoría que representa una determinada fase en la cadena de ataques o en el tipo de componente de amenaza. Por ejemplo, una actividad de amenaza detectada se puede clasificar como "movimiento lateral" para indicar que se ha intentado llegar a otros dispositivos de la red. Es probable que se haya producido una actividad después de que los atacantes hayan obtenido un primer apoyo. Cuando se detecta, un componente de amenaza puede clasificarse ampliamente como malware o específicamente como un tipo de amenaza específico. Los detalles específicos incluyen ransomware, robo de credenciales u otros tipos de software malintencionado o no deseado.

La tarjeta de **categorías de amenaza de dispositivo** muestra la distribución de las alertas a estas categorías. Use esta información para identificar la actividad de amenazas, como los intentos de robo de credenciales, que suelen tener un mayor impacto que los intentos de ingeniería social. También puede supervisar amenazas potencialmente destructivas como ransomware.

![Tarjeta de categorías de amenaza de dispositivo](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Supervisar alertas activas

La tarjeta de **Estado de alerta de dispositivo** indica el número de alertas que no se han resuelto y que pueden requerir atención. Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Microsoft defender.

![Tarjeta de estado de alerta de dispositivo](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Supervisión de la clasificación de las alertas resueltas

Al resolver una alerta de ATP de Microsoft defender, el personal de seguridad puede especificar si se ha verificado una alerta como:

* Una alerta verdadera que identifica la actividad de infracciones real o los componentes de amenazas
* Una alerta falsa que ha detectado incorrectamente actividad normal

La tarjeta de **clasificación de alertas de dispositivo** muestra si las alertas resueltas se clasificaron como verdaderas o falsas alertas. Desde esta tarjeta, puede ver más información en el portal del centro de seguridad de Microsoft defender.

Nota: en algunos casos, la información de clasificación no está disponible para determinadas alertas.

![Tarjeta de clasificación de alertas de dispositivo](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Determinación de la determinación de alertas resueltas

Además de clasificar si una alerta es verdadera o falsa durante la resolución, el personal de seguridad puede proporcionar una determinación. Una determinación indica el tipo de actividad normal o malintencionada que se encontró al validar la alerta.

La tarjeta de **determinación de alertas de dispositivo** muestra la determinación proporcionada para cada alerta.

* **Apt**: amenaza persistente avanzada, que indica que el componente de amenaza o actividad detectada forma parte de una infracción compleja diseñada para llegar a la red afectada  
* **Malware**: archivo malintencionado o código
* **Personal de seguridad**: actividad normal realizada por el personal de seguridad
* **Pruebas de seguridad**: actividad o componentes diseñados para simular amenazas reales y que se espera que desencadenen sensores de seguridad y generen alertas
* **Software no deseado**: aplicaciones y otro software que no se consideran malintencionados pero que infringen las directivas o los estándares de uso aceptables
* **Otros**: cualquier otra determinación que no se incluya en los tipos proporcionados

Desde esta tarjeta, puede ver más información en el centro de seguridad de Microsoft defender.

![Tarjeta de determinación de alertas de dispositivo](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Comprender qué dispositivos están expuestos

La **protección de dispositivos** muestra el nivel de riesgo para los dispositivos. El nivel de riesgo se basa en factores como el tipo y la gravedad de las alertas en el dispositivo.

![Tarjeta de protección de dispositivos](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Supervisión e informes del estado de los dispositivos administrados por Intune

Los siguientes informes contienen datos de los dispositivos inscritos en Intune. No se incluyen los datos de los dispositivos que no están en la inscripción. Solo los administradores globales pueden ver estas tarjetas.

Los datos de dispositivos inscritos de Intune incluyen:

* Cumplimiento de dispositivos
* Dispositivos con malware activo
* Tipos de malware en dispositivos
* Malware en dispositivos
* Dispositivos con detecciones de malware
* Usuarios con detecciones de malware

### <a name="monitor-device-compliance"></a>Supervisar el cumplimiento de dispositivos

El **cumplimiento de dispositivos** muestra el número de dispositivos inscritos en Intune compatibles con las directivas de configuración.

![Tarjeta de cumplimiento de dispositivos](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Detectar dispositivos con detecciones de malware

Las **detecciones de malware de dispositivos** proporcionan el número de dispositivos inscritos de Intune con malware que no se han resuelto completamente. La falta de resolución puede deberse a acciones pendientes, un reinicio, un análisis completo, acciones manuales del usuario o si la acción de corrección no se completó correctamente.

![Tarjeta de detección de malware de dispositivo](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Descripción de los tipos de malware detectados

**Tipos de malware en dispositivos** muestra distintos tipos de malware que se han detectado en los dispositivos inscritos en Intune. Puede investigar cada tipo del centro de seguridad 365 de Microsoft.

![Tipos de malware en la tarjeta de dispositivos](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Comprender el malware específico detectado en los dispositivos

**Malware on Devices** proporciona una lista del malware específico detectado en los dispositivos.

![Malware en tarjeta de dispositivos](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Conocer los dispositivos que tienen más malware

Los **dispositivos con detecciones de malware** muestran los dispositivos que tienen más detecciones de malware. en el centro de seguridad de Microsoft 365, puede investigar si el malware está activo, quién usa el dispositivo y su estado de administración en Intune.

![Tarjeta de detección de dispositivos con malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Comprender qué usuarios tienen dispositivos con más malware

**Los usuarios con detecciones de malware** muestran a los usuarios con dispositivos que han detectado más malware. En el centro de seguridad 365 de Microsoft, puede ver cuántos dispositivos se asignan a cada usuario y más información acerca de cada dispositivo y el tipo de malware.

![Usuarios con tarjeta de detección de malware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>Supervisar y administrar la implementación y detección de la regla de reducción de superficie de ataques

[Las reglas de reducción de superficie de ataques (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) ayudan a evitar acciones y aplicaciones que normalmente usan los ataques de malware para infectar dispositivos. Estas reglas controlan cuándo y cómo se pueden ejecutar los archivos ejecutables. Por ejemplo, puede impedir que JavaScript o VBScript inicien un archivo ejecutable descargado, bloqueen llamadas API Win32 de macros de Office o bloqueen procesos que se ejecuten desde unidades USB.

![Tarjeta de reducción de superficie de ataques](../../media/attack-surface-reduction-rules.png)

La tarjeta **Reglas de reducción de la superficie expuesta a ataques** ofrece información general sobre la implementación de reglas en los dispositivos.

La barra superior de la tarjeta muestra el número total de dispositivos que se encuentran en los siguientes modos de implementación:

* **Modo de bloqueo**: dispositivos con al menos una regla configurada para bloquear la actividad detectada
* **Modo auditoría**: dispositivos sin reglas establecidas para bloquear la actividad detectada, pero tiene al menos una regla establecida para auditar la actividad detectada  
* **Desactivado: dispositivos**con todas las reglas de ASR desactivadas

La parte inferior de esta tarjeta muestra la configuración por regla en los dispositivos. Cada barra indica el número de dispositivos que están configurados para bloquear, la detección de auditoría o la desactivación de la regla por completo.

### <a name="view-asr-detections"></a>Ver detecciones de ASR

Para ver información detallada sobre las detecciones de reglas de ASR en la red, seleccione **Ver detecciones** en la tarjeta de **reglas de reducción de superficie de ataques** . Se abrirá la pestaña **detecciones** de la página informe detallado.

![Pestaña detecciones](../../media/detections-tab.png)

El gráfico de la parte superior de la página muestra las detecciones con detecciones de agrupamiento de tiempo que se bloquearon o auditaron. En la tabla de la parte inferior se muestran las detecciones más recientes. Use la siguiente información de la tabla para comprender la naturaleza de las detecciones:

* **Archivo detectado**: el archivo, normalmente un script o un documento, cuyo contenido activó la actividad de ataque sospechoso
* **Regla**: nombre que describe las actividades de ataque para las que se ha diseñado la regla. Leer acerca de las reglas de ASR existentes
* **Aplicación de origen**: aplicación que ha cargado o ejecutado contenido que desencadena la actividad de ataque sospechoso. Puede ser una aplicación legítima, como un explorador Web, una aplicación de Office o una herramienta del sistema como PowerShell.
* **Publisher**: el proveedor que liberó la aplicación de origen

### <a name="review-device-asr-rule-settings"></a>Revisar la configuración de la regla de ASR del dispositivo

En la página informe de **reglas de reducción de superficie de ataques** , vaya a la ficha de **configuración** para revisar la configuración de las reglas para dispositivos individuales. Seleccione un dispositivo para obtener información detallada acerca de si cada regla está en modo de bloqueo, modo de auditoría o apagado por completo.

![Ficha Configuración](../../media/configuration-tab.png)

Microsoft Intune proporciona funciones de administración para las reglas de ASR. Si desea actualizar la configuración **, seleccione introducción** a **configurar dispositivos** en la ficha para abrir Administración de dispositivos en Intune.

### <a name="exclude-files-from-asr-rules"></a>Excluir archivos de las reglas de ASR

El centro de seguridad 365 de Microsoft recopila los nombres de los [archivos que puede que desee excluir](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) de las detecciones mediante las reglas de reducción de la superficie de ataques. Al excluir archivos, puede reducir las detecciones de falsos positivos y implementar con mayor confianza las reglas de reducción de superficie de ataques en el modo de bloqueo.

Las exclusiones se administran en Microsoft Intune, pero el centro de seguridad de Microsoft 365 proporciona una herramienta de análisis para ayudarle a comprender los archivos. Para iniciar la recopilación de archivos para su exclusión, vaya a la pestaña **agregar exclusiones** en la página del informe **reglas de reducción de superficie de ataques** .

>[!NOTE]  
>La herramienta analiza las detecciones por todas las reglas de reducción de la superficie de ataque, pero [solo algunas reglas admiten exclusiones](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).

![Ficha agregar exclusiones](../../media/add-exclusions-tab.png)

En la tabla se enumeran todos los nombres de archivo detectados por las reglas de reducción de la superficie de ataques. Puede seleccionar archivos para revisar el impacto de excluirlos:

* El número de detecciones
* El número de dispositivos que informan sobre las detecciones

Para obtener una lista de los archivos seleccionados con todas las rutas de acceso para la exclusión, seleccione **obtener rutas de exclusión**.

Registros para la regla de **protección contra credenciales de bloqueo de las credenciales de ASR desde el subsistema de la autoridad de seguridad local de Windows (lsass.exe)** capturar la aplicación de origen **lsass.exe**. Es un archivo de sistema normal, pero se captura como el archivo detectado. Como resultado, la lista generada de rutas de exclusión incluirá este archivo. Para excluir el archivo que desencadenó esta regla en lugar de **lsass.exe**, use la ruta de acceso a la aplicación de origen en lugar del archivo detectado.

Para encontrar la aplicación de origen, ejecute la siguiente [consulta de búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) para esta regla específica (identificada por el identificador de regla 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Comprobar archivos para su exclusión

Antes de excluir un archivo de ASR, le recomendamos que inspeccione el archivo para determinar si realmente no es malintencionado.

Para revisar un archivo, use la [Página de información del archivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) en el centro de seguridad de Microsoft defender. La página proporciona información sobre la prevalencia y la relación de detección de virus VirusTotal. También puede usar la página para enviar el archivo para un análisis detallado.

Para buscar un archivo detectado en el centro de seguridad de Microsoft defender, busque todas las detecciones de ASR mediante la siguiente consulta de búsqueda avanzada:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Use **SHA1** o **InitiatingProcessSHA1** en los resultados para buscar el archivo mediante la barra de búsqueda universal en el centro de seguridad de Microsoft defender.
