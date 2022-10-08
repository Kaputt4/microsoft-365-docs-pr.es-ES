---
title: Informes de reglas de reducción de superficie expuesta a ataques (ASR)
description: Proporciona información sobre las detecciones de reglas de reducción de superficie expuesta a ataques (ASR), la configuración, las amenazas de bloque y los métodos para habilitar tres reglas y exclusiones estándar.
keywords: Reglas de reducción de superficie expuesta a ataques, ASR, reglas de asr, caderas, sistema de prevención de intrusiones del host, reglas de protección, reglas contra vulnerabilidades de seguridad, antiexploit, reglas de vulnerabilidad de seguridad, reglas de prevención de infecciones, Microsoft Defender para punto de conexión, configurar reglas asr, descripción de la regla asr
ms.mktglfcycl: manage
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar,
manager: dansimp
ms.custom: asr
ms.topic: article
ms.collection:
- m365-security
- tier2
ms.date: 08/25/2022
search.appverid: met150
ms.openlocfilehash: 87aafd6add0d75ec19a621ef46d7beed7cbbb5c6
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68148821"
---
# <a name="attack-surface-reduction-asr-rules-report"></a>Informe de reglas de reducción de superficie expuesta a ataques (ASR)

**Se aplica a:**

- [Microsoft Microsoft 365 Defender para el plan de punto de conexión 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataformas:**

- Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

El informe de reglas de reducción de superficie expuesta a ataques (ASR) proporciona información sobre las _reglas de reducción de superficie expuesta a ataques_ que se aplican a los dispositivos de la organización. Este informe también proporciona información sobre:

- amenazas detectadas
- amenazas bloqueadas
- dispositivos que no están configurados para usar las reglas de protección estándar para bloquear amenazas

Además, este informe proporciona una interfaz fácil de usar que le permite:

- Visualización de detecciones de amenazas
- Visualización de la configuración de las reglas de ASR
- Configurar exclusiones (agregar)
- Active fácilmente la _protección básica_ habilitando las tres reglas de ASR más recomendadas con un solo botón de alternancia.
- Explorar en profundidad para recopilar información detallada

Para obtener más información sobre las reglas de reducción de superficie expuesta a ataques individuales, consulte [Referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md).

## <a name="prerequisites"></a>Requisitos previos

> [!IMPORTANT]
> Para que Windows&nbsp;Server&nbsp;2012&nbsp;R2 y Windows&nbsp;Server&nbsp;2016 aparezcan en el **informe Reglas de reducción de superficie expuesta a ataques**, estos dispositivos deben incorporarse mediante el paquete de solución unificada moderna. Para obtener más información, consulte [Nueva funcionalidad en la solución unificada moderna para Windows Server 2012 R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution).

## <a name="report-access-permissions"></a>Permisos de acceso de informes

Para acceder al **informe reglas de reducción de superficie expuesta a ataques** en el panel seguridad de Microsoft 365, se requieren los permisos siguientes:

| Tipo de permiso | Permiso | Nombre para mostrar del permiso |
|:---|:---|:---|
| Application | Machine.Read.All | "Leer todos los perfiles de máquina" |
|Delegado (cuenta profesional o educativa) | Machine.Read | "Leer información de la máquina" |

Para asignar estos permisos:

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con una cuenta con el administrador de seguridad o Administrador global rol asignado.
1. En el panel de navegación, seleccione **Configuración** \> **Roles de puntos** \> de conexión (en **Permisos**).
1. Seleccione el rol que desea editar.
1. Seleccione **Editar**.
1. En **Editar rol**, en la pestaña **General** , en **Nombre del** rol, escriba un nombre para el rol.
1. En **Descripción** , escriba un breve resumen del rol.
1. En **Permisos**, seleccione **Ver datos** y, en **Ver datos** , seleccione **Reducción de superficie expuesta a ataques**.

Para obtener más información sobre la administración de roles de usuario, consulte [Creación y administración de roles para el control de acceso basado en rol](user-roles.md).

## <a name="navigation"></a>Navegación

Para ir a las tarjetas de resumen del informe de reglas de reducción de superficie expuesta a ataques

1. Abra **Microsoft 365 Defender** portal.
1. En el panel izquierdo, haga clic en **Informes** y, en la sección principal, en **Informes** , seleccione **Informe de seguridad**.
1. Desplácese hacia abajo hasta **Dispositivos** para buscar las tarjetas de resumen **de las reglas de reducción de superficie expuesta a ataques** .

Las tarjetas de informe de resumen para las reglas asr se muestran en la siguiente ilustración.

>:::image type="content" source="images/attack-surface-reduction-rules-report-summary.png" alt-text="Muestra las tarjetas de resumen del informe de reglas de ASR" lightbox="images/attack-surface-reduction-rules-report-summary.png":::

## <a name="asr-rules-report-summary-cards"></a>Tarjetas de resumen del informe de reglas de ASR

El resumen del informe de reglas de ASR se divide en dos tarjetas:

- [**Tarjeta de resumen de detecciones de reglas de ASR**](#asr-rules-detections-summary-card)
- [Tarjeta de resumen de **configuración de reglas ASR**](#asr-rules-configuration-summary-card)

### <a name="asr-rules-detections-summary-card"></a>Tarjeta de resumen de detecciones de reglas de ASR

Muestra un resumen del número de amenazas detectadas bloqueadas por las reglas de ASR.

Proporciona dos botones de "acción":

- Visualización de detecciones: abre las **reglas de reducción de superficie expuesta a ataques** > pestaña **Detecciones** principal
- Agregar exclusiones: abre las **reglas de reducción de superficie expuesta a ataques** > pestaña **Exclusiones** principal

:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-card.png" alt-text="Muestra la tarjeta de detecciones de resumen del informe de reglas de ASR." lightbox="images/attack-surface-reduction-rules-report-main-detections-card.png":::

Al hacer clic en el vínculo **Detecciones de reglas de ASR** en la parte superior de la tarjeta también se abre la [pestaña Detecciones de reglas de reducción de superficie expuesta a ataques](#attack-surface-reduction-rules-main-detections-tab).

### <a name="asr-rules-configuration-summary-card"></a>Tarjeta de resumen de configuración de reglas de ASR

**La sección superior** se centra en tres reglas recomendadas, que protegen contra técnicas de ataque comunes. Esta tarjeta muestra información de estado actual sobre los equipos de la organización que tienen las siguientes [reglas de protección estándar de tres \(ASR\)](#simplified-standard-protection-option) establecidas en **modo de bloque**, **modo auditoría** o **desactivado** (no configurado). El botón **Proteger dispositivos** mostrará detalles de configuración completos solo para las tres reglas; los clientes pueden tomar medidas rápidamente para habilitar estas reglas.

**La sección inferior** expone seis reglas en función del número de dispositivos no protegidos por regla. El botón "Ver configuración" muestra todos los detalles de configuración de todas las reglas de ASR. El botón "Agregar exclusión" muestra la página agregar exclusión con todos los nombres de archivo o proceso detectados enumerados para que Security Operation Center (SOC) se evalúe. La página **Agregar exclusión** está vinculada a Microsoft Endpoint Manager (MEM).

Proporciona dos botones de "acción":

- Ver configuración: abre las **reglas de reducción de superficie expuesta a ataques** > pestaña **Detecciones** principal
- Agregar exclusiones: abre las **reglas de reducción de superficie expuesta a ataques** > pestaña **Exclusiones** principal

:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-configuration-card.png" alt-text="Muestra la tarjeta de configuración de resumen del informe de reglas de ASR." lightbox="images/attack-surface-reduction-rules-report-main-detections-configuration-card.png":::

Al hacer clic en el vínculo **de configuración de reglas de ASR** en la parte superior de la tarjeta también se abre la [pestaña Configuración de las reglas de reducción de superficie expuesta a ataques](#attack-surface-reduction-rules-main-configuration-tab).

#### <a name="simplified-standard-protection-option"></a>Opción de protección estándar simplificada

La tarjeta de resumen de configuración proporciona un botón para **proteger dispositivos** con las tres reglas de protección estándar. Como mínimo, Microsoft recomienda habilitar estas tres reglas de protección estándar de reducción de superficie expuesta a ataques:

- [Bloquear el robo de credenciales del subsistema de autoridad de seguridad local de Windows (lsass.exe)](attack-surface-reduction-rules-reference.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem)
- [Bloquear el abuso de controladores firmados vulnerables explotados](attack-surface-reduction-rules-reference.md#block-abuse-of-exploited-vulnerable-signed-drivers)
- [Bloquear la persistencia a través de la suscripción de eventos de Instrumental de administración de Windows (WMI)](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription)

Para habilitar las tres reglas de protección estándar:

1. Seleccione **Proteger dispositivos**. Se abre la pestaña **Configuración** principal.
1. En la pestaña **Configuración** , **las reglas básicas** alternan automáticamente de **Todas las reglas** a **Reglas de protección estándar** habilitadas.
1. En la lista **Dispositivos** , seleccione los dispositivos para los que desea que se apliquen las reglas de protección estándar y, a continuación, seleccione **Guardar**.

Esta tarjeta tiene otros dos botones de navegación:

- **Ver configuración** : abre las **reglas de reducción de superficie expuesta a ataques** > pestaña **Configuración** principal.
- **Agregar exclusiones** : abre las **reglas de reducción de superficie expuesta a ataques** > pestaña **Exclusiones** principal.

Al hacer clic en el vínculo **de configuración de reglas de ASR** en la parte superior de la tarjeta también se abre la [pestaña Configuración de las reglas de reducción de superficie expuesta a ataques](#attack-surface-reduction-rules-main-configuration-tab).

## <a name="attack-surface-reduction-rules-main-tabs"></a>Pestañas principales de las reglas de reducción de superficie expuesta a ataques

Aunque las tarjetas de resumen del informe de reglas de ASR son útiles para obtener un resumen rápido del estado de las reglas de ASR, las pestañas principales proporcionan información más detallada con funcionalidades de filtrado y configuración:

- [Pestaña Detecciones](#attack-surface-reduction-rules-main-detections-tab)
- [Pestaña Configuración](#attack-surface-reduction-rules-main-configuration-tab)
- [Pestaña Exclusiones](#attack-surface-reduction-rules-add-exclusions-tab)

### <a name="search-capabilities"></a>Funciones de búsqueda

 La funcionalidad de búsqueda se agrega a las pestañas principales **Detección**, **Configuración** y **Agregar exclusión** . Con esta funcionalidad, puede buscar mediante el identificador de dispositivo, el nombre de archivo o el nombre del proceso.

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-tabs-search.png" alt-text="Muestra la característica de búsqueda de informes de reglas ASR." lightbox="images/attack-surface-reduction-rules-report-main-tabs-search.png":::

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-tabs-search-configuration-tab.png" alt-text="Muestra la característica de búsqueda de informes de reglas ASR en la pestaña de configuración." lightbox="images/attack-surface-reduction-rules-report-main-tabs-search-configuration-tab.png":::

### <a name="filtering"></a>Filtrado

El filtrado proporciona una manera de especificar qué resultados se devuelven:

- **Date**  permite especificar un intervalo de fechas para los resultados de los datos.
- **Filters**

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-filtering.png" alt-text="Muestra la característica de filtrado de informes de reglas de ASR" lightbox="images/attack-surface-reduction-rules-report-main-detections-filtering.png":::

### <a name="attack-surface-reduction-rules-main-detections-tab"></a>Pestaña de detecciones principales de las reglas de reducción de superficie expuesta a ataques

- **Detecciones de auditoría**  Muestra cuántas detecciones de amenazas se capturaron mediante reglas establecidas en el modo _auditoría_ .
- **Detecciones bloqueadas** Muestra cuántas detecciones de amenazas se bloquearon mediante reglas establecidas en modo _de bloque_ .
- **Gráfico grande y consolidado** Muestra las detecciones bloqueadas y auditadas.

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-tab.png" alt-text="Muestra la pestaña de detecciones principales del informe de reglas de ASR, con _Audit detections_ y _Blocked detections_ descritos." lightbox="images/attack-surface-reduction-rules-report-main-detections-tab.png":::

Los gráficos proporcionan datos de detección sobre el intervalo de fechas mostrado, con la capacidad de mantener el puntero sobre una ubicación específica para recopilar información específica de la fecha.

En la sección inferior del informe se enumeran las amenazas detectadas ,por dispositivo, con los campos siguientes:

| Nombre del campo| Definición |
|:---|:---|
| Archivo detectado | El archivo determinado para contener una amenaza posible o conocida |
| Detectado en | La fecha en que se detectó la amenaza |
| ¿Bloqueado\/auditado? | Si la regla de detección para el evento específico estaba en modo de bloque o auditoría |
| Rule | ¿Qué regla detectó la amenaza? |
| Aplicación de origen | La aplicación que realizó la llamada al "archivo detectado" infractor |
| Device | Nombre del dispositivo en el que se produjo el evento Audit o Block |
| Grupo de dispositivos | Grupo de Active Directory al que pertenece el dispositivo |
| User |  La cuenta de equipo responsable de la llamada |
| Publisher | La empresa que publicó el .exe o la aplicación en particular |

Para obtener más información sobre los modos de bloque y auditoría de reglas ASR, consulte [Modos de regla de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md#asr-rule-modes).

#### <a name="actionable-flyout"></a>Control flotante accionable

La página principal "Detección" tiene una lista de todas las detecciones (archivos o procesos) en los últimos 30 días. Seleccione cualquiera de las detecciones para abrir con funcionalidades de exploración en profundidad.

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-flyout.png" alt-text="Muestra el control flotante de la pestaña de detecciones principales del informe de reglas de ASR." lightbox="images/attack-surface-reduction-rules-report-main-detections-flyout.png":::

La sección **Posible exclusión e impacto** proporciona el impacto del archivo o proceso seleccionado. Puede:

- Seleccione **Ir a la búsqueda** , que abre la página de consulta búsqueda avanzada.
- **La página Abrir archivo** se abre Microsoft Defender para punto de conexión detección (MDE)
- El botón **Agregar exclusión** está vinculado a la página principal agregar exclusión.

En la imagen siguiente se muestra cómo se abre la página de consulta búsqueda avanzada desde el vínculo del control flotante accionable:

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-detections-flyout-hunting.png" alt-text="Muestra el informe de reglas (ASR) del vínculo flotante de la pestaña de detecciones principales que abre búsqueda avanzada" lightbox="images/attack-surface-reduction-rules-report-main-detections-flyout-hunting.png":::

Para obtener más información sobre la búsqueda avanzada, vea [Búsqueda proactiva de amenazas con búsqueda avanzada en Microsoft 365 Defender](advanced-hunting-overview.md)

### <a name="attack-surface-reduction-rules-main-configuration-tab"></a>Reglas de reducción de superficie expuesta a ataques pestaña configuración principal

La pestaña **configuración** principal de reglas de ASR proporciona detalles de configuración de reglas ASR de resumen y por dispositivo. Hay tres aspectos principales en la pestaña Configuración:

**Reglas básicas** Proporciona un método para alternar los resultados entre **reglas básicas** y **todas las reglas**. De forma predeterminada, se selecciona **Reglas básicas** .

**Introducción a la configuración del dispositivo** Proporciona una instantánea actual de los dispositivos en uno de los siguientes estados:

- Todos los dispositivos expuestos (dispositivos con requisitos previos que faltan, reglas en modo auditoría, reglas mal configuradas o reglas no configuradas)
- Dispositivos con reglas no configuradas
- Dispositivos con reglas en modo de auditoría
- Dispositivos con reglas en modo de bloque

**La sección inferior sin nombre** de la pestaña Configuración proporciona una lista del estado actual de los dispositivos (por dispositivo):

- Dispositivo (nombre)
- Configuración general (independientemente de si hay reglas activadas o todas desactivadas)
- Reglas en modo de bloque (número de reglas por dispositivo establecidas para bloquear)
- Reglas en modo de auditoría (número de reglas en modo de auditoría)
- Reglas desactivadas (reglas que están desactivadas o no están habilitadas)
- Id. de dispositivo (GUID del dispositivo)

Estos elementos se muestran en la ilustración siguiente.

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-configuration-tab.png" alt-text="Muestra la pestaña de configuración principal del informe de reglas de ASR" lightbox="images/attack-surface-reduction-rules-report-main-configuration-tab.png":::

Para habilitar las reglas de ASR:

1. En **Dispositivo**, seleccione el dispositivo o los dispositivos para los que desea aplicar las reglas de ASR.
1. En la ventana flotante, compruebe las selecciones y, a continuación, seleccione **Agregar a la directiva**.

La pestaña **Configuración** y el control flotante _Agregar regla_ se muestran en la siguiente imagen.

> [NOTA!] Si tiene dispositivos que requieren que se apliquen reglas ASR diferentes, debe configurarlos individualmente.

>:::image type="content" source="images/attack-surface-reduction-rules-report-configuration-add-to-policy.png" alt-text="Muestra el control flotante de reglas de ASR para agregar reglas de ASR a los dispositivos" lightbox="images/attack-surface-reduction-rules-report-configuration-add-to-policy.png":::

### <a name="attack-surface-reduction-rules-add-exclusions-tab"></a>Reglas de reducción de superficie expuesta a ataques Pestaña Agregar exclusiones

La pestaña **Agregar exclusiones** presenta una lista clasificada de detecciones por nombre de archivo y proporciona un método para configurar exclusiones. De forma predeterminada, se muestra **la información agregar exclusiones** para tres campos:

- **Nombre de archivo** Nombre del archivo que desencadenó el evento de reglas de ASR.
- **Detecciones** Número total de eventos detectados para el archivo con nombre. Los dispositivos individuales pueden desencadenar varios eventos de reglas de ASR.
- **Dispositivos** Número de dispositivos en los que se produjo la detección.

>:::image type="content" source="images/attack-surface-reduction-rules-report-exclusion-tab.png" alt-text="Muestra la pestaña Agregar exclusiones del informe de reglas de ASR" lightbox="images/attack-surface-reduction-rules-report-exclusion-tab.png":::

> [!IMPORTANT]
> La exclusión de archivos o carpetas puede reducir considerablemente la protección proporcionada por las reglas de ASR. Los archivos excluidos pueden ejecutarse y no se registrará ningún informe o evento.
> Si las reglas de ASR detectan archivos que cree que no deben detectarse, primero debe [usar el modo de auditoría para probar la regla](attack-surface-reduction-rules-deployment-test.md#step-1-test-asr-rules-using-audit).

Al seleccionar un archivo, se abre un **resumen & impacto esperado** y se presentan los siguientes tipos de información:

- **Archivos seleccionados**  Número de archivos seleccionados para la exclusión
- **(_número de) detecciones_**  Indica la reducción esperada en las detecciones después de agregar las exclusiones seleccionadas.  La reducción de las detecciones se representa gráficamente para **las detecciones y detecciones reales** **después de las exclusiones**.
- **(_número de_) dispositivos afectados** Indica la reducción esperada en los dispositivos que notifican las detecciones de las exclusiones seleccionadas.

La página Agregar exclusión tiene dos botones para las acciones que se pueden usar en los archivos detectados (después de la selección). Puede:

- **Agregue la exclusión** que abrirá la página de directiva de ASR de Microsoft Endpoint Manager (MEM). Para obtener más información, vea: [MEM](https://enable-attack-surface-reduction.md#mem) en "Habilitar métodos de configuración alternativos de reglas ASR".
- **Obtener rutas de exclusión** que descargarán rutas de acceso de archivo en formato csv

>:::image type="content" source="images/attack-surface-reduction-rules-report-main-add-exclusions-flyout.png" alt-text="Muestra el resumen de impacto del control flotante de la pestaña Agregar exclusiones del informe de reglas de ASR" lightbox="images/attack-surface-reduction-rules-report-main-add-exclusions-flyout.png":::

## <a name="see-also"></a>Vea también

- [Introducción a la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment.md)
- [Planear la implementación de reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-plan.md)
- [Probar las reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-test.md)
- [Habilitar reglas de la reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-implement.md)
- [Operacionar reglas de reducción de la superficie expuesta a ataques (ASR)](attack-surface-reduction-rules-deployment-operationalize.md)
- [Informe de reglas de ASR\) de reducción \(de superficie expuesta a ataques](attack-surface-reduction-rules-report.md)
- [Referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md)
