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
ms.openlocfilehash: 63107c50c081eef65e0a56417845b470cc0a294a
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2022
ms.locfileid: "63449740"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-alertsq-abovefoldlink)

Las **alertas** muestran una lista de alertas que se marcaron desde dispositivos de la red. Las alertas más recientes se muestran en la parte superior de la lista, lo que le ayudará a ver primero las alertas más recientes.

> [!NOTE]
> Las alertas se reducen considerablemente con la investigación automatizada y la corrección, lo que permite a los expertos en operaciones de seguridad centrarse en amenazas más sofisticadas y otras iniciativas de alto valor. Cuando una alerta contiene una entidad compatible para la investigación automatizada (por ejemplo, un archivo) en un dispositivo que tiene un sistema operativo compatible, se puede iniciar una investigación y corrección automatizadas. Para obtener más información sobre las investigaciones automatizadas, vea [Overview of Automated investigations](automated-investigations.md).

Hay varias opciones entre las que puede elegir para personalizar la vista de alertas.

En la navegación superior puede:

- Personalizar columnas para agregar o quitar columnas
- Aplicar filtros
- Mostrar las alertas para una duración determinada como 1 día, 3 días, 1 semana, 30 días y 6 meses
- Exportar la lista de alertas a Excel
- Administrar alertas

:::image type="content" source="images/alerts-filters.png" alt-text="Imagen de lista de alertas" lightbox="images/alerts-filters.png":::

## <a name="sort-and-filter-alerts"></a>Ordenar y filtrar alertas 

Puede aplicar los siguientes filtros para limitar la lista de alertas y obtener una vista más centrada de las alertas.

### <a name="severity"></a>Severity

Puede filtrar las alertas en función de su gravedad.  

|Gravedad de alerta|Descripción|
|---|---|
|Alto <br> (Rojo)|Alertas que se ven comúnmente asociadas con amenazas persistentes avanzadas (APT). Estas alertas indican un alto riesgo debido a la gravedad del daño que pueden causar en los dispositivos. Algunos ejemplos son: actividades de herramientas de robo de credenciales, actividades de ransomware no asociadas con ningún grupo, manipulación de sensores de seguridad o cualquier actividad malintencionada indicativa de un adversario humano.|
|Medio <br> (Naranja)|Alertas de detección y respuesta de puntos de conexión comportamientos posteriores a la infracción que podrían formar parte de una amenaza persistente avanzada (APT). Esto incluye comportamientos observados típicos de fases de ataque, cambios anómalos en el Registro, ejecución de archivos sospechosos, etc. Aunque algunos podrían formar parte de las pruebas de seguridad interna, requiere investigación, ya que también puede ser parte de un ataque avanzado.|
|Bajo <br> (Amarillo)|Alertas sobre amenazas asociadas con malware frecuente. Por ejemplo, herramientas de piratería, herramientas de piratería no malware, como ejecutar comandos de exploración, borrar registros, etc., que a menudo no indican una amenaza avanzada dirigida a la organización. También podría venir de una prueba de herramienta de seguridad aislada por un usuario de la organización.|
|Informativo <br> (Gris)|Alertas que podrían no considerarse nocivas para la red, pero que pueden aumentar el conocimiento de la seguridad de la organización en posibles problemas de seguridad.|

#### <a name="understanding-alert-severity"></a>Descripción de la gravedad de la alerta

Antivirus de Microsoft Defender (Antivirus de Microsoft Defender) y Defender para las gravedades de alerta de extremo son diferentes porque representan distintos ámbitos.

La Antivirus de Microsoft Defender de amenaza representa la gravedad absoluta de la amenaza detectada (malware) y se asigna en función del riesgo potencial para el dispositivo individual, si está infectado.

La gravedad de la alerta defender para el extremo representa la gravedad del comportamiento detectado, el riesgo real para el dispositivo pero, lo que es más importante, el riesgo potencial para la organización.

Por ejemplo:

- La gravedad de una alerta de Defender for Endpoint sobre una amenaza Antivirus de Microsoft Defender detectada que se impidió por completo y no infectó el dispositivo se clasifica como "Informativo" porque no hubo ningún daño real.
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

### <a name="policy"></a>Directiva 

Puede filtrar las alertas en función de las siguientes directivas:

- Actividad desde países o regiones poco frecuentes
- Resultado del envío de administrador completado
- Investigación manual de correo electrónico desencadenada por el administrador
- Investigación de compromiso de usuario desencadenada por el administrador
- Token anómalo 
- Viajes atípicos
- Creación de una regla de reenvío o redirección
- Mensajes de correo electrónico que contienen direcciones URL malintencionadas quitados después de la entrega
- Mensajes de correo electrónico que contienen archivos malintencionados quitados después de la entrega
- Correo electrónico notificado por el usuario como malware o cebo
- Password Spray
- Acción de corrección realizada por el administrador en correos electrónicos, dirección URL o remitente
- Creación de servicios sospechosos 
- Propiedades de inicio de sesión desconocidas

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
