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
ms.openlocfilehash: 033826a7f82278f6e36b422284a1076cba57d584
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921983"
---
# <a name="new-microsoft-edge-app"></a>Nueva aplicación de Microsoft Edge

El nuevo [explorador de Microsoft Edge](https://www.microsoft.com/edge) proporciona un rendimiento de clase mundial con más privacidad, más productividad y más valor mientras explora. Microsoft Managed Desktop ofrece una vista previa pública de la implementación del nuevo explorador perimetral en su entorno.

## <a name="initial-deployment"></a>Implementación inicial

Para migrar los dispositivos de Escritorio administrado de Microsoft al nuevo explorador de Microsoft Edge, file an IT Support Ticket through the Microsoft Managed Desktop Portal. Implementaremos el canal estable perimetral en el grupo de prueba al presentar el vale y, a continuación, lo implementaremos en cada grupo de implementación posterior cada 24 horas. Para pausar la implementación, file another ticket asking Operations to hold.

El [canal beta](/deployedge/microsoft-edge-channels#beta-channel) también está disponible a petición de validación representativa en su organización. Microsoft Managed Desktop implementará la aplicación según sea necesario en los grupos Test y First para que todos esos usuarios tengan el Canal Beta además del canal estable. Para cualquier otro usuario que necesite acceso al canal beta, agrégrelos al grupo **Modern Workplace - Edge Beta Users** y haga que lo instalen desde el Portal de empresa.

## <a name="updates-to-microsoft-edge"></a>Actualizaciones de Microsoft Edge

Microsoft Managed Desktop implementa el [canal estable](/deployedge/microsoft-edge-channels#stable-channel) de Microsoft Edge, que se actualiza automáticamente cada seis semanas. El grupo de productos [](/deployedge/microsoft-edge-update-progressive-rollout) de Microsoft Edge implanta progresivamente las actualizaciones en el canal estable para garantizar la mejor experiencia para los clientes. 

El [canal beta](/deployedge/microsoft-edge-channels#beta-channel) se implementa en dispositivos de los grupos Test y First para la validación representativa dentro de la organización. Este canal es totalmente compatible y se actualiza automáticamente con nuevas características aproximadamente cada seis semanas.

Para asegurarse de que Microsoft Edge se actualiza correctamente, no modifique las directivas de actualización [de](/deployedge/microsoft-edge-update-policies)Microsoft Edge .



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrada por Microsoft Managed Desktop

Microsoft Managed Desktop ha creado un conjunto predeterminado de directivas para que Microsoft Edge proteja el explorador. La configuración predeterminada del explorador es la siguiente:

### <a name="microsoft-edge-extensions"></a>Extensiones de Microsoft Edge

La línea base de seguridad de Microsoft Edge en dispositivos de Escritorio administrado de Microsoft establece dos directivas para deshabilitar todas las extensiones de Chrome y proteger a los usuarios. Para habilitar e implementar extensiones en el entorno, consulte Configuración que administra. 

#### <a name="extension-installation-blocklist"></a>Lista de bloqueo de instalación de extensión
**Valor predeterminado:** Todos

Microsoft Managed Desktop establece esta directiva para evitar que las extensiones de Chrome se instalen en puntos de conexión administrados. Existen riesgos conocidos asociados con el modelo de extensión Chromium, como la protección contra la pérdida de datos, la privacidad y otros riesgos que pueden poner en peligro los dispositivos. 

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

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Configurar Windows Defender SmartScreen

**Valor predeterminado:** Habilitado

Habilitado de forma predeterminada para ayudar a proteger a los usuarios.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender smartscreen solicita sitios

**Valor predeterminado:** Habilitado

No se recomienda deshabilitar esta configuración, ya que permitiría a los usuarios omitir las advertencias y continuar con sitios potencialmente malintencionados.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Evitar el desvío de Windows Defender advertencias de SmartScreen sobre descargas

**Valor predeterminado:** Habilitado

No se recomienda deshabilitar esta configuración, ya que permitiría a los usuarios omitir advertencias y completar descargas no verificados.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Configuración predeterminada de Adobe Flash

**Valor predeterminado:** Deshabilitado

No se recomienda usar Flash debido a los riesgos de seguridad asociados. Si todavía tiene procesos que dependen de Flash, establezca la directiva **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar Flash para los sitios que lo necesiten. Si no puedes mantener una lista permitida de sitios para usar Flash, presentar una solicitud de cambio para cambiar el valor a **Hacer** clic para reproducir, lo que permite a los usuarios elegir cuándo es adecuado ejecutar Flash.

### <a name="password-manager"></a>Administrador de contraseñas

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Habilitar el guardado de contraseñas en el administrador de contraseñas

**Valor predeterminado:** Deshabilitado

No se recomienda permitir que los usuarios guarden contraseñas en su dispositivo.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modo de Internet Explorer en Microsoft Edge
El modo IE en Microsoft Edge facilita el uso de todos los sitios que la organización necesita en un solo explorador. Usa el motor chromium integrado para sitios compatibles con el motor de representación de Chromium y usa el motor MSHTML trident de Internet Explorer 11 (IE11) para sitios que no son o tienen dependencias de la funcionalidad de IE. [Más información] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop habilita el modo de Internet Explorer para sus dispositivos de forma predeterminada 

#### <a name="internet-explorer-mode-integration"></a>Integración del modo de Internet Explorer
**Valor predeterminado:** Modo de Internet Explorer

De forma predeterminada, los dispositivos están configurados para usar el modo Internet Explorer, pero puedes establecerlos para que abran sitios en una ventana independiente de Internet Explorer 11. Para cambiar este comportamiento, presente una solicitud de soporte técnico.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Agregar sitios a la lista de sitios del modo de empresa
Para que los sitios se abran en modo Internet Explorer, debe incluirlos en la [lista Sitio de empresa.](/DeployEdge/edge-ie-mode-sitelist) El mantenimiento e implementación de la lista de sitios de empresa es su responsabilidad. Para obtener más información, vea [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Otras opciones de configuración

#### <a name="enable-site-isolation-for-every-site"></a>Habilitar el aislamiento de sitios para cada sitio

**Valor predeterminado:** Habilitado

Cuando esta directiva está habilitada, los usuarios no pueden optar por el comportamiento predeterminado en el que cada sitio se ejecuta en su propio proceso.

#### <a name="supported-authentication-schemes"></a>Esquemas de autenticación compatibles

**Valor predeterminado:** NTLM, Negociar

Microsoft Managed Desktop no admite esquemas de autenticación básica o implícita.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importar automáticamente los datos y la configuración de otro explorador en la primera ejecución

**Valor predeterminado:** Importar automáticamente todos los tipos de datos y la configuración admitidos desde el explorador predeterminado 

Con esta directiva aplicada, la primera experiencia de ejecución omitirá la sección de importación, lo que minimizará la interacción del usuario. Los datos del explorador de versiones anteriores de Microsoft Edge siempre se migrarán silenciosamente en la primera ejecución, independientemente de esta configuración. 


## <a name="settings-you-manage"></a>Configuración que administra

Puede implementar cualquier configuración de Microsoft Edge no descrita anteriormente mediante el perfil Plantillas administrativas en Microsoft Intune. Para obtener más información, vea [Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune). Si quieres evaluar una directiva que no se incluye actualmente en las plantillas administrativas de Microsoft Edge en Intune, puedes usar la configuración personalizada para dispositivos Windows 10 en Intune.

### <a name="enabling-specific-chrome-extensions"></a>Habilitar extensiones específicas de Chrome

La plantilla administrativa ofrece una configuración para implementar extensiones de Chrome concretas con Microsoft Intune. Puede encontrarlo en Configuración del equipo > Microsoft Edge > extensiones > Permitir que se **instalen extensiones específicas**.

### <a name="install-extensions-silently"></a>Instalar extensiones de forma silenciosa

También puede usar la plantilla administrativa para establecer Microsoft Edge para instalar extensiones sin avisar al usuario. Puede encontrarlo en Configuración del equipo > Microsoft Edge > extensions > Control qué extensiones se **instalan silenciosamente**.

### <a name="microsoft-edge-update-policies"></a>Directivas de actualización de Microsoft Edge
Para asegurarse de que Microsoft Edge se actualiza correctamente, no modifique las directivas de actualización [de](/deployedge/microsoft-edge-update-policies)Microsoft Edge .

### <a name="other-common-enterprise-policies"></a>Otras directivas de empresa comunes

Microsoft Edge ofrece muchas otras directivas. Estas son algunas de las más comunes:
 
- [Configurar sitios en la lista de sitios de empresa y el modo IE](/deployedge/edge-ie-mode-sitelist)
- [Configurar la configuración de inicio, página principal y nueva página de pestañas](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurar configuración de juego de surf](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurar la configuración del servidor proxy](/deployedge/microsoft-edge-policies#proxy-server)