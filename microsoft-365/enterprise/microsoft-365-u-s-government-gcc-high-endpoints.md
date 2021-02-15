---
title: Puntos de conexión de Office 365 U.S. Government GCC High
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/15/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid: MET150
ms.assetid: cbd2369c-fd96-464c-bf48-c99826b459ee
description: En este artículo, encontrará puntos de conexión accesibles para los clientes que usan los planes GCC High de Office 365 U.S. Government.
hideEdit: true
ms.openlocfilehash: cf483f06d3802bc617855cafc6f3410af9372e41
ms.sourcegitcommit: a92b150da1e11d4a204c556ab98a4776727dbc22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "49883356"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Puntos de conexión de Office 365 U.S. Government GCC High

 *Se aplica a: Administrador de Office 365*

Office 365 requiere conectividad a Internet. Los puntos de conexión siguientes solo deben ser accesibles para los clientes que usen planes GCC High de Office 365 U.S. Government.
  
 **Puntos de conexión de Office 365:** [mundial (incluido GCC)](urls-and-ip-address-ranges.md) | [Office 365 operado por 21Vianet](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 Germany](microsoft-365-germany-endpoints.md)   |  [Office 365 Administración Pública de Estados Unidos (DoD)](microsoft-365-u-s-government-dod-endpoints.md) | *Office 365 Administración Pública de Estados Unidos (GCC High)* |
  
|||
|:-----|:-----|
|**Last updated:** 01/15/2021 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Descarga: la** lista completa en [formato JSON](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Empiece con la administración de puntos de conexión [de Office 365](managing-office-365-endpoints.md) para comprender nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de los puntos de conexión se actualizan al principio de cada mes con nuevas direcciones IP y direcciones URL publicadas 30 días antes de estar activos. Esto permite a los clientes que aún no tienen actualizaciones automatizadas completar sus procesos antes de que se requiera una nueva conectividad. Los puntos de conexión también pueden actualizarse durante el mes si es necesario para abordar escalaciones de soporte técnico, incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que se muestran en esta página a continuación se generan a partir de los servicios web basados en REST. Si usa un script o un dispositivo de red para tener acceso a estos datos, debe ir directamente [al servicio](microsoft-365-ip-web-service.md) web.

Los siguientes datos de puntos de conexión enumeran los requisitos para la conectividad del equipo de un usuario a Office 365. No incluye las conexiones de red de Microsoft a una red de clientes, a veces denominadas híbridas o conexiones de red de entrada.

Los puntos de conexión se agrupan en cuatro áreas de servicio. Las tres primeras se pueden seleccionar por separado para la conectividad; la cuarta área de servicio es una dependencia común (denominada de Microsoft 365 Common y Office) y debe disponer de conectividad de red en todo momento.

Estas son columnas de datos que se muestran:

- **ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.

- **Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer acerca de estas categorías y encontrar indicaciones para su administración en [https://aka.ms/pnc](https://aka.ms/pnc). Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.

- **ER:** esto es **sí si** el conjunto de puntos de conexión es compatible con Azure ExpressRoute con prefijos de ruta de Office 365. La comunidad DE BGP que incluye los prefijos de ruta que se muestran se alinea con el área de servicio enumerada. Cuando ER **es No,** esto significa que ExpressRoute no es compatible con este conjunto de puntos de conexión. Sin embargo, no se debe suponer que no se anuncia ninguna ruta para un conjunto de extremos donde ER es **No**. Si planea usar Azure AD Connect, lea la sección de consideraciones [especiales](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) para asegurarse de que tiene la configuración adecuada de Azure AD Connect.

- **Direcciones**: enumera los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.
 
- **Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.
 
[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

Notas sobre esta tabla:

- El Centro de seguridad y cumplimiento (SCC) proporciona compatibilidad con Azure ExpressRoute para Office 365. Lo mismo se aplica a muchas características expuestas a través del SCC, como informes, auditoría, eDiscovery avanzado, DLP unificado y gobierno de datos. Actualmente, dos características específicas, la importación de PST y la exportación de exhibición de documentos electrónicos, no admiten Azure ExpressRoute solo con filtros de ruta de Office 365 debido a su dependencia en Azure Blob Storage. Para consumir estas características, necesita conectividad independiente a Azure Blob Storage con cualquier opción de conectividad de Azure compatible, que incluye conectividad a Internet o Azure ExpressRoute con filtros de ruta pública de Azure. Debe evaluar el establecimiento de dicha conectividad para ambas características. El equipo de Protección de la información de Office 365 es consciente de esta limitación y está trabajando activamente para proporcionar compatibilidad con Azure ExpressRoute para Office 365 como limitado a los filtros de ruta de Office 365 para ambas características.

- Hay puntos de conexión opcionales adicionales para Aplicaciones de Microsoft 365 para empresas que no aparecen en la lista y que no son necesarios para que los usuarios inicien aplicaciones de Aplicaciones de Microsoft 365 para empresas y editan documentos. Los puntos de conexión opcionales se hospedan en centros de datos de Microsoft y no procesan, transmiten ni almacenan datos de clientes. Recomendamos que las conexiones de usuario a estos puntos de conexión se dirijan al perímetro predeterminado de salida de Internet.

