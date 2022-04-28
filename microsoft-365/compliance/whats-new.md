---
title: Novedades de Microsoft Purview
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
description: Ya sea que agregue nuevas soluciones al centro de cumplimiento, actualice las características existentes en función de sus comentarios o implemente documentación actualizada y actualizada, Microsoft 365 le ayuda a mantenerse al tanto del panorama de cumplimiento en constante cambio. Averigüe lo que hemos estado haciendo hasta este mes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b79015ce0ca55bf9a74b6acac8f38f09b9e5e984
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100553"
---
# <a name="whats-new-in-microsoft-purview"></a>Novedades de Microsoft Purview

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Ya sea que agregue nuevas soluciones al portal de [cumplimiento de Microsoft Purview](microsoft-365-compliance-center.md), actualice las características existentes en función de sus comentarios o implemente documentación actualizada y actualizada, Microsoft 365 le ayuda a mantenerse al tanto del cambiante panorama de cumplimiento. Eche un vistazo a continuación para ver las novedades de Microsoft Purview hoy en día.

> [!NOTE]
> Algunas características de cumplimiento se implantan a diferentes velocidades para nuestros clientes. Si aún no ve una característica, intente agregarse a la [versión de destino](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> ¿Te interesa lo que sucede en otros centros de administración? Consulte estos artículos:
>
> - [Novedades de la Centro de administración de Microsoft 365](/office365/admin/whats-new-in-preview)
> - [Novedades del centro de administración de SharePoint](/sharepoint/what-s-new-in-admin-center)
> - [Novedades de Microsoft 365 Defender](../security/defender/whats-new.md)
>
> Y visite la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener información sobre Microsoft 365 características que se lanzaron, se están implementando, están en desarrollo, han sido canceladas o publicadas anteriormente.

## <a name="april-2022"></a>Abril de 2022

### <a name="changes-to-product-names"></a>Cambios en los nombres de producto

Para satisfacer los desafíos del área de trabajo descentralizada y rica en datos de hoy en día, presentamos [Microsoft Purview](https://aka.ms/microsoftpurview), un completo conjunto de soluciones que le ayuda a comprender, gobernar y proteger todo el patrimonio de datos. Esta nueva familia de marcas combina las funcionalidades del anterior mapa de datos de Microsoft Purview y la cartera de cumplimiento de Microsoft 365 en la que ya confían los clientes, lo que proporciona una gobernanza de datos unificada y administración de riesgos para su organización.

| **Nombre anterior** | **Nombre nuevo** | **Descripción** |
|:----------------|:-------------|:----------------|
| Microsoft 365 auditoría avanzada <br><br> auditoría básica de Microsoft 365 | Auditoría de Microsoft Purview (Premium) <br><br> Auditoría de Microsoft Purview (estándar)| Las soluciones de auditoría proporcionan una solución integrada para ayudar a las organizaciones a responder eficazmente a eventos de seguridad, investigaciones forenses, investigaciones internas y obligaciones de cumplimiento. Para obtener más información, consulte [Auditoría avanzada de Microsoft Purview (Premium)](advanced-audit.md) y [Auditoría avanzada de Microsoft Purview (estándar).](set-up-basic-audit.md) |
| Cumplimiento de Microsoft 365 comunicación | Cumplimiento de comunicaciones de Microsoft Purview | El cumplimiento de comunicaciones ayuda a minimizar los riesgos, ya que le ayuda a detectar, capturar y tomar medidas correctivas rápidamente para los canales de comunicación de la empresa y las infracciones de directivas. Para obtener más información, consulte [Cumplimiento de comunicación de Microsoft Purview](communication-compliance-solution-overview.md). |
| Administrador de cumplimiento de Microsoft | Administrador de cumplimiento de Microsoft Purview | El Administrador de cumplimiento puede ayudarle a lo largo del proceso de cumplimiento, desde realizar un inventario de los riesgos de protección de datos hasta administrar las complejidades de la implementación de controles, estar al corriente de las normativas y certificaciones e informar a los auditores. Para más información, consulte [Administrador de cumplimiento de Microsoft Purview](compliance-manager.md). |
| Microsoft 365 clave de cliente | Clave de cliente de Microsoft Purview | La clave de cliente proporciona protección adicional contra la visualización de datos por parte de sistemas o personal no autorizados, y complementa el cifrado de disco de BitLocker en centros de datos de Microsoft. Para obtener más información, consulte [Clave de cliente de Microsoft Purview](customer-key-overview.md). |
| Caja de seguridad del cliente de Office 365 | Caja de seguridad del cliente de Microsoft Purview | La Caja de seguridad del cliente garantiza que Microsoft no puede acceder a su contenido para realizar operaciones de servicio sin su aprobación explícita. La Caja de seguridad del cliente le lleva al proceso de flujo de trabajo de aprobación que Microsoft usa para asegurarse de que solo las solicitudes autorizadas permiten el acceso al contenido. Para más información, consulte [Caja de seguridad del cliente de Microsoft Purview](customer-lockbox-requests.md). |
| Prevención de pérdida de datos | Prevención de pérdida de datos de Microsoft Purview | DLP ayuda a proteger los datos confidenciales y a reducir el riesgo evitando que los usuarios compartan esos datos de forma inapropiada con personas que no deberían tenerlos. Para más información, consulte [Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md). |
| Cifrado de clave doble para Microsoft 365 | Cifrado de clave doble de Microsoft Purview | El cifrado de doble clave (DKE) usa dos claves juntas para acceder al contenido protegido. Microsoft almacena una clave en Microsoft Azure y la otra. Para más información, consulte [Cifrado de doble clave de Microsoft Purview](double-key-encryption.md). |
| Microsoft 365 barreras de información | Barreras de información de Microsoft Purview | Barreras de información es una solución que restringe la comunicación y la colaboración entre ciertas personas dentro de la organización para proteger la información interna. Para obtener más información, consulte [Barreras de información de Microsoft Purview](information-barriers-solution-overview.md). |
| Microsoft Information Protection | Microsoft Purview Information Protection | La protección de la información le ayuda a detectar, clasificar y proteger la información confidencial dondequiera que viva o viaje. Para más información, consulte [Microsoft Purview Information Protection](information-protection.md). |
| Gobernanza de información de Microsoft | Administración del ciclo de vida de datos de Microsoft Purview | La administración del ciclo de vida de los datos proporciona herramientas y funcionalidades para conservar el contenido que necesita conservar y eliminar el contenido que no. Para más información, consulte [Administración del ciclo de vida de datos de Microsoft Purview](data-lifecycle-management.md). |
| Administración de riesgos internos de Microsoft 365 | Administración de riesgos internos de Microsoft Purview | La administración de riesgos internos usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, evaluar prioridades y actuar rápidamente en la actividad de usuario de riesgo. Para obtener más información, consulte [Administración de riesgos internos de Microsoft Purview](insider-risk-management.md). |
| Cifrado de mensajes de Office 365 | Cifrado de mensajes de Microsoft Purview | Con el cifrado de mensajes, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre personas dentro y fuera de la organización. Para más información, consulte [Cifrado de mensajes de Microsoft Purview](ome.md). |
| Privileged Access Management en Microsoft 365 | Privileged Access Management de Microsoft Purview | Privileged Access Management ayuda a proteger su organización frente a infracciones y ayuda a cumplir los procedimientos recomendados de cumplimiento limitando el acceso permanente a datos confidenciales o el acceso a la configuración crítica. Para más información, consulte [Administración de acceso con privilegios de Microsoft Purview](privileged-access-management-solution-overview.md). |
| Conectores de datos de Microsoft | Conectores de datos de Microsoft Purview | Microsoft 365 permite a los administradores usar conectores de datos para importar y archivar datos que no son de Microsoft, datos de terceros de plataformas de medios sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos, en buzones de su organización Microsoft 365. Para más información, consulte [Conectores de datos de Microsoft Purview](compliance-extensibility.md). |
| eDiscovery avanzado de Microsoft 365 <br><br> eDiscovery principal de Microsoft 365 | Exhibición de documentos electrónicos de Microsoft Purview (premium) <br><br> Exhibición de documentos electrónicos de Microsoft Purview (estándar) | La exhibición de documentos electrónicos, o eDiscovery, es el proceso de identificación y entrega de información electrónica que se puede usar como prueba en casos legales. Para obtener más información, consulte [Exhibición de documentos electrónicos de Microsoft Purview (Premium)](overview-ediscovery-20.md) y [Exhibición de documentos electrónicos de Microsoft Purview (estándar).](get-started-core-ediscovery.md) |
| Centro de cumplimiento de Microsoft 365 | Portal de cumplimiento de Microsoft Purview. | Portal de administración para acceder a soluciones y catálogo de soluciones dentro del conjunto de Cumplimiento de Microsoft 365 E5. Para más información, consulte [El portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center.md). |

## <a name="march-2022"></a>Marzo de 2022

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

- [Investigar y corregir alertas de cumplimiento de comunicaciones](communication-compliance-investigate-remediate.md) : se han quitado las instrucciones para la vista de anotación en desuso.

### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Trabajando con acciones de mejora](compliance-manager-improvement-actions.md), [Comenzar con el Administrador de cumplimiento](compliance-manager-setup.md): se ha agregado información sobre más acciones de mejora que se pueden supervisar y probar automáticamente ("evaluación de cumplimiento continuo"). Esto incluye nuevas capacidades para mejorar el estado de las pruebas de una acción a la de otra acción.

### <a name="data-classification"></a>Clasificación de datos

- [Introducción con el Explorador de contenido](data-classification-content-explorer.md): Teams instrucciones agregadas, sección de licencias que apunta a descripciones del servicio.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- [Las directivas de retención para Yammer](create-retention-policies.md#retention-policy-for-yammer-locations) ahora están disponibles con carácter general (GA).
- Compatibilidad con canales compartidos, actualmente en versión preliminar. Al configurar una directiva de retención para la ubicación del mensaje de canal Teams, los canales compartidos heredan la configuración de retención de su equipo primario.
- [Límites por inquilino para la eliminación de contenido](retention-limits.md#maximum-number-of-items-for-disposition).

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- [Prevención y Microsoft Teams de pérdida de datos](dlp-microsoft-teams.md): versión preliminar pública del contenido de Share Teams Channels.
- [Comenzar con la extensión de cumplimiento de Microsoft](dlp-chrome-get-started.md): versión preliminar pública de grupos de aplicaciones restringidos, quite las instrucciones de clave del Registro y la configuración ahora está habilitada de forma predeterminada.
- [Configuración de las opciones de prevención de pérdida de datos del punto de conexión](dlp-configure-endpoint-settings.md) : novedades de la versión preliminar pública de grupos de aplicaciones restringidos.
- Referencia de directiva [de prevención de pérdida de datos](dlp-policy-reference.md): se ha actualizado para la versión preliminar pública de los grupos de aplicaciones restringidos.
- [Comenzar con prevención de pérdida de datos para Power BI](dlp-powerbi-get-started.md): nuevo para la versión preliminar pública.

### <a name="insider-risk-management"></a>Administración de riesgos internos

- [Comenzar con la administración de riesgos internos](insider-risk-management-configure.md): se han agregado nuevas tareas para la guía acciones recomendadas.
- [Comenzar con la configuración de administración de riesgos internos](insider-risk-management-settings.md): nuevas actualizaciones para las características de notificaciones y alertas por correo electrónico, nuevas actualizaciones para las notificaciones de análisis.

### <a name="microsoft-information-protection"></a>Microsoft Information Protection

- [Compatibilidad con notas de la versión del juego de caracteres de doble byte](mip-dbcs-relnotes.md) : se han agregado instrucciones para macOS.

### <a name="microsoft-priva"></a>Microsoft Priva

- [Configurar la configuración de Priva](/privacy/priva/priva-settings) : se ha actualizado información aclarante sobre los períodos de retención de datos para las solicitudes de derechos del interesado; se agregaron detalles sobre cómo administrar y aplicar etiquetas de revisión de datos para solicitudes de derechos del interesado.
- [Crear una solicitud de derechos de sujeto](/privacy/priva/subject-rights-requests-create): se han agregado detalles sobre cómo refinar búsquedas y elegir condiciones y atributos; se ha agregado información sobre la nueva funcionalidad que permite a los usuarios seleccionar todas las versiones de SharePoint elementos en su búsqueda (frente a la configuración predeterminada, que solo devuelve la versión actual de SharePoint elementos).
- [Revisar los datos de una solicitud de derechos del interesado](/privacy/priva/subject-rights-requests-data-review) : se han agregado detalles en el paso 3 para revisar elementos durante la fase de revisión de datos, incluido el marcado de archivos como inclusión o exclusión, la anotación de archivos para aplicar censuras, la aplicación de etiquetas y la introducción de notas.
- [Generación de informes y cumplimiento de una solicitud de derechos de sujeto](/privacy/priva/subject-rights-requests-reports) : se han agregado detalles sobre cómo comprender los informes; aclarado cuando se genera un paquete de exportación y cómo trabajar con su contenido; se ha agregado información sobre los registros de auditoría, los informes de archivos etiquetados y los períodos de retención de los datos e informes de SRR.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- [Etiquetas de confidencialidad para Teams](sensitivity-labels-teams-groups-sites.md):
  - Compatibilidad con canales compartidos, actualmente en versión preliminar. Si un equipo tiene canales compartidos, hereda automáticamente la configuración de etiqueta de confidencialidad de su equipo primario y esa etiqueta no se puede quitar ni reemplazar con una etiqueta diferente.
  - Compatibilidad con plantillas, enumeradas anteriormente como [no compatibles con las API de Teams Graph y los cmdlets de PowerShell]( /microsoftteams/sensitivity-labels#limitations).  
- Para auditar Word, Excel y PowerPoint en la Web, el texto de justificación ahora está totalmente implementado.
- La aplicación de una etiqueta predeterminada a documentos existentes para Word, Excel y PowerPoint en la Web ahora está totalmente implementado.

## <a name="february-2022"></a>Febrero de 2022

### <a name="ediscovery"></a>eDiscovery

- [Administrar plantillas de comunicaciones de custodios en eDiscovery (Premium):](advanced-ediscovery-communications-library.md) los administradores de eDiscovery ahora pueden crear plantillas de comunicaciones custodios que se pueden usar en cualquier caso de exhibición de documentos electrónicos (Premium) de la organización.
- [Administrar oficiales emisores en eDiscovery (Premium):](advanced-ediscovery-issuing-officers.md) los administradores de exhibición de documentos electrónicos pueden agregar una lista de oficiales emisores que se pueden asignar a las comunicaciones del custodio en cualquier caso de exhibición de documentos electrónicos (Premium) de la organización.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- [Los ámbitos adaptables para las directivas](retention.md#adaptive-or-static-policy-scopes-for-retention) de retención y las directivas de etiqueta de retención ahora están disponibles con carácter general (GA). Las instrucciones para [configurar un ámbito adaptable](retention-settings.md#to-configure-an-adaptive-scope) ahora incluyen más información para SharePoint ámbitos de sitio: referencia de entrada de blog para usar propiedades de sitio personalizadas y cómo usar la propiedad site SiteTemplate para incluir o excluir tipos de sitio específicos con el generador de consultas avanzadas.
- [La búsqueda de directivas](retention.md#policy-lookup) en la solución de administración del ciclo de vida de datos ya está disponible con carácter general (GA).
- Alternativa de PowerShell a la configuración de administración de registros que permite a los usuarios eliminar elementos etiquetados en SharePoint y OneDrive mediante AllowFilesWithKeepLabelToBeDeletedSPO y AllowFilesWithKeepLabelToBeDeletedODB de [Get-PnPTenant](/powershell/module/sharepoint-pnp/get-pnptenant) y [Set-PnPTenant]( /powershell/module/sharepoint-pnp/set-pnptenant).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Nueva guía [Por qué elegir el etiquetado integrado en el complemento AIP para aplicaciones de Office](sensitivity-labels-aip.md) si usa el cliente de etiquetado unificado de Azure Information Protection (AIP) para equipos Windows. Esta página incluye información sobre la nueva versión preliminar privada para aplicaciones Office.
- Nueva configuración para las [directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange):
  - Configuración adicional del correo electrónico para admitir siempre la aplicación de una etiqueta de confidencialidad coincidente y aplicar el cifrado al correo electrónico recibido desde fuera de la organización.
  - Las exclusiones de instancias específicas (usuarios, grupos, sitios) se admiten mediante la nueva opción **Excluir** cuando se especifica la selección predeterminada de **Todos** para **Incluido**.
- Ahora en versión preliminar: los dispositivos móviles (iOS y Android) admiten [la coautoría](sensitivity-labels-coauthoring.md) cuando tiene versiones mínimas y opta por esta versión preliminar.
- La compatibilidad para establecer el tipo de vínculo de uso compartido predeterminado se extiende a documentos individuales en SharePoint y OneDrive. Para obtener más información, consulte el nuevo artículo [Uso de etiquetas de confidencialidad para configurar el tipo de vínculo de uso compartido predeterminado para sitios y documentos en SharePoint y OneDrive]( sensitivity-labels-default-sharing-link.md).
- Teams centro de administración ahora admite etiquetas de contenedor (etiquetas de confidencialidad con el ámbito de grupos & sitios).

## <a name="january-2022"></a>Enero de 2022

### <a name="microsoft-purview-data-lifecycle-management"></a>Administración del ciclo de vida de datos de Microsoft Purview

- La documentación de lo que anteriormente era Microsoft Information Governance se ha revisado y reestructurado sustancialmente para ayudarle a encontrar más fácilmente información relacionada con las soluciones que configure en el portal de cumplimiento de Microsoft Purview: Conectores de datos, Administración del ciclo de vida de datos y Administración de registros. Como parte de esta revisión, la documentación proporciona una distinción más clara para los escenarios de retención para la administración del ciclo de vida de datos frente a la administración de registros.
- [Obtenga información sobre la administración del ciclo de vida de los datos](data-lifecycle-management.md) : novedades, para admitir la reestructuración.
- [Comenzar con la administración del ciclo de vida de datos](get-started-with-data-lifecycle-management.md): nuevo, para reemplazar "Comenzar por retención", en este artículo se incluyen los pasos de introducción a todas las funcionalidades de administración del ciclo de vida de datos, que incluyen la retención.
- [Cree etiquetas de retención para excepciones a las directivas de retención](create-retention-labels-data-lifecycle-management.md) : escenario nuevo e identificado para usar etiquetas de retención para la administración del ciclo de vida de datos en lugar de la administración de registros.
- [Obtenga información sobre los buzones de archivo](archive-mailboxes.md) : nuevo, para admitir la reestructuración, contiene información conceptual que se encontraba anteriormente en el artículo "Habilitar buzones de archivo".

### <a name="microsoft-priva"></a>Microsoft Priva

- [La administración de privacidad ahora es Microsoft Priva](/privacy/priva/priva-overview) : se ha actualizado para cambiar el nombre del producto y sus soluciones, Priva Privacy Risk Management y Priva Subject Rights Requests.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Compatibilidad con nuevos [roles y grupos de roles](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels), ahora en versión preliminar.
- Nuevas [funcionalidades de supervisión](apply-sensitivity-label-automatically.md#monitoring-your-auto-labeling-policy) para directivas de etiquetado automático.
- Implementación ahora: etiqueta predeterminada para documentos existentes y texto de justificación para Office en la Web.
- Anunciado para el canal de Semi-Annual Enterprise de julio con la versión 2202+: Coautoría y auditoría para Outlook.

## <a name="december-2021"></a>Diciembre de 2021

### <a name="compliance-and-service-assurance"></a>Cumplimiento y garantía de servicio

- [Azure, Dynamics 365 y Windows notificación de infracción en virtud del RGPD](/compliance/regulatory/gdpr-breach-notification): se ha actualizado para aclarar que los clientes no necesitan usar un servicio de pago como Defender for Cloud para recibir notificaciones de seguridad y privacidad.

### <a name="ediscovery"></a>eDiscovery

- [Flujo de trabajo de eDiscovery (Premium) para el contenido de Microsoft Teams](teams-workflow-in-advanced-ediscovery.md#reference-guide): se ha actualizado con una nueva guía de referencia rápida descargable para administrar Teams contenido en eDiscovery (Premium)

### <a name="data-lifecycle-management"></a>Administración del ciclo de vida de los datos

- [Habilitar buzones de archivo en el centro de cumplimiento](enable-archive-mailboxes.md#run-diagnostics-on-archive-mailboxes) : se ha agregado una sección sobre la nueva herramienta de diagnóstico para buzones de archivo.
- [Uso de la carga de red para importar los archivos PST de la organización a Microsoft 365](use-network-upload-to-import-pst-files.md#step-2-upload-your-pst-files-to-microsoft-365): la importación de PST ahora admite AzCopy v10
- [Restauración de un buzón inactivo](restore-an-inactive-mailbox.md) : procedimiento revisado para restaurar un buzón inactivo agregando primero LegacyExchangeDN del buzón inactivo al buzón de destino

### <a name="information-protection"></a>Protección de la información

- [Implementación de una solución de protección de la información con Microsoft Purview](information-protection-solution.md): nueva guía paso a paso para los clientes que buscan una hoja de ruta prescriptiva para implementar Microsoft Purview Information Protection

### <a name="retention-and-records-management"></a>Retención y administración de registros

- Nuevas instrucciones sobre [cuánto tiempo tardan las directivas de retención en surtir efecto](create-retention-policies.md#how-long-it-takes-for-retention-policies-to-take-effect)
- Nueva configuración de inquilino que se implementa: una configuración de administración de registros que impide la edición de propiedades para elementos etiquetados SharePoint que están marcados como un registro y bloqueados, y otra configuración para evitar que los usuarios desbloqueen elementos marcados como un registro

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- El etiquetado obligatorio y una etiqueta predeterminada para Power BI ahora están disponibles con carácter general (GA)

## <a name="november-2021"></a>Noviembre de 2021

### <a name="compliance-manager"></a>Administrador de cumplimiento

Las nuevas actualizaciones de contenido se pueden ver en [Novedades del Administrador de cumplimiento de Microsoft Purview](compliance-manager-whats-new.md).

### <a name="device-onboarding"></a>Incorporación de dispositivos

Se agregaron los siguientes artículos para la incorporación de dispositivos:

- [Incorporar dispositivos macOS en la información general de Microsoft 365 (versión preliminar)](device-onboarding-macos-overview.md)
- [Incorporación y eliminación de dispositivos macOS en soluciones de Microsoft Purview mediante Intune (versión preliminar)](device-onboarding-offboarding-macos-intune.md)
- [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante Intune para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-intune-mde.md)
- [Incorporación y eliminación de dispositivos macOS en soluciones de Microsoft Purview mediante JAMF Pro (versión preliminar)](device-onboarding-offboarding-macos-jamfpro.md)
- [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-jamfpro-mde.md)

### <a name="ediscovery"></a>eDiscovery

- [Usar el nuevo formato de caso en eDiscovery (Premium)](advanced-ediscovery-new-case-format.md) el nuevo formato de caso se publicó a disponibilidad general y se cambió el nombre de "formato de mayúsculas y minúsculas grandes"

### <a name="retention-and-records-management"></a>Retención y administración de registros
- Implementación: los usuarios pueden eliminar la nueva configuración de administración de registros que controla si los usuarios pueden eliminar los elementos etiquetados en SharePoint y OneDrive. Anteriormente, las etiquetas de retención configuradas para conservar contenido y que no marcaban elementos como registros impedían a los usuarios eliminar contenido etiquetado en SharePoint cuando se permitía esta acción en OneDrive. Para obtener más información, consulte [Funcionamiento de la retención para SharePoint y OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Se han agregado los siguientes artículos nuevos:

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
- El nombre del ámbito de [las etiquetas de Mapa de datos de Microsoft Purview](/azure/purview/create-sensitivity-label) ahora es "Recursos de datos esquematizados".

## <a name="october-2021"></a>Octubre de 2021

### <a name="app-governance"></a>Gobernanza de aplicaciones

- [El complemento de gobernanza de aplicaciones para Defender for Cloud Apps se ha publicado para la disponibilidad general](/cloud-app-security/app-governance-manage-app-governance). La documentación de gobernanza de aplicaciones se ha movido para unirse a la documentación de aplicaciones de Defender for Cloud.

### <a name="compliance--service-assurance"></a>Cumplimiento & garantía de servicio

- [Service Assurance](/compliance) : revisión trimestral de actualizaciones de contenido para certificaciones e instrucciones de aplicabilidad) Administración de recursos del centro de datos
  - Arquitectura e infraestructura del centro de datos
  - Continuidad empresarial del centro de datos y recuperación ante desastres
  - Medidas de seguridad del entorno del centro de datos
  - Seguridad de acceso físico del centro de datos
  - Microsoft 365 programa de cumplimiento de SDL
  - Control de acceso de los ingenieros de servicio de Microsoft 365
  - Guía de evaluación de riesgos para MS Cloud

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- [Obtenga información sobre La prevención de pérdida de datos de Microsoft Purview](endpoint-dlp-learn-about.md) se actualizó para la compatibilidad con macOS y la clasificación avanzada; se ha actualizado para crear una directiva DLP personalizada para auditar la actividad de todos los tipos de archivo admitidos.
- [Comenzar con Microsoft 365 prevención de pérdida de datos de punto de conexión](endpoint-dlp-getting-started.md) se actualizó para la compatibilidad con macOS y la clasificación avanzada.
- [El uso de la prevención de pérdida de datos de punto de conexión](endpoint-dlp-using.md) se actualizó para la compatibilidad con macOS y la clasificación avanzada.
- Se ha actualizado la [referencia de sugerencias de directiva de prevención de pérdida de datos](dlp-policy-tips-reference.md) para la compatibilidad con macOS y la clasificación avanzada.
- Se ha actualizado [la incorporación de dispositivos macOS a Microsoft 365 (versión preliminar)](device-onboarding-macos-overview.md) para la compatibilidad con macOS y la clasificación avanzada.
- Se han agregado las siguientes páginas nuevas para la incorporación de dispositivos:
  - [Incorporación y eliminación de dispositivos macOS en soluciones de Microsoft Purview mediante Intune (versión preliminar)](device-onboarding-offboarding-macos-intune.md)
  - [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante Intune para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-intune-mde.md)
  - [Incorporación y eliminación de dispositivos macOS en soluciones de Microsoft Purview mediante JAMF Pro (versión preliminar)](device-onboarding-offboarding-macos-jamfpro.md)
  - [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-jamfpro-mde.md)

### <a name="ediscovery"></a>eDiscovery

- [Recopilar datos adjuntos en la nube en eDiscovery (Premium)](advanced-ediscovery-cloud-attachments.md) además de recopilar la versión más reciente de un archivo adjunto en la nube, puede recopilar la versión que se ha compartido en un mensaje de correo electrónico o Teams conversación de chat; recopilar la versión compartida es posible gracias a la nueva funcionalidad de aplicar automáticamente una etiqueta de retención a los datos adjuntos en la nube.
- [Configure versiones históricas en la nueva funcionalidad de eDiscovery (Premium)](advanced-ediscovery-historical-versions.md) que indexe todas las versiones de documentos almacenados en un sitio de SharePoint para la búsqueda; esto significa que las versiones de documento que contienen contenido que coinciden con una consulta de colección se devuelven en los resultados de la búsqueda.

### <a name="encryption"></a>Cifrado

- [Use el cifrado de un extremo a otro para las llamadas de Microsoft Teams uno a uno (versión preliminar pública)](/microsoftteams/teams-end-to-end-encryption) Nuevo contenido para la versión preliminar pública.

### <a name="data-lifecycle-management"></a>Administración del ciclo de vida de los datos

- [Configurar un conector para importar datos de auditoría de Epic EHR](import-epic-data.md) nuevo conector le permite importar datos desde el sistema de registros electrónicos de atención sanitaria epic para admitir un nuevo escenario general de uso indebido de datos de pacientes para la administración de riesgos internos.
- [Configurar un conector para importar datos de auditoría de EHR de atención sanitaria](import-healthcare-data.md) Nuevo conector le permite importar datos de un sistema electrónico de registros sanitarios para admitir un nuevo escenario general de uso indebido de datos de pacientes para la administración de riesgos internos.

### <a name="retention-and-records-management"></a>Retención y administración de registros
- [Los ámbitos de directiva adaptables](retention.md#adaptive-or-static-policy-scopes-for-retention) se publican en versión preliminar para las directivas de retención y las directivas de etiqueta de retención.
- Ahora puede [aplicar automáticamente una etiqueta de retención basada en una etiqueta de confidencialidad](apply-retention-labels-automatically.md#identify-files-and-emails-that-have-a-sensitivity-label).
- El plan de archivos tiene un nuevo [proceso de importación](file-plan-manager.md#import-retention-labels-into-your-file-plan).
- [Configuración común para directivas de retención y directivas de etiquetas de retención](retention-settings.md): nuevo artículo para obtener información detallada sobre la configuración de ámbitos adaptables y otras opciones tanto en directivas de retención como en directivas de etiquetas de retención.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

- [Obtenga información sobre el nuevo contenido de entidades con nombre (versión preliminar)](named-entities-learn.md) para entidades con nombre.
- [Use entidades con nombre en el contenido nuevo de las directivas de prevención de pérdida de datos (versión preliminar)](named-entities-use.md) en el uso de entidades con nombre.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- [Las etiquetas predeterminadas y las directivas predeterminadas](mip-easy-trials.md) se implementan para los clientes aptos.

## <a name="september-2021"></a>Septiembre de 2021

### <a name="app-governance"></a>Gobernanza de aplicaciones

- [La información de introducción a la gobernanza de aplicaciones simplificada](app-governance-get-started.md) tiene un flujo de trabajo modificado y se han agregado nuevos vínculos a la suscripción a la versión preliminar pública.
- [Nueva definición de alertas de detección](app-governance-anomaly-detection-alerts.md#app-made-high-volume-of-importance-mail-read-and-created-inbox-rule) agregada (actualizada; nueva definición agregada para las alertas de recopilación)

### <a name="auditing"></a>Auditoría

- [Activar o desactivar la auditoría](turn-audit-log-search-on-or-off.md) Se ha agregado una nueva sección sobre cómo se auditan los cambios en el estado de auditoría de una organización; Esto significa que los registros de auditoría se registran cuando la auditoría está activada o desactivada; puede buscar estos registros de auditoría en el registro de auditoría del administrador de Exchange.

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

- [Cumplimiento de la comunicación con](communication-compliance-siem.md) la guía de soluciones SIEM para la integración de cumplimiento de comunicaciones con soluciones SIEM)

### <a name="compliance-offerings"></a>Ofertas de cumplimiento

- [Seguridad en la nube de varios niveles (MTCS)](/compliance/regulatory/offering-mtcs-singapore) Actualizaciones estándar de Singapur para la cobertura de Dynamics 365
- [Sector de tarjetas de pago (PCI)](/compliance/regulatory/offering-pci-dss) Actualizaciones del Estándar de seguridad de datos (DSS) para SharePoint cobertura en línea
- Guía de software de cliente nueva [de la sección 508 de EE. UU.](/compliance/regulatory/offering-section-508-vpats)
- [Guía de accesibilidad de contenido web](/compliance/regulatory/offering-wcag-2-1) nueva guía de software de cliente

### <a name="compliance--service-assurance"></a>Cumplimiento & garantía de servicio

- [Service Assurance](/compliance/) revisa trimestralmente las actualizaciones de contenido para obtener certificaciones e instrucciones de aplicabilidad
  - Destrucción de dispositivos que contienen datos
  - Ataques DDOS

### <a name="data-connectors"></a>Conectores de datos

- [Archivado de datos de terceros en conectores de datos Microsoft 365](archiving-third-party-data.md#data-connectors-in-the-us-government-cloud) de CellTrust y 17a-4 LLC ahora disponibles en organizaciones GCC en la nube del Gobierno de EE. UU.
- [Configurar un conector para archivar datos de YouTube](archive-youtube-data.md) proporciona nuevas instrucciones para esta característica en versión preliminar pública.

### <a name="ediscovery"></a>eDiscovery

- [Use el editor de KQL para crear consultas de búsqueda](ediscovery-kql-editor.md) en versión preliminar pública de una nueva manera de crear consultas de búsqueda en Búsqueda de contenido, eDiscovery (estándar) y eDiscovery (Premium); el editor de KQL proporciona autocompletar para las propiedades y condiciones admitidas que se pueden buscar y muestra listas de valores admitidos para las propiedades y condiciones estándar; el KQL  editor también proporciona detección de errores y sugerencias para correcciones de posibles errores en las consultas de búsqueda

### <a name="information-barriers"></a>Barreras de información

- [Comenzar con barreras de información](information-barriers-policies.md#step-6-information-barriers-modes) nueva característica de vista previa para los modos de barreras de información
- [Barreras de información con Microsoft Teams](/microsoftteams/information-barriers-in-teams) nueva característica de vista previa para los modos de barreras de información
- [Barreras de información con OneDrive](/onedrive/information-barriers) nueva característica de vista previa para los modos de barreras de información
- [Barreras de información con SharePoint](/sharepoint/information-barriers) nueva característica de vista previa en línea para los modos de barreras de información

### <a name="insider-risk-management"></a>Administración de riesgos internos

- Comenzar con la nueva característica de versión preliminar [de administración de riesgos](insider-risk-management-configure.md#recommended-actions-preview) internos para iniciar las acciones recomendadas
- [Investigación de las actividades de riesgo internos](insider-risk-management-activities.md#get-help-managing-your-insider-risk-alert-queue) nueva sección de guía "Obtener ayuda para administrar la cola de alertas de riesgo internos"
- [Comenzar con la configuración de administración de riesgos internos](insider-risk-management-settings.md#admin-notifications) nueva característica de vista previa de la configuración de notificaciones de administración

### <a name="retention-and-records-management"></a>Retención y administración de registros
- [La revisión de eliminación de varias fases](disposition.md) ya está disponible con carácter general (GA), con nuevos [eventos de auditoría](search-the-audit-log-in-security-and-compliance.md#disposition-review-activities). La revisión de eliminación de varias fases le permite especificar hasta cinco fases consecutivas de revisión de eliminación para una etiqueta de retención, y los revisores pueden agregar otros usuarios a su fase de revisión de eliminación. También puede personalizar las notificaciones por correo electrónico y los avisos.
- Los canales privados para [las directivas de retención de Teams](create-retention-policies.md#retention-policy-for-teams-locations) ahora están disponibles con carácter general (GA).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad
- [La coautoría y autoguardado](sensitivity-labels-coauthoring.md) ahora están disponibles con carácter general (GA) para Windows (versión mínima de 2107 desde canal actual o canal de Enterprise mensual) y macOS (versión mínima de 16.51).
- Implementación para Office aplicaciones que usan etiquetas integradas: la configuración de etiqueta predeterminada ahora admite documentos existentes, así como nuevos documentos. Este cambio de comportamiento proporciona paridad con el cliente de unificación de etiquetado de Azure Information Protection. Para obtener más información sobre el lanzamiento por aplicación y las versiones mínimas, vea la [tabla de funciones](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint) para Word, Excel y PowerPoint.
- Las etiquetas de contenedor ahora admiten [la configuración predeterminada del vínculo de uso compartido mediante la configuración avanzada de PowerShell](sensitivity-labels-teams-groups-sites.md#configure-settings-for-the-default-sharing-link-type-for-a-site-by-using-powershell-advanced-settings).
- Las [tablas de funcionalidades](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) que enumeran las versiones mínimas admitidas para el etiquetado integrado ahora tienen versiones para el canal actual, el canal de Enterprise mensual y el canal de Semi-Annual Enterprise.
