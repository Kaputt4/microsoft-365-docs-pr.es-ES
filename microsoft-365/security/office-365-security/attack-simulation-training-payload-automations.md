---
title: Automatizaciones de cargas útiles para Entrenamiento de simulación de ataque
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Los administradores pueden aprender a usar automatizaciones de carga útil (recopilación de carga) para recopilar e iniciar simulaciones automatizadas para Entrenamiento de simulación de ataque en Microsoft Defender para Office 365 Plan 2.
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: eedb00fc7c53a9e0165f1f25bbac4c5cb5af199d
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68092608"
---
# <a name="payload-automations-for-attack-simulation-training"></a>Automatizaciones de cargas útiles para Entrenamiento de simulación de ataque

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

En Entrenamiento de simulación de ataque en Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2, las automatizaciones de carga útil (también conocidas como _recopilación de carga_) recopilan información de los mensajes de ataque de suplantación de identidad (phishing) del mundo real notificados por los usuarios en su organización. Aunque es probable que el número de estos mensajes sea bajo en su organización, puede especificar las condiciones que se deben buscar en los ataques de suplantación de identidad (por ejemplo, destinatarios, técnica de ingeniería social, información del remitente, etc.). Entrenamiento de simulación de ataque imitará los mensajes y las cargas que se usan en el ataque para iniciar automáticamente simulaciones inofensivas a los usuarios de destino.

Para ver las automatizaciones de carga disponibles, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email & pestaña \> **Colaboración** \> **Entrenamiento de simulación de ataque** \> **Automatizaciones** y, a continuación, seleccione **Automatizaciones de carga**. Para ir directamente a la pestaña **Automatizaciones** , donde puede seleccionar **Automatizaciones de carga**, use <https://security.microsoft.com/attacksimulator?viewid=automations>.

Se muestra la siguiente información para cada automatización de carga:

- **Nombre de automation**
- **Tipo**: el valor es **Payload**.
- **Elementos recopilados**
- **Última modificación**
- **Estado**: el valor es **Listo** o **Borrador**.

Al seleccionar una automatización de carga de la lista, aparece un control flotante de detalles con la siguiente información:

- **Pestaña General** : muestra información básica sobre la automatización de simulación.
- **Pestaña Historial de ejecución** : esta pestaña solo está disponible para las automatizaciones de carga con el valor **Estado** **listo**.

## <a name="create-payload-automations"></a>Creación de automatizaciones de carga

Para crear una automatización de carga, siga estos pasos:

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com/>, vaya a **Email & pestaña** \> Automatizaciones de la colaboración \> **Entrenamiento de simulación de ataque** \> **automatizaciones**. Para ir directamente a la pestaña **Automatizaciones** , donde puede seleccionar **Automatizaciones de carga**, use <https://security.microsoft.com/attacksimulator?viewid=automations>.

   Haga clic en ![el icono Crear automatización.](../../media/m365-cc-sc-create-icon.png) **Crear automatización**.

   :::image type="content" source="../../media/attack-sim-training-sim-automations-create.png" alt-text="El botón Crear simulación de la pestaña Automatizaciones de carga de Entrenamiento de simulación de ataque en el portal de Microsoft 365 Defender" lightbox="../../media/attack-sim-training-sim-automations-create.png":::

   > [!NOTE]
   > En cualquier momento durante el asistente para la creación, puede hacer clic en **Guardar y cerrar** para guardar el progreso y seguir configurando la automatización de la carga más adelante. Puede seleccionar dónde lo dejó seleccionando la automatización de carga en **Automatizaciones** de carga y, a continuación, haga clic en ![el icono Editar automatización.](../../media/m365-cc-sc-edit-icon.png) **Edite la automatización**. La automatización de carga parcialmente completada tendrá el valor **Estado** **Borrador**.

2. En la página **Nombre de Automation** , configure los siguientes valores:

   - **Nombre**: escriba un nombre descriptivo único para la automatización de carga.
   - **Descripción**: escriba una descripción detallada opcional para la automatización de la carga.

   Cuando termine, haga clic en **Siguiente**.

3. En la página **Condiciones de ejecución** , seleccione las condiciones del ataque de suplantación de identidad real que determina cuándo se ejecutará la automatización.

   Haga clic en ![el icono Agregar condición.](../../media/m365-cc-sc-create-icon.png) **Agregue la condición** y seleccione una de las condiciones siguientes:

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

   Puede usar cada condición solo una vez. Varias condiciones usan lógica AND (\<Condition1\> y \<Condition2\>).

   Para agregar otra condición, haga clic en el ![icono Agregar condición.](../../media/m365-cc-sc-create-icon.png) **Agregar condición**.

   Para quitar una condición después de agregarla, haga clic en ![Icono Quitar.](../../media/m365-cc-sc-delete-icon.png).

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Revisar automatización** , puede revisar los detalles de la automatización de la carga.

   Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   Cuando haya terminado, haga clic en **Enviar**.

5. En la página **Nueva automatización creada** , puede usar los vínculos para activar la automatización o ir a la página **Simulaciones** .

   Cuando haya terminado, haga clic en **Listo**.

De nuevo en **automatizaciones de carga** en **Automations**, la página de inicio de sesión que creó ahora es una lista.

## <a name="turn-payload-automations-on-or-off"></a>Activar o desactivar las automatizaciones de carga

Solo puede activar o desactivar las automatizaciones de carga en las que el valor **estado** es **Listo**. No se pueden activar ni desactivar automatizaciones de carga incompletas donde el valor **estado** es **Borrador**.

Para activar una automatización de carga, selecciónela en la lista haciendo clic en la casilla. Haga clic en el ![icono Activar.](../../media/m365-cc-sc-turn-on-off-icon.png) **Active el** icono que aparece y, a continuación, haga clic en **Confirmar** en el cuadro de diálogo.

Para desactivar una automatización de carga, selecciónela en la lista haciendo clic en la casilla. Haga clic en el ![icono Desactivar.](../../media/m365-cc-sc-turn-on-off-icon.png) **Active el** icono que aparece y, a continuación, haga clic en **Confirmar** en el cuadro de diálogo.

## <a name="modify-payload-automations"></a>Modificación de automatizaciones de carga

Para modificar una automatización de carga existente en **automatizaciones de carga** útil, realice uno de los pasos siguientes:

- Seleccione la automatización de carga de la lista haciendo clic en la casilla. Haga clic en el ![icono Editar automatización.](../../media/m365-cc-sc-edit-icon.png) **Icono de edición de automatización** que aparece.
- Seleccione la automatización de carga de la lista haciendo clic en cualquier lugar de la fila excepto en la casilla. En el control flotante de detalles que se abre, en la pestaña **General** , haga clic en **Editar** en las secciones **Nombre**, **Descripción** o **Condiciones de ejecución** .

El asistente para automatización de carga se abre con la configuración y los valores de la automatización de carga seleccionada. Los pasos son los mismos que se describen en la sección [Crear automatizaciones de carga](#create-payload-automations) .

## <a name="remove-payload-automations"></a>Eliminación de automatizaciones de carga

Para quitar una automatización de carga, seleccione la automatización de carga de la lista haciendo clic en la casilla. Haga clic en el ![icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Elimine** el icono que aparece y, a continuación, haga clic en **Confirmar** en el cuadro de diálogo.

## <a name="related-links"></a>Vínculos relacionados

[Introducción al uso de aprendizaje de simulación de ataques](attack-simulation-training-get-started.md)

[Automatizaciones de simulación para Entrenamiento de simulación de ataque](attack-simulation-training-simulation-automations.md)

[Obtenga información a través de la formación de simulación de ataques](attack-simulation-training-insights.md)
