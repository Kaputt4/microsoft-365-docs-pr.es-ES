---
title: Habilitar el bloqueo a primera vista para detectar malware en segundos
description: Active la característica de bloqueo a primera vista para detectar y bloquear el malware en pocos segundos.
keywords: analizar, bloquear a primera vista, malware, primera vista, nube, defender, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ba0f2184ced21aea60b172d44936e3e2d36e5270
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274957"
---
# <a name="turn-on-block-at-first-sight"></a>Activar el bloqueo a primera vista

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

En este artículo se describe una característica de antivirus o antimalware conocida como "bloqueo a primera vista" y se describe cómo habilitar el bloqueo a primera vista para la organización. 

> [!TIP]
> Este artículo está destinado a administradores empresariales y profesionales de TI que administran la configuración de seguridad para organizaciones. Si no es un administrador empresarial o un profesional de TI, pero tiene preguntas sobre el bloqueo a primera vista, consulte [¿No es un administrador empresarial o un profesional de TI?](#not-an-enterprise-admin-or-it-pro).

## <a name="what-is-block-at-first-sight"></a>¿Qué es "bloqueo a primera vista"?

El bloqueo a primera vista es una característica de protección contra amenazas de protección de nueva generación que detecta nuevo malware y lo bloquea en pocos segundos. El bloqueo a primera vista se habilita cuando se habilitan determinadas opciones de configuración de seguridad. Entre estas opciones se incluyen:

- Protección entregada en la nube; 
- Un tiempo de espera de envío de ejemplo especificado (como 50 segundos); y 
- Un nivel de bloqueo de archivos alto. 

En la mayoría de las organizaciones empresariales, la configuración necesaria para habilitar el bloqueo a primera vista se configura con las implementaciones de Antivirus de Microsoft Defender. 

## <a name="how-it-works"></a>Cómo funciona

Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso pero no detectado, consulta nuestro back-end de protección de la nube. El back-end de la nube aplica heurística, aprendizaje automático y análisis automatizado del archivo para determinar si los archivos son malintencionados o no son una amenaza.

Antivirus de Microsoft Defender usa varias tecnologías de detección y prevención para ofrecer una protección inteligente, en tiempo real y precisa. 

![Lista de motores AV de Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Para más información, consulte este blog: [Conozca las tecnologías avanzadas en el centro la protección de última generación de Microsoft Defender para punto de conexión](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Algunas cosas que debe saber sobre el bloqueo a primera vista

- En Windows 10, versión 1803 y versiones posteriores, el bloqueo a primera vista puede bloquear los archivos ejecutables no portátiles (como JS, VBS o macros) y los archivos ejecutables.

- Bloqueo a primera vista usa solo el back-end de protección en la nube para archivos ejecutables y archivos ejecutables no portátiles que se descargan de Internet o que se originan desde la zona de Internet. Se comprueba un valor de hash del archivo .exe a través del back-end de la nube, para determinar si se trata de un archivo no detectado anteriormente.

- Si el back-end de la nube no consigue determinar, Antivirus de Microsoft Defender bloquea el archivo y carga una copia en la nube. La nube realiza más análisis para alcanzar una determinación antes de permitir que el archivo se ejecute o bloquearlo en todos las futuras apariciones, en función de si determina que el archivo es malintencionado o no es una amenaza.

- En muchos casos, este proceso puede reducir el tiempo de respuesta para el nuevo malware de horas a segundos.

- Puede [especificar durante cuánto tiempo debe impedirse la ejecución del archivo](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) mientras el servicio de protección basado en la nube analiza el archivo. Además, puede [personalizar el mensaje que aparece en los escritorios de los usuarios ](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)cuando se bloquea un archivo. Puede cambiar el nombre de la empresa, la información de contacto y la dirección URL de mensajes.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Activar el bloqueo a primera vista con Microsoft Intune

> [!TIP]
> Microsoft Intune ahora forma parte de Microsoft Endpoint Manager.

1. En el Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), vaya a **Dispositivos** > **Perfiles de configuración**.

2. Seleccione o cree un perfil con el tipo de perfil **Restricciones de dispositivo**.

3. En las **Opciones de configuración** del perfil Restricciones de dispositivo, establezca o confirme las opciones siguientes en **Antivirus de Microsoft Defender**:

   - **Protección proporcionada por la nube**: Habilitar
   - **Nivel de bloqueo de archivos**: Alto
   - **Extensión de tiempo para el análisis de archivos de la nube**: 50
   - **Avisar a los usuarios antes del envío de muestras**: Enviar todos los datos sin avisar

   ![Configuración de Intune](images/defender/intune-block-at-first-sight.png)

4. Guarde la configuración.

> [!TIP]
> - Si establece el nivel de bloqueo de archivos en **Alto**, se aplica un nivel de detección muy riguroso. En el caso poco probable de que el bloqueo de archivos cause una detección de falso positivo de archivos legítimos, el equipo de operaciones de seguridad puede [restaurar los archivos en cuarentena](./restore-quarantined-files-microsoft-defender-antivirus.md).
> - Para obtener más información sobre cómo configurar las restricciones de dispositivos de Antivirus de Microsoft Defender en Intune, consulte[ Configurar las opciones de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).
> - Para obtener una lista de las restricciones de los dispositivos de Antivirus de Microsoft Defender en Intune, consulte [Configuración de restricción de dispositivos para Windows 10 (y posteriores) en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Activar el bloqueo a primera vista con Microsoft Endpoint Manager

> [!TIP]
> Si está buscando Microsoft Endpoint Configuration Manager, ahora forma parte de Microsoft Endpoint Manager.

1. En Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), vaya a **Seguridad de punto de conexión** > **Antivirus**.

2. Seleccione una directiva existente o cree una directiva con el tipo de perfil **Antivirus de Microsoft Defender**.

3. Establezca o confirme las siguientes opciones de configuración:

   - **Activar la protección proporcionada en la nube**: Sí
   - **Nivel de protección proporcionada en la nube**: Alto
   - **Tiempo de espera extendido de la nube de Defender**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Configuración de bloqueo a primera vista en Endpoint Manager":::

4. Aplique el perfil del Antivirus de Microsoft Defender a un grupo, como **Todos los usuarios**, **Todos los dispositivos** o **Todos los usuarios y dispositivos**.

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Activar el bloqueo a primera vista con la directiva de grupo

> [!NOTE]
> Se recomienda usar Intune o Microsoft Endpoint Manager para activar el bloqueo a primera vista. 

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**. 

2. Con el **Editor de administración de directivas de grupo** vaya a **Configuración del equipo** > **Plantillas administrativas** > **Componentes de Windows** > **Antivirus de Microsoft Defender** > **MAPAS**. 

3. En la sección MAPAS, haga doble clic en **Configurar la característica "Bloquear a primera vista"**, establezca esta opción en **Habilitado** y seleccione **Aceptar**.

    > [!IMPORTANT]
    > Establecerla en **Preguntar siempre (0)** reducirá el estado de protección del dispositivo. Establecerla en **No enviar nunca (2)** significa que el bloqueo a primera vista no funcionará.

4. En la sección MAPAS, haga doble clic en **Enviar archivos de muestra cuando sea necesario realizar análisis adicionales** y establézcalo en **Habilitado**. En **Enviar archivos de muestra cuando sea necesario realizar análisis adicionales**, seleccione **Enviar todas las muestras** y seleccione **Aceptar**.

5. Vuelva a implementar el objeto de directiva de grupo en la red como lo haría normalmente.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Confirmar que el bloqueo a primera vista está habilitado en dispositivos de clientes individuales

Puede confirmar que el bloqueo a primera vista está habilitado en dispositivos cliente individuales con la aplicación de Seguridad de Windows. El bloqueo a primera vista se habilita automáticamente siempre y cuando las opciones **Protección basada en la nube** y **Envío de muestras automático** estén activadas.

1. Abra la aplicación Seguridad de Windows.

2. Seleccione **Protección antivirus y contra amenazas** y, luego, en **Configuración de antivirus y protección contra amenazas**, seleccione **Administrar la configuración**.

   ![Captura de pantalla de la etiqueta Protección contra virus y amenazas en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Confirme que las opciones **Protección basada en la nube** y **Envío de muestras automático** estén activadas.

> [!NOTE]
> - Si la configuración de requisitos previos se configura e implementa mediante la directiva de grupo, la configuración que se describe en esta sección aparecerá atenuada y su uso no estará disponible en los puntos de conexión individuales. 
> - Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows.

## <a name="validate-block-at-first-sight-is-working"></a>Validar que esté funcionando el bloqueo a primera vista

Para comprobar que la característica funciona, siga las instrucciones de la guía [Validar las conexiones entre la red y la nube](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).

## <a name="turn-off-block-at-first-sight"></a>Desactivar el bloqueo a primera vista

> [!CAUTION]
> Al desactivar el bloqueo a primera vista disminuirá el estado de protección de los dispositivos y de la red.

Puede optar por deshabilitar el bloqueo a primera vista si quiere conservar la configuración de requisitos previos sin usar la protección del bloqueo a primera vista. Puede desactivar temporalmente el bloqueo a primera vista para ver cómo afecta esta característica a su red. Sin embargo, no se recomienda deshabilitar la protección de bloqueo a primera vista de forma permanente.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Desactivar el bloqueo a primera vista con Microsoft Endpoint Manager

1. Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Vaya a **Seguridad de punto de conexión** > **Antivirus** y, después, seleccione la directiva de Antivirus de Microsoft Defender.

3. En **Administrar**, elija **Propiedades**.

4. Junto a **Opciones de configuración**, elija **Editar**.

5. Cambie una o varias de las opciones siguientes:

   - Establezca **Activar la protección proporcionada en la nube** en **No** o **Sin configurar**.
   - Establezca **Nivel de protección proporcionada en la nube** en **Sin configurar**.
   - Desactive la casilla de **Tiempo de espera extendido en segundos en la nube de Defender**.

6. Revise y guarde la configuración.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Desactivar el bloqueo a primera vista con la directiva de grupo

1. En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.

2. Con el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol en **Componentes de Windows** > **Antivirus de Windows Defender** > **MAPAS**.

4. Haz doble clic en **Configurar la característica 'Bloqueo a primera vista'** y establezca la opción en **Deshabilitado**.

    > [!NOTE]
    > Si deshabilita el bloqueo a primera vista, no se deshabilitarán ni modificarán las directivas de grupo de requisitos previos.

## <a name="not-an-enterprise-admin-or-it-pro"></a>¿No es un administrador empresarial o un profesional de TI?

Si no es un administrador empresarial o un profesional de TI, pero tiene preguntas sobre el bloqueo a primera vista, esta sección es para usted. El bloqueo a primera vista es una característica de protección contra amenazas que detecta y bloquea malware en pocos segundos. Aunque no existe una configuración específica denominada "Bloqueo a primera vista", la característica se habilita cuando se configuran opciones específicas en el dispositivo.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>Cómo administrar el bloqueo a primera vista para activarlo o desactivarlo en su propio dispositivo

Si tiene un dispositivo personal que no está administrado por una organización, puede que se pregunte cómo activar o desactivar el bloqueo a primera vista. Puede usar la aplicación de Seguridad de Windows para administrar el bloqueo a primera vista.

1. En el equipo con Windows 10, abra la aplicación de Seguridad de Windows.

2. Seleccione **Protección antivirus y contra amenazas**.

3. En **Configuración de antivirus y protección contra amenazas**, seleccione **Administrar la configuración**.

4. Realice uno de los pasos siguientes:

   - Para habilitar el bloqueo a primera vista, asegúrese de que **Protección proporcionada en la nube** y **Envío de muestras automático** están activados.

   - Para deshabilitar el bloqueo a primera vista, desactive la **Protección proporcionada en la nube** o **Envío de muestras automático**. <br/>
    
     > [!CAUTION]
     > Desactivar el bloque a primera vista disminuye el nivel de protección del dispositivo. No se recomienda deshabilitar permanentemente el bloqueo a primera vista. 


## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Manténgase protegido con Seguridad de Windows](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)