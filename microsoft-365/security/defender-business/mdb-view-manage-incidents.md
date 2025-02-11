---
title: Visualización y administración de incidentes en Microsoft Defender para Empresas
description: Vea y administre alertas, responda a amenazas, administre dispositivos y revise las acciones de corrección en las amenazas detectadas en Defender for Business.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365-initiative-defender-business
- tier1
ms.openlocfilehash: 4fb399bebf27ffcffb9f388d2421804f50592056
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68096861"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business"></a>Visualización y administración de incidentes en Microsoft Defender para Empresas

A medida que se detectan amenazas y se generan alertas, se crean incidentes. El equipo de seguridad de la empresa puede ver y administrar incidentes en el portal de Microsoft 365 Defender.

**En este artículo se incluyen**:

- [Supervisión de incidentes y alertas](#monitor-your-incidents--alerts)
- [Gravedad de la alerta](#alert-severity)
- [Pasos siguientes](#next-steps)


## <a name="monitor-your-incidents--alerts"></a>Supervisión de los incidentes & alertas

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, seleccione **Incidentes**. Los incidentes que se crearon aparecen en la página.

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="Captura de pantalla de la lista incidentes":::

2. Seleccione una alerta para abrir su panel flotante, donde puede obtener más información sobre la alerta. 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="Captura de pantalla del incidente seleccionado con el control flotante abierto":::

3. En el panel flotante, puede ver el título de la alerta, ver una lista de recursos (como puntos de conexión o cuentas de usuario) que se vieron afectados, realizar acciones disponibles y usar vínculos para ver más información e incluso abrir la página de detalles de la alerta seleccionada. 

> [!TIP]
> Defender for Business está diseñado para ayudarle a abordar las amenazas detectadas mediante la oferta de acciones recomendadas. Cuando vea una alerta, busque las acciones recomendadas que debe realizar. Tome nota también de la gravedad de la alerta, que se determina no solo en función de la gravedad de la amenaza, sino también del nivel de riesgo para su empresa. 

## <a name="alert-severity"></a>Gravedad de la alerta

Cuando Microsoft Defender Antivirus asigna una gravedad de alerta basada en la gravedad absoluta de una amenaza detectada (malware) y el riesgo potencial para un punto de conexión individual (si está infectado). Defender for Business asigna una gravedad de alerta en función de la gravedad del comportamiento detectado, el riesgo real para un punto de conexión (dispositivo) y, lo que es más importante, el riesgo potencial para la empresa. En la tabla siguiente se enumeran algunos ejemplos:

| Escenario | Gravedad y motivo de la alerta |
|:---|:---|
| Microsoft Defender Antivirus detecta y detiene una amenaza antes de que se produzcan daños. | **Informativo**. La amenaza se detuvo antes de que se realizara cualquier daño. |
| Microsoft Defender Antivirus detecta el malware que se estaba ejecutando en su empresa. El malware se detiene y se corrige. | **Bajo**. Aunque es posible que se haya producido algún daño en un punto de conexión individual, el malware no supone ninguna amenaza para su empresa. |
| Defender for Business detecta el malware que se está ejecutando. El malware se bloquea casi inmediatamente. | **Medio** o **Alto**. El malware supone una amenaza para puntos de conexión individuales y para su empresa. |
| Se detecta un comportamiento sospechoso, pero aún no se realizan acciones correctivas. | **Bajo**, **Medio** o **Alto**. La gravedad depende del grado en que el comportamiento supone una amenaza para la empresa. |

## <a name="next-steps"></a>Pasos siguientes

- [Respuesta y mitigación de amenazas en Defender para empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)
- [Visualización o edición de directivas de dispositivos en Defender para empresas](mdb-view-edit-policies.md)