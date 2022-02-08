---
title: Microsoft Edge
description: Explica cómo se implementa Microsoft Edge y se actualiza el explorador
keywords: explorador, Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: aab02ec260f0131ab32d28834152f50b84abce21
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444610"
---
# <a name="microsoft-edge"></a>Microsoft Edge

[Microsoft Edge](https://www.microsoft.com/edge) proporciona un rendimiento y un valor de clase mundial con:

- Más privacidad y protección frente a amenazas externas.
- Más productividad y acceso rápido a Office aplicaciones, archivos, sitios y aplicaciones integradas Búsqueda de Microsoft.
- Experiencia sin problemas mediante la sincronización entre dispositivos con perfiles y soporte multiplataforma.

> [!IMPORTANT]
> La aplicación de escritorio de Internet Explorer 11 se retirará y se retirará del soporte técnico el 15 de junio de 2022 (para obtener una lista de lo que está en el ámbito, vea las preguntas más [frecuentes](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/internet-explorer-11-desktop-app-retirement-faq/ba-p/2366549). Las mismas aplicaciones y sitios de IE11 que usa hoy pueden abrirse en Microsoft Edge con el modo de Internet Explorer. [Obtenga más información aquí](https://blogs.windows.com/windowsexperience/2021/05/19/the-future-of-internet-explorer-on-windows-10-is-in-microsoft-edge/).

## <a name="updates-to-microsoft-edge"></a>Actualizaciones de Microsoft Edge

Microsoft Managed Desktop implementa el canal [estable extendido](/deployedge/microsoft-edge-channels#extended-stable-channel) de Microsoft Edge, que se actualiza automáticamente cada ocho semanas. Las actualizaciones del canal estable extendido se extienden [](/deployedge/microsoft-edge-update-progressive-rollout) progresivamente por el grupo de Microsoft Edge productos para garantizar la mejor experiencia para los clientes.

El [canal beta](/deployedge/microsoft-edge-channels#beta-channel) se implementa en dispositivos del grupo De prueba para la validación representativa dentro de la organización. Este canal es totalmente compatible y se actualiza automáticamente con nuevas características aproximadamente cada cuatro semanas.

> [!IMPORTANT]
> Para asegurarse de que Microsoft Edge actualizaciones correctamente, no modifique las Microsoft Edge [de actualización.](/deployedge/microsoft-edge-update-policies)

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Configuración administrado por Microsoft Managed Desktop

Microsoft Managed Desktop ha creado un conjunto predeterminado de directivas para Microsoft Edge proteger el explorador. La configuración predeterminada del explorador es la siguiente:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge de Microsoft Edge de datos

La línea base de seguridad Microsoft Edge dispositivos de Escritorio administrado de Microsoft establece dos directivas para deshabilitar todas las extensiones de Chrome y proteger a los usuarios. Para habilitar e implementar extensiones en el entorno, consulte [Configuración que administra](#settings-you-manage).

| Configuración | Valor predeterminado | Descripción |
| ------ | ------ | ------ |
| Lista de bloqueo de instalación de extensión | Todo | Microsoft Managed Desktop establece esta directiva para evitar que las extensiones de Chrome se instalen en puntos de conexión administrados. Existen riesgos conocidos asociados con el modelo de extensión Chromium de datos, incluida la protección contra pérdida de datos, la privacidad y otros riesgos que pueden poner en peligro los dispositivos. |
| Permitir hosts de mensajería nativa de nivel de usuario (instalados sin permisos de administrador) | Deshabilitado | Al deshabilitar esta directiva, Microsoft Edge solo usará hosts de mensajería nativos instalados en el nivel del sistema. Los hosts de mensajería nativa forman parte de las extensiones de Chrome, que permiten que el explorador interactúe con otras partes del extremo del usuario, lo que crea varios problemas de seguridad. |

### <a name="secure-sockets-layer-tlsssl"></a>Capa de sockets seguros (TLS/SSL)

| Configuración | Valor predeterminado | Descripción
| ------ | ------ | ------ |
| Versión mínima de TLS | Tls 1.2 mínimo compatible | Si desea usar la TLS 1.1 menos segura, puede presentar una solicitud para hacerlo. |
| Permitir que los usuarios continúen desde la página de advertencia ssl | Deshabilitado | No se recomienda habilitar esta configuración, ya que permite a los usuarios visitar sitios con errores de TSL. |

### <a name="microsoft-defender-smartscreen"></a>SmartScreen de Microsoft Defender

| Configuración | Valor predeterminado | Descripción
| ------ | ------ | ------ |
| Configurar Windows Defender SmartScreen | Habilitado | Habilitado de forma predeterminada para ayudar a proteger a los usuarios. |
| Windows Defender smartscreen solicita sitios | Habilitado | No se recomienda deshabilitar esta configuración, ya que permitiría a los usuarios omitir las advertencias y continuar con sitios potencialmente malintencionados. |
| Impedir la omisión de Windows Defender advertencias de SmartScreen sobre descargas | Habilitado | No se recomienda deshabilitar esta configuración, ya que permitiría a los usuarios omitir advertencias y completar descargas no verificados. |

### <a name="adobe-flash"></a>Adobe Flash

| Configuración | Valor predeterminado | Descripción
| ------ | ------ | ------ |
| Configuración predeterminada de Adobe Flash | Deshabilitado | No se recomienda usar Flash debido a los riesgos de seguridad asociados. <br><br> Si todavía tiene procesos que dependen de Flash, establezca la directiva **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar Flash para los sitios que lo necesiten. Si no puedes mantener una lista de sitios permitidos para usar Flash, presentar una solicitud de cambio para cambiar el valor a **Hacer** clic para reproducir, lo que permite a los usuarios elegir cuándo es adecuado ejecutar Flash. |

### <a name="password-manager"></a>Administrador de contraseñas

| Configuración | Valor predeterminado | Descripción
| ------ | ------ | ------ |
| Habilitar el guardado de contraseñas en el administrador de contraseñas | Deshabilitado | El administrador de contraseñas está deshabilitado de forma predeterminada. Si desea habilitar esta característica, presente una solicitud de soporte técnico y nuestros ingenieros de servicio pueden habilitar la configuración en su entorno. |

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modo internet Explorer en Microsoft Edge

El modo IE en Microsoft Edge facilita el uso de todos los sitios que su organización necesita en un solo explorador. Usa el motor de Chromium integrado para sitios que son compatibles con el Chromium de representación. Microsoft Edge el motor MSHTML trident de Internet Explorer 11 (IE11) para sitios que no son o tienen dependencias de la funcionalidad de IE. [Más información](/DeployEdge/edge-ie-mode)

Microsoft Managed Desktop habilita el modo Internet Explorer para los dispositivos de forma predeterminada.

| Configuración | Valor predeterminado | Descripción
| ------ | ------ | ------ |
| Integración del modo de Internet Explorer | Modo Internet Explorer | De forma predeterminada, los dispositivos están configurados para usar el modo Internet Explorer, pero puedes establecerlos para que abran sitios en una ventana independiente de Internet Explorer 11. Para cambiar este comportamiento, presente una solicitud de soporte técnico. |
| Agregar sitios a la lista Enterprise de sitios de modo de acceso | Ver descripción | Para que los sitios se abran en modo Internet Explorer, debe incluirlos en la [lista Enterprise sitio](/DeployEdge/edge-ie-mode-sitelist). Mantener e implementar la lista Enterprise sitio es su responsabilidad. Para obtener más información, vea [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy). |

### <a name="other-settings"></a>Otras opciones de configuración

| Configuración | Valor predeterminado | Descripción
| ------ | ------ | ------ |
| Habilitar el aislamiento de sitios para cada sitio | Habilitado | Cuando esta directiva está habilitada, los usuarios no pueden optar por el comportamiento predeterminado en el que cada sitio se ejecuta en su propio proceso. |
| Esquemas de autenticación compatibles | NTLM, Negociar | Microsoft Managed Desktop no admite esquemas de autenticación básica o implícita. |
| Importar automáticamente los datos y la configuración de otro explorador en la primera ejecución | Importe automáticamente todos los tipos de datos y la configuración admitidos desde el explorador predeterminado. | Con esta directiva aplicada, la primera experiencia de ejecución omitirá la sección de importación, lo que minimizará la interacción del usuario. Los datos del explorador de versiones anteriores de Microsoft Edge se migrarán siempre silenciosamente en la primera ejecución, independientemente de esta configuración. |

## <a name="settings-you-manage"></a>Configuración administrar

Puede implementar cualquier configuración Microsoft Edge no descrita anteriormente mediante el perfil Plantillas administrativas en Microsoft Intune. Para obtener más información, [vea Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune). Si desea evaluar una directiva que no se incluye actualmente en las plantillas administrativas de Microsoft Edge en Intune, puede usar la configuración personalizada para Windows 10 dispositivos en Intune.

| Configuración | Descripción
| ------ | ------ |
| Habilitar extensiones específicas de Chrome | La plantilla administrativa ofrece una configuración para implementar extensiones de Chrome determinadas con Microsoft Intune. Puede encontrarlo en Configuración del **equipo > Microsoft Edge > extensiones > Permitir que se instalen extensiones específicas**. |
| Instalar extensiones de forma silenciosa | También puede usar la plantilla administrativa para establecer Microsoft Edge para instalar extensiones sin avisar al usuario. Puede encontrarlo en Configuración del equipo > Microsoft Edge > **extensiones > control de las extensiones que se instalan de forma silenciosa**. |
| Microsoft Edge de actualización | Para asegurarse de que Microsoft Edge actualizaciones correctamente, no modifique las Microsoft Edge [de actualización.](/deployedge/microsoft-edge-update-policies) |
| Otras directivas de empresa comunes | Microsoft Edge ofrece muchas otras directivas. Estos son algunos de los más comunes: <ul> <li> [Configurar sitios en la lista Enterprise sitio y el modo IE](/deployedge/edge-ie-mode-sitelist)</li><li> [Configurar la configuración de inicio, página principal y nueva página de pestañas](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)</li> <li> [Configurar configuración de juego de surf](/deployedge/microsoft-edge-policies#allowsurfgame)</li> <li> [Configurar la configuración del servidor proxy](/deployedge/microsoft-edge-policies#proxy-server)</li></ul>
