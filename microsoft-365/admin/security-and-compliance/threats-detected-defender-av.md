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
description: Obtenga información sobre Antivirus de Microsoft Defender protege los dispositivos Windows de amenazas de software, como virus, malware y spyware.
ms.openlocfilehash: 4343726b1a0856616eaa8291adc24633aaad5eb0
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186785"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Amenazas detectadas por Antivirus de Microsoft Defender

Antivirus de Microsoft Defender protege los dispositivos Windows de amenazas de software, como virus, malware y spyware.

- Normalmente, los virus se propagan adjuntando su código a otros archivos del dispositivo o la red y pueden provocar que los programas infectados funcionen incorrectamente.
- El malware incluye archivos malintencionados, aplicaciones y código que pueden causar daños e interrumpir el uso normal de dispositivos. Además, el malware puede permitir el acceso no autorizado, usar recursos del sistema, robar contraseñas e información de cuenta, bloquearle fuera del equipo y pedir rescate, y mucho más.
- Spyware recopila datos, como la actividad de exploración web, y envía los datos a servidores remotos.
 
Para proporcionar protección contra amenazas, Antivirus de Microsoft Defender varios métodos. Estos métodos incluyen protección entregada en la nube, protección en tiempo real y actualizaciones de protección dedicadas.

- La protección entregada en la nube ayuda a proporcionar detección casi instantánea y bloqueo de amenazas nuevas y emergentes.
- La exploración siempre activa usa la supervisión del comportamiento de procesos y archivos y otras técnicas (también conocidas como protección *en tiempo real).*
- Las actualizaciones de protección dedicadas se basan en el aprendizaje automático, el análisis de big-data humano y automatizado y la investigación detallada de resistencia a amenazas. 

Para obtener más información sobre malware y Antivirus de Microsoft Defender, consulte los siguientes artículos: 

- [Descripción de malware & otras amenazas](/windows/security/threat-protection/intelligence/understanding-malware)
- [Cómo Identifica Microsoft malware y aplicaciones potencialmente no deseadas](/windows/security/threat-protection/intelligence/criteria)
- [Protección de última generación en Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>¿Qué sucede cuando se usa una solución antivirus que no es microsoft? 

Antivirus de Microsoft Defender forma parte del sistema operativo y está habilitado en dispositivos que ejecutan Windows 10. Sin embargo, si usa una solución antivirus que no es de Microsoft y no usa [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)para endpoint, Antivirus de Microsoft Defender automáticamente pasa al modo deshabilitado.  

Cuando se encuentra en modo deshabilitado, los usuarios y los clientes aún pueden usar Antivirus de Microsoft Defender para exámenes programados o a petición para identificar amenazas; sin embargo, Antivirus de Microsoft Defender ya no:

- se usará como la aplicación antivirus predeterminada.
- examinar activamente los archivos en busca de amenazas.
- corregir o resolver amenazas.

Si desinstala la solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender pasará automáticamente al modo activo para proteger los dispositivos Windows de amenazas.

> [!TIP]
> - Si usas Microsoft 365, considera la posibilidad de usar Antivirus de Microsoft Defender como la solución antivirus principal. La integración puede proporcionar una mejor protección. Vea [Mejor juntos: Antivirus de Microsoft Defender y Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Asegúrate de mantener la Antivirus de Microsoft Defender actualizada, incluso si estás usando una solución antivirus que no sea de Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Qué esperar cuando se detectan amenazas

Cuando se detectan amenazas Antivirus de Microsoft Defender, suceden las siguientes cosas:

- Los usuarios [reciben notificaciones en Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Las detecciones se enumeran en [la Seguridad de Windows en](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) la página Historial **de** protección.  
- Si ha protegido los dispositivos [de Windows 10](../setup/secure-win-10-pcs.md) y los inscribió en [Intune](/mem/intune/enrollment/windows-enrollment-methods)y su organización tiene 800 o menos dispositivos inscritos, verá detecciones de amenazas e información en el  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> en la página Amenazas y **antivirus,** **a** la que puede acceder desde la tarjeta Antivirus de Microsoft Defender en la página principal (o desde el panel de navegación seleccionando Amenazas de estado  >  **& antivirus).**

    Si su organización tiene más de 800 dispositivos inscritos en Intune, se le pedirá que vea las detecciones de amenazas y los conocimientos de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) en lugar de desde la página Amenazas y **antivirus.**
 
    > [!NOTE]
    > La **Antivirus de Microsoft Defender** y la página Amenazas y **antivirus** se están implantando en fases, por lo que es posible que no tenga acceso inmediato a ellas.

En la mayoría de los casos, los usuarios no necesitan realizar ninguna acción adicional. Tan pronto como se detecte un archivo o programa malintencionado en un dispositivo, Antivirus de Microsoft Defender lo bloquea e impide que se ejecute. Además, las amenazas detectadas recientemente se agregan al motor antivirus y antimalware para que otros dispositivos y usuarios también estén protegidos.  

Si hay una acción que un usuario necesita realizar, como aprobar la eliminación de un archivo malintencionado, lo verá en la notificación que recibe. Para obtener más información sobre las acciones que Antivirus de Microsoft Defender en nombre de un usuario o las acciones que los usuarios pueden necesitar realizar, consulte [Historial de protección](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Para obtener información sobre cómo administrar las detecciones de amenazas como profesional o administrador de TI, vea Revisar las amenazas detectadas [y tomar medidas.](review-threats-take-action.md)

Para obtener más información acerca de las diferentes amenazas, visite <a href="https://www.microsoft.com/wdsi/threats" target="_blank">el sitio Inteligencia de seguridad de Microsoft amenazas,</a>donde puede realizar las siguientes acciones: 

- Ver información actual sobre las principales amenazas.
- Ver las amenazas más recientes para una región específica.
- Busque en la enciclopedia de amenazas detalles sobre una amenaza específica.

## <a name="related-content"></a>Contenido relacionado

[Dispositivos Windows 10 seguros](/misc/secure-windows-10-devices.md) (artículo)\
[Evaluar Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artículo)\
[Cómo activar la protección antivirus en tiempo real y en](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) la nube (artículo)\
[Cómo activar y usar Antivirus de Microsoft Defender desde la aplicación Seguridad de Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artículo)\
[Cómo activar el Antivirus de Microsoft Defender mediante la directiva de grupo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artículo)\
[Cómo actualizar las definiciones de antivirus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artículo)\
[Cómo enviar malware y no malware a Microsoft para su análisis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artículo)
