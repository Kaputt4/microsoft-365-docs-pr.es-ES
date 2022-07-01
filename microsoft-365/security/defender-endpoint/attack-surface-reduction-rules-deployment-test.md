---
title: Probar las reglas de reducción de la superficie expuesta a ataques (ASR)
description: Proporciona instrucciones para probar la implementación de reglas de reducción de superficie expuesta a ataques (ASR).
keywords: Implementación de reglas de reducción de superficie expuesta a ataques, implementación de ASR, habilitación de reglas de asr, configuración de ASR, sistema de prevención de intrusiones de host, reglas de protección, reglas contra vulnerabilidades de seguridad, protección contra vulnerabilidades de seguridad, reglas de vulnerabilidad de seguridad, reglas de prevención de infecciones, Microsoft Defender para punto de conexión, configurar reglas asr
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 8bfe3e0d36a02831b5673b92217152ce87804d0a
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66601298"
---
# <a name="test-attack-surface-reduction-asr-rules"></a>Probar las reglas de reducción de la superficie expuesta a ataques (ASR)

Probar las reglas de reducción de superficie expuesta a ataques (ASR) le ayuda a determinar si las reglas impedirán las operaciones de línea de negocio antes de habilitar cualquier regla. Al empezar con un grupo pequeño y controlado, puede limitar las posibles interrupciones del trabajo a medida que expande la implementación en toda la organización.

Comience la implementación de las reglas de reducción de la superficie expuesta a ataques (ASR) con el anillo 1.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-testing-steps.png" alt-text="Pasos de prueba de reglas de ASR" lightbox="images/asr-rules-testing-steps.png":::
  
## <a name="step-1-test-asr-rules-using-audit"></a>Paso 1: Probar reglas asr mediante auditoría

Para comenzar la fase de prueba, active las reglas de ASR con las reglas establecidas en Auditar, empezando por los usuarios o dispositivos campeones en el anillo 1. Normalmente, la recomendación es habilitar todas las reglas (en Auditoría) para que pueda determinar qué reglas se desencadenan durante la fase de prueba. Tenga en cuenta que las reglas establecidas en Audit no afectan generalmente a la funcionalidad de la entidad o entidad a la que se aplica la regla, sino que generan eventos registrados para la evaluación; no hay ningún efecto en los usuarios finales.

### <a name="configure-asr-rules-using-mem"></a>Configuración de reglas de ASR mediante MEM

Puede usar Microsoft Endpoint Manager (MEM) Endpoint Security para configurar reglas ASR personalizadas.

1. Abra [el Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home).
2. Vaya a **Reducción de la superficie expuesta a ataques** de seguridad  >  de **punto de conexión**.
3. Seleccione **Crear directiva**.
4. En **Plataforma**, seleccione **Windows 10 y versiones posteriores** y, en **Perfil**, seleccione **Reglas de reducción de superficie expuesta a ataques**.
  
    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/asr-mem-create-profile.png" alt-text="Página de creación de perfiles para reglas de ASR" lightbox="images/asr-mem-create-profile.png":::

5. Haga clic en **Crear**.
6. En la pestaña **Aspectos básicos** del panel **Crear perfil** , en **Nombre** , agregue un nombre para la directiva. En **Descripción** , agregue una descripción para la directiva de reglas de ASR.
7. En la pestaña **Configuración** , en **Reglas de reducción de superficie expuesta a ataques**, establezca todas las reglas en **modo auditoría**.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/asr-mem-configuration-settings.png" alt-text="Configuración de reglas de ASR en modo auditoría" lightbox="images/asr-mem-configuration-settings.png":::

    >[!Note]
    >Hay variaciones en algunas listas de modo de reglas de ASR; _Bloqueados_ y _habilitados_ proporcionan la misma funcionalidad.

8. [Opcional] En el panel **Etiquetas de ámbito** , puede agregar información de etiquetas a dispositivos específicos. También puede usar etiquetas de ámbito y control de acceso basadas en rol para asegurarse de que los administradores adecuados tienen el acceso y la visibilidad adecuados a los objetos Intune adecuados. Más información: [Use el control de acceso basado en rol (RBAC) y las etiquetas de ámbito para ti distribuida en Intune](/mem/intune/fundamentals/scope-tags).
9. En el panel **Asignaciones** , puede implementar o "asignar" el perfil a los grupos de usuarios o dispositivos. Más información: [Asignación de perfiles de dispositivo en Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)
10. Revise la configuración en el panel **Revisar y crear** . Haga clic en **Crear** para aplicar las reglas.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/asr-mem-review-create.png" alt-text="Página Crear perfil" lightbox="images/asr-mem-review-create.png":::

La nueva directiva de reducción de la superficie expuesta a ataques para las reglas de ASR se muestra en **Seguridad del punto de conexión | Reducción de la superficie expuesta a ataques**.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/asr-mem-my-asr-rules.png" alt-text=" Página Reducción de superficie expuesta a ataques" lightbox="images/asr-mem-my-asr-rules.png":::

## <a name="step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>Paso 2: Descripción de la página de informes de reglas de reducción de superficie expuesta a ataques en el portal de Microsoft 365 Defender

La página de informes de reglas de ASR se encuentra en **Microsoft 365 Defender portal** > **informa de** > **las reglas de reducción de la superficie expuesta a ataques**. Esta página tiene tres pestañas:

- Detections
- Configuración
- Agregar exclusiones

### <a name="detections-tab"></a>Pestaña Detecciones

Proporciona una escala de tiempo de 30 días de eventos de auditoría y bloqueados detectados.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-01.png" alt-text="Pestaña Detecciones de reglas de reducción de superficie expuesta a ataques" lightbox="images/asr-defender365-01.png":::

El panel Reglas de reducción de superficie expuesta a ataques proporciona información general sobre los eventos detectados por regla.

>[!Note]
>Hay algunas variaciones en los informes de reglas de ASR. Microsoft está en proceso de actualizar el comportamiento de los informes de reglas de ASR para proporcionar una experiencia coherente.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-01b.png" alt-text="Página Reglas de reducción de superficie expuesta a ataques" lightbox="images/asr-defender365-01b.png"::: 

Haga clic en **Ver detecciones** para abrir la pestaña **Detecciones** .

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-reports-detections.png" alt-text="Detecciones de reglas de reducción de superficie expuesta a ataques" lightbox="images/asr-defender365-reports-detections.png":::

El panel **GroupBy** y **Filter** proporcionan las siguientes opciones:

**GroupBy** devuelve los resultados establecidos en los grupos siguientes:

- Sin agrupación
- Archivo detectado
- Auditoría o bloque
- Rule
- Aplicación de origen
- Device
- Usuario
- Publisher

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-reports-detections.png" alt-text="El filtro GroupBy de detecciones de reglas de reducción de superficie expuesta a ataques" lightbox="images/asr-defender365-reports-detections.png":::

**Filter** abre la página **Filter on rules (Filtrar en reglas** ), que permite limitar los resultados solo a las reglas de ASR seleccionadas:

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-filter.png" alt-text="Las detecciones de reglas de reducción de superficie expuesta a ataques se filtran en las reglas" lightbox="images/asr-defender365-filter.png":::

>[!Note]
>Si tiene una licencia de Microsoft Microsoft 365 Security E5 o A5, Windows E5 o A5, el vínculo siguiente abre la pestaña Informes de Microsoft Defender 365 > [Reducciones de superficie expuesta a ataques](https://security.microsoft.com/asr?viewid=detections) > Detecciones.

### <a name="configuration-tab"></a>Pestaña Configuración

Enumera, por equipo, el estado agregado de las reglas de ASR: Desactivado, Auditar, Bloquear.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-configurations.png" alt-text="La pestaña Configuración de las reglas de reducción de superficie expuesta a ataques y una entrada en su página" lightbox="images/asr-defender365-configurations.png":::

En la pestaña Configuraciones, puede comprobar, por dispositivo, qué reglas de ASR están habilitadas y en qué modo, seleccionando el dispositivo para el que desea revisar las reglas de ASR.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-configurations.settings.png" alt-text="Las reglas de reducción de superficie expuesta a ataques habilitadas y el modo" lightbox="images/asr-defender365-configurations.settings.png":::

El vínculo **Introducción** abre el Centro de administración de Microsoft Endpoint Manager, donde puede crear o modificar una directiva de endpoint protection para ASR:

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem1.png" alt-text="Elemento de menú *Seguridad de punto de conexión en la página Información general" lightbox="images/asr-defender365-05b-mem1.png":::

En seguridad de punto de conexión | Información general, seleccione **Reducción de superficie expuesta a ataques**:

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem2.png" alt-text="Reducción de la superficie expuesta a ataques en MEM" lightbox="images/asr-defender365-05b-mem2.png":::

El | de seguridad del punto de conexión Se abre el panel Reducción de superficie expuesta a ataques:

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem3.png" alt-text="Panel Reducción de la superficie expuesta a ataques de seguridad de punto de conexión" lightbox="images/asr-defender365-05b-mem3.png":::

>[!Note]
>Si tiene una licencia de Microsoft Defender 365 E5 (o Windows E5?), este vínculo abrirá la pestaña Informes de Microsoft Defender 365 > Reducciones de superficie expuesta a ataques > [Configuraciones](https://security.microsoft.com/asr?viewid=configuration) .

### <a name="add-exclusions"></a>Agregar exclusiones

Esta pestaña proporciona un método para seleccionar entidades detectadas (por ejemplo, falsos positivos) para la exclusión. Cuando se agregan exclusiones, el informe proporciona un resumen del impacto esperado.

>[!Note]
> Las exclusiones de Antivirus de Microsoft Defender se respetan con las reglas de ASR.  Consulte [Configuración y validación de exclusiones basadas en la extensión, el nombre o la ubicación](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

> [!div class="mx-imgBorder"]
> :::image type="content" source="Images/asr-defender365-06d.png" alt-text="Panel para la exclusión del archivo detectado" lightbox="Images/asr-defender365-06d.png":::

> [!Note]
>Si tiene una licencia de Microsoft Defender 365 E5 (o Windows E5?), este vínculo abrirá la pestaña Informes de Microsoft Defender 365 > Reducciones de superficie expuesta a [ataques > Exclusiones](https://security.microsoft.com/asr?viewid=exclusions) .

### <a name="use-powershell-as-an-alternative-method-to-enable-asr-rules"></a>Uso de PowerShell como método alternativo para habilitar reglas de ASR

Puede usar PowerShell, como alternativa a MEM, para habilitar las reglas de ASR en modo de auditoría para ver un registro de aplicaciones que se habrían bloqueado si la característica estuviera totalmente habilitada. También puede hacerse una idea de la frecuencia con la que se activarán las reglas durante el uso normal.

Para habilitar una regla de reducción de superficie expuesta a ataques en modo de auditoría, use el siguiente cmdlet de PowerShell:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Donde `<rule ID>` es un [valor GUID de la regla de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md).

Para habilitar todas las reglas de reducción de superficie expuesta a ataques agregadas en modo de auditoría, use el siguiente cmdlet de PowerShell:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Si desea auditar por completo cómo funcionarán las reglas de reducción de superficie expuesta a ataques en su organización, deberá usar una herramienta de administración para implementar esta configuración en los dispositivos de las redes.

También puede usar proveedores de servicios de configuración de directiva de grupo, Intune o administración de dispositivos móviles (MDM) para configurar e implementar la configuración. Obtenga más información en el artículo principal [Reglas de reducción de superficie expuesta a ataques](attack-surface-reduction.md) .

## <a name="use-windows-event-viewer-review-as-an-alternative-to-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>Usar Windows Visor de eventos Review como alternativa a la página de informes de reglas de reducción de superficie expuesta a ataques en el portal de Microsoft 365 Defender

Para revisar las aplicaciones que se habrían bloqueado, abra Visor de eventos y filtre por el identificador de evento 1121 en el registro Microsoft-Windows-Windows Defender/Operational. En la tabla siguiente se enumeran todos los eventos de protección de red.

Id. de evento | Descripción
-|-
 5007 | Evento cuando se cambia la configuración
 1121 | Evento cuando se activa una regla de reducción de superficie expuesta a ataques en modo de bloque
 1122 | Evento cuando se activa una regla de reducción de superficie expuesta a ataques en modo de auditoría

## <a name="additional-topics-in-this-deployment-collection"></a>Temas adicionales de esta colección de implementación

[Introducción a la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment.md)

[Planear la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-plan.md)

[Habilitar reglas de la reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-implement.md)

[Operacionar reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-operationalize.md)

[Referencia de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-reference.md)
