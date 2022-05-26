---
title: Automatizaciones de carga útil para el entrenamiento de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a usar automatizaciones de carga útil (recopilación de carga) para recopilar e iniciar simulaciones automatizadas para el entrenamiento de simulación de ataques en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.openlocfilehash: 7fb3b0bbad5bbec8044a94da1943b0bd25eba865
ms.sourcegitcommit: 872ab0b6a225c20274916e07ed4cc4944be9509a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65679382"
---
# <a name="payload-automations-for-attack-simulation-training"></a>Automatizaciones de carga útil para el entrenamiento de simulación de ataques

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

En El entrenamiento de simulación de ataques en Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2, las automatizaciones de carga útil (también conocidas como _recopilación de carga_) recopilan información de los mensajes de suplantación de identidad reales que los usuarios de su organización notificaron. Aunque es probable que el número de estos mensajes sea bajo en su organización, puede especificar las condiciones que se deben buscar en los ataques de suplantación de identidad (por ejemplo, destinatarios, técnica de ingeniería social, información del remitente, etc.). A continuación, el entrenamiento de simulación de ataque imitará los mensajes y las cargas que se usan en el ataque para iniciar automáticamente simulaciones inofensivas a los usuarios de destino.

Para crear una automatización de carga, siga estos pasos:

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com/>, vaya a **Correo electrónico & la** pestaña **Automatizaciones de entrenamiento** \> de simulación de ataque de colaboración \> **Automatizaciones** \> de **carga**.

   Para ir directamente a la pestaña **Automatizaciones** , use <https://security.microsoft.com/attacksimulator?viewid=automations>.

2. En **Automatizaciones de carga**, seleccione ![el icono Crear automatización.](../../media/m365-cc-sc-create-icon.png) **Crear automatización**.

   :::image type="content" source="../../media/attack-sim-training-sim-automations-create.png" alt-text="El botón Crear simulación de la pestaña Automatizaciones de carga en Entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-sim-automations-create.png":::

3. Se abre el asistente para la creación. En el resto de este artículo se describen las páginas y la configuración que contienen.

> [!NOTE]
> En cualquier momento durante el asistente para la creación, puede hacer clic en **Guardar y cerrar** para guardar el progreso y seguir configurando la automatización de la carga más adelante. Puede seleccionar dónde lo dejó seleccionando la automatización de carga en **Automatizaciones** de carga y, a continuación, haga clic en ![el icono Editar automatización.](../../media/m365-cc-sc-edit-icon.png) **Edite la automatización**.

## <a name="automation-name"></a>Nombre de automation

En la página **Nombre de Automation**, configure los siguientes valores:

- **Nombre**: escriba un nombre descriptivo único para la automatización de carga.
- **Descripción**: escriba una descripción detallada opcional para la automatización de la carga.

Cuando termine, haga clic en **Siguiente**.

## <a name="run-conditions"></a>Condiciones de ejecución

En la página **Condiciones de ejecución** , seleccione las condiciones del ataque de suplantación de identidad real que determina cuándo se ejecutará la automatización.

Puede usar cada condición solo una vez. Varias condiciones usan lógica AND (\<Condition1\> y \<Condition2\>).

![Icono Agregar condición.](../../media/m365-cc-sc-create-icon.png) **Agregar condición**.

- **No. de los usuarios destinados a la campaña**: Configure los siguientes valores:
  - **Igual que**, **Menor que**, **Mayor que**, **Menor o igual que**, o **Mayor o igual que**.
  - **Valor de entrada**: el número de usuarios a los que se ha dirigido la campaña de suplantación de identidad (phishing).
- **Campañas con una técnica de phish específica**: seleccione uno de los valores disponibles:
  - **Cosecha de credenciales**
  - **Datos adjuntos de malware**
  - **Vínculo en datos adjuntos**
  - **Vínculo a malware**
  - **Dirección URL de unidad por**
- **Dominio de remitente específico**: escriba un valor de dominio de correo electrónico del remitente (por ejemplo, contoso.com).
- **Nombre de remitente específico**: escriba un valor de nombre de remitente.
- **Correo electrónico de remitente específico**: escriba una dirección de correo electrónico del remitente.
- **Destinatarios de usuarios y grupos específicos**: empiece a escribir el nombre o la dirección de correo electrónico del usuario o grupo. Cuando aparezca, selecciónelo.

Para quitar una condición después de agregarla, haga clic en ![Icono Quitar.](../../media/m365-cc-sc-delete-icon.png).

Cuando termine, haga clic en **Siguiente**.

## <a name="review-automation"></a>Revisión de la automatización

En la página **Revisar automatización** , puede revisar los detalles de la automatización de la carga.

Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

Cuando haya terminado, haga clic en **Enviar**.
