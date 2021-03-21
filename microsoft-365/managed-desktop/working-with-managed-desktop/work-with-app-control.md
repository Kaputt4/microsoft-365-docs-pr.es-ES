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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917645"
---
# <a name="work-with-app-control"></a>Usar el control de aplicaciones

Una vez implementado el control de la aplicación en el entorno, tanto tú como las operaciones de escritorio administrado de Microsoft tienen responsabilidades continuas. Por ejemplo, es posible que quieras agregar una nueva aplicación en el entorno o agregar (o quitar) un firmante de confianza. Para mejorar la seguridad, todas las aplicaciones deben estar firmadas con código antes de liberarlas a los usuarios. Los detalles del editor de una aplicación incluyen información sobre el firmante.


## <a name="add-a-new-app"></a>Agregar una nueva aplicación

Para agregar una nueva aplicación, sigue estos pasos:

1. Agregar la aplicación a [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).
2. Implementa la aplicación en cualquier dispositivo en el anillo de prueba. 
3. Prueba la aplicación según tus procesos empresariales estándar. 
4. Comprueba Visor de eventos en Registros de aplicaciones y **servicios\Microsoft\Windows\AppLocker** y busca cualquier **evento 8003** **o 8006.** Estos eventos indican que la aplicación se bloquearía. Para obtener más información acerca de todos los eventos de App Locker y sus significados, consulta [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Si encuentra alguno de estos eventos, abra una solicitud de firmante con Operaciones de escritorio administrado de Microsoft.

## <a name="add-or-remove-a-trusted-signer"></a>Agregar (o quitar) un firmante de confianza

Cuando abra una solicitud de firmante, primero deberá proporcionar algunos detalles importantes del editor. A continuación, siga estos pasos:

1. [Recopilar detalles del editor](#gather-publisher-details).
2. Abra un vale con Operaciones de escritorio administrado de Microsoft para solicitar la regla de firmante e incluya los siguientes detalles:  
    - Nombre de la aplicación 
    - Versión de la aplicación 
    - Descripción 
    - Tipo de cambio ("agregar" o "quitar")  
    - Detalles del publicador (por ejemplo: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Para quitar la confianza de una aplicación, siga los mismos pasos, pero establezca **Cambiar tipo** para *quitar*.

Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:


|Grupo de implementación  |Tipo de directiva  |Timing  |
|---------|---------|---------|
|Prueba     |  Auditoría       |  Día 0       |
|Primero     | Enforced        | Día 1        |
|Rápida     | Enforced        |  Día 2       |
|Amplias     | Enforced        |  Día 3       |


Puede pausar o revertir la implementación en cualquier momento durante el lanzamiento. Para ello, abra otra solicitud de servicio con Operations.

> [!NOTE]
> Si pausa la versión de una regla de firmante, esa regla debe revertirse o completarse antes de que se pueda iniciar otra implementación.

## <a name="gather-publisher-details"></a>Recopilar detalles del editor

Para obtener acceso a los datos del editor de una aplicación, siga estos pasos:

1. Busque un dispositivo de Escritorio administrado de Microsoft en el anillo De prueba que tenga aplicada una directiva de modo de auditoría. 
2. Intente instalar la aplicación en el dispositivo.
3. Abre el Visor de eventos en ese dispositivo. 
4. En el Visor de eventos, vaya **a Registros de aplicaciones y servicios\Microsoft\Windows** y, a continuación, seleccione **AppLocker**. 
5. Busque cualquier **evento 8003** **u 8006** y, a continuación, copie la información del evento: 
    - Nombre de la aplicación 
    - Versión de la aplicación 
    - Descripción 
    - Detalles del publicador (por ejemplo: "O= <publisher name> , L= <location> , S=State, C=Country")