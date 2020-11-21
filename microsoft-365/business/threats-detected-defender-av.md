---
title: Amenazas detectadas por antivirus de Microsoft defender
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
description: Obtén información sobre cómo el antivirus de Microsoft defender protege los dispositivos Windows de amenazas de software, como virus, malware y spyware.
ms.openlocfilehash: e3c8a1071625bba41af5f3cccd50f8484acac18d
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376708"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Amenazas detectadas por antivirus de Microsoft defender

El antivirus de Microsoft defender protege los dispositivos Windows de las amenazas de software, como virus, malware y spyware.

- Los virus suelen propagarse adjuntando su código a otros archivos en el dispositivo o la red y pueden provocar que los programas infectados funcionen incorrectamente.
- El malware incluye archivos malintencionados, aplicaciones y código que pueden causar daños e interrumpir el uso normal de los dispositivos. Además, el malware puede permitir el acceso no autorizado, usar recursos del sistema, robar contraseñas e información de la cuenta, bloquear su equipo y solicitar Ransom y mucho más.
- El spyware recopila datos, como la actividad de navegación web, y envía los datos a servidores remotos.
 
Para proporcionar protección contra amenazas, el antivirus de Microsoft defender usa varios métodos. Estos métodos incluyen protección suministrada en la nube, protección en tiempo real y actualizaciones de protección dedicadas.

- La protección basada en la nube ayuda a proporcionar detección casi instantánea y bloqueo de amenazas nuevas y emergentes.
- El análisis de AlwaysOn usa la supervisión de comportamiento de archivos y procesos y otras técnicas (también conocida como *protección en tiempo real*).
- Las actualizaciones de protección dedicadas se basan en el aprendizaje de la máquina, el análisis humano y automatizado de datos importantes y la investigación en profundidad contra amenazas. 

Para obtener más información sobre malware y antivirus de Microsoft defender, vea los siguientes artículos: 

- [Descripción de malware & otras amenazas](/windows/security/threat-protection/intelligence/understanding-malware)
- [Modo en que Microsoft identifica el malware y las aplicaciones potencialmente no deseadas](/windows/security/threat-protection/intelligence/criteria)
- [Protección de próxima generación en Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>¿Qué ocurre cuando se usa una solución antivirus que no es de Microsoft? 

Antivirus de Microsoft defender forma parte del sistema operativo y se habilita en dispositivos que ejecutan Windows 10. Sin embargo, si usa una solución antivirus que no es de Microsoft y no está usando [Microsoft defender para el punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), el antivirus de Microsoft defender pasa automáticamente al modo deshabilitado.  

En el modo deshabilitado, los usuarios y clientes todavía pueden usar antivirus de Microsoft defender para los análisis programados o bajo demanda para identificar amenazas; sin embargo, el antivirus de Microsoft defender ya no hará lo siguiente:

- usarse como aplicación antivirus predeterminada.
- analice activamente los archivos en busca de amenazas.
- corrija, o resuelva, las amenazas.

Si desinstala la solución antivirus que no es de Microsoft, el antivirus de Microsoft defender entrará automáticamente en modo activo para proteger sus dispositivos Windows de las amenazas.

> [!TIP]
> - Si está usando Microsoft 365, considere la posibilidad de usar antivirus de Microsoft defender como solución antivirus principal. La integración puede proporcionar una mejor protección. Vea [mejor juntos: antivirus de Microsoft defender y Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Asegúrese de mantener actualizado el antivirus de Microsoft defender, incluso si está usando una solución antivirus que no es de Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Qué se debe esperar cuando se detectan amenazas

Cuando se detectan amenazas por parte de antivirus de Microsoft defender, ocurren las siguientes cosas:

- Los usuarios reciben [notificaciones en Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Las detecciones se enumeran en la página de la [aplicación seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) en la página **historial de protección** .  
- Si ha [protegido los dispositivos con Windows 10](secure-win-10-pcs.md) y los ha [inscrito en Intune](/mem/intune/enrollment/windows-enrollment-methods), verá las detecciones de amenazas y la información en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración de 365 de Microsoft</a> en la página **amenazas activas** , a las que puede obtener acceso desde la tarjeta **antivirus de Microsoft defender** en la página **principal** (o desde el panel de navegación, seleccionando amenazas de **salud**  >  **& antivirus**).
    > [!NOTE]
    > La página de la tarjeta **antivirus de Microsoft defender** y las **amenazas activas** se están implementando en fases, por lo que es posible que no tenga acceso inmediato a ellas.

En la mayoría de los casos, los usuarios no tienen que realizar ninguna acción. En cuanto un archivo o programa malintencionado se detecta en un dispositivo, el antivirus de Microsoft defender lo bloquea e impide que se ejecute. Además, se agregan amenazas recientemente detectadas al motor antivirus y antimalware para que también se protejan otros dispositivos y usuarios.  

Si hay una acción que debe realizar un usuario, como aprobar la eliminación de un archivo malintencionado, verá que en la notificación que reciben. Para obtener más información sobre las acciones que realiza el antivirus de Microsoft defender en nombre de un usuario o acciones que los usuarios pueden necesitar realizar, consulte [historial de protección](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Para obtener información sobre cómo administrar las detecciones de amenazas como administrador o profesional de ti, consulte [revisión de amenazas detectadas y emprender acciones](review-threats-take-action.md).

Para obtener más información acerca de las distintas amenazas, visite el <a href="https://www.microsoft.com/wdsi/threats" target="_blank">sitio de amenazas de inteligencia en seguridad de Microsoft</a>, donde puede realizar las siguientes acciones: 

- Ver información actual sobre amenazas principales.
- Ver las amenazas más recientes para una región específica.
- Busque en la enciclopedia de amenazas detalles sobre una amenaza específica.

## <a name="related-content"></a>Contenido relacionado

[Proteger dispositivos Windows 10](secure-windows-10-devices.md) (artículo) \
[Evaluar antivirus de Microsoft defender](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artículo) \
[Cómo activar la protección antivirus en tiempo real y entregada en la nube](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (artículo) \
[Cómo activar y usar antivirus de Microsoft defender desde la aplicación de seguridad de Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artículo) \
[Cómo activar antivirus de Microsoft defender mediante la Directiva de grupo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artículo) \
[Cómo actualizar sus definiciones de antivirus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artículo) \
[Cómo enviar malware y no malware a Microsoft para su análisis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artículo)