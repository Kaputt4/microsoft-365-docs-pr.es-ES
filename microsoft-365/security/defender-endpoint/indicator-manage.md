---
title: Administrar indicadores
ms.reviewer: ''
description: Administre los indicadores de un hash de archivo, dirección IP, direcciones URL o dominios que definen la detección, prevención y exclusión de entidades.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: a1323215d1227377c5d801a162a3cc6e9b7ef359
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67700320"
---
# <a name="manage-indicators"></a>Administrar indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

1. En el panel de navegación, seleccione **Configuración** \> **Indicadores** de **puntos** \> de conexión (en **Reglas**).

2. Seleccione la pestaña del tipo de entidad que desea administrar.

3. Actualice los detalles del indicador y haga clic en **Guardar** o haga clic en el botón **Eliminar** si desea quitar la entidad de la lista.

## <a name="import-a-list-of-iocs"></a>Importación de una lista de ioC

También puede elegir cargar un archivo CSV que defina los atributos de los indicadores, la acción que se va a realizar y otros detalles.

Descargue el archivo CSV de ejemplo para conocer los atributos de columna admitidos.

1. En el panel de navegación, seleccione **Configuración** \> **Indicadores** de **puntos** \> de conexión (en **Reglas**).

2. Seleccione la pestaña del tipo de entidad para la que desea importar indicadores.

3. Seleccione **Importar** \> **Elija archivo**.

4. Seleccione **Importar**. Haga esto para todos los archivos que desea importar.

5. Seleccione **Listo**.

> [!NOTE]
> Solo se pueden cargar 500 indicadores para cada lote.

En la tabla siguiente se muestran los parámetros admitidos.

Parámetro|Tipo|Descripción
:---|:---|:---
indicatorType|Enum|Tipo del indicador. Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url". **Required**
indicatorValue|Cadena|Identidad de la entidad [Indicator](ti-indicator.md) . **Required**
acción|Enum|Acción que se realizará si el indicador se detectará en la organización. Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed". **Required**
title|Cadena|Título de alerta de indicador. **Required**
description|Cadena| Descripción del indicador. **Required**
expirationTime|DateTimeOffset|La hora de expiración del indicador con el siguiente formato AAAA-MM-DDTHH:MM:SS.0Z. El indicador se elimina si transcurre el tiempo de expiración y lo que ocurra en el momento de expiración se produce en el valor de segundos (SS). **Optional**
severity|Enum|Gravedad del indicador. Los valores posibles son: "Informativo", "Bajo", "Medio" y "Alto". **Optional**
recommendedActions|Cadena|Acciones recomendadas de alerta de indicador de TI. **Optional**
rbacGroups|Cadena|Lista separada por comas de grupos de RBAC a los que se aplicaría el indicador. **Optional**
categoría|Cadena|Categoría de la alerta. Algunos ejemplos son: Ejecución y acceso a credenciales. **Optional**
mitretechniques|Cadena|Código/id de técnicas de MITRE (separados por comas). Para obtener más información, consulte [Tácticas empresariales](https://attack.mitre.org/tactics/enterprise/). **Opcional** Se recomienda agregar un valor en la categoría cuando se trata de una técnica MITRE.
GenerateAlert|Cadena|Si se debe generar la alerta. Los valores posibles son: True o False. **Optional**

> [!NOTE]
> No se admite la notación de enrutamiento de Inter-Domain sin clase (CIDR) para direcciones IP.
Para obtener más información, consulte [Microsoft Defender para punto de conexión categorías de alertas ahora están alineadas con MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).

Vea este vídeo para obtener información sobre cómo Microsoft Defender para punto de conexión proporciona varias maneras de agregar y administrar indicadores de riesgo (IO). 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLVw]

## <a name="see-also"></a>Vea también

- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para los archivos](indicator-file.md)
- [Crear indicadores para direcciones IP y URL/dominios](indicator-ip-domain.md)
- [Creación de indicadores basados en certificados](indicator-certificates.md)
