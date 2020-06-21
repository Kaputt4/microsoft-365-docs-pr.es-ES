---
title: Nueva aplicación Microsoft Edge
description: ''
keywords: explorador, escritorio administrado por Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0602d7c6afef6190578268c78994b43ac60d0d2f
ms.sourcegitcommit: 3119b2246001ba06af8264508785352dfb894166
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44820688"
---
# <a name="new-microsoft-edge-app"></a>Nueva aplicación Microsoft Edge

El nuevo [Explorador de Microsoft Edge](https://www.microsoft.com/edge) proporciona un rendimiento de primera clase con más privacidad, más productividad y más valor mientras se navega. El escritorio administrado de Microsoft ofrece una vista previa pública de la implementación del nuevo explorador perimetral en su entorno.

## <a name="initial-deployment"></a>Implementación inicial

Para migrar los dispositivos de escritorio administrados por Microsoft al nuevo explorador Microsoft Edge, archivo un vale de soporte técnico de ti a través del portal de escritorio administrado de Microsoft. Se implementará el canal estable del perímetro en el grupo de prueba cuando se archiva el vale y, a continuación, se implementa en cada grupo de implementación subsiguiente cada 24 horas. Para pausar la implementación, archivo otro que pregunte a las operaciones que hay que conservar.

## <a name="updates-to-microsoft-edge"></a>Actualizaciones de Microsoft Edge

Microsoft Managed Desktop implementa el [canal estable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) de Microsoft Edge, que se actualiza automáticamente cada seis semanas. El grupo de productos Microsoft Edge distribuye [progresivamente](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) las actualizaciones en el canal estable para garantizar la mejor experiencia para los clientes. El canal de la versión beta de Microsoft Edge no está disponible actualmente.

Para asegurarse de que Microsoft Edge se actualiza correctamente, no modifique las [directivas de actualización](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)de Microsoft Edge.

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrada por el escritorio administrado por Microsoft

Microsoft Managed Desktop ha creado un conjunto de directivas predeterminado para Microsoft Edge para proteger el explorador. La configuración predeterminada del explorador es la siguiente:

### <a name="microsoft-edge-extensions"></a>Extensiones de Microsoft Edge

La línea base de seguridad para Microsoft Edge en dispositivos de escritorio administrados de Microsoft establece dos directivas para deshabilitar todas las extensiones de Chrome y los usuarios finales seguros. Para habilitar e implementar extensiones en su entorno, vea la configuración que administre. 

#### <a name="extension-installation-blocklist"></a>Lista de bloqueo de instalación de extensión
**Valor predeterminado:** Todos

El escritorio administrado de Microsoft establece esta directiva para evitar que se instalen extensiones de Chrome en los extremos administrados. Se conocen risksassociated con el modelo de extensión de cromo, incluida la protección contra la pérdida de datos, la privacidad y otros riesgos que pueden poner en peligro los dispositivos. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Permitir hosts de mensajería nativa en el nivel de usuario (instalado sin permisos de administrador)

**Valor predeterminado:** Capacidad

Al deshabilitar esta Directiva, Microsoft Edge solo usará los hosts de mensajería nativa instalados en el nivel del sistema. Los hosts de mensajería nativa forman parte de las extensiones de Chrome que permiten al explorador interactuar con otras partes del extremo del usuario, lo que crea una gran variedad de problemas de seguridad.  

### <a name="secure-sockets-layer-ssl"></a>Capa de sockets seguros (SSL)

#### <a name="minimum-ssl-version"></a>Versión mínima de SSL

**Valor predeterminado:** Compatible con TLS 1,2 mínimo

Si desea usar el TLS 1,1 menos seguro, puede solicitar esto.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Permite a los usuarios continuar desde la página de advertencia de SSL

**Valor predeterminado:** Capacidad

No se recomienda habilitar esta configuración, ya que permite a los usuarios visitar sitios con errores de SSL.

### <a name="microsoft-defender-smart-screen"></a>Pantalla inteligente de Microsoft defender

#### <a name="configure-microsoft-defender-smartscreen"></a>Configurar SmartScreen de Microsoft defender

**Valor predeterminado:** Preparado

Está habilitado de forma predeterminada para ayudar a proteger a los usuarios finales.

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a>Avisos SmartScreen de Microsoft defender para sitios

**Valor predeterminado:** Preparado

No se recomienda deshabilitar esta configuración, ya que permite a los usuarios omitir las advertencias y continuar con sitios potencialmente malintencionados.

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>Impedir la omisión de advertencias de SmartScreen de Microsoft defender sobre descargas

**Valor predeterminado:** Preparado

No se recomienda deshabilitar esta configuración, ya que permite a los usuarios omitir las advertencias y completar las descargas sin comprobar.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Configuración predeterminada de Adobe Flash

**Valor predeterminado:** Capacidad

No se recomienda usar flash debido a los riesgos de seguridad asociados. Si sigue teniendo procesos que dependen de Flash, establezca la Directiva de **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar Flash para los sitios que la necesiten. Si no se puede mantener una lista de sitios permitida para usar Flash, archivo una solicitud de cambio para cambiar el valor a **click to Play**, lo que permite a los usuarios elegir cuándo es adecuado ejecutar Flash.

### <a name="password-manager"></a>Administrador de contraseñas

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Habilitar el guardado de contraseñas en el administrador de contraseñas

**Valor predeterminado:** Capacidad

No se recomienda permitir que los usuarios finales guarden contraseñas en el dispositivo.

### <a name="other-settings"></a>Otras opciones de configuración

#### <a name="enable-site-isolation-for-every-site"></a>Habilitar el aislamiento del sitio para cada sitio

**Valor predeterminado:** Preparado

Cuando esta directiva está habilitada, los usuarios no pueden optar por el comportamiento predeterminado en el que cada sitio se ejecuta en su propio proceso.

#### <a name="supported-authentication-schemes"></a>Esquemas de autenticación admitidos

**Valor predeterminado:** NTLM, Negotiate

El escritorio administrado de Microsoft no es compatible con esquemas de autenticación básica o implícita.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importar automáticamente los datos y la configuración de otro explorador al ejecutarse por primera vez

**Valor predeterminado:** Importar automáticamente todos los tipos de configuración y los tipos de los tipos de los idiomas admitidos del explorador predeterminado 

Con esta Directiva aplicada, la primera experiencia de ejecución omitirá la sección de importación, lo que minimizará la interacción del usuario. Los datos del explorador de versiones anteriores de Microsoft Edge siempre se migrarán silenciosamente en la primera ejecución, independientemente de esta configuración. 


## <a name="settings-you-manage"></a>Configuración que administra

Puede implementar cualquier configuración de Microsoft Edge que no se haya descrito anteriormente mediante el perfil plantillas administrativas de Microsoft Intune. Para obtener más información, vea [Configure Microsoft Edge Policy Settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune). Si quiere evaluar una directiva que no está incluida actualmente en las plantillas administrativas de Microsoft Edge en Intune, puede usar la configuración personalizada para dispositivos Windows 10 en Intune.

### <a name="enabling-specific-chrome-extensions"></a>Habilitación de extensiones de Chrome específicas

La plantilla administrativa ofrece una configuración para implementar extensiones de Chrome específicas con Microsoft Intune. Puede encontrarlo en **configuración del equipo > Microsoft Edge > extensiones > permitir que se instalen extensiones específicas**.

### <a name="install-extensions-silently"></a>Instalar extensiones en modo silencioso

También puede usar la plantilla administrativa para configurar Microsoft Edge para que instale extensiones sin avisar al usuario. Puede encontrarlo en **configuración del equipo > Microsoft Edge > extensiones > controlar qué extensiones se instalan silenciosamente**.

### <a name="other-common-enterprise-policies"></a>Otras directivas de empresa comunes

Microsoft Edge ofrece una gran cantidad de directivas adicionales. Estos son algunos de los más comunes:
 
- [Configurar sitios en la lista de sitios de empresa y en el modo IE](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Configurar las opciones de página de inicio, Página principal y nueva pestaña](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurar la configuración del juego surf](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurar opciones de servidor proxy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

