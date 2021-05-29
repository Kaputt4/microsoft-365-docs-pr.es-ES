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
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Ya sea que agregue nuevas soluciones al centro de cumplimiento, actualice las características existentes según sus comentarios o implemente documentación actualizada y actualizada, Microsoft 365 le ayudará a mantenerse al tanto del panorama de cumplimiento en constante cambio. Descubra lo que hemos estado haciendo hasta este mes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f249108dba279e255efd57ecd56159d3c71dcb4b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706623"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novedades de Cumplimiento de Microsoft 365

Ya sea agregar nuevas soluciones al centro de cumplimiento de [Microsoft 365,](microsoft-365-compliance-center.md)actualizar las características existentes en función de sus comentarios o implementar documentación actualizada y actualizada, Microsoft 365 le ayudará a mantenerse al tanto del cambiante panorama de cumplimiento. Echa un vistazo a continuación para ver las novedades de Microsoft 365 cumplimiento actual.

> [!NOTE]
> Algunas características de cumplimiento se implantan a diferentes velocidades para nuestros clientes. Si aún no ve una característica, intente agregarse a la [versión dirigida](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> ¿Te interesa lo que sucede en otros centros de administración? Consulte estos artículos:<br>[Novedades del Centro de administración Microsoft 365 administración](/office365/admin/whats-new-in-preview)<br>[Novedades del Centro de administración SharePoint administración](/sharepoint/what-s-new-in-admin-center)<br>[Novedades de Microsoft 365 Defender](../security/defender/whats-new.md)<br><br>
Y visite la [guía básica](https://www.microsoft.com/microsoft-365/roadmap) de Microsoft 365 para obtener información sobre Microsoft 365 características que se iniciaron, se están implementando, están en desarrollo, se cancelaron o se publicaron anteriormente.

## <a name="april-2021"></a>Abril de 2021

### <a name="advanced-ediscovery"></a>eDiscovery avanzado

- [Límites en Advanced eDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set). Las organizaciones ahora pueden exportar hasta 5 millones de elementos o 500 MB, lo que sea menor, en una sola exportación de elementos de un conjunto de revisión.

### <a name="data-classification"></a>Clasificación de datos

- [Actividades de etiquetado que están disponibles en el Explorador de actividades](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>Conectores de datos

- [Configurar un conector para archivar datos de Cisco Jabber en Oracle](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [Configurar un conector para archivar datos de Cisco Jabber en PostgreSQL](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- Nuevo tema para [referencia de sugerencias de directiva de prevención de](/microsoft-365/compliance/dlp-policy-tips-reference)pérdida de datos .
- Nuevo tema para [Obtener información sobre la prevención de pérdida de datos](/microsoft-365/compliance/dlp-learn-about-dlp).
- Nuevo tema para [Introducción al panel de alertas de](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)prevención de pérdida de datos .

### <a name="retention-policies-and-retention-label-policies"></a>Directivas de retención y directivas de etiquetas de retención

- La ubicación Microsoft 365 Groups ahora admite la aplicación de la configuración de retención Microsoft 365 solo Microsoft 365 buzones o simplemente los sitios SharePoint conectados mediante el cmdlet [Set-RetentionCompliancePolicy PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy) con el parámetro *Applications.*

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Outlook versiones y actualizaciones:
- [Ahora se admiten](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) diferentes opciones de configuración para la etiqueta predeterminada y el etiquetado obligatorio para el etiquetado integrado. Anteriormente, esta configuración solo era compatible con el cliente de etiquetado unificado AIP.
- [Encrypt-Only](encryption-sensitivity-labels.md#let-users-assign-permissions) ahora es compatible con macOS, iOS y Android.
- [El etiquetado obligatorio se](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) está implementando en las plataformas restantes.
- [Los marcados dinámicos con todas las variables](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) se admiten en todos los Outlook cliente.

## <a name="march-2021"></a>Marzo de 2021

Estos son algunos de los cambios realizados en Microsoft 365 de cumplimiento normativo y contenido para el mes de marzo.

### <a name="advanced-ediscovery"></a>eDiscovery avanzado

- **Advanced eDiscovery colecciones ahora** admiten la [nueva herramienta de colecciones y el flujo de trabajo](/microsoft-365/compliance/collections-overview). Otros temas nuevos incluyen [crear una colección borrador,](https://docs.microsoft.com/microsoft-365/compliance/create-draft-collection) [confirmar un borrador de](/microsoft-365/compliance/commit-draft-collection)colección en un conjunto de revisión y [estadísticas e informes de colección.](/microsoft-365/compliance/collection-statistics-reports)
- **Exporte documentos** en un conjunto de revisión en una [Azure Storage](/microsoft-365/compliance/download-export-jobs) cuenta.
- **Módulo de codificación predictiva para Advanced eDiscovery**. Primero vea la nueva funcionalidad [de codificación predictiva](/microsoft-365/compliance/predictive-coding-overview) que reemplaza al módulo relevancia retirado.

### <a name="data-classification"></a>Clasificación de los datos

- **Explorador de clasificación de datos**. [Introducción al](/microsoft-365/compliance/data-classification-activity-explorer) explorador de clasificación de datos.

### <a name="data-connectors"></a>Conectores de datos

- **Claves privadas**. Se ha agregado compatibilidad con claves privadas a los datos de mensajes [de Bloomberg,](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) los datos de [chat](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) ice y los conectores [de datos de Instant Bloomberg.](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys)

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- **Microsoft Teams compatibilidad con**. Compatibilidad de prevención de pérdida de datos extendida [a Microsoft Teams](/microsoft-365/compliance/dlp-teams-default-policy).
- **Extensión de cumplimiento de Microsoft**. Introducción a la extensión [de cumplimiento de Microsoft](/microsoft-365/compliance/dlp-chrome-get-started).

### <a name="encryption"></a>Cifrado

- **Clave de cliente para Microsoft 365**. [Información general sobre la clave de](/microsoft-365/compliance/customer-key-tenant-level) cliente Microsoft 365 en el nivel de inquilino (versión preliminar pública).
- **Cifrado de clave doble**. Obtenga más información sobre [cómo habilitar la compatibilidad con documentos](/microsoft-365/compliance/double-key-encryption) etiquetados y protegidos en SharePoint y OneDrive para la Empresa.

### <a name="insider-risk-management"></a>Administración de riesgos internos

Las siguientes actualizaciones de características de administración de riesgos insider se publicaron para la versión preliminar pública en marzo:

- Nueva característica de análisis para identificar riesgos antes de crear directivas de riesgo de insider
- Nueva administración y soporte de detección de secuencias de actividad de riesgo
- Nueva compatibilidad acumulativa de detección de exfiltración
- Nueva compatibilidad con recomendaciones y informes de estado de directivas desde la aplicación
- Nueva característica de registro de auditoría e informes
- Mejoras en el asistente para la creación de directivas
- Actualizaciones del explorador de contenido
- Nuevo proceso de administración de usuarios/soporte técnico (agregar o quitar usuarios de directivas)
- Nueva compatibilidad con la integración de AAD (compatibilidad con directivas de usuario de salida)
- Compatibilidad de dominio actualizada en directivas (REGEX)
- Mejoras y mejoras de plantillas de directiva

Los siguientes temas se actualizaron o agregaron para admitir estas nuevas características:

- [Información sobre riesgos internos de Microsoft](/microsoft-365/compliance/insider-risk-management)
- [Planificar la administración de riesgos internos](/microsoft-365/compliance/insider-risk-management-plan)
- [Introducción a la configuración de administración de riesgos de insider](/microsoft-365/compliance/insider-risk-management-settings)
- [Introducción a la administración de riesgos internos](/microsoft-365/compliance/insider-risk-management-configure)
- [Crear y administrar directivas de riesgos internos](/microsoft-365/compliance/insider-risk-management-policies)
- [Investigar alertas de riesgos internos](/microsoft-365/compliance/insider-risk-management-alerts)
- [Tomar medidas en casos de riesgos internos](/microsoft-365/compliance/insider-risk-management-cases)
- [Revisar actividades con el registro de auditoría de riesgo interno](/microsoft-365/compliance/insider-risk-management-audit-log)
- [Revisar datos con el explorador de contenido de riesgos internos](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [Administrar el flujo de trabajo con el Panel de usuarios](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>Administración de registros

- **Mejoras del plan de archivos**. Una actualización del [plan de](file-plan-manager.md) archivos elimina o mejora las restricciones de longitud anteriores para la importación.
- **Eliminar etiquetas de retención para registros**. Una versión preliminar admite la capacidad de eliminar [etiquetas de](create-apply-retention-labels.md#deleting-retention-labels) retención que marcan elementos como registros.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

El contenido se agregó o actualizó en los temas siguientes:

- [Introducción al tipo de información confidencial personalizada](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [Obtener más información acerca de los tipos de información confidencial](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Crear un tipo de información confidencial personalizado con clasificación basada en coincidencia exacta de datos](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Crear notificaciones para actividades exactas de coincidencia de datos](/microsoft-365/compliance/sit-edm-notifications-activities)
- [Definiciones de entidad de tipo de información confidencial](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [Crear un tipo de información confidencial personalizada con PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Crear un diccionario de palabras clave](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- **Compatibilidad con DoD**. Compatibilidad con inquilinos gubernamentales de Estados Unidos con entornos DoD.
- **Encrypt-Only para Outlook**. Las opciones de cifrado Outlook ahora incluyen Encrypt-Only cuando selecciona Permitir que [los usuarios asignen permisos.](encryption-sensitivity-labels.md#let-users-assign-permissions)
- **Aplicar etiquetas integradas en Office aplicaciones**. Instrucciones [actualizadas](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) sobre cómo aplicar etiquetas integradas en Office aplicaciones cuando tenga instalado el cliente de etiquetado unificado de Azure Information Protection.

## <a name="february-2021"></a>Febrero de 2021

Estos son algunos de los cambios realizados en Microsoft 365 de cumplimiento normativo y contenido para el mes de febrero.

### <a name="auditing"></a>Auditoría

- **Administrar directivas de retención de registros de auditoría**. Obtenga más información sobre el nuevo panel [De directivas de retención de auditoría.](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)
- **Busque en el registro de auditoría**. [Use el script de PowerShell para buscar en el registro de auditoría](/microsoft-365/compliance/audit-log-search-script).

### <a name="data-classification-content-explorer"></a>Explorador de contenido de clasificación de datos

El contenido se agregó o actualizó en los temas siguientes:

- [Introducción al explorador de contenido](/microsoft-365/compliance/data-classification-content-explorer)
- [Notas de la versión de clasificación de datos](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

El contenido se agregó o actualizó en los temas siguientes:

- [Obtenga información sobre DLP de extremo](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Enviar notificaciones de email y mostrar sugerencias para directivas DLP](https://docs.microsoft.com/microsoft-365/compliance/use-notifications-and-policy-tips)
- [Obtenga información sobre el Microsoft 365 de prevención de pérdida de datos local](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Introducción al escáner local de prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Crear una directiva DLP para proteger documentos con FCI u otras propiedades](https://docs.microsoft.com/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Uso de la prevención de pérdida de datos en punto de conexión](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-using)
- [Introducción a la prevención de pérdida de datos en punto de conexión](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>eDiscovery

El contenido se agregó o actualizó en los temas siguientes:

- [Descifrado en Microsoft 365 herramientas de exhibición de documentos electrónicos](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-decryption)
- [Consultas de palabras clave y condiciones de búsqueda](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Retiro del módulo Relevancia en Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/relevance-module-retirement)
- [Usar un script para agregar usuarios a una retención en un caso de exhibición de documentos electrónicos principal](https://docs.microsoft.com/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Cifrado

El contenido se agregó o actualizó en los temas siguientes:

#### <a name="azure-rights-management-service-rms"></a>Azure Rights Management Servicio (RMS)

- [Características de cifrado administradas por el cliente](https://docs.microsoft.com/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online cifrado de correo electrónico con AD RMS](https://docs.microsoft.com/microsoft-365/compliance/information-rights-management-in-exchange-online). La compatibilidad con este servicio ha quedado en desuso. Ya no puede usar AD RMS en un entorno Exchange híbrido. En su lugar, migre a Azure RMS.

#### <a name="customer-key"></a>Clave de cliente

- [Clave de cliente para Microsoft 365 en el nivel de inquilino](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level)
- [Información general sobre seguridad y cumplimiento](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>Information Rights Management (IRM)

- [Aplicar Information Rights Management (IRM) a una lista o biblioteca.](https://docs.microsoft.com/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Estas nubes nacionales no admiten esta configuración:
    - Microsoft Cloud for US Government
    - Microsoft Cloud Alemania
    - Azure y Microsoft 365 operados por 21Vianet en China)
- [Configure IRM para que use un servidor de AD RMS local.](https://docs.microsoft.com/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) La compatibilidad con este servicio en un entorno Exchange híbrido ha quedado en desuso.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

El contenido se agregó o actualizó en los temas siguientes:

- [Obtener más información acerca de los tipos de información confidencial](https://docs.microsoft.com/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Crear un tipo de información confidencial personalizado con PowerShell](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Crear tipos de información confidencial personalizados con clasificación basada en coincidencia exacta de datos](https://docs.microsoft.com/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Definiciones de entidad de tipos de información confidencial](https://docs.microsoft.com/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

El contenido se agregó o actualizó en los temas siguientes:

- **SharePoint uso compartido externo**. En [el caso de las etiquetas](sensitivity-labels-teams-groups-sites.md) de contenedor, la opción de uso compartido externo SharePoint sitios ya está disponible en general. Además, el centro Microsoft 365 administración y Planner ahora admiten la aplicación de estas etiquetas de confidencialidad. 
- **Coautoría y Autoguardado**. La compatibilidad [con la co-autoría y autoguardar](sensitivity-labels-coauthoring.md) archivos cifrados se libera como versión preliminar para las pruebas en inquilinos que no son de producción.

## <a name="january-2021"></a>Enero de 2021

### <a name="support-for-card-content-in-teams"></a>Compatibilidad con el contenido de tarjeta en Teams

Las siguientes Microsoft 365 de cumplimiento admiten ahora la detección de [contenido](/microsoftteams/platform/task-modules-and-cards/what-are-cards) de tarjeta generado a través de aplicaciones en Teams mensajes:

- **Core y Advanced eDiscovery**. El contenido de la tarjeta ahora se [puede colocar en espera](create-ediscovery-holds.md#preserve-card-content) o incluirse en las [búsquedas](/microsoftteams/ediscovery-investigation#search-for-card-content) (también se aplica a la búsqueda de contenido).
- **Auditar**. La actividad de la tarjeta se [registra ahora en el registro de auditoría.](/microsoftteams/audit-log-events#teams-activities)
- **Directivas de retención**. Ahora puede usar directivas de retención para [conservar y eliminar el contenido de la tarjeta.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Administración de registros y gobierno de la información

[Nueva evaluación para](retention-regulatory-requirements.md#new-zealand-public-records-act) abordar el uso del gobierno de la información y la administración de registros para ayudar a cumplir las obligaciones de cumplimiento de la Ley de registros públicos de Nueva Zelanda.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Las etiquetas de confidencialidad ahora se admiten para los inquilinos del Gobierno de Estados Unidos (GCC y GCC-H).
- Nueva [compatibilidad con el etiquetado](sensitivity-labels-office-apps.md) automático para macOS.

## <a name="december-2020"></a>Diciembre de 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Spotlight: Nuevo contenido para soluciones de riesgo de insider

El Microsoft 365 de contenido de cumplimiento es muy difícil crear documentos de "solución de contenido" para promover la forma en que las capacidades de cumplimiento se pueden usar conjuntamente para ayudar a cumplir los objetivos de cumplimiento.

En primer lugar, se trata de contenido que une nuestras soluciones de riesgo de información privilegiada: cumplimiento de comunicaciones, administración de riesgos de información privilegiada, barreras de información y administración de acceso con privilegios. Este es un vistazo a lo que encontrará:

- [Nueva página de aterrizaje para soluciones de riesgo de insider](insider-risk-solution-overview.md). Incluye detalles sobre los riesgos que las soluciones pueden ayudar a mitigar, los requisitos de licencias, la secuencia de implementación, las ilustraciones de arquitectura, los recursos de aprendizaje y mucho más.
- Nuevos artículos de información general para cada solución de riesgos de insider. Guía y vínculos a artículos que le ayudan a aprender, planear, implementar y administrar cada solución:
  - [Cumplimiento de las comunicaciones](communication-compliance-solution-overview.md)
  - [Administración de riesgos internos](insider-risk-management-solution-overview.md)
  - [Barreras de información](information-barriers-solution-overview.md)
  - [Administración del acceso con privilegios](privileged-access-management-solution-overview.md)
  
Más documentos de solución de contenido próximamente!

### <a name="advanced-ediscovery"></a>eDiscovery avanzado

Flujo de trabajo y funcionalidad mejorados para [agregar custodios](add-custodians-to-case.md) y orígenes de datos no [custodiados](non-custodial-data-sources.md) a un Advanced eDiscovery caso.

### <a name="data-connectors"></a>Conectores de datos

[Se han lanzado cuatro nuevos conectores de Veritas:](archiving-third-party-data.md#third-party-data-connectors)Redtail Speak, Salesforce Chatter, ServiceNow y Yieldbroker.

### <a name="encryption"></a>Cifrado

Introducción a [la clave de cliente para Microsoft 365 en el nivel de inquilino](customer-key-tenant-level.md). Con las claves que proporcione, puede crear una directiva de cifrado de datos (DEP) y asignarla al inquilino. El DEP cifra los datos en todo el espacio empresarial para estas cargas de trabajo:

- Teams de chat (chats de 1:1, chats de grupo, chats de reunión y conversaciones de canal)
- Teams multimedia (imágenes, fragmentos de código, vídeos, imágenes wiki)
- Teams de llamadas y reuniones almacenadas en Teams almacenamiento
- Teams de chat
- Teams sugerencias de chat de Cortana
- Teams de estado
- Información de usuario y señal para Exchange Online

### <a name="records-management"></a>Administración de registros

El [grupo de funciones de administración administración](get-started-with-records-management.md#permissions-required-for-records-management) de registros ahora concede permisos para todas las características de administración de registros, incluida la revisión de disposición.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- [Etiquetar automáticamente los datos en Azure Purview (versión preliminar).](/azure/purview/create-sensitivity-label) Ahora puede crear y aplicar automáticamente etiquetas de confidencialidad a activos de Azure Purview, como archivos en Azure Blob Storage y columnas de base de datos en SQL Server.
- [Requerir que los usuarios apliquen una etiqueta a los elementos](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents). Esta nueva opción, también conocida como "etiquetado obligatorio", requiere que los usuarios elijan y apliquen una etiqueta de confidencialidad en los escenarios específicos.
