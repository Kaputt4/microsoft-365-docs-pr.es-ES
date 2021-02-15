---
title: Novedades de Cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
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
description: Tanto si va a agregar nuevas soluciones al centro de cumplimiento, actualizar las características existentes en función de sus comentarios o implementar documentación actualizada y actualizada, Microsoft 365 le ayuda a mantenerse al día del cambiante panorama de cumplimiento. Descubra lo que hemos estado haciendo hasta este mes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40140c950bb42078cb1e72ae74762db00a4516b6
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233168"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novedades de Cumplimiento de Microsoft 365

Ya sea agregar nuevas soluciones al Centro de cumplimiento de [Microsoft 365,](microsoft-365-compliance-center.md)actualizar las características existentes en función de sus comentarios o implementar documentación actualizada y actualizada, Microsoft 365 le ayuda a mantenerse al día del cambiante panorama de cumplimiento. Echa un vistazo a continuación para ver las novedades del cumplimiento de Microsoft 365 en la actualidad.

> [!NOTE]
> Algunas características de cumplimiento se implantan a distintas velocidades para nuestros clientes. Si aún no ve una característica, pruebe a agregarse a [la versión dirigida.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)

> [!TIP]
> ¿Te interesa lo que sucede en otros centros de administración? Consulte estos artículos:<br>[Novedades del Centro de administración de Microsoft 365](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[Novedades del Centro de administración de SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Novedades de Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
Y visite el mapa de ruta de [Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) para obtener información sobre las características de Microsoft 365 que se iniciaron, se están implementando, están en desarrollo, se han cancelado o publicado anteriormente.

## <a name="january-2021"></a>Enero de 2021

### <a name="support-for-card-content-in-teams"></a>Compatibilidad con el contenido de tarjetas en Teams

Las siguientes soluciones de cumplimiento de Microsoft 365 ahora admiten la detección de contenido de [tarjetas](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards) generada a través de aplicaciones en mensajes de Teams:

- **EDiscovery básico y avanzado.** El contenido de la tarjeta ahora [se puede colocar en retención](create-ediscovery-holds.md#preserve-card-content) o incluirse en las [búsquedas](https://docs.microsoft.com/microsoftteams/ediscovery-investigation#search-for-card-content) (también se aplica a la búsqueda de contenido).
- **Auditar**. La actividad de la tarjeta se [registra ahora en el registro de auditoría.](https://docs.microsoft.com/microsoftteams/audit-log-events#teams-activities)
- **Directivas de retención**. Ahora puede usar directivas de retención para [conservar y eliminar el contenido de la tarjeta.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Gobierno de la información y administración de registros

[Nueva evaluación para](retention-regulatory-requirements.md#new-zealand-public-records-act) abordar el uso del gobierno de la información y la administración de registros para ayudar a cumplir las obligaciones de cumplimiento de la Ley de registros públicos de Nueva Zelanda.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Las etiquetas de confidencialidad ahora se admiten para los inquilinos de Us Government (GCC y GCC-H).
- Nueva [compatibilidad con el etiquetado](sensitivity-labels-office-apps.md) automático para macOS.

## <a name="december-2020"></a>Diciembre de 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Contenido destacado: nuevo contenido para soluciones de riesgo interno

El equipo de contenido de cumplimiento de Microsoft 365 está trabajando mucho en la creación de documentos de "solución de contenido" para promover el uso conjunto de las capacidades de cumplimiento para ayudar a cumplir los objetivos de cumplimiento.

En primer lugar, se ofrece contenido que une nuestras soluciones de riesgo interno: cumplimiento de comunicaciones, administración de riesgos interno, barreras de información y administración de acceso con privilegios. Este es un vistazo a lo que encontrará:

- [Nueva página de aterrizaje para soluciones de riesgo interno.](insider-risk-solution-overview.md) Incluye detalles sobre los riesgos que las soluciones pueden ayudar a mitigar, los requisitos de licencia, la secuencia de implementación, las ilustraciones de arquitectura, los recursos de aprendizaje y mucho más.
- Nuevos artículos de información general para cada solución de riesgo interno. Instrucciones y vínculos a artículos que le ayudarán a obtener información sobre, planear, implementar y administrar cada solución:
  - [Cumplimiento de las comunicaciones](communication-compliance-solution-overview.md)
  - [Administración de riesgos internos](insider-risk-management-solution-overview.md)
  - [Barreras de información](information-barriers-solution-overview.md)
  - [Administración del acceso con privilegios](privileged-access-management-solution-overview.md)
  
¡Próximamente, más documentos de solución de contenido!

### <a name="advanced-ediscovery"></a>eDiscovery avanzado

Se ha mejorado el flujo de trabajo y la funcionalidad para agregar [administradores](add-custodians-to-case.md) y orígenes de datos que no son [administradores](non-custodial-data-sources.md) a un caso de eDiscovery avanzado.

### <a name="data-connectors"></a>Conectores de datos

Se han publicado cuatro nuevos conectores [globanet:](archiving-third-party-data.md#third-party-data-connectors)Redtail Speak, Salesforce Salesforce Salesforce, ServiceNow y Yieldbroker.

### <a name="encryption"></a>Cifrado

Introducción a [la clave de cliente de Microsoft 365 en el nivel de inquilino.](customer-key-tenant-level.md) Con las claves que proporcione, puede crear una directiva de cifrado de datos (DEP) y asignarla al inquilino. El DEP cifra los datos en todo el espacio empresarial para estas cargas de trabajo:

- Mensajes de chat de Teams (chats de 1:1, chats de grupo, chats de reuniones y conversaciones de canal)
- Mensajes multimedia de Teams (imágenes, fragmentos de código, vídeos, imágenes wiki)
- Grabaciones de llamadas y reuniones de Teams almacenadas en el almacenamiento de Teams
- Notificaciones de chat de Teams
- Sugerencias de chat de Teams de Cortana
- Mensajes de estado de Teams
- Información de usuario y señal para Exchange Online

### <a name="records-management"></a>Administración de registros

El grupo [de roles administración de](get-started-with-records-management.md#permissions-required-for-records-management) administración de registros ahora concede permisos para todas las características de administración de registros, incluida la revisión de disposición.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- [Etiquetar automáticamente los datos en Azure Purview (versión preliminar).](https://docs.microsoft.com/azure/purview/create-sensitivity-label) Ahora puede crear y aplicar automáticamente etiquetas de confidencialidad a los activos de Azure Purview, como archivos de Azure Blob Storage y columnas de base de datos en SQL Server.
- [Requerir que los usuarios apliquen una etiqueta a los elementos](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents). Esta nueva opción, también conocida como "etiquetado obligatorio", requiere que los usuarios elijan y apliquen una etiqueta de confidencialidad en los escenarios específicos.

## <a name="november-2020"></a>Noviembre de 2020
Solo un recordatorio de que a menudo publicamos características nuevas y actualizadas en un estado de vista previa para aprender cómo se usan para que podamos perfeccionarlas y mejorarlas antes de publicarlas a disponibilidad general. Sus comentarios son fundamentales durante la versión preliminar (y posteriores), así que asegúrese de darnos cuenta de lo que piensa abriendo la tarjeta de comentarios en la parte inferior derecha del centro de cumplimiento.

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>Contenido destacado: Prevención de pérdida de datos de puntos de conexión (DLP) publicada

[DLP de punto](endpoint-dlp-learn-about.md) de conexión amplía las capacidades de supervisión y protección de la actividad de DLP a información confidencial en dispositivos Windows 10. Después de incorporar [los dispositivos](dlp-configure-endpoints.md) al Centro de cumplimiento de Microsoft 365, puede configurar directivas DLP para proteger la información confidencial en esos dispositivos.

### <a name="advanced-ediscovery"></a>eDiscovery avanzado

Para facilitar la administración del contenido cifrado en el flujo de trabajo de [](ediscovery-decryption.md) exhibición de documentos electrónicos, las herramientas de exhibición de documentos electrónicos de Microsoft 365 ahora incorporan el descifrado de archivos cifrados que se adjuntan a los mensajes de correo electrónico y se envían en Exchange. Además, los documentos cifrados almacenados en SharePoint y OneDrive se descifran en eDiscovery avanzado.

### <a name="compliance-manager"></a>Administrador de cumplimiento

- [Soporte técnico para suscripciones de Microsoft 365 Administración Gubernamental.](compliance-manager.md) El Administrador de cumplimiento ahora está disponible para los clientes moderados y altos de us Government Community (GCC).
- [Analizador de configuración de cumplimiento de Microsoft para el Administrador de cumplimiento.](compliance-manager-mcca.md) Nueva herramienta basada en PowerShell que le ayuda a empezar a trabajar con el Administrador de cumplimiento mediante el examen de las configuraciones actuales de su organización y su validación con los procedimientos recomendados de Microsoft 365.
- [Nuevas plantillas](compliance-manager-templates-list.md). Se agregaron 56 nuevas plantillas, lo que hace que el total de plantillas del Administrador de cumplimiento supere las 230.

### <a name="data-connectors"></a>Conectores de datos

[Cinco nuevos conectores globanet en versión preliminar.](archiving-third-party-data.md#third-party-data-connectors) Entre los nuevos conectores se incluyen Reuters Dealing, Reuters FX, CellTrust, XIP, MS SQL Database.

### <a name="retention-labels-disposition-review"></a>Etiquetas de retención (revisión de disposición)

Para ver elementos durante una revisión de eliminación, los usuarios deben ser ahora miembros de los grupos de roles Visor de contenido del Explorador de contenido y Visor de listas [del Explorador de contenido.](disposition.md#permissions-for-disposition) Aunque es necesario revisar los elementos, estos grupos de roles no son necesarios para completar la revisión de eliminación.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- [(Versión preliminar) Configuración de uso compartido externo para sitios de SharePoint.](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) Al crear una etiqueta que se usará para grupos y sitios, verá una opción para controlar el uso compartido externo para los sitios de SharePoint que tienen aplicada la etiqueta. Puede especificar que se permite el uso compartido para cualquier persona, invitados nuevos y existentes, solo invitados existentes o solo usuarios de su organización. Cuando se aplica la etiqueta, la configuración de la etiqueta reemplazará cualquier configuración de uso compartido externo [configurada en el Centro de administración de SharePoint](https://docs.microsoft.com/sharepoint/change-external-sharing-site).
- [Quite la etiqueta y el cifrado de un documento con etiqueta.](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document) Para quitar una etiqueta y el cifrado que aplica de un documento etiquetado en SharePoint, los administradores globales y los administradores de SharePoint pueden ejecutar el `Unlock-SPOSensitivityLabelEncryptedFile` nuevo cmdlet. Este cmdlet se ejecuta incluso si el administrador no tiene permisos de acceso al sitio o archivo, o si el servicio Azure Rights Management no está disponible.

## <a name="october-2020"></a>Octubre de 2020

### <a name="advanced-ediscovery"></a>eDiscovery avanzado

[Compatibilidad con el idioma CJK](ediscovery-cjk-support.md). EDiscovery avanzado ahora admite idiomas de juego de caracteres de doble byte, conocidos colectivamente como idiomas CJK (incluye chino simplificado, chino tradicional, japonés y coreano). Pueden usarse en varios escenarios avanzados de conjunto de revisión.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- [Ámbito de etiqueta.](sensitivity-labels.md#label-scopes) Al crear una etiqueta de confidencialidad, verá una nueva opción para definir el ámbito de la etiqueta. Esta opción le permite configurar etiquetas solo para archivos y correos electrónicos, contenedores (como sitios de SharePoint y Teams) o ambos.
- [Marcado de contenido dinámico.](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) Al configurar el marcado de contenido para una etiqueta de confidencialidad, ahora puede usar las variables dinámicas como y en la cadena de texto para el encabezado, pie de página `${Item.Label}` `${Item.Location}` o marca de agua.

## <a name="september-2020"></a>Septiembre de 2020

### <a name="spotlight-compliance-manager"></a>Foco de luz: Administrador de cumplimiento

Anunciada en Ignite este año, la puntuación de cumplimiento se ha cambiado de nombre como [Administrador de cumplimiento.](compliance-manager.md) Esta versión completa la transición de la anterior página principal del Administrador de cumplimiento en el Portal de confianza de servicios e introduce una solución de administración de cumplimiento de un extremo a otro en el Centro de cumplimiento de Microsoft 365.

Vea el vídeo siguiente para obtener información sobre cómo el Administrador de cumplimiento puede ayudar a simplificar la forma en que su organización administra el cumplimiento.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>Auditoría avanzada

- La nueva retención de registros de auditoría de 10 años ayuda a admitir investigaciones de larga duración y responder a obligaciones normativas, legales e internas.
- [Tres nuevos eventos cruciales.](advanced-audit.md#access-to-crucial-events-for-investigations) Los siguientes nuevos eventos pueden ayudarle a investigar posibles infracciones y determinar el ámbito de peligro: Send, SearchQueryInitiatedExchange y SearchQueryInitiatedSharePoint.

### <a name="communication-compliance"></a>Cumplimiento de comunicaciones

- [Grupos de roles actualizados.](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) Los grupos de roles de cumplimiento de comunicaciones ahora coinciden con la estructura del grupo de roles disponible para la solución de administración de riesgos interno.
- [Panel informes](communication-compliance-feature-reference.md#reports-preview). Su ubicación central para ver todos los informes de cumplimiento de comunicaciones. Los widgets de informes proporcionan una vista rápida de las conclusiones más necesarias para una evaluación general del estado de las actividades de cumplimiento de las comunicaciones.
- [Flujos de Power Automate](communication-compliance-feature-reference.md#power-automate-flows). Configurar flujos para automatizar tareas para alertas y usuarios, notificar a los administradores cuando los usuarios desencadenan alertas y mucho más.
- ["Mejorar la clasificación" acción de corrección](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action). Las alertas que contienen elementos que coinciden con clasificadores que se pueden entrenar pueden beneficiarse de los comentarios para ayudar a minimizar los falsos positivos en la organización. La **opción Mejorar clasificación** le permite proporcionar comentarios sobre si los elementos detectados coinciden con el clasificador configurado en la directiva de cumplimiento de comunicaciones relacionada. Incluso puedes sugerir otros clasificadores para asociar con el elemento a fin de mejorar la precisión de coincidencia para futuras alertas.

### <a name="data-connectors"></a>Conectores de datos

- [Nuevos conectores de datos de terceros.](archiving-third-party-data.md#third-party-data-connectors) 25 nuevos conectores de datos, incluidos 14 conectores de Globanet y 8 de Telemessage.
- [Conector de badging físico.](import-physical-badging-data.md) Importe datos de error físicos, como los eventos de acceso físico sin procesar de los empleados o las alarmas de acceso físico generadas por el sistema de protección de la organización. Algunos ejemplos son las entradas a edificios, salas de servidores o centros de datos. La solución de administración de riesgos de Insider puede usar los datos de daños físicos para ayudar a proteger su organización contra actividad malintencionada o robo de datos dentro de la organización.

### <a name="insider-risk-management"></a>Administración de riesgos internos

- [Integración de Microsoft Teams.](insider-risk-management-settings.md#microsoft-teams-preview) Cuando la integración de Teams está activada en la configuración de riesgos interno, puede coordinar y colaborar con otras partes interesadas en Teams en tareas como compartir y almacenar datos de forma segura relacionados con casos individuales, realizar un seguimiento y revisar las actividades de respuesta de analistas e investigadores, etc.
- [Flujos de Power Automate](insider-risk-management-settings.md#power-automate-flows-preview). Configurar flujos para automatizar tareas importantes para casos y usuarios, como recuperar información de usuario, alerta y caso para compartir con las partes interesadas y otras aplicaciones, automatizar acciones como publicar notas de casos y mucho más.
- [Explorador de actividades](insider-risk-management-alerts.md#activity-explorer-preview). Disponible al revisar alertas, el explorador de actividades proporciona a los investigadores y analistas una herramienta analítica completa para profundizar en cada alerta. Revise rápidamente una escala de tiempo de actividad de riesgo detectada e identifique y filtre todas las actividades de riesgo asociadas con las alertas.

### <a name="retention-policies-and-retention-labels"></a>Directivas de retención y etiquetas de retención

- [Compatibilidad con Yammer](retention-policies-yammer.md). Ahora puede usar directivas de retención para retener y eliminar mensajes de la comunidad de Yammer y mensajes privados.
- [Aplicar etiquetas a las grabaciones de reuniones de Teams.](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings) Al crear una directiva de etiquetado automático, use el editor de consultas de palabras clave para identificar las grabaciones de reuniones de Teams almacenadas en las cuentas de OneDrive de los usuarios o en SharePoint.

### <a name="records-management"></a>Administración de registros

[Compatibilidad con registros reglamentarios.](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record) Clasificar una etiqueta como un registro reglamentario aumenta las restricciones que se aplican al contenido al que se aplica la etiqueta y limita las acciones de administración disponibles para la propia etiqueta. Por ejemplo, después de aplicarlo al contenido, nadie, ni siquiera un administrador global, puede quitar la etiqueta. [Obtenga más información](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) sobre las acciones permitidas y bloqueadas para los registros reglamentarios.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

[Soporte técnico para clientes de Us Government.](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description) Las etiquetas de confidencialidad ahora son compatibles con los clientes de GCC, GCC High y DoD, solo para el escáner y el cliente de etiquetado unificado de Azure Information Protection.

### <a name="trainable-classifiers"></a>Clasificadores que se pueden entrenar

Las nuevas capacidades de reentrenamiento y comentarios ayudan a mejorar la precisión y minimizar las coincidencias de falsos positivos para todos los clasificadores personalizados y algunos clasificadores previamente formados. Este flujo te permite proporcionar comentarios sobre si los elementos coinciden con determinados clasificadores, sugerir otros clasificadores para asociar con elementos y volver a entrenar clasificadores para refinar y mejorar la precisión de coincidencia.

Esta nueva funcionalidad se incluye en las siguientes características:

> [!NOTE]
> Para todas las características, si proporcionas al menos 30 respuestas de comentarios, crearemos una versión reentrenada de ese clasificador que puedes revisar. Si hay mejoras, puede volver a publicar el clasificador.

- [Clasificadores que se pueden entrenar.](classifier-learn-about.md#retraining-classifiers) Para mejorar la precisión de los clasificadores publicados, puedes proporcionar comentarios sobre si los elementos detectados coinciden con el clasificador.
- [Cumplimiento de comunicaciones.](classifier-how-to-retrain-comms-compliance.md) La nueva **acción de corrección** mejorar la clasificación le permite proporcionar comentarios si un elemento de una alerta de cumplimiento de comunicaciones coincide con el clasificador configurado en la directiva de cumplimiento de comunicaciones.
- [Explorador de contenido.](classifier-how-to-retrain-content-explorer.md) Si configura una directiva de etiquetado automático de retención para aplicar automáticamente etiquetas a los mensajes de correo electrónico que coinciden con clasificadores que se pueden entrenar, puede usar el explorador de contenido para revisar los elementos etiquetados y proporcionar comentarios si los elementos coinciden con el clasificador.

## <a name="august-2020"></a>Agosto de 2020

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>Contenido destacado: actualizaciones de cumplimiento de comunicaciones y riesgos de Insider

Varias características nuevas y mejoradas alcanzaron la versión preliminar pública este mes:

**Administración de riesgos internos**

- Echa un vistazo a nuestras seis nuevas [plantillas de directiva:](insider-risk-management-policies.md#policy-templates)
    - Pérdidas de datos por usuarios prioritarios
    - Pérdidas de datos de usuarios descontentos
    - Infracciones de la directiva de seguridad general
    - Infracciones de la directiva de seguridad al abandonar usuarios
    - Infracciones de directivas de seguridad por parte de usuarios prioritarios
    - Infracciones de la directiva de seguridad por parte de usuarios descontentos

- La integración [con Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) le permite importar y filtrar alertas de Puntos de conexión de Microsoft Defender para actividades detectadas por directivas creadas a partir de las nuevas plantillas de directiva de infracción de seguridad. También hay una [](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) configuración de riesgos interno relacionada en la que puedes elegir importar alertas de seguridad a la administración de riesgos de Insider en función del estado de evaluación de alertas de Microsoft Defender para puntos de conexión.

    > [!NOTE]
    > Para aprovechar la integración de Microsoft Defender para puntos de conexión (incluidas las nuevas plantillas de infracción de directivas de seguridad), debes configurar Microsoft Defender para Endpoint en tu organización. También tendrás que habilitar Microsoft Defender para Endpoint para la integración de la administración de riesgos interno mediante la configuración de características avanzadas en [Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- Personalizar umbrales de indicador al [crear una directiva](insider-risk-management-policies.md#create-a-new-policy).
- Configure grupos [de](insider-risk-management-settings.md#priority-user-groups-preview) usuarios de prioridad para definir usuarios de su organización cuya actividad requiera una inspección más detallada en función de factores como su posición, nivel de acceso a información confidencial o historial de riesgos.
- Use las API de actividad de [](insider-risk-management-settings.md#export-alerts-preview) administración de Office 365 para exportar detalles de alertas de riesgo interno a otras aplicaciones que su organización pueda usar para administrar o agregar datos de riesgo interno.
- Las [nuevas configuraciones de](insider-risk-management-settings.md#domains-preview) dominio le ayudan a definir y controlar los niveles de riesgo de la actividad en dominios específicos.

**Cumplimiento de las comunicaciones**

- Al [revisar los mensajes en una](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)alerta, ahora puede quitar mensajes inapropiados en los canales de Microsoft Teams, 1:1 y los chats de grupo. Los mensajes y el contenido eliminados se reemplazan por una sugerencia de directiva que explica que se quitó debido a contenido confidencial.
- Nuevas [funciones de comunicación](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (también se incluirán en los nuevos grupos de roles de cumplimiento de comunicaciones que se publicarán en septiembre).
- Nueva experiencia de configuración de cumplimiento de comunicaciones que incluye la configuración de [la privacidad y](communication-compliance-feature-reference.md#privacy) las plantillas de [aviso.](communication-compliance-feature-reference.md#notice-templates)
- Nuevos [clasificadores para ayudar](communication-compliance-feature-reference.md#classifiers) a detectar imágenes para adultos, racy y gory.
- La nueva notificación "Patrón [](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) detectado" que aparece al revisar los mensajes de una alerta le permite saber si un usuario vuelve a detectar instancias del mismo comportamiento.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Para los inquilinos del Gobierno de los EE. UU. (GCC, GCC-H y DoD), las etiquetas de confidencialidad solo son compatibles con el cliente de etiquetado unificado y el escáner de Azure Information Protection. Para obtener más información, consulte la [Descripción del servicio Premium para la Administración Pública de Azure Information Protection](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).
- Ahora puede usar [PowerShell del Centro de & seguridad](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) y cumplimiento para crear y configurar todas las opciones que ve en el Centro de administración de etiquetas. Esto significa que, además de usar PowerShell para la configuración que no está disponible en los centros de administración de etiquetas, ahora puede crear scripts completos de creación y mantenimiento de etiquetas de confidencialidad y directivas de etiquetas de confidencialidad.

### <a name="records-management-content-overhaul"></a>Administración de registros: revisión de contenido

Nuevos documentos que cubren los pasos de implementación, el marcado de contenido como registros y el control de versiones de registros:

- [Introducción a la administración de registros](get-started-with-records-management.md)
- [Use etiquetas de retención para declarar registros](declare-records.md)
- [Use el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive](record-versioning.md)

### <a name="retention-labels--policies"></a>Etiquetas de retención & directivas

La actividad de administración relacionada con la retención ahora se registra y está disponible para su revisión en el registro de auditoría. Para obtener la lista completa, consulte las [Actividades de las directivas y etiquetas de retención](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

### <a name="advanced-ediscovery"></a>eDiscovery avanzado

- Al [agregar una colección a un conjunto](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)de revisión, ahora puede incluir datos adjuntos modernos (también denominados "datos adjuntos en la nube") y versiones de documentos de SharePoint.
- Nueva [experiencia de exportación de descarga directa,](export-documents-from-review-set.md)lo que elimina la necesidad de usar el Explorador de Azure Storage para descargar el contenido de casos.
