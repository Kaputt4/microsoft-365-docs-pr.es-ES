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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289464"
---
# <a name="work-with-app-control"></a>Usar el control de aplicaciones

Una vez implementado el control de aplicaciones en su entorno, tanto usted como las operaciones de escritorio administrado de Microsoft tienen responsabilidades continuas. Por ejemplo, es posible que desee agregar una nueva aplicación en el entorno o agregar (o quitar) un firmante de confianza. Para mejorar la seguridad, todas las aplicaciones deben estar firmadas con código antes de publicarlas para los usuarios. Los detalles del editor de una aplicación incluyen información sobre el firmante.


## <a name="add-a-new-app"></a>Agregar una nueva aplicación

Para agregar una nueva aplicación, sigue estos pasos:

1. Agregue la aplicación a [Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)
2. Implementa la aplicación en cualquier dispositivo del anillo de prueba. 
3. Prueba la aplicación de acuerdo con los procesos de negocio estándar. 
4. Comprueba el Visor de eventos en Registros de aplicaciones y **servicios\Microsoft\Windows\AppLocker** y busca cualquier evento **8003** **u 8006.** Estos eventos indican que la aplicación se bloquearía. Para obtener más información sobre todos los eventos de app Locker y sus significados, consulta Usar el Visor [de eventos con AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)
5. Si encuentra cualquiera de estos eventos, abra una solicitud de firmante con Operaciones de escritorio administrado de Microsoft.

## <a name="add-or-remove-a-trusted-signer"></a>Agregar (o quitar) un firmante de confianza

Cuando abras una solicitud de firmante, primero deberás proporcionar algunos detalles importantes del editor. A continuación, siga estos pasos:

1. [Recopilar detalles del editor.](#gather-publisher-details)
2. Abra un vale con operaciones de escritorio administrado de Microsoft para solicitar la regla de firmante e incluir los siguientes detalles:  
    - Nombre de la aplicación 
    - Versión de la aplicación 
    - Description 
    - Tipo de cambio ("agregar" o "quitar")  
    - Detalles del editor (por ejemplo: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Para quitar la confianza de una aplicación, siga los mismos pasos, pero establezca **Cambiar tipo** para *quitar.*

Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:


|Grupo de implementación  |Tipo de directiva  |Timing  |
|---------|---------|---------|
|Prueba     |  Auditoría       |  Día 0       |
|Primero     | Enforced        | Día 1        |
|Rápida     | Enforced        |  Día 2       |
|Amplias     | Enforced        |  Día 3       |


Puedes pausar o revertir la implementación en cualquier momento durante la implementación. Para ello, abra otra solicitud de servicio con Operations.

> [!NOTE]
> Si pausa la publicación de una regla de firmante, dicha regla debe revertirse o completarse antes de que se pueda iniciar otra implementación.

## <a name="gather-publisher-details"></a>Recopilar detalles del editor

Para acceder a los datos de editor de una aplicación, sigue estos pasos:

1. Busca un dispositivo de Escritorio administrado de Microsoft en el anillo de prueba al que se haya aplicado una directiva de modo auditoría. 
2. Intenta instalar la aplicación en el dispositivo.
3. Abre el Visor de eventos en ese dispositivo. 
4. En el Visor de eventos, ve a Registros de **aplicaciones y servicios\Microsoft\Windows** y, a continuación, **selecciona AppLocker**. 
5. Busque cualquier **evento 8003** **u 8006** y, a continuación, copie la información del evento: 
    - Nombre de la aplicación 
    - Versión de la aplicación 
    - Description 
    - Detalles del editor (por ejemplo: "O= <publisher name> , L= <location> , S=State, C=Country") 
