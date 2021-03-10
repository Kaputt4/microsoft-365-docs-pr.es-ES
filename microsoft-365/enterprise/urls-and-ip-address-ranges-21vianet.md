---
title: Direcciones URL e intervalos de direcciones IP para Office 365 operado por 21Vianet
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/28/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: En este artículo se enumeran las direcciones URL y los intervalos de direcciones IP para Office 365 cuando 21Vianet funciona en China.
hideEdit: true
ms.openlocfilehash: dae2b5feb4fbf7fc3e9bdd2419e2d114b5507ee8
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597075"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>Direcciones URL e intervalos de direcciones IP para Office 365 operado por 21Vianet

 *Hace referencia a Office 365 operado por 21Vianet: administración de pequeña empresa, Office 365 operado por 21Vianet: administración*

**Resumen**: los siguientes puntos de conexión (FQDN, puertos, direcciones URL, IPv4 y prefijos de IPv6) se aplican a Office 365 operado por 21Vianet y están diseñados para ofrecer servicios de productividad para las organizaciones que usan solo estos planes.
  
 **Puntos de conexión de Office 365:** [mundial (incluido GCC)](urls-and-ip-address-ranges.md)  | *Office 365 operado por 21Vianet* | [Office 365 Germany](microsoft-365-germany-endpoints.md)  |  [Office 365 Administración Pública de Estados Unidos (DoD)](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 Administración Pública de Estados Unidos (GCC High)](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Last updated:** 08/28/2020 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Descargue:** todos los destinos obligatorios y opcionales en una lista de [formato JSON](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> |

Comience con [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data. Los datos de los puntos de conexión se actualizan según sea necesario al principio de cada mes con las nuevas direcciones IP y direcciones URL publicadas 30 días antes de estar activos. Esto permite que los clientes que aún no tienen actualizaciones automatizadas completen sus procesos antes de que se requiera nueva conectividad. Los puntos de conexión también pueden actualizarse durante el mes si es necesario para abordar escalaciones de soporte técnico, incidentes de seguridad u otros requisitos operativos inmediatos. Los datos que se muestran en esta página a continuación se generan a partir de los servicios web basados en REST. Si usa un script o un dispositivo de red para obtener acceso a estos datos, debe ir al [servicio web directamente.](microsoft-365-ip-web-service.md)

Los siguientes datos de puntos de conexión enumeran los requisitos para la conectividad del equipo de un usuario a Office 365. No incluye las conexiones de red de Microsoft a una red de clientes, a veces denominadas híbridas o conexiones de red de entrada.

Los puntos de conexión se agrupan en cuatro áreas de servicio. Las tres primeras se pueden seleccionar por separado para la conectividad; la cuarta área de servicio es una dependencia común (denominada de Microsoft 365 Common y Office) y debe disponer de conectividad de red en todo momento.

Estas son columnas de datos que se muestran:

- **ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.

- **Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer acerca de estas categorías y encontrar indicaciones para su administración en [https://aka.ms/pnc](https://aka.ms/pnc). Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.

- **EMERGENCIA**: aparece como **Sí** si el conjunto de puntos de conexión se admite en Azure ExpressRoute con prefijos de ruta de Office 365. La comunidad de BGP que incluye los prefijos de ruta que aparecen se alinea con el área de servicio que se muestra. Si EMERGENCIA aparece como **No**, esto significa que ExpressRoute no es compatible con este conjunto de puntos de conexión. Sin embargo, no se debe dar por hecho que no se anuncia ninguna ruta para un conjunto de puntos de conexión cuando EMERGENCIA se establezca como **No**.

- **Direcciones**: enumera los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.
 
- **Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]


