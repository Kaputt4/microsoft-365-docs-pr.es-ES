---
title: Responder y mitigar amenazas en Microsoft Defender para empresas
description: A medida que se detectan amenazas, puede tomar medidas para responder y mitigar esas amenazas.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 50a759c4f84aee72b376ff9126c54d381f4a373f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327789"
---
# <a name="respond-to-and-mitigate-threats-in-microsoft-defender-for-business"></a>Responder y mitigar amenazas en Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando para Microsoft 365 Empresa Premium clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

El portal Microsoft 365 Defender permite al equipo de seguridad responder y mitigar las amenazas detectadas. Este artículo le guiará por un ejemplo de cómo puede usar Defender para empresas.

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="view-detected-threats"></a>Ver amenazas detectadas

1. Vaya al portal Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Tarjetas de aviso en la página principal. Las tarjetas te dicen de un vistazo cuántas amenazas se detectaron, junto con cuántas cuentas de usuario, puntos de conexión (dispositivos) y otros activos se vieron afectados. La siguiente imagen es un ejemplo de tarjetas que puede ver:

   :::image type="content" source="../../media/defender-business/mdb-examplecards.png" alt-text="Captura de pantalla de las tarjetas en Microsoft 365 Defender portal":::

3. Seleccione un botón o un vínculo en la tarjeta para ver más información y tomar medidas. Por ejemplo, nuestra tarjeta **Dispositivos en riesgo** incluye un **botón Ver detalles** . La selección de ese botón nos lleva a la **página Inventario de** dispositivos, como se muestra en la siguiente imagen:

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Captura de pantalla del inventario de dispositivos":::

   La **página Inventario de dispositivos** enumera los dispositivos de la organización, junto con su nivel de riesgo y su nivel de exposición.

4. Selecciona un elemento, como un dispositivo. Se abre un panel desplegable y muestra más información sobre las alertas e incidentes generados para ese elemento, como se muestra en la siguiente imagen:  

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout.png" alt-text="Captura de pantalla del panel desplegable de un dispositivo seleccionado":::

5. En el menú desplegable, vea la información que se muestra. Seleccione los puntos suspensivos (...) para abrir un menú que enumera las acciones disponibles, como se muestra en la siguiente imagen: 

   :::image type="content" source="../../media/defender-business/mdb-deviceinventory-selecteddeviceflyout-menu.png" alt-text="Captura de pantalla de las acciones disponibles para un dispositivo seleccionado":::

6. Seleccione una acción disponible. Por ejemplo, puedes elegir **Ejecutar examen antivirus**, lo que hará Antivirus de Microsoft Defender iniciar un examen rápido en el dispositivo. O bien, puedes seleccionar **Iniciar investigación automatizada** para desencadenar una investigación automatizada en el dispositivo.

## <a name="next-steps"></a>Siguientes pasos

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)

- [Administrar dispositivos en Microsoft Defender para empresas](mdb-manage-devices.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)