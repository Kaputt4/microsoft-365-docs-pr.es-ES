---
title: 'Fase 3 de implementación de reglas ASR: implementar'
description: Proporciona instrucciones para implementar la implementación de reglas de reducción de superficie de ataque.
keywords: Implementación de reglas de reducción de superficie de ataque, implementación de ASR, habilitar reglas asr, configurar ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades, anti exploit, reglas de vulnerabilidad, reglas de prevención de infecciones, Microsoft Defender para endpoint, configurar reglas ASR
search.product: eADQiWindows 10XVcnh
ms.reviewer: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 6556389ecef571626c1927aca9341945f113d150
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217415"
---
# <a name="attack-surface-reduction-rules-deployment-phase-3-implement"></a>Fase 3 de implementación de reglas de reducción de superficie de ataque: implementar

La fase de implementación mueve el anillo de las pruebas al estado funcional.

> [!div class="mx-imgBorder"]
> ![Pasos de implementación de reglas ASR](images/asr-rules-implementation-steps.png)

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>Paso 1: Transición de reglas ASR de auditoría a bloqueo

1. Una vez determinadas todas las exclusiones durante el modo de auditoría, empieza a establecer algunas reglas ASR en modo "bloquear", empezando por la regla que tiene el menor número de eventos desencadenados. Vea " [Habilitar reglas de reducción de superficie de ataque](enable-attack-surface-reduction.md).
2. Revise la página de informes en el portal de Microsoft 365 Defender web; vea Informe de protección contra amenazas [en Microsoft Defender para endpoint](threat-protection-reports.md). Revisa también los comentarios de tus campeones de ASR.
3. Refine las exclusiones o cree nuevas exclusiones según se determine necesario.
4. Vuelva a cambiar las reglas problemáticas a Auditoría.

  >[!Note]
  >Para las reglas problemáticas (reglas que crean demasiado ruido), es mejor crear exclusiones que desactivar las reglas o volver a auditar. Tendrá que determinar qué es lo mejor para su entorno.

  >[!Tip]
  >Cuando esté disponible, aproveche la configuración del modo de advertencia en las reglas para limitar las interrupciones. Habilitar reglas ASR en modo de advertencia permite capturar eventos desencadenados y ver sus posibles interrupciones, sin bloquear realmente el acceso del usuario final. Más información: [Modo de advertencia para usuarios.](attack-surface-reduction.md#warn-mode-for-users)

### <a name="how-does-warn-mode-work"></a>¿Cómo funciona el modo de advertencia?

El modo de advertencia es efectivamente una instrucción Block, pero con la opción de que el usuario "desbloquee" las ejecuciones posteriores del flujo o aplicación dados. El modo de advertencia desbloquea en una combinación de dispositivo, usuario, archivo y proceso. La información del modo de advertencia se almacena localmente y tiene una duración de 24 horas.

### <a name="step-2-expand-deployment-to-ring-n--1"></a>Paso 2: Expandir la implementación para que suene n + 1

Cuando esté seguro de haber configurado correctamente las reglas de ASR para el anillo 1, puede ampliar el ámbito de la implementación al siguiente anillo (anillo n + 1).

El proceso de implementación, pasos del 1 al 3, es esencialmente el mismo para cada anillo posterior:

1. Reglas de prueba en Auditoría
2. Revisar eventos de auditoría desencadenados por ASR en el portal de Microsoft 365 Defender web
3. Crear exclusiones
4. Revisión: refinar, agregar o quitar exclusiones según sea necesario
5. Establecer reglas en "bloquear"
6. Revise la página de informes en el Microsoft 365 Defender web.
7. Crear exclusiones.
8. Deshabilite las reglas problemáticas o vuelva a cambiarlas a Auditoría.

## <a name="additional-topics-in-this-deployment-collection"></a>Temas adicionales de esta colección de implementación

[Guía de implementación de reglas ASR: información general](attack-surface-reduction-rules-deployment.md)

[Fase 1 de implementación de reglas ASR: plan](attack-surface-reduction-rules-deployment-phase-1.md)

[Fase 2 de implementación de reglas ASR: prueba](attack-surface-reduction-rules-deployment-phase-2.md)

[Fase 4 de implementación de reglas ASR: operationalize](attack-surface-reduction-rules-deployment-phase-4.md)
