---
title: Descripción del orden de la directiva en Microsoft Defender para Empresas
description: Obtenga información sobre el orden de prioridad con las directivas de ciberseguridad para proteger los dispositivos de la empresa con Defender for Business.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 4d3f2f7a04891fdf3e08f06d6744894e18e944dd
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67320358"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>Descripción del orden de la directiva en Microsoft Defender para Empresas

## <a name="policy-order-in-defender-for-business"></a>Orden de directiva en Defender para empresas

Defender for Business incluye directivas predefinidas para ayudar a garantizar que los dispositivos que usan los empleados están protegidos. El equipo de seguridad también puede agregar nuevas directivas. Por ejemplo, supongamos que desea aplicar ciertas configuraciones a algunos dispositivos y configuraciones diferentes a otros dispositivos. Para ello, agregue directivas, como directivas de protección de próxima generación o directivas de firewall.

A medida que se agregan directivas, observará que se asigna un orden de prioridad. Puede editar el orden de prioridad de las directivas que defina, pero no puede cambiar el orden de prioridad de las directivas predeterminadas. Por ejemplo, supongamos que, para los dispositivos cliente de Windows, tiene tres directivas de protección de próxima generación. En este caso, la directiva predeterminada es el número 3 en prioridad. Puede cambiar el orden de las directivas numeradas 1 y 2, pero la directiva predeterminada seguirá siendo el número 3 de la lista. 

**Lo importante que hay que recordar sobre varias directivas es que los dispositivos solo recibirán la primera directiva aplicada.** En referencia a nuestro ejemplo anterior de tres directivas de próxima generación, supongamos que tiene dispositivos destinados a las tres directivas. En este caso, esos dispositivos recibirán el número de directiva 1, pero no recibirán las directivas numeradas 2 y 3. 

## <a name="key-points-to-remember-about-policy-order"></a>Puntos clave para recordar sobre el orden de la directiva

- A las directivas se les asigna un orden de prioridad.
- Los dispositivos solo reciben la primera directiva aplicada.
- Puede cambiar el orden de prioridad de las directivas.
- Las directivas predeterminadas tienen el orden de prioridad más bajo.

## <a name="next-steps"></a>Siguientes pasos

- [Introducción al uso de Defender para empresas](mdb-get-started.md)
- [Administrar dispositivos](mdb-manage-devices.md)
- [Visualización y administración de incidentes en Defender para empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Defender para empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)