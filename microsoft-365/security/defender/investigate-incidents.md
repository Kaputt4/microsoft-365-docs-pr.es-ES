---
title: Investigar incidentes en Microsoft 365 Defender
description: Analizar incidentes relacionados con dispositivos, usuarios y buzones de correo.
keywords: incidente, incidentes, equipos, dispositivos, usuarios, identidades, correo, correo electrónico, buzón, investigación, gráfico, evidencia
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592101"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Investigar incidentes en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**

- Microsoft 365 Defender

Microsoft 365 Defender agrega todas las alertas, activos, investigaciones y pruebas relacionadas de todos los dispositivos, usuarios y buzones de correo para darle una visión completa de toda la amplitud de un ataque.

Investigue las alertas que afectan a la red, entienda lo que significa y intercale la evidencia asociada con los incidentes para que pueda diseñar un plan de corrección eficaz.

## <a name="investigate-an-incident"></a>Investigar un incidente

1. Seleccione un incidente en la cola incidentes. <BR> Se abre un panel lateral y proporciona una vista previa de información importante, como el estado, la gravedad, las categorías y las entidades afectadas.

    ![Imagen del panel lateral del incidente](../../media/incident-side-panel.png)

2. Seleccione **abrir página de incidente**. <BR> Se abre la página de incidentes donde encontrará más información sobre incidentes, comentarios y acciones, pestañas (información general, alertas, dispositivos, usuarios, investigaciones, evidencias).

3. Revise las alertas, los dispositivos, los usuarios y otras entidades relacionadas con el incidente.

## <a name="incident-overview"></a>Información general del incidente

En la página de información general encontrará un resumen de las instantáneas en las principales cosas que debe tener en cuenta al incidente.

![Imagen de la página información general de incidentes](../../media/incidents-overview.png)

Las categorías de ataque te dan una vista visual y numérica de lo avanzado que ha progresado el ataque en la cadena de eliminación. Al igual que con otros productos de seguridad de Microsoft, Microsoft 365 Defender se alinea con el marco de [CK &trade;&MITRE ATT.](https://attack.mitre.org/)

La sección de ámbito ofrece una lista de los activos que se han visto afectados y que forman parte de este incidente. Si hay información específica sobre este activo, como el nivel de riesgo, la prioridad de investigación, así como cualquier etiqueta en los activos, esto también se mostrará en esta sección.

La escala de tiempo de las alertas proporciona una vista rápida al orden cronológico en el que se han producido las alertas, así como los motivos por los que estos avisos se relacionan con este incidente.

Por último, la sección de evidencia ofrece un resumen de cuántos artefactos diferentes se incluyeron en el incidente y su estado de corrección, por lo que puede identificar de inmediato si se necesita alguna acción al final.

Esta descripción general puede ayudar en la clasificación inicial del incidente al proporcionar información sobre las principales características del incidente que debe tener en cuenta.

## <a name="alerts"></a>Alertas

Puede ver todas las alertas relacionadas con el incidente y otra información sobre ellas, como la gravedad, las entidades que participaron en la alerta, el origen de las alertas (Microsoft Defender para identity, Microsoft Defender para endpoint, Microsoft Defender para Office 365) y el motivo por el que se vincularon.

![Imagen de la página de alertas de incidente](../../media/incident-alerts.png)

De forma predeterminada, los avisos se ordenan cronológicamente, para que pueda ver en primer lugar cómo se ha producido el ataque a lo largo del tiempo. Al hacer clic en cada alerta, se le dirigirá a la página de alerta relevante donde puede llevar a cabo una investigación en profundidad de esa alerta. Obtenga información sobre cómo usar las páginas de alertas y la cola de alertas unificada en [Investigar alertas](investigate-alerts.md)

## <a name="devices"></a>Dispositivos

En la pestaña dispositivos se muestran todos los dispositivos en los que se ven las alertas relacionadas con el incidente.

Al hacer clic en el nombre del equipo en el que se realizó el ataque, es dirigido a la página de su equipo, donde puede ver las alertas que se activaron y los eventos relacionados que se proporcionan para facilitar la investigación.

![Imagen de la pestaña equipos de un incidente](../../media/incident-machines.png)

Seleccionar la pestaña escala de tiempo permite desplazarse por la escala de tiempo de la máquina y ver todos los eventos y comportamientos que se observan en el equipo en orden cronológico, intercalados con las alertas iniciadas.

> [!TIP]
> Puedes realizar exámenes a petición en una página de dispositivo. En el Centro de seguridad de Microsoft 365, elija **Inventario de dispositivos**. Selecciona un dispositivo que tenga alertas y, a continuación, ejecuta un examen antivirus. Las acciones, como los exámenes antivirus, se realiza un seguimiento y están visibles en la **página Inventario de** dispositivos. Para obtener más información, consulta [Ejecutar el examen de Antivirus de Microsoft Defender en dispositivos](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).


## <a name="users"></a>Usuarios

Vea los usuarios que se han identificado como parte de un incidente determinado o que están relacionados con él.

Al hacer clic en el nombre de usuario, se accede a la página de seguridad de la aplicación en la nube del usuario, donde se pueden realizar más investigaciones.

![Imagen de la pestaña usuarios de un incidente](../../media/incident-users.png)

## <a name="mailboxes"></a>Buzones

Investigue los buzones que se han identificado como parte de un incidente o relacionados con él. Para realizar más tareas de investigación, al seleccionar la alerta relacionada con el correo se abrirá Microsoft Defender para Office 365, donde puede realizar acciones de corrección.

![Imagen de la pestaña buzón de un incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Investigaciones

Seleccione **Investigaciones para** ver todas las investigaciones automatizadas desencadenadas por alertas en este incidente. Las investigaciones realizarán acciones de corrección o esperarán a que el analista apruebe las acciones, según cómo haya configurado las investigaciones automatizadas para que se ejecuten en Microsoft Defender para Endpoint y Defender para Office 365.

![Imagen de la pestaña investigaciones de un incidente](../../media/incident-investigations.png)

Seleccione una investigación para ir a la página de detalles de la investigación para obtener toda la información sobre la investigación y el estado de corrección. Si hay acciones pendientes para su aprobación como parte de la investigación, aparecerán en la pestaña Acciones pendientes. Tome medidas como parte de la corrección de incidentes.

## <a name="evidence"></a>Evidencia

Microsoft 365 Defender investiga automáticamente todos los eventos admitidos por los incidentes y las entidades sospechosas de las alertas, lo que proporciona una respuesta automática e información sobre los archivos, procesos, servicios, correos electrónicos y mucho más importantes. Esto permite detectar y bloquear rápidamente posibles amenazas en el incidente.

![Imagen de la pestaña evidencia de un incidente](../../media/incident-evidence.png)

Cada una de las entidades analizadas se marcará con un veredicto (malintencionada, sospechosa, limpia), así como un estado de corrección. Esto le ayuda a comprender el estado de corrección de todo el incidente y cuáles son los siguientes pasos a seguir para solucionarlo.

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Administrar incidentes](manage-incidents.md)

