---
title: ¿Qué viene con la puntuación segura de Microsoft?
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo se calculan los detalles y qué administradores de seguridad pueden esperar.
keywords: seguridad, malware, Microsoft 365, M365, calificación segura, centro de seguridad, acciones de mejora
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
ms.openlocfilehash: 48ff6d6f5cac0991895c40cae90ca31657cfedff
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844887"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>¿Qué viene con la puntuación segura de Microsoft?

Para hacer que la [puntuación segura de Microsoft](microsoft-secure-score.md) sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo. Se cambiará la puntuación y la puntuación máxima posible. Sin embargo, esto no implica un cambio en su postura de seguridad.

Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)

## <a name="june-2020"></a>Junio de 2020

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Quitar la acción de mejora para la protección contra amenazas avanzada de Microsoft defender

* Activar las reglas de reducción de la superficie de ataque

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Agregar acciones de mejora para la protección contra amenazas avanzada de Microsoft defender

* Impedir que Adobe Reader cree procesos secundarios
* Usar protección avanzada contra ransomware
* Bloquear todas las aplicaciones de Office para crear procesos secundarios
* Impedir que las aplicaciones de Office creen contenido ejecutable
* Impedir que JavaScript o VBScript inicien contenido ejecutable descargado
* Bloquear la ejecución de scripts potencialmente ofuscados
* Bloquear contenido ejecutable del cliente de correo electrónico y Webmail
* Impedir que la aplicación de comunicación de Office cree procesos secundarios
* Bloquear procesos no habilitados y no firmados que se ejecutan desde USB
* Bloquear la persistencia a través de la suscripción de eventos WMI
* Impedir que las aplicaciones de Office inserten código en otros procesos
* Bloquear la ejecución de los archivos ejecutables a menos que cumplan un criterio de predominio, edad o lista de confianza
* Bloquear creaciones de procesos procedentes de PSExec y comandos WMI
* Bloquear credenciales de robo desde el subsistema de la autoridad de seguridad local de Windows (lsass.exe)
* Bloquear llamadas a la API Win32 desde macros de Office
