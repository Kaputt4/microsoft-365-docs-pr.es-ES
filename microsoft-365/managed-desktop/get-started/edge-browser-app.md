---
title: Nuevo Microsoft Edge
description: Explica cómo se implementa y actualiza el nuevo explorador perimetral
keywords: explorador, Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822255"
---
# <a name="new-microsoft-edge-app"></a>Nueva Microsoft Edge aplicación

El nuevo [Microsoft Edge ofrece](https://www.microsoft.com/edge) un rendimiento de clase mundial con más privacidad, más productividad y más valor mientras explora. Escritorio administrado de Microsoft ofrece una vista previa pública de la implementación del nuevo explorador perimetral en su entorno.

## <a name="initial-deployment"></a>Implementación inicial

Para migrar los dispositivos Escritorio administrado de Microsoft al nuevo explorador de Microsoft Edge, file an IT Support Ticket through the Escritorio administrado de Microsoft Portal. Implementaremos el canal estable perimetral en el grupo de prueba al presentar el vale y, a continuación, lo implementaremos en cada grupo de implementación posterior cada 24 horas. Para pausar la implementación, file another ticket asking Operations to hold.

El [canal beta](/deployedge/microsoft-edge-channels#beta-channel) también está disponible a petición de validación representativa en su organización. Escritorio administrado de Microsoft implementará la aplicación según sea necesario en los grupos Test y First para que todos esos usuarios tengan el Canal Beta además del canal estable. Para cualquier otro usuario que necesite acceso al canal beta, agrégrelos al grupo **Modern Workplace - Edge Beta Users** y haga que lo instalen desde el Portal de empresa

## <a name="updates-to-microsoft-edge"></a>Actualizaciones de Microsoft Edge

Escritorio administrado de Microsoft implementa el [canal](/deployedge/microsoft-edge-channels#stable-channel) estable de Microsoft Edge, que se actualiza automáticamente cada seis semanas. Las actualizaciones en el [](/deployedge/microsoft-edge-update-progressive-rollout) canal estable se revierte progresivamente por el grupo de productos Microsoft Edge para garantizar la mejor experiencia para los clientes. 

El [canal beta](/deployedge/microsoft-edge-channels#beta-channel) se implementa en dispositivos de los grupos Test y First para la validación representativa dentro de la organización. Este canal es totalmente compatible y se actualiza automáticamente con nuevas características aproximadamente cada seis semanas.

Para asegurarse de que Microsoft Edge actualizaciones correctamente, no modifique las Microsoft Edge [de actualización.](/deployedge/microsoft-edge-update-policies)



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrado por Escritorio administrado de Microsoft

Escritorio administrado de Microsoft ha creado un conjunto predeterminado de directivas para Microsoft Edge proteger el explorador. La configuración predeterminada del explorador es la siguiente:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge de Microsoft Edge de datos

La línea base de seguridad Microsoft Edge dispositivos Escritorio administrado de Microsoft establece dos directivas para deshabilitar todas las extensiones de Chrome y proteger a los usuarios. Para habilitar e implementar extensiones en el entorno, consulte Configuración puede administrar. 

#### <a name="extension-installation-blocklist"></a>Lista de bloqueo de instalación de extensión
**Valor predeterminado:** Todos

Escritorio administrado de Microsoft esta directiva para evitar que las extensiones de Chrome se instalen en puntos de conexión administrados. Existen riesgos conocidos asociados con el modelo de extensión Chromium de datos, incluida la protección contra pérdida de datos, la privacidad y otros riesgos que pueden poner en peligro los dispositivos. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Permitir hosts de mensajería nativa de nivel de usuario (instalados sin permisos de administrador)

**Valor predeterminado:** Deshabilitado

Al deshabilitar esta directiva, Microsoft Edge solo usará hosts de mensajería nativos instalados en el nivel del sistema. Los hosts de mensajería nativa forman parte de las extensiones de Chrome, que permiten que el explorador interactúe con otras partes del extremo del usuario, lo que crea una variedad de problemas de seguridad.  

### <a name="secure-sockets-layer-tlsssl"></a>Capa de sockets seguros (TLS/SSL)

#### <a name="minimum-tls-version"></a>Versión mínima de TLS

**Valor predeterminado:** Tls 1.2 mínimo compatible

Si desea usar la TLS 1.1 menos segura, puede presentar una solicitud para hacerlo.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Permite a los usuarios continuar desde la página de advertencia de SSL

**Valor predeterminado:** Deshabilitado

No se recomienda habilitar esta configuración, ya que permite a los usuarios visitar sitios con errores de TSL.

### <a name="microsoft-defender-smartscreen"></a>SmartScreen de Microsoft Defender

#### <a name="configure-windows-defender-smartscreen"></a>Configurar Windows Defender SmartScreen

**Valor predeterminado:** Habilitado

Habilitado de forma predeterminada para ayudar a proteger a los usuarios.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender Mensajes de SmartScreen para sitios

**Valor predeterminado:** Habilitado

No se recomienda deshabilitar esta configuración, ya que permitiría a los usuarios omitir las advertencias y continuar con sitios potencialmente malintencionados.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Impedir la omisión de Windows Defender advertencias de SmartScreen sobre descargas

**Valor predeterminado:** Habilitado

No se recomienda deshabilitar esta configuración, ya que permitiría a los usuarios omitir advertencias y completar descargas no verificados.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Configuración predeterminada de Adobe Flash

**Valor predeterminado:** Deshabilitado

No se recomienda usar Flash debido a los riesgos de seguridad asociados. Si todavía tiene procesos que dependen de Flash, establezca la directiva **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar Flash para los sitios que lo necesiten. Si no puedes mantener una lista permitida de sitios para usar Flash, presentar una solicitud de cambio para cambiar el valor a **Hacer** clic para reproducir, lo que permite a los usuarios elegir cuándo es adecuado ejecutar Flash.

### <a name="password-manager"></a>Administrador de contraseñas

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Habilitar el guardado de contraseñas en el administrador de contraseñas

**Valor predeterminado:** Deshabilitado

El administrador de contraseñas está deshabilitado de forma predeterminada. Si te gusta esta característica habilitada, presenta una solicitud de soporte técnico y nuestros ingenieros de servicio pueden habilitar la configuración en tu entorno. 

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modo internet Explorer en Microsoft Edge
El modo IE en Microsoft Edge facilita el uso de todos los sitios que su organización necesita en un solo explorador. Usa el motor Chromium integrado para sitios compatibles con el motor de representación de Chromium y usa el motor MSHTML trident de Internet Explorer 11 (IE11) para sitios que no son o tienen dependencias de la funcionalidad de IE. [Más información](/DeployEdge/edge-ie-mode) 

Escritorio administrado de Microsoft habilita el modo de Internet Explorer para los dispositivos de forma predeterminada 

#### <a name="internet-explorer-mode-integration"></a>Integración del modo de Internet Explorer
**Valor predeterminado:** Modo de Internet Explorer

De forma predeterminada, los dispositivos están configurados para usar el modo Internet Explorer, pero puedes establecerlos para que abran sitios en una ventana independiente de Internet Explorer 11. Para cambiar este comportamiento, presente una solicitud de soporte técnico.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Agregar sitios a la lista Enterprise sitio de modo de acceso
Para que los sitios se abran en modo Internet Explorer, debe incluirlos en la [lista Enterprise sitio](/DeployEdge/edge-ie-mode-sitelist). Mantener e implementar la lista Enterprise sitio es su responsabilidad. Para obtener más información, vea [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Otras opciones de configuración

#### <a name="enable-site-isolation-for-every-site"></a>Habilitar el aislamiento de sitios para cada sitio

**Valor predeterminado:** Habilitado

Cuando esta directiva está habilitada, los usuarios no pueden optar por el comportamiento predeterminado en el que cada sitio se ejecuta en su propio proceso.

#### <a name="supported-authentication-schemes"></a>Esquemas de autenticación compatibles

**Valor predeterminado:** NTLM, Negociar

Escritorio administrado de Microsoft no admite esquemas de autenticación básica o implícita.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importar automáticamente los datos y la configuración de otro explorador en la primera ejecución

**Valor predeterminado:** Importar automáticamente todos los tipos de datos y la configuración admitidos desde el explorador predeterminado 

Con esta directiva aplicada, la primera experiencia de ejecución omitirá la sección de importación, lo que minimizará la interacción del usuario. Los datos del explorador de versiones anteriores de Microsoft Edge se migrarán siempre silenciosamente en la primera ejecución, independientemente de esta configuración. 


## <a name="settings-you-manage"></a>Configuración administrar

Puede implementar cualquier configuración Microsoft Edge no descrita anteriormente mediante el perfil Plantillas administrativas en Microsoft Intune. Para obtener más información, [vea Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune). Si desea evaluar una directiva que no se incluye actualmente en las plantillas administrativas de Microsoft Edge en Intune, puede usar la configuración personalizada para los dispositivos Windows 10 en Intune.

### <a name="enabling-specific-chrome-extensions"></a>Habilitar extensiones específicas de Chrome

La plantilla administrativa ofrece una configuración para implementar extensiones de Chrome determinadas con Microsoft Intune. Puede encontrarlo en Configuración del **equipo > Microsoft Edge > extensiones > Permitir** que se instalen extensiones específicas .

### <a name="install-extensions-silently"></a>Instalar extensiones de forma silenciosa

También puede usar la plantilla administrativa para establecer Microsoft Edge para instalar extensiones sin avisar al usuario. Puede encontrarlo en Configuración del equipo > Microsoft Edge > extensiones > Control de extensiones que **se instalan silenciosamente**.

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge de actualización
Para asegurarse de que Microsoft Edge actualizaciones correctamente, no modifique las Microsoft Edge [de actualización.](/deployedge/microsoft-edge-update-policies)

### <a name="other-common-enterprise-policies"></a>Otras directivas de empresa comunes

Microsoft Edge ofrece muchas otras directivas. Estas son algunas de las más comunes:
 
- [Configurar sitios en la lista Enterprise sitio y el modo IE](/deployedge/edge-ie-mode-sitelist)
- [Configurar la configuración de inicio, página principal y nueva página de pestañas](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurar configuración de juego de surf](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurar la configuración del servidor proxy](/deployedge/microsoft-edge-policies#proxy-server)
