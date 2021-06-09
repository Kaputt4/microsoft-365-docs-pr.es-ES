---
title: Actividades previas a la migración de Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Summary: Pre-work when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.'
ms.openlocfilehash: db4563b4a63dc39ee8171e80fd76ae15b7cd10e9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844291"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Actividades previas a la migración de Microsoft Cloud Deutschland

Use estos vínculos para obtener acceso a los pasos previos a la migración relevantes para su organización.

Si está usando

- **Office 365 en Microsoft Cloud Deutschland**, siga [estos pasos](#general-tenant-migration-considerations).
- **Dominios personalizados**, realice [este paso](#dns-entries-for-custom-domains).
- **Office Apps**, tenga en cuenta [este paso](#office-apps).
- **SharePoint Online**, realice [este paso](#sharepoint-online).
- **Exchange Online** o **Exchange hybrid**, realice [este paso](#exchange-online).
- **Skype Empresarial Online**, realice [este paso](#skype-for-business-online).
- **Dynamics 365**, realice [este paso](#dynamics365).
- **Power BI**, realice [este paso](#power-bi).
- **Servicios de federación de Active Directory** para Azure AD Conectar, siga estos [pasos.](#active-directory-federation-services-ad-fs)
- **Servicios de terceros** o aplicaciones de línea de negocio **(LOB)** que están integradas con Office 365, realice [este paso](#line-of-business-apps).
- Una solución de administración de dispositivos móviles (MDM) de terceros, realice [este paso](#mobile-device-management).
- **Servicios de Azure** con su Office 365 suscripción, realice [este paso](#microsoft-azure).

## <a name="general-tenant-migration-considerations"></a>Consideraciones generales de migración de inquilinos

**Se aplica a:** Todos los clientes que usan Office 365 en la instancia de Microsoft Deutschland Cloud

Office 365 los identificadores de inquilino e usuario se conservan durante la migración. Las llamadas de servicio de Azure AD se redirigen desde Microsoft Cloud Deutschland a Office 365 servicios globales y son transparentes para Office 365 servicios.

- Las solicitudes de interesados (DSR) del Reglamento general de protección de datos (RGPD) se ejecutan desde el portal de administración de Azure para futuras solicitudes. Los datos de diagnóstico heredados o que no son del cliente que residen en Microsoft Cloud Deutschland se eliminan en o antes de que transcurren 30 días.
- Las solicitudes de autenticación multifactor (MFA) que usan Microsoft Authenticator se muestran como objectid de usuario (GUID) mientras el espacio empresarial se copia en Office 365 servicios. Las solicitudes MFA se realizarán según lo esperado a pesar de este comportamiento de presentación.  Microsoft Authenticator cuentas que se activaron mediante el uso de Office 365 de servicios mostrarán el nombre principal de usuario (UPN).  Las cuentas agregadas mediante puntos de conexión de Microsoft Cloud Deutschland mostrarán el ObjectID del usuario, pero funcionarán con puntos de conexión de Microsoft Cloud Deutschland y Office 365 de servicios.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Prepárese para notificar a los usuarios sobre el reinicio y el inicio de sesión en y fuera de sus clientes después de la migración. | Office las licencias de cliente pasarán de Microsoft Cloud Deutschland a Office 365 servicios en la migración. Los clientes recogen una nueva licencia válida después de iniciar sesión en Office clientes. | Los productos Office usuarios necesitan actualizar las licencias de Office 365 servicios. Si las licencias no se actualizan, los Office pueden experimentar errores de validación de licencias. |
| Garantizar la conectividad de [red a Office 365 direcciones IP y direcciones IP de los servicios.](https://aka.ms/o365urls) | Todos los clientes y servicios hospedados por el cliente que se usan para obtener acceso Office 365 servicio deben poder tener acceso a los puntos de conexión Office 365 servicios globales. <br>En caso de que usted o sus asociados de colaboración tengan reglas de firewall que impidan el acceso a las direcciones URL y direcciones IP enumeradas en las direcciones URL de servicios de Office 365 y las direcciones IP deben cambiar las reglas de firewall para permitir el acceso [a](https://aka.ms/o365urls) los extremos de servicio global de Office 365| Pueden producirse errores en el servicio o el software cliente si no se realiza antes de la fase 4  |
| Cancelar cualquier suscripción de prueba. | Las suscripciones de prueba no se migrarán y bloquearán la transferencia de suscripciones de pago. | Los servicios de prueba expiran y no funcionan si los usuarios acceden después de la cancelación. |
| Analice las diferencias en las características de licencia entre Microsoft Cloud Deutschland y Office 365 Global Services. | Office 365 incluyen características y servicios adicionales que no están disponibles en el Microsoft Cloud Deutschland actual. Durante la transferencia de suscripción, las nuevas características estarán disponibles para los usuarios. | <ul><li> Analice las distintas características proporcionadas por las licencias de Microsoft Cloud Deutschland y Office 365 Global Services. Comience con la [descripción Office 365 de servicio de la plataforma.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Determine si las nuevas características de Office 365 servicios deben deshabilitarse inicialmente para limitar los efectos en los usuarios o en la administración de cambios de usuario, y modificar las asignaciones de licencias de usuario según sea necesario. </li><li>Prepare a los usuarios y al personal de servicio de atención al cliente para los nuevos servicios y características proporcionados por Office 365 servicios. |
| Cree directivas de retención en toda [la](/microsoft-365/compliance/retention) organización para protegerse de la eliminación involuntaria de contenido durante la migración.  |<ul><li>Para asegurarse de que los usuarios finales no eliminan accidentalmente el contenido durante la migración, los clientes pueden optar por habilitar una directiva de retención en toda la organización. </li><li>Aunque la retención no es necesaria, dado que las retenciones realizadas en cualquier momento durante la migración deben funcionar según lo esperado, tener una directiva de retención es un mecanismo de seguridad de copia de seguridad. Al mismo tiempo, es posible que todos los clientes no utilicen una directiva de retención, especialmente aquellos que están preocupados por la conservación.</li></ul>| Aplicar la directiva de retención tal como se describe [en Obtenga información sobre las directivas de retención y las etiquetas de retención.](/microsoft-365/compliance/retention-policies) Los errores del servicio o del software cliente pueden producirse si esto no se realiza antes de la fase 4 de 9. </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>Entradas DNS para dominios personalizados

<!-- before phase 9 -->

**Se aplica a**: Clientes que establecen un CNAME _msoid_ personalizado en su propio dominio DNS o que usan un dominio para Exchange Online

Si se configura, _el Msoid_ CNAME solo afecta a los clientes que usan un cliente de escritorio de Office (Aplicaciones Microsoft 365, Office 365 ProPlus, Office 2019, 2016, ...).

En caso de que haya establecido un CNAME DNS denominado _msoid_ en uno o varios espacios de nombres DNS de su propiedad, debe quitar el CNAME hasta el final de la fase 8 como máximo. Puede quitar el _msoid_ CNAME en cualquier momento antes del final de la fase 8.

Para comprobar si ha establecido un CNAME en el espacio de nombres DNS, siga los pasos siguientes y reemplace _contoso.com_ por su propio nombre de dominio:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Si la línea de comandos devuelve un registro DNS, quite _el Msoid_ CNAME del dominio.

> [!NOTE]
> Si usa un dominio personalizado para Exchange Online, tendrá que tener acceso a su proveedor de hospedaje DNS. Asegúrese de que puede tener acceso a la configuración de DNS y modificarla, ya que modificará los registros DNS durante la migración.

## <a name="office-apps"></a>Office Aplicaciones

**Se aplica a**: Clientes que usan Office aplicaciones, especialmente en Windows cliente <br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 9

Office 365 los inquilinos que se encuentran en la región "Alemania" requieren que todos los usuarios cierren, cierren sesión desde Office 365 y vuelvan a iniciar sesión para todas las aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, etc.) y un cliente OneDrive para la Empresa después de que la migración del espacio empresarial haya alcanzado la fase 9. Al iniciar sesión, permite a los Office obtener nuevos tokens de autenticación del servicio global de Azure AD.

Esto es necesario para todos los clientes. Para garantizar una experiencia de migración sin problemas, se recomienda informar e informar a todos los usuarios afectados con antelación y en una fase temprana sobre esta próxima actividad.

Los clientes con Windows administrados pueden preparar Windows máquinas con Office Herramienta de recorte de cliente [(OCCT).](https://github.com/microsoft/OCCT) La OCCT está diseñada para ejecutarse periódicamente en Windows clientes hasta que el inquilino alcanzó la fase 9 de la migración. Cuando se haya alcanzado la fase 9, la OCCT realizará todos los cambios necesarios en el equipo automáticamente sin la interacción del usuario.

La OCCT se puede implementar en Windows clientes en cualquier momento antes de la fase 9. Si la OCCT admite la experiencia de migración, se recomienda iniciar la implementación lo antes posible para equipar un número máximo de clientes.

## <a name="active-directory-federation-services-ad-fs"></a>Servicios de federación de Active Directory (ADFS)

**Se aplica a**: Los clientes que usan AD FS localmente para autenticar a los usuarios que se conectan a Microsoft Office 365<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 2

Leer y aplicar los pasos [de migración de ADFS](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

**Se aplica a**: Clientes que usan SharePoint 2013 local<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 4

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Limite SharePoint flujos de trabajo de 2013, úsenlo durante la SharePoint en línea. | Reduzca SharePoint flujos de trabajo de 2013 y complete los flujos de trabajo en el vuelo antes de las transiciones. | La inacción puede provocar confusión del usuario y llamadas al servicio de ayuda. |
||||

## <a name="exchange-online"></a>Exchange en línea

<!-- before phase 5 -->

**Se aplica a**: Exchange Online clientes<br>
**Cuando se aplica:** cualquier momento antes del final de la fase 9

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Notifique a los asociados externos de la próxima transición a Office 365 servicios. |  Los clientes deben notificar a sus partners con los que han habilitado la configuración de espacio de direcciones de disponibilidad y calendario compartido (permitir el uso compartido de información de disponibilidad con Office 365). La configuración de disponibilidad debe realizar la transición para usar los [Office 365 de conexión en](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) todo el mundo cuando se Exchange Online migración. | Si no lo hace, puede producirse un error en el servicio o el cliente en una fase posterior de la migración de clientes. |
| Notificar a los usuarios los cambios necesarios en el cliente IMAP4/POP3/SMTP. | Los usuarios que tienen conexiones de dispositivo a puntos de conexión de Microsoft Cloud Deutschland para protocolos de cliente IMAP4, POP3, SMTP deben actualizar manualmente sus dispositivos cliente para cambiar a los nombres de servidor [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes). | Comunique previamente esta dependencia a los usuarios de estos protocolos y asegúrese de que cambien a usar Outlook móvil o Outlook en la web durante esta migración. Si no se actualizan los puntos de conexión de cliente, se producirán errores de conexión de cliente en Microsoft Cloud Deutschland cuando se migren los buzones de usuario. |
||||

### <a name="exchange-online-hybrid-customers"></a>Exchange Online Clientes híbridos

**Se aplica a:** Todos los clientes que usan una configuración Exchange híbrida activa con Exchange servidores locales<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 5

Enterprise clientes con una implementación híbrida de Exchange Online y un Exchange Server local ejecuten el Asistente para configuración híbrida (HCW) y AAD Conectar para mantener y establecer la configuración híbrida.
Exchange Online Los administradores híbridos deben ejecutar el Asistente para configuración híbrida **(HCW) varias veces** como parte de esta transición.
Al realizar la transición de Microsoft Cloud Deutschland a la región de Office 365 Alemania, el administrador debe volver a ejecutar la última compilación de HCW en modo "Office 365 Alemania" antes de que comience la migración de Exchange (fase 5). A continuación, vuelva a ejecutar el HCW en modo "Office 365 Worldwide" al finalizar la fase 5 para finalizar la implementación local con la configuración de la región de Office 365 Alemania. La ejecución de HCW no debe ejecutarse durante la fase 5, es importante ejecutar el HCW no hasta que finalice la fase 5.
Los atributos de directorio se sincronizan entre Office 365 y Azure AD con la implementación local a través de AAD Conectar.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Volver a ejecutar HCW con Office 365 configuración de Alemania <br><br> <i>Puede iniciar esta actividad inmediatamente después de recibir la notificación del centro de mensajes de que su Office 365 de inquilino ha comenzado (fase 1).</i>| Desinstalar y volver a ejecutar HCW (17.0.5378.0 o posterior) desde antes de la fase 5 garantizará que la configuración local esté preparada para enviar y recibir correo con usuarios y usuarios de Microsoft Cloud Deutschland que se migran Office 365 la región de [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Alemania. <p><li> En hcw, para el cuadro de lista debajo de **Mi Office 365 organización** está hospedado por , seleccione Office 365 **Alemania.** | Si no se completa esta tarea antes de que comience la fase 5 [migración Exchange] puede resultar en NDR para el correo enrutado entre la implementación Exchange local y Office 365.
| Conservación de la configuración de buzones compartidos | Algunos clientes híbridos han convertido buzones de usuario en la nube para que sean buzones "compartidos" mediante Exchange Online comandos. Esta configuración de buzón de correo en la nube se escribe en el buzón y en el directorio Exchange Online local, sin embargo, no se sincroniza de nuevo con Active Directory del cliente a través de AAD Conectar. El resultado es una discrepancia entre la representación de Active Directory de los valores RemoteRecipientType y RemoteDisplayType de buzones de correo y Exchange Online el buzón como compartido. <br><br> El cliente es responsable de asegurarse de que todos los buzones compartidos se aprovisionan correctamente mediante `New-RemoteMailbox -Shared` , `Enable-RemoteMailbox -Shared` o `Set-RemoteMailbox -Shared` .  Vea esta referencia para obtener información sobre cómo convertir el buzón de un usuario [en un entorno híbrido.](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide)| Si no se completa esta tarea antes de la fase 5 [migración Exchange Online], los NDR para buzones compartidos pueden volver a convertirse en buzones sin licencia y la pérdida de acceso compartido para los buzones afectados. [Los buzones](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) compartidos se convierten inesperadamente en buzones de usuario después de que la sincronización de directorios se ejecute en una implementación híbrida de Exchange indica el impacto de no abordar esto antes de que Exchange Online se complete la migración.
||||

## <a name="skype-for-business-online"></a>Skype Empresarial Online

<!-- before phase 7 -->

**Se aplica a**: Skype para clientes de Business Online<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 7

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Implemente Teams cliente de escritorio para usuarios que tienen acceso Skype Empresarial en Alemania. | La migración mueve Skype Empresarial usuarios a Microsoft Teams para colaboración, llamadas y chat. Implemente el cliente Microsoft Teams de escritorio o asegúrese de que hay disponible un explorador compatible. | La inacción dará lugar a la falta de disponibilidad de Microsoft Teams de colaboración. |
| Revise y prepare los cambios dns relacionados con la migración. | Cambios de zona DNS propiedad del cliente para Skype Empresarial Online. |<ul><li>Se recomienda actualizar el tiempo de vida (TTL) para los registros DNS de dominio propiedad del cliente a 5 minutos para acelerar la actualización de los registros DNS. Sin embargo, el recorte administrado por Microsoft asociado a este cambio dns puede producirse en cualquier momento dentro de la ventana de cambio de 24 horas proporcionada. </li><li>La interrupción del servicio es posible en el futuro. Los usuarios no podrán iniciar sesión en Skype Empresarial y se redirigirán a la experiencia Teams migración en los Office 365 servicios. </li></ul>|
| Prepare el aprendizaje y la preparación del usuario final y administración para la transición a Microsoft Teams. | Tenga éxito en la transición de Skype a Teams planeando la comunicación y preparación del usuario. | <ul><li>Los clientes deben tener en cuenta los nuevos servicios y cómo usarlos una vez que sus servicios se transiciónn a los Office 365 servicios. </li><li>Después de que se realicen cambios dns tanto para los dominios de vanidad del cliente como para el dominio inicial, los usuarios iniciarían sesión en Skype Empresarial y verían que ahora se migran a Teams. Esto también descargaría el cliente de escritorio para Teams en segundo plano. </li></ul>|
||||

## <a name="mobile-device-management"></a>Administración de dispositivos móviles

<!-- before phase 5 -->
**Se aplica a:** Clientes que usan una solución de administración de dispositivos móviles (MDM) de terceros<br>
**Cuando se aplica:** cualquier momento antes de que se inicie la fase 5

| Pasos | Descripción | Se aplica a | Impacto |
|:-------|:-----|:-------|:-------|
| Prepare la formación de usuario final y administración sobre los usuarios que quitan y agregan de nuevo su cuenta a Microsoft Outlook para iOS y Android. | Es posible que Outlook microsoft para cuentas de iOS y Android configuradas con buzones en Microsoft Cloud Deutschland tenga que quitarse y agregarse de nuevo a Outlook para sincronizar correctamente la nueva configuración de los servicios Office 365. | Microsoft Outlook para clientes de iOS y Android | Outlook buzones de correo configurados anteriormente para Microsoft Cloud Deutschland puede que no retome la nueva configuración de Office 365 Services, lo que provoca errores y un rendimiento degradado de otras experiencias de usuario. Se recomienda a los administradores de TI que proporcionen documentación que indique proactivamente a los usuarios que quiten y vuelvan a agregar sus cuentas a Microsoft Outlook para iOS y Android si se producen problemas con el inicio de sesión o la sincronización del correo después de la migración. |
| Determine si es necesaria una reconfiguración después de la migración. | Las soluciones de administración de dispositivos móviles (MDM) pueden dirigirse a `outlook.de` puntos de conexión. En esta transición a Office 365, los perfiles de cliente deben actualizarse a la dirección URL Office 365 servicios, `outlook.office365.com` . | Exchange Online y clientes mdm | Los clientes pueden seguir funcionando mientras se puede obtener acceso al punto de conexión, pero producirán un error si los puntos de conexión `outlook.de` de Microsoft Cloud Deutschland ya no están disponibles. |
|||||

## <a name="line-of-business-apps"></a>Aplicaciones de línea de negocio

**Se aplica a:** Clientes que usan aplicaciones de línea de negocio (LOB) con puntos de conexión proporcionados por Microsoft Cloud Deutschland<br>
**Cuando se aplica:** después de la finalización de la fase 2 y antes del final de la fase 9

Si usa un servicio de terceros o aplicaciones de línea de negocio (LOB) integradas con Office 365, debe resolver las dependencias de los puntos de conexión proporcionados por la instancia de Microsoft Cloud Deutschland. Por ejemplo, si las aplicaciones de LOB se conectan a `https://graph.microsoft.de/` , debes cambiar el punto de conexión a `https://graph.microsoft.com/` . Los puntos de conexión del servicio Microsoft Office 365 global estarán disponibles para el inquilino después de la fase 2.

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Determine si es necesaria una reconfiguración después de la migración. | Los servicios y aplicaciones de terceros que se integran con Office 365 pueden codificarse para esperar direcciones IP y direcciones URL de Microsoft Cloud Deutschland. | Acción necesaria. La inacción puede provocar errores en el servicio o el software cliente. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Se aplica a**: Clientes que usan Microsoft Dynamics 365

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Para las suscripciones de espacio aislado de Dynamics 365, asegúrese de descargar el entorno de producción de la instancia de Dynamics SQL de su suscripción a Dynamics 365 en Microsoft Cloud Deutschland. La copia de seguridad de producción más reciente debe restaurarse en el espacio aislado antes de la migración de espacio aislado. | La migración de Dynamics 365 requiere que los clientes se aseguren de que el entorno de espacio aislado se actualice con la base de datos de producción más reciente. | El equipo de FastTrack ayudará a los clientes a realizar ejecuciones secas para validar la actualización de versión de 8.x a 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Se aplica a**: Clientes que usan Power BI

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Eliminación de objetos de Power BI suscripciones que no se migrarán de Power BI Microsoft Cloud Deutschland a Office 365 servicios. | La migración de Power BI de usuario requerirá una acción del cliente para eliminar determinados artefactos, como conjuntos de datos y paneles. | <ul><li>Los administradores pueden tener que quitar los siguientes elementos de su suscripción: </li><li>Real-Time conjuntos de datos (por ejemplo, conjuntos de datos de streaming o inserción) </li><li>Power BI configuración y origen de datos locales de Puerta de enlace de datos </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Si usa la misma partición de identidad de Azure Active Directory para Office 365 y Microsoft Azure en la instancia de Microsoft Cloud Deutschland, asegúrese de que se está preparando para la migración controlada por el cliente de Microsoft Azure servicios.

> [!NOTE]
> Es posible que la migración de los servicios Microsoft Azure no se inicie antes de que el inquilino de Office 365 haya alcanzado la fase de migración 9 y que se complete antes de que se haya iniciado la fase 10 de migración.

Los clientes que usan Office 365 y recursos de Azure (por ejemplo, redes, proceso y almacenamiento) realizarán la migración de recursos a la instancia Office 365 servicios. Esta migración es responsabilidad del cliente. Las publicaciones del Centro de mensajes marcarán el inicio. La migración debe completarse antes de finalizar la organización de Azure AD en el Office 365 de servicios. Para las migraciones de Azure, consulte el libro de reproducción de migración de Azure, Información general sobre las instrucciones [de migración para Azure Germany](/azure/germany/germany-migration-main).

| Pasos | Descripción | Impacto |
|:-------|:-------|:-------|
| Determine qué servicios de Azure están en uso y prepárese para la migración futura de Alemania al espacio empresarial de Office 365 servicios mediante el trabajo con sus asociados. Siga los pasos descritos en el libro de [reproducción de migración de Azure](/azure/germany/germany-migration-main). |<ul><li>La migración de recursos de Azure es una responsabilidad del cliente y requiere un esfuerzo manual siguiendo los pasos prescritos. Comprender qué servicios se usan en la organización es clave para la migración correcta de los servicios de Azure. </li><li> Office 365 Los clientes de Alemania que tienen suscripciones de Azure bajo la misma partición de identidad (organización) deben seguir el orden prescrito por Microsoft cuando puedan iniciar la migración de suscripción y servicios.</li></ul>|<ul><li>Los clientes pueden tener varias suscripciones de Azure, cada suscripción que contenga infraestructura, servicios y componentes de plataforma. </li><li> Los administradores deben identificar suscripciones y partes interesadas para garantizar que la migración y validación rápidas sea posible como parte de este evento de migración. </li><li>Si no se completa correctamente la migración de estas suscripciones y los componentes de Azure dentro de la escala de tiempo prescrita, afectará a la finalización de la transición de Office y Azure AD a los servicios Office 365 y puede provocar la pérdida de datos. </li><li> Una notificación del Centro de mensajes señalará el punto en el que puede comenzar la migración dirigida por el cliente. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services.

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:**

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components.
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>Más información

Introducción:

- [Migración de Microsoft Cloud Deutschland a Office 365 servicios en las nuevas regiones del centro de datos alemán](ms-cloud-germany-transition.md)
- [Asistencia para la migración a Microsoft Cloud Alemania](https://aka.ms/germanymigrateassist)
- [Cómo participar en la migración](ms-cloud-germany-migration-opt-in.md)
- [Experiencia del cliente durante la migración](ms-cloud-germany-transition-experience.md)

Pasar a través de la transición:

- [Impactos y acciones de las fases de migración](ms-cloud-germany-transition-phases.md)
- [Pre-work adicional](ms-cloud-germany-transition-add-pre-work.md)
- Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicaciones en la nube:

- [Información del programa de migración de Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Información del programa de migración de Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introducción a su actualización de Microsoft Teams](/microsoftteams/upgrade-start-here)
