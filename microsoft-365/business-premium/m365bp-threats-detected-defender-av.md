---
title: Amenazas detectadas por Antivirus de Microsoft Defender
f1.keywords: CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.collection:
- m365-security
- tier1
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo Microsoft Defender Antivirus protege los dispositivos Windows frente a amenazas de software, como virus, malware y spyware.
ms.openlocfilehash: 35a36a74645477afc9e33da72e6c5e6d9ce17dbe
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097915"
---
# <a name="overview-of-threat-protection-by-microsoft-defender-antivirus"></a>Introducción a la protección contra amenazas por Microsoft Defender Antivirus

Microsoft Defender Antivirus protege los dispositivos Windows frente a amenazas de software, como virus, malware y spyware.

- Los virus normalmente se propagan adjuntando su código a otros archivos en el dispositivo o la red y pueden hacer que los programas infectados funcionen incorrectamente.
- El malware incluye archivos malintencionados, aplicaciones y código que pueden causar daños e interrumpir el uso normal de los dispositivos. Además, el malware puede permitir el acceso no autorizado, usar recursos del sistema, robar contraseñas e información de cuenta, bloquear su equipo y pedir rescate, y mucho más.
- El spyware recopila datos, como la actividad de exploración web, y envía los datos a servidores remotos.
 
Para proporcionar protección contra amenazas, Microsoft Defender Antivirus usa varios métodos. Estos métodos incluyen la protección entregada en la nube, la protección en tiempo real y las actualizaciones de protección dedicadas.

- La protección proporcionada en la nube ayuda a proporcionar detección y bloqueo casi instantáneos de amenazas nuevas y emergentes.
- El examen siempre activo usa la supervisión del comportamiento de archivos y procesos y otras técnicas (también conocidas como *protección en tiempo real*).
- Las actualizaciones de protección dedicadas se basan en el aprendizaje automático, el análisis de macrodatos humanos y automatizados, y la investigación en profundidad de la resistencia a amenazas. 

Para obtener más información sobre el malware y Microsoft Defender Antivirus, consulte los artículos siguientes: 

- [Descripción del malware & otras amenazas](/windows/security/threat-protection/intelligence/understanding-malware)
- [Cómo Microsoft identifica el malware y las aplicaciones potencialmente no deseadas](/windows/security/threat-protection/intelligence/criteria)
- [Protección de próxima generación en Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>¿Qué ocurre cuando se usa una solución antivirus que no es de Microsoft? 

Microsoft Defender Antivirus forma parte del sistema operativo y está habilitado en dispositivos que ejecutan Windows 10. Sin embargo, si usa una solución antivirus que no es de Microsoft y no usa [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), Microsoft Defender Antivirus pasa automáticamente al modo deshabilitado.  

Cuando se encuentra en modo deshabilitado, los usuarios y los clientes pueden seguir usando Microsoft Defender Antivirus para los exámenes programados o a petición para identificar amenazas; sin embargo, Microsoft Defender Antivirus dejará de:

- se usará como la aplicación antivirus predeterminada.
- examinar activamente los archivos en busca de amenazas.
- corregir o resolver amenazas.

Si desinstala la solución antivirus que no es de Microsoft, Microsoft Defender Antivirus entrará automáticamente en modo activo para proteger los dispositivos Windows frente a amenazas.

> [!TIP]
> - Si usa Microsoft 365, considere la posibilidad de usar Microsoft Defender Antivirus como solución antivirus principal. La integración puede proporcionar una mejor protección. Consulte [Mejor juntos: Microsoft Defender Antivirus y Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Asegúrese de mantener Microsoft Defender Antivirus actualizado, incluso si usa una solución antivirus que no sea de Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Qué esperar cuando se detectan amenazas

Cuando Microsoft Defender Antivirus detecta amenazas, sucede lo siguiente:

- Los usuarios reciben [notificaciones en Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Las detecciones se muestran en la [aplicación Seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) de la página **Historial de protección**.  
- Si ha protegido los [dispositivos Windows 10](../admin/setup/secure-win-10-pcs.md) y [los ha inscrito en Intune](/mem/intune/enrollment/windows-enrollment-methods) y su organización tiene 800 o menos dispositivos inscritos, verá detecciones e información sobre amenazas en la <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> de la página **Amenazas y antivirus**, a la que puede acceder desde el **Microsoft Defender tarjeta Antivirus** en la página **Inicio** (o en el panel de navegación **seleccionando** Amenazas de  >  estado **& antivirus**).

    Si su organización tiene más de 800 dispositivos inscritos en Intune, se le pedirá que vea las detecciones de amenazas y la información de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) en lugar de desde la página **Amenazas y antivirus**.
 
    > [!NOTE]
    > La **tarjeta Microsoft Defender Antivirus** y **la página De amenazas y antivirus** se están implementando en fases, por lo que es posible que no tenga acceso inmediato a ellas.

En la mayoría de los casos, los usuarios no necesitan realizar ninguna acción adicional. En cuanto se detecta un archivo o programa malintencionado en un dispositivo, Microsoft Defender Antivirus lo bloquea e impide que se ejecute. Además, las amenazas recién detectadas se agregan al motor antivirus y antimalware para que otros dispositivos y usuarios también estén protegidos.  

Si hay una acción que un usuario necesita realizar, como aprobar la eliminación de un archivo malintencionado, lo verá en la notificación que recibe. Para obtener más información sobre las acciones que Microsoft Defender Antivirus realiza en nombre de un usuario o las acciones que los usuarios pueden necesitar realizar, consulte [Historial de protección](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Para obtener información sobre cómo administrar las detecciones de amenazas como profesional o administrador de TI, consulte [Revisión de amenazas detectadas y toma medidas](m365bp-review-threats-take-action.md).

Para obtener más información sobre las diferentes amenazas, visite el <a href="https://www.microsoft.com/wdsi/threats" target="_blank">sitio Inteligencia de seguridad de Microsoft Amenazas</a>, donde puede realizar las siguientes acciones: 

- Vea la información actual sobre las principales amenazas.
- Vea las amenazas más recientes para una región específica.
- Busque en la enciclopedia de amenazas detalles sobre una amenaza específica.

## <a name="related-content"></a>Contenido relacionado

[Protección de dispositivos Windows](/misc/m365bp-secure-windows-devices) (artículo)\
[Evaluar Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artículo)\
[Cómo activar la protección antivirus en tiempo real y entregada en la nube](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (artículo)\
[Cómo activar y usar Microsoft Defender Antivirus desde la aplicación Seguridad de Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artículo)\
[Cómo activar Microsoft Defender Antivirus mediante directiva de grupo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artículo)\
[Actualización de las definiciones de antivirus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artículo)\
[Cómo enviar malware y no malware a Microsoft para su análisis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artículo)