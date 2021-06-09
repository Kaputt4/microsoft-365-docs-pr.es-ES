---
title: Proteger las carpetas importantes contra ransomware de cifrar los archivos con acceso controlado a carpetas
description: Los archivos de las carpetas predeterminadas se pueden proteger para que no los cambien las aplicaciones malintencionadas. Impedir que el ransomware cifre los archivos.
keywords: acceso controlado a carpetas, windows 10, Windows Defender, ransomware, protect, files, folders
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 7c471dc99a5deafcc60177812f60f1f884b10ee1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845575"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Proteger carpetas importantes con acceso controlado a carpetas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>¿Qué es el acceso controlado a carpetas?

El acceso controlado a carpetas ayuda a proteger los datos valiosos de las amenazas y aplicaciones malintencionadas, como el ransomware. El acceso controlado a carpetas protege los datos comprobando las aplicaciones en una lista de aplicaciones conocidas y de confianza. Compatible con clientes de Windows Server 2019 y Windows 10, el acceso controlado a carpetas se puede desactivar con la aplicación Seguridad de Windows, Microsoft Endpoint Configuration Manager o Intune (para dispositivos administrados). 

> [!NOTE]
> Los motores de scripting no son de confianza y no se les puede permitir el acceso a carpetas protegidas controladas.  Por ejemplo, PowerShell no es de confianza mediante el acceso controlado a carpetas, incluso si permite con indicadores de certificado [e archivo](/microsoft-365/security/defender-endpoint/indicator-certificates). 

El acceso controlado a carpetas funciona mejor con [Microsoft Defender para](microsoft-defender-endpoint.md)endpoint, lo que le ofrece informes detallados sobre los eventos y bloques de acceso controlado a carpetas como parte de los escenarios habituales de investigación de [alertas.](investigate-alerts.md)

> [!TIP]
> Los bloques de acceso a carpetas controladas no generan alertas en la cola [De alertas.](alerts-queue.md) Sin embargo, puedes ver información sobre los bloques de acceso controlados a carpetas en la vista de escala de tiempo del [dispositivo,](investigate-machines.md)mientras usas la búsqueda [avanzada](advanced-hunting-overview.md)o con reglas [de detección personalizadas.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>¿Cómo funciona el acceso controlado a carpetas?

El acceso controlado a carpetas solo permite que las aplicaciones de confianza accedan a carpetas protegidas. Las carpetas protegidas se especifican cuando se configura el acceso controlado a carpetas. Normalmente, las carpetas usadas normalmente, como las que se usan para documentos, imágenes, descargas, entre otras, se incluyen en la lista de carpetas controladas. 

El acceso controlado a carpetas funciona con una lista de aplicaciones de confianza. Las aplicaciones que se incluyen en la lista de software de confianza funcionan según lo esperado. Las aplicaciones que no se incluyen en la lista no pueden realizar cambios en archivos dentro de carpetas protegidas. 

Las aplicaciones se agregan a la lista en función de su prevalencia y reputación. Las aplicaciones que son muy frecuentes en toda la organización y que nunca han mostrado ningún comportamiento que se considere malintencionado se consideran confiables. Esas aplicaciones se agregan a la lista automáticamente.

Las aplicaciones también se pueden agregar manualmente a la lista de confianza mediante Configuration Manager o Intune. Se pueden realizar acciones adicionales, como agregar un indicador [de archivo](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) para una aplicación, desde la consola del Centro de seguridad.

## <a name="why-controlled-folder-access-is-important"></a>Por qué es importante el acceso controlado a carpetas

El acceso controlado a carpetas es especialmente útil para ayudar a proteger los documentos y la información de [ransomware](https://www.microsoft.com/wdsi/threats/ransomware). En un ataque de ransomware, los archivos pueden ser cifrados y retenidos como rehenes. Con el acceso controlado a carpetas, aparece una notificación en el equipo donde una aplicación intentó realizar cambios en un archivo de una carpeta protegida. Puede personalizar [la notificación con los](customize-attack-surface-reduction.md#customize-the-notification) detalles de su empresa y la información de contacto. También puede habilitar las reglas individualmente para personalizar las técnicas que supervisan las características.

Las [carpetas protegidas](#review-controlled-folder-access-events-in-windows-event-viewer) incluyen carpetas comunes del sistema (incluidos los sectores de arranque) y puede [agregar más carpetas.](customize-controlled-folders.md#protect-additional-folders) También puedes permitir [que las aplicaciones](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) les den acceso a las carpetas protegidas.

Puede usar el [modo de auditoría para](audit-windows-defender.md) evaluar cómo el acceso controlado a carpetas afectaría a su organización si estuviera habilitado. También puede visitar el sitio web Windows Defender prueba en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.

El acceso controlado a carpetas se admite en las siguientes versiones de Windows:
- [Windows 10, versión 1709](/windows/whats-new/whats-new-windows-10-version-1709) y versiones posteriores
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Windows carpetas del sistema están protegidas de forma predeterminada

Windows carpetas del sistema están protegidas de forma predeterminada, junto con otras carpetas: 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> Puede configurar carpetas adicionales como protegidas, pero no puede quitar las Windows del sistema que están protegidas de forma predeterminada.

## <a name="requirements-for-controlled-folder-access"></a>Requisitos para el acceso controlado a carpetas

El acceso controlado a carpetas [requiere Antivirus de Microsoft Defender protección en tiempo real.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a>Revisar eventos de acceso controlado a carpetas en el Centro de seguridad de Microsoft Defender

Defender for Endpoint proporciona informes detallados sobre eventos y bloques como parte de sus escenarios de [investigación de alertas.](investigate-alerts.md)

Puede consultar datos de punto de conexión de Microsoft Defender mediante [búsqueda avanzada](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection). Si usa el modo [de auditoría,](audit-windows-defender.md)puede usar la búsqueda avanzada para ver cómo la configuración de acceso controlado a carpetas afectaría al entorno si estuvieran habilitadas. [](advanced-hunting-overview.md)

Consulta de ejemplo:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Revisar los eventos de acceso controlado a carpetas Windows visor de eventos

Puedes revisar el registro Windows eventos para ver los eventos que se crean cuando el acceso controlado a carpetas bloquea (o audita) una aplicación:You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:

1. Descargue el [paquete de evaluación](https://aka.ms/mp7z2w) y extraiga el archivo *cfa-events.xml* a una ubicación de fácil acceso en el dispositivo.
2. Escriba **Visor de eventos** en el menú Inicio para abrir el Windows de eventos.
3. En el panel izquierdo, en **Acciones**, seleccione **Importar vista personalizada...**.
4. Navegue hasta donde ha extraído *cfa-events.xml* y selecciónelo. Como alternativa, [copie el XML directamente](event-views.md).
5. Seleccione **Aceptar**.

En la tabla siguiente se muestran los eventos relacionados con el acceso controlado a carpetas:

|Id. de evento | Descripción |
|:---|:---|
|5007 | Evento cuando se cambia la configuración |
|1124 | Evento de acceso a carpetas controladas auditada | 
|1123 | Evento de acceso controlado a carpetas bloqueadas |

## <a name="view-or-change-the-list-of-protected-folders"></a>Ver o cambiar la lista de carpetas protegidas

Puedes usar la aplicación Seguridad de Windows para ver la lista de carpetas protegidas por el acceso controlado a carpetas. 

1. En el Windows 10, abre la aplicación Seguridad de Windows usuario.
2. Seleccione **Protección antivirus y contra amenazas**.
3. En **Protección contra ransomware,** seleccione **Administrar protección contra ransomware**.
4. Si el acceso controlado a carpetas está desactivado, tendrás que activarlo. Seleccione **carpetas protegidas**.
5. Realice uno de los pasos siguientes:
   - Para agregar una carpeta, seleccione **+ Agregar una carpeta protegida.**
   - Para quitar una carpeta, selecciónelo y, a continuación, **seleccione Quitar**. 

> [!NOTE]
> [Windows las carpetas del](#windows-system-folders-are-protected-by-default) sistema están protegidas de forma predeterminada y no se pueden quitar de la lista.

## <a name="see-also"></a>Consulte también

- [Evaluar acceso controlado a carpetas](evaluate-controlled-folder-access.md)
- [Personalizar el acceso controlado a carpetas](customize-controlled-folders.md)
- [Proteger más carpetas](customize-controlled-folders.md#protect-additional-folders)
