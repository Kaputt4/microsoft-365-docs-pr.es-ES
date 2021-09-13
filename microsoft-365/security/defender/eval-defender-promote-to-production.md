---
title: Promover el entorno Microsoft 365 Defender evaluación a Producción
description: Use este artículo para promover las evales de MDI, MDO, MDE y MCAS a su entorno vivo en Microsoft 365 Defender o M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 51b03ebf277583541fc86bdbd80535704929fcf3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219997"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>Promover el entorno Microsoft 365 Defender evaluación a la producción

**Se aplica a:**
- Microsoft 365 Defender

Para promover el entorno Microsoft 365 Defender evaluación a la producción, primero compre la licencia necesaria. Siga los pasos de [Crear el entorno de eval](eval-create-eval-environment.md) y compre la Office 365 E5 licencia (en lugar de seleccionar Iniciar prueba gratuita).

A continuación, complete cualquier configuración adicional y expanda los grupos piloto hasta que estos lleguen a la producción completa. 

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Defender for Identity no requiere ninguna configuración adicional. Solo asegúrate de haber comprado las licencias necesarias e instalado el sensor en todos los controladores de dominio de Active Directory y servidores de Servicios de federación de Active Directory (AD FS). 

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender para Office 365
Después de evaluar o pilotar MDO correctamente, se puede promover a todo el entorno de producción.
1. Compre y aprovisione las licencias necesarias y asígnelas a los usuarios de producción.
2. Vuelva a ejecutar las configuraciones de directiva de línea base recomendadas (estándar o estricta) en el dominio de correo electrónico de producción o grupos específicos de usuarios.
3. Si lo desea, cree y configure cualquier directiva MDO personalizada en su dominio de correo electrónico de producción o grupos de usuarios.  Sin embargo, recuerde que las directivas de línea base asignadas siempre tendrán prioridad sobre las directivas personalizadas.
4. Actualice el registro MX público del dominio de correo electrónico de producción para resolverlo directamente en EOP.
5. Retirar las puertas de enlace SMTP de terceros y deshabilitar o eliminar los conectores EXO asociados con esta retransmisión.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión
Para promover el entorno de evaluación de Microsoft Defender para endpoints de un entorno piloto a la producción, simplemente incorpore más puntos de conexión al servicio con cualquiera de las herramientas y métodos [admitidos.](../defender-endpoint/onboard-configure.md)

Usa las siguientes directrices generales para incorporar más dispositivos a Microsoft Defender para endpoint. 

1. Compruebe que el dispositivo cumple los [requisitos mínimos](../defender-endpoint/minimum-requirements.md).
2. Según el dispositivo, siga los pasos de configuración proporcionados en la sección incorporación del portal defender para endpoints.
3. Usa la herramienta de administración y el método de implementación adecuados para tus dispositivos.
4.  Ejecute una prueba de detección para comprobar que los dispositivos están correctamente incorporados e informando al servicio.

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security no requiere ninguna configuración adicional. Solo asegúrate de haber comprado las licencias necesarias. Si ha definido el ámbito de la implementación en determinados grupos de usuarios, aumente el ámbito de estos grupos hasta que alcance la escala de producción. 

