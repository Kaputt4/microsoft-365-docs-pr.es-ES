---
title: Amenazas detectadas por Antivirus de Microsoft Defender
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Obtenga información sobre cómo Antivirus de Microsoft Defender protege los dispositivos Windows frente a amenazas de software, como virus, malware y spyware.
ms.openlocfilehash: 47f6af2b91eed8096a685f8d3281f16fdc677331
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65466314"
---
# <a name="overview-of-threat-protection-by-microsoft-defender-antivirus"></a>Introducción a la protección contra amenazas por Antivirus de Microsoft Defender

Antivirus de Microsoft Defender protege los dispositivos Windows frente a amenazas de software, como virus, malware y spyware.

- Los virus normalmente se propagan adjuntando su código a otros archivos en el dispositivo o la red y pueden hacer que los programas infectados funcionen incorrectamente.
- El malware incluye archivos malintencionados, aplicaciones y código que pueden causar daños e interrumpir el uso normal de los dispositivos. Además, el malware puede permitir el acceso no autorizado, usar recursos del sistema, robar contraseñas e información de cuenta, bloquear su equipo y pedir rescate, y mucho más.
- El spyware recopila datos, como la actividad de exploración web, y envía los datos a servidores remotos.
 
Para proporcionar protección contra amenazas, Antivirus de Microsoft Defender usa varios métodos. Estos métodos incluyen la protección entregada en la nube, la protección en tiempo real y las actualizaciones de protección dedicadas.

- La protección proporcionada en la nube ayuda a proporcionar detección y bloqueo casi instantáneos de amenazas nuevas y emergentes.
- El examen siempre activo usa la supervisión del comportamiento de archivos y procesos y otras técnicas (también conocidas como *protección en tiempo real*).
- Las actualizaciones de protección dedicadas se basan en el aprendizaje automático, el análisis de macrodatos humanos y automatizados, y la investigación en profundidad de la resistencia a amenazas. 

Para obtener más información sobre malware y Antivirus de Microsoft Defender, consulte los artículos siguientes: 

- [Descripción del malware & otras amenazas](/windows/security/threat-protection/intelligence/understanding-malware)
- [Cómo Microsoft identifica el malware y las aplicaciones potencialmente no deseadas](/windows/security/threat-protection/intelligence/criteria)
- [Protección de próxima generación en Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>¿Qué ocurre cuando se usa una solución antivirus que no es de Microsoft? 

Antivirus de Microsoft Defender forma parte del sistema operativo y está habilitado en los dispositivos que ejecutan Windows 10. Sin embargo, si usa una solución antivirus que no es de Microsoft y no usa [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), Antivirus de Microsoft Defender pasa automáticamente al modo deshabilitado.  

Cuando se encuentra en modo deshabilitado, los usuarios y los clientes pueden seguir usando Antivirus de Microsoft Defender para los exámenes programados o a petición para identificar amenazas; sin embargo, Antivirus de Microsoft Defender ya no:

- se usará como la aplicación antivirus predeterminada.
- examinar activamente los archivos en busca de amenazas.
- corregir o resolver amenazas.

Si desinstala la solución antivirus que no es de Microsoft, Antivirus de Microsoft Defender pasará automáticamente al modo activo para proteger los dispositivos Windows frente a amenazas.

> [!TIP]
> - Si usa Microsoft 365, considere la posibilidad de usar Antivirus de Microsoft Defender como solución antivirus principal. La integración puede proporcionar una mejor protección. Vea [Mejor juntos: Antivirus de Microsoft Defender y Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Asegúrese de mantener Antivirus de Microsoft Defender actualizado, incluso si usa una solución antivirus que no sea de Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Qué esperar cuando se detectan amenazas

Cuando Antivirus de Microsoft Defender detecta amenazas, sucede lo siguiente:

- Los usuarios reciben [notificaciones en Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Las detecciones se muestran en la [aplicación Seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) de la página **Historial de protección**.  
- Si ha protegido los [dispositivos Windows 10](../setup/secure-win-10-pcs.md) y [los ha inscrito en Intune](/mem/intune/enrollment/windows-enrollment-methods) y su organización tiene 800 o menos dispositivos inscritos, verá detecciones e información sobre amenazas en la <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> de la página **Amenazas y antivirus**, a la que puede acceder desde el **Antivirus de Microsoft Defender** tarjeta en la página **Inicio** (o en el panel de navegación seleccionando **HealthThreats** >  & antivirus).

    Si su organización tiene más de 800 dispositivos inscritos en Intune, se le pedirá que vea las detecciones de amenazas y la información de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) en lugar de desde la página **Amenazas y antivirus**.
 
    > [!NOTE]
    > La tarjeta **Antivirus de Microsoft Defender** y **la página amenazas y antivirus** se están implementando por fases, por lo que es posible que no tenga acceso inmediato a ellas.

En la mayoría de los casos, los usuarios no necesitan realizar ninguna acción adicional. En cuanto se detecta un archivo o programa malintencionado en un dispositivo, Antivirus de Microsoft Defender lo bloquea e impide que se ejecute. Además, las amenazas recién detectadas se agregan al motor antivirus y antimalware para que otros dispositivos y usuarios también estén protegidos.  

Si hay una acción que un usuario necesita realizar, como aprobar la eliminación de un archivo malintencionado, lo verá en la notificación que recibe. Para obtener más información sobre las acciones que Antivirus de Microsoft Defender realiza en nombre de un usuario o las acciones que los usuarios pueden necesitar realizar, consulte [Historial de protección](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Para obtener información sobre cómo administrar las detecciones de amenazas como profesional o administrador de TI, consulte [Revisión de amenazas detectadas y toma medidas](review-threats-take-action.md).

Para obtener más información sobre las diferentes amenazas, visite el <a href="https://www.microsoft.com/wdsi/threats" target="_blank">sitio Inteligencia de seguridad de Microsoft Amenazas</a>, donde puede realizar las siguientes acciones: 

- Vea la información actual sobre las principales amenazas.
- Vea las amenazas más recientes para una región específica.
- Busque en la enciclopedia de amenazas detalles sobre una amenaza específica.

## <a name="related-content"></a>Contenido relacionado

[Protección de dispositivos Windows](/misc/m365bp-secure-windows-devices) (artículo)\
[Evaluar Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artículo)\
[Cómo activar la protección antivirus en tiempo real y entregada en la nube](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (artículo)\
[Cómo activar y usar Antivirus de Microsoft Defender desde la aplicación Seguridad de Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artículo)\
[Cómo activar Antivirus de Microsoft Defender mediante directiva de grupo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artículo)\
[Actualización de las definiciones de antivirus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artículo)\
[Cómo enviar malware y no malware a Microsoft para su análisis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artículo)