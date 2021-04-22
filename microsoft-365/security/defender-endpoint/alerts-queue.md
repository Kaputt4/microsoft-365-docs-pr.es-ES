---
title: Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender
description: Obtenga información sobre cómo funcionan las colas de alertas de Microsoft Defender para puntos de conexión y cómo ordenar y filtrar listas de alertas.
keywords: alertas, colas, cola de alertas, ordenar, ordenar, filtrar, administrar alertas, nuevas, en curso, resueltas, más recientes, tiempo en cola, gravedad, período de tiempo, alertas de expertos en amenazas de Microsoft
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
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 48a3ff8dba5bccd62d7d43b295c136a814056a15
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934338"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

La **cola De alertas** muestra una lista de alertas marcadas desde dispositivos de la red. De forma predeterminada, la cola muestra alertas vistas en los últimos 30 días en una vista agrupada. Las alertas más recientes se muestran en la parte superior de la lista, lo que le ayudará a ver primero las alertas más recientes.

> [!NOTE]
> La cola de alertas se reduce considerablemente con la investigación automatizada y la corrección, lo que permite a los expertos en operaciones de seguridad centrarse en amenazas más sofisticadas y otras iniciativas de alto valor. Cuando una alerta contiene una entidad compatible para la investigación automatizada (por ejemplo, un archivo) en un dispositivo que tiene un sistema operativo compatible, se puede iniciar una investigación y corrección automatizadas. Para obtener más información sobre las investigaciones automatizadas, vea [Overview of Automated investigations](automated-investigations.md).

Hay varias opciones entre las que puede elegir para personalizar la vista de cola de alertas. 

En la navegación superior puede:

- Seleccionar vista agrupada o vista de lista
- Personalizar columnas para agregar o quitar columnas 
- Seleccionar los elementos que se mostrarán por página
- Navegar entre páginas
- Aplicar filtros

![Imagen de la cola de alertas](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>Ordenar, filtrar y agrupar la cola de alertas

Puede aplicar los siguientes filtros para limitar la lista de alertas y obtener una vista más centrada de las alertas.

### <a name="severity"></a>Severity

Gravedad de alerta | Descripción
:---|:---
Alto </br>(Rojo) | Alertas que se ven comúnmente asociadas con amenazas persistentes avanzadas (APT). Estas alertas indican un alto riesgo debido a la gravedad del daño que pueden causar en los dispositivos. Algunos ejemplos son: actividades de herramientas de robo de credenciales, actividades de ransomware no asociadas con ningún grupo, manipulación de sensores de seguridad o cualquier actividad malintencionada indicativa de un adversario humano.
Mediano </br>(Naranja) | Alertas de comportamientos de detección de puntos de conexión y respuesta posteriores a la infracción que pueden formar parte de una amenaza persistente avanzada (APT). Esto incluye comportamientos observados típicos de fases de ataque, cambios anómalos en el Registro, ejecución de archivos sospechosos, etc. Aunque algunos podrían formar parte de las pruebas de seguridad interna, requiere investigación, ya que también puede ser parte de un ataque avanzado.
Bajo </br>(Amarillo) | Alertas sobre amenazas asociadas con malware frecuente. Por ejemplo, herramientas de piratería, herramientas de piratería no malware, como ejecutar comandos de exploración, borrar registros, etc., que a menudo no indican una amenaza avanzada dirigida a la organización. También podría venir de una prueba de herramienta de seguridad aislada por un usuario de la organización.
Informativo </br>(Gris) | Alertas que podrían no considerarse nocivas para la red, pero que pueden aumentar el conocimiento de la seguridad de la organización en posibles problemas de seguridad.

#### <a name="understanding-alert-severity"></a>Descripción de la gravedad de la alerta

Las gravedades de alerta de Microsoft Defender Antivirus (Antivirus de Microsoft Defender) y Defender para endpoints son diferentes porque representan distintos ámbitos.

La gravedad de la amenaza antivirus de Microsoft Defender representa la gravedad absoluta de la amenaza detectada (malware) y se asigna en función del riesgo potencial para el dispositivo individual, si está infectado.

La gravedad de la alerta defender para el extremo representa la gravedad del comportamiento detectado, el riesgo real para el dispositivo pero, lo que es más importante, el riesgo potencial para la organización.

Por ejemplo:

- La gravedad de una alerta de Defender for Endpoint sobre un antivirus de Microsoft Defender detectado que se impidió por completo y no infectó el dispositivo se clasifica como "Informativo" porque no hubo ningún daño real.
- Una alerta sobre un malware comercial que se detectó durante la ejecución, pero bloqueada y subsanada por Microsoft Defender AV, se clasifica como "Baja" porque puede haber causado algún daño en el dispositivo individual, pero no representa ninguna amenaza organizativa.
- Una alerta sobre malware detectado durante la ejecución que puede suponer una amenaza no solo para el dispositivo individual, sino para la organización, independientemente de si finalmente se bloqueó, puede clasificarse como "Mediana" o "Alta".
- Las alertas de comportamiento sospechosas, que no se han bloqueado o corregido, se clasificarán como "Baja", "Media" o "Alta" siguiendo las mismas consideraciones de amenazas organizativas.

#### <a name="understanding-alert-categories"></a>Descripción de las categorías de alertas

Hemos redefinido las categorías de alertas para alinearlas con las [tácticas](https://attack.mitre.org/tactics/enterprise/) de ataque empresarial en la matriz DE [ATT de MITRE&CK](https://attack.mitre.org/). Los nuevos nombres de categoría se aplican a todas las alertas nuevas. Las alertas existentes conservarán los nombres de categoría anteriores.

En la tabla siguiente se enumeran las categorías actuales y cómo se asignan generalmente a categorías anteriores. 

| Nueva categoría       | Nombre de categoría api   | Componente o actividad de amenazas detectadas                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Colección           | Colección          | Localización y recopilación de datos para exfiltración                                                                                         |
| Comando y control  | CommandAndControl   | Conexión a una infraestructura de red controlada por atacantes para retransmitir datos o recibir comandos                                          |
| Acceso a credenciales    | CredentialAccess    | Obtener credenciales válidas para extender el control sobre dispositivos y otros recursos de la red                                       |
| Evasión de defensa      | DefenseEvasion      | Evitar controles de seguridad, por ejemplo, desactivar aplicaciones de seguridad, eliminar implantes y ejecutar rootkits                        |
| Descubrimiento            | Descubrimiento           | Recopilación de información sobre dispositivos y recursos importantes, como equipos de administrador, controladores de dominio y servidores de archivos  |
| Ejecución            | Ejecución           | Iniciar herramientas de atacante y código malintencionado, incluidos los RAT y puertas traseras                                                             |
| Exfiltración         | Exfiltración        | Extraer datos de la red a una ubicación externa controlada por atacantes                                                         |
| Exploit              | Exploit             | Código de vulnerabilidad y posible actividad de explotación                                                                                       |
| Acceso inicial       | InitialAccess       | Obtener una entrada inicial a la red de destino, que suele implicar la suposición de contraseñas, vulnerabilidades de seguridad o correos electrónicos de suplantación de identidad                      |
| Movimiento lateral     | LateralMovement     | Mover entre dispositivos de la red de destino para alcanzar recursos críticos o obtener persistencia de red                                |
| Malware              | Malware             | Puertas traseras, troyanos y otros tipos de código malintencionado                                                                                 |
| Persistencia          | Persistencia         | Creación de puntos de extensibilidad de inicio automático (ASEP) para permanecer activo y sobrevivir a los reinicios del sistema                                        |
| Escalamiento de privilegios | PrivilegeEscalation | Obtener niveles de permisos más altos para el código ejecutándose en el contexto de un proceso o cuenta con privilegios                         |
| Ransomware           | Ransomware          | Malware que cifra archivos y extorsiona el pago para restaurar el acceso                                                                     |
| Actividad sospechosa  | SuspiciousActivity  | Actividad atípica que podría ser actividad de malware o parte de un ataque                                                                 |
| Software no deseado    | UnwantedSoftware    | Aplicaciones y aplicaciones de baja reputación que afectan a la productividad y a la experiencia del usuario; detectados como aplicaciones potencialmente no deseadas (PUA) |

### <a name="status"></a>Estado

Puede elegir limitar la lista de alertas en función de su estado.

### <a name="investigation-state"></a>Estado de investigación

Corresponde al estado de investigación automatizada.

### <a name="category"></a>Categoría

Puede elegir filtrar la cola para mostrar tipos específicos de actividad malintencionada.

### <a name="assigned-to"></a>Asignado a

Puede elegir entre mostrar las alertas que se le han asignado o la automatización.

### <a name="detection-source"></a>Origen de detección

Seleccione el origen que desencadenó la detección de alertas. Los participantes de vista previa de Microsoft Threat Experts ahora pueden filtrar y ver detecciones desde el nuevo servicio de búsqueda administrado por expertos en amenazas.

>[!NOTE]
>El filtro Antivirus solo aparecerá si los dispositivos usan Antivirus de Microsoft Defender como el producto antimalware de protección en tiempo real predeterminado.

| Origen de detección                  | Valor de API                  |
|-----------------------------------|----------------------------|
| Sensores de terceros                 | ThirdPartySensors          |
| Antivirus                         | WindowsDefenderAv          |
| Investigación automatizada           | AutomatedInvestigation     |
| Detección personalizada                  | CustomDetection            |
| TI personalizada                         | CustomerTI                 |
| EDR                               | WindowsDefenderAtp         |
| Microsoft 365 Defender            | MTP                        |
| Microsoft Defender para Office 365 | OfficeATP                  |
| Expertos en amenazas de Microsoft          | ThreatExperts              |
| SmartScreen                       | WindowsDefenderSmartScreen |

### <a name="os-platform"></a>Plataforma del sistema operativo

Limite la vista de cola de alertas seleccionando la plataforma del sistema operativo que le interesa investigar.

### <a name="device-group"></a>Grupo de dispositivos

Si tienes grupos de dispositivos específicos que te interesan comprobar, puedes seleccionar los grupos para limitar la vista de cola de alertas. 

### <a name="associated-threat"></a>Amenaza asociada

Use este filtro para centrarse en las alertas relacionadas con amenazas de perfil alto. Puede ver la lista completa de amenazas de alto perfil en [Análisis de amenazas.](threat-analytics.md)

## <a name="related-topics"></a>Temas relacionados

- [Administrar alertas de Microsoft Defender para puntos de conexión](manage-alerts.md)
- [Investigar alertas de punto de conexión de Microsoft Defender](investigate-alerts.md)
- [Investigar un archivo asociado a una alerta de Microsoft Defender para punto de conexión](investigate-files.md)
- [Investigar dispositivos en la lista Microsoft Defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigar una dirección IP asociada a una alerta de Microsoft Defender para punto de conexión](investigate-ip.md)
- [Investigar un dominio asociado a una alerta de Microsoft Defender para punto de conexión](investigate-domain.md)
- [Investigar una cuenta de usuario en Microsoft Defender para endpoint](investigate-user.md)
