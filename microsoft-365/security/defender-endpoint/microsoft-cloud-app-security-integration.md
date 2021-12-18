---
title: Introducción a la integración de Microsoft Defender for Cloud Apps
ms.reviewer: ''
description: Microsoft Defender para endpoint se integra con Defender for Cloud Apps reenviando todas las actividades de red de aplicaciones en la nube.
keywords: nube, aplicación, redes, visibilidad, uso
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 8260903ba8031bae76f420a7b010ed73df1c833d
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560391"
---
# <a name="microsoft-defender-for-cloud-apps-in-defender-for-endpoint-overview"></a>Introducción a Microsoft Defender para aplicaciones en la nube en Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender para aplicaciones en la nube es una solución completa que da visibilidad a los servicios y aplicaciones en la nube, ya que permite controlar y limitar el acceso a las aplicaciones en la nube, al tiempo que se cumplen los requisitos de cumplimiento en los datos almacenados en la nube. Para obtener más información, [vea Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security).

> [!NOTE]
> Esta característica está disponible con una licencia E5 para [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) dispositivos que ejecutan Windows 10 versión 1809 o posterior, o Windows 11.

## <a name="microsoft-defender-for-endpoint-and-defender-for-cloud-apps-integration"></a>Integración de Microsoft Defender para Endpoint y Defender para Cloud Apps

La detección de Defender for Cloud Apps se basa en los registros de tráfico en la nube que se reenvían desde servidores proxy y firewall de empresa. Microsoft Defender para endpoint se integra con Defender para aplicaciones en la nube mediante la recopilación y reenvío de todas las actividades de red de aplicaciones en la nube, lo que proporciona una visibilidad sin precedentes del uso de aplicaciones en la nube. La funcionalidad de supervisión está integrada en el dispositivo, lo que proporciona una cobertura completa de la actividad de red.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4yQ]

La integración proporciona las siguientes mejoras importantes en la detección existente de Defender para Aplicaciones en la nube:

- Disponible en todas partes: dado que la actividad de red se recopila directamente desde el punto de conexión, está disponible siempre que el dispositivo esté, dentro o fuera de la red corporativa, ya que ya no depende del tráfico enrutado a través del firewall de empresa o los servidores proxy.

- Funciona sin necesidad de configuración: reenviar registros de tráfico en la nube a Defender para aplicaciones en la nube requiere configuración de firewall y servidor proxy. Con la integración de Defender for Endpoint y Defender for Cloud Apps, no se requiere ninguna configuración. Solo tienes que activarla en Centro de seguridad de Microsoft Defender configuración y puedes ir.\

- Contexto del dispositivo: los registros de tráfico en la nube carecen de contexto del dispositivo. La actividad de la red defender para puntos de conexión se notifica con el contexto del dispositivo (a qué dispositivo se ha accedido a la aplicación en la nube), por lo que puedes comprender exactamente dónde (dispositivo) se realizó la actividad de red, además de quién (usuario) la realizó.

Para obtener más información acerca de la detección en la nube, consulta [Trabajar con aplicaciones detectadas.](/cloud-app-security/discovered-apps)

## <a name="related-topic"></a>Tema relacionado

- [Configurar la integración de Microsoft Defender for Cloud Apps](microsoft-cloud-app-security-config.md)
