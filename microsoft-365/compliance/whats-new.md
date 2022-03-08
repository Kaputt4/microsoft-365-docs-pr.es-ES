---
title: Novedades de Cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Ya sea agregar nuevas soluciones al centro de cumplimiento, actualizar las características existentes en función de sus comentarios o implementar documentación actualizada y actualizada, Microsoft 365 le ayudará a mantenerse al tanto del panorama de cumplimiento en constante cambio. Descubra lo que hemos estado haciendo hasta este mes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 15a97fc419bc6e4264f3c3cd0bbe389b79e5c2f0
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326977"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novedades de Cumplimiento de Microsoft 365

Ya sea agregar nuevas soluciones al [Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center.md), actualizar las características existentes en función de sus comentarios o implementar documentación actualizada y actualizada, Microsoft 365 le ayudará a mantenerse al tanto del panorama de cumplimiento en constante cambio. Echa un vistazo a continuación para ver las novedades de Microsoft 365 cumplimiento actual.

> [!NOTE]
> Algunas características de cumplimiento se implantan a diferentes velocidades para nuestros clientes. Si aún no ve una característica, intente agregarse a la [versión dirigida](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> ¿Te interesa lo que sucede en otros centros de administración? Consulte estos artículos:
>
> - [Novedades de la Centro de administración de Microsoft 365](/office365/admin/whats-new-in-preview)
> - [Novedades del Centro de administración SharePoint administración](/sharepoint/what-s-new-in-admin-center)
> - [Novedades de Microsoft 365 Defender](../security/defender/whats-new.md)
>
> Y visite la [guía básica de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener información sobre Microsoft 365 características que se iniciaron, se están implementando, están en desarrollo, se han cancelado o publicado anteriormente.

## <a name="february-2022"></a>Febrero de 2022

### <a name="ediscovery"></a>eDiscovery

- [Administrar plantillas de](advanced-ediscovery-communications-library.md) comunicaciones de custodia en Advanced eDiscovery: los administradores de exhibición de documentos electrónicos ahora pueden crear plantillas de comunicaciones de custodia que se pueden usar en cualquier Advanced eDiscovery caso de la organización.
- [Administrar agentes](advanced-ediscovery-issuing-officers.md) emisores en Advanced eDiscovery: los administradores de exhibición de documentos electrónicos pueden agregar una lista de agentes emisores que se pueden asignar a comunicaciones de custodia en cualquier Advanced eDiscovery caso de la organización.

### <a name="information-governance-and-records-management"></a>Administración de registros y gobierno de la información

- [Los ámbitos adaptables](retention.md#adaptive-or-static-policy-scopes-for-retention) para las directivas de retención y las directivas de etiquetas de retención están disponibles por lo general (GA). Las instrucciones para [](retention-settings.md#to-configure-an-adaptive-scope) configurar un ámbito adaptable ahora incluyen más información para ámbitos de sitio de SharePoint: Referencia de entrada de blog para usar propiedades de sitio personalizadas y cómo usar la propiedad site SiteTemplate para incluir o excluir tipos de sitio específicos con el generador de consultas avanzado.
- [La búsqueda de](retention.md#policy-lookup) directivas en la solución de gobierno de información ya está disponible (GA).
- PowerShell alternativa a la configuración de administración de registros que permite a los usuarios eliminar elementos etiquetados en SharePoint y OneDrive mediante AllowFilesWithKeepLabelToBeDeletedSPO y AllowFilesWithKeepLabelToBeDeletedODB de [Get-PnPTenant](/powershell/module/sharepoint-pnp/get-pnptenant) y [Set-PnPTenant]( /powershell/module/sharepoint-pnp/set-pnptenant).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Nueva guía Por qué elegir el etiquetado integrado de MIP en el complemento [AIP](sensitivity-labels-aip.md) para aplicaciones de Office si usa el cliente de etiquetado unificado de Azure Information Protection (AIP) para Windows equipos. Esta página incluye información sobre la nueva vista previa privada para Office aplicaciones.
- Nueva configuración para [directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange):
  - Configuración adicional para que el correo electrónico admita siempre la aplicación de una etiqueta de confidencialidad coincidente y para aplicar el cifrado al correo electrónico recibido desde fuera de la organización.
  - Las exclusiones para instancias específicas (usuarios, grupos, sitios) se admiten mediante la nueva  opción Excluido cuando se especifica la selección predeterminada de **All** para **Included**.
- Ahora en versión preliminar: los dispositivos móviles (iOS y Android) admiten [la co-autoría](sensitivity-labels-coauthoring.md) cuando tienes versiones mínimas y optas por esta vista previa.
- La compatibilidad para establecer el tipo de vínculo de uso compartido predeterminado se extiende a documentos individuales en SharePoint y OneDrive. Para obtener más información, vea el nuevo [artículo Use sensitivity labels to configure the default sharing link type for sites and documents in SharePoint and OneDrive]( sensitivity-labels-default-sharing-link.md).
- Teams centro de administración ahora admite etiquetas de contenedor (etiquetas de confidencialidad con el ámbito de grupos & sitios).

## <a name="january-2022"></a>Enero de 2022

### <a name="microsoft-information-governance"></a>Gobernanza de información de Microsoft

- La página y la sección gobierno de información de Microsoft en Microsoft 365 de la documentación se revisan y reestructuran sustancialmente para ayudarle a encontrar más fácilmente información relacionada [con](manage-information-governance.md) las soluciones que configura en el Centro de cumplimiento de Microsoft 365: Conectores de datos, Gobierno de información y Administración de registros. Como parte de esta revisión, la documentación proporciona una distinción más clara para los escenarios de retención para el gobierno de la información frente a la administración de registros.
- [Obtenga información sobre el gobierno de](information-governance.md) la información: nuevo, para admitir la reestructuración.
- [Introducción al gobierno de](get-started-with-information-governance.md) la información: nuevo, para reemplazar "Introducción a la retención", en este artículo se incluyen los pasos de introducción para todas las capacidades de gobierno de la información, que incluyen la retención.
- [Cree etiquetas de retención para excepciones a las directivas](create-retention-labels-information-governance.md) de retención: nuevo escenario identificado para usar etiquetas de retención para el gobierno de la información en lugar de la administración de registros.
- [Obtenga información sobre los buzones de](archive-mailboxes.md) archivo: nuevo, para admitir la reestructuración, contiene información conceptual que se encontraba anteriormente en Habilitar buzones de archivo.

### <a name="microsoft-priva"></a>Microsoft Priva

- [La administración de privacidad ahora es Microsoft Priva](/privacy/priva/priva-overview) : actualizada para cambiar el nombre del producto y sus soluciones, Priva Privacy Risk Management y Priva Subject Rights Requests.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Compatibilidad con los nuevos [roles y grupos de roles de MIP](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels), ahora en versión preliminar.
- Nuevas [funcionalidades de supervisión](apply-sensitivity-label-automatically.md#monitoring-your-auto-labeling-policy) para directivas de etiquetado automático.
- Ahora, implementando: etiqueta predeterminada para documentos existentes en Canal actual (versión preliminar) y texto de justificación para Office en la Web.
- Anunciado para el canal de Semi-Annual Enterprise de julio con versión 2202+: Co-autoría y auditoría para Outlook.

## <a name="december-2021"></a>Diciembre de 2021

### <a name="compliance-and-service-assurance"></a>Cumplimiento y garantía de servicio

- [Azure, Dynamics 365 y Windows](/compliance/regulatory/gdpr-breach-notification) notificación de infracción en el RGPD: se actualiza para aclarar que los clientes no necesitan usar un servicio de pago como Defender for Cloud para recibir notificaciones de seguridad y privacidad

### <a name="ediscovery"></a>eDiscovery

- [Advanced eDiscovery flujo de trabajo de contenido en Microsoft Teams](teams-workflow-in-advanced-ediscovery.md#reference-guide): se actualiza con una nueva guía de referencia rápida descargable para administrar Teams contenido en Advanced eDiscovery

### <a name="information-governance"></a>Información de gobierno

- [Habilitar buzones de archivo en el centro de cumplimiento](enable-archive-mailboxes.md#run-diagnostics-on-archive-mailboxes) : sección agregada sobre la nueva herramienta de diagnóstico para buzones de archivo
- [Usar la carga de red para importar los archivos PST](use-network-upload-to-import-pst-files.md#step-2-upload-your-pst-files-to-microsoft-365) de la organización a Microsoft 365: la importación de PST ahora es compatible con AzCopy v10
- [Restaurar un buzón inactivo](restore-an-inactive-mailbox.md) : procedimiento revisado para restaurar un buzón inactivo agregando primero LegacyExchangeDN de buzón inactivo al buzón de destino

### <a name="information-protection"></a>Protección de la información

- [Implementar una solución de MIP](information-protection-solution.md): nueva guía paso a paso para los clientes que buscan una guía básica prescriptiva para implementar Microsoft Information Protection (MIP)

### <a name="retention-and-records-management"></a>Administración de registros y retención

- Nueva guía sobre [cuánto tiempo se tarda en que las directivas de retención entren en vigor](create-retention-policies.md#how-long-it-takes-for-retention-policies-to-take-effect)
- Nueva configuración de inquilino: una configuración de administración de registros que impide la edición de propiedades de elementos SharePoint etiquetados que se marcan como registro y bloqueados, y otra configuración para impedir que los usuarios desbloqueen elementos marcados como registro

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- El etiquetado obligatorio y una etiqueta predeterminada para Power BI están disponibles por lo general (GA)

## <a name="november-2021"></a>Noviembre de 2021

### <a name="compliance-manager"></a>Administrador de cumplimiento

Las nuevas actualizaciones de contenido se pueden ver en [Novedades del Administrador de cumplimiento de Microsoft](compliance-manager-whats-new.md).

### <a name="device-onboarding"></a>Incorporación de dispositivos

Se agregaron los siguientes artículos para la incorporación de dispositivos:

- [Incorporar dispositivos macOS en la información general de Microsoft 365 (versión preliminar)](device-onboarding-macos-overview.md)
- [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante Intune (versión preliminar)](device-onboarding-offboarding-macos-intune.md)
- [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante Intune para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-intune-mde.md)
- [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante JAMF Pro (versión preliminar)](device-onboarding-offboarding-macos-jamfpro.md)
- [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-jamfpro-mde.md)

### <a name="ediscovery"></a>eDiscovery

- [Use el nuevo formato de caso en Advanced eDiscovery](advanced-ediscovery-new-case-format.md) nuevo formato de caso se publicó a disponibilidad general y cambió el nombre de "formato de caso grande"

### <a name="retention-and-records-management"></a>Administración de registros y retención
- Implementar: nueva configuración de administración de registros que controla si los SharePoint y OneDrive pueden ser eliminados por los usuarios. Anteriormente, las etiquetas de retención configuradas para retener contenido y que no marcaban elementos como registros impedía a los usuarios eliminar contenido etiquetado en SharePoint cuando esta acción se permitía en OneDrive. Para obtener más información, vea [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Se agregaron los siguientes artículos nuevos:

- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md)
- [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md)
- [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md)
- [Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-create-schema.md)
- [Aplicar hash y cargar la tabla de origen de información confidencial para los datos exactos que coincidan con los tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md)
- [Crear un paquete de reglas o tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-create-rule-package.md)
- [Probar un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md)
- [Administrar el esquema exacto de coincidencia de datos](sit-use-exact-data-manage-schema.md)
- [Actualizar el archivo de tabla de origen de información confidencial](sit-use-exact-data-refresh-data.md)

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad
- El nombre de ámbito de las [etiquetas de Azure Purview](/azure/purview/create-sensitivity-label) ahora es "Activos de datos esquematizados".

## <a name="october-2021"></a>Octubre de 2021

### <a name="app-governance"></a>Gobierno de aplicaciones

- [El complemento de gobierno de aplicaciones para Defender para Aplicaciones en la nube se ha publicado a la disponibilidad general](/cloud-app-security/app-governance-manage-app-governance). La documentación de gobierno de aplicaciones se ha movido para unirse a la documentación de Defender for Cloud Apps.

### <a name="compliance--service-assurance"></a>Garantía de & cumplimiento

- [Garantía de servicio](/compliance) : revisión trimestral de actualizaciones de contenido para certificaciones e instrucciones de aplicabilidad) Administración de activos del centro de datos
  - Arquitectura e infraestructura del centro de datos
  - Continuidad empresarial del centro de datos y recuperación ante desastres
  - Protecciones del entorno del centro de datos
  - Seguridad de acceso físico del centro de datos
  - Microsoft 365 de cumplimiento de SDL
  - Control de acceso de los ingenieros de servicio de Microsoft 365
  - Guía de evaluación de riesgos para MS Cloud

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- [Obtenga información sobre la prevención de pérdida de](endpoint-dlp-learn-about.md) datos se actualizó para la compatibilidad con macOS y la clasificación avanzada; actualizada para crear una directiva DLP personalizada para auditar la actividad de todos los tipos de archivo admitidos.
- [Introducción a la Microsoft 365 prevención](endpoint-dlp-getting-started.md) de pérdida de datos de punto de conexión se actualizó para la compatibilidad con macOS y la clasificación avanzada.
- [El uso de la prevención de pérdida de datos de](endpoint-dlp-using.md) endpoint se actualizó para la compatibilidad con macOS y la clasificación avanzada.
- [La referencia de sugerencias de directiva de prevención de](dlp-policy-tips-reference.md) pérdida de datos se actualizó para la compatibilidad con macOS y la clasificación avanzada.
- [La incorporación de dispositivos macOS Microsoft 365 (versión preliminar)](device-onboarding-macos-overview.md) se actualizó para la compatibilidad con macOS y la clasificación avanzada.
- Se agregaron las siguientes páginas nuevas para dispositivos de incorporación:
  - [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante Intune (versión preliminar)](device-onboarding-offboarding-macos-intune.md)
  - [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante Intune para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-intune-mde.md)
  - [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante JAMF Pro (versión preliminar)](device-onboarding-offboarding-macos-jamfpro.md)
  - [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-jamfpro-mde.md)

### <a name="ediscovery"></a>eDiscovery

- Recopilar datos adjuntos en la nube en [Advanced eDiscovery](advanced-ediscovery-cloud-attachments.md) además de recopilar la versión más reciente de los datos adjuntos de la nube, puede recopilar la versión que se compartió en un mensaje de correo electrónico o una conversación de chat de Teams; la nueva capacidad de aplicar automáticamente una etiqueta de retención a los datos adjuntos de la nube permite recopilar la versión compartida.
- [Advanced eDiscovery Configure](advanced-ediscovery-historical-versions.md) versiones históricas en una nueva funcionalidad que indiza todas las versiones de documentos almacenados en un sitio de SharePoint para la búsqueda; esto significa que las versiones de documentos que contienen contenido que coincide con una consulta de colección se devuelven en los resultados de la búsqueda.

### <a name="encryption"></a>Cifrado

- [Usar el cifrado de un](/microsoftteams/teams-end-to-end-encryption) extremo a otro para las llamadas de Microsoft Teams (versión preliminar pública) Nuevo contenido para la versión preliminar pública.

### <a name="information-governance"></a>Información de gobierno

- Configurar un conector para importar datos de auditoría [de EHR](import-epic-data.md) épicos le permite importar datos del sistema de registros electrónicos de atención médica de Epic para admitir un nuevo escenario general de uso incorrecto de datos de pacientes para la administración de riesgos de información interna.
- [Configurar un](import-healthcare-data.md) conector para importar datos de auditoría ehr de atención sanitaria nuevo conector le permite importar datos de un sistema de registros de salud electrónicos para admitir un nuevo escenario general de uso incorrecto de datos de pacientes para la administración de riesgos internas.

### <a name="retention-and-records-management"></a>Administración de registros y retención
- [Los ámbitos de directivas adaptables](retention.md#adaptive-or-static-policy-scopes-for-retention) se liberan en versión preliminar para directivas de retención y directivas de etiquetas de retención.
- Ahora puede aplicar [automáticamente una etiqueta de retención basada en una etiqueta de confidencialidad](apply-retention-labels-automatically.md#identify-files-and-emails-that-have-a-sensitivity-label).
- Plan de archivos tiene un nuevo [proceso de importación](file-plan-manager.md#import-retention-labels-into-your-file-plan).
- [Configuración común para directivas](retention-settings.md) de retención y directivas de etiquetas de retención: nuevo artículo para obtener información detallada sobre la configuración de ámbitos adaptables y otras opciones de configuración tanto en directivas de retención como en directivas de etiquetas de retención.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

- [Obtenga información sobre el nuevo contenido de entidades con nombre (](named-entities-learn.md) versión preliminar) para entidades con nombre.
- [Use entidades con nombre en el nuevo](named-entities-use.md) contenido de las directivas de prevención de pérdida de datos (versión preliminar) para usar entidades con nombre.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- [Las etiquetas predeterminadas y las directivas](mip-easy-trials.md) predeterminadas se están implementando para los clientes elegibles.

## <a name="september-2021"></a>Septiembre de 2021

### <a name="app-governance"></a>Gobierno de aplicaciones

- [La información de introducción al gobierno de aplicaciones optimizada](app-governance-get-started.md) ha cambiado el flujo de trabajo y ha agregado nuevos vínculos al registro de vista previa pública
- [Nueva definición de alertas](app-governance-anomaly-detection-alerts.md#app-made-high-volume-of-importance-mail-read-and-created-inbox-rule) de detección agregada (actualizada; se agregó una nueva definición para alertas de colección)

### <a name="auditing"></a>Auditoría

- [Activar o desactivar la auditoría se](turn-audit-log-search-on-or-off.md) agregó una nueva sección sobre cómo se auditan los cambios en el estado de auditoría de una organización; esto significa que los registros de auditoría se registran cuando la auditoría está activada o desactivada; puede buscar en el registro Exchange de auditoría de administración para estos registros de auditoría

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

- [Cumplimiento de la comunicación con la guía de soluciones SIEM](communication-compliance-siem.md) para la integración de cumplimiento de comunicaciones con soluciones SIEM)

### <a name="compliance-offerings"></a>Ofertas de cumplimiento

- [Seguridad en la nube de varios niveles (MTCS)](/compliance/regulatory/offering-mtcs-singapore) Actualizaciones estándar para Singapur para cobertura de Dynamics 365
- [Sector de tarjetas de pago (PCI)](/compliance/regulatory/offering-pci-dss) Actualizaciones del estándar de seguridad de datos (DSS) para SharePoint cobertura en línea
- Nueva guía de software de cliente de [la sección 508](/compliance/regulatory/offering-section-508-vpats) de EE. UU.
- [Directrices de accesibilidad de contenido web](/compliance/regulatory/offering-wcag-2-1) nuevas instrucciones de software de cliente

### <a name="compliance--service-assurance"></a>Garantía de & cumplimiento

- [Control de servicio](/compliance/) revisa trimestralmente las actualizaciones de contenido para las certificaciones y las instrucciones de aplicabilidad
  - Destrucción de dispositivos que contienen datos
  - Ataques DDOS

### <a name="data-connectors"></a>Conectores de datos

- [Archivar datos de terceros en Microsoft 365](archiving-third-party-data.md#data-connectors-in-the-us-government-cloud) conectores de datos de CellTrust y 17a-4 LLC ahora disponibles en organizaciones GCC en la nube del Gobierno de Estados Unidos
- [Configurar un conector para archivar datos de YouTube](archive-youtube-data.md) proporciona nuevas instrucciones para esta característica en la versión preliminar pública.

### <a name="ediscovery"></a>eDiscovery

- Use el [editor de KQL](ediscovery-kql-editor.md) para crear consultas de búsqueda de vista previa pública de una nueva forma de crear consultas de búsqueda en búsqueda de contenido, exhibición de documentos electrónicos principales y Advanced eDiscovery; el editor de KQL proporciona autocompleción para las propiedades y condiciones compatibles con búsquedas y muestra listas de valores admitidos para las propiedades y condiciones estándar; el editor KQL también proporciona detección de errores y sugerencias para corregir posibles errores en consultas de búsqueda

### <a name="information-barriers"></a>Barreras de información

- [Introducción a las barreras de información](information-barriers-policies.md#step-6-information-barriers-modes) nueva característica de vista previa para los modos de barreras de información
- [Barreras de información con Microsoft Teams](/microsoftteams/information-barriers-in-teams) nueva característica de vista previa para los modos de barreras de información
- [Barreras de información con OneDrive](/onedrive/information-barriers) nueva característica de vista previa para los modos de barreras de información
- [Barreras de información con SharePoint nueva](/sharepoint/information-barriers) característica de vista previa en línea para los modos de barreras de información

### <a name="insider-risk-management"></a>Administración de riesgos internos

- [Introducción a la nueva característica de vista](insider-risk-management-configure.md#recommended-actions-preview) previa de administración de riesgos insider para empezar a usar las acciones recomendadas
- [Investigar actividades de riesgo interno](insider-risk-management-activities.md#get-help-managing-your-insider-risk-alert-queue) nueva sección de instrucciones "Obtener ayuda para administrar la cola de alertas de riesgo de insider"
- [Introducción a la configuración de administración de riesgos insider](insider-risk-management-settings.md#admin-notifications) nueva característica de vista previa de la configuración de notificaciones de administrador

### <a name="retention-and-records-management"></a>Administración de registros y retención
- [La revisión de disposición de varias](disposition.md) fases ya está disponible generalmente (GA), con nuevos eventos [de auditoría](search-the-audit-log-in-security-and-compliance.md#disposition-review-activities). La revisión de disposición de varias fases permite especificar hasta cinco fases consecutivas de revisión de disposición para una etiqueta de retención y los revisores pueden agregar otros usuarios a su fase de revisión de eliminación. También puede personalizar las notificaciones por correo electrónico y los avisos.
- Los canales [privados para Teams directivas de](create-retention-policies.md#retention-policy-for-teams-locations) retención están disponibles por lo general (GA).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad
- [La co-autoría y autoguardado](sensitivity-labels-coauthoring.md) ahora están disponibles (GA) para Windows (versión mínima de 2107 desde canal actual o canal de Enterprise mensual) y macOS (versión mínima de 16.51).
- Implementación para aplicaciones Office que usan etiquetas integradas: la configuración de etiqueta predeterminada ahora admite documentos existentes, así como documentos nuevos. Este cambio de comportamiento proporciona paridad con el cliente de unificación de etiquetado de Azure Information Protection. Para obtener más información sobre el lanzamiento por aplicación y las versiones mínimas, vea la [tabla de funciones](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint) para Word, Excel y PowerPoint.
- Las etiquetas de contenedor ahora [admiten la configuración predeterminada de vínculos de uso compartido mediante la configuración avanzada de PowerShell](sensitivity-labels-teams-groups-sites.md#configure-settings-for-the-default-sharing-link-type-for-a-site-by-using-powershell-advanced-settings).
- Las [tablas de](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) funcionalidades que muestran las versiones mínimas admitidas para el etiquetado integrado ahora tienen versiones para El canal actual, el canal de Enterprise mensual y el canal Semi-Annual Enterprise integrado.
