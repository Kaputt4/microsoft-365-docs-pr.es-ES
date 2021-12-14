---
title: Comprender el orden de la directiva en Microsoft Defender para empresas (versión preliminar)
description: Obtenga información sobre el orden de prioridad con directivas en Microsoft Defender para empresas (versión preliminar)
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: efb246e07c7a55dbf71102f06e90fbbd9b0c202b
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423004"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business-preview"></a>Comprender el orden de la directiva en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Microsoft Defender para empresas (versión preliminar).

## <a name="policy-order-in-microsoft-defender-for-business"></a>Orden de directiva en Microsoft Defender para empresas

Microsoft Defender para empresas (versión preliminar) incluye directivas predefinidas para ayudar a garantizar que los dispositivos que usan los empleados estén protegidos. El equipo de seguridad también puede agregar nuevas directivas. Por ejemplo, supongamos que desea aplicar determinadas opciones de configuración a algunos dispositivos y otras configuraciones a otros dispositivos. Puede hacerlo agregando directivas, como directivas de protección de próxima generación o directivas de firewall.

A medida que se agregan directivas, observará que se asigna un orden de prioridad. Puede editar el orden de prioridad de las directivas que defina, pero no puede cambiar el orden de prioridad de las directivas predeterminadas. Por ejemplo, supongamos que para los dispositivos Windows cliente, tiene tres directivas de protección de próxima generación. En este caso, la directiva predeterminada es el número 3 de prioridad. Puede cambiar el orden de las directivas que están numeradas 1 y 2, pero la directiva predeterminada seguirá siendo el número 3 en la lista. 

**Lo importante que debe recordar acerca de varias directivas es que los dispositivos recibirán la primera directiva aplicada únicamente.** En referencia al ejemplo anterior de tres directivas de próxima generación, suponga que tiene dispositivos dirigidos por las tres directivas. En este caso, esos dispositivos recibirán la directiva número 1, pero no recibirán directivas numeradas 2 y 3. 

## <a name="key-points-to-remember-about-policy-order"></a>Puntos clave para recordar sobre el orden de directivas

- Las directivas tienen asignado un orden de prioridad

- Los dispositivos reciben solo la primera directiva aplicada

- Puede cambiar el orden de prioridad de las directivas

- Las directivas predeterminadas tienen el orden de prioridad más bajo

## <a name="next-steps"></a>Siguientes pasos

- [Introducción al uso de Defender para empresas (versión preliminar)](mdb-get-started.md)

- [Administrar dispositivos](mdb-manage-devices.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas (versión preliminar)](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)