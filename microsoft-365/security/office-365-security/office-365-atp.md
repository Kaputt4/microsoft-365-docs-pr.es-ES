---
title: Protección contra amenazas avanzada de Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: La Protección contra amenazas avanzada de Office 365 incluye datos adjuntos seguros, vínculos seguros, herramientas avanzadas contra la suplantación de identidad, herramientas de creación de informes y funciones de inteligencia de amenazas.
ms.openlocfilehash: d8ac32436a0b825e6e649dd7a23e73cad9a17480
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202226"
---
# <a name="office-365-advanced-threat-protection-atp"></a>Protección contra amenazas avanzada de Office 365 (ATP)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen la [Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Si utiliza Outlook.com, Microsoft 365 Familia o Microsoft 365 Personal, y está buscando información sobre los vínculos seguros o los datos adjuntos seguros en Outlook, consulte [Seguridad avanzada de Outlook.com para suscriptores de Microsoft 365](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

La Protección contra amenazas avanzada de Office 365 (ATP) protege su organización contra las amenazas malintencionadas ocultas en mensajes de correo electrónico, vínculos (direcciones URL) y herramientas de colaboración. ATP incluye:

- **[Directivas de protección contra amenazas](#configure-atp-policies)**: defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización.

- **[Informes](#view-office-365-atp-reports)**: vea informes en tiempo real para supervisar el rendimiento de ATP en la organización.

- **[Investigación de amenazas y funcionalidades de respuesta](#use-threat-investigation-and-response-capabilities)**: use las herramientas más avanzadas para investigar, entender, simular y evitar las amenazas.

- **[Investigación automatizada y funcionalidades de respuesta](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**: ahorre tiempo y esfuerzo al investigar y mitigar las amenazas.

## <a name="getting-started"></a>Introducción

Si no está familiarizado con la Protección contra amenazas avanzada de Office 365 o prefiere aprender mediante la *práctica*, puede que le convenga analizar por partes la configuración inicial de ATP, investigar y consultar informes utilizando este artículo como referencia. Aquí se muestran fragmentos previos de configuración de manera lógica:

- Configure todo con "*anti*" en el nombre.
    - antimalware
    - anti-phishing
    - anti-spam (protección contra correo electrónico no deseado)
- Configure todo con "*seguro*" en el nombre.
    - vínculos seguros
    - archivos adjuntos seguros
- Defender las cargas de trabajo (ej. SharePoint Online, OneDrive y Teams) 
- Proteger con la purga automática

Para aprender con la práctica, [haga clic en este vínculo](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true). 

> [!NOTE]
> ATP ofrece dos tipos de plan diferentes. Si tiene "Detecciones en tiempo real", tiene el **Plan 1** y, si tiene el Explorador de amenazas, tiene el **Plan 2**. El plan que tenga influirá en las herramientas que pueda ver, de modo que asegúrese de saber cuál es su plan mientras aprende.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP Plan 1 y Plan 2

La siguiente tabla es un resumen de lo que se incluye en cada plan.

****

|Plan 1 de ATP de Office 365|Plan 2 de ATP de Office 365|
|---|---|
|<br/>Funcionalidades de configuración, protección y detección: <ul><li>[Archivos adjuntos seguros](atp-safe-attachments.md)</li><li>[Vínculos seguros](atp-safe-links.md)</li><li>[ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Protección contra phishing de ATP](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Detecciones en tiempo real](threat-explorer.md)</li></ul>|Funcionalidades del plan 1 de ATP de Office 365<br/>--- además ---<br/>Funcionalidades de automatización, investigación, corrección y educación:</li><li>[Rastreadores de amenazas](threat-trackers.md)</li><li>[Explorador de amenazas](threat-explorer.md)</li><li>[Investigación y respuesta automatizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Simulador de ataque](attack-simulator.md)</li></ul>|
|

- El plan 2 de ATP de Office 365 está incluido en Office 365 E5, Office 365 A5, Seguridad de Microsoft 365 E5 y en Microsoft 365 E5.

- El plan 1 de ATP de Office 365 está incluido en Microsoft 365 Empresa Premium.

- El Plan 1 de ATP de Office 365 y el Plan 2 de ATP de Office 365 están disponibles como complementos para determinadas suscripciones. Para obtener más información, consulte [Disponibilidad de características en los planes de ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- La característica [Documentos seguros](safe-docs.md) solo está disponible para los usuarios con las licencias de Microsoft 365 E5 o Seguridad de Microsoft 365 E5 (no se incluye en los planes de ATP de Office 365).

- Si su suscripción actual no incluye el ATP de Office 365, [póngase en contacto con ventas para iniciar una prueba](https://go.microsoft.com/fwlink/p/?LinkId=518644) y ver cómo ATP puede funcionar para su organización.

## <a name="configure-atp-policies"></a>Configurar directivas ATP

Con ATP de Office 365, el equipo de seguridad de su organización puede configurar la protección definiendo directivas en el Centro de seguridad y cumplimiento (vaya a [https://protection.office.com](https://protection.office.com) > **Administración de amenazas** > **Directiva**).

> [!TIP]
> Para ver una lista de directivas para definir rápidamente, vea [Protegerse ante amenazas](protect-against-threats.md).

## <a name="advanced-threat-protection-policies"></a>Directivas de la Protección contra amenazas avanzada

Las directivas definidas por la organización determinan el comportamiento y el nivel de protección para las amenazas predefinidas. Las opciones de directivas son muy flexibles. Por ejemplo, el equipo de seguridad de su organización puede establecer protección contra amenazas específica para el nivel de usuario, organización, destinatario y dominio. Es importante revisar las directivas de forma periódica, ya que a diario surgen nuevas amenazas y desafíos.

- **[Archivos adjuntos seguros ATP](atp-safe-attachments.md)**: Proporciona protección de día cero para proteger su sistema de mensajería, comprobando si los archivos adjuntos del correo electrónico contienen contenido malicioso. Dirige todos los mensajes y datos adjuntos que no tienen una firma de virus o malware a un entorno especial y, a continuación, utiliza técnicas de aprendizaje automático y análisis para detectar fines malintencionados. Si no se encuentra ninguna actividad sospechosa, el mensaje se reenvía al buzón. Para obtener más información, consulte [Configurar directivas de datos adjuntos seguros de ATP de Office 365](set-up-atp-safe-attachments-policies.md).

- **[Vínculos seguros de ATP](atp-safe-links.md)**: Proporciona verificación del tiempo de clic de las URL, por ejemplo, en mensajes de correo electrónico y archivos de Office. La protección es continua y se aplica en todo su entorno de mensajería y Office. Los vínculos se analizan en cada clic: los vínculos seguros siguen siendo accesibles y los vínculos maliciosos se bloquean dinámicamente. Para obtener más información, consulte [Configurar directivas de vínculos seguros de ATP de Office 365](set-up-atp-safe-links-policies.md).

- **[ATP para los equipos de SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)**: protege su organización cuando los usuarios colaboran y comparten archivos, identificando y bloqueando archivos maliciosos en sitios de equipo y bibliotecas de documentos. Para obtener más información, consulte [Activar ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

- **[Protección anti phishing ATP](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**: detecta los intentos de suplantar la identidad de sus usuarios y dominios internos o personalizados. Aplica modelos de aprendizaje automático y algoritmos avanzados de detección de suplantación para evitar ataques de suplantación de identidad. Para obtener más información, consulte [Configuración de las directivas ATP contra suplantación de identidad en Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Ver informes de ATP de Office 365

ATP de Office 365 incluye un [panel de informes](view-reports-for-atp.md) avanzado para supervisar el rendimiento de ATP. Puede acceder a él en **Informes** > **Panel** en el Centro de seguridad y cumplimiento.

Los informes se actualizan en tiempo real y proporcionan los detalles más recientes. Estos informes también proporcionan recomendaciones y le avisan de amenazas inminentes. Los informes predefinidos incluyen:

- [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)

- [Informe de estado de protección contra amenazas](view-reports-for-atp.md#threat-protection-status-report)

- [Informe de tipos de archivos de Protección contra amenazas avanzada](view-reports-for-atp.md#advanced-threat-protection-file-types-report)

- [Informe de eliminación de mensajes de Protección contra amenazas avanzada](view-reports-for-atp.md#advanced-threat-protection-message-disposition-report)

- ... y muchas más.

## <a name="use-threat-investigation-and-response-capabilities"></a>Usar las funciones de investigación y respuesta de amenazas

Office 365 ATP Plan 2 incluye las mejores [herramientas de investigación y respuesta de amenazas](office-365-ti.md) que permiten que el equipo de seguridad de su organización anticipe, entienda y evite ataques malintencionados.

- **[Los rastreadores de amenazas](threat-trackers.md)** proporcionar la información más reciente sobre los problemas de ciberseguridad existentes. Por ejemplo, puede ver información sobre el malware más reciente y tomar medidas antes de que se convierta en una amenaza real para su organización. Entre los rastreadores disponibles se incluyen [Rastreadores destacados](threat-trackers.md#noteworthy-trackers), [Rastreadores en tendencia](threat-trackers.md#trending-trackers), [Consultas rastreadas](threat-trackers.md#tracked-queries) y [Consultas guardadas](threat-trackers.md#saved-queries).

- **[Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)** (también conocido como Explorador) es un informe en tiempo real que le permite identificar y analizar amenazas recientes. Puede configurar el Explorador para mostrar datos de períodos personalizados.

- ** El [Simulador de ataques](attack-simulator.md)** le permite ejecutar escenarios de ataque realistas en su organización para identificar vulnerabilidades. Están disponibles las simulaciones de los tipos de ataques actuales, incluidos los de phishing de objetivo definido (robo de credenciales), ataques de difusión de contraseña y por fuerza bruta.

## <a name="save-time-with-automated-investigation-and-response"></a>Ahorre tiempo gracias a las investigaciones y respuestas automáticas

(**NOVEDAD**) Al investigar un posible ciberataque, el tiempo es esencial. Cuanto antes pueda identificar y mitigar las amenazas, mejor será para su organización. Las funcionalidades de la [Respuesta e investigación automatizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) incluyen un conjunto de cuadernos de estrategias de seguridad que se pueden iniciar automáticamente, como cuando se activa una alerta, o manualmente, como desde una vista del Explorador. AIR puede ahorrar el tiempo y esfuerzo de su equipo de operaciones de seguridad, y reducir amenazas de manera eficaz. Para obtener más información, consulte[AIR en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).

## <a name="permissions-required-to-use-atp-features"></a>Permisos necesarios para usar las características de ATP

Para acceder a las características de ATP en el Centro de seguridad y cumplimiento, debe tener asignado un rol adecuado. En la tabla siguiente se ofrecen algunos ejemplos:

|Rol o grupo de roles|Recursos para obtener más información|
|---|---|
|Administrador Global (puede asignarse en el Azure Active Directory o en el Centro de seguridad y cumplimiento)|[Acerca de los roles de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Administrador de Seguridad (puede asignarse en Azure Active Directory o en el Centro de seguridad y cumplimiento)|[Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md)|
|Gestión de organizaciones de Exchange Online (esto se asigna en Exchange Online)|[Permisos de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|Búsqueda y purga (se asigna solo en el Centro de seguridad y cumplimiento)|[Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md)|

Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Obtener ATP de Office 365

ATP de Office 365 está incluido en determinadas suscripciones, como Microsoft 365 E5, Office 365 E5, Office 365 A5 y Microsoft 365 Empresa Premium. Si su suscripción no incluye Office 365 ATP, puede comprar ATP Plan 1 o ATP Plan 2 como complemento para determinadas suscripciones. Para obtener más información, vea los siguientes recursos:

- [Disponibilidad de Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) para obtener una lista de suscripciones que incluyen planes de ATP.

- [Disponibilidad de características en los planes de Protección contra amenazas avanzada (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) para obtener una lista de las características incluidas en Plan 1 y Plan 2.

- [Obtener la Protección contra amenazas avanzada de Office 365 adecuada](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) para comparar los planes y comprar ATP de Office 365.

- [Iniciar una prueba gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Nuevas características en ATP de Office 365

Se agregan nuevas características a Office 365 ATP continuamente. Para obtener más información, consulte los siguientes recursos:

- El [Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) ofrece una lista de las nuevas características en proceso de desarrollo e implementación.

- La [Descripción del servicio de Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) muestra las características y la disponibilidad en todos los planes de ATP.

## <a name="see-also"></a>Vea también

- [Protección contra amenazas de Microsoft](../mtp/microsoft-threat-protection.md)

- [Investigación y respuesta automatizada (AIR) en la Protección contra amenazas de Microsoft](../mtp/mtp-autoir.md)
