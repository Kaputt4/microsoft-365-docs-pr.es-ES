---
title: Introducción a las funcionalidades de detección y respuesta de puntos de conexión
ms.reviewer: ''
description: Obtenga información sobre las funcionalidades de detección y respuesta de puntos de conexión en Microsoft Defender para punto de conexión
keywords: Microsoft Defender para punto de conexión, detección y respuesta de puntos de conexión, respuesta, detección, ciberseguridad, protección
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ba33bc890fe2a6d07bb16e1cb36d7096a2aea4c9
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67699946"
---
# <a name="overview-of-endpoint-detection-and-response"></a>Introducción a la EDR

**Se aplica a:**
- [Microsoft Defender para punto de conexión, planes 1 y 2](defender-endpoint-plan-1-2.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Las funcionalidades de detección y respuesta de puntos de conexión de Defender para punto de conexión proporcionan detecciones avanzadas de ataques casi en tiempo real y accionables. Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas.

Cuando se detecta una amenaza, se crean alertas en el sistema para que un analista la investigue. Las alertas con las mismas técnicas de ataque o atribuidas al mismo atacante se agregan a una entidad denominada _incidente_. Agregar alertas de esta manera permite a los analistas investigar y responder de forma colectiva a las amenazas con facilidad.

> [!NOTE]
> La detección de Defender para punto de conexión no está pensada para ser una solución de auditoría o registro que registre todas las operaciones o actividades que se producen en un punto de conexión determinado. Nuestro sensor tiene un mecanismo de limitación interna, por lo que la alta tasa de repetición de eventos idénticos no inundará los registros.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4o1j5]

> [!IMPORTANT]
> El plan 1 y [Microsoft Defender para Empresas](../defender-business/mdb-overview.md) de [Defender para punto de conexión](defender-endpoint-plan-1.md) incluyen solo las siguientes acciones de respuesta manual:
> - Ejecutar examen de antivirus
> - Aislar el dispositivo
> - Detener y poner en cuarentena un archivo
> - Adición de un indicador para bloquear o permitir un archivo

Inspirado en la mentalidad de "suponer vulneración", Defender para punto de conexión recopila continuamente la telemetría cibernética del comportamiento. Esto incluye la información de procesos, las actividades de red, ópticas profundas en el kernel y el administrador de memoria, las actividades de inicio de sesión de usuario, los cambios en el registro y el sistema de archivos, entre otros. La información se almacena durante seis meses, lo que permite que un analista se desplace hacia el tiempo de inicio de un ataque. El analista puede dinamizar varias vistas y enfocar una investigación a través de varios vectores.

Las capacidades de respuesta le ofrecen la posibilidad de solucionar rápidamente las amenazas al actuar en las entidades afectadas.

## <a name="related-topics"></a>Temas relacionados

- [Panel de operaciones de seguridad](security-operations-dashboard.md)
- [Cola de incidentes](view-incidents-queue.md)
- [Cola de alertas](alerts-queue.md)
- [Lista de dispositivos](machines-view-overview.md)
