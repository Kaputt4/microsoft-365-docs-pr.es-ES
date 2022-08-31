---
title: Tipos de datos y filtros admitidos en modo guiado para la búsqueda en Microsoft 365 Defender
description: Refine la consulta mediante las distintas funcionalidades de modo guiado en la búsqueda avanzada en Microsoft 365 Defender.
keywords: modo guiado, búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: d3b8373743fc742a0d9c4cd83f99101618a3ef6c
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67475591"
---
# <a name="refine-your-query-in-guided-mode"></a>Refinar la consulta en modo guiado 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.
## <a name="use-different-data-types"></a>Uso de tipos de datos diferentes

La búsqueda avanzada en modo guiado admite varios tipos de datos que puede usar para ajustar la consulta.

- Números<br>
![Captura de pantalla de números como tercera condición](../../media/guided-hunting/data-numbers.png)

- Cadenas<br>
![Captura de pantalla de cadenas como tercera condición](../../media/guided-hunting/data-strings.png)

   En el cuadro de texto libre, escriba el valor y presione **Entrar** para agregarlo. Tenga en cuenta que el delimitador entre valores es **Entrar**.<br>

   ![Captura de pantalla que muestra las diferentes condiciones que puede usar](../../media/guided-hunting/data-strings-2.png)

- Boolean<br>
![Captura de pantalla de valores booleanos como tercera condición](../../media/guided-hunting/boolean.png)


- Datetime<br>
![Captura de pantalla de valores datetime como tercera condición](../../media/guided-hunting/data-datetime.png)


- Lista cerrada: no es necesario recordar el valor exacto que está buscando. Puede elegir fácilmente entre una lista cerrada sugerida que admita la selección múltiple.<br>
![Captura de pantalla de una lista cerrada usada como tercera condición](../../media/guided-hunting/data-closed.png)


## <a name="use-subgroups"></a>Uso de subgrupos
Para crear grupos de condiciones, haga clic en **Agregar subgrupo**:

![Captura de pantalla que resalta el botón Agregar subgrupo](../../media/guided-hunting/subgroup-1.png)

![Captura de pantalla que muestra el uso de subgrupos](../../media/guided-hunting/subgroup-2.png)

## <a name="use-smart-auto-complete-for-search"></a>Uso del autocompletar inteligente para la búsqueda
Se admite la autocompletar inteligente para buscar dispositivos y cuentas de usuario. No es necesario recordar el identificador de dispositivo, el nombre completo del dispositivo o el nombre de la cuenta de usuario. Puede empezar a escribir los primeros caracteres del dispositivo o usuario que está buscando y aparece una lista sugerida desde la que puede elegir lo que necesita:

![Captura de pantalla en la que se muestra el soporte técnico de autocompletar inteligente](../../media/guided-hunting/smart-auto.png)

## <a name="use-eventtype"></a>Use `EventType`
Incluso puede buscar tipos de eventos específicos, como todos los inicios de sesión con errores, eventos de modificación de archivos o conexiones de red correctas mediante el filtro **EventType** en cualquier sección donde sea aplicable.

Por ejemplo, si desea agregar una condición que busque eliminaciones de valores del Registro, puede ir a la sección **Eventos del Registro** y seleccionar **EventType**.

![Captura de pantalla de varios eventtypes](../../media/guided-hunting/hunt-specific-events-1.png)

Seleccionar EventType en Eventos del Registro le permite elegir entre diferentes eventos del Registro, incluido el que está buscando, **RegistryValueDeleted**.

![Captura de pantalla de EventType RegistryValueDeleted](../../media/guided-hunting/hunt-specific-events-2.png)

>[!NOTE] 
>`EventType` es el equivalente de en el esquema de `ActionType` datos, con el que los usuarios del modo avanzado podrían estar más familiarizados.

## <a name="test-your-query-with-a-smaller-sample-size"></a>Prueba de la consulta con un tamaño de ejemplo más pequeño
Si sigue trabajando en la consulta y desea ver su rendimiento y algunos resultados de ejemplo rápidamente, ajuste el número de registros que se devolverán seleccionando un conjunto más pequeño a través del menú desplegable **Tamaño de** ejemplo. 
 
![Captura de pantalla del menú desplegable tamaño de ejemplo](../../media/guided-hunting/smaller-sample.png)

El tamaño de ejemplo se establece en 10 000 resultados de forma predeterminada. Este es el número máximo de registros que se pueden devolver en la búsqueda. Sin embargo, se recomienda reducir el tamaño de la muestra a 10 o 100 para probar rápidamente la consulta, ya que al hacerlo se consumen menos recursos mientras sigue trabajando para mejorar la consulta.

A continuación, una vez finalizada la consulta y lista para usarla para obtener todos los resultados pertinentes para la actividad de búsqueda, asegúrese de que el tamaño de la muestra está establecido en 10 000, el máximo.

## <a name="switch-to-advanced-mode-after-building-a-query"></a>Cambiar al modo avanzado después de compilar una consulta
Puede hacer clic en **Editar en KQL** para ver la consulta KQL generada por las condiciones seleccionadas. La edición en KQL abre una nueva pestaña en modo avanzado, con la consulta KQL correspondiente:

![Captura de pantalla que resalta el botón Editar en KQL](../../media/guided-hunting/switch-to-advanced.png)

![Captura de pantalla que muestra la misma consulta de guiada a avanzada](../../media/guided-hunting/switch-to-advanced-2.png)

En el ejemplo anterior, la vista seleccionada es Todo, por lo que puede ver que la consulta KQL busca en todas las tablas que tienen propiedades de archivo de nombre y SHA256, y en todas las columnas pertinentes que cubren estas propiedades. 

Si cambia la vista a **Correos electrónicos & colaboración**, la consulta se reduce a:

![Captura de pantalla que muestra la misma consulta de guiada a avanzada, pero con dominio limitado](../../media/guided-hunting/switch-to-advanced-3.png)

## <a name="see-also"></a>Vea también
 - [Cuotas de búsqueda avanzadas y parámetros de uso](advanced-hunting-limits.md)
 - [Ampliación de la cobertura de búsqueda avanzada con la configuración adecuada](advanced-hunting-extend-data.md)