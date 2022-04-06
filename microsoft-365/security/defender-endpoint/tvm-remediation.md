---
title: Corregir vulnerabilidades con Administración de amenazas y vulnerabilidades
description: Corrija las debilidades de seguridad detectadas a través de recomendaciones de seguridad y cree excepciones si es necesario, en Administración de amenazas y vulnerabilidades.
keywords: Corrección de Tvm de Microsoft Defender para Endpoint, Microsoft Defender para Endpoint tvm, Administración de amenazas y vulnerabilidades, & administración de vulnerabilidades amenazas, amenazas & administración de vulnerabilidades  remediation, tvm remediation intune, tvm remediation sccm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9631c38279fbcfcbc4d55b09409af9bb16c783f6
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476673"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>Corregir vulnerabilidades con Administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Amenaza y administración de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a>Corrección de solicitudes

La Administración de amenazas y vulnerabilidades de Microsoft Defender para endpoints se une a la diferencia entre los administradores de SEGURIDAD y TI a través del flujo de trabajo de solicitud de corrección. Los administradores de seguridad como usted pueden solicitar al administrador de TI que corrija una vulnerabilidad de **las páginas de** recomendaciones de seguridad a Intune.

### <a name="enable-microsoft-intune-connection"></a>Habilitar Microsoft Intune conexión

Para usar esta funcionalidad, habilite las Microsoft Intune conexiones. En el portal Microsoft 365 Defender, **vaya a Configuración** \> **características avanzadas** \> **generales**. Desplácese hacia abajo y busque **Microsoft Intune conexión**. De forma predeterminada, la alternancia está desactivada. Activa la **Microsoft Intune de** **conexión.**

**Nota**: Si tienes habilitada la conexión de Intune, obtienes una opción para crear una tarea de seguridad de Intune al crear una solicitud de corrección. Esta opción no aparece si la conexión no está establecida.

Consulta [Usar Intune para corregir las vulnerabilidades identificadas por Microsoft Defender para obtener más](/intune/atp-manage-vulnerabilities) información.

### <a name="remediation-request-steps"></a>Pasos de solicitud de corrección

1. Vaya al menú **de navegación de** administración de amenazas y vulnerabilidades en el portal de Microsoft 365 Defender y seleccione **Recomendaciones** [**de seguridad**](tvm-security-recommendation.md).

2. Seleccione una recomendación de seguridad para la que desea solicitar corrección y, a continuación, seleccione **Opciones de corrección**.

3. Rellene el formulario, incluidos los grupos de dispositivos aplicables, la prioridad, la fecha de vencimiento y las notas opcionales.
    1. Si elige la opción de corrección "atención requerida", la selección de una fecha de vencimiento no estará disponible ya que no hay ninguna acción específica.

4. Seleccione **Enviar solicitud**. Enviar una solicitud de corrección crea un elemento de actividad de corrección dentro de Administración de amenazas y vulnerabilidades, que se puede usar para supervisar el progreso de corrección de esta recomendación. Esto no desencadenará una corrección ni aplicará ningún cambio en los dispositivos.

5. Notifique al administrador de TI acerca de la nueva solicitud y haga que inicie sesión en Intune para aprobar o rechazar la solicitud e iniciar una implementación de paquete.

6. Vaya a la [**página Corrección**](tvm-remediation.md) para ver el estado de la solicitud de corrección.

Si quieres comprobar cómo se muestra el vale en Intune, consulta Usar Intune para corregir las vulnerabilidades identificadas por [Microsoft Defender](/intune/atp-manage-vulnerabilities) para endpoint para obtener más información.

> [!NOTE]
> Si la solicitud implica la corrección de más de 10 000 dispositivos, solo podemos enviar 10 000 dispositivos para su corrección a Intune.

Después de identificar y asignar las debilidades de seguridad cibernética de su organización a recomendaciones de seguridad que se pueden [realizar, comience](tvm-security-recommendation.md) a crear tareas de seguridad. Puede crear tareas a través de la integración con Microsoft Intune donde se crean vales de corrección.

Reduzca la exposición de su organización a las vulnerabilidades y aumente la configuración de seguridad mediante la corrección de las recomendaciones de seguridad.

## <a name="view-your-remediation-activities"></a>Ver las actividades de corrección

Cuando envía una solicitud de corrección desde la página Recomendaciones de seguridad, inicia una actividad de corrección. Se crea una tarea de seguridad que se puede realizar un seguimiento en la página Administración de amenazas y vulnerabilidades **corrección** y se crea un vale de corrección en Microsoft Intune.

Si elige la opción de corrección "atención requerida", no habrá ninguna barra de progreso, estado de vale o fecha de vencimiento, ya que no hay ninguna acción real que podamos supervisar.

Una vez que se encuentra en la página Corrección, seleccione la actividad de corrección que desea ver. Puede seguir los pasos de corrección, realizar un seguimiento del progreso, ver la recomendación relacionada, exportar a CSV o marcar como completada.

:::image type="content" source="../../media/remediation-flyouteolswnew.png" alt-text="La página Corrección, con una actividad de corrección seleccionada, y el control desplegable de esa actividad que enumera la descripción, las herramientas de administración de dispositivos y servicios de IT y la corrección de dispositivos" lightbox="../../media/remediation-flyouteolswnew.png":::

> [!NOTE]
> Hay un período de retención de 180 días para las actividades de corrección completadas. Para mantener el rendimiento óptimo de la página Corrección, la actividad de corrección se quitará 6 meses después de su finalización.

### <a name="completed-by-column"></a>Completado por columna

Realice un seguimiento de quién cerró la actividad de corrección con la columna "Completado por" en la página Corrección.

- **Dirección de correo** electrónico: el correo electrónico de la persona que completó manualmente la tarea
- **Confirmación del** sistema: la tarea se completó automáticamente (todos los dispositivos corregidos)
- **N/A**: La información no está disponible porque no sabemos cómo se completó esta tarea anterior

:::image type="content" source="images/tvm-completed-by.png" alt-text="El Objeto Creado por y completado por columnas con dos filas" lightbox="images/tvm-completed-by.png":::

### <a name="top-remediation-activities-in-the-dashboard"></a>Principales actividades de corrección en el panel

Ver **las principales actividades de corrección** en el [panel de administración **de amenazas y** vulnerabilidades](tvm-dashboard-insights.md). Seleccione cualquiera de las entradas para ir a la **página Corrección** . Puede marcar la actividad de corrección como completada después de que el equipo de administración de TI corrija la tarea.

:::image type="content" source="images/tvm-remediation-activities-card.png" alt-text="La tarjeta Principales actividades de corrección" lightbox="images/tvm-remediation-activities-card.png":::

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre amenazas administración de vulnerabilidades amenazas](next-gen-threat-and-vuln-mgt.md)
- [Panel](tvm-dashboard-insights.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)