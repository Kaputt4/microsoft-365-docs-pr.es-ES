---
title: Novedades de las soluciones de cumplimiento y riesgo de Microsoft Purview
description: Ya sea agregando nuevas soluciones al centro de cumplimiento, actualizando las características existentes en función de sus comentarios o implementando documentación actualizada y actualizada, Microsoft Purview le ayuda a mantenerse al tanto del cambiante panorama de cumplimiento. Averigüe lo que hemos estado haciendo hasta este mes.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
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
- purview-compliance
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 70ba18d1471ea5fc5d145f64b68c6fef1691124c
ms.sourcegitcommit: 3d7dd25abcbf923b45eae84ff4d9d2bb95ef4ca4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "68777641"
---
# <a name="whats-new-in-microsoft-purview-risk-and-compliance-solutions"></a>Novedades de las soluciones de cumplimiento y riesgo de Microsoft Purview

Ya sea agregando nuevas soluciones a la [portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center.md), actualizando las características existentes en función de sus comentarios o implementando documentación actualizada y actualizada, Microsoft 365 le ayuda a mantenerse al tanto del cambiante panorama de cumplimiento. Eche un vistazo a continuación para ver las novedades de Microsoft Purview hoy en día.

> [!NOTE]
> Algunas características de cumplimiento se implantan a diferentes velocidades para nuestros clientes. Si aún no ve una característica, intente agregarse a la [versión de destino](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> ¿Te interesa lo que sucede en otros centros de administración? Consulte estos artículos:
>
> - [Novedades de la Centro de administración de Microsoft 365](/office365/admin/whats-new-in-preview)
> - [Novedades del Centro de administración de SharePoint](/sharepoint/what-s-new-in-admin-center)
> - [Novedades de Microsoft 365 Defender](../security/defender/whats-new.md)
>
> Y visite la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener información sobre las características de Microsoft 365 que se lanzaron, se están implementando, están en desarrollo, se han cancelado o publicado anteriormente.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="october-2022"></a>Octubre de 2022

### <a name="communication-compliance"></a>Cumplimiento de las comunicaciones

- **En versión preliminar**: nueva integración de cumplimiento de comunicaciones [con la administración de riesgos internos](/microsoft-365/compliance/communication-compliance#integration-with-insider-risk-management-preview). El cumplimiento de comunicaciones ahora puede proporcionar señales de riesgo detectadas en los mensajes a las directivas de administración de riesgos internos. Los usuarios de riesgo detectados en los mensajes por la directiva de cumplimiento de comunicaciones actúan como un evento desencadenante para que los usuarios entren en el ámbito de las directivas de administración de riesgos internos.

### <a name="insider-risk-management"></a>Administración de riesgos internos

- **En versión preliminar**: Insider Risk Management presenta [pruebas forenses](/microsoft-365/compliance/insider-risk-management-forensic-evidence), que permiten capturar actividades visuales personalizables en todos los dispositivos para ayudar a su organización a mitigar, comprender y responder mejor a posibles riesgos de datos, como la filtración de datos no autorizados de datos confidenciales.
- **En versión preliminar**: integración de administración de riesgos internos [con cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance#integration-with-insider-risk-management-preview) al usar las *fugas de datos por parte de usuarios de riesgo* o *infracciones de directivas de seguridad por plantillas de directiva de usuarios de riesgo* . El cumplimiento de comunicaciones ahora puede proporcionar señales de riesgo detectadas en los mensajes a las directivas de administración de riesgos internos.
- **En versión preliminar**: la nueva [personalización de alertas insertadas](/microsoft-365/compliance/insider-risk-management-settings#inline-alert-customization-preview) permite a los analistas e investigadores editar rápidamente las directivas al revisar las alertas.
- Nuevas [actualizaciones de puntuación de contenido de prioridad](/microsoft-365/compliance/insider-risk-management-policies#prioritize-content-in-policies) que permiten elegir si se asignan puntuaciones de riesgo a todas las actividades detectadas por una directiva o solo las actividades que incluyen contenido prioritario.
- Los equipos de seguridad ahora pueden [personalizar un desencadenador de seguridad](/microsoft-365/compliance/insider-risk-management-policies#policy-templates) en la directiva de "fugas de datos" para que se muestre cuando un usuario realice una secuencia, lo que le permite responder a acciones del usuario que podrían considerarse más arriesgadas.
- Las nuevas actualizaciones ahora permiten a los equipos de seguridad crear [directivas con secuencias](/microsoft-365/compliance/insider-risk-management-policies#sequence-detection-preview) sin ninguna otra selección de indicador de directiva subyacente necesaria.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- **Disponibilidad general (GA):** [volver a etiquetar al final del período de retención](retention-settings.md#relabeling-at-the-end-of-the-retention-period).
- **Disponibilidad general (GA):** [iniciar un registro desbloqueado](declare-records.md#configuring-retention-labels-to-declare-records).
- **Disponibilidad general (GA):** los usuarios ahora pueden aplicar etiquetas de retención publicadas a los archivos [directamente en Teams](create-apply-retention-labels.md#applying-retention-labels-using-microsoft-365-groups).
- Nuevas instrucciones de soporte técnico de retención: las directivas de retención para Teams admiten el [chat con clips](https://support.microsoft.com/office/start-a-chat-in-teams-0c71b32b-c050-4930-a887-5afbe742b3d8?storagetype=live#bkmk_chatwithself) de [vídeo](https://support.microsoft.com/office/record-a-video-clip-in-teams-0c57dae5-2974-4214-9c46-7a2136386f1c) y características, y las directivas de retención para [las publicaciones de argumentos](https://support.microsoft.com/office/overview-of-storyline-for-yammer-and-viva-engage-530e4e66-9f1c-4be1-b371-08ea40dc4b69) de yammer.
- Experiencia mejorada en el producto si las directivas de retención tienen errores: ahora verá una descripción detallada del error en el panel de detalles, con acciones en el producto para realizar que puedan resolver el problema. Por ejemplo, quite las ubicaciones no válidas y vuelva a sincronizar la directiva.

### <a name="microsoft-priva"></a>Microsoft Priva

- **En versión preliminar**: [las directivas de transferencia de datos](/privacy/priva/risk-management-policy-data-transfer) de Privacy Risk Management ahora ofrecen condiciones de límite flexibles adicionales: detección de transferencias basadas en los atributos de Azure Active Directory de los usuarios, transferencias entre usuarios en diferentes grupos de Microsoft 365 y transferencias entre sitios de SharePoint.

### <a name="on-premises-scanner"></a>Escáner local
- **En versión preliminar**: se cambia el nombre del analizador local de Azure Information Protection (AIP) **Microsoft Purview Information Protection escáner** y [la configuración se mueve a la portal de cumplimiento Microsoft Purview](/information-protection/deploy-aip-scanner-configure-install).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad
- Llamada a la acción: [guía de migración](sensitivity-labels-aip.md) para ayudarle a pasar del complemento AIP para aplicaciones de Office, con un [cuaderno de estrategias de migración](https://microsoft.github.io/ComplianceCxE/playbooks/AIP2MIPPlaybook) de nuestro equipo de Ingeniería de la experiencia del cliente (CxE)
- **Disponibilidad general (GA):** contextos de autenticación para grupos de etiquetas [y configuración de sitio](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) que funcionan con directivas de acceso condicional de Azure AD para aplicar condiciones de acceso más estrictas a un sitio.
- **Disponibilidad general (GA):** [permisos de uso compartido de sitios mediante PowerShell](sensitivity-labels-teams-groups-sites.md#configure-site-sharing-permissions-by-using-powershell-advanced-settings).
- **Implementación**: [se respeta la prevención de la copia en el Portapapeles para los archivos etiquetados y cifrados en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations), con algunas excepciones para escenarios de reetiquetado.
- **En versión preliminar**: el complemento AIP para aplicaciones de Office está [deshabilitado de forma predeterminada](sensitivity-labels-aip.md#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps) y requiere una nueva configuración para invalidar este valor predeterminado.
- Instrucción de compatibilidad: [tipos de archivos admitidos para SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#supported-file-types), después de habilitar las etiquetas de confidencialidad para estos servicios.
- Nuevo [requisito previo para la coautoría](sensitivity-labels-coauthoring.md#prerequisites) y azure Information Protection cliente y analizador de etiquetado unificados: no se admite el uso del cifrado de doble clave en el mismo inquilino que la característica de coautoría.

## <a name="september-2022"></a>Septiembre de 2022

### <a name="communication-compliance"></a>Cumplimiento de las comunicaciones

- [Introducción al cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-configure): nuevas actualizaciones para las acciones recomendadas y la incorporación acelerada. Las acciones recomendadas pueden ayudar a su organización a empezar a trabajar rápidamente con el cumplimiento de las comunicaciones.
- [Investigar y corregir alertas de cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-investigate-remediate): nueva actualización de la compatibilidad con el resaltado de palabras clave para la vista de texto sin formato. El resaltado de palabras clave, que actualmente solo está disponible en inglés, puede ayudarle a dirigirse al área de interés en los mensajes largos y los datos adjuntos.
- [Usar informes y auditorías de cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-reports-audits): aclaraciones sobre los permisos necesarios para ver y administrar informes de cumplimiento de comunicaciones. Para ver y administrar informes, los usuarios deben estar asignados al grupo de roles *Visores de cumplimiento de comunicaciones* .
 
### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Lista de plantillas del Administrador de cumplimiento](/microsoft-365/compliance/compliance-manager-templates-list): nueva plantilla agregada para australiana Information Security Registered Assessor Program (IRAP) con ISM versión 3.5 - Official).

### <a name="data-classification"></a>Clasificación de datos

- [Aumentar la precisión del clasificador (versión preliminar):](data-classification-increase-accuracy.md) en este artículo se muestra cómo confirmar si los elementos coincidentes por un clasificador son verdaderos positivos (una coincidencia) o un falso positivo (no una coincidencia) y proporcionan comentarios de coincidencia o no coincidencia. Puede usar esos comentarios para ajustar los clasificadores para aumentar la precisión. También puede enviar a Microsoft las versiones redactadas del documento y los comentarios De coincidencia y no coincidencia si desea ayudar a aumentar la precisión de los clasificadores que proporciona Microsoft.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- En versión preliminar: las etiquetas de retención ahora admiten la ejecución de un flujo de Power Automate al final del período de retención para admitir acciones personalizadas e integración con otras soluciones. Para obtener más información, consulte [Personalización de lo que sucede al final del período de retención](retention-label-flow.md).
- Para los elementos de administración de registros sometidos a revisión de eliminación, al seleccionar ese elemento en el área Eliminación del portal de cumplimiento, una nueva columna Progreso muestra el estado del elemento. Ese estado puede ser "Aprobado para su eliminación, "Esperando eliminación de SharePoint/OneDrive" o "Esperando eliminación de Exchange" o "Eliminado permanentemente". Cuando se aprueba un elemento para su eliminación permanente como parte del proceso de revisión de eliminación, esa eliminación puede tardar hasta 15 días en completarse y esta nueva columna le ayuda a realizar un seguimiento de su progreso.
- La configuración para [habilitar un buzón de correo para el archivado](enable-archive-mailboxes.md) se mueve al nuevo Centro de administración de Exchange (EAC) y las instrucciones se han actualizado en consecuencia.
- Actualmente, los clasificadores entrenables para etiquetas de retención de aplicación automática no se admiten con ámbitos adaptables. Como solución alternativa, use ámbitos estáticos para esta combinación de configuración.
- Las instrucciones para [personalizar una directiva de archivo y eliminación para buzones](set-up-an-archive-and-deletion-policy-for-mailboxes.md) se actualizan para incluir solo etiquetas de retención que tienen un resultado que no se puede lograr con la retención de Microsoft 365.

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- [Diseño de una directiva de prevención de pérdida de datos diseño complejo de reglas (versión preliminar):](dlp-policy-design.md#complex-rule-design-preview) el generador de reglas DLP admite lógica booleana (AND, OR, NOT) y grupos anidados. Se han agregado nuevos vídeos y contenidos que le guiarán a través de esta nueva funcionalidad.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad
- [La compatibilidad con PDF](sensitivity-labels-office-apps.md#pdf-support) en Word, Excel y PowerPoint ya está disponible para el canal actual de Windows y el canal mensual de empresa.
- La etiqueta predeterminada de los documentos existentes ahora está totalmente implantada en Mac y Windows en canal actual y canal mensual de empresa, lo que proporciona paridad con el complemento AIP.
- En versión preliminar: la nueva [barra de confidencialidad](sensitivity-labels-office-apps.md#sensitivity-bar) y la compatibilidad con [los colores de etiqueta](sensitivity-labels-office-apps.md#label-colors) en las aplicaciones de Office, lo que proporciona paridad con el complemento AIP con funcionalidad adicional.
- En versión preliminar: [compatibilidad con S/MIME](sensitivity-labels-office-apps.md#configure-a-label-to-apply-smime-protection-in-outlook) para Windows, lo que proporciona paridad con el complemento AIP. La compatibilidad con Mac y móvil ya está totalmente implantada.
- En versión preliminar: clasificadores entrenables para directivas de etiquetado automático (todas las cargas de trabajo).

### <a name="trainable-classifiers"></a>Clasificadores que se pueden entrenar

- [Definiciones de clasificadores entrenables](classifier-tc-definitions.md)  : se han agregado más de 20 clasificadores nuevos, por lo que las definiciones de todos los clasificadores entrenables se han desglosado en este nuevo artículo.

## <a name="august-2022"></a>Agosto de 2022

### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Actualice las acciones de mejora y incorpore los datos de cumplimiento en el Administrador de cumplimiento](compliance-manager-update-actions.md) : nueva funcionalidad para actualizar varias acciones de mejora a la vez, lo que también permite a las organizaciones llevar el trabajo de cumplimiento completado en otros sistemas al Administrador de cumplimiento para realizar el seguimiento allí.
- [Trabajar con acciones de mejora en el Administrador de cumplimiento](compliance-manager-improvement-actions.md) : los usuarios ahora pueden incluir un vínculo o una dirección URL como parte de la evidencia para la implementación de acciones de mejora o el trabajo de prueba.

### <a name="compliance-offerings--service-assurance"></a>Ofertas de cumplimiento & garantía de servicio

- [Administración de cambios de Microsoft 365](/compliance/assurance/assurance-microsoft-365-change-management) : nuevo tema de garantía que trata los cambios de código y no de código en los servicios de Microsoft.
- **Tema de la oferta de la marca de oro de Japón CS** : retirada, certificación no renovada.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- La configuración de [Exchange (heredada)](data-lifecycle-management.md#exchange-legacy-features) pasa del Centro de administración de Exchange clásico (EAC) a la portal de cumplimiento Microsoft Purview, en **Administración del ciclo de vida de los datos**. Las características existentes de administración del ciclo de vida de datos se encuentran en un nuevo subnodo, **Microsoft 365**.
- En el caso de los datos adjuntos en la nube (actualmente en versión preliminar), la retención automática y temporal de los archivos eliminados en la biblioteca de suspensión de conservación se protege frente al archivo original que los usuarios eliminan antes de que se pueda crear y etiquetar la copia. Para obtener más información, consulte [Cómo funciona la retención con los datos adjuntos en la nube](retention-policies-sharepoint.md#how-retention-works-with-cloud-attachments).

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- [Introducción a la prevención de pérdida de datos del punto de conexión: vínculos actualizados](endpoint-dlp-getting-started.md) para nombres de artículos más accesibles
- [Obtenga información sobre la prevención de pérdida de datos del punto de conexión: vínculos actualizados](endpoint-dlp-learn-about.md) para nombres de artículos más accesibles; instrucciones actualizadas sobre los tipos de archivo admitidos; guía de copia a otra aplicación actualizada
- [Compartir alertas de prevención de pérdida de datos](dlp-share-alerts.md) (versión preliminar): nuevo
- [Configuración de la DLP de punto de conexión](dlp-configure-endpoint-settings.md) : disponibilidad general de dominios de servicio confidenciales
- [Referencia de directiva de prevención de pérdida de datos](dlp-policy-reference.md) : disponibilidad general de dominios de servicio confidenciales
- [Uso de la prevención de pérdida de datos de punto de conexión](endpoint-dlp-using.md) : disponibilidad general de dominios de servicio confidenciales

### <a name="insider-risk-management"></a>Administración de riesgos internos

- [Creación y administración de directivas de administración de riesgos internos](/microsoft-365/compliance/insider-risk-management-policies#general-risky-browser-usage-preview): nueva plantilla de directiva de uso general de explorador de riesgo para la versión preliminar pública. Esta directiva puede ayudar a detectar y habilitar la puntuación de riesgos para la exploración web que podría infringir la directiva de uso aceptable de su organización, como visitar sitios que representan una amenaza (por ejemplo, sitios de phishing) o contienen contenido para adultos.
- [Creación y administración de directivas de administración de riesgos internos](/microsoft-365/compliance/insider-risk-management-policies#quick-policies-from-recommended-actions-preview) : nuevas plantillas de directivas rápidas para la versión preliminar pública. Puede usar una directiva rápida para acelerar la configuración de una directiva de pérdida *de datos general* o *robo de datos.*
- [Introducción a la configuración de administración de riesgos internos](/microsoft-365/compliance/insider-risk-management-settings#intelligent-detections): nuevos clasificadores y exclusión admiten la configuración de detección inteligente.

### <a name="microsoft-priva"></a>Microsoft Priva

- [Microsoft Priva guía del usuario de prueba](/privacy/priva/priva-trial-playbook): guía actualizada y simplificada para alinearse con las actualizaciones de documentación recientes

### <a name="sensitive-information-types"></a>Tipos de información confidencial

- [Creación de una experiencia clásica de flujo de trabajo de tipo de información confidencial de coincidencia exacta de datos](sit-create-edm-sit-classic-ux-workflow.md) : nueva
- [Creación del archivo de ejemplo sit de EDM para la nueva experiencia](sit-create-edm-sit-unified-ux-sample-file.md) : nuevo
- [Creación de EDM SIT con la nueva experiencia](sit-create-edm-sit-unified-ux-schema-rule-package.md) : nuevo
- [Creación de una nueva experiencia de flujo de trabajo de tipo de información confidencial que coincida con datos exactos](sit-create-edm-sit-unified-ux-workflow.md) : nueva
- Se han agregado instrucciones para la experiencia de creación de SIT de EDM nueva y clásica en los temas siguientes:
  - [Introducción a los tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-based-sits-overview.md)
  - [Crear un paquete de reglas o tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-create-rule-package.md)
  - [Crear el esquema para tipos de información confidencial basados en las coincidencias exactas de datos](sit-get-started-exact-data-match-create-schema.md)
  - [Exportar datos de origen para el tipo de información confidencial basada en la coincidencia exacta de datos](sit-get-started-exact-data-match-export-data.md)
  - [Aplicar hash y cargar la tabla de origen de información confidencial para los datos exactos que coincidan con los tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md)
  - [Probar un tipo de información confidencial de coincidencia exacta de datos](sit-get-started-exact-data-match-test.md)
  - [Más información sobre los tipos de información confidencial de coincidencia exacta de datos](sit-learn-about-exact-data-match-based-sits.md)
- [Límites de tipos de información confidencial](sit-limits.md) : nuevo

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Disponibilidad general (GA) y ya no es necesario participar: los dispositivos móviles (iOS y Android, con versiones mínimas) admiten la [coautoría de archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md).
- Disponibilidad general con el canal actual 2208+ para Word, Excel y PowerPoint en Windows: [compatibilidad con PDF](sensitivity-labels-office-apps.md#pdf-support). La compatibilidad con Outlook para bloquear la impresión en PDF cuando sea necesario, se está implementando en el canal beta.
- Implementación en disponibilidad general con canal actual 2208+ para Windows y 16.63+ para macOS: etiqueta predeterminada para documentos existentes.
- En versión preliminar: clasificadores entrenables para directivas [de etiquetado automático](apply-sensitivity-label-automatically.md).
- Guía sobre cómo [configurar Azure AD para contenido cifrado](encryption-azure-ad-configuration.md), que incluye información sobre la configuración de acceso entre inquilinos de identidades externas, las directivas de acceso condicional y las cuentas de invitado.

## <a name="july-2022"></a>Julio de 2022

### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Lista de plantillas de Administrador de cumplimiento](compliance-manager-templates-list.md) : se ha agregado una nueva plantilla Premium en la categoría de países Asia-Pacific para "Hong Kong - Código de práctica bancaria y tarjeta de pago".

### <a name="compliance-offerings--service-assurance"></a>Ofertas de cumplimiento & garantía de servicio

- [Resistencia de datos de SharePoint y OneDrive en Microsoft 365](/compliance/assurance/assurance-sharepoint-onedrive-data-resiliency) : cambios en la sección resistencia del almacenamiento de blobs.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- [Sección de licencias combinadas](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management) con detalles agregados para escenarios.
- La retención de versiones de documentos de SharePoint ya no usa archivos independientes en la biblioteca de suspensión de conservación. Para obtener más información, consulte la documentación actualizada Sobre [cómo funciona la retención con las versiones del documento](retention-policies-sharepoint.md#how-retention-works-with-document-versions).
- Instrucciones sobre cómo [validar los registros que ha migrado a SharePoint o OneDrive](records-management.md#validating-migrated-records).
- Se ha actualizado el informe de evaluación de Cohasset para [SEC 17a-4(f), FINRA 4511(c) y CFTC 1.31(c)-(d)](retention-regulatory-requirements.md#sec-17a-4f-finra-4511c-and-cftc-131c-d).
- Se han quitado las declinaciones de responsabilidades de versión preliminar de las directivas de retención para los canales compartidos de Teams ahora que esta característica se está implementando en disponibilidad general.

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- [Referencia de directiva DLP](dlp-policy-reference.md#blocking-and-notifications-in-sharepoint-online-and-onedrive-for-business): se ha agregado una nueva sección sobre bloqueo y notificaciones en SharePoint Online y OneDrive para la Empresa en respuesta a las escalaciones de clientes. Se ha actualizado para admitir la versión preliminar pública de los dominios de servicios confidenciales. Se ha actualizado la compatibilidad con Power BI. Se ha actualizado la compatibilidad con clasificadores entrenables.
- [Configuración de los valores de DLP de punto de conexión](dlp-configure-endpoint-settings.md#sensitive-service-domains) : se ha agregado nuevo contenido para admitir la versión preliminar pública de la versión preliminar pública de los dominios de servicio confidenciales en versión preliminar pública. Se ha actualizado el comportamiento de coincidencia de direcciones URL.
- [Uso de DLP de punto de conexión](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains) : nuevo contenido de escenario que admite la versión preliminar pública de los dominios de servicios confidenciales. Se ha actualizado la información de la suscripción.

### <a name="ediscovery"></a>eDiscovery

- [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md) : se ha quitado la información sustituida.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

- [Definiciones de entidades de tipo de información confidencial](sensitive-information-type-entity-definitions.md) : hemos agregado 41 nuevas definiciones de entidad sit para admitir los 41 nuevos SIT de examen de credenciales. El contenido de las definiciones de entidad de SIT se retrabajo completamente de un único artículo monolítico en artículos individuales más fáciles de hacer referencia y compatibles. Ahora hay 303 artículos en total, incluidos los 42 nuevos SIT de examen de credenciales.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- En versión preliminar: [etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint](sensitivity-labels-sharepoint-default-label.md).
- En versión preliminar: [permisos personalizados de toda la organización](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions) para Windows cuando se configura una etiqueta de confidencialidad para permitir a los usuarios asignar permisos. Para obtener más información, consulte  [Compatibilidad con permisos personalizados de toda la organización](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions).
- Ahora se implementa en Canal actual (versión preliminar) para Windows: etiqueta predeterminada para los documentos existentes.
- Ahora disponible con el canal Semi-Annual Enterprise: [coautoría de archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md).
- El [nombre del ámbito de la etiqueta](sensitivity-labels.md#label-scopes) "Archivos & correos electrónicos" que ve al configurar una etiqueta de confidencialidad ahora es "Elementos".

## <a name="june-2022"></a>Junio de 2022

### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Alertas y directivas de alertas del Administrador de cumplimiento de Microsoft Purview](compliance-manager-alert-policies.md) : se han agregado tres roles de AAD que tienen permisos para crear o editar directivas de alertas.
- [Analizador de configuración para Microsoft Purview](compliance-manager-mcca.md) : nuevo nombre y vínculos de referencia actualizados para esta herramienta de introducción para el Administrador de cumplimiento anteriormente denominada "Analizador de configuración de cumplimiento de Microsoft".

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- Numerosas actualizaciones de páginas para las capturas de pantalla de marca de Microsoft Purview.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- En versión preliminar: [Microsoft Graph API para la administración de registros](compliance-extensibility.md#microsoft-graph-api-for-records-management-preview)

### <a name="microsoft-priva"></a>Microsoft Priva

- [Solicitudes de derechos del sujeto](/privacy/priva/subject-rights-requests) : actualizaciones importantes y reestructuración del contenido de SRR para ayudar mejor a los usuarios en cada paso de progreso; detalles a continuación.
  - [Obtenga información sobre Solicitudes de los interesados Priva](/privacy/priva/subject-rights-requests): articulación más clara de la propiedad de valor del cliente y el esquema general del proceso de SRR.
  - [Comprender las páginas de flujo de trabajo y detalles](/privacy/priva/subject-rights-requests-workflow) : articula los pasos para completar una solicitud, indicar la progresión manual frente a la automática y vincular a contenido detallado; En una sección se explica cómo interpretar y trabajar con la página de detalles de una solicitud, incluida la nueva pestaña "Historial".
  - [Cree una solicitud y defina la configuración de búsqueda](/privacy/priva/subject-rights-requests-create) : una nueva trama con subtítulos que explican que ahora hay dos maneras de crear una solicitud: a través de un método personalizado mediante un proceso guiado y a través de la nueva característica de usar una plantilla, cuyos parámetros de búsqueda tienen como objetivo recuperar el contenido más relevante para la situación.
  - [Estimación y recuperación de datos](/privacy/priva/subject-rights-requests-data-retrieval) : explica por qué algunas solicitudes se detienen en la fase de estimación de datos y cómo ajustar la búsqueda como resultado; también explica cómo establecer una solicitud para pausar primero antes de avanzar automáticamente a la recuperación de datos.
  - [Revisar los datos de una solicitud de derechos del interesado](/privacy/priva/subject-rights-requests-data-review) : las nuevas características de archivo de importación permiten a los usuarios traer archivos de ubicaciones que no son de Microsoft 365, o archivos que la búsqueda no ha recogido en caso contrario, en la pestaña Datos recopilados.
  - [Generar informes y cerrar solicitudes](/privacy/priva/subject-rights-requests-reports) : aclara cuándo se generan los paquetes de datos finales y qué tipos de archivos incluyen.
  - [Integrar y ampliar a través de Microsoft Graph API y Power Automate](/privacy/priva/subject-rights-requests-automate): se ha revisado el título de esta página anterior de Power Automate y se ha ampliado el contenido de la página para incluir Graph API contenido y vínculos de referencia que anteriormente residían en otra página.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

- [Obtenga información sobre los tipos de información confidencial basados en coincidencias de datos exactas](sit-learn-about-exact-data-match-based-sits.md) : se ha agregado una sección sobre los servicios que admite EDM.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- En versión preliminar: [compatibilidad con PDF para aplicaciones de Office](sensitivity-labels-office-apps.md#pdf-support), que incluye la conversión de documentos al formato PDF, la heredación de la etiqueta con cualquier marcado visual y cifrado. No se admite la impresión en PDF y esta opción deja de estar disponible para los usuarios si su directiva de etiquetas está configurada para el etiquetado obligatorio.
- En versión preliminar: el cuadro de diálogo que los usuarios ven cuando su directiva de etiqueta está configurada para requerir una justificación para quitar o degradar una etiqueta se actualiza para advertir a los usuarios de que su respuesta con tipo no debe incluir datos confidenciales. En la captura de pantalla de la sección [¿Qué directivas de etiquetas pueden hacer](sensitivity-labels.md#what-label-policies-can-do) ?, se muestra este cuadro de diálogo actualizado que se abrirá paso a los canales de implementación de Office para su uso en producción.
- En versión preliminar: [la compatibilidad con Outlook para aplicar la protección S/MIME](sensitivity-labels-office-apps.md#configure-a-label-to-apply-smime-protection-in-outlook) está empezando a implementarse en todas las plataformas cliente.
- Para [las directivas de etiquetado automático](apply-sensitivity-label-automatically.md#creating-an-auto-labeling-policy), una nueva configuración que puede activar automáticamente la directiva si no se edita dentro de un número establecido de días.

### <a name="trainable-classifiers"></a>Clasificadores capacitados

- [Obtenga información sobre los clasificadores entrenables](classifier-learn-about.md) : se ha agregado un clasificador de imágenes entrenables para adultos, Racy y Gory.

## <a name="may-2022"></a>Mayo de 2022

### <a name="communication-compliance"></a>Cumplimiento de las comunicaciones

- [Informes y auditorías de cumplimiento de comunicaciones](communication-compliance-reports-audits.md) : se han actualizado los límites de tamaño de archivo para los informes exportados.
- [Directivas de cumplimiento de comunicaciones](communication-compliance-policies.md) : los mensajes notificados por el usuario aclarados deshabilitan o habilitan el proceso y el procesamiento aclarado para Teams y Exchange.

### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Alertas y directivas de alertas](compliance-manager-alert-policies.md) : nueva sección que explica la directiva de cambio de puntuación predeterminada para todas las organizaciones.
- [Trabajar con acciones de mejora](compliance-manager-improvement-actions.md) : estados de estado aclarados para el estado de implementación y el estado de prueba, haciendo una distinción entre las acciones probadas automáticamente y las acciones probadas manualmente.
- [Lista de plantillas](compliance-manager-templates-list.md) : se han agregado dos nuevas plantillas en la región de Europa, Oriente Medio y África (EMEA): Qatar National Information Assurance (NIA) y EAU Data Privacy Law.

### <a name="compliance-offerings--service-assurance"></a>Ofertas de cumplimiento & garantía de servicio

- [Ciclo de vida del desarrollo de seguridad de Microsoft](/compliance/assurance/assurance-microsoft-security-development-lifecycle) : nuevo tema de garantía de SDL para los servicios de Microsoft.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- Actualmente se implementa en versión preliminar: nueva [opción de nueva etiqueta al final del período de retención](retention-settings.md#relabeling-at-the-end-of-the-retention-period).
- Nueva guía de implementación: [Implementación de una solución de gobernanza de datos con Microsoft Purview](data-governance-solution.md)
- Corrección en la documentación para confirmar que los buzones de recursos son compatibles con la retención y eliminación de Exchange tanto para ámbitos estáticos como para ámbitos adaptables. En el caso de los ámbitos estáticos, los buzones de recursos se incluyen de forma predeterminada en una directiva de toda la organización (todos los valores predeterminados).
- Nueva documentación para los usuarios finales: [Administración del almacenamiento de correo electrónico con buzones de archivo en línea](https://support.services.microsoft.com/office/manage-email-storage-with-online-archive-mailboxes-1cae7d17-7813-4fe8-8ca2-9a5494e9a721)

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- [Enviar notificaciones por correo electrónico y sugerencias de directivas para directivas DLP](use-notifications-and-policy-tips.md) : se ha agregado información nueva sobre lo que desencadena una notificación y quién puede recibirlas.

### <a name="information-barriers"></a>Barreras de información

- [Obtenga información sobre las barreras de información](information-barriers.md), [Introducción a las barreras de información](information-barriers-policies.md): estructura refactorización de temas y aclaración adicional para Exchange Online compatibilidad y limitaciones, actualizada para incluir compatibilidad con la nueva experiencia de interfaz de usuario de IB.

### <a name="insider-risk-management"></a>Administración de riesgos internos

- [Introducción a la configuración de administración de riesgos](insider-risk-management-settings.md) internos: se han agregado instrucciones para nuevos indicadores de Defender for Cloud App, nueva anomalía como un evento desencadenante en umbrales personalizados, nueva priorización de extensiones de archivo y compatibilidad con la directiva de etiquetas de confidencialidad.
- [Casos de administración de riesgos](insider-risk-management-cases.md) internos: se ha aclarado la escalación a la guía de casos de eDiscovery.

### <a name="microsoft-priva"></a>Microsoft Priva

- [Obtenga información sobre la evaluación gratuita de Priva](/privacy/priva/priva-trial) : se ha actualizado el vínculo a los nuevos términos y condiciones de evaluación universales de Microsoft 365 y a las actualizaciones secundarias para aclarar los roles y la idoneidad.
- [Introducción a Priva](/privacy/priva/priva-setup) : sección agregada que indica las limitaciones de la disponibilidad de Priva.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

- [Obtenga información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md) : desde una escalación del cliente, se agregaron las regiones en las que se admite EDM y los procedimientos para buscar la región del inquilino.
- [Creación de un paquete de reglas SIT de EDM](sit-get-started-exact-data-match-create-rule-package.md) : se ha agregado "trabajar con tipos de datos específicos" del artículo de esquema.
- [Crear esquema para EDM SIT](sit-get-started-exact-data-match-create-schema.md) : se ha quitado "trabajar con tipos de datos específicos".
- [Usar entidades con nombre en las directivas DLP](named-entities-use.md): se ha agregado una instrucción de compatibilidad para Microsoft Defender for Cloud Apps.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Nueva opción al final del proceso de creación o edición de etiquetas para convertir automáticamente la [configuración de etiquetado automático en una directiva de etiquetado automático](apply-sensitivity-label-automatically.md#convert-your-label-settings-into-an-auto-labeling-policy).
- Las directivas de etiquetado automático para SharePoint y OneDrive ahora pueden aplicar etiquetas con cifrado cuando la cuenta que modificó por última vez el archivo ya no existe en Azure AD.
- Las etiquetas de contenedor son compatibles con Office 365 redes de entrega de contenido (CDN).
- Aclaraciones para [quitar y eliminar etiquetas](create-sensitivity-labels.md#removing-and-deleting-labels).
- Nuevos [escenarios comunes](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels):
  - Etiquete columnas de base de datos SQL con las mismas etiquetas de confidencialidad que las que se usan para archivos y correos electrónicos para que la organización tenga una solución de etiquetado unificada que continúe protegiendo los datos estructurados cuando se exportan.
  - Aplicar una etiqueta de confidencialidad a un archivo después de recibir una alerta de que el contenido que contiene datos personales se comparte y necesita protección

### <a name="changes-to-product-names"></a>Cambios en los nombres de producto

Para satisfacer los desafíos del área de trabajo descentralizada y rica en datos de hoy en día, presentamos [Microsoft Purview](https://aka.ms/microsoftpurview), un completo conjunto de soluciones que le ayuda a comprender, gobernar y proteger todo el patrimonio de datos. Esta nueva familia de marcas combina las funcionalidades de la antigua Mapa de datos de Microsoft Purview y la cartera de cumplimiento de Microsoft 365 en la que ya confían los clientes, lo que proporciona una gobernanza de datos unificada y administración de riesgos para su organización.

| **Nombre anterior** | **Nombre nuevo** | **Descripción** |
|:----------------|:-------------|:----------------|
| Auditoría avanzada de Microsoft 365 <br><br> Auditoría básica de Microsoft 365 | Auditoría de Microsoft Purview (Premium) <br><br> Auditoría de Microsoft Purview (estándar)| Las soluciones de auditoría proporcionan una solución integrada para ayudar a las organizaciones a responder eficazmente a eventos de seguridad, investigaciones forenses, investigaciones internas y obligaciones de cumplimiento. Para obtener más información, consulte [Auditoría avanzada de Microsoft Purview (Premium)](advanced-audit.md) y [Auditoría avanzada de Microsoft Purview (estándar).](set-up-basic-audit.md) |
| Cumplimiento de comunicaciones de Microsoft 365 | Cumplimiento de comunicaciones de Microsoft Purview | El cumplimiento de comunicaciones ayuda a minimizar los riesgos, ya que le ayuda a detectar, capturar y tomar medidas correctivas rápidamente para los canales de comunicación de la empresa y las infracciones de directivas. Para más información, consulte [Cumplimiento de comunicaciones de Microsoft Purview](communication-compliance-solution-overview.md). |
| Administrador de cumplimiento de Microsoft | Administrador de cumplimiento de Microsoft Purview | El Administrador de cumplimiento puede ayudarle a lo largo del proceso de cumplimiento, desde realizar un inventario de los riesgos de protección de datos hasta administrar las complejidades de la implementación de controles, estar al corriente de las normativas y certificaciones e informar a los auditores. Para más información, consulte [Administrador de cumplimiento de Microsoft Purview](compliance-manager.md). |
| Clave de cliente de Microsoft 365 | Clave de cliente de Microsoft Purview | La clave de cliente proporciona protección adicional contra la visualización de datos por parte de sistemas o personal no autorizados, y complementa el cifrado de disco de BitLocker en centros de datos de Microsoft. Para obtener más información, consulte [Clave de cliente de Microsoft Purview](customer-key-overview.md). |
| Caja de seguridad del cliente de Office 365 | Caja de seguridad del cliente de Microsoft Purview | La Caja de seguridad del cliente garantiza que Microsoft no puede acceder a su contenido para realizar operaciones de servicio sin su aprobación explícita. La Caja de seguridad del cliente le lleva al proceso de flujo de trabajo de aprobación que Microsoft usa para asegurarse de que solo las solicitudes autorizadas permiten el acceso al contenido. Para más información, consulte [Caja de seguridad del cliente de Microsoft Purview](customer-lockbox-requests.md). |
| Prevención de pérdida de datos | Prevención de pérdida de datos de Microsoft Purview | DLP ayuda a proteger los datos confidenciales y a reducir el riesgo evitando que los usuarios compartan esos datos de forma inapropiada con personas que no deberían tenerlos. Para obtener más información, consulte [Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md). |
| Cifrado de clave doble para Microsoft 365 | Cifrado de doble clave de Microsoft Purview | El cifrado de doble clave (DKE) usa dos claves juntas para acceder al contenido protegido. Microsoft almacena una clave en Microsoft Azure y usted mantiene la otra clave. Para más información, consulte [Cifrado de doble clave de Microsoft Purview](double-key-encryption.md). |
| Barreras de información de Microsoft 365 | Barreras de información de Microsoft Purview | Barreras de información es una solución que restringe la comunicación y la colaboración entre ciertas personas dentro de la organización para proteger la información interna. Para obtener más información, consulte [Barreras de información de Microsoft Purview](information-barriers-solution-overview.md). |
| Microsoft Information Protection | Microsoft Purview Information Protection | La protección de la información le ayuda a detectar, clasificar y proteger la información confidencial dondequiera que viva o viaje. Para obtener más información, consulte [Microsoft Purview Information Protection](information-protection.md). |
| Gobernanza de información de Microsoft | Administración del ciclo de vida de datos de Microsoft Purview | La administración del ciclo de vida de los datos proporciona herramientas y funcionalidades para conservar el contenido que necesita conservar y eliminar el contenido que no. Para más información, consulte [Administración del ciclo de vida de Microsoft Purview](data-lifecycle-management.md). |
| Administración de riesgos internos de Microsoft 365 | Administración de riesgos internos de Microsoft Purview | La administración de riesgos internos usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, evaluar prioridades y actuar rápidamente en la actividad de usuario de riesgo. Para más información, consulte [Administración de riesgos internos de Microsoft Purview](insider-risk-management.md). |
| Cifrado de mensajes de Office 365 | Cifrado de mensajes de Microsoft Purview | Con el cifrado de mensajes, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre personas dentro y fuera de la organización. Para obtener más información, consulte [Cifrado de mensajes de Microsoft Purview](ome.md). |
| Privileged Access Management en Microsoft 365 | Privileged Access Management de Microsoft Purview | Privileged Access Management ayuda a proteger su organización frente a infracciones y ayuda a cumplir los procedimientos recomendados de cumplimiento limitando el acceso permanente a datos confidenciales o el acceso a la configuración crítica. Para más información, consulte [Administración de acceso con privilegios de Microsoft Purview](privileged-access-management-solution-overview.md). |
| Conectores de datos de Microsoft | Conectores de datos de Microsoft Purview | Microsoft 365 permite a los administradores usar conectores de datos para importar y archivar datos que no son de Microsoft, datos de terceros de plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, en buzones de su organización de Microsoft 365. Para más información, consulte [Conectores de datos de Microsoft Purview](compliance-extensibility.md). |
| eDiscovery avanzado de Microsoft 365 <br><br> Exhibición de documentos electrónicos de Microsoft 365 Core | Exhibición de documentos electrónicos de Microsoft Purview (premium) <br><br> Exhibición de documentos electrónicos de Microsoft Purview (estándar) | La exhibición de documentos electrónicos, o eDiscovery, es el proceso de identificación y entrega de información electrónica que se puede usar como prueba en casos legales. Para obtener más información, consulte [Microsoft Purview eDiscovery (Premium)](overview-ediscovery-20.md) y [Microsoft Purview eDiscovery (Estándar).](get-started-core-ediscovery.md) |
| Centro de cumplimiento de Microsoft 365 | Portal de cumplimiento de Microsoft Purview. | Administración portal para acceder a soluciones y catálogo de soluciones dentro del conjunto de Cumplimiento de Microsoft 365 E5. Para obtener más información, consulte [portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center.md). |
