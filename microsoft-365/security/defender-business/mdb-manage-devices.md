---
title: Administrar dispositivos en Microsoft Defender para empresas
description: Obtenga información sobre cómo administrar dispositivos en Microsoft Defender para empresas
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
ms.openlocfilehash: e0c564fda55393d9f60bd79081a309bde1e87f02
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329353"
---
# <a name="manage-devices-in-microsoft-defender-for-business"></a>Administrar dispositivos en Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando para Microsoft 365 Empresa Premium clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

En Microsoft Defender para empresas, puedes administrar dispositivos de la siguiente manera:

- [Ver una lista de dispositivos incorporados](#view-the-list-of-onboarded-devices) para ver su nivel de riesgo, nivel de exposición y estado de mantenimiento

- [Realizar acciones en un dispositivo que](#take-action-on-a-device-that-has-threat-detections) tenga detecciones de amenazas

- [Incorporación de un dispositivo a Defender para empresas](#onboard-a-device)  

- [Offboard a device from Defender for Business](#offboard-a-device)

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="view-the-list-of-onboarded-devices"></a>Ver la lista de dispositivos incorporados

:::image type="content" source="../../media/defender-business/mdb-deviceinventory.png" alt-text="Captura de pantalla del inventario de dispositivos":::

1. Vaya al portal Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Inventario de dispositivos**.

3. Selecciona un dispositivo para abrir su panel desplegable, donde puedes obtener más información sobre su estado y tomar medidas. 

   Si aún no tienes ningún dispositivo en la lista, incorpora dispositivos [a Microsoft Defender para empresas](mdb-onboard-devices.md)

## <a name="take-action-on-a-device-that-has-threat-detections"></a>Realizar acciones en un dispositivo que tenga detecciones de amenazas

:::image type="content" source="../../media/defender-business/mdb-selected-device.png" alt-text="Captura de pantalla de un dispositivo seleccionado con detalles y acciones disponibles":::

1. En el Microsoft 365 Defender web ([https://security.microsoft.com](https://security.microsoft.com)), en el panel de navegación, elija **Inventario de dispositivos**. 

2. Selecciona un dispositivo para abrir el panel desplegable y revisa la información que se muestra.

3. Seleccione los puntos suspensivos (**...**) para abrir el menú de acciones. 

4. Seleccione una acción, como Ejecutar examen **antivirus** o **Iniciar investigación automatizada**. 

## <a name="onboard-a-device"></a>Incorporación de un dispositivo

Consulta [Incorporar dispositivos a Microsoft Defender para empresas](mdb-onboard-devices.md).

## <a name="offboard-a-device"></a>Fuera de un dispositivo

Consulta [Offboarding a device](mdb-onboard-devices.md#offboarding-a-device).

## <a name="next-steps"></a>Pasos siguientes

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)

- [Crear o editar grupos de dispositivos](mdb-create-edit-device-groups.md)