---
title: Supervisar pérdidas de datos personales
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- m365-security
ms.localizationpriority: high
search.appverid:
- MET150
description: Obtenga información sobre las tres herramientas que puede usar para supervisar pérdidas de datos personales.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: dd25ee58f219a18544b05969e2c0a51eb7788a13
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68069015"
---
# <a name="monitor-for-leaks-of-personal-data"></a>Supervisar pérdidas de datos personales

There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.

:::image type="content" source="../../media/Monitor-for-leaks-of-personal-data-image1.png" alt-text="Las herramientas para supervisar el uso y el transporte de datos personales" lightbox="../../media/Monitor-for-leaks-of-personal-data-image1.png":::

En la ilustración:

- Start with Microsoft Purview data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These reports provide the greatest level of detail for monitoring personal data. However, these reports don't include all services in Office 365.

- Next, use alert policies and the audit log to monitor activity across services. Set up ongoing monitoring or search the audit log to investigate an incident. The audit log works across services—Sway, Power BI, eDiscovery, Dynamics 365, Power Automate, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.

- Finally, Use Microsoft Defender for Cloud Apps to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use sensitive information types and unified labels across Azure Information Protection and Office with Defender for Cloud Apps. You can set up policies that apply to all of your SaaS apps or specific apps (like Box). Defender for Cloud Apps doesn't discover files in Exchange Online, including files attached to email.

## <a name="data-loss-prevention-reports"></a>Informes de prevención de pérdida de datos

After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view more details by selecting a point on a line on the graph.

Puede usar los informes DLP para lo siguiente:

- Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
- Descubrir los procesos de negocio que infringen las directivas DLP de su organización.
- Comprender cualquier impacto de negocio de las directivas DLP.
- Ver las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de directiva reemplazando la directiva o informando de un falso positivo.
- Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.
- Ver una lista de los archivos con datos confidenciales que coincida con las directivas DLP en el panel de detalles.

Además, puede usar los informes DLP para ajustar las directivas DLP a medida que las ejecuta en modo de prueba.

DLP reports are in the Microsoft Purview compliance portal. Go to **Reports** \> **Organizational data** section to find the **DLP policy matches**, **DLP incidents**, and **DLP false positives and overrides** reports.

Para obtener más información, consulte [Ver los informes de prevención de pérdida de datos](../../compliance/view-the-dlp-reports.md).

:::image type="content" source="../../media/Monitor-for-leaks-of-personal-data-image2.png" alt-text="Informe que muestra las coincidencias de directivas DLP" lightbox="../../media/Monitor-for-leaks-of-personal-data-image2.png":::

## <a name="audit-log-and-alert-policies"></a>Directivas de alerta y registro de auditoría

El registro de auditoría contiene eventos de Exchange Online, SharePoint Online, OneDrive para la Empresa, Azure Active Directory, Microsoft Teams, Power BI, Sway y otros servicios.

El portal de Microsoft 365 Defender y el portal de cumplimiento de Microsoft Purview ofrecen dos formas de supervisar e informar en el registro de auditoría:

- Configurar directivas de alerta, ver alertas y supervisar tendencias: use las herramientas de directiva de alertas y del panel de alertas en el portal de Microsoft 365 Defender o en el portal de cumplimiento de Microsoft Purview.
- Search the audit log directly: Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.

Information compliance and security teams can use these tools to proactively review activities performed by both end users and administrators across services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR-related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.

Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built-in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.

Solutions are available that subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365).

Más información sobre las directivas de alerta y buscar en el registro de auditoría:

- [Directivas de alerta en Microsoft 365](../../compliance/alert-policies.md)
- [Buscar en el registro de auditoría de actividad de usuario y administración de Office 365](../../compliance/search-the-audit-log-in-security-and-compliance.md) (introducción)
- [Activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md)
- [Buscar en el registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)
- [Propiedades detalladas del registro de auditoría](../../compliance/detailed-properties-in-the-office-365-audit-log.md)

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps le ayuda a descubrir otras aplicaciones SaaS en uso en las redes y los datos confidenciales que se envían a estas aplicaciones y desde las mismas.

Microsoft Defender for Cloud Apps is a comprehensive service providing deep visibility, granular controls, and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.

To better understand your cloud environment, the Defender for Cloud Apps investigate feature provides deep visibility into all activities, files, and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.

Para obtener ejemplos, la siguiente ilustración muestra dos directivas de Defender for Cloud Apps que pueden ayudarle con el RGPD.

:::image type="content" source="../../media/Monitor-for-leaks-of-personal-data-image3.png" alt-text="Directivas de Defender for Cloud Apps" lightbox="../../media/Monitor-for-leaks-of-personal-data-image3.png":::

Las primera directiva envía una alerta cuando se comparten archivos con un atributo DCP predefinido o una expresión personalizada que elija fuera de la organización desde las aplicaciones SaaS que elija.

The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.

Estos tipos de atributos estarán disponibles próximamente en Defender for Cloud Apps:

- Tipos de información confidencial
- Etiquetas unificadas en Microsoft 365 y Azure Information Protection

### <a name="defender-for-cloud-apps-dashboard"></a>Panel de Microsoft Defender for Cloud Apps

If you haven't yet started to use Defender for Cloud Apps, begin by starting it up. To access Defender for Cloud Apps: <https://portal.cloudappsecurity.com>.

> [!NOTE]
> Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Defender for Cloud Apps or before you assign labels. After setup, Defender for Cloud Apps does not scan existing files again until they are modified.

:::image type="content" source="../../media/Monitor-for-leaks-of-personal-data-image4.png" alt-text="Panel que muestra información sobre las alertas" lightbox="../../media/Monitor-for-leaks-of-personal-data-image4.png":::

Más información:

- [Implementar Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security)
- [Más información sobre Microsoft Defender for Cloud Apps](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Bloqueo de descargas de información confidencial con el proxy de Microsoft Defender for Cloud Apps](/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a>Directivas de archivo y actividad de ejemplo para detectar el uso compartido de datos personales

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a>Detectar el uso compartido de archivos que contengan DCP: número de tarjeta de crédito

Envíe una alerta cuando se comparte un archivo que contiene un número de tarjeta de crédito desde una aplicación de nube autorizada.

|Control|Configuración|
|---|---|
|Tipo de directiva|Directiva de archivo|
|Plantilla de directiva|Sin plantilla|
|Gravedad de directiva|Alta|
|Categoría|DLP|
|Configuración del filtro|Nivel de acceso = público (Internet), público, externo <p> Aplicación = \<select apps\> (use esta opción si desea limitar la supervisión a aplicaciones SaaS específicas)|
|Aplicar a|Todos los archivos, todos los propietarios|
|Control de contenido|Incluye los archivos que coinciden con una expresión actual: Todos los países: Finanzas: Número de tarjeta de crédito <p> No requerir contexto relevante: desactivado (esto coincidirá con palabras clave, así como regex) <p> Incluir archivos con al menos 1 coincidencia <p> Quitar máscara de los últimos 4 caracteres de la infracción: activada|
|Alertas|Crear una alerta para cada archivo coincidente: activada <p> Límite de alertas diario: 1000 <p> Seleccionar una alerta como correo electrónico: activada <p> Para: infosec@contoso.com|
|Gobierno|Microsoft OneDrive para la Empresa <p> Hacer privado: comprobar Quitar usuarios externos <p> Resto de opciones: desactivadas <p> Microsoft SharePoint Online <p> Hacer privado: comprobar Quitar usuarios externos <p> Resto de opciones: desactivadas|

Directivas similares:

- Detectar el uso compartido de archivos que contengan DCP: dirección de correo electrónico
- Detectar el uso compartido de archivos que contengan DCP: número de pasaporte

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a>Detectar Datos de recursos humanos o Datos de cliente en Box o OneDrive para la Empresa

Envía una alerta cuando se carga un archivo etiquetado como Datos de recursos humanos o Datos de cliente en OneDrive para la Empresa o Box.

Notas:

- La supervisión de Box requiere un conector configurado con el SDK API Connector.
- Esta directiva requiere funcionalidades que actualmente están en versión preliminar privada.

|Control|Configuración|
|---|---|
|Tipo de directiva|Directiva de actividad|
|Plantilla de directiva|Sin plantilla|
|Gravedad de directiva|Alta|
|Categoría|Control de uso compartido|
|Actúa en|Actividad única|
|Configuración del filtro|Tipo de actividad = cargar archivo <p> Aplicación = Microsoft OneDrive para la Empresa y Box <p> Etiqueta de clasificación (actualmente en versión preliminar privada): Azure Information Protection = datos del cliente, recursos humanos (datos de salario, recursos humanos), datos de empleado|
|Alertas|Crear una alerta: activada <p> Límite de alertas diario: 1000 <p> Seleccionar una alerta como correo electrónico: activada <p> Para: infosec@contoso.com|
|Gobierno|Todas las aplicaciones <p> Poner el usuario en cuarentena: comprobar <p> Resto de opciones: desactivadas <p> Office 365 <p> Poner el usuario en cuarentena: comprobar <p> Resto de opciones: desactivadas|

Directivas similares:

- Detectar descargas grandes de datos de clientes o datos de recursos humanos: Envía una alerta cuando se detecta que un solo usuario está descargando un gran número de archivos que contienen datos de recursos humanos o de clientes en un breve período de tiempo.
- Detectar el uso compartido de datos de clientes y datos de recursos humanos: Envía una alerta cuando se comparten archivos con datos de clientes o de recursos humanos.
