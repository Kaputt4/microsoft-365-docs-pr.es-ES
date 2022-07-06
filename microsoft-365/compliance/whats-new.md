---
title: Novedades de las soluciones de cumplimiento y riesgo de Microsoft Purview
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
ms.openlocfilehash: 828389ded4e62b7cc7f7bbb1a0da8ef3534b6a58
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66637791"
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

## <a name="may-2022"></a>Mayo de 2022

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

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

## <a name="april-2022"></a>Abril de 2022

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

- [Crear y administrar directivas de cumplimiento de comunicaciones](communication-compliance-policies.md) : se ha actualizado con las instrucciones agregadas para la nueva característica de directiva de mensajes notificada por el usuario para la integración de Microsoft Teams.
- [Introducción al cumplimiento de comunicaciones](communication-compliance-configure.md) : se ha actualizado para agregar aclaraciones sobre la suscripción y las licencias de F5.

### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Lista de plantillas del Administrador](compliance-manager-templates-list.md) de cumplimiento: se han agregado 6 nuevas plantillas y vínculos de navegación en la página para saltar más fácilmente a las categorías de plantillas.
- [Información general del Administrador de cumplimiento](compliance-manager.md) : vídeo de información general del producto actualizado.

### <a name="compliance-offerings--service-assurance"></a>Ofertas de cumplimiento & garantía de servicio

- [Ofertas de cumplimiento](/compliance/regulatory/offering-home) : actualizaciones para la cobertura de servicios e informes de auditoría para las ofertas de VPATS, SOC, ISO y FedRAMP.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- Con el [cambio de nombre del producto](#changes-to-product-names), se cambia el nombre **de Administración** **del ciclo de vida** de datos en el portal de cumplimiento.
- Actualmente en implementación: nuevo diseño para la configuración de la etiqueta de retención.
- Lanzamiento actualmente: nueva opción de etiqueta en versión preliminar, "Desbloquear este registro de forma predeterminada". Para obtener más información, vea [Configuración de etiquetas de retención para declarar registros](declare-records.md#configuring-retention-labels-to-declare-records) y [Uso del control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive](record-versioning.md).

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- Artículos actualizados para la disponibilidad general de incorporación de dispositivos macOS:
  - [Más información sobre dlp de punto de conexión](endpoint-dlp-learn-about.md)
  - [Configuración de la prevención de pérdida de datos de punto de conexión](dlp-configure-endpoint-settings.md)
  - [Planear la prevención de pérdida de datos (DLP)](dlp-overview-plan-for-dlp.md)
  - [Referencia de directiva de prevención de pérdida de datos](dlp-policy-reference.md)
  - [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)
- [Condiciones, excepciones y acciones de directiva DLP:](dlp-conditions-and-exceptions.md) se han agregado instrucciones para modificar la acción del sujeto.
- Referencia de directiva [de prevención de pérdida de datos: predicados](dlp-policy-reference.md) de SPO/ODB de GA; se ha actualizado con nuevas instrucciones sobre el procesamiento de reglas en puntos de conexión.

### <a name="device-onboarding"></a>Incorporación de dispositivos

- Artículos actualizados para la disponibilidad general de incorporación de dispositivos macOS:
  - [Introducción a la incorporación de dispositivos macOS en a Microsoft 365](device-onboarding-macos-overview.md)
  - [Incorporar y retirar dispositivos macOS en soluciones de cumplimiento con Intune para clientes de Microsoft Defender para punto de conexión](device-onboarding-offboarding-macos-intune-mde.md)
  - [Incorporar y desactivar dispositivos macOS en soluciones de Microsoft Purview mediante Intune](device-onboarding-offboarding-macos-intune.md)
  - [Incorporación y retirada de dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes de Microsoft Defender para punto de conexión](device-onboarding-offboarding-macos-jamfpro-mde.md)
  - [Incorporación y eliminación de dispositivos macOS en soluciones de Microsoft Purview mediante JAMF Pro](device-onboarding-offboarding-macos-jamfpro.md)

### <a name="information-barriers"></a>Barreras de información

- [Usar barreras de información con SharePoint: instrucciones agregadas](/sharepoint/information-barriers) para la nueva compatibilidad con canales privados en SharePoint.
- [Administrar directivas de barreras de información](information-barriers-edit-segments-policies.md) : guía agregada para quitar segmentos y directivas o segmentos juntos.

### <a name="microsoft-priva"></a>Microsoft Priva

- [Directivas de administración de riesgos de privacidad](/privacy/priva/risk-management) : nuevas páginas, actualizaciones significativas y reestructuración del contenido de las directivas; detalles siguientes:
  - [Directivas de administración de riesgos de privacidad](/privacy/priva/risk-management-policies) : se han agregado detalles significativos sobre la configuración y administración de directivas que se aplican a todas las directivas; se han agregado vínculos a páginas nuevas para cada uno de los tres tipos de directiva.
  - [Directivas de sobreexposición de datos](/privacy/priva/risk-management-policy-data-overexposure) : articula la necesidad y los usos de la directiva; explica la configuración predeterminada para la creación inmediata y las instrucciones detalladas para personalizar la configuración.
  - [Directivas de transferencia de datos](/privacy/priva/risk-management-policy-data-transfer) : resalta la nueva condición para que la directiva detecte transferencias fuera de la organización; articula la necesidad y los usos de la directiva; explica la configuración predeterminada para la creación inmediata y las instrucciones detalladas para personalizar la configuración.
  - [Directivas de minimización de datos](/privacy/priva/risk-management-policy-data-minimization) : articula la necesidad y los usos de la directiva; explica la configuración predeterminada para la creación inmediata y las instrucciones detalladas para personalizar la configuración.
  - [Investigar y corregir alertas](/privacy/priva/risk-management-alerts) : se han agregado detalles aclarantes y cambios de formato para mejorar la legibilidad.
  - [Notificaciones de usuario](/privacy/priva/risk-management-notifications) : se ha agregado información sobre la funcionalidad para obtener una vista previa y personalizar el contenido de las notificaciones por correo electrónico.
- [Creación de una solicitud de derechos de sujeto](/privacy/priva/subject-rights-requests-create) : se ha agregado una sección para empezar a trabajar con la primera solicitud con la configuración predeterminada para explorar la funcionalidad.
- [Revisar los datos de una solicitud de derechos del interesado](/privacy/priva/subject-rights-requests-data-review) : se han agregado detalles que explican los elementos de prioridad que se deben revisar y cómo encontrarlos, y la necesidad de configurar la coincidencia de datos para obtener esta información.
- [Búsqueda y visualización de datos personales](/privacy/priva/priva-data-profile) : se ha aclarado que los usuarios deben configurar la coincidencia de datos con el fin de recibir información sobre "Elementos con el contenido del interesado más importante" en "Información clave".
- [Coincidencia de datos para solicitudes de derechos del interesado](/privacy/priva/subject-rights-requests-data-match) : aclaró la progresión del paso en este proceso y agregó el segundo paso para crear tipos de información confidencial.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

- [Usar entidades con nombre en directivas DLP](named-entities-use.md) : disponibilidad general de entidades con nombre.
- [Obtenga información sobre las entidades con nombre](named-entities-learn.md) : disponibilidad general de entidades con nombre.
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md) : disponibilidad general de entidades con nombre y actualizaciones de patrones.
- [Obtenga información sobre los tipos de información confidencial](sensitive-information-type-learn-about.md) : disponibilidad general de entidades con nombre.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Escenario recién admitido para sitios de SharePoint, ahora en versión preliminar: [Configurar permisos de uso compartido de sitios mediante la configuración avanzada de PowerShell](sensitivity-labels-teams-groups-sites.md#configure-site-sharing-permissions-by-using-powershell-advanced-settings)
- [La coautoría de archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md) ya está disponible para realizar pruebas con el canal Semi-Annual Enterprise Channel (versión preliminar).
- Las cuentas de OneDrive eliminadas ahora se muestran correctamente en los resultados de la simulación para las directivas de etiquetado automático.
- Problema conocido si [asigna permisos a contactos de correo en grupos](/office365/troubleshoot/sensitivity-labels/mail-contacts-lose-access-encrypted-content) al configurar una etiqueta de confidencialidad para el cifrado.

### <a name="changes-to-product-names"></a>Cambios en los nombres de producto

Para satisfacer los desafíos del área de trabajo descentralizada y rica en datos de hoy en día, presentamos [Microsoft Purview](https://aka.ms/microsoftpurview), un completo conjunto de soluciones que le ayuda a comprender, gobernar y proteger todo el patrimonio de datos. Esta nueva familia de marcas combina las funcionalidades de la antigua Mapa de datos de Microsoft Purview y la cartera de cumplimiento de Microsoft 365 en la que ya confían los clientes, lo que proporciona una gobernanza de datos unificada y administración de riesgos para su organización.

| **Nombre anterior** | **Nombre nuevo** | **Description** |
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

## <a name="march-2022"></a>Marzo de 2022

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

- [Investigar y corregir alertas de cumplimiento de comunicaciones](communication-compliance-investigate-remediate.md) : se han quitado las instrucciones para la vista de anotación en desuso.

### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Trabajando con acciones de mejora](compliance-manager-improvement-actions.md), [Introducción al Administrador de cumplimiento](compliance-manager-setup.md) : se ha agregado información sobre más acciones de mejora que se pueden supervisar y probar automáticamente ("evaluación continua del cumplimiento"). esto incluye nuevas capacidades para crear el estado de prueba de una acción a la de otra acción.

### <a name="data-classification"></a>Clasificación de los datos

- [Introducción al Explorador de contenido](data-classification-content-explorer.md) : instrucciones de Teams agregadas, sección de licencias que apunta a descripciones de servicio.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- [Las directivas de retención para Yammer](create-retention-policies.md#retention-policy-for-yammer-locations) ahora están disponibles con carácter general (GA).
- Compatibilidad con canales compartidos, actualmente en versión preliminar. Al configurar una directiva de retención para la ubicación del mensaje del canal de Teams, los canales compartidos heredan la configuración de retención de su equipo primario.
- [Límites por inquilino para la eliminación de contenido](retention-limits.md#maximum-number-of-items-for-disposition).

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

- [Prevención de pérdida de datos y Microsoft Teams](dlp-microsoft-teams.md) : versión preliminar pública del contenido de Los canales de Share Teams.
- [Introducción a la extensión de cumplimiento de Microsoft](dlp-chrome-get-started.md) : versión preliminar pública de grupos de aplicaciones restringidos, eliminación de instrucciones de clave del Registro y configuración ahora habilitada de forma predeterminada.
- [Configuración de las opciones de prevención de pérdida de datos del punto de conexión](dlp-configure-endpoint-settings.md) : novedades de la versión preliminar pública de grupos de aplicaciones restringidos.
- Referencia de directiva [de prevención de pérdida de datos](dlp-policy-reference.md): se ha actualizado para la versión preliminar pública de los grupos de aplicaciones restringidos.
- [Introducción a la prevención de pérdida de datos para Power BI](dlp-powerbi-get-started.md) : novedades de la versión preliminar pública.
- 
### <a name="information-protection"></a>Protección de la información

- [Compatibilidad con notas de la versión del juego de caracteres de doble byte](mip-dbcs-relnotes.md) : se han agregado instrucciones para macOS.
- 
### <a name="insider-risk-management"></a>Administración de riesgos internos

- [Introducción a la administración de riesgos internos](insider-risk-management-configure.md) : se han agregado nuevas tareas para la guía acciones recomendadas.
- [Introducción a la configuración de administración de riesgos](insider-risk-management-settings.md) internos: nuevas actualizaciones para las características de notificaciones y alertas por correo electrónico, nuevas actualizaciones para las notificaciones de análisis.

### <a name="microsoft-priva"></a>Microsoft Priva

- [Configurar la configuración de Priva](/privacy/priva/priva-settings) : se ha actualizado información aclarante sobre los períodos de retención de datos para las solicitudes de derechos del interesado; se agregaron detalles sobre cómo administrar y aplicar etiquetas de revisión de datos para solicitudes de derechos del interesado.
- [Crear una solicitud de derechos de sujeto](/privacy/priva/subject-rights-requests-create) : se han agregado detalles sobre cómo refinar búsquedas y elegir condiciones y atributos; se ha agregado información sobre la nueva funcionalidad que permite a los usuarios seleccionar todas las versiones de elementos de SharePoint en su búsqueda (frente a la configuración predeterminada, que solo devuelve la versión actual de los elementos de SharePoint).
- [Revisar los datos de una solicitud de derechos del interesado](/privacy/priva/subject-rights-requests-data-review) : se han agregado detalles en el paso 3 para revisar elementos durante la fase de revisión de datos, incluido el marcado de archivos como inclusión o exclusión, la anotación de archivos para aplicar censuras, la aplicación de etiquetas y la introducción de notas.
- [Generación de informes y cumplimiento de una solicitud de derechos de sujeto](/privacy/priva/subject-rights-requests-reports) : se han agregado detalles sobre cómo comprender los informes; aclarado cuando se genera un paquete de exportación y cómo trabajar con su contenido; se ha agregado información sobre los registros de auditoría, los informes de archivos etiquetados y los períodos de retención de los datos e informes de SRR.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- [Etiquetas de confidencialidad para Teams](sensitivity-labels-teams-groups-sites.md):
  - Compatibilidad con canales compartidos, actualmente en versión preliminar. Si un equipo tiene canales compartidos, hereda automáticamente la configuración de etiqueta de confidencialidad de su equipo primario y esa etiqueta no se puede quitar ni reemplazar con una etiqueta diferente.
  - Compatibilidad con plantillas, enumeradas anteriormente como [no compatibles con las API de Graph de Teams y los cmdlets de PowerShell]( /microsoftteams/sensitivity-labels#limitations).  
- Para auditar Word, Excel y PowerPoint en la Web, el texto de justificación ahora está totalmente implementado.
- La aplicación de una etiqueta predeterminada a documentos existentes para Word, Excel y PowerPoint en la Web ahora está totalmente implementado.

## <a name="february-2022"></a>Febrero de 2022

### <a name="ediscovery"></a>eDiscovery

- [Administrar plantillas de comunicaciones de custodios en eDiscovery (Premium):](advanced-ediscovery-communications-library.md) los administradores de eDiscovery ahora pueden crear plantillas de comunicaciones custodios que se pueden usar en cualquier caso de eDiscovery (Premium) de la organización.
- [Administrar oficiales emisores en eDiscovery (Premium):](advanced-ediscovery-issuing-officers.md) los administradores de eDiscovery pueden agregar una lista de oficiales emisores que se pueden asignar a las comunicaciones de custodio en cualquier caso de exhibición de documentos electrónicos (Premium) de la organización.

### <a name="data-lifecycle-management-and-records-management"></a>Administración del ciclo de vida de los datos y administración de registros

- [Los ámbitos adaptables para las directivas](retention.md#adaptive-or-static-policy-scopes-for-retention) de retención y las directivas de etiqueta de retención ahora están disponibles con carácter general (GA). Las instrucciones para [configurar un ámbito adaptable](retention-settings.md#to-configure-an-adaptive-scope) ahora incluyen más información para los ámbitos de sitio de SharePoint: referencia de entrada de blog para usar propiedades de sitio personalizadas y cómo usar la propiedad site SiteTemplate para incluir o excluir tipos de sitio específicos con el generador de consultas avanzadas.
- [La búsqueda de directivas](retention.md#policy-lookup) en la solución de administración del ciclo de vida de datos ya está disponible con carácter general (GA).
- Alternativa de PowerShell a la configuración de administración de registros que permite a los usuarios eliminar elementos etiquetados en SharePoint y OneDrive mediante AllowFilesWithKeepLabelToBeDeletedSPO y AllowFilesWithKeepLabelToBeDeletedODB desde [Get-PnPTenant](https://pnp.github.io/powershell/cmdlets/Get-PnPTenant.html) y [Set-PnPTenant](https://pnp.github.io/powershell/cmdlets/Set-PnPTenant.html).

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Nueva guía [Por qué elegir el etiquetado integrado en el complemento AIP para aplicaciones de Office](sensitivity-labels-aip.md) si usa el cliente de etiquetado unificado de Azure Information Protection (AIP) para equipos Windows. Esta página incluye información sobre la nueva versión preliminar privada para aplicaciones de Office.
- Nueva configuración para las [directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange):
  - Configuración adicional del correo electrónico para admitir siempre la aplicación de una etiqueta de confidencialidad coincidente y aplicar el cifrado al correo electrónico recibido desde fuera de la organización.
  - Las exclusiones de instancias específicas (usuarios, grupos, sitios) se admiten mediante la nueva opción **Excluir** cuando se especifica la selección predeterminada de **Todos** para **Incluido**.
- Ahora en versión preliminar: los dispositivos móviles (iOS y Android) admiten [la coautoría](sensitivity-labels-coauthoring.md) cuando tiene versiones mínimas y opta por esta versión preliminar.
- La compatibilidad para establecer el tipo de vínculo de uso compartido predeterminado se extiende a documentos individuales en SharePoint y OneDrive. Para obtener más información, vea el nuevo artículo [Uso de etiquetas de confidencialidad para configurar el tipo de vínculo de uso compartido predeterminado para sitios y documentos en SharePoint y OneDrive]( sensitivity-labels-default-sharing-link.md).
- El Centro de administración de Teams ahora admite etiquetas de contenedor (etiquetas de confidencialidad con el ámbito de Grupos & sitios).

## <a name="january-2022"></a>Enero de 2022

### <a name="microsoft-purview-data-lifecycle-management"></a>Administración del ciclo de vida de datos de Microsoft Purview

- La documentación de lo que anteriormente era Microsoft Information Governance se ha revisado y reestructurado sustancialmente para ayudarle a encontrar más fácilmente información relacionada con las soluciones que se configuran en la portal de cumplimiento Microsoft Purview: Data Connectors, Data Lifecycle Management y Records Management. Como parte de esta revisión, la documentación proporciona una distinción más clara para los escenarios de retención para la administración del ciclo de vida de datos frente a la administración de registros.
- [Obtenga información sobre la administración del ciclo de vida de los datos](data-lifecycle-management.md) : novedades, para admitir la reestructuración.
- [Introducción a la administración del ciclo de vida de los datos](get-started-with-data-lifecycle-management.md) : novedad para reemplazar "Introducción a la retención", en este artículo se incluyen los pasos de introducción a todas las funcionalidades de administración del ciclo de vida de datos, que incluyen la retención.
- [Cree etiquetas de retención para excepciones a las directivas de retención](create-retention-labels-data-lifecycle-management.md) : escenario nuevo e identificado para usar etiquetas de retención para la administración del ciclo de vida de datos en lugar de la administración de registros.
- [Obtenga información sobre los buzones de archivo](archive-mailboxes.md) : nuevo, para admitir la reestructuración, contiene información conceptual que se encontraba anteriormente en el artículo "Habilitar buzones de archivo".

### <a name="microsoft-priva"></a>Microsoft Priva

- [La administración de la privacidad está ahora Microsoft Priva](/privacy/priva/priva-overview): se ha actualizado para cambiar el nombre del producto y sus soluciones, Administración de riesgo de privacidad Priva y Solicitudes de los interesados Priva.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Compatibilidad con nuevos [roles y grupos de roles](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels), ahora en versión preliminar.
- Nuevas [funcionalidades de supervisión](apply-sensitivity-label-automatically.md#monitoring-your-auto-labeling-policy) para directivas de etiquetado automático.
- Implementación ahora: etiqueta predeterminada para documentos existentes y texto de justificación para Office en la Web.
- Anunciado para julio Semi-Annual Enterprise Channel con la versión 2202+: Coautoría y auditoría para Outlook.

## <a name="december-2021"></a>Diciembre de 2021

### <a name="compliance-and-service-assurance"></a>Cumplimiento y garantía de servicio

- [Notificación de infracción de Azure, Dynamics 365 y Windows en virtud del RGPD](/compliance/regulatory/gdpr-breach-notification) : se ha actualizado para aclarar que los clientes no necesitan usar un servicio de pago como Defender for Cloud para recibir notificaciones de seguridad y privacidad.

### <a name="ediscovery"></a>eDiscovery

- [Flujo de trabajo de eDiscovery (Premium) para contenido en Microsoft Teams](teams-workflow-in-advanced-ediscovery.md#reference-guide) : se ha actualizado con una nueva guía de referencia rápida descargable para administrar el contenido de Teams en eDiscovery (Premium)

### <a name="data-lifecycle-management"></a>Administración del ciclo de vida de los datos

- [Habilitar buzones de archivo en el centro de cumplimiento](enable-archive-mailboxes.md#run-diagnostics-on-archive-mailboxes) : se ha agregado una sección sobre la nueva herramienta de diagnóstico para buzones de archivo.
- [Uso de la carga de red para importar archivos PST de la organización a Microsoft 365](use-network-upload-to-import-pst-files.md#step-2-upload-your-pst-files-to-microsoft-365) : la importación de PST ahora admite AzCopy v10
- [Restauración de un buzón inactivo](restore-an-inactive-mailbox.md) : procedimiento revisado para restaurar un buzón inactivo agregando primero LegacyExchangeDN del buzón inactivo al buzón de destino

### <a name="information-protection"></a>Protección de la información

- [Implementación de una solución de protección de la información con Microsoft Purview](information-protection-solution.md): nueva guía paso a paso para los clientes que buscan una hoja de ruta prescriptiva para implementar Microsoft Purview Information Protection

### <a name="retention-and-records-management"></a>Retención y administración de registros

- Nuevas instrucciones sobre [cuánto tiempo tardan las directivas de retención en surtir efecto](create-retention-policies.md#how-long-it-takes-for-retention-policies-to-take-effect)
- Nueva configuración de inquilino que se implementa: una configuración de administración de registros que impide la edición de propiedades para elementos de SharePoint etiquetados que están marcados como un registro y bloqueados, y otra configuración para evitar que los usuarios desbloqueen elementos marcados como un registro

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- El etiquetado obligatorio y una etiqueta predeterminada para Power BI ahora están disponibles con carácter general (GA)
