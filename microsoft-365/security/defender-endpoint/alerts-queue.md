---
title: Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión
description: Obtenga información sobre cómo funcionan las colas de alertas de Microsoft Defender para puntos de conexión y cómo ordenar y filtrar listas de alertas.
keywords: alertas, colas, cola de alertas, ordenar, ordenar, filtrar, administrar alertas, nuevas, en curso, resueltas, más recientes, tiempo en cola, gravedad, período de tiempo, alertas de expertos en amenazas de Microsoft
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 0d6b012d2e3dbe6778c8d9c70552cf24427f8a3d
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472053"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)

La **cola De alertas** muestra una lista de alertas marcadas desde dispositivos de la red. De forma predeterminada, la cola muestra alertas vistas en los últimos 30 días en una vista agrupada. Las alertas más recientes se muestran en la parte superior de la lista, lo que le ayudará a ver primero las alertas más recientes.

> [!NOTE]
> Las alertas se reducen considerablemente con la investigación automatizada y la corrección, lo que permite a los expertos en operaciones de seguridad centrarse en amenazas más sofisticadas y otras iniciativas de alto valor. Cuando una alerta contiene una entidad compatible para la investigación automatizada (por ejemplo, un archivo) en un dispositivo que tiene un sistema operativo compatible, se puede iniciar una investigación y corrección automatizadas. Para obtener más información sobre las investigaciones automatizadas, vea [Overview of Automated investigations](automated-investigations.md).

Hay varias opciones entre las que puede elegir para personalizar la vista de alertas.

En la navegación superior puede:

- Personalizar columnas para agregar o quitar columnas
- Aplicar filtros
- Mostrar las alertas para una duración determinada como 1 día, 3 días, 1 semana, 30 días y 6 meses
- Exportar la lista de alertas a Excel
- Administrar alertas

:::image type="content" source="images/alerts-queue-list.png" alt-text="La página Cola de alertas" lightbox="images/alerts-queue-list.png":::

## <a name="sort-and-filter-alerts"></a>Ordenar y filtrar alertas 

Puede aplicar los siguientes filtros para limitar la lista de alertas y obtener una vista más centrada de las alertas.

### <a name="severity"></a>Severity

Gravedad de alerta|Descripción
---|---
Alto <br> (Rojo)|Alertas que se ven comúnmente asociadas con amenazas persistentes avanzadas (APT). Estas alertas indican un alto riesgo debido a la gravedad del daño que pueden causar en los dispositivos. Algunos ejemplos son: actividades de herramientas de robo de credenciales, actividades de ransomware no asociadas con ningún grupo, manipulación de sensores de seguridad o cualquier actividad malintencionada indicativa de un adversario humano.
Mediano <br> (Naranja)|Alertas de detección y respuesta de puntos de conexión comportamientos posteriores a la infracción que podrían formar parte de una amenaza persistente avanzada (APT). Estos comportamientos incluyen comportamientos observados típicos de fases de ataque, cambios anómalos en el Registro, ejecución de archivos sospechosos, etc. Aunque algunos podrían formar parte de las pruebas de seguridad interna, requiere investigación, ya que también puede ser parte de un ataque avanzado.
Bajo <br> (Amarillo)|Alertas sobre amenazas asociadas con malware frecuente. Por ejemplo, herramientas de piratería, herramientas de piratería no malware, como ejecutar comandos de exploración, borrar registros, etc., que a menudo no indican una amenaza avanzada dirigida a la organización. También podría venir de una prueba de herramienta de seguridad aislada por un usuario de la organización.
Informativo <br> (Gris)|Alertas que podrían no considerarse nocivas para la red, pero que pueden aumentar el conocimiento de la seguridad de la organización en posibles problemas de seguridad.

#### <a name="understanding-alert-severity"></a>Descripción de la gravedad de la alerta

Antivirus de Microsoft Defender (Antivirus de Microsoft Defender) y Defender para las gravedades de alerta de extremo son diferentes porque representan distintos ámbitos.

La Antivirus de Microsoft Defender de amenaza representa la gravedad absoluta de la amenaza detectada (malware) y se asigna en función del riesgo potencial para el dispositivo individual, si está infectado.

La gravedad de la alerta defender para el extremo representa la gravedad del comportamiento detectado, el riesgo real para el dispositivo pero, lo que es más importante, el riesgo potencial para la organización.

Por ejemplo:

- La gravedad de una alerta de Defender for Endpoint sobre una amenaza Antivirus de Microsoft Defender detectada que se evitó y no infectó el dispositivo se clasifica como "Informativo" porque no hubo ningún daño real.
- Una alerta sobre un malware comercial que se detectó durante la ejecución, pero bloqueada y subsanada por Microsoft Defender AV, se clasifica como "Baja" porque puede haber causado algún daño en el dispositivo individual, pero no representa ninguna amenaza organizativa.
- Una alerta sobre malware detectado durante la ejecución que puede suponer una amenaza no solo para el dispositivo individual, sino para la organización, independientemente de si finalmente se bloqueó, puede clasificarse como "Mediana" o "Alta".
- Las alertas de comportamiento sospechosas, que no se han bloqueado o corregido, se clasificarán como "Baja", "Media" o "Alta" siguiendo las mismas consideraciones de amenazas organizativas.

### <a name="status"></a>Estado

Puede elegir filtrar la lista de alertas en función de su estado.

### <a name="categories"></a>Categorías

Hemos redefinido las categorías de alertas para alinearlas con las [tácticas](https://attack.mitre.org/tactics/enterprise/) de ataque empresarial en la [matriz DE ATT&MITRE](https://attack.mitre.org/). Los nuevos nombres de categoría se aplican a todas las alertas nuevas. Las alertas existentes conservarán los nombres de categoría anteriores.

### <a name="service-sources"></a>Orígenes del servicio

Expertos en amenazas de Microsoft los participantes de vista previa ahora pueden filtrar y ver las detecciones del nuevo servicio de búsqueda administrado por expertos en amenazas.

Filtre las alertas en función de los siguientes orígenes de servicio:

- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Microsoft Defender para punto de conexión
- Microsoft 365 Defender
- Microsoft Defender para Office 365
- Gobierno de aplicaciones
- AAD identity protection

> [!NOTE]
> El filtro Antivirus solo aparecerá si los dispositivos usan Antivirus de Microsoft Defender como el producto antimalware de protección en tiempo real predeterminado.

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
|TI personalizada|CustomerTI|
|EDR|WindowsDefenderAtp|
|Microsoft 365 Defender|MTP|
|Microsoft Defender para Office 365|OfficeATP|
|Expertos en amenazas de Microsoft|ThreatExperts|
|SmartScreen|WindowsDefenderSmartScreen|

### <a name="entities"></a>Entidades

Puede filtrar las alertas según el nombre de la entidad o el identificador. 

### <a name="automated-investigation-state"></a>Estado de investigación automatizada

Puede elegir filtrar las alertas en función de su estado de investigación automatizada.



## <a name="related-topics"></a>Temas relacionados

- [Administrar alertas de Microsoft Defender para puntos de conexión](manage-alerts.md)
- [Investigar alertas de punto de conexión de Microsoft Defender](investigate-alerts.md)
- [Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigar una cuenta de usuario en Microsoft Defender para endpoint](investigate-user.md)
