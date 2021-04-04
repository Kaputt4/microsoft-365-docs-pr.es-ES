---
title: Microsoft Defender para Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender para Office 365 incluye datos adjuntos seguros, vínculos seguros, herramientas avanzadas antiphishing, herramientas de creación de informes y funciones de inteligencia de amenazas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dad2722a1f9e99fad53c83348d049fa9a60f8b62
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580995"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Si utiliza Outlook.com, Microsoft 365 Familia o Microsoft 365 Personal, y está buscando información sobre los vínculos seguros o los datos adjuntos seguros en Outlook, consulte [Seguridad avanzada de Outlook.com para suscriptores de Microsoft 365](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Microsoft Defender para Office 365 protege su organización contra las amenazas malintencionadas ocultas en mensajes de correo electrónico, vínculos (direcciones URL) y herramientas de colaboración. Microsoft Defender para Office 365 incluye:

- **[Directivas de protección contra amenazas](#configure-microsoft-defender-for-office-365-policies)**: defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización.

- **[Informes](#view-microsoft-defender-for-office-365-reports)**: vea informes en tiempo real para supervisar el rendimiento de Microsoft Defender para Office 365 en la organización.

- **[Investigación de amenazas y funcionalidades de respuesta](#use-threat-investigation-and-response-capabilities)**: use las herramientas más avanzadas para investigar, entender, simular y evitar las amenazas.

- **[Investigación automatizada y funcionalidades de respuesta](office-365-air.md)**: ahorre tiempo y esfuerzo al investigar y mitigar las amenazas.

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Guía interactiva de Microsoft Defender para Office 365
En esta guía interactiva, aprenderá cómo proteger su organización con Microsoft Defender para Office 365. Verá cómo Defender para Office 365 puede ayudarle a definir directivas de protección, analizar amenazas en su organización y responder a ataques.

[Eche un vistazo a la guía interactiva](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>Introducción

Si no está familiarizado con Microsoft Defender para Office 365 o prefiere aprender mediante la *práctica*, puede que le convenga analizar por partes la configuración inicial de Microsoft Defender para Office 365, investigar y consultar informes utilizando este artículo como referencia. Aquí se muestran fragmentos previos de configuración de manera lógica:

- Configure todo con "*anti*" en el nombre.
  - antimalware
  - anti-phishing
  - anti-spam (protección contra correo electrónico no deseado)
- Configure todo con "*seguro*" en el nombre.
  - vínculos seguros
  - archivos adjuntos seguros
- Defender las cargas de trabajo (ej. SharePoint Online, OneDrive y Teams)
- Proteger con la purga automática

Para aprender con la práctica, [haga clic en este vínculo](protect-against-threats.md).

> [!NOTE]
> Microsoft Defender para Office 365 tiene dos tipos de planes diferentes. Si tiene "Detecciones en tiempo real", tiene el **Plan 1** y, si tiene el Explorador de amenazas, tiene el **Plan 2**. El plan que tenga influirá en las herramientas que pueda ver, de modo que asegúrese de saber cuál es su plan mientras aprende.

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Plan 1 y Plan 2 de Microsoft Defender para Office 365

La siguiente tabla es un resumen de lo que se incluye en cada plan.

****

|Plan 1 de Microsoft Defender para Office 365|Plan 2 de Microsoft Defender para Office 365|
|---|---|
|Funcionalidades de configuración, protección y detección: <ul><li>[Archivos adjuntos seguros](safe-attachments.md)</li><li>[Vínculos seguros](safe-links.md)</li><li>[Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Protección antiphishing en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecciones en tiempo real](threat-explorer.md)</li></ul>|Capacidades del Plan 1 de Microsoft Defender para Office 365 <br>--- además ---<br> Funcionalidades de automatización, investigación, corrección y educación:<ul><li>[Rastreadores de amenazas](threat-trackers.md)</li><li>[Explorador de amenazas](threat-explorer.md)</li><li>[Investigación y respuesta automatizadas](office-365-air.md)</li><li>[Simulador de ataque](attack-simulator.md)</li><li>[Vistas de campañas](campaigns.md)</li></ul>|
|

- El Plan 2 de Microsoft Defender para Office 365 está incluido en Office 365 E5, Office 365 A5, Seguridad de Microsoft 365 E5, y Microsoft 365 E5.

- El Plan 1 de Microsoft Defender para Office 365 está incluido en Microsoft 365 Empresa Premium.

- El Plan 1 de Microsoft Defender para Office 365 y el Plan 2 de Microsoft Defender para Office 365 están disponibles como complementos para determinadas suscripciones. Para obtener más información, consulte [Disponibilidad de características en los planes de Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- La característica [Documentos seguros](safe-docs.md) solo está disponible para los usuarios con las licencias de Microsoft 365 E5 o Seguridad de Microsoft 365 E5 (no se incluye en los planes de Microsoft Defender para Office 365).

- Si su suscripción actual no incluye Microsoft Defender para Office 365, [póngase en contacto con el departamento de Ventas para iniciar una prueba](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) y ver cómo Microsoft Defender para Office 365 puede funcionar para su organización.

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Configurar las directivas de Microsoft Defender para Office 365

Con Microsoft Defender para Office 365, el equipo de seguridad de su organización puede configurar la protección mediante la definición de directivas en el Centro de seguridad y cumplimiento (vaya a <https://protection.office.com> \> **Administración de amenazas** \> **Directiva**).

Obtenga más información con [este vídeo](https://www.youtube.com/watch?v=vivvTmWJ_3c). 

> [!TIP]
> Para ver una lista rápida de directivas por definir, consulte [Protección contra amenazas](protect-against-threats.md).

## <a name="defender-for-office-365-policies"></a>Directivas de Microsoft Defender para Office 365

Las directivas definidas por la organización determinan el comportamiento y el nivel de protección para las amenazas predefinidas. Las opciones de directivas son muy flexibles. Por ejemplo, el equipo de seguridad de su organización puede establecer protección contra amenazas específica para el nivel de usuario, organización, destinatario y dominio. Es importante revisar las directivas de forma periódica, ya que a diario surgen nuevas amenazas y desafíos.

- **[Archivos adjuntos seguros](safe-attachments.md)**: Proporciona protección de día cero para proteger su sistema de mensajería, comprobando si los archivos adjuntos del correo electrónico contienen contenido malicioso. Dirige todos los mensajes y datos adjuntos que no tienen una firma de virus o malware a un entorno especial y, a continuación, utiliza técnicas de aprendizaje automático y análisis para detectar fines malintencionados. Si no se encuentra ninguna actividad sospechosa, el mensaje se reenvía al buzón. Para más información, consulte [Configurar directivas de datos adjuntos seguros](set-up-safe-attachments-policies.md).

- **[Vínculos seguros](safe-links.md)**: Proporciona verificación del tiempo de clic de las URL, por ejemplo, en mensajes de correo electrónico y archivos de Office. La protección es continua y se aplica en todo su entorno de mensajería y Office. Los vínculos se analizan en cada clic: los vínculos seguros siguen siendo accesibles y los vínculos maliciosos se bloquean dinámicamente. Para más información, consulte [Configurar directivas de vínculos seguros](set-up-safe-links-policies.md).

- **[Datos adjuntos para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md)**: protege su organización cuando los usuarios colaboran y comparten archivos, identificando y bloqueando archivos maliciosos en sitios de equipo y bibliotecas de documentos. Para obtener más información, consulte [Activar Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

- **[Protección antiphishing en Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: detecta los intentos de suplantar la identidad de sus usuarios y dominios internos o personalizados. Aplica modelos de aprendizaje automático y algoritmos avanzados de detección de suplantación para evitar ataques de suplantación de identidad. Para obtener más información, consulte [Configuración de las directivas antiphishing en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-microsoft-defender-for-office-365-reports"></a>Ver informes de Microsoft Defender para Office 365

Microsoft Defender para Office 365 incluye un [panel de informes](view-reports-for-mdo.md) avanzado para supervisar el rendimiento de su Microsoft Defender para Office 365. Puede acceder a este en **Informes** \> **Panel** en el Centro de seguridad y cumplimiento.

Los informes se actualizan en tiempo real y proporcionan los detalles más recientes. Estos informes también proporcionan recomendaciones y le avisan de amenazas inminentes. Los informes predefinidos incluyen:

- [Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)

- [Informe de estado de protección contra amenazas](view-reports-for-mdo.md#threat-protection-status-report)

- [Informe de tipos de archivo de Microsoft Defender para Office 365](view-reports-for-mdo.md#defender-for-office-365-file-types-report)

- [Informe de eliminación de mensajes de Microsoft Defender para Office 365](view-reports-for-mdo.md#defender-for-office-365-message-disposition-report)

- ... y muchas más.

## <a name="use-threat-investigation-and-response-capabilities"></a>Usar las funciones de investigación y respuesta de amenazas

El Plan 2 de Microsoft Defender para Office 365 incluye las mejores [herramientas de investigación y respuesta de amenazas](office-365-ti.md). Con ellas, el equipo de seguridad de su organización puede anticiparse a ataques malintencionados, entenderlos y evitarlos.

- **[Los rastreadores de amenazas](threat-trackers.md)** proporcionar la información más reciente sobre los problemas de ciberseguridad existentes. Por ejemplo, puede ver información sobre el malware más reciente y tomar medidas antes de que se convierta en una amenaza real para su organización. Entre los rastreadores disponibles se incluyen [Rastreadores destacados](threat-trackers.md#noteworthy-trackers), [Rastreadores en tendencia](threat-trackers.md#trending-trackers), [Consultas rastreadas](threat-trackers.md#tracked-queries) y [Consultas guardadas](threat-trackers.md#saved-queries).

- **[Explorador de amenazas (o detecciones en tiempo real)](threat-explorer.md)** (también conocido como Explorador) es un informe en tiempo real que le permite identificar y analizar amenazas recientes. Puede configurar el Explorador para mostrar datos de períodos personalizados.

- **El [Simulador de ataques](attack-simulator.md)** le permite ejecutar escenarios de ataque realistas en su organización para identificar vulnerabilidades. Están disponibles las simulaciones de los tipos de ataques actuales, incluidos los de phishing de objetivo definido (robo de credenciales), ataques de difusión de contraseña y por fuerza bruta.

## <a name="save-time-with-automated-investigation-and-response"></a>Ahorre tiempo gracias a las investigaciones y respuestas automáticas

(**NOVEDAD**) Al investigar un posible ciberataque, el tiempo es esencial. Cuanto antes pueda identificar y mitigar las amenazas, mejor será para su organización. Las funcionalidades de la [Respuesta e investigación automatizadas](office-365-air.md) (AIR) incluyen un conjunto de cuadernos de estrategias de seguridad que se pueden iniciar automáticamente, como cuando se activa una alerta, o manualmente, como desde una vista del Explorador. AIR puede ahorrar el tiempo y esfuerzo de su equipo de operaciones de seguridad, y reducir amenazas de manera eficaz. Para obtener más información, consulte[AIR en Office 365](office-365-air.md).

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Permisos necesarios para usar las características de Microsoft Defender para Office 365

Para acceder a las características de Microsoft Defender para Office 365 en el Centro de seguridad y cumplimiento, debe tener asignado un rol adecuado. En la tabla siguiente se ofrecen algunos ejemplos:

|Rol o grupo de roles|Recursos para obtener más información|
|---|---|
|Administrador Global (puede asignarse en el Azure Active Directory o en el Centro de seguridad y cumplimiento)|[Acerca de los roles de administración de Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Administrador de Seguridad (puede asignarse en Azure Active Directory o en el Centro de seguridad y cumplimiento)|[Permisos de roles de administrador en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md)|
|Gestión de organizaciones de Exchange Online (esto se asigna en Exchange Online)|[Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|Búsqueda y purga (se asigna solo en el Centro de seguridad y cumplimiento)|[Permisos en el Centro de seguridad y cumplimiento ](permissions-in-the-security-and-compliance-center.md)|

Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="get-microsoft-defender-for-office-365"></a>Obtener Microsoft Defender para Office 365

Microsoft Defender para Office 365 está incluido en determinadas suscripciones, como Microsoft 365 E5, Office 365 E5, Office 365 A5 y Microsoft 365 Empresa Premium. Si su suscripción no incluye Microsoft Defender para Office 365, puede comprar el Plan 1 o el Plan 2 de Microsoft Defender para Office 365 como complemento para determinadas suscripciones. Para obtener más información, consulte los siguientes recursos:

- [Disponibilidad de Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability), donde se muestra una lista de suscripciones que incluyen planes de Microsoft Defender para Office 365.

- [Disponibilidad de características en los planes de Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans), donde verá una lista de las características incluidas en el Plan 1 y el Plan 2.

- [Obtener el Microsoft Defender para Office 365 adecuado](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content), donde podrá comparar los planes del programa y comprarlo para Office 365.

- [Iniciar una prueba gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Nuevas características de Microsoft Defender para Office 365

Se agregan nuevas características a Microsoft Defender para Office 365 continuamente. Para obtener más información, consulte los siguientes recursos:

- El [Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) ofrece una lista de las nuevas características en proceso de desarrollo e implementación.

- [La descripción del servicio de Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describe las características y la disponibilidad de los planes de Microsoft Defender para Office 365.

## <a name="see-also"></a>Consulte también

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

- [Investigación y respuesta automatizada (AIR) en Microsoft 365 Defender](../defender/m365d-autoir.md) 1
