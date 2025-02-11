---
title: Office 365 puntos de conexión del DOD del Gobierno de EE. UU.
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/29/2022
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
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
description: Office 365 requiere conectividad a Internet. Los puntos de conexión siguientes solo deben ser accesibles para los clientes que usan Office 365 planes doD del Gobierno de EE. UU.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83b6bf838ee4422a4b54f2e6f7df73a3a987bcdd
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68201051"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 puntos de conexión del DoD del Gobierno de EE. UU.

*Se aplica a: Office 365 Admin*

Office 365 requiere conectividad a Internet. Los puntos de conexión siguientes solo deben ser accesibles para los clientes que usan Office 365 planes doD del Gobierno de EE. UU.
  
**puntos de conexión Office 365:** [en todo el mundo (incluido GCC)](urls-and-ip-address-ranges.md) \| [Office 365 opera 21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| *Office 365 U.S. Government DoD* \| [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)

<br>
****

|Notas|Descargar|
|---|---|
|**Última actualización:** 29/09/2022 - ![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Suscripción del registro de cambios](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Descargar:** la lista completa en [formato JSON](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|
|

Comience por [Administración de puntos de conexión de Office 365](managing-office-365-endpoints.md) conocer nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de los puntos de conexión se actualizan según sea necesario al principio de cada mes con las nuevas direcciones IP y direcciones URL publicadas 30 días antes de su actividad. Esto permite a los clientes que aún no tienen actualizaciones automatizadas completar sus procesos antes de que se requiera una nueva conectividad. Los datos de punto de conexión también pueden actualizarse durante el mes si es necesario para administrar las solicitudes de soporte técnico, los incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que se muestran en la página siguiente se generan a partir de los servicios web basados en REST. Si usa un script o un dispositivo de red para acceder a estos datos, debe ir directamente al [servicio web](microsoft-365-ip-web-service.md) .

Los datos de puntos de conexión siguientes enumeran los requisitos de conectividad desde el equipo de un usuario a Office 365. No incluye conexiones de red de Microsoft a una red de cliente, a veces denominadas conexiones de red híbridas o entrantes. Para obtener más información, consulte [Puntos de conexión adicionales no incluidos en el servicio web](additional-office365-ip-addresses-and-urls.md).

The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.

Estas son columnas de datos que se muestran:

- **ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.

- **Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer sobre estas categorías e instrucciones para administrarlas en [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). En esta columna también se enumeran los conjuntos de puntos de conexión necesarios para tener conectividad de red. En el caso de los conjuntos de puntos de conexión que no son necesarios para tener conectividad de red, se proporcionan notas en este campo para indicar qué funcionalidad faltaría si el conjunto de puntos de conexión está bloqueado. Si excluye un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no requieren conectividad.

- **ER**: esto es **Sí** si el conjunto de puntos de conexión se admite a través de Azure ExpressRoute con prefijos de ruta Office 365. La comunidad BGP que incluye los prefijos de ruta que se muestran se alinea con el área de servicio enumerada. Cuando ER es **No**, esto significa que ExpressRoute no se admite para este conjunto de puntos de conexión. Sin embargo, no se debe suponer que no se anuncia ninguna ruta para un conjunto de puntos de conexión donde ER es **No**. Si tiene previsto usar Azure AD Connect, lea la [sección consideraciones especiales](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) para asegurarse de que tiene la configuración de Azure AD Connect adecuada.

- **Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.

- **Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.

[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Notas sobre esta tabla:

- El Centro de seguridad y cumplimiento (SCC) proporciona compatibilidad con Azure ExpressRoute para Office 365. Lo mismo se aplica a muchas características expuestas a través del SCC, como informes, auditoría, exhibición de documentos electrónicos (Premium), DLP unificada y gobernanza de datos. Dos características específicas, importación de PST y exportación de exhibición de documentos electrónicos, actualmente no admiten Azure ExpressRoute con solo filtros de ruta de Office 365 debido a su dependencia en Azure Blob Storage. Para consumir esas características, necesita conectividad independiente para Azure Blob Storage mediante cualquier opción de conectividad de Azure compatible, que incluya conectividad a Internet o Azure ExpressRoute con filtros de ruta pública de Azure. Tiene que evaluar el establecimiento de dicha conectividad para ambas características. El equipo de Office 365 Information Protection es consciente de esta limitación y está trabajando activamente para ofrecer compatibilidad con Azure ExpressRoute para Office 365 tan limitado a Office 365 filtros de ruta para ambas características.

- Hay puntos de conexión opcionales adicionales para Aplicaciones Microsoft 365 para empresas que no aparecen en la lista y no son necesarios para que los usuarios inicien Aplicaciones Microsoft 365 para empresas aplicaciones y editen documentos. Los puntos de conexión opcionales se hospedan en centros de datos de Microsoft y no procesan, transmiten ni almacenan datos de clientes. Se recomienda que las conexiones de usuario a estos puntos de conexión se dirijan al perímetro de salida de Internet predeterminado.
