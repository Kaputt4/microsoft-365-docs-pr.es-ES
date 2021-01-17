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
ms.openlocfilehash: 8723171820bb1c089d34b81f5adb6663ecc9b8af
ms.sourcegitcommit: 27cb4591e08f62ba0a08d6dcf224bf2039034fe5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2021
ms.locfileid: "49883719"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novedades de Cumplimiento de Microsoft 365

Ya sea agregar nuevas soluciones al Centro de cumplimiento de [Microsoft 365,](microsoft-365-compliance-center.md)actualizar las características existentes en función de sus comentarios o implementar documentación actualizada y actualizada, Microsoft 365 le ayuda a mantenerse al día del cambiante panorama de cumplimiento. Echa un vistazo a continuación para ver las novedades del cumplimiento de Microsoft 365 en la actualidad. 

> [!NOTE]
> Algunas características de cumplimiento se implantan a distintas velocidades para nuestros clientes. Si aún no ve una característica, pruebe a agregarse a [la versión dirigida.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)


> [!TIP]
> ¿Te interesa lo que sucede en otros centros de administración? Consulte estos artículos:<br>[Novedades del Centro de administración de Microsoft 365](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[Novedades del Centro de administración de SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Novedades de Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
Y visite el mapa de ruta de [Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) para obtener información sobre las características de Microsoft 365 que se iniciaron, se están implementando, están en desarrollo, se han cancelado o publicado anteriormente.

## <a name="november--december-2020"></a>Noviembre & diciembre de 2020
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
    > Para aprovechar la integración de Microsoft Defender para puntos de conexión (incluidas las nuevas plantillas de infracción de directivas de seguridad), deberá configurar Microsoft Defender para Endpoint en su organización. También tendrás que habilitar Microsoft Defender para Endpoint para la integración de la administración de riesgos interno mediante la configuración de características avanzadas en [Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- Personalizar umbrales de indicador al [crear una directiva](insider-risk-management-policies.md#create-a-new-policy).
- Configure grupos [de](insider-risk-management-settings.md#priority-user-groups-preview) usuarios de prioridad para definir usuarios de su organización cuya actividad requiera una inspección más detallada en función de factores como su posición, nivel de acceso a información confidencial o historial de riesgos.
- Use las API de actividad de [](insider-risk-management-settings.md#export-alerts-preview) administración de Office 365 para exportar detalles de alertas de riesgo interno a otras aplicaciones que su organización pueda usar para administrar o agregar datos de riesgo interno.
- Las [nuevas configuraciones de](insider-risk-management-settings.md#domains-preview) dominio le ayudan a definir y controlar los niveles de riesgo de la actividad en dominios específicos.

**Cumplimiento de las comunicaciones**

- Al [revisar los mensajes en una alerta,](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)ahora puede quitar mensajes inapropiados en los canales de Microsoft Teams, 1:1 y los chats de grupo. Los mensajes y el contenido eliminados se reemplazan por una sugerencia de directiva que explica que se quitó debido a contenido confidencial.
- Nuevas [funciones de comunicación](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (también se incluirán en los nuevos grupos de roles de cumplimiento de comunicaciones que se publicarán en septiembre).
- Nueva experiencia de configuración de cumplimiento de comunicaciones que incluye la configuración de [la privacidad y](communication-compliance-feature-reference.md#privacy) las plantillas de [aviso.](communication-compliance-feature-reference.md#notice-templates)
- Nuevos [clasificadores para ayudar](communication-compliance-feature-reference.md#classifiers) a detectar imágenes para adultos, racy y gory.
- La nueva notificación "Patrón [](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) detectado" que aparece al revisar mensajes en una alerta le permite saber si un usuario vuelve a detectar instancias del mismo comportamiento.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

- Para los inquilinos del Gobierno de los EE. UU. (GCC, GCC-H y DoD), las etiquetas de confidencialidad solo son compatibles con el cliente de etiquetado unificado y el escáner de Azure Information Protection. Para obtener más información, consulte la [Descripción del servicio Premium para la Administración Pública de Azure Information Protection](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).
- Ahora puede usar [PowerShell del Centro & seguridad y](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) cumplimiento para crear y configurar todas las opciones que ve en el Centro de administración de etiquetas. Esto significa que, además de usar PowerShell para la configuración que no está disponible en los centros de administración de etiquetas, ahora puede crear scripts completos de creación y mantenimiento de etiquetas de confidencialidad y directivas de etiquetas de confidencialidad.

### <a name="records-management-content-overhaul"></a>Administración de registros: revisión de contenido

Nuevos documentos que cubren los pasos de implementación, el marcado de contenido como registros y el control de versiones de registros:

- [Introducción a la administración de registros](get-started-with-records-management.md)
- [Use etiquetas de retención para declarar registros](declare-records.md)
- [Use el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive](record-versioning.md)

### <a name="retention-labels--policies"></a>Etiquetas de retención & directivas

La actividad de administración relacionada con la retención ahora se registra y está disponible para su revisión en el registro de auditoría. Para obtener la lista completa, consulte las [Actividades de las directivas y etiquetas de retención](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

### <a name="advanced-ediscovery"></a>eDiscovery avanzado

- Al [agregar una colección a un conjunto](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)de revisión, ahora puede incluir datos adjuntos modernos (también denominados "datos adjuntos en la nube") y versiones de documentos de SharePoint.
- Nueva [experiencia de exportación de descarga directa,](export-documents-from-review-set.md)lo que elimina la necesidad de usar azure Storage Explorer para descargar el contenido de casos.


## <a name="july-2020"></a>Julio de 2020

### <a name="spotlight-on-help-docs"></a>Foco de luz sobre documentos de ayuda

Para ayudarle a comprender qué soluciones de cumplimiento se usan para proteger y gobernar los datos confidenciales de su organización, hemos creado dos nuevas páginas de aterrizaje con información general sobre cómo funcionan conjuntamente las soluciones para lograr esos objetivos, incluidos vínculos a documentos relacionados para que pueda profundizar.

[Microsoft Information Protection en Microsoft 365.](information-protection.md)<br>
[Gobierno de la información de Microsoft en Microsoft 365](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>Exhibición avanzada de documentos electrónicos: agregar orígenes de datos que no son de custodia a sus casos

Agregue datos a un caso sin tener que asociarlos con un administrador (conocido como orígenes de datos que no [son administradores).](non-custodial-data-sources.md) Y si necesita poner estos datos no custodiados en retención, podrá hacerlo con nuestra nueva característica de indización avanzada.

### <a name="data-connectors-hr-connector-enhancements"></a>Conectores de datos: mejoras del conector de RECURSOS

(En versión preliminar) Una nueva versión del conector de [RECURSOS](import-hr-data.md) humanos le permite importar datos relacionados con cambios en el nivel de trabajo, revisiones de rendimiento y planes de mejora del rendimiento. A continuación, estos datos se pueden usar en varias directivas de [riesgo interno](insider-risk-management-policies.md) para detectar actividad relacionada.

### <a name="retention-labels-new-support-for-email"></a>Etiquetas de retención: nueva compatibilidad con el correo electrónico

Ahora puede crear una etiqueta [de retención para](retention.md#retention-labels) empezar a conservar el correo electrónico en función de cuándo se etiquetaron los mensajes. Esto no se aplica a los elementos de calendario, que se conservarán en función de cuándo se envíe el elemento.

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>Etiquetas de confidencialidad: nueva característica y una mejora

- (En versión preliminar) Al configurar las opciones de cifrado para una [](encryption-sensitivity-labels.md#double-key-encryption) etiqueta, busque la nueva opción para usar cifrado de doble clave para proteger aún más los archivos y mensajes de correo electrónico etiquetados.
- Al crear o eliminar etiquetas de confidencialidad o crear, editar o eliminar sus directivas de etiquetas, los cambios ahora se sincronizan en un plazo de 1 hora para todos los usuarios, aplicaciones y servicios.

## <a name="june-2020"></a>Junio de 2020

### <a name="spotlight-new-data-connectors-hit-preview"></a>Foco de luz: vista previa de nuevos conectores de datos

A partir de nuestra promesa de ayudarle a importar datos de más orígenes de terceros a Microsoft 365, nos complace anunciar la versión preliminar de dos conectores de datos más:

- [Mensaje de Bloomberg](archive-bloomberg-message-data.md). Importar y archivar datos de correo electrónico de servicios financieros desde la herramienta de colaboración de mensajes de Bloomberg. Después de almacenar los datos en buzones, puede acceder a los datos y usarlos en características de cumplimiento, como retención por juicio, búsqueda de contenido, archivado local, auditoría, cumplimiento de comunicaciones y directivas de retención.
- [ICE Chat](archive-icechat-data.md). Importar y archivar datos de chat de servicios financieros desde la herramienta de colaboración de chat ICE. Después de almacenar los datos en buzones, puede acceder a los datos y usarlos en características de cumplimiento, como retención por juicio, exhibición de documentos electrónicos, archivado, auditoría, cumplimiento de comunicaciones y directivas de retención.

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>Puntuación de cumplimiento & Administrador de cumplimiento: los aciertos siguen a la baja

Las actualizaciones de junio incluyen una nueva vista de evaluación en profundidad en la [puntuación de cumplimiento.](compliance-score.md) Supervisar el progreso del control, agregar, eliminar evaluaciones directamente de la puntuación de cumplimiento y mucho más.

¿Desea mantenerse al tanto de las actualizaciones de la puntuación de cumplimiento y el Administrador de cumplimiento? Marque las notas [de la versión de puntuación de cumplimiento](compliance-score-release-notes.md) y vuelva a comprobarlo con frecuencia.

## <a name="may-2020"></a>Mayo de 2020

### <a name="spotlight-data-classification-is-officially-released"></a>Foco de luz: la clasificación de datos se ha publicado oficialmente

La clasificación de datos, también conocido como["Conocer](data-classification-overview.md)los datos", las características (análisis, explorador de contenido y explorador de actividades) han pasado de la fase de vista previa y están disponibles para todas las organizaciones. La información y las herramientas eficaces pueden ayudarle a descubrir y evaluar cómo se usan la información y las etiquetas confidenciales (retención y confidencialidad) en el contenido de toda la organización. Revisar el contenido que contiene información confidencial o que tiene etiquetas aplicadas, explorar la actividad de etiquetas en las ubicaciones de Microsoft 365, crear tipos personalizados de información confidencial y mucho más.

Realizar un paseo en vídeo...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>Clasificadores que se pueden entrenar: una corrección y una característica

Puede dar más mejoras a los clasificadores que se pueden entrenar:

- Una corrección basada en sus comentarios: cuando se edificó y entrenó un clasificador personalizado, ya no es necesario escribir manualmente las direcciones URL del sitio de SharePoint y las rutas de acceso a carpetas. Ahora puede elegir entre una lista de sitios y carpetas rellenada previamente.
- Nueva característica: al crear una etiqueta de confidencialidad y configurar las opciones de etiquetado automático para las aplicaciones de Office, ahora puede aplicar automáticamente (o recomendar que los usuarios apliquen) la etiqueta al contenido que coincida con clasificadores que se pueden entrenar. [Más información](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>Cumplimiento de comunicaciones: el soporte técnico de Yammer está aquí

Los mensajes privados y las conversaciones de la comunidad pública en Yammer son compatibles con las directivas de cumplimiento de comunicaciones. Yammer es un canal opcional y debe estar en modo [nativo para](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) admitir el examen de mensajes y datos adjuntos.

### <a name="data-loss-prevention-new-sharing-restriction"></a>Prevención de pérdida de datos: nueva restricción de uso compartido

Al configurar una directiva DLP para proteger el contenido en SharePoint o OneDrive, ahora puede configurar la acción "Restringir el acceso al contenido" para bloquear a las personas a las que se les ha concedido acceso al contenido a través de la opción["Cualquiera](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)con el vínculo".

### <a name="insider-risk-management-tailor-your-alert-volume"></a>Administración de riesgos de Insider: adaptar el volumen de alertas

A las actividades de usuario detectadas por las directivas de riesgo internas se les asigna una puntuación de riesgo específica, que a su vez determina la gravedad de la alerta (baja, media, alta). De forma predeterminada, Microsoft 365 genera una cierta cantidad de alertas de gravedad baja, media y alta, pero con la nueva configuración del volumen de [alertas,](insider-risk-management-settings.md#alert-volume)puede aumentar o disminuir el volumen para adaptarlo a sus necesidades.

### <a name="pst-import-new-region-supported"></a>Importación de PST: nueva región compatible

La carga en la red ya está disponible en Emiratos Árabes Unidos.

### <a name="sensitivity-labels-new-privacy-option"></a>Etiquetas de confidencialidad: nueva opción de privacidad

Al configurar las [opciones de sitio](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) y grupo para una etiqueta, ahora puede establecer la opción de privacidad en Ninguno: permitir al usuario elegir quién puede acceder al **sitio.** Esto resulta útil cuando se desea proteger el contenido del contenedor mediante una etiqueta de confidencialidad, pero se permite a los usuarios configurar la configuración de privacidad por sí mismos.

## <a name="april-2020"></a>Abril de 2020

### <a name="records-management-overhauland-a-new-addition"></a>Administración de registros: revisión... y una nueva adición

April incluye un par de actualizaciones clave para nuestra solución de administración de registros:

- La sección "Administración de registros" ahora está totalmente disponible en el centro de cumplimiento. Aproveche las interfaces de usuario y la funcionalidad actualizadas para el plan de archivos, etiquetas de retención y directivas de etiquetas, eventos y eliminación.
- Hablando de eliminación, también hemos lanzado la prueba de [eliminación](disposition.md#disposition-of-records) de registros en SharePoint y OneDrive. Ahora puede ver una lista de elementos en esas ubicaciones que se han eliminado automáticamente o después de una revisión de eliminación.

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>Etiquetas de confidencialidad: vista previa de las directivas de etiquetado automático

Con las directivas de etiquetado automático, ahora puede aplicar automáticamente etiquetas de confidencialidad a los documentos de SharePoint y OneDrive que ya están guardados (también conocido como "datos en reposo) y a los correos electrónicos que ya se han enviado o recibido (también conocido como "correo electrónico en tránsito"). Dado que este etiquetado lo aplican los servicios en lugar de las aplicaciones, no es necesario preocuparte por qué aplicaciones tienen los usuarios y qué versión.

Esta funcionalidad amplía el etiquetado del lado cliente existente que ya se incluye en la configuración de "Etiquetado automático para aplicaciones de Office" al crear una etiqueta de confidencialidad. Para estar al día de las diferencias y ventajas de ambas opciones de etiquetado automático, consulte el [artículo actualizado.](apply-sensitivity-label-automatically.md)

## <a name="march-2020"></a>Marzo de 2020

### <a name="introducing-advanced-audit"></a>Introducción a la auditoría avanzada

[La auditoría avanzada de Microsoft 365](advanced-audit.md) presenta nuevas capacidades de auditoría que pueden ayudar a su organización con investigaciones forenses y de cumplimiento. Entre los aspectos destacados se incluyen la retención a largo plazo de los registros de auditoría, las directivas de retención de registros de auditoría personalizadas, la nueva acción de auditoría del buzón *MailItemsAccessed* y la introducción de un nuevo límite de nivel de inquilino, que proporciona a su organización su propia cuota de ancho de banda totalmente asignada para acceder a los datos de auditoría.

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>Puntuación de cumplimiento & Administrador de cumplimiento: obtener una vista previa de las mejoras más recientes

Entre las actualizaciones clave de esta versión preliminar se incluyen:

- Proceso simplificado para crear y modificar plantillas
- Control y aviso de control de versiones para plantillas y acciones
- Sincronización de acciones comunes entre grupos
- La compatibilidad con idiomas ahora se extiende a chino (simplificado), chino (tradicional), francés, alemán, italiano, japonés, coreano, portugués (Brasil), ruso y español

Obtenga más información sobre [la puntuación de cumplimiento](compliance-score.md) y el Administrador de [cumplimiento](compliance-manager-overview.md)

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>Etiquetas de confidencialidad: compatibilidad para etiquetar archivos de Office en SharePoint y OneDrive (versión preliminar)

Habilitar la vista previa permite a los usuarios aplicar etiquetas de confidencialidad en Office en la Web. Podrán ver el botón  Confidencialidad en la cinta de opciones y el nombre de la etiqueta aplicada en la barra de estado. Además, si usan aplicaciones de escritorio para etiquetar y guardar sus archivos en SharePoint o OneDrive, Microsoft 365 ahora podrá procesar el contenido de estos archivos si la etiqueta tiene aplicada la configuración de cifrado. La coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda y otras características de colaboración también serán compatibles en estas circunstancias.

[Obtenga información sobre cómo habilitar la vista previa](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>Febrero de 2020

### <a name="insider-risk-management-is-officially-released"></a>Se ha publicado oficialmente la administración de riesgos de Insider

Rollitos de batería, por favor...<br>La administración de riesgos de Insider ahora está disponible para las organizaciones con las siguientes suscripciones:

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (de pago o de prueba)
- Suscripción de Microsoft 365 Enterprise E3 con el complemento de cumplimiento [de Microsoft E5](https://go.microsoft.com/fwlink/?linkid=2120432)

Por lo tanto, hemos realizado algunas mejoras desde la versión preliminar, incluidos los nuevos [grupos de roles](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) y la configuración de toda la [solución.](insider-risk-management-configure.md#step-4-configure-insider-risk-settings)

Como siempre, deje comentarios mientras usa la solución para que podamos seguir haciendo mejoras.

### <a name="records-management"></a>Administración de registros

Esta nueva solución ofrece todas las capacidades de administración de registros bajo un único paraguas. Entre los aspectos más destacados se incluyen la introducción del control de versiones de registros para SharePoint y OneDrive y la prueba de eliminación de registros.

![Página de administración de registros en el Centro de cumplimiento de Microsoft 365](../media/mcc-records-management-page.png)

[Obtenga más información sobre la administración de registros](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>Foco de luz de la solución: conectores de datos para Facebook y Twitter

Conectores de [datos publicados el](#just-launched) mes pasado y estamos buscando su ayuda para probar los siguientes conectores.

- [Páginas empresariales de Facebook](archive-facebook-data-with-sample-connector.md). Importa y archiva datos de páginas empresariales de Facebook a Microsoft 365. Es útil para soluciones de cumplimiento, como la administración de registros y la exhibición de documentos electrónicos.
- [Twitter](archive-twitter-data-with-sample-connector.md). Importa y archiva datos de Twitter a Microsoft 365. Es útil para soluciones de cumplimiento, como la administración de registros y la exhibición de documentos electrónicos.

Al configurar y validar estos conectores, déjenos comentarios sobre lo que salió bien, lo que no y lo que podemos hacer para mejorar la experiencia.

## <a name="january-2020"></a>Enero de 2020

La espera ha terminado. Nos complace anunciar que el Centro de cumplimiento de Microsoft 365 está disponible para todos los clientes con planes de Microsoft 365, Office 365, Enterprise Mobility + Security (EMS) y Windows 10 Enterprise. Los datos o directivas que estaba administrando en el Centro de seguridad y cumplimiento de & están disponibles en el centro de cumplimiento, por lo que no es necesario saltar de un lado a otro.

Marque y diríjase ahora a su tienda de un solo [https://compliance.microsoft.com](https://compliance.microsoft.com) uso para administrar el cumplimiento normativo en toda la organización... o [lea este artículo](microsoft-365-compliance-center.md) para profundizar un poco más.

![Página principal del Centro de cumplimiento de Microsoft 365](../media/mcc-home-ga.png)

También hemos publicado soluciones nuevas y actualizadas este mes. Este es un vistazo rápido a los puntos destacados.

### <a name="now-in-preview"></a>Ahora en versión preliminar

**Administración de riesgos de Insider (versión preliminar)**

Nos complace anunciar que nuestra solución de administración de riesgos de Insider está ahora en versión preliminar pública. En pocas palabras, la administración de riesgos de Insider ayuda a tu organización a identificar y tomar medidas de forma inteligente en los riesgos de insider proporcionando:

- Controles de anonimización para ayudar a garantizar la privacidad del usuario.
- Plantillas de directivas inteligentes con indicadores nativos y de terceros que identifican amenazas internas, como pérdidas de datos.
- Flujos de trabajo integrados de investigación de un extremo a otro que se extienden a través de equipos legales, de RRHH y de IT.

Nos encantaría escuchar lo que piensa. A medida que use la solución, déjenos comentarios para que podamos asegurarnos de que estamos a la medida que nos dirigemos hacia la disponibilidad general.

[Más información sobre la administración de riesgos interno](insider-risk-management.md)

### <a name="just-launched"></a>Just launched

**Cumplimiento de las comunicaciones**

Desde la fase de vista previa hasta la disponibilidad completa, el cumplimiento de las comunicaciones es un componente clave de nuestro nuevo conjunto de soluciones de riesgo interno. Esta solución sólida ayuda a minimizar los riesgos de comunicación mediante flujos de trabajo para detectar, investigar y tomar medidas correctivas para mensajes que no cumplen los estándares de su organización.

Los comentarios de los clientes durante la vista previa fueron fantásticos. Se han realizado varias mejoras, como una experiencia de primera ejecución para empezar, mejoras en las acciones de investigación y corrección, etc.

[Más información sobre el cumplimiento de las comunicaciones](communication-compliance.md)

![Página de cumplimiento de comunicaciones en el Centro de cumplimiento de Microsoft 365 que muestra la primera tarjeta de la experiencia de bienvenida](../media/mcc-communication-compliance-page-with-fre.png)

**Conectores de datos**

Anteriormente, al compartir espacio con otras características de "importación" en el Centro de seguridad y cumplimiento de Office 36 & 5, los conectores de datos ahora tienen su propia casa en el Centro de cumplimiento de Microsoft 365. Use la nueva página "Conectores de datos" para importar y archivar datos de los archivos de recursos humanos (RRHH) de su organización y diversas plataformas de terceros (como Facebook, LinkedIn, Twitter e Instant Bloomberg) a los buzones de la organización de Microsoft 365. Una vez importados, estos datos se pueden administrar en varias soluciones de cumplimiento, como eDiscovery, administración de riesgos de Insider, cumplimiento de comunicaciones, auditoría, directivas de retención y mucho más.

[Más información sobre conectores de datos](archiving-third-party-data.md)

![Página conectores de datos en el Centro de cumplimiento de Microsoft 365](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>Actualizaciones notables

**Nuevas plantillas de evaluación para la puntuación de cumplimiento (versión preliminar)**

Siempre trabajando para ayudarle a avanzar por el panorama de cumplimiento en constante evolución, nuestro equipo de puntuación de cumplimiento envió un nuevo conjunto de plantillas para ayudarle a evaluar la posición de cumplimiento de su organización frente a normativas recientes y obtener instrucciones sobre cómo implementar controles más eficaces. Verá nuevas plantillas para:

- ISO/IEC 27701:2019
- Ley de privacidad del consumidor de California (CCPA)
- Ley general de protección de datos de Brasil (Lei Geral dePrimção de Dados - LGPD)
- SOC 1 Type 2 y SOC 2 Type 2

[Más información sobre las plantillas de puntuación de cumplimiento](compliance-score.md#templates)