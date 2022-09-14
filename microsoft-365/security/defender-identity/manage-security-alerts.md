---
title: Microsoft Defender for Identity alertas de seguridad en Microsoft 365 Defender
description: Aprenda a administrar y revisar las alertas de seguridad emitidas por Microsoft Defender for Identity en Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 14a05f522cab6c0af5ae9bf54aed83bafdd7befc
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67682445"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Alertas de seguridad de Defender for Identity en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explican los conceptos básicos sobre cómo trabajar con [Microsoft Defender for Identity](/defender-for-identity) alertas de seguridad en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

Las alertas de Defender for Identity se integran de forma nativa en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con un formato de página de alerta de identidad dedicado. Esto marca el primer paso del recorrido para [introducir toda la experiencia de Microsoft Defender for Identity en Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).

La nueva página De alerta de identidad proporciona a Microsoft Defender for Identity clientes un mejor enriquecimiento de señales entre dominios y nuevas funcionalidades automatizadas de respuesta de identidad. Garantiza la seguridad y ayuda a mejorar la eficacia de las operaciones de seguridad.

Una de las ventajas de investigar las alertas a través de [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) es que Microsoft Defender for Identity alertas se correlacionan aún más con la información obtenida de cada uno de los demás productos del conjunto. Estas alertas mejoradas son coherentes con los demás formatos de alerta de Microsoft 365 Defender que se origina en [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security) y [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint). La nueva página elimina eficazmente la necesidad de navegar a otro portal de productos para investigar las alertas asociadas a la identidad.

Las alertas que se originan en Defender for Identity ahora pueden desencadenar las [Microsoft 365 Defender funcionalidades de investigación y respuesta automatizadas (AIR),](/microsoft-365/security/defender/m365d-autoir) incluida la corrección automática de alertas y la mitigación de herramientas y procesos que pueden contribuir a la actividad sospechosa.

> [!IMPORTANT]
> Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y nuevas.

## <a name="review-security-alerts"></a>Revisión de alertas de seguridad

Se puede acceder a las alertas desde varias ubicaciones, incluida la página **Alertas** , la página **Incidentes** , las páginas de **dispositivos** individuales y desde la página **Búsqueda avanzada** . En este ejemplo, revisaremos la **página Alertas**.

En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a **Incidentes & alertas** y, a continuación, a **Alertas**.

:::image type="content" source="../../media/defender-identity/incidents-alerts.png" alt-text="Elemento de menú Alertas" lightbox="../../media/defender-identity/incidents-alerts.png":::

Para ver las alertas de Defender for Identity, en la parte superior derecha, seleccione **Filtrar** y, a continuación, en **Orígenes de servicio**, seleccione **Microsoft Defender for Identity** y seleccione **Aplicar**:

:::image type="content" source="../../media/defender-identity/filter-defender-for-identity.png" alt-text="Filtro para los eventos de Defender for Identity" lightbox="../../media/defender-identity/filter-defender-for-identity.png":::

Las alertas se muestran con información en las columnas siguientes: **Nombre de alerta**, **Etiquetas**, **Gravedad**, **Estado de investigación**, **Estado**, **Categoría**, **Origen de detección**, **Activos afectados**, **Primera actividad** y **Última actividad**.

:::image type="content" source="../../media/defender-identity/filtered-alerts.png" alt-text="Eventos de Defender for Identity" lightbox="../../media/defender-identity/filtered-alerts.png":::

## <a name="manage-alerts"></a>Administrar alertas

Si hace clic en el **nombre** de alerta de una de las alertas, irá a la página con detalles sobre la alerta. En el panel izquierdo, verá un resumen de **Lo que ha ocurrido**:

:::image type="content" source="../../media/defender-identity/what-happened.png" alt-text="El panel What happened (Lo que ha ocurrido)" lightbox="../../media/defender-identity/what-happened.png":::

Encima del cuadro **What happened (Lo que ha ocurrido** ) hay botones para **las cuentas**, el **host de destino** y el **host de origen** de la alerta. Para otras alertas, es posible que vea botones para obtener más información sobre hosts, cuentas, direcciones IP, dominios y grupos de seguridad adicionales. Seleccione cualquiera de ellos para obtener más detalles sobre las entidades implicadas.

En el panel derecho, verá los **detalles** de la alerta. Aquí puede ver más detalles y realizar varias tareas:

- **Clasificación de esta alerta**: aquí puede designar esta alerta como una **alerta True** o **una alerta False**.

    :::image type="content" source="../../media/defender-identity/classify-alert.png" alt-text="Página en la que se puede clasificar una alerta" lightbox="../../media/defender-identity/classify-alert.png":::

- **Estado de alerta** : en **Establecer clasificación**, puede clasificar la alerta como **True** o **False**. En **Asignado a**, puede asignar la alerta a usted mismo o anular su asignación.

    :::image type="content" source="../../media/defender-identity/alert-state.png" alt-text="Panel Estado de alerta" lightbox="../../media/defender-identity/alert-state.png":::

- **Detalles de la alerta** : en **Detalles** de la alerta, puede encontrar más información sobre la alerta específica, seguir un vínculo a la documentación sobre el tipo de alerta, ver con qué incidente está asociada la alerta, revisar las investigaciones automatizadas vinculadas a este tipo de alerta y ver los dispositivos y usuarios afectados.

   :::image type="content" source="../../media/defender-identity/alert-details.png" alt-text="Página Detalles de la alerta" lightbox="../../media/defender-identity/alert-details.png":::

- **Comentarios & historial** : aquí puede agregar sus comentarios a la alerta y ver el historial de todas las acciones asociadas a la alerta.

    :::image type="content" source="../../media/defender-identity/comments-history.png" alt-text="Página Historial de comentarios &" lightbox="../../media/defender-identity/comments-history.png":::

- **Administrar alerta** : si selecciona **Administrar alerta**, irá a un panel que le permitirá editar:
  - **Estado** : puede elegir **Nuevo**, **Resuelto** o **En curso**.
  - **Clasificación** : puede elegir **Alerta verdadera** o **Alerta falsa**.
  - **Comentario** : puede agregar un comentario sobre la alerta.

    Si selecciona los tres puntos junto a **Administrar alerta**, puede **Consultar a un experto en amenazas**, **Exportar** la alerta a un archivo de Excel o **Vincular a otro incidente**.

    :::image type="content" source="../../media/defender-identity/manage-alert.png" alt-text="La opción Administrar alerta" lightbox="../../media/defender-identity/manage-alert.png":::

    > [!NOTE]
    > En el archivo de Excel, ahora tiene dos vínculos disponibles: **Ver en Microsoft Defender for Identity** y **Ver en Microsoft 365 Defender**. Cada vínculo le llevará al portal correspondiente y proporcionará información sobre la alerta allí.

## <a name="see-also"></a>Vea también

- [Investigar alertas con Microsoft 365 Defender](../defender/investigate-alerts.md)
