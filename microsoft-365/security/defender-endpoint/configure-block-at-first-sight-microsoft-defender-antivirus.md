---
title: Habilitar bloque a primera vista para detectar malware en segundos
description: Activa la característica de bloqueo a primera vista para detectar y bloquear malware en cuestión de segundos.
keywords: scan, BAFS, malware, first seen, first sight, cloud, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765760"
---
# <a name="turn-on-block-at-first-sight"></a>Activar el bloque a primera vista

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Bloquear a primera vista proporciona una forma de detectar y bloquear nuevo malware en segundos. Esta protección está habilitada de forma predeterminada cuando se habilitan determinadas opciones de configuración de requisitos previos. Estas opciones incluyen protección entregada en la nube, un tiempo de espera de envío de ejemplo especificado (como 50 segundos) y un nivel de bloqueo de archivos alto. En la mayoría de las organizaciones empresariales, esta configuración está habilitada de forma predeterminada con las implementaciones de Antivirus de Microsoft Defender. 

Puede especificar [cuánto tiempo se](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) debe impedir que un archivo se ejecute mientras el servicio de protección basado en la nube analiza el archivo. Además, puede personalizar [el mensaje que se muestra en los escritorios de los](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) usuarios cuando se bloquea un archivo. Puede cambiar el nombre de la empresa, la información de contacto y la dirección URL del mensaje.

>[!TIP]
>Visite el sitio web de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que las características funcionan y ver cómo funcionan.

## <a name="how-it-works"></a>Cómo funciona

Cuando Antivirus de Microsoft Defender encuentra un archivo sospechoso pero no detectado, consulta nuestro back-end de protección en la nube. El back-end en la nube aplica heurística, aprendizaje automático y análisis automatizado del archivo para determinar si los archivos son malintencionados o no son una amenaza.

Microsoft Defender Antivirus usa varias tecnologías de detección y prevención para ofrecer una protección precisa, inteligente y en tiempo real. Para obtener más información, vea este blog: Conozca las tecnologías avanzadas en el núcleo de Microsoft Defender para la [protección de última generación de Endpoint](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).
![Lista de motores antivirus de Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

En Windows 10, versión 1803 o posterior, bloquear a primera vista puede bloquear archivos ejecutables no portátiles (como JS, VBS o macros), así como archivos ejecutables.

Bloquear a primera vista solo usa el back-end de protección en la nube para archivos ejecutables y archivos ejecutables no portátiles que se descargan de Internet o que se originan en la zona de Internet. Un valor hash del archivo .exe se comprueba a través del back-end de la nube para determinar si el archivo es un archivo no detectado anteriormente.

Si el back-end de la nube no puede tomar una determinación, Antivirus de Microsoft Defender bloquea el archivo y carga una copia en la nube. La nube realiza análisis adicionales para llegar a una determinación antes de que permita que el archivo se ejecute o lo bloquee en todos los futuros encuentros, en función de si determina que el archivo es malintencionado o seguro.

En muchos casos, este proceso puede reducir el tiempo de respuesta del nuevo malware de horas a segundos.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Activar el bloque a primera vista con Microsoft Intune

> [!TIP]
> Microsoft Intune ahora forma parte de Microsoft Endpoint Manager.

1. En el Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), vaya a **Perfiles de** configuración de  >  **dispositivos**.

2. Seleccione o cree un perfil con el **tipo de perfil Restricciones de** dispositivo.

3. En configuración **para** el perfil restricciones de dispositivos, establezca o confirme la siguiente configuración en **Antivirus de Microsoft Defender**:

   - **Protección entregada en la nube:** habilitada
   - **Nivel de bloqueo de archivos:** alto
   - **Extensión de tiempo para el examen de archivos por la nube:** 50
   - **Preguntar a los usuarios antes del envío de** ejemplo: enviar todos los datos sin preguntar

   ![Configuración de Intune](images/defender/intune-block-at-first-sight.png)

4. Guarda la configuración.

> [!TIP]
> - Al establecer el nivel de bloqueo de archivos en **High** se aplica un nivel de detección fuerte. En el improbable caso de que el bloqueo de archivos cause una detección de falsos positivos de archivos legítimos, puede [restaurar archivos en cuarentena.](./restore-quarantined-files-microsoft-defender-antivirus.md)
> - Para obtener más información acerca de cómo configurar las restricciones de dispositivos antivirus de Microsoft Defender en Intune, consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).
> - Para obtener una lista de las restricciones de dispositivos antivirus de Microsoft Defender en Intune, consulta Restricción de dispositivos [para Windows 10 (y](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)versiones más recientes) en Intune .

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Activar el bloque a primera vista con Microsoft Endpoint Manager

> [!TIP]
> Si está buscando Microsoft Endpoint Configuration Manager, ahora forma parte de Microsoft Endpoint Manager.

1. En Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), vaya a Endpoint **security**  >  **Antivirus**.

2. Seleccione una directiva existente o cree una nueva con el tipo de perfil antivirus de **Microsoft Defender.**

3. Establezca o confirme las siguientes opciones de configuración:

   - **Activar la protección entregada en la nube:** Sí
   - **Nivel de protección entregado en la nube:** alto
   - **Tiempo de espera extendido de la nube de Defender en segundos:** 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Bloquear la configuración a primera vista en Endpoint Manager":::

4. Aplica el perfil antivirus de Microsoft Defender a un grupo, como Todos los **usuarios,** Todos los dispositivos **o** **Todos los usuarios y dispositivos.**

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Activar el bloque a primera vista con la directiva de grupo

> [!NOTE]
> Se recomienda usar Intune o Microsoft Endpoint Manager para activar el bloque a primera vista. 

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**. 

2. Con el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo Plantillas   >  **administrativas** Componentes  >  **de Windows**  >  **Microsoft Defender Antivirus**  >  **MAPS**. 

3. En la sección MAPAS, haga doble clic en Configurar la característica **"Bloquear** a primera vista" y estadúrela en **Habilitado** y, a continuación, **seleccione Aceptar**.

    > [!IMPORTANT]
    > Si se **establece en Preguntar siempre (0),** se disminuirá el estado de protección del dispositivo. Establecer en **Nunca enviar (2)** significa que el bloqueo a primera vista no funcionará.

4. En la sección MAPAS, haga doble clic en **Enviar** ejemplos de archivos cuando sea necesario realizar más análisis y establóquelo en **Habilitado**. En **Enviar ejemplos de archivos cuando sea necesario** realizar un análisis adicional, seleccione Enviar todas **las** muestras y, a continuación, haga clic en **Aceptar**.

5. Si ha cambiado alguna configuración, vuelva a implementar el objeto de directiva de grupo en toda la red para asegurarse de que se tratan todos los puntos de conexión.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a>Confirmar que el bloque a primera vista está habilitado en clientes individuales

Puedes confirmar que el bloqueo a primera vista está habilitado en clientes individuales mediante la configuración de seguridad de Windows.

El bloqueo a primera vista se  habilita automáticamente siempre que la protección entregada en la nube y el **envío** automático de muestra estén activados.

1. Abre la aplicación Seguridad de Windows.

2. Seleccione **Protección contra & virus** y, a continuación, en Configuración de protección contra & **virus,** seleccione **Administrar configuración**.

   ![Captura de pantalla de la etiqueta & de protección contra amenazas de virus en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Confirme que **la protección entregada en la nube** y el envío automático de **muestras** están activados.

> [!NOTE]
> - Si la configuración de requisitos previos se configura e implementa mediante la directiva de grupo, la configuración descrita en esta sección será grised-out y no estará disponible para su uso en puntos de conexión individuales. 
> - Los cambios realizados a través de un objeto de directiva de grupo deben implementarse primero en puntos de conexión individuales antes de que la configuración se actualice en Configuración de Windows.

## <a name="validate-block-at-first-sight-is-working"></a>Validar bloque a primera vista funciona

Para validar que la característica funciona, siga las instrucciones de [Validar conexiones entre la red y la nube.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)

## <a name="turn-off-block-at-first-sight"></a>Desactivar el bloque a primera vista

> [!CAUTION]
> Desactivar el bloque a primera vista disminuirá el estado de protección de los dispositivos y la red.

Es posible que elija deshabilitar el bloqueo a primera vista si desea conservar la configuración de requisitos previos sin usar realmente la protección de bloqueo a primera vista. Puedes desactivar temporalmente el bloqueo a primera vista si tienes problemas de latencia o quieres probar el impacto de la característica en la red. Sin embargo, no recomendamos deshabilitar el bloqueo a primera vista de forma permanente.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Desactivar el bloque a primera vista con Microsoft Endpoint Manager

1. Vaya al Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.

2. Vaya a **Endpoint security**  >  **Antivirus** y, a continuación, seleccione la directiva antivirus de Microsoft Defender.

3. En **Administrar**, elija **Propiedades**.

4. Junto a **Configuración,** elija **Editar**.

5. Cambie una o varias de las opciones siguientes:

   - Establezca **Activar la protección entregada en la nube** en **No** o No **configurado**.
   - Establezca **el nivel de protección entregado en la nube** en No **configurado.**
   - Desactive el **cuadro Tiempo de espera extendido de Defender Cloud en** segundos.

6. Revise y guarde la configuración.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Desactivar el bloque a primera vista con la directiva de grupo

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, haga clic en **Editar**.

2. Con el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expande el árbol a través **de componentes de Windows** Microsoft Defender  >  **Antivirus**  >  **MAPS**.

4. Haga doble clic **en Configurar la característica "Bloquear a primera vista"** y establezca la opción en **Deshabilitado**.

    > [!NOTE]
    > Deshabilitar el bloque a primera vista no deshabilita ni modifica las directivas de grupo de requisitos previos.

## <a name="see-also"></a>Vea también

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Habilitar la protección de entrega en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)