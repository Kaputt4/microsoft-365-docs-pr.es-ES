---
title: Habilitación y configuración de Microsoft Defender funcionalidades de protección antivirus
description: Habilitar y configurar Microsoft Defender características de protección en tiempo real del Antivirus, como la supervisión del comportamiento, la heurística y el aprendizaje automático
keywords: antivirus, protección en tiempo real, rtp, aprendizaje automático, supervisión del comportamiento, heurística
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: conceptual
ms.date: 10/22/2021
manager: dansimp
ms.custom: nextgen
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 667cb940c716e95922301dca18985f6378e472ac
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620423"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Habilitar y configurar la protección siempre activa del Antivirus de Windows Defender en la directiva de grupo

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

La protección always-on consta de protección en tiempo real, supervisión del comportamiento y heurística para identificar malware basado en actividades sospechosas y malintencionadas conocidas.

Estas actividades incluyen eventos, como procesos que realizan cambios inusuales en los archivos existentes, modificación o creación de claves del Registro de inicio automático y ubicaciones de inicio (también conocidas como puntos de extensibilidad de inicio automático o ASEP) y otros cambios en el sistema de archivos o la estructura de archivos.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Habilitar y configurar la protección always-on en समूह नीति

Puede usar **el Editor de समूह नीति local** para habilitar y configurar Microsoft Defender configuración de protección siempre activa del Antivirus.

Para habilitar y configurar la protección always-on:

1. Abra **el Editor de समूह नीति local**, como se indica a continuación:

    1. En el cuadro de búsqueda Windows 10 o Windows 11 barra de tareas, escriba **gpedit**.

    2. En **Mejor coincidencia**, seleccione **Editar directiva de grupo** para iniciar **el Editor de समूह नीति local**.
    
       :::image type="content" source="images/gpedit-search.png" alt-text="El resultado de búsqueda de la barra de tareas GPEdit en el panel de control" lightbox="images/gpedit-search.png":::

2. En el panel izquierdo del **Editor de समूह नीति local**, expanda el árbol a **Configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> de Windows **Microsoft Defender Antivirus**.

3. Configure la configuración de la directiva de servicio antimalware Microsoft Defender Antivirus.

   En el panel de detalles **Microsoft Defender Antivirus** de la derecha, haga doble clic en **Permitir que el servicio antimalware se inicie con prioridad normal** y establézcalo en **Habilitado**.

   A continuación, seleccione **Aceptar**.

4. Configure las opciones de directiva de protección en tiempo real de Microsoft Defender Antivirus, como se indica a continuación:

    1. En el panel de detalles **Microsoft Defender Antivirus**, haga doble clic en **Protección en tiempo real**. O bien, en el árbol **Microsoft Defender Antivirus** del panel izquierdo, seleccione **Protección en tiempo real**.

    2. En el panel Detalles de **protección en tiempo real** de la derecha, haga doble clic en la configuración de directiva como se especifica en [Configuración de directivas de protección en tiempo real](#real-time-protection-policy-settings) (más adelante en este artículo).

    3. Configure la configuración según corresponda y seleccione **Aceptar**.

    4. Repita los pasos anteriores para cada configuración de la tabla.

5. Configure la configuración de la directiva de examen Microsoft Defender Antivirus, como se indica a continuación:

    1. En el **árbol Microsoft Defender Antivirus** del panel izquierdo, seleccione **Examinar**.
    
   2. En el panel **Detalles del examen** de la derecha, haga doble clic **en Activar heurística** y establézcalo en **Habilitado**. 

   3. Seleccione **Aceptar**.

6. Cierre **el Editor de समूह नीति local**.

### <a name="real-time-protection-policy-settings"></a>Configuración de directivas de protección en tiempo real

|Setting|Configuración predeterminada|
|---|---|
|Activar la supervisión del comportamiento <p> El motor antivirus supervisará los procesos de archivos, los cambios de archivos y del Registro, y otros eventos en los puntos de conexión para detectar actividades malintencionadas sospechosas y conocidas.|Habilitado|
|Examinar todos los archivos y datos adjuntos descargados <p> Los archivos descargados y los datos adjuntos se examinan automáticamente. Este examen funciona además del Windows डिफेन्डर filtro SmartScreen, que examina los archivos antes y durante la descarga.|Habilitado|
|Supervisión de la actividad de archivos y programas en el equipo <p> El motor Microsoft Defender Antivirus toma nota de los cambios de archivo (escrituras de archivos, como movimientos, copias o modificaciones) y la actividad general del programa (programas que se abren o ejecutan y que hacen que se ejecuten otros programas).|Habilitado|
|Activar notificaciones de escritura de volumen sin procesar <p> La supervisión del comportamiento analizará la información sobre las escrituras de volúmenes sin procesar.|Habilitado|
|Activar el examen de procesos siempre que se habilite la protección en tiempo real <p> Puede habilitar de forma independiente el motor Microsoft Defender Antivirus para examinar los procesos en ejecución en busca de modificaciones o comportamientos sospechosos. Esto resulta útil si ha deshabilitado temporalmente la protección en tiempo real y quiere examinar automáticamente los procesos que se iniciaron mientras se deshabilitó.|Habilitado|
|Definir el tamaño máximo de los archivos descargados y los datos adjuntos que se van a examinar <p> Puede definir el tamaño en kilobytes.|Habilitado|
|Configuración de la invalidación de configuración local para activar la supervisión del comportamiento <p> Configure una invalidación local para la configuración de la supervisión del comportamiento. Esta configuración solo se puede establecer mediante समूह नीति. Si habilita esta configuración, la configuración de preferencias locales tendrá prioridad sobre समूह नीति. Si deshabilita o no establece esta configuración, समूह नीति tendrá prioridad sobre la configuración de preferencias local.|Habilitado|
|Configuración de la invalidación de configuración local para examinar todos los archivos y datos adjuntos descargados <p> Configure una invalidación local para la configuración del examen de todos los archivos y datos adjuntos descargados. Esta configuración solo se puede establecer mediante समूह नीति. Si habilita esta configuración, la configuración de preferencias locales tendrá prioridad sobre समूह नीति. Si deshabilita o no establece esta configuración, समूह नीति tendrá prioridad sobre la configuración de preferencias local.|Habilitado|
|Configuración de la invalidación de configuración local para supervisar la actividad de archivos y programas en el equipo <p> Configure una invalidación local para la configuración de la supervisión de la actividad de archivo y programa en el equipo. Esta configuración solo se puede establecer mediante समूह नीति. Si habilita esta configuración, la configuración de preferencias locales tendrá prioridad sobre समूह नीति. Si deshabilita o no establece esta configuración, समूह नीति tendrá prioridad sobre la configuración de preferencias local.|Habilitado|
|Configuración de la invalidación de configuración local para activar la protección en tiempo real <p> Configure una invalidación local para que la configuración active la protección en tiempo real. Esta configuración solo se puede establecer mediante समूह नीति. Si habilita esta configuración, la configuración de preferencias locales tendrá prioridad sobre समूह नीति. Si deshabilita o no establece esta configuración, समूह नीति tendrá prioridad sobre la configuración de preferencias local.|Habilitado|
|Configuración de la invalidación de configuración local para la supervisión de la actividad de archivo entrante y saliente <p> Configure una invalidación local para la configuración de la supervisión de la actividad de archivo entrante y saliente. Esta configuración solo se puede establecer mediante समूह नीति. Si habilita esta configuración, la configuración de preferencias locales tendrá prioridad sobre समूह नीति. Si deshabilita o no establece esta configuración, समूह नीति tendrá prioridad sobre la configuración de preferencias local.|Habilitado|
|Configuración de la supervisión de la actividad de archivos y programas entrantes y salientes <p> Especifique si la supervisión debe producirse en la dirección entrante, saliente, ambas o ninguna de ellas. Esta acción es relevante para las instalaciones de Windows Server en las que haya definido servidores específicos o roles de servidor que ven grandes cantidades de cambios de archivo en una sola dirección y desea mejorar el rendimiento de la red. Los puntos de conexión (y servidores) totalmente actualizados en una red verán poco impacto en el rendimiento, independientemente del número o la dirección de los cambios de archivo.|Habilitado (ambas direcciones)|

## <a name="disable-real-time-protection-in-group-policy"></a>Deshabilitar la protección en tiempo real en समूह नीति

> [!WARNING]
> Deshabilitar la protección en tiempo real reduce drásticamente la protección en los puntos de conexión y no se recomienda.

La principal funcionalidad de protección en tiempo real está habilitada de forma predeterminada, pero puede deshabilitarla mediante **el Editor de समूह नीति local**.

### <a name="to-disable-real-time-protection-in-group-policy"></a>Para deshabilitar la protección en tiempo real en la directiva de grupo

1. Abra **el Editor de समूह नीति local**.

   1. En el cuadro de búsqueda Windows 10 o Windows 11 barra de tareas, escriba **gpedit**.
   2. En **Mejor coincidencia**, seleccione **Editar directiva de grupo** para iniciar **el Editor de समूह नीति local**.

2. En el panel izquierdo del **Editor de समूह नीति local**, expanda el árbol a **Configuración** \> del equipo **Plantillas** \> administrativas **Componentes** \> de Windows **Microsoft Defender Antivirus Protección** \> en **tiempo real**.

3. En el panel Detalles **de protección en tiempo real** de la derecha, haga doble clic en **Desactivar protección en tiempo real**.

4. En la ventana **Desactivar la configuración de protección en tiempo real** , establezca la opción **en Habilitado**.
   
5. seleccione **Aceptar**.

6. Cierre **el Editor de समूह नीति local**.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Configurar la protección en tiempo real, heurística y de comportamiento](configure-protection-features-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
