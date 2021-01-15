---
title: Amenazas detectadas por Antivirus de Microsoft Defender
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Obtén información sobre cómo Antivirus de Microsoft Defender protege los dispositivos Windows contra amenazas de software, como virus, malware y spyware.
ms.openlocfilehash: 1653aef6967cdf76e6e19acda158fb29758280a8
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870904"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Amenazas detectadas por Antivirus de Microsoft Defender

Antivirus de Microsoft Defender protege los dispositivos Windows contra amenazas de software, como virus, malware y spyware.

- Normalmente, los virus se propagan adjuntando su código a otros archivos de su dispositivo o red y pueden hacer que los programas infectados funcionen incorrectamente.
- El malware incluye archivos malintencionados, aplicaciones y código que pueden causar daños y alterar el uso normal de los dispositivos. Además, el malware puede permitir el acceso no autorizado, usar recursos del sistema, robar contraseñas e información de la cuenta, bloquear el equipo y pedir un rescate, etc.
- Spyware recopila datos, como la actividad de exploración web, y envía los datos a servidores remotos.
 
Para proporcionar protección contra amenazas, Antivirus de Microsoft Defender usa varios métodos. Estos métodos incluyen la protección de entrega en la nube, la protección en tiempo real y las actualizaciones de protección dedicadas.

- La protección de entrega en la nube ayuda a proporcionar detección casi instantánea y bloqueo de amenazas nuevas y emergentes.
- La detección siempre activa usa la supervisión del comportamiento de los archivos y los procesos, así como otras técnicas (también conocidas como protección *en tiempo real).*
- Las actualizaciones de protección dedicadas se basan en el aprendizaje automático, el análisis de big-data humano y automatizado y la investigación detallada de la resistencia a amenazas. 

Para obtener más información sobre malware y Antivirus de Microsoft Defender, consulte los siguientes artículos: 

- [Descripción del malware & otras amenazas](/windows/security/threat-protection/intelligence/understanding-malware)
- [Cómo Microsoft identifica el malware y las aplicaciones potencialmente no deseadas](/windows/security/threat-protection/intelligence/criteria)
- [Protección de próxima generación en Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>¿Qué sucede cuando se usa una solución antivirus que no es de Microsoft? 

Antivirus de Microsoft Defender forma parte del sistema operativo y está habilitado en dispositivos que ejecutan Windows 10. Sin embargo, si usa una solución antivirus que no es de Microsoft y no usa [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)para Endpoint, antivirus de Microsoft Defender pasa automáticamente al modo deshabilitado.  

Cuando se encuentra en modo deshabilitado, los usuarios y clientes aún pueden usar antivirus de Microsoft Defender para exámenes programados o a petición para identificar amenazas; sin embargo, Antivirus de Microsoft Defender ya no:

- se usa como la aplicación antivirus predeterminada.
- examinar activamente los archivos en busca de amenazas.
- corregir o resolver las amenazas.

Si desinstalas la solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender pasará automáticamente al modo activo para proteger los dispositivos Windows de las amenazas.

> [!TIP]
> - Si usa Microsoft 365, considere la posibilidad de usar Antivirus de Microsoft Defender como solución antivirus principal. La integración puede proporcionar una mejor protección. Vea [Mejor juntos: Antivirus de Microsoft Defender y Office 365.](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)
> - Asegúrese de mantener antivirus de Microsoft Defender actualizado, incluso si usa una solución antivirus que no sea de Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Qué esperar cuando se detectan amenazas

Cuando antivirus de Microsoft Defender detecta amenazas, sucede lo siguiente:

- Los usuarios [reciben notificaciones en Windows.](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e) 
- Las detecciones se enumeran en la aplicación [Seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) en la página Historial **de** protección.  
- Si ha protegido sus dispositivos [Windows 10](secure-win-10-pcs.md) y los inscribió en [Intune](/mem/intune/enrollment/windows-enrollment-methods)y su organización tiene 800 dispositivos o menos inscritos, verá detecciones de amenazas e información en el  Centro de administración de Microsoft  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365</a> en la página Amenazas y **antivirus,** a la que puede acceder desde la tarjeta Antivirus de **Microsoft Defender** en la página principal (o desde el panel de navegación seleccionando Amenazas de estado  >  **& antivirus).**

    Si tu organización tiene más de 800 dispositivos inscritos en Intune, se te pedirá que veas las detecciones de amenazas y la información de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) en lugar de desde la página Amenazas y **antivirus.**
 
    > [!NOTE]
    > La **tarjeta antivirus de Microsoft Defender** y la página amenazas y **antivirus** se están implantando en fases, por lo que es posible que no tenga acceso inmediato a ellas.

En la mayoría de los casos, los usuarios no necesitan realizar ninguna acción adicional. En cuanto se detecta un archivo o programa malintencionado en un dispositivo, Antivirus de Microsoft Defender lo bloquea y evita que se ejecute. Además, las amenazas detectadas recientemente se agregan al motor antivirus y antimalware para que también estén protegidos otros dispositivos y usuarios.  

Si hay una acción que un usuario necesita realizar, como aprobar la eliminación de un archivo malintencionado, lo verá en la notificación que recibe. Para obtener más información sobre las acciones que antivirus de Microsoft Defender realiza en nombre de un usuario o las acciones que los usuarios pueden necesitar realizar, consulte [Historial de protección.](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708) Para obtener información sobre cómo administrar las detecciones de amenazas como profesional o administrador de TI, consulte Revisar las amenazas detectadas [y tomar medidas.](review-threats-take-action.md)

Para obtener más información sobre las diferentes amenazas, visite el sitio de amenazas de inteligencia de seguridad de <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft,</a>donde puede realizar las siguientes acciones: 

- Ver la información actual sobre las amenazas principales.
- Ver las amenazas más recientes para una región específica.
- Busque en lacyclopedia de amenazas detalles sobre una amenaza específica.

## <a name="related-content"></a>Contenido relacionado

[Proteger dispositivos Windows 10](secure-windows-10-devices.md) (artículo)\
[Evaluar antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artículo)\
[Cómo activar la protección antivirus en tiempo real y de](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) entrega en la nube (artículo)\
[Cómo activar y usar el Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) de Microsoft Defender desde la aplicación Seguridad de Windows (artículo)\
[Cómo activar antivirus de Microsoft Defender mediante la directiva de grupo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artículo)\
[Cómo actualizar las definiciones de antivirus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artículo)\
[Cómo enviar malware y no malware a Microsoft para su análisis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artículo)