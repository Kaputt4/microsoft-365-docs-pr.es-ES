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
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 8490793794d7cbd1ad7b3e660e2394edf870e2a7
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089636"
---
# <a name="understand-policy-order-in-microsoft-defender-for-business"></a>Descripción del orden de la directiva en Microsoft Defender para Empresas

## <a name="policy-order-in-microsoft-defender-for-business"></a>Orden de la directiva en Microsoft Defender para Empresas

Microsoft Defender para Empresas incluye directivas predefinidas para ayudar a garantizar que los dispositivos que usan los empleados estén protegidos. El equipo de seguridad también puede agregar nuevas directivas. Por ejemplo, supongamos que desea aplicar ciertas configuraciones a algunos dispositivos y configuraciones diferentes a otros dispositivos. Para ello, agregue directivas, como directivas de protección de próxima generación o directivas de firewall.

A medida que se agregan directivas, observará que se asigna un orden de prioridad. Puede editar el orden de prioridad de las directivas que defina, pero no puede cambiar el orden de prioridad de las directivas predeterminadas. Por ejemplo, supongamos que, para los dispositivos cliente Windows, tiene tres directivas de protección de próxima generación. En este caso, la directiva predeterminada es el número 3 en prioridad. Puede cambiar el orden de las directivas numeradas 1 y 2, pero la directiva predeterminada seguirá siendo el número 3 de la lista. 

**Lo importante que hay que recordar sobre varias directivas es que los dispositivos solo recibirán la primera directiva aplicada.** En referencia a nuestro ejemplo anterior de tres directivas de próxima generación, supongamos que tiene dispositivos destinados a las tres directivas. En este caso, esos dispositivos recibirán el número de directiva 1, pero no recibirán las directivas numeradas 2 y 3. 


## <a name="key-points-to-remember-about-policy-order"></a>Puntos clave para recordar sobre el orden de la directiva

- A las directivas se les asigna un orden de prioridad.
- Los dispositivos solo reciben la primera directiva aplicada.
- Puede cambiar el orden de prioridad de las directivas.
- Las directivas predeterminadas tienen el orden de prioridad más bajo.

## <a name="next-steps"></a>Pasos siguientes

- [Comenzar mediante Defender para empresas](mdb-get-started.md)
- [Administrar dispositivos](mdb-manage-devices.md)
- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)