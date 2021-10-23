---
title: Habilitar y configurar las Antivirus de Microsoft Defender de protección
description: Habilitar y configurar Antivirus de Microsoft Defender de protección en tiempo real, como la supervisión del comportamiento, la heurística y el aprendizaje automático
keywords: antivirus, protección en tiempo real, rtp, aprendizaje automático, supervisión del comportamiento, heurística
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.date: 10/18/2021
manager: dansimp
ms.custom: nextgen
ms.collection: M365-security-compliance
ms.openlocfilehash: 1861e15ce72bafdafa796463ff41163c338fc8bf
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555625"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>Habilitar y configurar la protección siempre activa del Antivirus de Windows Defender en la directiva de grupo


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

La protección siempre activa consiste en la protección en tiempo real, la supervisión del comportamiento y la heurística para identificar malware basado en actividades sospechosas y malintencionadas conocidas.

Estas actividades incluyen eventos, como procesos que hacen cambios inusuales en los archivos existentes, modificar o crear claves de registro de inicio automático y ubicaciones de inicio (también conocidas como puntos de extensibilidad de inicio automático o ASEP) y otros cambios en el sistema de archivos o la estructura de archivos.

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>Habilitar y configurar la protección siempre activa en la directiva de grupo

Puede usar el **Editor de directivas de** grupo local para habilitar y configurar Antivirus de Microsoft Defender de protección siempre activa.

Para habilitar y configurar la protección siempre activa:

1. Abra el Editor de directivas de grupo **local,** de la siguiente manera:

    1. En el Windows 10 o Windows cuadro de búsqueda de la barra de tareas 11, escriba **gpedit**.

    2. En **Coincidencia recomendada,** seleccione **Editar directiva de grupo** para iniciar el Editor de directivas de grupo **local.**
    
       ![Resultado de búsqueda de la barra de tareas GPEdit.](images/gpedit-search.png)

2. En el panel izquierdo del Editor de  directivas de grupo **local,** expanda el árbol a Configuración del equipo Plantillas administrativas \>  \> **Windows componentes** \> **Antivirus de Microsoft Defender**.

3. Configure la Antivirus de Microsoft Defender de la directiva de servicio antimalware, como se muestra a continuación:

   1. En el **Antivirus de Microsoft Defender** detalles de la derecha, haga doble clic en la configuración de directiva especificada en la tabla siguiente:

      <br/><br/>

      |Configuración|Configuración predeterminada|
      |---|---|
      |Permitir que el servicio antimalware se inicie con prioridad normal <p> Puede reducir la prioridad del motor Antivirus de Microsoft Defender motor. Reducir la prioridad puede ser útil en casos en los que quieras tener un proceso de inicio lo más delgado posible; sin embargo, la toma de esta acción podría afectar a la protección de puntos de conexión. Continúe con precaución.|Habilitado
      |Permitir que el servicio antimalware siga ejecutándose siempre <p> Si las actualizaciones de protección se han deshabilitado, puede Antivirus de Microsoft Defender para que se ejecuten. Deshabilitar las actualizaciones de protección reduce la protección de puntos de conexión.|Deshabilitado|

   2. Configure la configuración según corresponda y seleccione **Aceptar**.

   3. Repita los pasos anteriores para cada configuración de la tabla.

4. Configure la Antivirus de Microsoft Defender directiva de protección en tiempo real, como se muestra a continuación:

    1. En el **panel Antivirus de Microsoft Defender** detalles, haga doble clic en Protección en **tiempo real**. O bien, en el **Antivirus de Microsoft Defender** en el panel izquierdo, seleccione **Protección en tiempo real**.

    2. En el **panel Detalles de** protección en tiempo real a la derecha, haga doble clic en la configuración de directiva especificada en Configuración de directiva de protección en tiempo [real](#real-time-protection-policy-settings) (más adelante en este artículo).

    3. Configure la configuración según corresponda y seleccione **Aceptar**.

    4. Repita los pasos anteriores para cada configuración de la tabla.

5. Configure la configuración Antivirus de Microsoft Defender directiva de análisis, de la siguiente manera:

    1. En el **Antivirus de Microsoft Defender** en el panel izquierdo, seleccione **Examinar**.
    
       ![Antivirus de Microsoft Defender Opciones de examen.](images/gpedit-windows-defender-antivirus-scan.png)

      ![Antivirus de Microsoft Defender Opciones de examen](images/gpedit-windows-defender-antivirus-scan.png)

   2. En el **panel Detección** de detalles de la derecha, haga doble clic en la configuración de directiva especificada en la tabla siguiente:
      <br/><br/>

      |Configuración|Configuración predeterminada|
      |---|---|
      |Activar heurística <p> La protección heurística deshabilitará o bloqueará la actividad sospechosa inmediatamente antes de que se pida al Antivirus de Microsoft Defender que detecte la actividad.|Habilitado|


   3. Configure la configuración según corresponda y seleccione **Aceptar**.

6. Cierre **el Editor de directivas de grupo local**.

### <a name="real-time-protection-policy-settings"></a>Configuración de directiva de protección en tiempo real

|Configuración|Configuración predeterminada|
|---|---|
|Activar la supervisión del comportamiento <p> El motor antivirus supervisará los procesos de archivos, los cambios de archivos y del Registro y otros eventos en los puntos de conexión en busca de actividad malintencionada sospechosa y conocida.|Habilitado|
|Examinar todos los archivos y datos adjuntos descargados <p> Los archivos descargados y los datos adjuntos se examinan automáticamente. Este examen funciona además del filtro Windows Defender SmartScreen, que examina los archivos antes y durante la descarga.|Habilitado|
|Supervisar la actividad de archivos y programas en el equipo <p> El motor de Antivirus de Microsoft Defender toma nota de los cambios de archivos (escrituras de archivos, como movimientos, copias o modificaciones) y la actividad general del programa (programas que se abren o ejecutan y que hacen que se ejecuten otros programas).|Habilitado|
|Activar las notificaciones de escritura por volumen sin procesar <p> La supervisión del comportamiento analizará la información sobre las escrituras de volumen sin procesar.|Habilitado|
|Activar el examen de procesos siempre que esté habilitada la protección en tiempo real <p> Puede habilitar el motor de Antivirus de Microsoft Defender de forma independiente para examinar los procesos en ejecución en busca de modificaciones o comportamientos sospechosos. Esto resulta útil si ha deshabilitado temporalmente la protección en tiempo real y desea examinar automáticamente los procesos que se iniciaron mientras estaba deshabilitado.|Habilitado|
|Definir el tamaño máximo de los archivos y datos adjuntos descargados que se examinarán <p> Puede definir el tamaño en kilobytes.|Habilitado|
|Configurar la invalidación de configuración local para activar la supervisión del comportamiento <p> Configure una invalidación local para la configuración de la supervisión del comportamiento. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.|Habilitado|
|Configurar la invalidación de configuración local para examinar todos los archivos y datos adjuntos descargados <p> Configure una invalidación local para la configuración del examen de todos los archivos y datos adjuntos descargados. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.|Habilitado|
|Configurar la invalidación de configuración local para la actividad del programa y el archivo de supervisión en el equipo <p> Configure una invalidación local para la configuración de la supervisión de la actividad de archivos y programas en el equipo. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.|Habilitado|
|Configurar la invalidación de configuración local para activar la protección en tiempo real <p> Configure una invalidación local para que la configuración active la protección en tiempo real. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.|Habilitado|
|Configurar la invalidación de configuración local para la supervisión de la actividad de archivos entrantes y salientes <p> Configure una invalidación local para la configuración de la supervisión de la actividad de archivos entrantes y salientes. Esta configuración solo se puede establecer mediante la directiva de grupo. Si habilita esta configuración, la configuración de preferencia local tendrá prioridad sobre la directiva de grupo. Si deshabilita o no configura esta configuración, la directiva de grupo tendrá prioridad sobre la configuración de preferencia local.|Habilitado|
|Configurar la supervisión para la actividad del programa y los archivos entrantes y salientes <p> Especifique si la supervisión debe producirse en la dirección entrante, saliente, ambas o ninguna. Esta acción es relevante para las instalaciones de Windows Server en las que ha definido servidores específicos o roles de servidor que ven grandes cantidades de cambios de archivo en una sola dirección y desea mejorar el rendimiento de la red. Los puntos de conexión (y los servidores) totalmente actualizados en una red verán poco impacto en el rendimiento independientemente del número o la dirección de los cambios en los archivos.|Habilitado (ambas direcciones)|

## <a name="disable-real-time-protection-in-group-policy"></a>Deshabilitar la protección en tiempo real en la directiva de grupo

> [!WARNING]
> Deshabilitar la protección en tiempo real reduce drásticamente la protección en los puntos de conexión y no se recomienda.

La principal funcionalidad de protección en tiempo real está habilitada de forma predeterminada, pero puede deshabilitarla mediante el Editor de directivas **de grupo local**.

### <a name="to-disable-real-time-protection-in-group-policy"></a>Para deshabilitar la protección en tiempo real en la directiva de grupo

1. Abra **el Editor de directivas de grupo local**.

   1. En el Windows 10 o Windows cuadro de búsqueda de la barra de tareas 11, escriba **gpedit**.
   2. En **Coincidencia recomendada,** seleccione **Editar directiva de grupo** para iniciar el Editor de directivas de grupo **local.**

2. En el panel izquierdo del Editor de  directivas de grupo **local,** expanda el árbol a Configuración del equipo Plantillas administrativas Windows componentes Antivirus de Microsoft Defender \>  \>  \>  \> **protección en tiempo real**.

3. En el **panel detalles de protección** en tiempo real a la derecha, haga doble clic en Desactivar la protección en tiempo **real.**

   ![Desactivar la protección en tiempo real.](images/gpedit-turn-off-real-time-protection.png)

4. En la ventana Desactivar la configuración de protección en tiempo **real,** establezca la opción en **Habilitado**.

   ![Desactivar la protección en tiempo real habilitada.](images/gpedit-turn-off-real-time-protection-enabled.png)
   
5. seleccione **Aceptar**.

6. Cierre **el Editor de directivas de grupo local**.

## <a name="see-also"></a>Vea también

- [Configurar la protección en tiempo real, heurística y de comportamiento](configure-protection-features-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
