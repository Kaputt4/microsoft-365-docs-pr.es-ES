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
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541112"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>¿Qué viene con la puntuación segura de Microsoft?

Para hacer que la puntuación segura de Microsoft sea un mejor representante de su postura de seguridad y mejorar el uso, estamos realizando algunos cambios en un futuro próximo. Se cambiará la puntuación y la puntuación máxima posible. Sin embargo, esto no implica un cambio en su postura de seguridad.

Para obtener más información sobre los cambios recientes, vea [what's New in Secure score de Microsoft](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>21 de abril de 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Eliminación de acciones de mejora que no cumplen con las expectativas para una medición fiable o que no proporcionan una representación útil de la postura de seguridad

Para asegurarse de que la puntuación segura de Microsoft es significativa y que cada acción de mejora es medible y confiable, se quitan las siguientes acciones de mejora.

- Aplicar protecciones de IRM a los documentos
- Aplicar directivas de prevención de pérdida de datos

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a>Adición de la acción de mejora de Azure AD en la versión preliminar

- No permitir a los usuarios conceder consentimiento a las aplicaciones no administradas (actualmente disponibles en la versión de lanzamiento)

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a>Adición de acciones de mejora de ATP de Azure en la versión preliminar

- Deshabilitar el servicio de cola de impresión en controladores de dominio
- Modificar las delegaciones Kerberos no seguras para impedir la suplantación
- Proteger y administrar contraseñas de administración local con los intervalos de Microsoft
- Reducir el riesgo de ruta de movimiento lateral a las entidades confidenciales
- Eliminación de cuentas latentes de grupos confidenciales
- Quitar atributos del historial SID no seguro de entidades
- Resolver atributos de cuenta no segura
- Detener la exposición de credenciales de texto no cifrado
- Detener la comunicación de protocolos heredados
- Detener el uso de cifrado débil

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a>Compatibilidad con las recomendaciones de seguridad de la amenaza ATP de Microsoft defender & Vulnerability Management (TVM) en la versión preliminar

- Todas las recomendaciones de seguridad emitidas suministradas por TVM ahora también estarán disponibles en la calificación segura de Microsoft
