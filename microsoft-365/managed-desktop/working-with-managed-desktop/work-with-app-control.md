---
title: Usar el control de aplicaciones
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430452"
---
# <a name="work-with-app-control"></a>Usar el control de aplicaciones

Una vez que se haya implementado el control de aplicaciones en el entorno, tanto usted como las operaciones de escritorio administradas de Microsoft tienen responsabilidades en curso. Por ejemplo, es posible que quiera agregar una nueva aplicación en el entorno o agregar (o quitar) un firmante de confianza. Para mejorar la seguridad, todas las aplicaciones deben estar firmadas con código antes de liberarlas a los usuarios finales. Los detalles del publicador de una aplicación incluyen información sobre el firmante.


## <a name="add-a-new-app"></a>Agregar una nueva aplicación

Para agregar una nueva aplicación, siga estos pasos:

1. Agregue la aplicación a [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).
2. Implemente la aplicación en cualquier dispositivo en el anillo de prueba. 
3. Pruebe la aplicación de acuerdo con los procesos de negocio estándar. 
4. Consulte el visor de eventos en **aplicaciones y servicios Logs\Microsoft\Windows\AppLocker**, buscando los eventos **8003** o **8006** . Estos eventos indican que la aplicación estaría bloqueada. Para obtener más información sobre todos los eventos del bloqueador de aplicaciones y sus significados, vea [using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Si encuentra alguno de estos eventos, abra una solicitud de firmante con Microsoft Managed Desktop Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Agregar (o quitar) un firmante de confianza

Al abrir una solicitud de firmante, primero deberá proporcionar algunos detalles importantes de Publisher. A continuación, siga estos pasos:

1. [Recopilar detalles de Publisher](#gather-publisher-details).
2. Abra un vale con las operaciones de escritorio administradas de Microsoft para solicitar la regla de firmante e incluya los siguientes detalles:  
    - Nombre de la aplicación 
    - Versión de la aplicación 
    - Descripción 
    - Tipo de cambio ("agregar" o "quitar")  
    - Detalles de la editorial (por ejemplo: "O = <publisher name> , L = <location> , S = estado, C = país") 

> [!NOTE]
> Para quitar la confianza de una aplicación, siga los mismos pasos, pero establezca **tipo de cambio** en *quitar*.

Las operaciones implementarán progresivamente las directivas en los grupos de implementación siguiendo esta programación:


|Grupo de implementación  |Tipo de directiva  |Timing  |
|---------|---------|---------|
|Prueba     |  Auditoría       |  Día 0       |
|Primero     | Enforced        | Día 1        |
|Rápida     | Enforced        |  Día 2       |
|Amplias     | Enforced        |  Día 3       |


Puede pausar o revertir la implementación en cualquier momento durante la ejecución. Para ello, abra otra solicitud de servicio con operaciones.

> [!NOTE]
> Si pausa la liberación de una regla de firmante, dicha regla debe revertirse o completarse antes de que se pueda iniciar otra implementación.

## <a name="gather-publisher-details"></a>Recopilar detalles de Publisher

Para obtener acceso a los datos de Publisher para una aplicación, siga estos pasos:

1. Busque un dispositivo de escritorio administrado por Microsoft en el anillo de prueba que tiene una directiva de modo de auditoría aplicada. 
2. Intente instalar la aplicación en el dispositivo.
3. Abra el visor de eventos en ese dispositivo. 
4. En el visor de eventos, vaya a **Logs\Microsoft\Windows de servicios y aplicaciones**y, a continuación, seleccione **AppLocker**. 
5. Busque cualquier evento **8003** o **8006** y, a continuación, copie la información del evento: 
    - Nombre de la aplicación 
    - Versión de la aplicación 
    - Descripción 
    - Detalles de la editorial (por ejemplo: "O = <publisher name> , L = <location> , S = estado, C = país") 
