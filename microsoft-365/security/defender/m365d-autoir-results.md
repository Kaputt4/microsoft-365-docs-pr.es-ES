---
title: Detalles y resultados de una investigación automatizada
description: Ver los resultados y los resultados clave de la investigación automatizada en Microsoft 365 Defender
keywords: automatizada, investigación, resultados, analizar, detalles, corrección, autoair
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 08/11/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: 238c2f90c47338e9ece876bf0a9146bdfaa9427c
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68069675"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Detalles y resultados de una investigación automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Con Microsoft 365 Defender, cuando se ejecuta una [investigación automatizada](m365d-autoir.md), los detalles sobre esa investigación están disponibles durante y después del proceso de investigación automatizado. Si tiene los [permisos necesarios](m365d-action-center.md#required-permissions-for-action-center-tasks), puede ver esos detalles en una vista de detalles de investigación que le proporciona el estado actualizado y la capacidad de aprobar las acciones pendientes. 

## <a name="new-unified-investigation-page"></a>(NUEVO) Página de investigación unificada

La página de investigación se ha actualizado recientemente para incluir información en los dispositivos, el correo electrónico y el contenido de colaboración. La nueva página de investigación unificada define un lenguaje común y proporciona una experiencia unificada para las investigaciones automáticas en [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) y [Microsoft Defender para Office 365](../office-365-security/defender-for-office-365.md). Para acceder a la página de investigación unificada, seleccione el vínculo en el banner amarillo en el que verá:

- Cualquier página de investigación del <a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">portal de cumplimiento Microsoft Purview</a>
- Cualquier página de investigación en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com))
- Cualquier incidente o experiencia del Centro de acción en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>

## <a name="open-the-investigation-details-view"></a>Abrir la vista de detalles de la investigación

Puede abrir un informe en la vista previa de impresión utilizando uno de los métodos siguientes:

- [Seleccionar un elemento en el centro de actividades](#select-an-item-in-the-action-center)
- [Seleccionar una investigación en una página de detalles de un incidente](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Seleccionar un elemento en el centro de actividades

El [Centro de acciones](m365d-action-center.md) mejorado ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) reúne [acciones de corrección](m365d-remediation-actions.md) en todos los dispositivos, correo electrónico & contenido de colaboración e identidades. Las acciones enumeradas incluyen acciones de corrección que se realizaron de forma automática o manual. En el Centro de actividades, puede ver las acciones que están esperando la aprobación y las acciones que ya se aprobaron o completaron. También puede navegar a más detalles, como una página de investigación.

> [!TIP]
> Debe tener [ciertos permisos](m365d-action-center.md#required-permissions-for-action-center-tasks) para aprobar, rechazar o deshacer acciones.

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión. 

2. En el panel de navegación, elija **Centro de actividades**. 

3. En la pestaña **pendiente** o **historial**, seleccione un elemento. Se abre el panel flotante.

4. Revise la información del panel flotante y, a continuación, realice uno de los pasos siguientes:
   - Seleccione **Abrir página de investigación** para ver más detalles sobre la investigación.
   - Seleccione **Aprobar** para iniciar una acción pendiente.
   - Seleccione **Rechazar** para evitar que se realice una acción pendiente.
   - Seleccione **Ir a buscar** para ir a [Búsqueda avanzada](advanced-hunting-overview.md).

### <a name="open-an-investigation-from-an-incident-details-page"></a>Abrir una investigación desde una página de detalles de un incidente

Use una página de detalles de un incidente para ver información detallada sobre un incidente, incluidas las alertas que contenían información acerca de cualquier dispositivo, cuenta de usuario o buzón que les afecten.

1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a> e inicie sesión. 

2. En el panel de navegación, elija **Incidentes & alertas** > **Incidentes**. 

3. Seleccione un elemento de la lista y, a continuación, elija **Abrir página de incidente**.

4. Seleccione la pestaña **Investigaciones** y, a continuación, seleccione una investigación en la lista. Se abre el panel flotante.

5. Seleccione **Abrir página de investigación**. 

Por ejemplo:

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="Página de investigación del portal de Microsoft 365 Defender" lightbox="../../media/mtp-incidentdetails-tabs.png":::

## <a name="investigation-details"></a>Detalles de la investigación

Use la vista detalles de la investigación para ver la actividad pasada, actual y pendiente relacionada con una investigación. Por ejemplo:

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Página de detalles de la investigación en el portal de Microsoft 365 Defender" lightbox="../../media/mtp-air-investdetails.png":::

En la vista de detalles de la investigación, puede ver información en las pestañas **gráfico de investigación**, **alertas**, **dispositivos**, **identidades**, **resultados clave**, **entidades**, **registro**, y **acciones pendientes**, que se describen en la siguiente tabla.

> [!NOTE]
> Las pestañas específicas que vea en una página de detalles de investigación dependen de lo que incluya su suscripción. Por ejemplo, si la suscripción no incluye Microsoft Defender para Office 365 plan 2, no verá una pestaña **Buzones**.

| Pestaña | Descripción |
|:--------|:--------|
| **Gráfico de investigación** | Proporciona una representación visual de la investigación. Muestra una lista de las entidades y enumera las amenazas encontradas, junto con las alertas y si hay acciones pendientes de aprobación.<br/>Puede seleccionar un elemento en el gráfico para ver más detalles. Por ejemplo, al seleccionar el icono **Evidencia** , se le lleva a la pestaña **Evidencia** , donde puede ver las entidades detectadas y sus veredictos. |
| **Alertas** | Muestra las alertas relacionadas con la investigación. Las alertas pueden provenir de características de protección contra amenazas en el dispositivo de un usuario, en aplicaciones de Office, Microsoft Defender for Cloud Apps y otras características de Microsoft 365 Defender. <br> <br> Si ve *tipo de alerta no compatible*, significa que las funcionalidades de investigación automatizada no pueden recoger esa alerta para ejecutar una investigación automatizada. Sin embargo, puede [investigar estas alertas manualmente](investigate-incidents.md#alerts).
| **Devices** | Enumera los dispositivos incluidos en la investigación junto con su nivel de corrección. (Los niveles de corrección corresponden [al nivel de automatización de los grupos de dispositivos](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)). |
| **Buzones** |Enumera los buzones que se ven afectados por las amenazas detectadas.  |
| **Usuarios**  | Enumera las cuentas de usuario que se ven afectadas por las amenazas detectadas. |
| **Evidencia** | Enumera las pruebas que generan las alertas o las investigaciones. Incluye veredictos (*malintencionados*, *sospechosos*, *desconocidos* o *no se encontraron amenazas*) y el estado de corrección. |
| **Entities** | Proporciona detalles sobre cada entidad analizada, incluido un veredicto para cada tipo de entidad (*malintencionada*, *sospechosa* o *Sin amenazas encontradas*).|
|**Log** | Proporciona una vista cronológica y detallada de todas las acciones de investigación realizadas después de que se desencadenó una alerta.|
| **Historial de acciones pendientes** | Muestra los elementos que necesitan aprobación para continuar. Vaya al Centro de acciones ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) para aprobar las acciones pendientes. |


## <a name="investigation-states"></a>Estados de investigación

En la tabla siguiente se enumeran los estados de investigación y lo que indican.


|Estado de investigación  |Definición  |
|---------|---------|
|Benigno   | Se investigaron los artefactos y se estableció que no se encontraron amenazas.|
|PendingResource     | Una investigación automatizada se pausa porque una acción de corrección está pendiente de aprobación o el dispositivo en el que se encontró un artefacto no está disponible temporalmente.|
|UnsupportedAlertType     | No hay disponible una investigación automatizada para este tipo de alerta. Se puede realizar una investigación adicional manualmente mediante la búsqueda avanzada. |
|Error     | Al menos un analizador de investigación se encontró con un problema en el que no pudo completar la investigación. Si se produce un error en una investigación después de aprobar las acciones de corrección, es posible que las acciones de corrección se hayan realizado correctamente.|
|Corrección correcta| Se completó una investigación automatizada y se completaron o aprobaron todas las acciones de corrección.|

Para proporcionar más contexto sobre cómo se muestran los estados de investigación, en la tabla siguiente se enumeran las alertas y su estado de investigación automatizado correspondiente. Esta tabla se incluye como ejemplo de lo que un equipo de operaciones de seguridad podría ver en el portal de Microsoft 365 Defender.

|Nombre de alerta | Severity | Estado de investigación | Estado | Categoría |
|-----------|----------|---------------------|--------|----------|
|Se detectó malware en un archivo de imagen de disco wim|Informativo|Benigno|Resuelto|Malware|
|Se detectó malware en un archivo de archivo rar|Informativo|PendingResource|Nuevo|Malware|
|Se detectó malware en un archivo de archivo rar|Informativo|UnsupportedAlertType|Nueva|Malware|
|Se detectó malware en un archivo de archivo rar|Informativo|UnsupportedAlertType|Nueva|Malware|
|Se detectó malware en un archivo de archivo rar|Informativo|UnsupportedAlertType|Nueva|Malware|
|Se detectó malware en un archivo zip|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo zip|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo zip|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo zip|Informativo|PendingResource|Nueva|Malware|
|Wpakill hacktool se ha evitado|Bajo|Error|Nuevo|Malware|
|GendowsBatch hacktool se ha evitado|Bajo|Error|Nuevo|Malware|
|Keygen hacktool se ha evitado|Bajo|Error|Nuevo|Malware|
|Se detectó malware en un archivo zip|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo de archivo rar|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo de archivo rar|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo zip|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo de archivo rar|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo de archivo rar|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo de imagen de disco iso.|Informativo|PendingResource|Nueva|Malware|
|Se detectó malware en un archivo de imagen de disco iso.|Informativo|PendingResource|Nuevo|Malware|
|Se detectó malware en un archivo de datos de Outlook pst|Informativo|UnsupportedAlertType|Nuevo|Malware|
|Se detectó malware en un archivo de datos de Outlook pst|Informativo|UnsupportedAlertType|Nueva|Malware|
|MediaGet detectado|Mediano|Parcialmente invertido|Nuevo|Malware|
|TrojanEmailFile|Mediano|CorrectamenteRemediated|Resuelto|Malware|
|Se ha evitado el malware CustomEnterpriseBlock|Informativo|CorrectamenteRemediated|Resuelto|Malware|
|Se bloqueó un malware CustomEnterpriseBlock activo|Bajo|CorrectamenteRemediated|Resuelto|Malware|
|Se bloqueó un malware CustomEnterpriseBlock activo|Bajo|CorrectamenteRemediated|Resuelto|Malware|
|Se bloqueó un malware CustomEnterpriseBlock activo|Bajo|CorrectamenteRemediated|Resuelto|Malware|
|TrojanEmailFile|Mediano|Benigno|Resuelto|Malware|
|Se ha evitado el malware CustomEnterpriseBlock|Informativo|UnsupportedAlertType|Nuevo|Malware|
|Se ha evitado el malware CustomEnterpriseBlock|Informativo|CorrectamenteRemediated|Resuelto|Malware|
|TrojanEmailFile|Mediano|CorrectamenteRemediated|Resuelto|Malware|
|TrojanEmailFile|Mediano|Benigno|Resuelto|Malware|
|Se bloqueó un malware CustomEnterpriseBlock activo|Bajo|PendingResource|Nueva|Malware|

## <a name="next-steps"></a>Pasos siguientes

- [Ver y aprobar acciones de corrección](m365d-autoir-actions.md)
- [Más información sobre las acciones de corrección](m365d-remediation-actions.md)
