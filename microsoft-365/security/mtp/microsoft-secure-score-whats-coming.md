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
ms.openlocfilehash: efb75f26d66258880c9defa94869f27e18685052
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372008"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>¿Qué viene con la puntuación segura de Microsoft?

Para hacer que la puntuación segura de Microsoft sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo. Se cambiará la puntuación y la puntuación máxima posible. Sin embargo, esto no implica un cambio en su postura de seguridad.

Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)

## <a name="march-16th-2020"></a>16 de marzo de 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Eliminación de acciones de mejora que no cumplen con las expectativas para una medición fiable o que no proporcionan una representación útil de la postura de seguridad

Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.

- Almacenar documentos de usuario en OneDrive para la empresa
- Configurar las directivas de datos adjuntos seguros de Office 365 ATP
- Configurar vínculos seguros de Office 365 para comprobar direcciones URL
- No permitir la delegación de buzones
- Permitir vínculos de uso compartido de invitados anónimos para sitios y documentos
- Activar la consola de Cloud App Security
- Configurar el tiempo de expiración de los vínculos de uso compartido externo

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Compatibilidad con los valores predeterminados de seguridad para acciones de mejora de Azure AD

La calificación segura de Microsoft actualizará las acciones de mejora para admitir los [valores predeterminados de seguridad en Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que facilitan la protección de la organización con opciones de seguridad preconfiguradas para ataques comunes.

Afectará a las siguientes acciones de mejora:

- Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro
- Requerir MFA para roles administrativos
- Habilitar la Directiva para bloquear la autenticación heredada
