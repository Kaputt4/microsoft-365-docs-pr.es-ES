---
title: Protección contra amenazas avanzada de Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/03/2019
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
description: La Protección contra amenazas avanzada de Office 365 incluye datos adjuntos seguros, vínculos seguros, herramientas avanzadas contra la suplantación de identidad, herramientas de creación de informes y funciones de inteligencia de amenazas.
ms.openlocfilehash: ba7395c29a700039e29c066daa942687e610e4aa
ms.sourcegitcommit: 8fda7852b2a5baa92b8a365865b014ea6d100bbc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "39813770"
---
# <a name="office-365-advanced-threat-protection"></a>Protección contra amenazas avanzada de Office 365

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen la [Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Si usa Outlook.com, Office 365 Hogar u Office 365 personal, y está buscando información sobre vínculos seguros en Outlook, consulte [Seguridad avanzada de Outlook.com](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Información general

La Protección contra amenazas avanzada de Office 365 (ATP) protege su organización contra las amenazas malintencionadas ocultas en mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. ATP incluye:

- [Directivas de protección contra amenazas](#configure-atp-policies): defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización. 

- [Informes](#view-office-365-atp-reports): vea informes en tiempo real para supervisar el rendimiento de ATP en la organización. 

- [Investigación de amenazas y capacidades de respuesta](#use-threat-investigation-and-response-capabilities): use las herramientas más avanzadas para investigar, entender, simular y evitar las amenazas. 

- [Funciones de respuesta a incidencias automatizada](#save-time-with-automated-incident-response): ahorre tiempo y esfuerzo al investigar y mitigar amenazas.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP Plan 1 y Plan 2

ATP se incluye en Office 365 E5. Sin embargo, el Plan 1 y 2 de ATP de Office 365 están disponibles como complementos para determinadas suscripciones. Para obtener más información, consulte [Disponibilidad de características en los planes de ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

> [!TIP]
> Si no tienes Office 365 ATP, puedes [comiezar una prueba gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279).


## <a name="configure-atp-policies"></a>Configurar directivas ATP

Con ATP de Office 365, el equipo de seguridad de su organización puede configurar la protección definiendo directivas en el Centro de seguridad y cumplimiento de Office 365 (vaya a [https://protection.office.com](https://protection.office.com) > **Administración de amenazas** > **Directiva**). 

> [!TIP]
> Para ver una lista de directivas para definir rápidamente, vea [Protegerse ante amenazas](protect-against-threats.md).

Las directivas definidas por la organización determinan el comportamiento y el nivel de protección para las amenazas predefinidas. Las opciones de directivas son muy flexibles. Por ejemplo, el equipo de seguridad de su organización puede establecer protección contra amenazas específica para el nivel de usuario, organización, destinatario y dominio. Es importante revisar las directivas de forma periódica, ya que a diario surgen nuevas amenazas y desafíos.  

- **[Archivos adjuntos seguros ATP](atp-safe-attachments.md)**: Proporciona protección de día cero para proteger su sistema de mensajería, comprobando si los archivos adjuntos del correo electrónico contienen contenido malicioso. Dirige todos los mensajes y datos adjuntos que no tienen una firma de virus o malware a un entorno especial y, a continuación, utiliza técnicas de aprendizaje automático y análisis para detectar fines malintencionados. Si no se encuentra ninguna actividad sospechosa, el mensaje se reenvía al buzón. Para obtener más información, consulte [Configurar directivas de datos adjuntos seguros de ATP de Office 365](set-up-atp-safe-attachments-policies.md).

- **[Vínculos seguros de ATP](atp-safe-links.md)**: Proporciona verificación del tiempo de clic de las URL, por ejemplo, en mensajes de correo electrónico y archivos de Office. La protección es continua y se aplica en todo su entorno de mensajería y Office. Los vínculos se analizan en cada clic: los vínculos seguros siguen siendo accesibles y los vínculos maliciosos se bloquean dinámicamente. Para obtener más información, consulte [Configurar directivas de vínculos seguros de ATP de Office 365](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies). 

- **[ATP para los equipos de SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md)**: protege su organización cuando los usuarios colaboran y comparten archivos, identificando y bloqueando archivos maliciosos en sitios de equipo y bibliotecas de documentos. Para obtener más información, consulte [Activar ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md). 

- **[Protección anti phishing ATP](atp-anti-phishing.md)**: detecta los intentos de suplantar la identidad de sus usuarios y dominios personalizados. Aplica modelos de aprendizaje automático y algoritmos avanzados de detección de suplantación para evitar ataques de suplantación de identidad. Para obtener más información, consulte [Configurar directivas contra suplantación de identidad y directivas contra suplantación de identidad de ATP de Office 365](set-up-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Ver informes de ATP de Office 365

ATP de Office 365 incluye un [panel de informes](view-reports-for-atp.md) avanzado para supervisar el rendimiento de ATP. Puede acceder a él en **Informes** > **Panel** en el Centro de seguridad y cumplimiento. 

Los informes se actualizan en tiempo real y proporcionan los detalles más recientes. Estos informes también proporcionan recomendaciones y le avisan de amenazas inminentes. Los informes predefinidos incluyen: 

- [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)

- [Informe de estado de protección contra amenazas](view-reports-for-atp.md#threat-protection-status-report)

- [Informe de tipos de archivos de ATP](view-reports-for-atp.md#atp-file-types-report)

- [Informe de disposición de mensajes ATP](view-reports-for-atp.md#atp-message-disposition-report)

- ... y muchas más. 

## <a name="use-threat-investigation-and-response-capabilities"></a>Usar las funciones de investigación y respuesta de amenazas

Office 365 ATP Plan 2 incluye las mejores [herramientas de investigación y respuesta de amenazas](office-365-ti.md) que permiten que el equipo de seguridad de su organización anticipe, entienda y evite ataques malintencionados. 

- **[Los rastreadores de amenazas](threat-trackers.md)** proporcionar la información más reciente sobre los problemas de ciberseguridad existentes. Por ejemplo, puede ver información sobre el malware más reciente y tomar medidas antes de que se convierta en una amenaza real para su organización. Entre los rastreadores disponibles se incluyen [Rastreadores destacados](threat-trackers.md#noteworthy-trackers), [Rastreadores en tendencia](threat-trackers.md#trending-trackers), [Consultas rastreadas](threat-trackers.md#tracked-queries) y [Consultas guardadas](threat-trackers.md#saved-queries).

- **[Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)** (también conocido como Explorador) es un informe en tiempo real que le permite identificar y analizar amenazas recientes. Puede configurar el Explorador para mostrar datos de períodos personalizados.

- **[Simulador de ataques](attack-simulator.md)** le permite ejecutar escenarios de ataque realistas en su organización para identificar vulnerabilidades. Hay disponibles simulaciones de los tipos actuales de ataques, incluido un [ataque de phishing de objetivo definido de nombre para mostrar](attack-simulator.md#display-name-spear-phishing-attack), un [ataque de difusión de contraseña](attack-simulator.md#password-spray-attack) y un [ataque de contraseña por fuerza bruta](attack-simulator.md#brute-force-password-attack) entre otros.
    
## <a name="save-time-with-automated-incident-response"></a>Ahorrar tiempo con respuesta a incidencia automatizada

(**NOVEDAD**) Al investigar un posible ciberataque, el tiempo es esencial. Cuanto antes pueda identificar y mitigar las amenazas, mejor será para su organización. Las funciones de la [Respuesta a incidencia automatizada](automated-investigation-response-office.md) (AIR) incluyen un conjunto de cuadernos de estrategias de seguridad que se pueden iniciar automáticamente, como cuando se activa una alerta, o manualmente, como desde una vista del Explorador. AIR puede ahorrar el tiempo y esfuerzo de su equipo de operaciones de seguridad, y reducir amenazas de manera eficaz. Para obtener más información, consulte[AIR en Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Permisos necesarios para usar las características de ATP

Para acceder a las características de ATP en el Centro de seguridad y cumplimiento, debe tener asignado un rol adecuado. En la tabla siguiente se ofrecen algunos ejemplos:

|Rol o grupo de roles  |Recursos para obtener más información  |
|---------|---------|
|Administrador Global de Office 365 (esto puede ser asignado en el Azure Active Directory o en el Centro de seguridad y cumplimiento de Office 365) |[Acerca de los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Administrador de Seguridad (esto puede ser asignado en el Azure Active Directory o en el Centro de seguridad y cumplimiento de Office 365) |[Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md)|
|Gestión de organizaciones de Exchange Online (esto se asigna en Exchange Online)|[Permisos de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|
|Búsqueda y purga (esto se asigna sólo en el Centro de seguridad y cumplimiento de Office 365) |[Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md) |

Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Obtener ATP de Office 365

ATP de Office 365 está incluido en determinadas suscripciones, como Microsoft 365 E5, Office 365 E5, Office 365 A5 y Microsoft 365 Empresa. Si su suscripción no incluye Office 365 ATP, puede comprar ATP Plan 1 o ATP Plan 2 como complemento para determinadas suscripciones. Para obtener más información, vea los siguientes recursos:

- [Disponibilidad de Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) para obtener una lista de suscripciones que incluyen planes de ATP.

- [Disponibilidad de características en los planes de Protección contra amenazas avanzada (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) para obtener una lista de las características incluidas en Plan 1 y Plan 2.

- [Obtener la Protección contra amenazas avanzada de Office 365 adecuada](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) para comparar los planes y comprar ATP de Office 365.

- [Iniciar una prueba gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Nuevas características en ATP de Office 365

Se agregan nuevas características a Office 365 ATP continuamente. Para obtener más información, consulte los siguientes recursos:

- El [Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) ofrece una lista de las nuevas características en proceso de desarrollo e implementación.

- La [Descripción del servicio de Protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) muestra las características y la disponibilidad en todos los planes de ATP.
