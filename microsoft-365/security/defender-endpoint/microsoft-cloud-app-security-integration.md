---
title: Introducción a la integración de Microsoft Defender for Cloud Apps
ms.reviewer: ''
description: Microsoft Defender para punto de conexión se integra con Defender for Cloud Apps reenviando todas las actividades de redes de aplicaciones en la nube.
keywords: nube, aplicación, redes, visibilidad, uso
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.date: 10/18/2018
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4a988a9d28ffdae2d9629413fa64d033eea263ca
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68231690"
---
# <a name="microsoft-defender-for-cloud-apps-in-defender-for-endpoint-overview"></a>Microsoft Defender for Cloud Apps en Información general de Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Cloud Apps es una solución completa que proporciona visibilidad sobre las aplicaciones y los servicios en la nube, ya que le permite controlar y limitar el acceso a las aplicaciones en la nube, a la vez que aplica los requisitos de cumplimiento en los datos almacenados en la nube. Para obtener más información, consulte [Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security).

> [!NOTE]
> Esta característica está disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) en dispositivos que ejecutan Windows 10 versión 1809 o posterior, o Windows 11.

## <a name="microsoft-defender-for-endpoint-and-defender-for-cloud-apps-integration"></a>integración de Microsoft Defender para punto de conexión y Defender for Cloud Apps

La detección de Defender for Cloud Apps se basa en que los registros de tráfico en la nube se reenvían a él desde servidores proxy y firewall empresariales. Microsoft Defender para punto de conexión se integra con Defender for Cloud Apps mediante la recopilación y el reenvío de todas las actividades de redes de aplicaciones en la nube, lo que proporciona una visibilidad sin precedentes del uso de aplicaciones en la nube. La funcionalidad de supervisión está integrada en el dispositivo, lo que proporciona una cobertura completa de la actividad de red.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4yQ]

La integración proporciona las siguientes mejoras importantes en la detección existente de Defender for Cloud Apps:

- Disponible en todas partes: dado que la actividad de red se recopila directamente desde el punto de conexión, está disponible siempre que el dispositivo esté, en la red corporativa o fuera de ella, ya que ya no depende del tráfico enrutado a través del firewall de empresa o de los servidores proxy.

- Funciona de forma inmediata, no se requiere ninguna configuración: el reenvío de registros de tráfico en la nube a Defender for Cloud Apps requiere la configuración del firewall y del servidor proxy. Con la integración de Defender para punto de conexión y Defender for Cloud Apps, no se requiere ninguna configuración. Solo tiene que activarlo en Microsoft 365 Defender configuración y está bien para ir.

- Contexto del dispositivo: los registros de tráfico en la nube carecen del contexto del dispositivo. La actividad de red de Defender para punto de conexión se notifica con el contexto del dispositivo (qué dispositivo accedió a la aplicación en la nube), por lo que puede comprender exactamente dónde (dispositivo) se realizó la actividad de red, además de quién (usuario) la realizó.

Para obtener más información sobre la detección de la nube, consulte [Trabajar con aplicaciones detectadas](/cloud-app-security/discovered-apps).

## <a name="related-topic"></a>Tema relacionado

- [Configurar la integración de Microsoft Defender for Cloud Apps](microsoft-cloud-app-security-config.md)
