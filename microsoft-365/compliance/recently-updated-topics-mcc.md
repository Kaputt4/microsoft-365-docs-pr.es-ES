---
title: Actualizaciones recientes en el centro de cumplimiento
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 03/22/2020
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- m365-security-compliance
description: Al igual que con las características del centro de cumplimiento de Microsoft 365, el contenido de ayuda está evolucionando siempre. Descubra las novedades y las actualizaciones de este mes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3bba8d0bbd68c6d28d72bcf32abdc798d7125250
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818970"
---
# <a name="recent-updates-to-microsoft-365-compliance-content"></a>Actualizaciones recientes del contenido de cumplimiento de Microsoft 365

Al igual que con las características del centro de cumplimiento de Microsoft 365, el contenido de ayuda está evolucionando siempre. Estamos creando artículos nuevos, actualizando los existentes y realizando cambios en función de sus comentarios. Eche un vistazo al siguiente para ver las novedades y las actualizaciones de este mes.

> [!TIP]
> Para estar al tanto de las últimas actualizaciones de características en el centro de cumplimiento de Microsoft 365, consulte [what's New in the microsoft 365 Compliance Center](whats-new.md).

## <a name="march-2020"></a>Marzo de 2020

### <a name="auditing"></a>Auditoría

[Usar la auditoría avanzada para investigar cuentas comprometidas](mailitemsaccessed-forensics-investigations.md) (nuevo)<br>Nuevas instrucciones sobre el uso de la nueva acción de auditoría del buzón de *MailItemsAccessed* para investigaciones forenses.

[Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md) (actualizado)<br>Los cambios incluyen:
- [Sección nueva](search-the-audit-log-in-security-and-compliance.md#the-appsharepoint-user-in-audit-records) con detalles sobre el usuario "App@sharepoint" que aparece en registros de auditoría.
- [Nuevas descripciones](search-the-audit-log-in-security-and-compliance.md#quarantine-activities) de las actividades en cuarentena.
- En la sección [actividad de administración de usuarios](search-the-audit-log-in-security-and-compliance.md#user-administration-activities) , se aclara que el evento de cambio de contraseña de usuario que se desencadena cuando un usuario cambia su contraseña (a través del restablecimiento de contraseña de autoservicio) se desencadena cuando un administrador restablece la contraseña de un usuario.

### <a name="auto-expanding-archive"></a>Archivo de expansión automática

[Información general sobre el archivado ilimitado](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive) (actualizado)<br>Se agregó una aclaración de que no se puede eliminar ninguna carpeta del archivo principal o de un archivo auxiliar una vez que el archivado de expansión automática está habilitado en un buzón.

### <a name="compliance-scorecompliance-manager"></a>Puntuación de cumplimiento/administrador de cumplimiento

Todos los temas de [puntuación de cumplimiento](compliance-score.md) y de [Administrador de cumplimiento](compliance-manager-overview.md) reflejan las actualizaciones de estos productos publicados a principios de abril (ambos aún están en versión preliminar pública). Las actualizaciones clave incluyen:
- Proceso simplificado para crear y modificar plantillas
- Aviso y control de versiones para plantillas y acciones
- Sincronización de acciones comunes entre grupos
- Compatibilidad con idiomas ahora extendida a chino (simplificado), Chino (tradicional), Francés, alemán, Italiano, Japonés, Coreano, Portugués (Brasil), Ruso y español

### <a name="communication-compliance"></a>Cumplimiento de las comunicaciones

[Caso práctico-contoso configura rápidamente una directiva de idioma ofensivo para Microsoft Teams, Exchange y Yammer Communications](communication-compliance-case-study.md) (nuevo)<br>Un caso práctico paso a paso para las organizaciones educativas y de pequeñas empresas para ayudarles a configurar rápidamente una directiva de lenguaje ofensivo. Se incrementaron las solicitudes de los clientes a medida que las organizaciones aumentan las respuestas COVID19.

[Introducción al cumplimiento de la comunicación](communication-compliance-configure.md) (actualizado)<br>Requisitos de licencia y permisos actualizados.

### <a name="customer-key"></a>Clave de cliente

[Desplazamiento o rotación de una clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md) (actualizada)<br>Actualizaciones de la organización que ayudan a aclarar qué teclas puede y qué no puede hacer.

[Obtener información sobre la clave de disponibilidad para la clave de cliente](customer-key-availability-key-understand.md) (actualizada)<br>Se agregó una aclaración alrededor de la arquitectura de Exchange Online para la clave de cliente.

### <a name="data-loss-prevention"></a>Prevención de pérdida de datos

[Introducción a la prevención de pérdida de datos](data-loss-prevention-policies.md) (actualizada)<br>Se actualizó el tiempo necesario para que las etiquetas de retención surtan efecto y las directivas de comportamiento predeterminado sin alertas configuradas.

### <a name="ediscovery"></a>eDiscovery

[Introducción a la exhibición avanzada de](get-started-with-advanced-ediscovery.md) documentos electrónicos (nueva)<br>Proporciona información sobre los requisitos de licencia y permisos, los pasos para establecer la configuración global y crear un nuevo caso y un tutorial del flujo de trabajo de eDiscovery avanzado.

[Jubilación de las herramientas de eDiscovery heredadas](legacy-ediscovery-retirement.md) (actualizadas)<br>Las fechas de jubilación se movieron tres meses debido a la situación de salud pública. El artículo actualizado se ha puesto de los nuevos plazos de jubilación.

### <a name="insider-risk-management"></a>Administración de riesgos de Insider

[Introducción a la administración de riesgos de Insider](insider-risk-management-configure.md) (actualizado)<br>Requisitos de licencia y permisos actualizados.

[Definir directivas de barrera de información](information-barriers-policies.md) (actualizadas)<br>Se ha aclarado la velocidad de procesamiento y el tiempo necesarios para aplicar. Se agregaron detalles sobre la forma en que no debe haber directivas de libreta de direcciones. También varias actualizaciones de código de PowerShell, incluido el nuevo código para el filtrado.

[Barreras](information-barriers.md) de la información (actualizada)<br>Se han corregido algunos vínculos rotos y se han actualizado los vínculos y el título de PDF. Por los comentarios de los clientes, clarificado que las barreras de información solo admiten restricciones bidireccionales. Las restricciones en un solo sentido (como marketing pueden comunicarse con los comerciantes de día, pero el día no puede comunicarse con el marketing) no es compatible.

[Solución de problemas de barreras](information-barriers-troubleshooting.md) de la información (actualizada)<br>Se agregó la sección nuevo escenario de solución de problemas. Se agregó un vínculo a los pasos para volver a aplicar las barreras de la información.

### <a name="office-365-message-encryption"></a>Cifrado de mensajes de Office 365

[Administración del cifrado de mensajes de Office 365](manage-office-365-message-encryption.md) (actualizado)<br>Se actualiza para reflejar que la función forzar contenedor es una característica estándar OME, no una avanzada. Rescribió los ejemplos de PowerShell para excluir todas las referencias a las características avanzadas de revocación y expiración de OME.

[Preguntas más frecuentes sobre el cifrado de mensajes](ome-faq.md) (actualizada)<br>Se aclara que solo Outlook para la web puede aplicar el cifrado ad hoc. Del mismo modo, para todos los clientes de Outlook, los mensajes y los datos adjuntos de PDF no protegidos heredan la protección OME de la Directiva de prevención de pérdida de datos (DLP) o de la regla de flujo de correo en Exchange Online.

### <a name="privileged-access-management"></a>Administración del acceso con privilegios

[Introducción a la administración de acceso privilegiada](privileged-access-management-configuration.md) (actualizada)<br>Requisitos de licencia y permisos actualizados.

### <a name="pst-import"></a>Importación de PST

[Preguntas más frecuentes sobre la importación de archivos PST](faqimporting-pst-files-to-office-365.md) (actualizado)<br>Se agregaron preguntas más frecuentes sobre cómo procesa el proceso de importación de PST elementos de correo electrónico duplicados.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

[Obtener información sobre las etiquetas de confidencialidad](sensitivity-labels.md) (actualizada)<br>Se agregaron detalles de desuso sobre la administración de etiquetas en el portal de Azure, lo que incluye un vínculo al [aviso oficial](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179).

[Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) (actualizada)<br>Se ha agregado información sobre la nueva función lector de etiquetas de confidencialidad, que solo se admite en un primer momento para los cmdlets de PowerShell de etiqueta.

[Creación y configuración de las etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md#removing-and-deleting-labels) (actualizada)<br>Nueva sección agregada explica las consecuencias de quitar y eliminar etiquetas.

[Usar las etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, los grupos de microsoft 365 y los sitios de SharePoint (versión preliminar pública)](sensitivity-labels-teams-groups-sites.md) (actualización)<br>Los cambios incluyen:

- Se quitaron las instrucciones de Azure AD y en su lugar se vinculó a la [información autoritativa de Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).
- Se actualizó la sección [Cómo configurar las opciones de configuración de sitio y grupo cuando se crea o edita una etiqueta de confidencialidad](sensitivity-labels-teams-groups-sites.md#how-to-configure-site-and-group-settings-when-you-create-or-edit-sensitivity-labels) con información sobre la **privacidad de la configuración de sitios de Microsoft Teams conectados a grupos de Office 365** , que incluye la nueva opción **ninguno** .
- Se agregó una nota que describe cómo solo estarán disponibles las etiquetas con la configuración de sitio y grupo cuando los usuarios creen equipos, grupos y sitios. Esta funcionalidad se implementa gradualmente para las organizaciones.

[Restringir el acceso al contenido mediante las etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md) (actualizado)<br>[Nueva sección](encryption-sensitivity-labels.md#example-configurations-for-the-encryption-settings) con opciones de cifrado de ejemplo para algunas de las configuraciones más utilizadas para proteger documentos y mensajes de correo electrónico.

[Aplicar una etiqueta de confidencialidad a contenido automáticamente](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps) (actualizado)<br>Explicación de las diferencias de comportamiento entre las etiquetas integradas y el cliente de etiquetado Unificado de Azure Information Protection.

[Habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) (actualizado)<br>Los cambios incluyen:

- Clarificado que la habilitación de esta vista previa muestra el botón de **confidencialidad** en la cinta de las etiquetas de Office para la web, además de admitir documentos etiquetados y cifrados.
- Se actualizaron las instrucciones para Office 365 multi-geo.
- La lista de limitaciones tiene nuevas entradas que incluyen lo que sucede cuando un equipo se desconecta o se suspende, y si se elimina una etiqueta.

[Usar las etiquetas de confidencialidad en las aplicaciones de Office](sensitivity-labels-office-apps.md) (actualizada)<br>Los cambios incluyen:

- Se movió la información de licencias a para empezar a [trabajar con las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md).
- [Sección nueva](sensitivity-labels-office-apps.md#labeling-client-for-desktop-apps) que explica cómo usar etiquetas integradas en las aplicaciones de escritorio de Office, debe usar una edición de suscripción de Office en lugar de ediciones independientes.
- Las tablas de aplicaciones compatibles incluyen la aplicación de Office para iOS y Android y la configuración que permite a los usuarios asignar permisos para Word, Excel y PowerPoint que se actualizan, ya que se implementan en un canal mensual para Windows y Mac.  
- [Nueva sección](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-other-labeling-solutions) en la que se explica cómo se puede usar la configuración de directiva de grupo para deshabilitar las etiquetas integradas si actualmente usa otras soluciones de etiquetado que desea seguir usando para los equipos Windows. 
- Se actualizó la sección de [Opciones de Information Rights Management (IRM) y las etiquetas de confidencialidad](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels) con la recomendación de usar etiquetas que aplican el cifrado en lugar de las opciones de IRM, con una explicación de las posibles consecuencias cuando se mezclan las dos soluciones de protección.

### <a name="trainable-classifiers"></a>Clasificadores capacitados

[Introducción a los clasificadores capacitados (versión preliminar)](classifier-getting-started-with.md) (actualización)<br>Se ha agregado información sobre cómo la plantilla de lenguaje ofensivo está en desuso. También se ha agregado una tabla que enumera los 25 principales idiomas utilizados en el clasificador de código fuente integrado.

## <a name="february-2020"></a>Febrero de 2020

> [!NOTE]
> Los artículos que aparecen en los meses anteriores pueden haber sido actualizados, movidos o eliminados. Como resultado, algunos de los siguientes detalles podrían estar anticuados y los vínculos podrían romperse.

### <a name="auditing"></a>Auditoría

[Auditoría avanzada en Microsoft 365](advanced-audit.md) (nueva)<br>Disponible para organizaciones con una suscripción a Office 365 E5 o Microsoft 365 Enterprise E5, la auditoría avanzada amplía las capacidades de auditoría existentes mediante la introducción de características como períodos de retención largos para registros de auditoría, nuevas directivas de retención de registro de auditoría y una nueva acción de auditoría de buzones de correo que realiza el seguimiento de las lecturas de correo.

[Administración de directivas de retención de registro de auditoría](audit-log-retention-policies.md) (nueva)<br>Detalles sobre la administración de directivas de retención de registro de auditoría, la nueva característica de auditoría avanzada que permite guardar registros de auditoría de diferentes servicios durante un máximo de un año.

[Administrar la auditoría de buzones de correo](enable-mailbox-auditing.md#logon-types-and-mailbox-actions) (actualizado)<br>Se agregó información sobre la nueva acción de buzón de MailItemsAccessed, que se introdujo con la auditoría avanzada.

[Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) (actualizado)<br>Se agregaron nuevas descripciones para actividades de etiqueta de confidencialidad e información adicional acerca de [las actividades de colaboración de formularios](search-the-audit-log-in-security-and-compliance.md#forms-activities-performed-by-co-authors-and-anonymous-responders)de auditoría.

### <a name="compliance-offerings"></a>Ofertas de cumplimiento

[Marco de garantía de ENISA Information](offering-enisa.md) (nueva)<br>Nuevo tema sobre el marco de seguridad de la información de la Agencia Europea de seguridad de la información (ENISA) (IAF).

[Controles de la organización de servicios (SOC)](offering-SOC.md) (actualizadas)<br>Se agregaron nuevas referencias de auditoría.

[Autoridad del Reglamento prudencial australiano (APRA)](offering-APRA-Australia.md) (actualizado)<br>Contenido alineado para nuevos estándares normativos.

### <a name="customer-key"></a>Clave de cliente

[Cifrado de servicio con clave de cliente](customer-key-overview.md) (nueva)<br>Artículo nuevo que presenta la clave de cliente y conceptos relacionados, como BitLocker y el cifrado de servicio, y cómo funcionan conjuntamente.

[Administrar la clave de cliente](customer-key-manage.md) (nueva)<br>Instrucciones posteriores a la configuración para administrar la clave de cliente, incluidos los pasos para la administración de los permisos de DEPs y de la bóveda de claves, los tiempos estimados para completar las operaciones, cómo comprobar que el cifrado funcionó y cómo salir del servicio.

[Rollo o rotación de una clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md) (nueva)<br>Describe cómo deshacer las claves administradas por el cliente para la clave de cliente.

[Obtener información sobre la clave de disponibilidad para la clave de cliente](customer-key-availability-key-understand.md) (nueva)<br>Cobertura detallada sobre la clave de disponibilidad: Cuándo y cómo se usa para recuperarse de la pérdida de claves, donde existe en la jerarquía de clave de cliente, y más.

[Configurar la clave de cliente para Microsoft 365](customer-key-set-up.md) (actualizado)<br>Titulado anteriormente "controlar los datos en Microsoft 365 mediante la clave de cliente", este artículo se centra únicamente en cómo configurar la clave de cliente para Office 365, incluidas las instrucciones actualizadas.

### <a name="data-classification"></a>Clasificación de los datos

[Notas de la versión preliminar pública de clasificación de datos (versión preliminar)](data-classification-pub-preview-relnotes.md) (nueva)<br>Notas de la versión para la versión preliminar pública que presenta nuevas funciones en las que se inicia el análisis del contenido confidencial y etiquetado antes de crear directivas. Esto le permite revisar la forma en que las etiquetas de confidencialidad y retención existentes afectan a su organización para ayudarle a evaluar las necesidades de protección y gobernanza de la Directiva.

### <a name="gdpr"></a>RGPD

[Solicitudes del interesado de Office 365 para RGPD y CCPA](gdpr-dsr-Office365.md) (actualizado)<br>Se quitaron las referencias a Microsoft StaffHub debido a [la retirada de la aplicación](https://docs.microsoft.com/microsoftteams/expand-teams-across-your-org/shifts/microsoft-staffhub-to-be-retired).

Se agregaron referencias del administrador de cumplimiento y vínculos actualizados para la puntuación de cumplimiento en los artículos siguientes.<br>
[Resumen del Reglamento de protección general de datos](gdpr.md) (artículo también incluye nuevas preguntas más frecuentes del centro de confianza).<br>
[Plan de acción de RGPD de Microsoft 365: principales prioridades de los primeros 30 días, 90 días y el periodo posterior](gdpr-action-plan.md)<br>
[Apoye a su programa de RGPD con las listas de comprobación de preparación de responsabilidad](gdpr-arc.md)<br>
[Lista de comprobación de preparación de responsabilidad de Azure para RGPD](gdpr-arc-Azure.md)<br>
[Lista de comprobación de preparación de responsabilidad de Dynamics 365 para RGPD](gdpr-arc-Dynamics365.md)<br>
[Lista de comprobación de preparación de responsabilidad para Microsoft Office 365](gdpr-arc-Office365.md)<br>

### <a name="insider-risk-management"></a>Administración de riesgos internos

Se actualizaron los siguientes artículos para apoyar la versión oficial de la administración de riesgos de Insiders.<br>
[Obtenga información sobre la administración de riesgos de Insider en Microsoft 365](insider-risk-management.md)<br>
[Introducción a la administración de riesgos internos](insider-risk-management-configure.md)<br>
[Crear y administrar directivas de riesgos internos](insider-risk-management-policies.md)<br>
[Investigar alertas de riesgos internos](insider-risk-management-alerts.md)<br>
[Tomar medidas en casos de riesgos internos](insider-risk-management-cases.md)<br>
[Revisar datos con el explorador de contenido de riesgos internos](insider-risk-management-content-explorer.md)<br>
[Agregar usuarios a las directivas de riesgos internos](insider-risk-management-users.md)<br>
[Crear avisos de riesgos de Insider](insider-risk-management-notices.md)<br>

### <a name="records-management"></a>Administración de registros

[Información general sobre las etiquetas de retención](labels.md) (actualizada)<br>La sección para aplicar una etiqueta de retención basada en condiciones ahora incluye la opción de usar clasificadores que se pueden entrenar.

### <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

[Introducción a las etiquetas de confidencialidad](get-started-with-sensitivity-labels.md) (nueva)<br>Incluye orientación para clientes de Azure Information Protection, información general de alto nivel del proceso y pasos para implementar etiquetas de confidencialidad, permisos para crear y administrar las etiquetas, una lista de escenarios comunes que admiten etiquetas y una lista de documentación de usuario final disponible.

[Obtener información sobre las etiquetas de confidencialidad](sensitivity-labels.md) (actualizada)<br>Cambiar el título de "información general sobre las etiquetas de confidencialidad" y movió la información de la sección "introducción" al nuevo artículo Introducción a las [etiquetas de confidencialidad](get-started-with-sensitivity-labels.md).

[Creación y configuración de las etiquetas de confidencialidad y sus directivas](create-sensitivity-labels.md) (actualizada)<br>Se movieron los detalles del permiso al nuevo artículo, introducción a las [etiquetas de confidencialidad](get-started-with-sensitivity-labels.md).

[Restringir el acceso al contenido mediante las etiquetas de confidencialidad para aplicar el cifrado](encryption-sensitivity-labels.md) (actualizado)<br>Las nuevas opciones de "ninguno" y "quitar" reemplazan el cambio de cifrado y "agregar cualquier usuario autenticado" se agrega como un nuevo permiso para asignar ahora. La sección para permitir que los usuarios asignen permisos se actualizó ahora que pedir a los usuarios que seleccionen permisos personalizados en Word, PowerPoint y Excel se están implementando en versión preliminar para Windows y Mac. Sección nueva para obtener configuraciones de ejemplo sobre cómo configurar las opciones de cifrado para que admitan casos de uso específicos. Nueva sección que enumera las consideraciones para cifrar contenido.

[Aplicar una etiqueta de confidencialidad a contenido automáticamente](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps) (actualizado)<br>La sección para configurar las etiquetas automáticas para las aplicaciones de Office ahora incluye la nueva opción para usar clasificadores cocapacitados.

[Usar las etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, los grupos de microsoft 365 y los sitios de SharePoint (versión preliminar pública)](sensitivity-labels-teams-groups-sites.md) (actualización)<br>Revisiones en una mejor experiencia de lectura y aclaraciones técnicas. Además, por comentarios de los clientes, se agregaron vínculos al [artículo de Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels) para habilitar la vista previa y aplicar etiquetas de confidencialidad a los grupos de Microsoft 365 en el portal de Azure. Por último, se agregó una sección nueva para auditar actividades de etiqueta de confidencialidad.

[Habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (Public Preview)](sensitivity-labels-sharepoint-onedrive-files.md) (actualizado)<br>Varias actualizaciones incluyen aclaraciones por los comentarios de los clientes sobre cómo funciona esta característica, haciendo hincapié en que las nuevas funciones solo se aplican a los archivos nuevos y modificados, y una nueva limitación que puede que vea durante una fase de pruebas si elimina etiquetas.

[Usar las etiquetas de confidencialidad en las aplicaciones de Office](sensitivity-labels-office-apps.md) (actualizada)<br>Se actualizaron las tablas de funciones para permitir a los usuarios asignar permisos y aplicar una etiqueta al contenido automáticamente. Además, por los comentarios de los clientes, se agregó una excepción para los datos adjuntos de correo electrónico que heredan una etiqueta.

### <a name="service-descriptions"></a>Descripciones de servicio

[Guía de licencias de Microsoft 365 para el cumplimiento de & de seguridad](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) (actualizado)<br>Cambie el título de "Guía de licencias de servicios a nivel de inquilino de Microsoft 365" para reflejar mejor el contenido.

