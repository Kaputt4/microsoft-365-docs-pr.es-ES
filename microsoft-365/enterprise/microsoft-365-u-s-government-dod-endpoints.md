---
title: Office 365 puntos de conexión del DOD del gobierno de EE. UU.
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 02/28/2022
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: Office 365 requiere conectividad a Internet. Los puntos de conexión siguientes deben ser accesibles para los clientes que usan Office 365 solo planes de DoD del gobierno de Estados Unidos.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 000ae3590b0c99b59f557e6b70deaa60649054a6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325649"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 puntos de conexión de DoD del gobierno de EE. UU.

*Se aplica a: Office 365 Admin*

Office 365 requiere conectividad a Internet. Los puntos de conexión siguientes deben ser accesibles para los clientes que usan Office 365 solo planes de DoD del gobierno de Estados Unidos.
  
**Office 365** de conexión: Office 365 mundial (incluido GCC [)](urls-and-ip-address-ranges.md) \| operado por [21 Office 365](urls-and-ip-address-ranges-21vianet.md) \|  \| Dedo del Gobierno de los Estados [Unidos Office 365](microsoft-365-u-s-government-gcc-high-endpoints.md) high de administración GCC Estados Unidos

<br>

****

|Notas|Descargar|
|---|---|
|**Last updated:** 02/28/2022 - ![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Suscripción del registro de cambios](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Descargar: la** lista completa en [formato JSON](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|
|

Comience por [Administración de puntos de conexión de Office 365](managing-office-365-endpoints.md) conocer nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de los puntos de conexión se actualizan según sea necesario al principio de cada mes con las nuevas direcciones IP y direcciones URL publicadas 30 días antes de su actividad. Esto permite a los clientes que aún no tienen actualizaciones automatizadas completar sus procesos antes de que se requiera nueva conectividad. Los datos de punto de conexión también pueden actualizarse durante el mes si es necesario para administrar las solicitudes de soporte técnico, los incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que se muestran en la página siguiente se generan a partir de los servicios web basados en REST. Si usa un script o un dispositivo de red para tener acceso a estos datos, debería ir al [servicio web](microsoft-365-ip-web-service.md) directamente.

Los datos de puntos de conexión siguientes enumeran los requisitos de conectividad desde el equipo de un usuario a Office 365. No incluye conexiones de red de Microsoft a una red de clientes, a veces denominadas conexiones de red híbridas o entrantes. Para obtener más información, consulte [Puntos de conexión adicionales no incluidos en el servicio web](additional-office365-ip-addresses-and-urls.md).

Los puntos de conexión se agrupan en cuatro áreas de servicio. Las tres primeras se pueden seleccionar por separado para la conectividad; la cuarta área de servicio es una dependencia común (denominada de Microsoft 365 Common y Office) y debe disponer de conectividad de red en todo momento.

Estas son columnas de datos que se muestran:

- **ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.

- **Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer sobre estas categorías y encontrar indicaciones para su administración en [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.

- **ER**: Esto es **Sí si** el conjunto de puntos de conexión es compatible con Azure ExpressRoute con Office 365 de ruta. La comunidad BGP que incluye los prefijos de ruta que se muestran se alinea con el área de servicio enumerada. Cuando ER es **No**, esto significa que ExpressRoute no es compatible con este conjunto de puntos de conexión. Sin embargo, no se debe suponer que no se anuncia ninguna ruta para un conjunto de puntos de conexión donde ER es **No**. Si tiene previsto usar Azure AD Conectar, lea la sección consideraciones [especiales](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) para asegurarse de que tiene la configuración Azure AD Conectar adecuada.

- **Direcciones**: enumera los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.

- **Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.

[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Notas sobre esta tabla:

- El Centro de seguridad y cumplimiento (SCC) proporciona compatibilidad con Azure ExpressRoute para Office 365. Lo mismo se aplica a muchas características expuestas a través del SCC, como informes, auditoría, Advanced eDiscovery, DLP unificada y gobierno de datos. Dos características específicas, PST Import y eDiscovery Export, actualmente no admiten Azure ExpressRoute con solo filtros de ruta Office 365 debido a su dependencia de Azure Blob Storage. Para consumir estas características, necesita conectividad independiente a Azure Blob Storage con cualquier opción de conectividad de Azure compatible, que incluya conectividad a Internet o Azure ExpressRoute con filtros de ruta pública de Azure. Debe evaluar el establecimiento de dicha conectividad para ambas características. El equipo de Office 365 Information Protection es consciente de esta limitación y está trabajando activamente para proporcionar compatibilidad con Azure ExpressRoute para Office 365 limitado Office 365 filtros de ruta para ambas características.

- Hay puntos de conexión opcionales adicionales para Aplicaciones Microsoft 365 para empresas que no se enumeran y no son necesarios para que los usuarios inicien Aplicaciones Microsoft 365 para empresas aplicaciones y editan documentos. Los puntos de conexión opcionales se hospedan en centros de datos de Microsoft y no procesan, transmiten ni almacenan datos de clientes. Se recomienda que las conexiones de usuario a estos puntos de conexión se dirijan al perímetro predeterminado de salida de Internet.
