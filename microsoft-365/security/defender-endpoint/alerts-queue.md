---
title: Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión
description: Obtenga información sobre cómo funcionan las colas de alertas de Microsoft Defender para punto de conexión y cómo ordenar y filtrar listas de alertas.
keywords: alertas, colas, cola de alertas, ordenación, orden, filtro, administración de alertas, nuevas, en curso, resueltas, más recientes, tiempo en cola, gravedad, período de tiempo, alertas de expertos en amenazas de Microsoft
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: article
ms.date: 03/27/2020
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: e9623dbf66826d3654e987ef41ca9006c0548888
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68145807"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)

La **cola Alertas** muestra una lista de alertas marcadas desde dispositivos de la red. De forma predeterminada, la cola muestra las alertas que se han visto en los últimos 30 días en una vista agrupada. Las alertas más recientes se muestran en la parte superior de la lista para ayudarle a ver primero las alertas más recientes.

> [!NOTE]
> Las alertas se reducen significativamente con la investigación y corrección automatizadas, lo que permite a los expertos en operaciones de seguridad centrarse en amenazas más sofisticadas y otras iniciativas de alto valor. Cuando una alerta contiene una entidad admitida para la investigación automatizada (por ejemplo, un archivo) en un dispositivo que tiene un sistema operativo compatible, se puede iniciar una investigación y corrección automatizadas. Para obtener más información sobre las investigaciones automatizadas, consulte [Introducción a las investigaciones automatizadas](automated-investigations.md).

Hay varias opciones entre las que puede elegir para personalizar la vista de alertas.

En la navegación superior, puede hacer lo siguiente:

- Personalización de columnas para agregar o quitar columnas
- Aplicar filtros
- Mostrar las alertas durante una duración determinada, como 1 día, 3 días, 1 semana, 30 días y 6 meses
- Exportación de la lista de alertas a Excel
- Administrar alertas

:::image type="content" source="images/alerts-queue-list.png" alt-text="Página Cola de alertas" lightbox="images/alerts-queue-list.png":::

## <a name="sort-and-filter-alerts"></a>Ordenar y filtrar alertas 

Puede aplicar los siguientes filtros para limitar la lista de alertas y obtener una vista más centrada de las alertas.

### <a name="severity"></a>Severity

Gravedad de la alerta|Descripción
---|---
Alto <br> (Rojo)|Alertas que se suelen ver asociadas a amenazas persistentes avanzadas (APT). Estas alertas indican un alto riesgo debido a la gravedad de los daños que pueden infligir en los dispositivos. Algunos ejemplos son: actividades de herramientas de robo de credenciales, actividades de ransomware no asociadas a ningún grupo, manipulación de sensores de seguridad o cualquier actividad malintencionada que indica un adversario humano.
Mediano <br> (Naranja)|Alertas de comportamientos posteriores a la vulneración y de detección de puntos de conexión que podrían formar parte de una amenaza persistente avanzada (APT). Estos comportamientos incluyen comportamientos observados típicos de las fases de ataque, cambio anómalo del Registro, ejecución de archivos sospechosos, etc. Aunque algunas podrían formar parte de pruebas de seguridad internas, requiere investigación, ya que también podría formar parte de un ataque avanzado.
Bajo <br> (Amarillo)|Alertas sobre amenazas asociadas a malware frecuente. Por ejemplo, herramientas de piratería, herramientas de piratería que no son de malware, como ejecutar comandos de exploración, borrar registros, etc., que a menudo no indican una amenaza avanzada dirigida a la organización. También podría proceder de una prueba de herramientas de seguridad aisladas por parte de un usuario de su organización.
Informativo <br> (Gris)|Alertas que podrían no considerarse perjudiciales para la red, pero que pueden impulsar el reconocimiento de la seguridad de la organización sobre posibles problemas de seguridad.

#### <a name="understanding-alert-severity"></a>Descripción de la gravedad de la alerta

Microsoft Defender gravedad de las alertas de Antivirus y Defender para punto de conexión son diferentes porque representan ámbitos diferentes.

La gravedad de la amenaza Microsoft Defender Antivirus representa la gravedad absoluta de la amenaza detectada (malware) y se asigna en función del riesgo potencial para el dispositivo individual, si está infectado.

La gravedad de la alerta de Defender para punto de conexión representa la gravedad del comportamiento detectado, el riesgo real para el dispositivo pero, lo que es más importante, el riesgo potencial para la organización.

Por ejemplo:

- La gravedad de una alerta de Defender para punto de conexión sobre una amenaza detectada por Microsoft Defender Antivirus que se impidió y no infectó el dispositivo se clasifica como "Informativo" porque no se produjo ningún daño real.
- Una alerta sobre un malware comercial se detectó durante la ejecución, pero bloqueada y corregida por Microsoft Defender Antivirus, se clasifica como "Baja" porque puede haber causado algún daño al dispositivo individual pero no supone ninguna amenaza organizativa.
- Una alerta sobre malware detectado durante la ejecución que puede suponer una amenaza no solo para el dispositivo individual, sino también para la organización, independientemente de si finalmente se bloqueó, puede clasificarse como "Medio" o "Alto".
- Las alertas de comportamiento sospechosas, que no se bloquearon ni corregiron, se clasificarán como "Baja", "Media" o "Alta" siguiendo las mismas consideraciones de amenazas de la organización.

### <a name="status"></a>Estado

Puede elegir filtrar la lista de alertas en función de su estado.

> [!NOTE]
> Si ve un estado de *alerta de tipo de alerta no compatible* , significa que las funcionalidades de investigación automatizada no pueden recoger esa alerta para ejecutar una investigación automatizada. Sin embargo, puede [investigar estas alertas manualmente](../defender/investigate-incidents.md#alerts).

### <a name="categories"></a>Categories

Hemos redefinido las categorías de alertas para que se alineen con las [tácticas de ataque empresariales](https://attack.mitre.org/tactics/enterprise/) en la [matriz de MITRE ATT&CK](https://attack.mitre.org/). Los nuevos nombres de categoría se aplican a todas las alertas nuevas. Las alertas existentes conservarán los nombres de categoría anteriores.

### <a name="service-sources"></a>Orígenes del servicio

Expertos en amenazas de Microsoft los participantes de la versión preliminar ahora pueden filtrar y ver las detecciones del nuevo servicio de búsqueda administrado por expertos en amenazas.

Filtre las alertas en función de los siguientes orígenes de servicio:

- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Microsoft Defender para punto de conexión
- Microsoft 365 Defender
- Microsoft Defender para Office 365
- Gobernanza de aplicaciones
- AAD Identity Protection

> [!NOTE]
> El filtro Antivirus solo aparecerá si los dispositivos usan Microsoft Defender Antivirus como producto antimalware de protección en tiempo real predeterminado.

### <a name="tags"></a>Etiquetas

Puede filtrar las alertas en función de las etiquetas asignadas a las alertas.

### <a name="policy"></a>Policy 

Puede filtrar las alertas en función de las siguientes directivas:

|Origen de detección|Valor de API|
|---|---|
|Sensores de terceros|ThirdPartySensors|
|Antivirus|WindowsDefenderAv|
|Investigación automatizada|AutomatedInvestigation|
|Detección personalizada|CustomDetection|
|TI personalizado|CustomerTI|
|Edr|WindowsDefenderAtp|
|Microsoft 365 Defender|Mtp|
|Microsoft Defender para Office 365|OfficeATP|
|Expertos en amenazas de Microsoft|ThreatExperts|
|SmartScreen|WindowsDefenderSmartScreen|

### <a name="entities"></a>Entidades

Puede filtrar las alertas en función del nombre o el identificador de entidad. 

### <a name="automated-investigation-state"></a>Estado de investigación automatizado

Puede elegir filtrar las alertas en función de su estado de investigación automatizado.



## <a name="related-topics"></a>Temas relacionados

- [Administrar alertas de Microsoft Defender para punto de conexión](manage-alerts.md)
- [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md)
- [Investigación de un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigación de dispositivos en la lista de dispositivos Microsoft Defender para punto de conexión](investigate-machines.md)
- [Investigación de una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigación de un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigación de una cuenta de usuario en Microsoft Defender para punto de conexión](investigate-user.md)
