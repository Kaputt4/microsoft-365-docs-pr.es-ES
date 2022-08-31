---
title: Paso 7. Promover el entorno de evaluación de Microsoft 365 Defender a Producción
description: Use este artículo para promover sus evals de MDI, MDO, MDE y Defender for Cloud Apps a su entorno activo en Microsoft 365 Defender o M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 018b8047ecce5dd4d41becb19ed779025715fe70
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479674"
---
# <a name="step-7-promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>Paso 7. Promover el entorno de evaluación de Microsoft 365 Defender a producción

**Se aplica a:**
- Microsoft 365 Defender

Para promover el entorno de evaluación de Microsoft 365 Defender a producción, primero compre la licencia necesaria. Siga los pasos descritos en [Creación del entorno eval](eval-create-eval-environment.md) y compra la licencia de Office 365 E5 (en lugar de seleccionar Iniciar evaluación gratuita).

A continuación, complete cualquier configuración adicional y expanda los grupos piloto hasta que hayan alcanzado la producción completa.

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity

Defender for Identity no requiere ninguna configuración adicional. Solo tiene que asegurarse de que ha adquirido las licencias necesarias e instalado el sensor en todos los controladores de dominio de Active Directory y servidores de Servicios de federación de Active Directory (AD FS) (AD FS).

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender para Office 365

Después de evaluar o probar correctamente MDO, se puede promover a todo el entorno de producción.

1. Compre y aprovisione las licencias necesarias y asígnelas a los usuarios de producción.
2. Vuelva a ejecutar las configuraciones de directiva de línea base recomendadas (estándar o estricta) en el dominio de correo electrónico de producción o en grupos específicos de usuarios.
3. Opcionalmente, cree y configure las directivas de MDO personalizadas en el dominio de correo electrónico de producción o los grupos de usuarios.  Sin embargo, recuerde que las directivas de línea base asignadas siempre tendrán prioridad sobre las directivas personalizadas.
4. Actualice el registro MX público del dominio de correo electrónico de producción para que se resuelva directamente en EOP.
5. Retire las puertas de enlace SMTP de terceros y deshabilite o elimine los conectores EXO asociados a esta retransmisión.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

Para promover Microsoft Defender para punto de conexión entorno de evaluación de un entorno piloto a producción, basta con incorporar más puntos de conexión al servicio mediante cualquiera de las [herramientas y métodos admitidos](../defender-endpoint/onboard-configure.md).

Use las siguientes directrices generales para incorporar más dispositivos a Microsoft Defender para punto de conexión.

1. Compruebe que el dispositivo cumple los [requisitos mínimos](../defender-endpoint/minimum-requirements.md).
2. En función del dispositivo, siga los pasos de configuración que se proporcionan en la sección de incorporación del portal de Defender para punto de conexión.
3. Use la herramienta de administración y el método de implementación adecuados para los dispositivos.
4. Ejecute una prueba de detección para comprobar que los dispositivos están incorporados correctamente e informando al servicio.

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps no requiere ninguna configuración adicional. Solo tiene que asegurarse de que ha comprado las licencias necesarias. Si ha limitado la implementación a determinados grupos de usuarios, aumente el ámbito de estos grupos hasta alcanzar la escala de producción.
