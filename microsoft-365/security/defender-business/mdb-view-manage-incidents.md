---
title: Visualización y administración de incidentes en Microsoft Defender para Empresas
description: Obtenga información sobre cómo ver & administrar alertas, responder a amenazas, administrar dispositivos y revisar las acciones de corrección
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: ec1d85b72cfbe17e182d3aed573476e4fadfdef6
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64861452"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business"></a>Visualización y administración de incidentes en Microsoft Defender para Empresas

> [!NOTE]
> Microsoft Defender para Empresas ahora se incluye en [Microsoft 365 Empresa Premium](../../business-premium/index.md). 

A medida que se detectan amenazas y se desencadenan alertas, se crean incidentes. El equipo de seguridad de la empresa puede ver y administrar incidentes en el portal de Microsoft 365 Defender.

**En este artículo se incluyen**:

- [Supervisión de incidentes y alertas](#monitor-your-incidents--alerts)
- [Gravedad de la alerta](#alert-severity)
- [Pasos siguientes](#next-steps)

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="monitor-your-incidents--alerts"></a>Supervisión de los incidentes & alertas

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, seleccione **Incidentes**. Los incidentes que se crearon aparecen en la página.

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="Captura de pantalla de la lista incidentes":::

2. Seleccione una alerta para abrir su panel flotante, donde puede obtener más información sobre la alerta. 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="Captura de pantalla del incidente seleccionado con el control flotante abierto":::

3. En el panel flotante, puede ver el título de la alerta, ver una lista de recursos (como puntos de conexión o cuentas de usuario) que se vieron afectados, realizar acciones disponibles y usar vínculos para ver más información e incluso abrir la página de detalles de la alerta seleccionada. 

> [!TIP]
> Microsoft Defender para Empresas está diseñado para ayudarle a abordar las amenazas detectadas mediante la oferta de acciones recomendadas. Cuando vea una alerta, busque las acciones recomendadas que debe realizar. Tome nota también de la gravedad de la alerta, que se determina no solo en función de la gravedad de la amenaza, sino también del nivel de riesgo para su empresa. 

## <a name="alert-severity"></a>Gravedad de la alerta

Cuando Antivirus de Microsoft Defender asigna una gravedad de alerta basada en la gravedad absoluta de una amenaza detectada (malware) y el riesgo potencial para un punto de conexión individual (si está infectado).
Microsoft Defender para Empresas asigna una gravedad de alerta en función de la gravedad del comportamiento detectado, el riesgo real para un punto de conexión (dispositivo) y, lo que es más importante, el riesgo potencial para la empresa. En la tabla siguiente se enumeran algunos ejemplos:

| Escenario | Gravedad de la alerta | Reason |
|:---|:---|:---|
| Antivirus de Microsoft Defender detecta y detiene una amenaza antes de que se produzcan daños. | Informativo | La amenaza se detuvo antes de que se realizara cualquier daño. |
| Antivirus de Microsoft Defender detecta el malware que se estaba ejecutando dentro de la empresa. El malware se detiene y se corrige. | Bajo | Aunque es posible que se haya producido algún daño en un punto de conexión individual, el malware no supone ninguna amenaza para su empresa. |
| Microsoft Defender para Empresas detecta el malware que se está ejecutando. El malware se bloquea casi inmediatamente. | Medio o alto | El malware supone una amenaza para puntos de conexión individuales y para su empresa. |
| Se detecta un comportamiento sospechoso, pero aún no se realizan acciones correctivas. | Bajo, Medio o Alto | La gravedad depende del grado en que el comportamiento supone una amenaza para la empresa. |

## <a name="next-steps"></a>Siguientes pasos

- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)
- [Ver o editar directivas de dispositivo en Microsoft Defender para Empresas](mdb-view-edit-policies.md)