---
title: Novedades de Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: crimora
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, consulte lo que se ha agregado, cambiado y corregido en Microsoft 365 Lighthouse cada mes.
ms.openlocfilehash: 2c63cd304fc8893c5a767212ef540939e9954793
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68735075"
---
# <a name="whats-new-in-microsoft-365-lighthouse"></a>Novedades de Microsoft 365 Lighthouse

Estamos agregando continuamente nuevas características a [Microsoft 365 Lighthouse](m365-lighthouse-overview.md), solucionando problemas que aprendemos y realizando cambios en función de sus comentarios. Revise este artículo para descubrir en qué hemos estado trabajando.

> [!NOTE]
> Algunas características se implantan a diferentes velocidades para nuestros clientes. Si aún no ve una característica, debería verla pronto.

## <a name="september-2022"></a>Septiembre de 2022

### <a name="fully-automated-setup-of-microsoft-defender-for-business"></a>Configuración totalmente automatizada de Microsoft Defender para Empresas

Hemos agregado un paso totalmente automatizado a la línea base predeterminada que le ayuda a configurar los inquilinos del cliente con Microsoft Defender para Empresas. Este paso aprovisiona automáticamente el inquilino para Microsoft Defender para Empresas e incorpora automáticamente dispositivos inscritos Intune a Microsoft Defender para Empresas.

### <a name="capability-to-filter-the-multifactor-authentication-mfa-list-to-show-relevant-user-accounts"></a>Funcionalidad para filtrar la lista de autenticación multifactor (MFA) para mostrar las cuentas de usuario pertinentes

La página Autenticación multifactor ahora admite el filtrado de la lista de cuentas de usuario por tipo de cuenta (por ejemplo, por Administración, miembro o invitado). También puede excluir otras cuentas de la lista, como cuentas de servicio o cuentas de acceso de emergencia. Para acceder a esta funcionalidad, vaya a Autenticación **multifactor** **de usuarios** > , seleccione un inquilino de la lista para abrir el panel de detalles del inquilino y, a continuación, seleccione la pestaña **Usuarios no registrados para MFA**. Estas funcionalidades de filtrado y exclusión le ayudan a centrarse en las cuentas de usuario pertinentes. 

### <a name="capability-to-act-on-security-incidents-and-alerts"></a>Funcionalidad para actuar sobre incidentes de seguridad y alertas

Ahora puede actuar sobre los incidentes y alertas que se muestran en la página **Incidentes y alertas** de **seguridad** >  del dispositivo. Las acciones admitidas actualmente incluyen la asignación del incidente o la alerta a usted mismo o la resolución del incidente o la alerta. 

## <a name="august-2022"></a>Agosto de 2022

### <a name="view-and-manage-inactive-user-accounts"></a>Visualización y administración de cuentas de usuario inactivas 

Microsoft 365 Lighthouse ahora proporciona una lista de todas las cuentas de usuario inactivas de los inquilinos administrados. Para acceder a la lista, seleccione **Usuarios** > **inactivos en** el panel de navegación izquierdo de Microsoft 365 Lighthouse. Puede reducir los riesgos de seguridad mediante esta lista para realizar un seguimiento y limpiar las cuentas que todavía están habilitadas, pero que no se han usado en los últimos seis meses. 

### <a name="microsoft-edge-policy-deployment"></a>Implementación de directivas de Microsoft Edge   

Hemos agregado una tarea de implementación de directivas de Microsoft Edge a la línea base predeterminada. Esta tarea de implementación le permite proteger los exploradores del inquilino del cliente con la configuración de seguridad de Edge, que incluye protección integrada contra phishing y malware. Microsoft Edge ha demostrado ser más seguro que Google Chromium para pequeñas y medianas empresas con dispositivos que ejecutan Windows 10 o posterior.

Para obtener más información, consulte [Seguridad de Microsoft Edge para su empresa](/deployedge/ms-edge-security-for-business).

## <a name="july-2022"></a>Julio de 2022

### <a name="enhanced-baseline-deployment"></a>Implementación de línea base mejorada

Microsoft 365 Lighthouse ahora hace que la implementación de líneas base en todos los inquilinos administrados sea más rápida y fácil:

- Detectar e informar automáticamente del estado de cada tarea asignada
- Consolidación de los informes de estado y simplificación de la lógica que determina el estado de implementación
- Informar de qué tareas están completas y qué tareas necesitan su atención
- Notificación del estado de implementación de nivel de usuario para las tareas aplicables
- Detección de configuraciones existentes desde el inquilino y comparación con la línea base
- Proporcionar detalles sobre las tareas que se han descartado
- Identificación de dónde se requieren licencias adicionales para completar una tarea asignada

## <a name="june-2022"></a>Junio de 2022

### <a name="support-for-microsoft-365-e5-customers"></a>Soporte técnico para clientes Microsoft 365 E5

Hemos cambiado nuestros requisitos de incorporación para permitirle incorporar Microsoft 365 E5 clientes a Microsoft 365 Lighthouse. La lista ampliada de licencias que Microsoft 365 Lighthouse admite para la incorporación incluye Microsoft 365 Empresa Premium, Microsoft 365 E3, Microsoft 365 E5, Microsoft Defender para Empresas y Windows 365 para empresas. Los clientes que tengan al menos una de estas licencias, cumplan los requisitos de permisos de acceso delegado y no superen el número máximo de usuarios con licencia se pueden administrar en Microsoft 365 Lighthouse.  

Para obtener una lista completa de los requisitos, consulte [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

### <a name="microsoft-defender-for-business-integration"></a>integración Microsoft Defender para Empresas

Microsoft 365 Lighthouse ahora se integra con Microsoft Defender para Empresas para proporcionarle información relacionada y funcionalidades de administración para todos los inquilinos de clientes que tienen Microsoft Defender para Empresas. Para ver la lista de dispositivos de cliente que se han incorporado a Microsoft Defender para Empresas, seleccione **Dispositivos** en el panel de navegación izquierdo de Microsoft 365 Lighthouse. Para ver la lista de incidentes y alertas marcados en los inquilinos de los clientes, vaya a **Seguridad de** **dispositivos** >  y, a continuación, seleccione la pestaña **Incidentes y alertas**.  

También hemos agregado un paso a la línea base predeterminada para ayudarle a configurar Microsoft Defender para Empresas para los inquilinos del cliente. Para ver este paso, seleccione **Líneas base** en el panel de navegación izquierdo de Microsoft 365 Lighthouse o vea el plan de implementación para cualquiera de los inquilinos del cliente.

### <a name="status-of-quarantined-email-messages"></a>Estado de los mensajes de correo electrónico en cuarentena

Hemos agregado una nueva funcionalidad en torno a los datos de cuarentena de correo electrónico para los inquilinos administrados. Accesible mediante la selección de **Protección de datos** en el panel de navegación izquierdo de Microsoft 365 Lighthouse, esta característica proporciona visibilidad sobre el estado de los mensajes de correo electrónico en cuarentena en los inquilinos del cliente. Puede ver información consolidada de los volúmenes de cuarentena totales e información detallada de cada inquilino administrado para ayudarle a priorizar los inquilinos que puedan requerir acción.

### <a name="increase-in-maximum-license-limit"></a>Aumento del límite máximo de licencias

Estamos haciendo posible administrar más clientes en Microsoft 365 Lighthouse al aumentar de nuevo el límite máximo de licencias para la incorporación de clientes. Los clientes con hasta 2500 licencias de usuario ahora se pueden incorporar a Microsoft 365 Lighthouse. Seguiremos evaluando este requisito en futuras versiones de Microsoft 365 Lighthouse. 

Para obtener más información, vea [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

## <a name="may-2022"></a>Mayo de 2022

### <a name="redesigned-left-navigation-pane"></a>Panel de navegación izquierdo rediseñado

Hemos dado el panel de navegación izquierdo en Microsoft 365 Lighthouse un nuevo aspecto. Observará un diseño más elegante, con nodos de nivel superior como inquilinos, usuarios y dispositivos que se expanden para mostrar subnodos relacionados, como usuarios de riesgo, cumplimiento de dispositivos y administración de amenazas. Este modelo de navegación se alinea con el modelo usado por otros centros de administración de Microsoft 365.

### <a name="enriched-user-details-pane"></a>Panel de detalles del usuario enriquecido

Hemos rediseñado el panel de detalles del usuario para incluir más información del usuario y más acciones que puede realizar para administrar mejor a los usuarios. Ahora tiene el mismo aspecto que el panel de detalles del usuario en el Centro de administración de Microsoft 365. Para acceder al panel de detalles del usuario en Microsoft 365 Lighthouse, seleccione **Usuarios** en el panel de navegación izquierdo y, a continuación, seleccione **Buscar usuarios** o **Usuarios de riesgo**. Seleccione cualquier usuario para abrir el panel de detalles.

## <a name="april-2022"></a>Abril de 2022

### <a name="delegated-access-type-and-roles-on-tenants-page"></a>Tipo de acceso delegado y roles en la página Inquilinos

Hemos actualizado la página Inquilinos para mostrar el tipo de acceso delegado del proveedor de servicios **administrados** (MSP) (None, DAP, GDAP o Ambos DAP & GDAP) por cliente en la columna **Acceso delegado** . También hemos agregado una nueva columna titulada **Sus roles** que enumera los roles DAP y GDAP por cliente para un usuario que ha iniciado sesión. Estas dos mejoras en la página **Inquilinos** facilitarán a los técnicos de MSP comprender qué tipos de permisos administrativos delegados están disponibles para cada cliente y qué roles delegados se les han concedido explícitamente.

Para más información, consulte [Introducción a los permisos en Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md).

## <a name="march-2022"></a>Marzo de 2022

### <a name="windows-365-business-integration-and-management-actions"></a>Windows 365 Business acciones de integración y administración

En función de los comentarios de los usuarios, hemos integrado Windows 365 Business en Microsoft 365 Lighthouse. Esta integración le ayudará a administrar y supervisar todos los equipos en la nube de sus clientes desde una sola ubicación. 

Además de la integración con Windows 365 Business pc en la nube en Microsoft 365 Lighthouse, ahora puede realizar las siguientes acciones de administración:

- Restart
- Reprovision
- Cambiar nombre
 
Para más información sobre las nuevas características, consulte [Información general de la página Windows 365 (PC en la nube) en Microsoft 365 Lighthouse](m365-lighthouse-win365-page-overview.md).

### <a name="microsoft-365-lighthouse-partner-amendment"></a>Microsoft 365 Lighthouse enmienda de asociados

Ahora que Microsoft 365 Lighthouse está en disponibilidad general, necesitamos que nuestros asociados actuales firmen una modificación actualizada Microsoft 365 Lighthouse partner. A todos los Microsoft 365 Lighthouse asociados que se registraron durante el período de versión preliminar se les pedirá que completen este nuevo contrato en las próximas semanas. La finalización requerirá derechos de administrador global en el inquilino del asociado y debe completarse en un plazo de 90 días para seguir accediendo al portal de Microsoft 365 Lighthouse.

## <a name="february-2022"></a>Febrero de 2022

### <a name="granular-delegated-access-permissions-gdap-roles"></a>Roles de permisos de acceso delegado pormenorizados (GDAP)

Microsoft 365 Lighthouse ahora incluye la funcionalidad para que los CSP usen roles de privilegios de Administración delegados granulares (GDAP). Con la actualización más reciente, los MSP pueden aprovechar los roles de GDAP para sus técnicos que habilitan el principio de acceso con privilegios mínimos en Microsoft 365 Lighthouse. Esta funcionalidad reduce los riesgos inherentes a los amplios permisos del rol Permisos de acceso delegado (DAP) del agente de Administración habilitando controles pormenorizados sobre los datos y la configuración de los clientes con los que cada técnico podrá trabajar.

Para más información sobre GDAP en Microsoft 365 Lighthouse, consulte [Configuración de la seguridad del portal de Microsoft 365 Lighthouse](m365-lighthouse-configure-portal-security.md).

### <a name="capability-to-notify-users-to-act-on-noncompliant-devices"></a>Funcionalidad para notificar a los usuarios que actúen en dispositivos no compatibles

Como parte del paso de línea base de cumplimiento de dispositivos, hemos agregado la capacidad de notificar a los usuarios de un inquilino de cliente que actúen en dispositivos no conformes. Con este cambio, una vez que aplique el paso de implementación de cumplimiento de dispositivos para cualquier inquilino de cliente, la directiva de cumplimiento de dispositivos creada en ese inquilino enviará automáticamente una notificación a los usuarios cuando su dispositivo no sea conforme recordándoles que realicen las acciones adecuadas para que el dispositivo vuelva a cumplirse.

### <a name="deployment-validation-and-reporting"></a>Validación de la implementación e informes

Microsoft 365 Lighthouse ahora puede probar las configuraciones de inquilino para los pasos de implementación con directivas de acceso condicional.  

Esta nueva funcionalidad detecta las directivas existentes dentro de los inquilinos del cliente que administra y las compara con el plan de implementación. Microsoft 365 Lighthouse, a continuación, proporciona designaciones de estado para los pasos de implementación y los procesos de paso de implementación para ayudarle a comprender qué procesos de implementación ya se han completado, cuáles deben abordarse y dónde la configuración prescrita por el plan de implementación es igual, falta o entra en conflicto con la configuración incluida en las directivas existentes. Conocer esta información hace que la identificación, priorización y resolución de conflictos de directivas sea más rápida, fácil y eficaz.

### <a name="deployment-step-to-configure-microsoft-defender-firewall"></a>Paso de implementación para configurar Microsoft Defender Firewall

Microsoft 365 Lighthouse ha agregado el paso Configurar la implementación de firewall de Microsoft Defender a su línea base predeterminada. Este paso ayuda a los MSP a proteger los dispositivos de inquilino del cliente a través de la configuración de firewall predeterminada para dispositivos Windows 10 (y versiones posteriores). Microsoft Defender Firewall bloquea el tráfico de red no autorizado que entra o sale de los dispositivos de inquilino del cliente y reduce el riesgo de amenazas de seguridad de red. Actualmente se está desarrollando una característica de reglas de firewall de Microsoft Defender.

Microsoft Defender Firewall está activado de forma predeterminada en Windows 10 (y versiones posteriores). Si el inquilino del cliente no tiene esto configurado, siga estos pasos:

1. En la página **Inquilinos** de Microsoft 365 Lighthouse, seleccione el inquilino del cliente para abrir la página **Información general** del inquilino.
2. Seleccione la pestaña **Plan de implementación** .
3. En la lista de pasos de implementación, seleccione **Configurar Microsoft Defender firewall**.
4. Seleccione **Revisar e implementar** para implementar esta configuración en el inquilino del cliente. 

### <a name="increase-in-maximum-license-limit"></a>Aumento del límite máximo de licencias

Estamos haciendo posible administrar más clientes en Microsoft 365 Lighthouse mediante el aumento del límite máximo de licencias para la incorporación de clientes. Los clientes con hasta 1000 licencias de usuario ahora se pueden incorporar a Microsoft 365 Lighthouse. Seguiremos evaluando este requisito en futuras versiones de Microsoft 365 Lighthouse.

Para obtener más información, vea [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

### <a name="support-for-advisor-customers"></a>Soporte técnico para clientes de Advisor

Hemos cambiado los requisitos de incorporación para permitir que los inquilinos de clientes existentes con relaciones de advisor se incorporen a Microsoft 365 Lighthouse. Los clientes con contratos de revendedor y asesor ahora pueden estar en Microsoft 365 Lighthouse si cumplen los requisitos de permisos de acceso delegado, tienen las licencias necesarias y no superan el número máximo de usuarios.

Para obtener más información, vea [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

## <a name="january-2022"></a>Enero de 2022

### <a name="capability-to-view-audit-logs-in-microsoft-365-lighthouse"></a>Funcionalidad para ver los registros de auditoría en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse ahora incluye la capacidad de ver los registros de auditoría. Puede revisar las acciones anteriores para encontrar configuraciones incorrectas y acciones de riesgo para la corrección, el proceso de soporte técnico y la investigación de seguridad, entrenar a los empleados y cumplir los requisitos de cumplimiento y auditoría. Con la actualización más reciente, puede hacer lo siguiente:

- Vea los registros de auditoría para ver todas las acciones realizadas dentro de Microsoft 365 Lighthouse, incluido lo que cambió en qué inquilino del cliente, cuándo se cambió y quién lo cambió.
- Busque y filtre los registros de auditoría para encontrar información específica.
- Exporte los registros para que pueda analizarlos y conservarlos.
 
En el panel de navegación izquierdo de Microsoft 365 Lighthouse, seleccione **Registros de auditoría**. O [bien, vaya directamente a la página Registros de auditoría ahora](https://lighthouse.microsoft.com/#blade/Microsoft_Intune_MTM/Audit.ReactView) para comprobarlo.

## <a name="november-2021"></a>Noviembre de 2021

### <a name="microsoft-365-services-usage-data"></a>Datos de uso de servicios de Microsoft 365

Ahora puede ver los datos de uso de los servicios de Microsoft 365 desde dentro de Microsoft 365 Lighthouse. Comprender cómo los clientes usan sus servicios de Microsoft 365 es fundamental para ayudarles a sacar el máximo partido a sus inversiones en TI. En lugar de usar varios recursos para ver información en los distintos servicios de productividad, seguridad y cumplimiento de los clientes, Microsoft 365 Lighthouse los agrega en una vista sencilla y eficaz.  

Esta información puede ayudar a informar a los clientes y ofrecer más valor a los clientes, ya que le permite ayudarles a comprender qué servicios usan activamente sus usuarios y dónde pueden haber oportunidades para mejorar su seguridad o productividad. 

Para obtener más información, vea [Información general de la página Inquilinos de Microsoft 365 Lighthouse: Uso de servicios de Microsoft 365](m365-lighthouse-tenants-page-overview.md#microsoft-365-services-usage-section).

### <a name="exchange-online-protection-and-microsoft-365-defender-for-office-365-default-baseline-step"></a>Exchange Online Protection y Microsoft 365 Defender para Office 365 paso de línea base predeterminado

Hemos agregado un nuevo paso a la línea base predeterminada para incluir instrucciones para habilitar directivas de seguridad para Exchange Online Protection (EOP) y Microsoft Defender para Office 365 (MDO). EOP y MDO ayudan a proteger a los usuarios contra correo no deseado, phishing y correos electrónicos de malware mediante el envío de los correos electrónicos a la carpeta de correo no deseado o cuarentena del usuario (próximamente). El plan de implementación le guía en la configuración de EOP y MDO, ampliando aún más su posición de seguridad durante la siguiente revisión del plan de implementación de inquilinos del cliente.

### <a name="default-tenant-tags"></a>Etiquetas de inquilino predeterminadas

Ahora puede designar determinadas etiquetas de inquilino de *forma predeterminada* en el panel **Administrar etiquetas** de la página **Inquilinos**, por lo que la próxima vez que inicie sesión en Microsoft 365 Lighthouse, todas las vistas y la información se filtrarán de forma predeterminada para mostrar solo los inquilinos que tienen una etiqueta predeterminada. Las etiquetas predeterminadas pueden ayudarle a centrarse en la información de los inquilinos de clientes de prioridad alta.

## <a name="october-2021"></a>Octubre de 2021

### <a name="capability-to-filter-by-multiple-tenant-tags"></a>Funcionalidad para filtrar por varias etiquetas de inquilino

Ahora es posible filtrar los datos por varias etiquetas de inquilino al mismo tiempo. Esta funcionalidad puede ayudarle a filtrar más fácilmente las vistas e información existentes que están disponibles en Microsoft 365 Lighthouse para mostrar los inquilinos de clientes pertinentes.

### <a name="capability-to-assign-baseline-configurations-to-specific-azure-active-directory-groups"></a>Funcionalidad para asignar configuraciones de línea base a grupos específicos de Azure Active Directory

Hemos agregado la capacidad de asignar configuraciones de línea base a grupos específicos de Azure Active Directory (Azure AD) de los inquilinos del cliente desde dentro de Microsoft 365 Lighthouse. En cualquier página de paso de implementación, examine y seleccione los grupos de Azure AD específicos que desea incluir o excluir y, a continuación, implemente las configuraciones en el inquilino del cliente.

### <a name="improvements-to-risky-users-page"></a>Página Mejoras en usuarios de riesgo

Ahora puede ver y comprender fácilmente los motivos del riesgo de un usuario desde dentro de Microsoft 365 Lighthouse. En el panel de navegación izquierdo de Microsoft 365 Lighthouse, seleccione **Usuarios** y, a continuación, seleccione la pestaña **Usuarios de riesgo**. Seleccione **Ver detecciones de riesgo** en la columna **Detalles** para cualquier usuario. Desde aquí, puede revisar los detalles del riesgo y, a continuación, seleccionar **Confirmar usuario en peligro** o **Descartar riesgo de usuario**. También puede confirmar o descartar un riesgo para varios usuarios al mismo tiempo desde la página **Usuarios de riesgo** . La capacidad de descartar el riesgo de un usuario puede ser útil cuando el restablecimiento de contraseña no es una opción o si cree que el usuario afectado ya no está en riesgo.

### <a name="capability-to-provide-feedback-on-microsoft-365-lighthouse"></a>Funcionalidad para proporcionar comentarios sobre Microsoft 365 Lighthouse

Sus comentarios son importantes y son importantes para nosotros, por lo que hemos agregado una nueva funcionalidad de comentarios que en ocasiones (no más de una vez al mes) le pedirá que proporcione comentarios. También puede proporcionar comentarios en cualquier momento seleccionando el icono de comentarios en la esquina superior derecha de Microsoft 365 Lighthouse.

## <a name="september-2021"></a>Septiembre de 2021

### <a name="tenant-filter-changes"></a>Cambios en el filtro de inquilinos

Hemos realizado algunos cambios en la experiencia de filtrado de inquilinos para ayudarle a ver y administrar rápidamente inquilinos y etiquetas desde cualquier página dentro de Microsoft 365 Lighthouse. Seleccione el filtro **Inquilinos** en la parte superior de cualquier página y, a continuación, examine o escriba el nombre de inquilino o etiqueta por el que desea filtrar.

## <a name="august-2021"></a>Agosto de 2021

### <a name="in-product-email-workflows-to-communicate-with-users"></a>Flujos de trabajo de correo electrónico del producto para comunicarse con los usuarios 

Hemos facilitado la comunicación con los usuarios de los inquilinos del cliente sobre las acciones que deben realizar. En la lista de usuarios no registrados para la autenticación multifactor (MFA) o el autoservicio de restablecimiento de contraseña, ahora puede seleccionar uno o más usuarios y enviarles un mensaje de correo electrónico mediante una plantilla de correo electrónico descargable.

### <a name="capability-to-take-action-on-noncompliant-devices"></a>Funcionalidad para realizar acciones en dispositivos no compatibles

Hemos introducido la funcionalidad para sincronizar o reiniciar uno o varios dispositivos en varios inquilinos de clientes. Esta funcionalidad ayuda a garantizar que los dispositivos de los clientes estén protegidos contra riesgos. Para comprobar esta funcionalidad, seleccione **Dispositivos** en el panel de navegación izquierdo de Microsoft 365 Lighthouse y, a continuación, seleccione la pestaña **Dispositivos**. Busque las opciones **Sincronizar** y **reiniciar** situadas encima de la lista de dispositivos. También puede acceder a estas opciones desde el panel de detalles del dispositivo de cualquier dispositivo.

### <a name="capability-to-monitor-and-manage-windows-365-cloud-pcs"></a>Funcionalidad para supervisar y administrar equipos en la nube Windows 365

Hemos agregado la capacidad de supervisar las conexiones locales y aprovisionar y administrar Windows 365 equipos en la nube en todos los inquilinos del cliente. La nueva página **Windows 365** proporciona información detallada sobre todos los equipos en la nube de los inquilinos en una ubicación cómoda. 

### <a name="support-for-microsoft-365-e3-customers"></a>Soporte técnico para clientes Microsoft 365 E3

Hemos cambiado nuestros requisitos de incorporación para permitirle incorporar Microsoft 365 E3 clientes a Microsoft 365 Lighthouse. Para poder administrarse en Microsoft 365 Lighthouse, cada cliente debe cumplir los siguientes requisitos:

- Debe tener el acceso delegado configurado para que el MSP pueda administrar el inquilino del cliente.
- Debe tener al menos una licencia de Microsoft 365 Empresa Premium o Microsoft 365 E3
- No debe tener más de 500 usuarios con licencia

Para obtener más información sobre los requisitos, vea [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

## <a name="june-2021"></a>Junio de 2021

### <a name="capability-to-add-custom-tags-to-customer-tenants"></a>Funcionalidad para agregar etiquetas personalizadas a inquilinos de clientes

Ahora puede crear y aplicar etiquetas personalizadas a los inquilinos del cliente que administra en Microsoft 365 Lighthouse. Use estas etiquetas para ayudarle a organizar los inquilinos o úselos para filtrar más fácilmente la lista de inquilinos para mostrar información sobre los conjuntos pertinentes de inquilinos de clientes. 

### <a name="baselines-to-standardize-your-customer-tenant-deployments"></a>Líneas base para estandarizar las implementaciones de inquilinos del cliente

Con la nueva característica de líneas base, ahora puede implementar configuraciones estándar para ayudar a proteger a los usuarios, dispositivos y datos en los inquilinos del cliente. La línea base predeterminada contiene actualmente los siguientes pasos de implementación (con más información próximamente): 

- Requerir MFA para administradores 
- Requerir MFA para los usuarios 
- Bloquear autenticación heredada 
- Inscripción de dispositivos Windows en Microsoft Endpoint Manager: unión a Azure AD 
- Configuración de la directiva de Antivirus de Defender para dispositivos Windows 
- Configuración de la directiva de cumplimiento para dispositivos Windows 

Para actuar sobre estos pasos de implementación, seleccione **Inquilinos** en el panel de navegación izquierdo del faro de Microsoft 365, seleccione un inquilino en la lista de inquilinos y, a continuación, seleccione la pestaña **Plan de implementación** . 

## <a name="may-2021"></a>Mayo de 2021

### <a name="enhancements-to-tenants-page"></a>Página Mejoras en los inquilinos

Hemos realizado las siguientes mejoras en la página **Inquilinos** :

- Se ha agregado una lista de recuentos totales por problema a la parte superior de la página. 
- Se ha proporcionado la capacidad de mantener el puntero sobre un estado en la columna **Estado** de la lista de inquilinos para ver los detalles de la restricción. 
- Se han mejorado las etiquetas de estado