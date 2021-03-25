---
title: Introducción a la integración de Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender para endpoint se integra con Cloud App Security mediante el reenvío de todas las actividades de red de aplicaciones en la nube.
keywords: nube, aplicación, redes, visibilidad, uso
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 6ea885c17cf506ef6f9a4a7138630aed671f0ce8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074328"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Introducción a Microsoft Cloud App Security en Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) es una solución completa que da visibilidad a los servicios y aplicaciones en la nube, ya que permite controlar y limitar el acceso a las aplicaciones en la nube, al tiempo que se cumplen los requisitos de cumplimiento en los datos almacenados en la nube. Para obtener más información, vea [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Esta característica está disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) en dispositivos que ejecutan Windows 10 versión 1809 o posterior.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Integración de Microsoft Defender para Endpoint y Cloud App Security 

La detección de Cloud App Security se basa en los registros de tráfico en la nube que se le reenvían desde servidores proxy y firewall de empresa. Microsoft Defender para endpoint se integra con Cloud App Security recopilando y reenviando todas las actividades de red de aplicaciones en la nube, lo que proporciona una visibilidad sin igual del uso de aplicaciones en la nube. La funcionalidad de supervisión está integrada en el dispositivo, lo que proporciona una cobertura completa de la actividad de red.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


La integración proporciona las siguientes mejoras importantes en la detección existente de Cloud App Security: 

- Disponible en todas partes: dado que la actividad de red se recopila directamente desde el punto de conexión, está disponible siempre que el dispositivo esté, dentro o fuera de la red corporativa, ya que ya no depende del tráfico enrutado a través del firewall de empresa o los servidores proxy. 

- Funciona sin necesidad de configuración: el reenvío de registros de tráfico en la nube a Cloud App Security requiere una configuración de servidor proxy y firewall. Con la integración de Defender para Endpoint y Cloud App Security, no se requiere ninguna configuración. Solo tienes que activarla en la configuración del Centro de seguridad de Microsoft Defender y puedes ir. 

- Contexto del dispositivo: los registros de tráfico en la nube carecen de contexto del dispositivo. La actividad de la red defender para puntos de conexión se notifica con el contexto del dispositivo (a qué dispositivo se ha accedido a la aplicación en la nube), por lo que puedes comprender exactamente dónde (dispositivo) se realizó la actividad de red, además de quién (usuario) la realizó. 

Para obtener más información acerca de la detección en la nube, consulta [Trabajar con aplicaciones detectadas.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Tema relacionado

- [Configurar la integración de Microsoft Cloud App Security](microsoft-cloud-app-security-config.md)
