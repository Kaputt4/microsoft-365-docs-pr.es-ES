---
title: Automatización de carga útil para el aprendizaje de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a usar las automatizacións de carga (recolección de carga) para recopilar e iniciar simulaciones automatizadas para el aprendizaje de simulación de ataques en Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.openlocfilehash: 0e090b79c8e04de5f0e9e81449d805d2b124bc59
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717700"
---
# <a name="payload-automations-for-attack-simulation-training"></a>Automatización de carga útil para el aprendizaje de simulación de ataques

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

En el curso de simulación de ataques en Microsoft 365 E5 o Microsoft Defender para el Plan 2 de Office 365, las automatizacións de carga (también conocidas como recolección de _carga)_ recopilan información de mensajes de suplantación de identidad reales que los usuarios de la organización han notificado. Aunque el número de estos mensajes es probablemente bajo en la organización, puede especificar las condiciones que debe buscar en los ataques de suplantación de identidad (por ejemplo, destinatarios, técnica de ingeniería social, información del remitente, etc.). A continuación, el entrenamiento de simulación de ataque imitará los mensajes y cargas que se usan en el ataque para iniciar automáticamente simulaciones inofensivas para usuarios dirigidos.

Para crear una automatización de carga, siga estos pasos:

1. En el portal Microsoft 365 Defender en , vaya a Correo electrónico & de aprendizaje de simulación de <https://security.microsoft.com/>  \>  \> **ataques De** carga.

   Para ir directamente a la **pestaña Automatización de carga,** use <https://security.microsoft.com/attacksimulator?viewid=payloadautomation> .

2. En la **pestaña Automatización de carga,** seleccione ![ Crear icono de simulación.](../../media/m365-cc-sc-create-icon.png) **Crear simulación**.

   ![Cree el botón de simulación en la pestaña Automatización de carga en el aprendizaje de simulación de ataque en el portal Microsoft 365 Defender ataque.](../../media/attack-sim-training-sim-automations-create.png)

3. Se abrirá el Asistente para creación. El resto de este artículo describe las páginas y la configuración que contienen.

> [!NOTE]
> En cualquier momento durante el asistente  para la creación de simulación, puede hacer clic en Guardar y cerrar para guardar el progreso y continuar configurando la simulación más adelante. La simulación incompleta tiene el **valor de Estado** **Borrador** en la **ficha Simulaciones.** Puede elegir dónde lo dejó seleccionando la simulación y haciendo clic ![ en Editar icono de simulación.](../../media/m365-cc-sc-edit-icon.png) **Edite** simulation.## Name y describa la simulación.

## <a name="automation-name"></a>Nombre de automatización

En la **página Nombre de** automatización, configure las siguientes opciones:

- **Nombre:** escriba un nombre descriptivo único para la simulación.
- **Descripción:** escriba una descripción detallada opcional para la simulación.

Cuando termine, haga clic en **Siguiente**.

## <a name="run-conditions"></a>Condiciones de ejecución

En la **página Condiciones de** ejecución, seleccione las condiciones del ataque de suplantación de identidad real que determina cuándo se ejecutará la automatización.

Puede usar cada condición solo una vez. Varias condiciones usan lógica AND ( \<Condition1\> y \<Condition2\> ).

![Agregar icono de condición.](../../media/m365-cc-sc-create-icon.png) **Agregar condición**.

- **No. de los usuarios destinados a la campaña:** Configure las siguientes opciones:
  - **Igual a**, **Less than**, **Greater than**, Less than or equal **to**, or Greater than or **equal to**.
  - **Escriba valor:** el número de usuarios a los que se ha dirigido la campaña de suplantación de identidad.
- **Campañas con una técnica de phishing específica:** seleccione uno de los valores disponibles:
  - **Recolección de credenciales**
  - **Datos adjuntos de malware**
  - **Vínculo en datos adjuntos**
  - **Vínculo a malware**
  - **Dirección URL de unidad por**
- **Dominio de remitente específico:** escriba un valor de dominio de correo electrónico del remitente (por ejemplo, contoso.com).
- **Nombre de remitente específico:** escriba un valor de nombre de remitente.
- **Correo electrónico de remitente** específico: escriba una dirección de correo electrónico del remitente.
- **Destinatarios de usuarios y grupos específicos:** empiece a escribir el nombre o la dirección de correo electrónico del usuario o grupo. Cuando aparezca, selecciónelo.

Para quitar una condición después de agregarla, haga clic en ![Icono Quitar.](../../media/m365-cc-sc-delete-icon.png).

Cuando termine, haga clic en **Siguiente**.

## <a name="review-automation"></a>Revisar la automatización

En la **página Revisar automatización,** puede revisar los detalles de la automatización de carga.

Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

Cuando haya terminado, haga clic en **Enviar**.
