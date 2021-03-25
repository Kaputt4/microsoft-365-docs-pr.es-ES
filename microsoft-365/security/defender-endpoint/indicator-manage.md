---
title: Administrar indicadores
ms.reviewer: ''
description: Administrar indicadores para un hash de archivo, dirección IP, direcciones URL o dominios que definen la detección, prevención y exclusión de entidades.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6edb4ddf764788a11ea3b6f1863dd95e694f1849
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075744"
---
# <a name="manage-indicators"></a>Administrar indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. En el panel de navegación, seleccione  >  **Indicadores de configuración**.

2. Seleccione la pestaña del tipo de entidad que desea administrar.  

3. Actualice los detalles del indicador y  haga clic en **Guardar** o haga clic en el botón Eliminar si desea quitar la entidad de la lista.

## <a name="import-a-list-of-iocs"></a>Importar una lista de iocs

También puede elegir cargar un archivo CSV que defina los atributos de los indicadores, la acción que se va a realizar y otros detalles.

Descargue el CSV de ejemplo para conocer los atributos de columna admitidos.

1. En el panel de navegación, seleccione  >  **Indicadores de configuración**.

2. Seleccione la pestaña del tipo de entidad para la que desea importar los indicadores.

3. Seleccione **Importar**  >  **elegir archivo**. 

4. Seleccione **Importar**. Haga esto para todos los archivos que desea importar. 

5. Seleccione **Listo**.

En la tabla siguiente se muestran los parámetros admitidos.

Parámetro | Tipo    |   Descripción
:---|:---|:---
indicatorType | Enum | Tipo del indicador. Los valores posibles son: "FileSha1", "FileSha256", "IpAddress", "DomainName" y "Url". **Required**
indicatorValue | Cadena | Identidad de la [entidad Indicator.](ti-indicator.md) **Required**
acción | Enum | La acción que se realizará si el indicador se detectará en la organización. Los valores posibles son: "Alert", "AlertAndBlock" y "Allowed". **Required**
title | Cadena | Título de alerta del indicador. **Required**
description | Cadena |  Descripción del indicador. **Required**
expirationTime | DateTimeOffset | La hora de expiración del indicador con el siguiente formato YYYY-MM-DDTHH:MM:SS.0Z. **Optional**
severity | Enum | Gravedad del indicador. Los valores posibles son: "Informational", "Low", "Medium" y "High". **Optional**
recommendedActions | Cadena | Acciones recomendadas de alerta del indicador TI. **Optional**
rbacGroupNames | Cadena | Lista separada por comas de nombres de grupo RBAC a los que se aplicaría el indicador. **Optional**
categoría | Cadena | Categoría de la alerta. Algunos ejemplos son: Ejecución y acceso a credenciales. **Optional**
mitretechniques| Cadena | Código/id de técnicas MITRE (separados por comas). Para obtener más información, vea [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/). **Opcional** Se recomienda agregar un valor en categoría cuando se utiliza una técnica MITRE.

Para obtener más información, vea Microsoft Defender para las categorías de alertas de punto de conexión ahora están alineadas con [MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).


## <a name="see-also"></a>Ver también
- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para archivos](indicator-file.md)
- [Crear indicadores para direcciones IP y direcciones URL/dominios](indicator-ip-domain.md)
- [Crear indicadores basados en certificados](indicator-certificates.md)
