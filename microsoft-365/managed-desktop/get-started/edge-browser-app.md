---
title: Nuevo Microsoft Edge
description: Explica cómo se implementa y actualiza el nuevo explorador Edge
keywords: explorador, Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841344"
---
# <a name="new-microsoft-edge-app"></a>Nueva aplicación de Microsoft Edge

El nuevo [explorador Microsoft Edge proporciona](https://www.microsoft.com/edge) un rendimiento de primer nivel con más privacidad, más productividad y más valor mientras exploras. Escritorio administrado de Microsoft ofrece una versión preliminar pública de la implementación del nuevo explorador Edge en su entorno.

## <a name="initial-deployment"></a>Implementación inicial

Para migrar los dispositivos de Escritorio administrado de Microsoft al nuevo explorador Microsoft Edge, debe presentar un vale de soporte técnico de TI a través del Portal de escritorio administrado de Microsoft. Implementaremos el canal estable perimetral en el grupo de prueba al presentar el vale y, a continuación, lo implementaremos en cada grupo de implementación posterior cada 24 horas. Para pausar la implementación, file another ticket asking Operations to hold.

El [canal beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) también está disponible cuando se solicita la validación representativa dentro de su organización. Escritorio administrado de Microsoft implementará la aplicación según sea necesario para los grupos De prueba y Primeros grupos para que todos esos usuarios tengan el canal beta además del canal estable. Para cualquier otro usuario que necesite acceso al canal beta, agrégrelos al grupo **Modern Workplace - Edge Beta Users** y haga que lo instalen desde el Portal de empresa.

## <a name="updates-to-microsoft-edge"></a>Actualizaciones de Microsoft Edge

Escritorio administrado de Microsoft implementa el [canal estable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) de Microsoft Edge, que se actualiza automáticamente cada seis semanas. El grupo de productos [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) de Microsoft Edge implanta las actualizaciones en el canal estable de forma progresiva para garantizar la mejor experiencia para los clientes. 

El [canal beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) se implementa en dispositivos de los grupos Test y First para la validación representativa dentro de la organización. Este canal es totalmente compatible y se actualiza automáticamente con nuevas características aproximadamente cada seis semanas.

Para asegurarse de que Microsoft Edge se actualiza correctamente, no modifique las directivas de actualización [de](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrada por Escritorio administrado de Microsoft

Escritorio administrado de Microsoft ha creado un conjunto predeterminado de directivas para Que Microsoft Edge proteja el explorador. La configuración predeterminada del explorador es la siguiente:

### <a name="microsoft-edge-extensions"></a>Extensiones de Microsoft Edge

La línea base de seguridad para Microsoft Edge en dispositivos de Escritorio administrado de Microsoft establece dos directivas para deshabilitar todas las extensiones de Chrome y proteger a los usuarios. Para habilitar e implementar extensiones en su entorno, consulte Configuración que administra. 

#### <a name="extension-installation-blocklist"></a>Lista de bloqueados de instalación de extensión
**Valor predeterminado:** Todos

Escritorio administrado de Microsoft establece esta directiva para evitar que se instalen extensiones de Chrome en los puntos de conexión administrados. Existen riesgos conocidos asociados con el modelo de extensión chromium, como la protección contra la pérdida de datos, la privacidad y otros riesgos que pueden poner en peligro los dispositivos. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Permitir hosts de mensajería nativa de nivel de usuario (instalados sin permisos de administrador)

**Valor predeterminado:** Deshabilitado

Al deshabilitar esta directiva, Microsoft Edge solo usará hosts de mensajería nativos instalados en el nivel del sistema. Los hosts de mensajería nativa forman parte de las extensiones de Chrome, que permiten que el explorador interactúe con otras partes del extremo del usuario, lo que crea una variedad de problemas de seguridad.  

### <a name="secure-sockets-layer-tlsssl"></a>Capa de sockets seguros (TLS/SSL)

#### <a name="minimum-tls-version"></a>Versión mínima de TLS

**Valor predeterminado:** Tls 1.2 mínimo compatible

Si desea usar tls 1.1 menos seguro, puede presentar una solicitud para hacerlo.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Permite a los usuarios continuar desde la página de advertencia de SSL

**Valor predeterminado:** Deshabilitado

No se recomienda habilitar esta configuración, ya que permite a los usuarios visitar sitios con errores de TSL.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Configurar Windows Defender SmartScreen

**Valor predeterminado:** Habilitado

Habilitado de forma predeterminada para ayudar a proteger a los usuarios.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender de SmartScreen para sitios

**Valor predeterminado:** Habilitado

No se recomienda deshabilitar esta configuración, ya que esto permitiría a los usuarios ignorar las advertencias y seguir usando sitios potencialmente malintencionados.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Evitar la omisión de Windows Defender advertencias de SmartScreen sobre descargas

**Valor predeterminado:** Habilitado

No se recomienda deshabilitar esta configuración, ya que esto permitiría a los usuarios omitir las advertencias y completar descargas no verificados.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Configuración predeterminada de Adobe Flash

**Valor predeterminado:** Deshabilitado

No recomendamos usar Flash debido a los riesgos de seguridad asociados. Si todavía tiene procesos que dependen de Flash, establezca la directiva **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar Flash para los sitios que la necesiten. Si no puedes mantener una lista de sitios permitidos para usar Flash, presentar una solicitud de cambio para cambiar el valor a **Hacer** clic y reproducir, lo que permite a los usuarios elegir cuándo es adecuado ejecutar Flash.

### <a name="password-manager"></a>Administrador de contraseñas

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Habilitar el almacenamiento de contraseñas en el administrador de contraseñas

**Valor predeterminado:** Deshabilitado

No se recomienda permitir que los usuarios guarden contraseñas en su dispositivo.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modo de Internet Explorer en Microsoft Edge
El modo IE en Microsoft Edge facilita el uso de todos los sitios que la organización necesita en un único explorador. Usa el motor chromium integrado para sitios que son compatibles con el motor de representación de Chromium y usa el motor MSHTML trident de Internet Explorer 11 (IE11) para sitios que no son o tienen dependencias en la funcionalidad de IE. [Más información] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Escritorio administrado de Microsoft habilita el modo Internet Explorer para sus dispositivos de forma predeterminada 

#### <a name="internet-explorer-mode-integration"></a>Integración del modo Internet Explorer
**Valor predeterminado:** Modo internet Explorer

De forma predeterminada, los dispositivos están configurados para usar el modo Internet Explorer, pero puedes configurarlos para que abran sitios en una ventana independiente de Internet Explorer 11. Para cambiar este comportamiento, presente una solicitud de soporte técnico.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Agregar sitios a la lista de sitios del Modo de empresa
Para que los sitios se abran en modo Internet Explorer, debe incluirlos en la lista [De sitios de empresa.](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist) Mantener e implementar la lista de sitios de empresa es su responsabilidad. Para obtener más información, consulta [Configurar mediante la directiva Configurar la lista de sitios del Modo de empresa](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Otras opciones de configuración

#### <a name="enable-site-isolation-for-every-site"></a>Habilitar el aislamiento de sitios para cada sitio

**Valor predeterminado:** Habilitado

Cuando esta directiva está habilitada, los usuarios no pueden optar por no participar en el comportamiento predeterminado en el que cada sitio se ejecuta en su propio proceso.

#### <a name="supported-authentication-schemes"></a>Esquemas de autenticación admitidos

**Valor predeterminado:** NTLM, Negociar

El Escritorio administrado de Microsoft no admite esquemas de autenticación básica o implícita.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importar automáticamente los datos y la configuración de otro explorador en la primera ejecución

**Valor predeterminado:** Importar automáticamente todos los tipos de datos y la configuración admitidos desde el explorador predeterminado 

Con esta directiva aplicada, la experiencia de primera ejecución omitirá la sección de importación, minimizando la interacción del usuario. Los datos del explorador de versiones anteriores de Microsoft Edge siempre se migrarán silenciosamente en la primera ejecución, independientemente de esta configuración. 


## <a name="settings-you-manage"></a>Configuración que administra

Puedes implementar cualquier configuración de Microsoft Edge que no se describió anteriormente mediante el perfil plantillas administrativas de Microsoft Intune. Para obtener más información, [vea Configurar las opciones de directiva de Microsoft Edge con Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune) Si quieres evaluar una directiva que actualmente no está incluida en las plantillas administrativas de Microsoft Edge en Intune, puedes usar la configuración personalizada para dispositivos Windows 10 en Intune.

### <a name="enabling-specific-chrome-extensions"></a>Habilitar extensiones específicas de Chrome

La plantilla administrativa ofrece una configuración para implementar extensiones de Chrome concretas con Microsoft Intune. Puede encontrarlo en Configuración del equipo > Microsoft Edge > extensiones > permitir la instalación **de extensiones específicas.**

### <a name="install-extensions-silently"></a>Instalar extensiones en modo silencioso

También puede usar la plantilla administrativa para configurar Microsoft Edge para instalar extensiones sin avisar al usuario. Puede encontrarlo en Configuración del equipo > Microsoft Edge > Extensiones > control de qué extensiones se **instalan en modo silencioso.**

### <a name="microsoft-edge-update-policies"></a>Directivas de actualización de Microsoft Edge
Para asegurarse de que Microsoft Edge se actualiza correctamente, no modifique las directivas de actualización [de](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.

### <a name="other-common-enterprise-policies"></a>Otras directivas de empresa comunes

Microsoft Edge ofrece muchas otras directivas. Estas son algunas de las más comunes:
 
- [Configurar sitios en la lista de sitios de empresa y el modo IE](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Configurar las opciones de inicio, página principal y página de nueva pestaña](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurar la configuración del juego de surf](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configuración de las opciones del servidor proxy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

