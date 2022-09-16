---
title: Cómo configurar ataques automatizados y aprendizaje con Aprendizaje de simulación de ataques
description: Los pasos para automatizar el entrenamiento de Simulación de ataque y enviar una carga útil a los usuarios de destino. Siguiendo esta guía, aprenderá a crear flujos de ataque automatizados con técnicas y cargas específicas.
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 19804b1bf83dd2ef6f763e14a80f8784d07a942a
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67740837"
---
# <a name="how-to-setup-automated-attacks-and-training-within-attack-simulation-training"></a>Cómo configurar ataques automatizados y aprendizaje con Aprendizaje de simulación de ataques

Entrenamiento de simulación de ataque le permite ejecutar simulaciones de ataques benignos en su organización para evaluar el riesgo de suplantación de identidad (phishing) y enseñar a los usuarios a evitar mejor los ataques de phish. Siguiendo esta guía, configurará flujos automatizados con técnicas y cargas específicas que se ejecutan cuando se cumplen las condiciones especificadas, iniciando simulaciones en su organización.

## <a name="what-youll-need"></a>Lo que necesitará

- Microsoft Defender para Office 365 Plan 2 (incluido como parte de E5).
- Permisos suficientes (rol administrador de seguridad).
- 5-10 minutos para realizar los pasos siguientes.

## <a name="send-a-payload-to-target-users"></a>Envío de una carga útil a los usuarios de destino

1. Vaya a [Entrenamiento de simulación de ataque](https://security.microsoft.com/attacksimulator).
1. Elija **Automatizaciones de simulación** en la barra de navegación superior.
1. Presione **Crear automatización**.
1. Asigne a la automatización de simulación un nombre relevante y memorable. *A continuación*.
1. Elija las técnicas que desea usar en el control flotante. *A continuación*.
1. Seleccione manualmente hasta 20 cargas que quiera usar para esta automatización o seleccione Aleatoriamente. *A continuación*.
1. Si seleccionó OAuth como carga útil, deberá escribir el nombre, el logotipo y el ámbito (permisos) que desea que tenga la aplicación cuando se use en una simulación. *A continuación*.
1. Elija a quién dirigirse con la carga, si elige toda la organización, resalte el botón de radio. *A continuación*.
1. De lo contrario, seleccione **Agregar usuarios** y, a continuación, busque o filtre los usuarios con el asistente, presione Agregar usuarios. *A continuación*.
1. Personalice el entrenamiento si procede; de lo contrario, deje seleccionado Asignar entrenamiento para mí (recomendado). *A continuación*.
1. Personalice la página de aterrizaje que se muestra cuando un usuario se phished si procede; de lo contrario, deje como valor predeterminado de Microsoft. *A continuación*.
1. Elija si desea recibir notificaciones del usuario final, si es así, seleccione las preferencias de entrega y personalícelas cuando corresponda. *A continuación*.
1. En Programación de simulación, puede seleccionar **Aleatorio** o **Fijo**; la opción recomendada es Aleatoria, una vez seleccionada, seleccione *Siguiente*.
1. En función de la elección de Aleatorio o Fijo, los detalles de la programación pueden diferir, pero seleccionar preferencias en la elección, incluidas las fechas de inicio y finalización de la automatización. *A continuación*.
1. En **Detalles de inicio**, seleccione las opciones finales que desee, como usar cargas únicas o dirigirse a delincuentes reincidentes y, a continuación, seleccione *Siguiente*.
1. **Enviar** y la automatización de simulación está configurada.

## <a name="learn-more"></a>Más información

Encontrará instrucciones completas en [Automatizaciones de simulación para Entrenamiento de simulación de ataque: Office 365 | Microsoft Docs](../../office-365-security/attack-simulation-training-simulation-automations.md).
