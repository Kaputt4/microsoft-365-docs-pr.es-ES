---
title: Descripción del orden de la directiva en Microsoft Defender para Empresas
description: Obtenga información sobre el orden de prioridad con las directivas de Microsoft Defender para Empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 13e803666cc7af14af52031eb86a2f86edf06f80
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666314"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>Descripción del orden de la directiva en Microsoft Defender para Empresas

> [!IMPORTANT]
> Microsoft Defender para Empresas se está implementando para [Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender for Business como una suscripción independiente está en versión preliminar y se implementará gradualmente para los clientes y asociados de TI que [se registren aquí](https://aka.ms/mdb-preview) para solicitarla. La versión preliminar incluye un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a los productos o servicios preliminares que se pueden modificar sustancialmente antes de que se publiquen comercialmente. Microsoft no ofrece ninguna garantía, expresa o implícita, de la información que se proporciona aquí. 

## <a name="policy-order-in-microsoft-defender-for-business"></a>Orden de la directiva en Microsoft Defender para Empresas

Microsoft Defender para Empresas incluye directivas predefinidas para ayudar a garantizar que los dispositivos que usan los empleados estén protegidos. El equipo de seguridad también puede agregar nuevas directivas. Por ejemplo, supongamos que desea aplicar ciertas configuraciones a algunos dispositivos y configuraciones diferentes a otros dispositivos. Para ello, agregue directivas, como directivas de protección de próxima generación o directivas de firewall.

A medida que se agregan directivas, observará que se asigna un orden de prioridad. Puede editar el orden de prioridad de las directivas que defina, pero no puede cambiar el orden de prioridad de las directivas predeterminadas. Por ejemplo, supongamos que, para los dispositivos cliente Windows, tiene tres directivas de protección de próxima generación. En este caso, la directiva predeterminada es el número 3 en prioridad. Puede cambiar el orden de las directivas numeradas 1 y 2, pero la directiva predeterminada seguirá siendo el número 3 de la lista. 

**Lo importante que hay que recordar sobre varias directivas es que los dispositivos solo recibirán la primera directiva aplicada.** En referencia a nuestro ejemplo anterior de tres directivas de próxima generación, supongamos que tiene dispositivos destinados a las tres directivas. En este caso, esos dispositivos recibirán el número de directiva 1, pero no recibirán las directivas numeradas 2 y 3. 

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre Microsoft Defender para Empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="key-points-to-remember-about-policy-order"></a>Puntos clave para recordar sobre el orden de la directiva

- A las directivas se les asigna un orden de prioridad.

- Los dispositivos solo reciben la primera directiva aplicada.

- Puede cambiar el orden de prioridad de las directivas.

- Las directivas predeterminadas tienen el orden de prioridad más bajo.

## <a name="next-steps"></a>Siguientes pasos

- [Comenzar mediante Defender para empresas](mdb-get-started.md)

- [Administrar dispositivos](mdb-manage-devices.md)

- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)

- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)

- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)