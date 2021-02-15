---
title: Solicitudes de caja de seguridad del cliente
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre las solicitudes de caja de seguridad del cliente que le permiten controlar cómo un ingeniero de soporte técnico de Microsoft puede acceder a sus datos cuando se encuentra con un problema.
ms.openlocfilehash: b475c9af80d0e28961360825788d9e19a426dc69
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48768868"
---
# <a name="customer-lockbox-in-office-365"></a>Caja de seguridad del cliente en Office 365

En este artículo se proporcionan instrucciones de implementación y configuración para la Caja de seguridad del cliente. Caja de seguridad del cliente admite solicitudes de acceso a datos en Exchange Online, SharePoint Online y OneDrive para la Empresa. Para recomendar soporte técnico para otros servicios, envíe una solicitud a [Office 365 UserVoice.](https://office365.uservoice.com/)

Para ver las opciones para otorgar licencias a los usuarios para que se beneficien de las ofertas de cumplimiento de Microsoft 365, incluida esta, a partir del 1 de abril de 2020, consulte la guía de licencias de [Microsoft 365](https://aka.ms/ComplianceSD)para el cumplimiento de & seguridad.

La Caja de seguridad del cliente garantiza que Microsoft no puede acceder al contenido para realizar una operación de servicio sin su aprobación explícita. Caja de seguridad del cliente le incluye en el flujo de trabajo de aprobación para las solicitudes de acceso a su contenido.

En ocasiones, los ingenieros de Microsoft ayudan a solucionar problemas notificados por el cliente en el proceso de soporte técnico. Por lo general, los problemas se solucionan a través de extensas herramientas de telemetría y depuración que Microsoft tiene para sus servicios. Sin embargo, algunos casos requieren que un ingeniero de Microsoft acceda al contenido del cliente para determinar la causa raíz y solucionar el problema. La Caja de seguridad del cliente requiere que el ingeniero solicite acceso al cliente como paso final en el flujo de trabajo de aprobación. Esto ofrece a las organizaciones la opción de aprobar o denegar estas solicitudes y proporcionar control de acceso directo al cliente.

### <a name="customer-lockbox-overview-video"></a>Vídeo de introducción a la Caja de seguridad del cliente

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a>Flujo de trabajo de caja de seguridad del cliente

Los siguientes pasos describen el flujo de trabajo típico cuando un ingeniero de Microsoft inicia una solicitud de caja de seguridad del cliente:

1. Alguien de una organización experimenta un problema con su buzón de Microsoft 365.

2. Una vez que el usuario soluciona el problema, pero no puede solucionarlo, abre una solicitud de soporte técnico con el Soporte técnico de Microsoft.

3. Un ingeniero de soporte técnico de Microsoft revisa la solicitud de servicio y determina la necesidad de tener acceso al inquilino de la organización para reparar el problema en Exchange Online.

4. El ingeniero de soporte técnico de Microsoft inicia sesión en la herramienta de solicitud de caja de seguridad del cliente y realiza una solicitud de acceso a datos que incluye el nombre del inquilino de la organización, el número de solicitud de servicio y el tiempo estimado que el ingeniero necesita tener acceso a los datos.

5. Después de que un administrador de soporte técnico de Microsoft apruebe la solicitud, la Caja de seguridad del cliente envía al aprobador designado en la organización una notificación por correo electrónico sobre la solicitud de acceso pendiente de Microsoft.

    ![Ejemplo de una notificación de correo electrónico de caja de seguridad del cliente](../media/CustomerLockbox1.png)

   Cualquier persona que esté asignada al rol [de](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) administrador del aprobador de acceso a la caja de seguridad del cliente en el Centro de administración de Microsoft 365 puede aprobar las solicitudes de caja de seguridad del cliente.

6. El aprobador inicia sesión en el Centro de administración de Microsoft 365 y aprueba la solicitud. Este paso desencadena la creación de un registro de auditoría disponible mediante la búsqueda en el registro de auditoría. Para obtener más información, vea [Auditoría de solicitudes de caja de seguridad del cliente.](#auditing-customer-lockbox-requests)

   Si el cliente rechaza la solicitud o no la aprueba en un plazo de 12 horas, la solicitud expira y no se concede acceso al ingeniero de Microsoft.

   > [!IMPORTANT]
   > Microsoft no incluye ningún vínculo en las notificaciones por correo electrónico de caja de seguridad del cliente que requieran que inicie sesión en Office 365.

7. Una vez que el aprobador de la organización aprueba la solicitud, el ingeniero de Microsoft recibe el mensaje de aprobación, inicia sesión en el inquilino en Exchange Online y corrige el problema del cliente. Los ingenieros de Microsoft tienen la duración solicitada para solucionar el problema tras el cual se revoca automáticamente el acceso.

> [!NOTE]
> Todas las acciones realizadas por un ingeniero de Microsoft se registran en el registro de auditoría. Puede buscar y revisar estos registros de auditoría.

## <a name="turn-customer-lockbox-requests-on-or-off"></a>Activar o desactivar las solicitudes de caja de seguridad del cliente

Puede activar los controles de caja de seguridad del cliente en el Centro de administración de Microsoft 365. Al activar la Caja de seguridad del cliente, Microsoft debe obtener la aprobación de su organización antes de acceder al contenido de su espacio empresarial.

1. Con una cuenta de trabajo o escuela que tenga asignado el rol de administrador global o **aprobador** de acceso a la Caja de seguridad del cliente, vaya [https://admin.microsoft.com](https://admin.microsoft.com) e inicie sesión.

2. Elija **Configuración > configuración de la organización.**

3. Seleccione **Security & Privacy Customer** Lockbox Edit y, a continuación, mueva el botón de alternancia a On o Off para activar  >    >  o desactivar la característica.  

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>Aprobar o denegar una solicitud de caja de seguridad del cliente

1. Con una cuenta de trabajo o escuela que tenga asignado el rol de administrador global o **aprobador** de acceso a la Caja de seguridad del cliente, vaya [https://admin.microsoft.com](https://admin.microsoft.com) e inicie sesión.

2. Elija **Soporte > solicitudes de caja de seguridad del cliente.**

    ![Haga clic en Soporte técnico y, a continuación, haga clic en Solicitudes de caja de seguridad del cliente](../media/CustomerLockbox5.png)

    Se muestra una lista de solicitudes de caja de seguridad del cliente.

    ![Lista de solicitudes de caja de seguridad del cliente](../media/CustomerLockbox6.png)

3. Seleccione una solicitud de caja de seguridad del cliente y, a continuación, **elija Aprobar** o **denegar.**

    ![Aprobar o denegar solicitudes de caja de seguridad del cliente](../media/CustomerLockbox7.png)

    Se muestra un mensaje de confirmación sobre la aprobación de la solicitud de caja de seguridad del cliente.

    ![Aprobar o denegar solicitudes de caja de seguridad del cliente](../media/CustomerLockbox8.png)

> [!NOTE]
> Use el cmdlet Set-AccessToCustomerDataRequest para aprobar, rechazar o cancelar solicitudes de caja de seguridad del cliente de Microsoft 365 que controlan el acceso a los datos por parte de los ingenieros de soporte técnico de Microsoft. Para obtener más información, [vea Set-AccessToCustomerDataRequest](https://docs.microsoft.com/powershell/module/exchange/set-accesstocustomerdatarequest).


## <a name="auditing-customer-lockbox-requests"></a>Auditoría de solicitudes de caja de seguridad del cliente

Los registros de auditoría que corresponden a las solicitudes de caja de seguridad del cliente se registran en el registro de auditoría. Puede obtener acceso a estos registros mediante la herramienta de búsqueda de registros de [auditoría](search-the-audit-log-in-security-and-compliance.md) en el Centro de & cumplimiento. Las acciones relacionadas con la aceptación o denegación de una solicitud de caja de seguridad del cliente y las acciones realizadas por los ingenieros de Microsoft (cuando se aprueban las solicitudes de acceso) también se registran en el registro de auditoría. Puede buscar y revisar estos registros de auditoría.

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>Buscar en el registro de auditoría la actividad relacionada con las solicitudes de caja de seguridad del cliente

Antes de poder usar el registro de auditoría para realizar un seguimiento de las solicitudes de caja de seguridad del cliente, debe seguir algunos pasos para configurar el registro de auditoría. Para obtener más información, vea [Buscar el registro de auditoría en el Centro de & cumplimiento.](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin) Una vez que haya completado la configuración, siga estos pasos para crear una consulta de búsqueda de registros de auditoría para devolver registros de auditoría relacionados con la Caja de seguridad del cliente:

1. Vaya a [https://protection.office.com](https://protection.office.com).
  
2. Inicie sesión con su cuenta profesional o educativa.

3. En el panel izquierdo del Centro de seguridad & cumplimiento, elija Buscar & **búsqueda de** registro de auditoría  >  **de investigación.**

    Se **muestra la página búsqueda del registro de** auditoría.

    ![Página de búsqueda del registro de auditoría](../media/auditlogsearch1.png)
  
4. Configurar los siguientes criterios de búsqueda: 

    1. **Actividades:** deje este campo en blanco para que la búsqueda devuelva los registros de auditoría de todas las actividades. Esto es necesario para devolver los registros de auditoría relacionados con las solicitudes de caja de seguridad del cliente y la actividad correspondiente realizada por los ingenieros de Microsoft.

    1. **Fecha de inicio** y **fecha de finalización:** seleccione un intervalo de fecha y hora para mostrar los eventos que se produjeron dentro de ese período.

    1. **Usuarios:** deje este campo en blanco.

    1. **Archivo, carpeta o sitio:** deje este campo en blanco.

5. Haga clic en **Búsqueda** para ejecutar la búsqueda mediante sus criterios de búsqueda. 

    Los resultados de la búsqueda se cargan y, después de un momento, se muestran en **Resultados** en la página de búsqueda **del registro de** auditoría.

6. Haga **clic en Filtrar resultados** en la página de resultados de búsqueda y realice una de las siguientes acciones:

   - Para mostrar registros de auditoría relacionados con un aprobador de la organización que aprueba  o deniega una solicitud de caja de seguridad del cliente: en el cuadro de la columna Actividad, escriba **Set-AccessToCustomerDataRequest**.

   - Para mostrar registros de auditoría relacionados con un ingeniero de Microsoft que realiza  acciones en respuesta a una solicitud de caja de seguridad del cliente aprobada: en el cuadro debajo de la columna Usuario, escriba **Operador de Microsoft**. La **columna** Actividad muestra la acción realizada por el ingeniero.

      ![Filtrar por "Operador de Microsoft" para mostrar registros de auditoría](../media/CustomerLockbox10.png)

7. En la lista de resultados, haga clic en un registro de auditoría para mostrarlo.

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>Registro de auditoría de una solicitud de acceso a la Caja de seguridad del cliente

Cuando una persona de su organización aprueba o deniega una solicitud de caja de seguridad del cliente, se registra un registro de auditoría en el registro de auditoría. Este registro contiene la siguiente información.

| Auditar propiedad de registro| Descripción|
|:---------- |:----------|
| Fecha       | La fecha y la hora en que se aprobó o denegó la solicitud de caja de seguridad del cliente.
| Dirección IP | La dirección IP del equipo que el aprobador usó para aprobar o denegar una solicitud. |
| User       | La cuenta de servicio BOXServiceAccount@ \[ customerforest \] .prod.outlook.com.            |
| Actividad   | Set-AccessToCustomerDataRequest; Esta es la actividad de auditoría que se registra al aprobar o denegar una solicitud de caja de seguridad del cliente.                                |
| Elemento       | Guid de la solicitud de caja de seguridad del cliente                             |

La siguiente captura de pantalla muestra un ejemplo de un registro de auditoría que corresponde a una solicitud de caja de seguridad del cliente aprobada. Si se denegó una solicitud de caja de seguridad del cliente, el valor del parámetro **ApprovalDecision** sería **Deny**.

![Registro de auditoría de una solicitud de caja de seguridad del cliente aprobada](../media/CustomerLockbox9.png)

> [!TIP]
> Para mostrar información más detallada en un registro de auditoría, haga clic **en Más información.**

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Registro de auditoría de una acción realizada por un ingeniero de Microsoft

Las acciones realizadas por un ingeniero de Microsoft después de que se apruebe una solicitud de caja de seguridad del cliente (y que pueden dar lugar al acceso al contenido del cliente) se registran en el registro de auditoría. Estos registros contienen la siguiente información.

| Auditar propiedad de registro| Descripción|
|:---------- |:----------|
| Fecha       | Fecha y hora en que se realizó la acción. Ten en cuenta que la hora en que se realizó esta acción será en un plazo de 4 horas a partir de la aprobación de la solicitud de caja de seguridad del cliente.              |
| Dirección IP | La dirección IP del equipo que usó el ingeniero de Microsoft. |
| User       | Operador de Microsoft; este valor indica que este registro está relacionado con una solicitud de caja de seguridad del cliente.                                  |
| Actividad   | Nombre de la actividad realizada por el ingeniero de Microsoft.|
| Elemento       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a>¿A qué servicios de Microsoft 365 se aplica la Caja de seguridad del cliente?

La Caja de seguridad del cliente es compatible actualmente con Exchange Online, SharePoint Online y OneDrive para la Empresa.

#### <a name="is-customer-lockbox-available-to-all-customers"></a>¿La Caja de seguridad del cliente está disponible para todos los clientes?

La Caja de seguridad del cliente se incluye con las suscripciones de Microsoft 365 u Office 365 E5 y se puede agregar a otros planes con una suscripción de complemento de protección y cumplimiento de la información o de cumplimiento avanzado. Consulte Planes [y precios para](https://products.office.com/business/office-365-enterprise-e5-business-software) obtener más información.

#### <a name="what-is-customer-content"></a>¿Qué es el contenido del cliente?

El contenido del cliente son los datos creados por los usuarios de los servicios y aplicaciones de Microsoft 365. Entre los ejemplos de contenido del cliente se incluyen:

- Cuerpo del correo electrónico o datos adjuntos de correo electrónico

- Contenido del sitio de SharePoint

- Información en el cuerpo de un archivo de SharePoint

- Cuerpo del archivo de presentación de Skype Empresarial

- Mensajes instantáneos (MI) o conversaciones de voz

- Blob generado por el cliente o datos de almacenamiento estructurado (por ejemplo, contenedores de SQL)

- Información de seguridad propiedad del cliente (por ejemplo, certificados, claves de cifrado y contraseñas)

- Inferencias y todas las inferencias posteriores, si el contenido del cliente permanece

Para obtener información adicional sobre el contenido del cliente en Office 365, vea el Centro de confianza de [Office 365.](https://products.office.com/business/office-365-trust-center-privacy/)

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>¿A quién se notifica cuando hay una solicitud de acceso a mi contenido?

Se notifica a los administradores globales y a cualquier persona asignada al rol de administrador del aprobador de acceso a la Caja de seguridad del cliente. También son los mismos usuarios que pueden aprobar las solicitudes de caja de seguridad del cliente.

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>¿Quién puede aprobar o rechazar estas solicitudes en mi organización?

Los administradores globales y cualquier persona asignada al rol de administrador del aprobador de acceso a la Caja de seguridad del cliente pueden aprobar las solicitudes de caja de seguridad del cliente. Los clientes controlan estas asignaciones de roles en sus organizaciones.

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>¿Cómo puedo participar en la Caja de seguridad del cliente?

Un administrador global puede habilitar y configurar la Caja de seguridad del cliente en el Centro de administración de Microsoft 365 o Microsoft 365.

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>Si apruebo una solicitud de caja de seguridad del cliente, ¿qué puede hacer el ingeniero y cómo sabrá lo que hizo el ingeniero de Microsoft?

Después de aprobar una solicitud de caja de seguridad del cliente, el ingeniero de Microsoft concedió estos privilegios necesarios para acceder al contenido del cliente mediante cmdlets aprobados previamente. Las acciones realizadas por los ingenieros de Microsoft en respuesta a las solicitudes de caja de seguridad del cliente se registran y son accesibles en el registro de auditoría del Centro de & cumplimiento.

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>¿Cómo sé que Microsoft sigue el proceso de aprobación?

Puede hacer referencia cruzada a las notificaciones de aprobación de correo electrónico enviadas a los administradores y aprobadores de su organización con el historial de solicitudes de caja de seguridad del cliente en el Centro de administración de Microsoft 365.

Caja de seguridad del cliente se incluye en el último informe de auditoría [de SOC 1 SSAE 16](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports). Para obtener más información, puede encontrar los informes más recientes en el Portal de confianza [de servicios de Microsoft.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>¿Puede Microsoft modificar la lista de aprobadores de mi espacio empresarial? Si no es así, ¿cómo se evita?

Solo un administrador global de la organización puede especificar quién puede aprobar las solicitudes de caja de seguridad del cliente. Esto significa que solo los miembros del grupo administrador global de Azure Active Directory pueden especificar quién puede aprobar la solicitud. La pertenencia al grupo de administradores globales en Azure Active Directory solo la administra su organización.

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>¿Qué ocurre si necesito más información sobre una solicitud de acceso al contenido para aprobarla?

Cada solicitud de caja de seguridad del cliente contiene un número de solicitud de servicio de Microsoft 365. Puede ponerse en contacto con el Soporte técnico de Microsoft y hacer referencia a este número de servicio para obtener más información sobre la solicitud.

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>Cuando se aprueba una solicitud de caja de seguridad del cliente, ¿durante cuánto tiempo son válidos los permisos?

Actualmente, el período máximo para los permisos de acceso concedidos al ingeniero de Microsoft es de 4 horas. El ingeniero de Microsoft también puede solicitar un período más corto.

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>¿Cómo puedo obtener un historial de todas las solicitudes de caja de seguridad del cliente?

Todas las solicitudes de caja de seguridad del cliente se ven en el Centro de administración de Microsoft 365.

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>¿Cómo puedo correlacionar las solicitudes de acceso al contenido con los registros de auditoría relacionados?

La fuente de actividades del Centro de cumplimiento contiene actividades de registro de la Caja de seguridad del cliente. Los clientes pueden hacer referencia cruzada a las actividades de registro de la Caja de seguridad del cliente desde la fuente de actividades con la solicitud de correo electrónico que reciben.

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>¿Qué sucede cuando un cliente no responde a una solicitud de caja de seguridad del cliente?

Las solicitudes de caja de seguridad del cliente tienen una duración predeterminada de 12 horas. Si no responde a una solicitud en un plazo de 12 horas, la solicitud expira.

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>¿Qué hace Microsoft cuando un cliente rechaza una solicitud de caja de seguridad del cliente?

Si un cliente rechaza una solicitud de caja de seguridad del cliente, no se produce acceso al contenido del cliente. Si un usuario de su organización sigue experimentando un problema de servicio que requiere que Microsoft acceda al contenido del cliente para resolver el problema, el problema de servicio puede persistir y Microsoft informará al usuario sobre esto.

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>¿Protege la Caja de seguridad del cliente contra las solicitudes de datos de los organismos de seguridad u otros terceros?

No. Microsoft se toma muy en serio las solicitudes de terceros para los datos de los clientes. Como proveedor de servicios en la nube, Microsoft siempre promueve la privacidad de los datos de los clientes. En caso de que obtengamos una citación, Microsoft siempre intenta redirigir al tercero al cliente para obtener la información. (Lea el blog de Brad Smith: [Proteger los datos de los clientes del espionaje gubernamental).](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) Publicamos periódicamente [información detallada sobre](https://www.microsoft.com/corporate-responsibility/lerr) las solicitudes de cumplimiento de la ley que Microsoft recibe.

Consulte el [Centro de confianza](https://www.microsoft.com/trustcenter/default.aspx) de Microsoft con respecto a las solicitudes de datos de terceros y la sección "Divulgación de datos de clientes" en los Términos de Online [Services](https://www.microsoft.com/Licensing/product-licensing/products.aspx) para obtener más información.

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>¿Cómo garantiza Microsoft que un miembro de su personal no tenga acceso permanente al contenido de los clientes en las aplicaciones de Office 365?

Microsoft implementa amplias medidas preventivas a través de sistemas de control de acceso y medidas de investigación para identificar y solucionar los intentos de sortear estos sistemas de control de acceso. Microsoft 365 funciona con los principios de privilegios mínimos y acceso just-in-time. Por lo tanto, ningún personal de Microsoft tiene permiso para acceder al contenido de los clientes de forma continua. Si se concede el permiso, tiene una duración limitada. 

Microsoft 365 usa un sistema de control de acceso denominado *Caja* de seguridad para procesar solicitudes de permisos que conceden la capacidad de realizar funciones operativas y administrativas dentro del servicio. Un operador debe solicitar acceso al contenido del cliente mediante caja de seguridad, lo que requiere que una segunda persona tome medidas en la solicitud (por ejemplo, aprobarla) antes de conceder el acceso. Esa segunda persona no puede ser el solicitante y debe estar designada para aprobar el acceso al contenido del cliente. Solo si se aprueba la solicitud, el operador obtiene acceso temporal al contenido del cliente. Una vez expirado el período de elevación, Caja de seguridad revoca el acceso.

Consulte los Términos de [Online Services para](https://www.microsoft.com/licensing/product-licensing/products) obtener más información sobre las prácticas de seguridad generales de Microsoft.

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>¿En qué circunstancias los ingenieros de Microsoft necesitan acceso a mi contenido?

El escenario más común en el que los ingenieros de Microsoft necesitan acceder al contenido del cliente es cuando el cliente realiza una solicitud de soporte técnico que requiere acceso para solucionar problemas. Un principio fundamental de Microsoft 365 es que el servicio funciona sin acceso de Microsoft al contenido del cliente. Casi todas las operaciones de servicio realizadas por Microsoft están completamente automatizadas y la participación humana es altamente controlada y abstraida del contenido del cliente. El objetivo de Microsoft 365 es acceder al contenido del cliente para dar soporte al servicio no es necesario hasta que el cliente apruebe una solicitud específica para el acceso de Microsoft.

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>Ya consideré que mis datos estaban seguros con la nube de Microsoft, así que ¿por qué necesito la Caja de seguridad del cliente?

La Caja de seguridad del cliente proporciona un nivel adicional de control al ofrecer a los clientes la capacidad de dar autorización de acceso explícita para las operaciones de servicio. Al demostrar que hay procedimientos para la autorización explícita de acceso a datos, la Caja de seguridad del cliente también ayuda a los clientes a cumplir ciertas obligaciones de cumplimiento, como HIPAA y FEDRAMP.
