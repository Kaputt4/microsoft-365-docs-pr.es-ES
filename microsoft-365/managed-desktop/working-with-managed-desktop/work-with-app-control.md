---
title: Usar el control de aplicaciones
description: Aprende a administrar el control de aplicaciones.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 99979a08a67245d471b33ce26e4b7f35790fead5
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569917"
---
# <a name="work-with-app-control"></a>Usar el control de aplicaciones

Una vez que el control de la aplicación se ha implementado en el entorno, tanto tú como Microsoft Managed Desktop operaciones tienen responsabilidades continuas. Por ejemplo, es posible que quieras agregar una nueva aplicación en el entorno o agregar (o quitar) un firmante de confianza. Para mejorar la seguridad, todas las aplicaciones deben estar firmadas con código antes de liberarlas a los usuarios. Los detalles del editor de una aplicación incluyen información sobre el firmante.

## <a name="add-a-new-app"></a>Agregar una nueva aplicación

**Para agregar una nueva aplicación:**

1. Agrega la aplicación a [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).
1. Implementa la aplicación en cualquier dispositivo en el anillo de prueba.
1. Prueba la aplicación según tus procesos empresariales estándar.
1. Compruebe el Visor de eventos **en Registros de aplicaciones y servicios\Microsoft\Windows\AppLocker**. Busque cualquier **evento 8003** u **8006** . Estos eventos indican que la aplicación se bloquearía. Para obtener más información sobre todos los eventos de App Locker y sus significados, [consulta Usar Visor de eventos con AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
1. Si encuentra alguno de estos eventos, abra una solicitud de firmante con Microsoft Managed Desktop operations.

## <a name="add-or-remove-a-trusted-signer"></a>Agregar (o quitar) un firmante de confianza

Cuando abra una solicitud de firmante, primero deberá proporcionar algunos detalles importantes del editor.

**Para agregar (o quitar) un firmante de confianza:**

1. [Recopilar detalles del editor](#gather-publisher-details).
1. Abra un vale con Microsoft Managed Desktop operaciones para solicitar la regla de firmante e incluya los siguientes detalles:  
    - Nombre de la aplicación
    - Versión de la aplicación
    - Descripción
    - Tipo de cambio ("agregar" o "quitar")  
    - Publisher detalles (por ejemplo: `O=<publisher name>,L=<location>,S=State,C=Country`)

> [!NOTE]
> Para quitar la confianza de una aplicación, sigue los mismos pasos, pero establece **el tipo Cambiar** para *quitar*.

Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:

|Grupo de implementación|Tipo de directiva|Timing|
|---|---|---|
|Prueba|Auditoría|Día 0|
|Primero|Enforced|Día 1|
|Rápida|Enforced|Día 2|
|Amplias|Enforced|Día 3|

Puede pausar o revertir la implementación en cualquier momento durante el lanzamiento. Para pausar o revertir, abra otra solicitud de soporte técnico con Microsoft Managed Desktop operaciones.

> [!NOTE]
> Si pausa la versión de una regla de firmante, esa regla debe revertirse o completarse antes de que se pueda iniciar otra implementación.

## <a name="gather-publisher-details"></a>Recopilar detalles del editor

**Para obtener acceso a los datos del publicador de una aplicación:**

1. Busque un Microsoft Managed Desktop en el anillo de prueba que tenga aplicada una directiva de modo de auditoría.
1. Intente instalar la aplicación en el dispositivo.
1. Abre el Visor de eventos en ese dispositivo.
1. En el Visor de eventos, vaya **a Registros de aplicaciones y servicios\Microsoft\Windows** y, a continuación, **seleccione AppLocker**.
1. Busque cualquier **evento 8003** **u 8006** y, a continuación, copie la información del evento:
    - Nombre de la aplicación
    - Versión de la aplicación
    - Descripción
    - Publisher detalles (por ejemplo: `O=<publisher name>, L=<location>, S=State, C=Country`)
