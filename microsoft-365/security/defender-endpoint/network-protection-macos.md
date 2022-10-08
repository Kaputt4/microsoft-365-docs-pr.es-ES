---
title: Uso de la protección de red para evitar conexiones macOS a sitios incorrectos
description: Proteja la red evitando que los usuarios de macOS accedan a direcciones de red malintencionadas y sospechosas conocidas.
keywords: Protección de red, vulnerabilidades de seguridad de MacOS, sitio web malintencionado, ip, dominio, dominios, comando y control, SmartScreen, notificación del sistema
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde
manager: dansimp
ms.custom: asr
ms.subservice: mde
ms.topic: overview
ms.collection:
- m365-security
- tier2
ms.date: ''
search.appverid: met150
ms.openlocfilehash: 3617ae81204d6c2e244d58868fad6fe7d315f29e
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68229094"
---
# <a name="network-protection-for-macos"></a>Protección de red para macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Microsoft 365 Defender para el plan de punto de conexión 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Microsoft 365 Defender para el plan de punto de conexión 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

## <a name="overview"></a>Información general

Microsoft lleva la funcionalidad de protección de red a macOS (mín. macOS 11).

La protección de red de Microsoft ayuda a reducir la superficie expuesta a ataques de los dispositivos frente a eventos basados en Internet. Impide que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar:

- estafas de phishing
- Hazañas
- otro contenido malintencionado en Internet

La protección de red amplía el ámbito de Microsoft 365 Defender [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview.md) para bloquear todo el tráfico HTTP saliente que intenta conectarse a orígenes de baja reputación. Los bloques del tráfico HTTP saliente se basan en el dominio o el nombre de host.

## <a name="new-and-updated-capabilities"></a>Funcionalidades nuevas y actualizadas

- Puede ejecutar la VPN corporativa en tándem o "en paralelo" con la protección de red. Actualmente, no se identifica ningún conflicto de VPN. Si experimenta conflictos, puede proporcionar comentarios a través del canal de comentarios que aparece en la parte inferior de esta página.
  - El filtrado de contenido web es compatible con la protección de red para macOS.  
  - Si la protección de red está configurada y activa en el dispositivo, las directivas de filtrado de contenido web (WCF) creadas en el portal de MDEP se respetan en los exploradores, incluido Chromium Microsoft Edge para macOS. Actualmente, el filtrado de contenido web en Microsoft Edge en Mac requiere protección de red; otras características de E5, como Microsoft Defender para aplicaciones en la nube o indicadores personalizados, actualmente también requieren protección de red.

### <a name="known-issues"></a>Problemas conocidos

- La experiencia de usuario de bloqueo o advertencia no es personalizable y puede requerir otros cambios de apariencia y sensación.
  - Se recopilan comentarios de los clientes para impulsar más mejoras de diseño

### <a name="important-notes"></a>Notas importantes

- No se recomienda controlar la protección de red de preferencias del sistema mediante el botón Desconectar. En su lugar, use la herramienta de línea de comandos mdatp o JAMF/Intune para controlar la protección de red para macOS.
- Para evaluar la eficacia de la protección contra amenazas web de macOS, se recomienda probarlo en exploradores distintos de Microsoft Edge para macOS (por ejemplo, Safari). Microsoft Edge para macOS tiene protección contra amenazas web integrada que está habilitada independientemente de si la característica de protección de red Mac que esté evaluando está activada o no.

> [!NOTE]
>
> Microsoft Edge para macOS no admite actualmente el filtrado de contenido web, indicadores personalizados u otras características empresariales. Sin embargo, la protección de red proporcionará esta protección a Microsoft Edge para macOS, así como si la protección de red está habilitada.

## <a name="prerequisites"></a>Requisitos previos

- Licencias: Microsoft 365 Defender para el inquilino del punto de conexión (puede ser de prueba)
- Máquinas incorporadas:
  - Versión mínima de macOS: 11
  - Versión del producto 101.78.13 o posterior
  - El dispositivo debe estar en el canal de actualización de Microsoft AutoUpdate insiderSlow (versión preliminar) o InsiderFast (beta). Puede comprobar el canal de actualización mediante el siguiente comando:

```bash
mdatp health --field release_ring 
```

Si el dispositivo aún no está en el canal de actualización InsiderSlow(Preview), ejecute el siguiente comando desde terminal. La actualización del canal surte efecto la próxima vez que se inicie el producto (cuando se instale la siguiente actualización del producto o cuando se reinicie el dispositivo).

```bash
defaults write com.microsoft.autoupdate2 ChannelName -string InsiderSlow
```

Como alternativa, si se encuentra en un entorno administrado (JAMF o Intune), puede configurar el grupo de dispositivos de forma remota. Para obtener más información, vea [Establecer preferencias para Microsoft 365 Defender para punto de conexión en macOS](mac-preferences.md).

## <a name="deployment-instructions"></a>Instrucciones de implementación

### <a name="microsoft-365-defender-for-endpoint"></a>Microsoft 365 Defender para punto de conexión

Después de configurar el dispositivo para que esté en el canal de actualización InsiderSlow(preview), instale la versión más reciente del producto a través de Microsoft AutoUpdate. Para abrir Microsoft AutoUpdate, ejecute el siguiente comando desde terminal:

```bash
open /Library/Application\ Support/Microsoft/MAU2.0/Microsoft\ AutoUpdate.app
```

Configure el producto con la información de su organización siguiendo las instrucciones de nuestra documentación pública.  

La protección de red está deshabilitada de forma predeterminada, pero se puede configurar para ejecutarse en uno de los siguientes modos (también denominados niveles de cumplimiento):

- **Auditoría**: útil para asegurarse de que no afecta a las aplicaciones de línea de negocio ni para hacerse una idea de la frecuencia con la que se producen los bloques
- **Bloquear**: la protección de red impide la conexión a sitios web malintencionados
- **Deshabilitado**: todos los componentes asociados a la protección de red están deshabilitados

Puede implementar esta característica de una de las siguientes maneras: manualmente, a través de JAMF o a través de Intune. En las secciones siguientes se describe cada uno de estos métodos en detalle.

#### <a name="manual-deployment"></a>Implementación manual

Para configurar el nivel de cumplimiento, ejecute el siguiente comando desde terminal:

```bash
mdatp config network-protection enforcement-level --value [enforcement-level]
```

Por ejemplo, para configurar la protección de red para que se ejecute en modo de bloqueo, ejecute el siguiente comando:

```bash
mdatp config network-protection enforcement-level --value block
```

Para confirmar que la protección de red se ha iniciado correctamente, ejecute el siguiente comando desde el terminal y compruebe que imprime "iniciado":

```bash
mdatp health --field network_protection_status
```

#### <a name="jamf-deployment"></a>Implementación de JAMF

Una implementación de JAMF correcta requiere un perfil de configuración para establecer el nivel de cumplimiento de la protección de red.  
Después de crear este perfil de configuración, asígnelo a los dispositivos en los que desea habilitar la protección de red.

##### <a name="configure-the-enforcement-level"></a>Configuración del nivel de cumplimiento

Nota: Si ya ha configurado Microsoft 365 Defender para punto de conexión en Mac mediante las instrucciones que se enumeran aquí, actualice el archivo plist que implementó anteriormente con el contenido que se muestra a continuación y vuelva a implementarlo desde JAMF.

1. En **Perfiles de configuración de**  **equipos** > , seleccione  **Opciones** > **Aplicaciones & Configuración personalizada**
2. Seleccione **Cargar archivo** (archivo PLIST)
3. Establecer dominio de preferencia en _com.microsoft.wdav_
4. Carga del siguiente archivo plist

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>networkProtection</key> 
    <dict> 
        <key>enforcementLevel</key> 
        <string>block</string> 
    </dict> 
</dict> 
</plist> 
```

#### <a name="intune-deployment"></a>Implementación de Intune

Una implementación correcta Intune requiere un perfil de configuración para establecer el nivel de cumplimiento de la protección de red.  
Después de crear este perfil de configuración, asígnelo a los dispositivos en los que desea habilitar la protección de red.

##### <a name="configure-the-enforcement-level-using-intune"></a>Configuración del nivel de cumplimiento mediante Intune

> [!NOTE]
> Si ya ha configurado Microsoft Defender para punto de conexión en Mac con las instrucciones que se enumeran aquí, actualice el archivo plist que implementó anteriormente con el contenido que se muestra a continuación y vuelva a implementarlo desde Intune.

1. Abra **Administrar** > **configuración del dispositivo**. Seleccione **Administrar** > **perfiles** > **Crear perfil**.
2. Especifique un nombre para el perfil. Cambie **Platform=macOS** a **Profile type=Custom**. Seleccione **Configurar**.
3. Guarde la siguiente carga como _com.microsoft.wdav.xml_

```xml
<?xml version="1.0" encoding="utf-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1"> 
    <dict> 
        <key>PayloadUUID</key> 
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string> 
        <key>PayloadType</key> 
        <string>Configuration</string> 
        <key>PayloadOrganization</key> 
        <string>Microsoft</string> 
        <key>PayloadIdentifier</key> 
        <string>com.microsoft.wdav</string> 
        <key>PayloadDisplayName</key> 
        <string>Microsoft Defender ATP settings</string> 
        <key>PayloadDescription</key> 
        <string>Microsoft Defender ATP configuration settings</string> 
        <key>PayloadVersion</key> 
        <integer>1</integer> 
        <key>PayloadEnabled</key> 
        <true/> 
        <key>PayloadRemovalDisallowed</key> 
        <true/> 
        <key>PayloadScope</key> 
        <string>System</string> 
        <key>PayloadContent</key> 
        <array> 
            <dict> 
                <key>PayloadUUID</key> 
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string> 
                <key>PayloadType</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadOrganization</key> 
                <string>Microsoft</string> 
                <key>PayloadIdentifier</key> 
                <string>com.microsoft.wdav</string> 
                <key>PayloadDisplayName</key> 
                <string>Microsoft Defender ATP configuration settings</string> 
                <key>PayloadDescription</key> 
                <string/> 
                <key>PayloadVersion</key> 
                <integer>1</integer> 
                <key>PayloadEnabled</key> 
                <true/> 
                <key>networkProtection</key> 
                <dict> 
                    <key>enforcementLevel</key> 
                    <string>block</string> 
                </dict> 
            </dict> 
        </array> 
    </dict> 
</plist>
```

4. Compruebe que el archivo anterior se copió correctamente. Desde el terminal, ejecute el siguiente comando y compruebe que la salida es Correcta:

```bash
plutil -lint com.microsoft.wdav.xml
```

5. Escriba _com.microsoft.wdav_ como nombre del perfil de configuración personalizado.
6. Abra el perfil de configuración y cargue el archivo com.microsoft.wdav.xml. (Este archivo se creó en el paso 3).
7. Seleccione **Aceptar.**
8. Seleccione **Administrar** > **asignaciones**. En la pestaña **Incluir** , seleccione los dispositivos para los que desea habilitar la protección de red.

## <a name="how-to-explore-the-features"></a>Cómo explorar las características

1. Obtenga información sobre cómo [proteger su organización frente a amenazas web](web-threat-protection.md) mediante la protección contra amenazas web.
   - La protección contra amenazas web forma parte de la protección web en Microsoft Defender para punto de conexión. Usa la protección de red para proteger los dispositivos frente a amenazas web.
2. Ejecute el flujo [Indicadores personalizados de compromiso](indicator-ip-domain.md) para obtener bloques en el tipo indicador personalizado.
3. Explorar el [filtrado de contenido web](web-content-filtering.md).
   > [!NOTE]
   > Si va a quitar una directiva o cambiar grupos de dispositivos al mismo tiempo, esto podría provocar un retraso en la implementación de directivas.
   > Sugerencia profesional: puede implementar una directiva sin seleccionar ninguna categoría en un grupo de dispositivos. Esta acción creará una directiva de solo auditoría para ayudarle a comprender el comportamiento del usuario antes de crear una directiva de bloque.
   >
   > La creación de grupos de dispositivos se admite en El plan 1 y el plan 2 de Defender para punto de conexión.  

4. [Integre Microsoft Defender para punto de conexión con Defender for Cloud Apps](/defender-cloud-apps/mde-integration) y los dispositivos macOS habilitados para la protección de red tendrán funcionalidades de cumplimiento de directivas de punto de conexión.
   > [!NOTE]
   > La detección y otras características no se admiten actualmente en estas plataformas.

## <a name="scenarios"></a>Escenarios

Los siguientes escenarios se admiten durante la versión preliminar pública:

### <a name="web-threat-protection"></a>Protección contra amenazas web

La protección contra amenazas web forma parte de la protección web en Microsoft 365 Defender para punto de conexión. Usa la protección de red para proteger los dispositivos frente a amenazas web. Mediante la integración con Microsoft Edge para macOS y exploradores populares de terceros como Chrome y Firefox, la protección contra amenazas web detiene las amenazas web sin un proxy web. La protección contra amenazas web puede proteger los dispositivos mientras están en el entorno local o fuera de ellos. La protección contra amenazas web detiene el acceso a los siguientes tipos de sitios:

- sitios de phishing
- vectores de malware
- sitios de vulnerabilidades de seguridad
- sitios que no son de confianza o de baja reputación
- sitios que ha bloqueado en la lista de indicadores personalizados

:::image type="content" source="images/network-protection-reports-web-protection.png" alt-text="Web Protection notifica detecciones de amenazas web." lightbox="images/network-protection-reports-web-protection.png":::

Para obtener más información, consulte [Protección de su organización frente a amenazas web](web-threat-protection.md).

### <a name="custom-indicators-of-compromise"></a>Indicadores personalizados de peligro  

El indicador de coincidencia de peligro (IoC) es una característica esencial en todas las soluciones de Endpoint Protection. Esta funcionalidad ofrece a SecOps la capacidad de establecer una lista de indicadores para la detección y el bloqueo (prevención y respuesta).

Cree indicadores que definan la detección, prevención y exclusión de entidades. Puede definir la acción que se va a realizar, así como la duración de la aplicación de la acción y el ámbito del grupo de dispositivos al que se va a aplicar.

Los orígenes admitidos actualmente son el motor de detección en la nube de Defender para punto de conexión, el motor de investigación y corrección automatizado y el motor de prevención de puntos de conexión (Microsoft Defender Antivirus).

:::image type="content" source="images/network-protection-add-url-domain-indicator.png" alt-text="Muestra el indicador de agregar dirección URL o dominio de protección de red." lightbox="images/network-protection-add-url-domain-indicator.png":::

Para obtener más información, vea: [Crear indicadores para direcciones IP y direcciones URL/dominios](indicator-ip-domain.md).

### <a name="web-content-filtering"></a>Filtrado de contenido web

El filtrado de contenido web forma parte de las funcionalidades de [protección web](web-protection-overview.md) en Microsoft Defender para punto de conexión y Microsoft Defender para Empresas. El filtrado de contenido web permite a su organización realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido. Muchos de estos sitios web (incluso si no son malintencionados) pueden ser problemáticos debido a las regulaciones de cumplimiento, el uso del ancho de banda u otros problemas.

Configure directivas en los grupos de dispositivos para bloquear determinadas categorías. El bloqueo de una categoría impide que los usuarios de grupos de dispositivos especificados accedan a las direcciones URL asociadas a la categoría. Para cualquier categoría que no esté bloqueada, las direcciones URL se auditan automáticamente. Los usuarios pueden acceder a las direcciones URL sin interrupciones y recopilará estadísticas de acceso para ayudar a crear una decisión de directiva más personalizada. Los usuarios verán una notificación de bloque si un elemento de la página que están viendo realiza llamadas a un recurso bloqueado.

El filtrado de contenido web está disponible en los principales exploradores web, con bloques realizados por Network Protection (Safari, Chrome, Firefox, Brave y Opera). Para obtener más información sobre la compatibilidad con exploradores, consulte [Requisitos previos](#prerequisites).

:::image type="content" source="images/network-protection-wcf-add-policy.png" alt-text="Muestra la directiva de adición de filtrado de contenido web de protección de red." lightbox="images/network-protection-wcf-add-policy.png":::

Para obtener más información sobre los informes, vea [Filtrado de contenido web](web-content-filtering.md).

### <a name="microsoft-defender-for-cloud-applications"></a>Microsoft Defender para aplicaciones en la nube

El Microsoft Defender para aplicaciones en la nube o catálogo de aplicaciones en la nube identifica las aplicaciones que desea que se advierta a los usuarios finales al acceder con Microsoft 365 Defender para punto de conexión y las marque como _Supervisadas_. Los dominios enumerados en aplicaciones supervisadas se sincronizarán más adelante con Microsoft 365 Defender para punto de conexión:

:::image type="content" source="images/network-protection-macos-mcas-monitored-apps.png" alt-text="Muestra las aplicaciones supervisadas de protección de red.":::

En un plazo de entre 10 y 15 minutos, estos dominios se mostrarán en Microsoft 365 Defender para Endpoint Security Center en Indicadores > direcciones URL o dominios con Action=Warn. Dentro del acuerdo de nivel de servicio de cumplimiento (consulte los detalles al final de este artículo), los usuarios finales recibirán mensajes de advertencia al intentar acceder a estos dominios:

:::image type="content" source="images/network-protection-macos-indicators-urls-domains-warn.png" alt-text="Muestra los indicadores de protección de red para la advertencia de direcciones URL o dominios.":::

Cuando el usuario final intente acceder a los dominios supervisados, se le advertirá Microsoft 365 Defender para el punto de conexión.

- El usuario obtendrá una experiencia de bloque sin formato acompañada del siguiente mensaje del sistema, que mostrará el sistema operativo, incluido el nombre de la aplicación bloqueada (por ejemplo, Blogger.com).

  :::image type="content" source="images/network-protection-macos-content-blocked.png" alt-text="Muestra el contenido de protección de red del usuario final bloqueado notificación del sistema.":::

Si el usuario final encuentra un _bloque_, el usuario tendrá dos posibles resoluciones:

#### <a name="user-bypass"></a>Omisión de usuario

- **Para la experiencia del mensaje del sistema**: presione el botón Desbloquear. Al volver a cargar la página web, el usuario podrá continuar y usar la aplicación en la nube. (Esta acción es aplicable durante las próximas 24 horas, después de las cuales el usuario tendrá que desbloquear una vez más)

#### <a name="user-education"></a>Educación del usuario

- **Para la experiencia del mensaje del sistema**: presione el propio mensaje del sistema. El usuario final se redirigirá a una dirección URL de redireccionamiento personalizada establecida globalmente en Microsoft Defender para aplicaciones en la nube (más información en la parte inferior de esta página)

> [!NOTE]
> Omisións de seguimiento por aplicación**: puede realizar un seguimiento de cuántos usuarios han omitido la advertencia en la página _Aplicación_ de Microsoft Defender para aplicaciones en la nube.

  :::image type="content" source="images/network-protection-macos-mcas-cloud-app-security.png" alt-text="Muestra información general sobre la seguridad de aplicaciones en la nube de protección de red.":::

## <a name="appendix"></a>Apéndice

### <a name="end-user-education-center-sharepoint-site-template"></a>Plantilla de sitio de SharePoint del Centro de educación del usuario final

Para muchas organizaciones, es importante tomar los controles en la nube proporcionados por Microsoft Defender para Aplicaciones en la nube y no solo establecer limitaciones en los usuarios finales cuando sea necesario, sino también educarlos y entrenarlos sobre:

- el incidente específico
- por qué ha sucedido
- cuál es el pensamiento detrás de esta decisión
- cómo se pueden mitigar los sitios de bloque

Al enfrentarse a un comportamiento inesperado, la confusión de los usuarios puede reducirse proporcionándoles toda la información posible, no solo para explicar lo que ha sucedido, sino también para educarlos para que sean más conscientes la próxima vez que elijan una aplicación en la nube para completar su trabajo. Por ejemplo, esta información puede incluir:

- Directivas y directrices de seguridad y cumplimiento de la organización para el uso de Internet y la nube
- Aplicaciones en la nube aprobadas o recomendadas para su uso
- Aplicaciones en la nube restringidas o bloqueadas para su uso

Para esta página, se recomienda que su organización use un sitio de SharePoint básico.  

### <a name="important-things-to-know"></a>Cosas importantes que debe saber

1. Los dominios de aplicación pueden tardar hasta dos horas (normalmente menos) en propagarse y actualizarse en los dispositivos de punto de conexión, una vez marcados como _Supervisados_.  
2. De forma predeterminada, se realizará una acción para todas las aplicaciones y dominios marcados como Supervisados en Microsoft Defender portal de aplicaciones en la nube para todos los puntos de conexión incorporados en la organización.  
3. Las direcciones URL completas no se admiten actualmente y no se enviarán desde Microsoft Defender para aplicaciones en la nube a Microsoft 365 Defender para punto de conexión, si las direcciones URL completas aparecen en Microsoft Defender  para las aplicaciones supervisadas de Aplicaciones en la nube, por lo tanto, no se advertirá al usuario en caso de intento de acceso (por ejemplo, no se admite google.com/drive, mientras que se admite drive.google.com).  

¿No hay ninguna notificación del usuario final en exploradores de terceros? Comprobación de la configuración del mensaje del sistema

## <a name="see-also"></a>Vea también

- [Microsoft 365 Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft 365 Defender para la integración de puntos de conexión con Microsoft Microsoft 365 Defender for Cloud Applications](/defender-cloud-apps/mde-integration)
- [Conozca las características innovadoras de Microsoft Edge](https://www.microsoft.com/edge/features)
- [Proteger la red](network-protection.md)
- [Habilitar protección de red](enable-network-protection.md)
- [Protección web](web-protection-overview.md)
- [Crear indicadores](manage-indicators.md)
- [Filtrado de contenido web](web-content-filtering.md)
