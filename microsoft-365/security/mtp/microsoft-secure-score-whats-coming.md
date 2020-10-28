---
title: Qué llega a la puntuación segura de Microsoft
description: Describe los nuevos cambios que vienen a la puntuación segura de Microsoft en el centro de seguridad de Microsoft 365.
keywords: puntuación segura de Microsoft, calificación segura, puntuación segura de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779253"
---
# <a name="whats-coming-to-microsoft-secure-score"></a>Qué llega a la puntuación segura de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Estamos realizando algunos cambios en un futuro próximo para hacer que [Microsoft califique](microsoft-secure-score.md) con seguridad una mejor representativo de su postura de seguridad y mejorar el uso. Su puntuación y la puntuación máxima posible pueden cambiar.

## <a name="proposed-changes"></a>Cambios propuestos

### <a name="november-2020"></a>2020 de noviembre

Eliminación de la capacidad de crear vales de ServiceNow a través de la calificación segura yendo a **compartir co> ServiceNow** .

- El período de versión preliminar del conector de ServiceNow está finalizando. Esta capacidad ya no estará disponible al final del 2020. Gracias por sus comentarios y el soporte técnico continuo mientras determinamos los siguientes pasos.

Adición de 18 acciones de mejora relacionadas con Microsoft defender para el punto de conexión (ATP anterior de Microsoft defender):

Recomendaciones relacionadas con la reducción de superficie de ataques (ASR):
- Bloquear contenido ejecutable del cliente de correo electrónico y Webmail
- Bloquear todas las aplicaciones de Office para crear procesos secundarios
- Impedir que las aplicaciones de Office creen contenido ejecutable
- Impedir que las aplicaciones de Office inserten código en otros procesos
- Impedir que JavaScript o VBScript inicien contenido ejecutable descargado
- Bloquear la ejecución de scripts potencialmente ofuscados
- Bloquear llamadas a la API Win32 desde macros de Office
- Bloquear la ejecución de los archivos ejecutables a menos que cumplan un criterio de predominio, edad o lista de confianza
- Usar protección avanzada contra ransomware
- Bloquear credenciales de robo desde el subsistema de la autoridad de seguridad local de Windows (lsass.exe)
- Bloquear creaciones de procesos procedentes de PSExec y comandos WMI
- Bloquear procesos no habilitados y no firmados que se ejecutan desde USB
- Impedir que la aplicación de comunicación de Office cree procesos secundarios
- Impedir que Adobe Reader cree procesos secundarios
- Bloquear la persistencia a través de la suscripción de eventos WMI

Recomendaciones relacionadas con los servicios:
- Corregir la ruta del servicio sin comillas para los servicios de Windows
- Cambiar la ruta de acceso del ejecutable del servicio a una ubicación común protegida
- Cambiar la cuenta de servicio para evitar la contraseña almacenada en caché en el registro de Windows

## <a name="related-resources"></a>Recursos relacionados

- [Introducción a la puntuación segura de Microsoft](microsoft-secure-score.md)
- [Evaluar su postura de seguridad](microsoft-secure-score-improvement-actions.md)
- [Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos](microsoft-secure-score-history-metrics-trends.md)
- [Novedades](microsoft-secure-score-whats-new.md)
