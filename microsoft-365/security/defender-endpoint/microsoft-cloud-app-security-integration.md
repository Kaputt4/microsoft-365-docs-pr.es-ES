---
title: Introducción a integración de Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender para endpoint se integra con Cloud App Security reenviando todas las actividades de red de aplicaciones en la nube.
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
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844747"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security información general de Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) es una solución completa que da visibilidad a los servicios y aplicaciones en la nube, ya que permite controlar y limitar el acceso a las aplicaciones en la nube, al tiempo que se cumplen los requisitos de cumplimiento en los datos almacenados en la nube. Para obtener más información, [vea Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

>[!NOTE]
>Esta característica está disponible con una licencia E5 [para](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) Enterprise Mobility + Security dispositivos que Windows 10 versión 1809 o posterior.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender para la integración de puntos Cloud App Security de conexión 

Cloud App Security de detección se basa en los registros de tráfico en la nube que se reenvían desde servidores proxy y firewall de empresa. Microsoft Defender para endpoint se integra con Cloud App Security recopilando y reenviando todas las actividades de red de aplicaciones en la nube, lo que proporciona una visibilidad sin precedentes del uso de aplicaciones en la nube. La funcionalidad de supervisión está integrada en el dispositivo, lo que proporciona una cobertura completa de la actividad de red.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


La integración proporciona las siguientes mejoras importantes en la detección de Cloud App Security existente: 

- Disponible en todas partes: dado que la actividad de red se recopila directamente desde el punto de conexión, está disponible siempre que el dispositivo esté, dentro o fuera de la red corporativa, ya que ya no depende del tráfico enrutado a través del firewall de empresa o los servidores proxy. 

- Funciona sin necesidad de configuración: reenviar registros de tráfico en la nube a Cloud App Security configuración del servidor proxy y firewall. Con Defender for Endpoint y Cloud App Security integración, no se requiere ninguna configuración. Solo tienes que activarlo en Centro de seguridad de Microsoft Defender configuración y puedes ir. 

- Contexto del dispositivo: los registros de tráfico en la nube carecen de contexto del dispositivo. La actividad de la red defender para puntos de conexión se notifica con el contexto del dispositivo (a qué dispositivo se ha accedido a la aplicación en la nube), por lo que puedes comprender exactamente dónde (dispositivo) se realizó la actividad de red, además de quién (usuario) la realizó. 

Para obtener más información acerca de la detección en la nube, consulta [Trabajar con aplicaciones detectadas.](/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Tema relacionado

- [Configurar la integración con Microsoft Cloud App Security](microsoft-cloud-app-security-config.md)
