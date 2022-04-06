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
- M365-security-compliance
ms.localizationpriority: high
search.appverid:
- MET150
description: Obtenga información sobre las tres herramientas que puede usar para supervisar pérdidas de datos personales.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba164fde38be1e8eed53b71ab568124140deaac5
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682711"
---
# <a name="monitor-for-leaks-of-personal-data"></a>Supervisar pérdidas de datos personales

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Existen muchas herramientas que pueden usarse para supervisar el uso y transporte de datos personales. En este tema se describen tres herramientas que funcionan bien.

![Herramientas para supervisar el uso y transporte de datos personales.](../../media/Monitor-for-leaks-of-personal-data-image1.png)

En la ilustración:

- Comience con los informes de prevención de pérdida de datos de Microsoft 365 para supervisar datos personales en SharePoint Online, OneDrive para la Empresa y correo electrónico en tránsito. Estos informes proporcionan mayor nivel de detalle de supervisión de datos personales. No obstante, estos informes no incluyen todos los servicios de Office 365.

- Después, use directivas de alerta y el registro de auditoría para supervisar la actividad de los servicios. Configure la supervisión continua o busque el registro de auditoría para investigar un incidente. El registro de auditoría funciona en todos los servicios: Sway, Power BI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, actividad administrativa, OneDrive para la Empresa, SharePoint Online, correo electrónico en tránsito, y buzones de correo en reposo. Las conversaciones de Skype se incluyen en los buzones en reposo.

- Por último, use Microsoft Defender for Cloud Apps para supervisar archivos con datos confidenciales en otros proveedores SaaS. Próximamente, se podrán usar las etiquetas unificadas y los tipos de información confidencial en Azure Information Protection y en Ofﬁce. Puede configurar directivas que se apliquen a todas sus aplicaciones SaaS o a aplicaciones específicas (como Box). Defender for Cloud Apps no detecta archivos en Exchange Online, incluidos los archivos adjuntos al correo electrónico.

## <a name="data-loss-prevention-reports"></a>Informes de prevención de pérdida de datos

Después de crear las directivas de prevención de pérdida de datos (DLP), deberá comprobar que su funcionamiento es el deseado y que le ayudan a cumplir las normativas. Con los informes DLP en Office 365, puede ver rápidamente el número de coincidencias de directivas DLP, reemplazos o falsos positivos; comprobar si la tendencia es ascendente o descendente a lo largo del tiempo; filtrar el informe de maneras diferentes; y ver más detalles seleccionando un punto en una línea del gráfico.

Puede usar los informes DLP para lo siguiente:

- Centrarse en períodos de tiempo específicos y comprender las causas de los picos y las tendencias.
- Descubrir los procesos de negocio que infringen las directivas DLP de su organización.
- Comprender cualquier impacto de negocio de las directivas DLP.
- Ver las justificaciones enviadas por los usuarios cuando resuelven una sugerencia de directiva reemplazando la directiva o informando de un falso positivo.
- Comprobar el cumplimiento de una directiva DLP específica mostrando las coincidencias de dicha directiva.
- Ver una lista de los archivos con datos confidenciales que coincida con las directivas DLP en el panel de detalles.

Además, puede usar los informes DLP para ajustar las directivas DLP a medida que las ejecuta en modo de prueba.

Los informes DLP están en el Centro de cumplimiento de Microsoft 365. Vaya a **Informes**\>**sección** de datos de la organización para encontrar **las coincidencias de la directiva DLP**, **los incidentes** y **falsos positivos e invalidaciones de informes** DLP.

Para obtener más información, consulte [Ver los informes de prevención de pérdida de datos](../../compliance/view-the-dlp-reports.md).

![Informe que muestra coincidencias de directivas DLP.](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="audit-log-and-alert-policies"></a>Directivas de alerta y registro de auditoría

El registro de auditoría contiene eventos de Exchange Online, SharePoint Online, OneDrive para la Empresa, Azure Active Directory, Microsoft Teams, Power BI, Sway y otros servicios.

El portal de Microsoft 365 Defender y el Centro de cumplimiento de Microsoft 365 ofrecen dos formas de supervisar e informar en el registro de auditoría:

- Configurar directivas de alerta, ver alertas y supervisar tendencias: Use la directiva de alerta y las herramientas del panel de alertas en el portal de Microsoft 365 Defender o el Centro de cumplimiento de Microsoft 365.
- Buscar el registro de auditoría directamente: Busque todos los eventos en un intervalo de fechas definido, o filtre los resultados basándose en criterios específicos, como la acción, el usuario que la realizó o el objeto de destino.

Los equipos de cumplimiento y seguridad de la información pueden usar estas herramientas para revisar proactivamente las actividades realizadas por los usuarios finales y los administradores en los servicios. Pueden configurarse alertas automáticas para enviar notificaciones por correo electrónico cuando se producen ciertas actividades en colecciones de sitios específicos, por ejemplo, cuando se comparte el contenido de los sitios que se sabe que contienen información relacionada con RGPD. Esto permite que los equipos contacten con usuarios para asegurarse de que se siguen directivas de seguridad corporativa, o que proporcionen aprendizaje adicional.

Los equipos de seguridad de información también pueden buscar en el registro de auditoría para investigar las posibles infracciones de datos y determinar la causa raíz y la extensión de la infracción. Esta función integrada facilita el cumplimiento de los artículos 33 y 34 del RGPD, que requieren que se proporcionen notificaciones a la autoridad de control del RGPD y a los propietarios de los datos sujetos a una infracción en un período de tiempo determinado. Las entradas del registro de auditoría solo se conservan durante 90 días en el servicio, por lo que a menudo se recomienda, y muchas organizaciones lo requieren, que estos registros se conserven durante largos períodos de tiempo.

Existen soluciones que se adhieren a los Registros de auditoría unificados mediante la API de actividad de administración de Microsoft y pueden almacenar entradas de registro según sea necesario, y proporcionar paneles avanzados y alertas. Un ejemplo es el [Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365).

Más información sobre las directivas de alerta y buscar en el registro de auditoría:

- [Directivas de alerta en Microsoft 365](../../compliance/alert-policies.md)
- [Buscar en el registro de auditoría de actividad de usuario y administración de Office 365](../../compliance/search-the-audit-log-in-security-and-compliance.md) (introducción)
- [Activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md)
- [Buscar en el registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)
- [Propiedades detalladas del registro de auditoría](../../compliance/detailed-properties-in-the-office-365-audit-log.md)

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps le ayuda a descubrir otras aplicaciones SaaS en uso en las redes y los datos confidenciales que se envían a estas aplicaciones y desde las mismas.

Microsoft Defender for Cloud Apps es un servicio integral que proporciona una gran visibilidad, controles granulares y una mayor protección contra las amenazas para sus aplicaciones en la nube. Identifica más de 15 000 aplicaciones en la nube en la red de todos los dispositivos y proporciona una puntuación de riesgo y una evaluación y análisis de riesgo continuos. No se necesitan agentes: la información se recoge de sus firewalls y proxies para ofrecerle una visibilidad completa y un contexto para el uso de la nube y shadow IT.

Para comprender mejor su entorno en la nube, la característica de investigación de Defender for Cloud Apps proporciona una profunda visibilidad de todas las actividades, archivos y cuentas de las aplicaciones sancionadas y administradas. Puede obtener información detallada a nivel de archivos y descubrir por dónde viajan los datos en las aplicaciones en la nube.

Para obtener ejemplos, la siguiente ilustración muestra dos directivas de Defender for Cloud Apps que pueden ayudarle con el RGPD.

![Ejemplo de directivas de Defender for Cloud Apps.](../../media/Monitor-for-leaks-of-personal-data-image3.png)

Las primera directiva envía una alerta cuando se comparten archivos con un atributo DCP predefinido o una expresión personalizada que elija fuera de la organización desde las aplicaciones SaaS que elija.

La segunda directiva bloquea las descargas de archivos en cualquier dispositivo no administrado. Usted elige los atributos de los archivos que se buscarán y las aplicaciones SaaS a las que desee que se aplique la directiva.

Estos tipos de atributos estarán disponibles próximamente en Defender for Cloud Apps:

- Tipos de información confidencial
- Etiquetas unificadas en Microsoft 365 y Azure Information Protection

### <a name="defender-for-cloud-apps-dashboard"></a>Panel de Microsoft Defender for Cloud Apps

Si todavía no ha empezado a utilizar Defender for Cloud Apps, empiece por iniciarlo. Para acceder a Defender for Cloud Apps: <https://portal.cloudappsecurity.com>.

> [!NOTE]
> No olvide habilitar "Analizar automáticamente archivos de etiquetas de clasificación de Azure Information Protection" (en la configuración General) al comenzar a usar Defender for Cloud Apps o antes de asignar etiquetas. Después de la configuración, Defender for Cloud Apps no vuelve a examinar los archivos existentes hasta que se modifican.

![Panel en el que se muestra información de alertas.](../../media/Monitor-for-leaks-of-personal-data-image4.png)

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
