---
title: Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre cómo ver & administrar alertas, responder a amenazas, administrar dispositivos y revisar acciones de corrección
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 01/06/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365initiative-defender-business
ms.openlocfilehash: ad0b7a3aa9f68c44a594a9a27906f2fb765bd121
ms.sourcegitcommit: aac7e002ec6e10a41baa2d0bd38614b0ed471a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62244852"
---
# <a name="view-and-manage-incidents-in-microsoft-defender-for-business-preview"></a>Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán aquí [para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios)y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

A medida que se detectan amenazas y se desencadenan alertas, se crean incidentes. El equipo de seguridad de su empresa puede ver y administrar incidentes en el portal Microsoft 365 Defender web.

**Este artículo incluye:**

- [Cómo supervisar los incidentes y alertas](#monitor-your-incidents--alerts)
- [Gravedad de alerta](#alert-severity)
- [Pasos siguientes](#next-steps)

>
> **¿Tiene un minuto?**
> Por favor, <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">haga nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="monitor-your-incidents--alerts"></a>Supervisar las alertas de & incidentes

1. En el Microsoft 365 Defender de navegación ( [https://security.microsoft.com](https://security.microsoft.com) ), en el panel de navegación, seleccione **Incidentes**. Los incidentes que se crearon aparecen en la página.

   :::image type="content" source="../../media/defender-business/mdb-incidents-list.png" alt-text="Captura de pantalla de la lista incidentes":::

2. Seleccione una alerta para abrir su panel desplegable, donde puede obtener más información sobre la alerta. 

   :::image type="content" source="../../media/defender-business/mdb-incident-flyout.png" alt-text="Captura de pantalla del incidente seleccionado con el menú desplegable abierto":::

3. En el panel desplegable, puede ver el título de la alerta, ver una lista de activos (como puntos de conexión o cuentas de usuario) que se vieron afectados, realizar acciones disponibles y usar vínculos para ver más información e incluso abrir la página de detalles de la alerta seleccionada. 

> [!TIP]
> Microsoft Defender para empresas (versión preliminar) está diseñado para ayudarle a solucionar las amenazas detectadas ofreciendo acciones recomendadas. Cuando vea una alerta, busque las acciones recomendadas que debe realizar. También tome nota de la gravedad de la alerta, que se determina no solo en función de la gravedad de la amenaza, sino también en el nivel de riesgo para su empresa. 

## <a name="alert-severity"></a>Gravedad de alerta

Cuando Antivirus de Microsoft Defender asigna una gravedad de alerta en función de la gravedad absoluta de una amenaza detectada (malware) y el riesgo potencial para un extremo individual (si está infectado).
Microsoft Defender para empresas (versión preliminar) asigna una gravedad de alerta en función de la gravedad del comportamiento detectado, el riesgo real para un punto de conexión (dispositivo) y, lo que es más importante, el riesgo potencial para su empresa. En la tabla siguiente se enumeran algunos ejemplos: <br/><br/>

| Escenario | Gravedad de alerta | Reason |
|:---|:---|:---|
| Antivirus de Microsoft Defender detecta y detiene una amenaza antes de hacer cualquier daño. | Informativo | La amenaza se detuvo antes de que se realizara cualquier daño. |
| Antivirus de Microsoft Defender detecta malware que se estaba ejecutando en su empresa. El malware se detiene y se corrige. | Bajo | Aunque es posible que se hayan causado algunos daños a un punto de conexión individual, el malware ahora no representa ninguna amenaza para su empresa. |
| El malware que se está ejecutando lo detecta Microsoft Defender para empresas (versión preliminar). El malware se bloquea casi inmediatamente. | Medio o alto | El malware representa una amenaza para puntos de conexión individuales y para su empresa. |
| Se detecta un comportamiento sospechoso, pero aún no se han realizado acciones de corrección. | Bajo, Medio o Alto | La gravedad depende del grado en que el comportamiento representa una amenaza para su empresa. |

## <a name="next-steps"></a>Siguientes pasos

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)

- [Ver o editar directivas de dispositivos en Microsoft Defender para empresas (versión preliminar)](mdb-view-edit-policies.md)