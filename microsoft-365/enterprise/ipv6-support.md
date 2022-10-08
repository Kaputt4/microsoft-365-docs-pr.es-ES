---
title: Compatibilidad con IPv6 en los servicios de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/02/2022
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Resumen: describe la compatibilidad con IPv6 en los componentes de Microsoft 365 y en las ofertas gubernamentales de Microsoft 365.'
ms.openlocfilehash: db517778f2aa17af142c4204220cbcd3dbd026e4
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68172651"
---
# <a name="ipv6-support-in-microsoft-365-services"></a>Compatibilidad con IPv6 en los servicios de Microsoft 365

Con la creciente adopción y compatibilidad de IPv6 entre redes empresariales, proveedores de servicios y dispositivos, muchos clientes se preguntan si sus usuarios pueden seguir accediendo a los servicios de Microsoft 365 desde clientes IPv6 y redes IPv6. Los servicios de Microsoft 365 se pueden usar correctamente desde dispositivos de pila doble IPv6 y solo IPv6. De hecho, tenemos un número creciente de clientes, desde consumidores hasta grandes empresas, que avanzan hacia una mayor adopción de IPv6. Para la mayoría de los clientes, IPv4 no desaparecerá por completo de su entorno digital, por lo que no estamos planeando requerir IPv6 ni anular la prioridad de IPv4 en ninguna característica o servicio de Microsoft 365.

Una de nuestras prioridades clave con Microsoft 365 es garantizar experiencias fluidas de clientes y usuarios a través de Internet desde cualquier ubicación, desde cualquier dispositivo. Esto incluye el acceso a Microsoft 365 desde dispositivos cliente que usan IPv6 en la configuración de pila dual, así como la transición a implementaciones de cliente solo IPv6. En la mayoría de los casos, cuando se sigue un modelo estándar basado en Internet de conexión a Microsoft 365 como se describe en [Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md), [direcciones URL y intervalos de direcciones IP de Microsoft 365](urls-and-ip-address-ranges.md) y [procedimientos recomendados de planeamiento de red de Microsoft 365](network-and-migration-planning.md#best-practices-for-network-planning-and-improving-migration-performance-for-office-365), las transiciones de IPv6 no interrumpirán la experiencia del usuario.

Muchos servicios de Microsoft 365 ya proporcionan compatibilidad nativa con IPv6 hoy en día y se puede acceder directamente desde la pila dual IPv6 y los clientes de solo IPv6. Microsoft 365 también permite el acceso a través de las tecnologías de traducción IPv6 convencionales a IPv4 (como servidores proxy base 64 o DNS64/NAT64) que suelen usar los clientes y proveedores de soluciones de red para conectarse a recursos de Internet IPv4.

Al igual que con cualquier servicio SaaS e Internet en general, el ámbito de las interfaces, características y API de Microsoft 365 habilitados para IPv6 de forma nativa se expande continuamente y sin la acción ni el control directos del cliente. Si ejecuta servicios IPv6 o solo IPv6 en sus redes que necesitan acceso a Microsoft 365 e Internet, se recomienda incluir mecanismos de transición IPv6/IPv4 dinámicos, como DNS64/NAT64, para garantizar la conectividad IPv6 de un extremo a otro a Microsoft 365 sin ninguna reconfiguración de red adicional.

La mayoría de los servicios de Microsoft 365 se han habilitado o se habilitarán con funcionalidades IPv6 de forma totalmente transparente para los usuarios finales y los administradores de TI. Algunos escenarios de Microsoft 365 (como el correo electrónico entrante anónimo) tienen requisitos y consideraciones especiales para su uso junto con IPv6. Para obtener más información sobre los requisitos y consideraciones de IPv6 específicos del escenario, póngase en contacto con el equipo de cuentas de Microsoft o con el soporte técnico de Microsoft.

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/o365ip6](https://aka.ms/o365ip6)

## <a name="see-also"></a>Vea también

[Información general de conectividad de red de Microsoft 365](microsoft-365-networking-overview.md)

[Administrar puntos de conexión de Office 365](managing-office-365-endpoints.md)

[Direcciones URL e intervalos de direcciones IP de Office 365](urls-and-ip-address-ranges.md)

[Dirección IP de Office 365 y servicio web de URL](microsoft-365-ip-web-service.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Planeamiento de red y ajuste del rendimiento para Microsoft 365](network-planning-and-performance.md)

[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)

[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)

[Redes de entrega de contenido](content-delivery-networks.md)

[Prueba de conectividad de Microsoft 365](https://aka.ms/netonboard)

[Cómo construye Microsoft su red global rápida y confiable](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de redes de Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
