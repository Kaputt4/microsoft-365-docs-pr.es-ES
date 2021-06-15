---
title: Office 365 de conexión para Alemania
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2020
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
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: En este artículo encontrará puntos de conexión accesibles para los clientes que usan Office 365 en Alemania.
hideEdit: true
ms.openlocfilehash: 27d7b3c895cb3a8cae148262ce3962f03fb417aa
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925817"
---
# <a name="office-365-germany-endpoints"></a>Puntos de conexión de Office 365 de Alemania

 *Se aplica a: Office 365 Admin*

Office 365 requiere conectividad a Internet. Los puntos de conexión siguientes deben ser accesibles para los clientes que **usan Office 365 planes de** Alemania.

> [!NOTE]
> Para los clientes, que están en la transición a la nueva región Microsoft 365 centro de datos en Alemania, los puntos de conexión cambiarán.
> Para obtener información adicional, consulte [Migración de Microsoft Cloud Deutschland a Office 365 servicios](ms-cloud-germany-transition.md)en las nuevas regiones del centro de datos alemán.
  
 **Puntos de conexión de Office 365:** [mundial (incluido GCC)](urls-and-ip-address-ranges.md)  | [Office 365 operado por 21Vianet](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 Germany*  |  [Office 365 Administración Pública de Estados Unidos (DoD)](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 Administración Pública de Estados Unidos (GCC High)](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
**Last updated:** 12/01/2020 - ![ RSS Change Log ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [subscription](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

**Descargue:** todos los destinos obligatorios y opcionales en una lista de [formato JSON](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Comience por [Administración de puntos de conexión de Office 365](managing-office-365-endpoints.md) conocer nuestras recomendaciones para administrar la conectividad de red con estos datos. Los datos de los puntos de conexión se actualizan según sea necesario al principio de cada mes con las nuevas direcciones IP y direcciones URL publicadas 30 días antes de su actividad. Esto permite a los clientes que aún no tienen actualizaciones automatizadas completar sus procesos antes de que se requiera nueva conectividad. Los datos de punto de conexión también pueden actualizarse durante el mes si es necesario para administrar las solicitudes de soporte técnico, los incidentes de seguridad u otros requisitos operativos inmediatos. Siempre puede hacer referencia a la suscripción [de registro de cambios](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Los datos que se muestran en la página siguiente se generan a partir de los servicios web basados en REST. Si usa un script o un dispositivo de red para tener acceso a estos datos, debería ir al [servicio web](microsoft-365-ip-web-service.md) directamente.

Los datos de punto de conexión siguientes enumeran los requisitos de conectividad desde la máquina de un usuario a Office 365. No incluye conexiones de red de Microsoft a una red de clientes, a veces denominadas conexiones de red híbridas o entrantes.

Los puntos de conexión se agrupan en cuatro áreas de servicio. Las tres primeras se pueden seleccionar por separado para la conectividad; la cuarta área de servicio es una dependencia común (denominada de Microsoft 365 Common y Office) y debe disponer de conectividad de red en todo momento.

Estas son columnas de datos que se muestran:

- **ID**: el número de identificación de la fila, también conocido como un conjunto de puntos de conexión. Este identificador es el mismo que devuelve el servicio web para el conjunto de puntos de conexión.

- **Categoría**: muestra si el conjunto de puntos de conexión se clasifica como "Optimizar", "Permitir" o "Predeterminado". Puede leer sobre estas categorías y encontrar indicaciones para su administración en [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). Esta columna también muestra los conjuntos de puntos de conexión que deben tener conectividad de red. Para los conjuntos de puntos de conexión que no necesitan conectividad de red, le proporcionamos notas en este campo para indicar qué funcionalidad faltaría si se bloqueara el conjunto de puntos de conexión. Si va a excluir un área de servicio completa, los conjuntos de puntos de conexión enumerados como necesarios no necesitan conectividad.

- **EMERGENCIA**: aparece como **Sí** si el conjunto de puntos de conexión se admite en Azure ExpressRoute con prefijos de ruta de Office 365. La comunidad de BGP que incluye los prefijos de ruta que aparecen se alinea con el área de servicio que se muestra. Si EMERGENCIA aparece como **No**, esto significa que ExpressRoute no es compatible con este conjunto de puntos de conexión. Sin embargo, no se debe dar por hecho que no se anuncia ninguna ruta para un conjunto de puntos de conexión cuando EMERGENCIA se establezca como **No**.

- **Direcciones**: enumera los FQDN o nombres de dominio con caracteres comodín y los intervalos de direcciones IP para el conjunto de puntos de conexión. Tenga en cuenta que un intervalo de direcciones IP está en formato CIDR y puede incluir varias direcciones IP individuales en la red especificada.
 
- **Puertos**: muestra los puertos TCP o UDP que se combinan con las direcciones para formar el punto de conexión de la red. Es posible que observe repeticiones de intervalos de direcciones IP cuando se enumeran diferentes puertos.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

