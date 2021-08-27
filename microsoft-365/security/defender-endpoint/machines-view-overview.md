---
title: Ver y organizar la lista de dispositivos de Microsoft Defender para endpoints
description: Obtenga información sobre las características disponibles que puede usar en la lista dispositivos, como ordenar, filtrar y exportar la lista para mejorar las investigaciones.
keywords: sort, filter, export, csv, device name, domain, last seen, internal IP, health state, active alerts, active malware detections, threat category, review alerts, network, connection, malware, type, password stealer, ransomware, exploit, threat, general malware, unwanted software
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 993516c20629ddf4466325c547cd9208440dc41d
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573924"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>Ver y organizar la lista de Microsoft Defender para dispositivos de punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-machinesview-abovefoldlink)

La **lista Dispositivos** muestra una lista de los dispositivos de la red donde se generaron alertas. De forma predeterminada, la cola muestra los dispositivos vistos en los últimos 30 días.  

De un vistazo verá información como dominio, nivel de riesgo, plataforma del sistema operativo y otros detalles para facilitar la identificación de los dispositivos más en riesgo.

Hay varias opciones entre las que puedes elegir para personalizar la vista de lista de dispositivos. En la navegación superior puede:

- Agregar o quitar columnas
- Exportar toda la lista en formato CSV
- Seleccionar el número de elementos que se mostrarán por página
- Aplicar filtros

Durante el proceso de incorporación, la lista **de** dispositivos se rellena gradualmente con dispositivos a medida que comienzan a informar de los datos del sensor. Use esta vista para realizar un seguimiento de los puntos de conexión incorporados a medida que se en línea o descargue la lista completa de puntos de conexión como un archivo CSV para el análisis sin conexión.

>[!NOTE]
> Si exportas la lista de dispositivos, contendrá todos los dispositivos de tu organización. Puede tardar mucho tiempo en descargarse, según el tamaño de la organización. Al exportar la lista en formato CSV, se muestran los datos sin filtrar. El archivo CSV incluirá todos los dispositivos de la organización, independientemente de cualquier filtrado aplicado en la vista en sí.

![Imagen de la lista de dispositivos con lista de dispositivos.](images/device-inventory.png)

## <a name="sort-and-filter-the-device-list"></a>Ordenar y filtrar la lista de dispositivos

Puede aplicar los siguientes filtros para limitar la lista de alertas y obtener una vista más centrada.

### <a name="device-name"></a>Nombre del dispositivo

Selecciona el nombre del dispositivo que te interesa investigar.

### <a name="domain"></a>Dominio

Seleccione el dominio que le interesa investigar.

### <a name="risk-level"></a>Nivel de riesgo

El nivel de riesgo refleja la evaluación general del riesgo del dispositivo en función de una combinación de factores, incluidos los tipos y la gravedad de las alertas activas en el dispositivo. Resolver alertas activas, aprobar actividades de corrección y suprimir alertas posteriores puede reducir el nivel de riesgo.

### <a name="exposure-level"></a>Nivel de exposición

El nivel de exposición refleja la exposición actual del dispositivo en función del impacto acumulado de sus recomendaciones de seguridad pendientes. Los niveles posibles son bajos, medianos y altos. Una exposición baja significa que los dispositivos son menos vulnerables a la explotación.

Si el nivel de exposición indica "No hay datos disponibles", hay algunas razones por las que esto puede ser así:

- El dispositivo dejó de informar durante más de 30 días. En ese caso, se considera inactivo y no se calcula la exposición.
- El sistema operativo del dispositivo no es compatible: consulta [requisitos mínimos para Microsoft Defender para endpoint](minimum-requirements.md).
- Dispositivo con agente obsoleto (poco probable).

### <a name="os-platform"></a>Plataforma del sistema operativo

Seleccione solo las plataformas del sistema operativo que le interesa investigar.

### <a name="windows-10-versions"></a>Windows 10 versiones anteriores

Seleccione solo las Windows 10 que está interesado en investigar.

### <a name="health-state"></a>Estado

Filtre por los siguientes estados de estado del dispositivo:

- **Activo:** dispositivos que informan activamente de los datos del sensor al servicio.
- **Inactivo:** dispositivos que han dejado de enviar señales durante más de 7 días.
- **Configuración errónea:** dispositivos que tienen comunicaciones deficientes con el servicio o que no pueden enviar datos del sensor. Los dispositivos mal configurados se pueden clasificar en:
  - Sin datos del sensor
  - Comunicaciones deficientes

  Para obtener más información sobre cómo solucionar problemas en dispositivos mal configurados, consulte [Fix unhealthy sensors](fix-unhealthy-sensors.md).

### <a name="onboarding-status"></a>Estado de incorporación

El estado de incorporación indica si el dispositivo está incorporado actualmente a Microsoft Defender para Endpoint o no. Puede filtrar por los siguientes estados:

- **Incorporado:** el punto de conexión se incorpora a Microsoft Defender para endpoint.

- **Se puede incorporar:** el punto de conexión se descubrió en la red como un dispositivo compatible, pero no está incorporado actualmente. Microsoft recomienda encarecidamente la incorporación de estos dispositivos.

- **No compatible:** el punto de conexión se ha detectado en la red, pero Microsoft Defender no admite endpoint.

- **Información insuficiente:** el sistema no pudo determinar la compatibilidad del dispositivo.

### <a name="last-device-update"></a>Última actualización del dispositivo

Filtra la vista en función de cuándo se actualizó por última vez el dispositivo.

### <a name="first-seen"></a>Primera vista

Filtra la vista en función del momento en que el dispositivo se vio por primera vez en la red o cuando el sensor de Microsoft Defender para endpoints lo informó por primera vez.

### <a name="tags"></a>Etiquetas

Filtre la lista en función de la agrupación y el etiquetado que haya agregado a dispositivos individuales. Consulta [Crear y administrar etiquetas de dispositivo.](machine-tags.md)

## <a name="related-topics"></a>Temas relacionados

- [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md)
