---
title: Comprender el orden de la directiva en Microsoft Defender para empresas
description: Obtenga información sobre el orden de prioridad con las directivas de Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 1b2b171c6872cd7ff555a92bcd88b50fa0ff4880
ms.sourcegitcommit: 2697938d2d4fec523b501c5e7b0b8ec8f34e59b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2022
ms.locfileid: "63449181"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>Comprender el orden de la directiva en Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando [para Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

## <a name="policy-order-in-microsoft-defender-for-business"></a>Orden de directiva en Microsoft Defender para empresas

Microsoft Defender para empresas incluye directivas predefinidas para ayudar a garantizar que los dispositivos que usan los empleados estén protegidos. El equipo de seguridad también puede agregar nuevas directivas. Por ejemplo, supongamos que desea aplicar determinadas opciones de configuración a algunos dispositivos y otras configuraciones a otros dispositivos. Puede hacerlo agregando directivas, como directivas de protección de próxima generación o directivas de firewall.

A medida que se agregan directivas, observará que se asigna un orden de prioridad. Puede editar el orden de prioridad de las directivas que defina, pero no puede cambiar el orden de prioridad de las directivas predeterminadas. Por ejemplo, supongamos que para los dispositivos Windows cliente, tiene tres directivas de protección de próxima generación. En este caso, la directiva predeterminada es el número 3 de prioridad. Puede cambiar el orden de las directivas que están numeradas 1 y 2, pero la directiva predeterminada seguirá siendo el número 3 en la lista. 

**Lo importante que debe recordar acerca de varias directivas es que los dispositivos recibirán la primera directiva aplicada únicamente.** En referencia al ejemplo anterior de tres directivas de próxima generación, suponga que tiene dispositivos dirigidos por las tres directivas. En este caso, esos dispositivos recibirán la directiva número 1, pero no recibirán directivas numeradas 2 y 3. 

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="key-points-to-remember-about-policy-order"></a>Puntos clave para recordar sobre el orden de directivas

- Las directivas tienen asignado un orden de prioridad.

- Los dispositivos reciben solo la primera directiva aplicada.

- Puede cambiar el orden de prioridad de las directivas.

- Las directivas predeterminadas tienen el orden de prioridad más bajo.

## <a name="next-steps"></a>Siguientes pasos

- [Introducción al uso de Defender para empresas](mdb-get-started.md)

- [Administrar dispositivos](mdb-manage-devices.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)