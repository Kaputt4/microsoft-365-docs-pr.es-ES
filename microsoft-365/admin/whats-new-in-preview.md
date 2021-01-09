---
title: ¿Cuáles son las novedades del Centro de administración de Microsoft 365?
f1.keywords:
- CSH
ms.author: anfowler
author: adefowler
manager: shohara
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
- FRP150
description: 'El Centro de administración de Microsoft 365: obtenga información sobre las características que se agregaron este mes.'
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
ms.openlocfilehash: 12b7dfd39a9cf8ac73e8f1c7f2297721c2d629bf
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787884"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Novedades del Centro de administración de Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Es posible que parte de la información de este artículo no se aplique a Office 365 operado por 21Vianet.

::: moniker-end

We're continuously adding new features to [the Microsoft 365 admin center,](microsoft-365-admin-center-preview.md)fixing issues we learn about, and making changes based on your feedback. Echa un vistazo a continuación para ver lo que está disponible para ti en la actualidad. Algunas características se implantan a distintas velocidades para nuestros clientes. Si aún no ve una característica, pruebe a agregarse a [la versión dirigida.](manage/release-options-in-office-365.md)

Y si quieres saber las novedades de otros servicios en la nube de Microsoft:

- [Novedades de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/whats-new)
- [Novedades del Centro de administración de Exchange](https://docs.microsoft.com/Exchange/whats-new)
- [Novedades de Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/whats-new)
- [Novedades del Centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/whats-new)
- [Novedades de Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)
- [Novedades del Centro de administración de SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)
- [Actualizaciones de Office](https://docs.microsoft.com/OfficeUpdates/)

## <a name="ignite-2020-august--september"></a>Ignite 2020 (agosto & septiembre)

Bienvenido a Microsoft Ignite: nuestro primer Ignite solo en línea. Esperamos verlo en una de nuestras sesiones: Catálogo de sesiones de [Microsoft Ignite 2020](https://myignite.microsoft.com/sessions). Estas son solo algunas de las cosas de las que hablaremos en Ignite. 
> [!NOTE]
> No todas las características estarán disponibles para todos los usuarios inmediatamente. Si no ve las nuevas características, únase [a la versión dirigida.](manage/release-options-in-office-365.md)

### <a name="multi-tenant-management"></a>Administración multiinquilino

Hemos desarrollado un conjunto de características para administradores multiinquilino como usted para que el trabajo se haga de forma más rápida y eficaz. Para obtener más información, vea [Administrar varios inquilinos.](multi-tenant/manage.md)

- **Sus inquilinos:** cambie rápidamente entre los inquilinos que administra.
- Todos los **inquilinos:** una nueva página donde puede ver rápidamente el estado de todos los servicios de sus inquilinos, las solicitudes de servicio abiertas, los productos y la facturación, las tareas de configuración recomendadas y el número de usuarios de ese inquilino.
- **Configuración:** la página de instalación multiinquilino le ofrece una vista de lista de la página de instalación, pero organizada para muchos inquilinos. Puede ver qué características no están activadas, qué tareas se completan para todos los inquilinos, tareas que los inquilinos aún necesitan completar. Esta vista le ayudará a realizar un seguimiento de la adopción de características y a asegurarse de que siempre se realizan las tareas de configuración de seguridad recomendadas.
- **Estado del** servicio: la vista de estado del servicio muestra si algún incidente o aviso está afectando a los inquilinos. Incluso le mostrará cuántos de los inquilinos administrados se ven afectados. Solo tiene que seleccionar un incidente para obtener más información en la pestaña información general y, a continuación, cambiar a la pestaña Inquilinos afectados para explorar en profundidad y dar soporte técnico a ese inquilino.
- **Las migraciones de buzones** entre inquilinos son un nuevo servicio, ahora en versión preliminar pública, que le permite mover buzones entre inquilinos sin necesidad de quitar y, a continuación, incorporar buzones. 
- **Uso compartido de dominios entre** inquilinos: pronto, puede unirse a una vista previa privada de las funcionalidades que le permiten compartir un dominio entre varios inquilinos. Por ejemplo, si Contoso adquiere Wingtip Toys, Contoso puede compartir el dominio con Wingtip Toys para que los usuarios de ambos inquilinos puedan usar "contoso.com" como direcciones de correo electrónico.

![Página de estado del servicio para varios inquilinos con un incidente seleccionado y la pestaña Inquilinos afectados abierta. El menú de navegación tiene todos los inquilinos, el programa de instalación y el estado del servicio como únicas opciones.](../media/MAC-WN-MTinServiceHealth.png)

### <a name="monitor-your-most-important-accounts"></a>Supervisar las cuentas más importantes

Puede supervisar y realizar un seguimiento de los mensajes de correo electrónico con errores o retrasos enviados a los usuarios que tienen un alto impacto empresarial, como su director general. Puede realizar un seguimiento de las cuentas de prioridad agregando usuarios a la lista de cuentas de prioridad en el Centro de administración de Microsoft 365. Agregue ejecutivos, líderes, administradores u otros usuarios que tengan acceso a información confidencial o de prioridad alta.

Las cuentas de prioridad solo están disponibles para las organizaciones que cumplen los dos requisitos siguientes:

- Office 365 E3, Microsoft 365 E3, Office 365 E5 o Microsoft 365 E5.
- Al menos 10 000 licencias y al menos 50 usuarios activos mensuales de Exchange Online.

![Página de instalación de la característica: Supervisar las cuentas más importantes](../media/MAC-WN-PriorityAccounts.png)

Hay dos formas de empezar:

- Vaya a **Usuarios** y, a continuación, en el menú "Más acciones",  seleccione Administrar cuentas de prioridad para agregar usuarios a la lista.
- Vaya a **Instalación,** busque la tarea de instalación **Supervisar las cuentas más** importantes y, a continuación, seleccione **Introducción.**

Para obtener más información sobre las cuentas de prioridad, consulte [Supervisión de cuentas de prioridad.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

### <a name="search-faster-and-get-better-results-from-any-page"></a>Buscar más rápido y obtener mejores resultados desde cualquier página

We've started rolling out a new Search experience for the admin center, and we can't wait for you to try it out. ![El cuadro de búsqueda se ha movido a la región de banner. Alt+S para buscar desde cualquier página.](../media/MAC-WN-GlobalSearch.png)

- El cuadro de búsqueda se movió al área de encabezado donde dice "Centro de administración de Microsoft 365" para que ahora busque desde cualquier página, no solo la página principal. Incluso tenemos un acceso directo: **Alt+S**.
- La búsqueda es más inteligente y le dará mejores resultados, incluso más rápido. Pruebe a escribir "2fa" para empezar.
- Los resultados de la búsqueda se organizan por el tipo de elemento o acción que puede realizar.
  - **Usuarios:** seleccione el nombre del usuario y puede editarlo directamente. Si selecciona el menú "más acciones" junto a su nombre, puede restablecer su contraseña. Puede buscar por nombre para mostrar, apellidos, nombre, nombre de usuario o dirección de correo electrónico principal y alias de correo electrónico. Pero para obtener una coincidencia exacta, busque por dirección de correo electrónico principal o nombre de usuario.
  - **Grupos:** edite el grupo desde cualquier página, agregue miembros y asigne propietarios.
  - **Acciones:** de forma similar a cómo puede buscar un usuario y, a continuación, restablecer su contraseña, también puede buscar "restablecer contraseña" desde cualquier página y, a continuación, restablecer una o más contraseñas para los usuarios.
  - **Navegación:** los resultados en Navegación pueden ayudarle rápidamente a acceder rápidamente a una página en el Centro de administración. Por ejemplo, la búsqueda de "roles" le llevará a la página Roles para los roles de Azure AD.
  - **Configuración:** busque cualquier configuración relacionada con su organización, los servicios a los que se suscriba y la configuración de seguridad y privacidad. 
  - **Dominios:** puede encontrar vínculos rápidos a sus dominios y, a continuación, el vínculo le llevará a la página Información general y estado de ese dominio.
  - **Documentación:** si no podemos encontrar un resultado para usted, intentaremos encontrar documentación para ayudarle. La lista de artículos seleccionados tarda un poco más en encontrar una coincidencia, así que espere un segundo para que la búsqueda encuentre los resultados. 
  - **Comentarios:**¿No encontró lo que estaba buscando? Envíenos sus comentarios desde La búsqueda. Agregaremos la funcionalidad de búsqueda para más páginas y más características en el centro de administración.

### <a name="microsoft-365-admin-mobile-app"></a>Aplicación móvil de administración de Microsoft 365

La aplicación móvil de administración de [Microsoft 365,](https://www.microsoft.com/microsoft-365/business/manage-office-365-admin-app)que se incluye con su suscripción, le permite administrar Microsoft 365 desde su dispositivo móvil para que pueda salir de su escritorio para realizar tareas diarias. De hecho, hay más de 90 características en la aplicación y solo agregamos algunas más:

- Compatibilidad con las directivas de administración de aplicaciones móviles y acceso condicional de **Microsoft Intune:** ahora puede usar su dispositivo personal para administrar Microsoft 365 incluso si su organización ha activado la administración de aplicaciones móviles y las directivas de acceso condicional de Intune.
- **Notificaciones del centro de mensajes:** active las notificaciones del centro de mensajes en notificaciones de configuración si desea recibir una alerta sobre las nuevas publicaciones  >   del centro de mensajes. A través de las notificaciones, queremos asegurarnos de que se mantenga informado sobre información y eventos importantes en todo el espacio empresarial.
- **Alertas de** facturación: también puedes activar las notificaciones de facturación en notificaciones de configuración si quieres recibir notificaciones de facturación en el dispositivo si una suscripción está a punto  >   de expirar.
- **Modo oscuro:** bienvenido al lado oscuro de la aplicación móvil. Esta era una de las características más solicitadas. Ve a **Temas**  >  **de configuración** para activarlo.
- **Notificar un problema:** ahora puedes informar de un problema en la aplicación o ver los problemas notificados por otros administradores. Visite **el estado del** servicio para comprobarlo.

![La página Estado de la aplicación de administración de Microsoft 365 con notificaciones para el centro de mensajes, estado del servicio, alertas de facturación.](../media/MAC-WN-AdminMobileApp.png)

### <a name="usage-recommendations-for-small-and-medium-businesses"></a>Recomendaciones de uso para pequeñas y medianas empresas

Es posible que las pequeñas  y medianas empresas reciban una recomendación en la página principal si algunas de las personas de la organización no usan activamente teams, OneDrive u aplicaciones de Office. Cuando vea la recomendación, puede enviar rápidamente un correo electrónico de aprendizaje de Microsoft a los usuarios inactivos para ayudarles a empezar a usar la aplicación y asegurarse de que obtiene todo el valor de las suscripciones.

### <a name="remote-work-collection"></a>Colección de trabajo remoto

En octubre, agregaremos una colección de trabajo remoto para ayudar a los propietarios de pequeñas empresas y a su personal a entrar en línea y trabajar de forma remota.  **La configuración de elementos básicos** del trabajo remoto es una lista protegida de todas las características que Microsoft recomienda para habilitar de forma segura el trabajo remoto y colaborar de forma eficaz. En un par de semanas, puede probarlo en Setup  >  **Remote work essentials**.

![Página de aspectos básicos del trabajo remoto en el programa de instalación con 7 tareas no iniciadas.](../media/MAC-WN-RemoteWork.png)

Para obtener más información acerca de cómo permitir de forma segura el trabajo remoto y una dirección web práctica que sea fácil de recordar y compartir, vaya a [aka.ms/remote-business](https://aka.ms/remote-business).

### <a name="need-help-moving-to-more-admin-centers"></a>¿Necesita ayuda? mover a más centros de administración

Estamos observando y actualizando continuamente el contenido y las herramientas para mantenerse al día con los cambios en el producto. Ahora tenemos muchas más herramientas de diagnóstico de autoservicio para ayudarle a resolver problemas de forma rápida y eficaz. Estas son algunas de las que se agregaron recientemente:

- Cambiar la directiva de limitación del servicio web de Exchange
- Comprobación del estado de aprovisionamiento y validación de Teams para usuarios específicos
- Corregir problemas de configuración de DKIM
- Diagnosticar errores de inscripción de usuarios de Intune

Y estamos implementando la nueva y mejorada experiencia de soporte técnico que ya ve en el Centro de administración de Microsoft 365 en algunos de los otros centros de administración. El Centro de administración de Teams y los Centros de administración de seguridad y cumplimiento ya tienen esta nueva experiencia. Y pronto, **el Centro de administración de Exchange,** el Centro de administración de **SharePoint** y **Office.com** se actualizarán junto con esta nueva experiencia de ayuda para administradores.

### <a name="manage-changes-with-microsoft-planner"></a>Administrar cambios con Microsoft Planner

En mayo, anunciamos que pronto podrá sincronizar las publicaciones del Centro de mensajes con Microsoft Planner y ahora está disponible para que todos puedan usarlas.  Ahora puede crear tareas a partir de mensajes, asignarlas y realizar un seguimiento de ellas hasta su finalización. La primera vez que seleccione **la sincronización de Planner,** tendrá que conectarse al plan adecuado.

![Página del centro de mensajes con "sincronización de planner" resaltada en la barra de comandos junto al botón de preferencias.](../media/MAC-WN-MCPlannerSync.png)

Para obtener más información, consulte este artículo y vídeo para ver cómo funciona: Realizar un seguimiento de las publicaciones del centro de [mensajes en Planner](https://docs.microsoft.com/Office365/Planner/track-message-center-tasks-planner)

### <a name="documentation-training-and-videos"></a>Documentación, aprendizaje y vídeos

- Totalmente nuevo y justo a tiempo para Microsoft Ignite:[El concentrador virtual.](https://adoption.microsoft.com/virtual-hub/) Profundizar en el aprendizaje técnico para profesionales de TI y desarrolladores. Busque rápidamente unos 20 vídeos nuevos como parte de #SIDETRACKED, el nombre de la pista de administración de Ignite este año.
- Novedades de la serie de vídeos de [Microsoft 365:](https://www.youtube.com/watch?v=OVjb2lGJ4GU&t=2s) este mes, tratamos las nuevas características disponibles en whiteboard para Teams y en la web, cómo automatizar el aprovisionamiento de usuarios en Azure AD, nuevos desencadenadores y acciones de Power Automate en Teams, etc. Y manténgase atento para el mes que viene, donde tendremos un resumen de todas las cosas excelentes que están sucediendo en Ignite.
- Hemos rediseñado la página de [documentación de Microsoft 365](https://docs.microsoft.com/microsoft-365) que se centra en las soluciones en primer lugar. Resaltaremos las nuevas soluciones a medida que estén disponibles en esta página, así que tenga un vistazo.

![Nueva página de aterrizaje para la documentación de soluciones de Microsoft 365 con soluciones como "Dar poder a los trabajadores remotos".](../media/MAC-WN-M365Docspage.png)

## <a name="july-2020"></a>Julio de 2020

### <a name="getting-ready-for-ignite-2020"></a>Prepararse para Ignite 2020

A medida que nos estamos trasladando a la estación de Ignite en Microsoft, no estamos lanzando tantas características para que podamos hablar mucho durante nuestras sesiones.

La próxima actualización de este artículo será el día de apertura de nuestro primer Ignite solo en línea. Y este año, es gratuito asistir. Check it out, get signed up: [Microsoft Ignite 2020](https://www.microsoft.com/ignite).

### <a name="your-products"></a>Sus productos

Se ha realizado mucho trabajo en la administración de suscripciones para que la página sea más rápida de cargar, más rápida para encontrar lo que está buscando y para cumplir con los estándares de accesibilidad web (directrices[WCAG 2.1).](http://www.w3.org/TR/WCAG21/)

- **Rediseño de** la tabla: se ha rediseñado la tabla para que puedas agrupar suscripciones similares. Vaya a  >  **Facturación de sus productos.**
- **Detalles del** producto: obtenga más detalles que nunca sobre las suscripciones seleccionando el producto en la lista.
- **Haga todo desde aquí:** y no tiene que ir a saltar por varias páginas para administrar un producto. Por ejemplo, si necesita cancelar una suscripción, el panel se abrirá para realizar la acción justo allí.

![La página Productos con el panel Cancelar suscripción abierto.](../media/MAC-WN-SubscrDetails.png)

### <a name="domains"></a>Dominios

La administración de dominios puede ser complicada y hemos lanzado una nueva característica para que sea más fácil. Vaya a Configuración > Dominios y, a continuación, seleccione un dominio para obtener más información sobre su dominio y el estado del dominio.

:::image type="content" source="../media/MAC-WN-DomainDNS.PNG" alt-text="Página de detalles de dominios para contoso.com":::

### <a name="docs-training-and-videos-july-2020"></a>Documentos, cursos y vídeos (julio de 2020)

Novedades de la serie de vídeos de [Microsoft 365:](https://youtu.be/m1Nu8WJgCDY) este mes, tratamos la nueva experiencia de Yammer para web y móvil, cómo integrar la aplicación Comunidades de Yammer para Microsoft Teams, nuevos paquetes de directivas para dar soporte a firstline workers y administradores, y mucho más.

## <a name="june-2020"></a>Junio de 2020

### <a name="keeping-up-with-office-whats-new-management"></a>Mantenerse al día con la administración de novedades de Office

Hace unos meses, agregamos una configuración que le permite administrar los mensajes novedades que se muestran en las aplicaciones [de Office de un usuario.](#office-whats-new-management) Este mes, hemos publicado una nueva tarjeta de página principal  que le ayudará a actuar rápidamente y realizar un seguimiento de los mensajes novedades que desea que se muestran a los usuarios de su organización.

### <a name="docs-training-and-videos-june"></a>Documentos, cursos y vídeos (junio)

- [Introducción a Teams](https://support.microsoft.com/office/184f1aba-2f91-43f0-86e1-9fae607e24f6)

## <a name="may-2020"></a>Mayo de 2020

### <a name="new-update-channel-for-office"></a>Nuevo canal de actualización para Office

El 12 de mayo anunciamos la disponibilidad de un nuevo canal de actualización para Office: Canal empresarial mensual. Este canal de actualización proporciona a los usuarios nuevas características de Office una vez al mes, el segundo martes del mes.

Si permite que los usuarios instalen Office automáticamente desde el portal, puede seleccionar canal empresarial mensual para ellos. Para ello, inicie sesión en el Centro de administración de Microsoft 365 y vaya **a** Mostrar todas las opciones de descarga de software de Office de los Servicios de configuración  >   >    >    >  **de la organización.** Si selecciona Una **vez al mes (Canal** empresarial mensual), todas las nuevas autoconsecciones de Office se configurarán para usar el Canal empresarial mensual.

Junto con el lanzamiento del Canal empresarial mensual, también estamos revisando los nombres de los canales de actualización existentes. Por ejemplo, se cambia el nombre del canal mensual a Canal actual. Los nuevos nombres tienen efecto el 9 de junio de 2020.

Para obtener más información, vea [Cambios para actualizar canales de Aplicaciones de Microsoft 365.](https://docs.microsoft.com/DeployOffice/update-channels-changes)

### <a name="new-admin-roles"></a>Nuevos roles de administrador

Hemos agregado algunos nuevos roles de administrador de Azure Active Directory al Centro de administración de Microsoft 365.

- El rol de administrador de identidad híbrida concede permiso a los usuarios para administrar los servicios de autenticación y aprovisionamiento en la nube.
- El rol de administrador de red permite a los usuarios administrar ubicaciones de red y revisar las perspectivas de red de Software como servicio de Microsoft 365.
- El rol de administrador de impresoras concede permiso para administrar todos los aspectos de las impresoras y las conexiones de impresora.
- El técnico de impresora es un subconjunto del rol de administrador de impresoras en el que los usuarios pueden registrar y anular el registro de impresoras, así como actualizar el estado de la impresora.
Para obtener más información sobre estos roles, consulte [Acerca de los roles de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

### <a name="export-groups-list"></a>Exportar lista de grupos

Hemos escuchado a muchos administradores que necesitan compartir información sobre grupos y su uso a personas que no tienen acceso a los centros de administración. Ahora puede exportar la lista de grupos a un archivo CSV con fines de auditoría, lo que significa que puede lanzar ese script de PowerShell antiguo. Para probarlo, vaya a **Grupos**  >  **y,** a continuación, **seleccione Exportar grupos** desde la barra de comandos.

### <a name="microsoft-365-solution-and-architecture-center"></a>Centro de soluciones y arquitectura de Microsoft 365

Este mes, hemos lanzado un nuevo sitio llamado Centro de arquitectura y soluciones de [https://docs.microsoft.com](https://docs.microsoft.com) [Microsoft 365,](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center)que reúne las instrucciones técnicas que necesita para comprender, planear e implementar soluciones integradas de Microsoft 365 para una colaboración segura y compatible. En este centro, encontrarás:

- Guía de soluciones fundamentales
- Soluciones de carga de trabajo y guía de escenarios
- Ilustraciones de arquitectura y soluciones (los pósteres!!!)
- Guía específica del sector
- Entidades de seguridad de diseño de arquitectura empresarial

### <a name="docs-training-and-videos-may"></a>Documentos, cursos y vídeos (mayo)

- Novedades de la serie de vídeos de **Microsoft 365:** este mes, se trata la nueva experiencia de soporte técnico en los Centros de seguridad y cumplimiento de Teams, la integración de Planner con el Centro de mensajes y el nuevo diseño de vídeo 3x3 en Microsoft Teams. 
- La página del centro de ayuda del Centro de administración de [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/) se actualizó para ayudarle a encontrar lo que necesita más rápidamente. Y si ves esa página en este momento, hemos agregado una tarjeta para informarte de cambios y actualizaciones importantes.

## <a name="april-2020"></a>Abril de 2020

### <a name="intune-roles-management"></a>Administración de roles de Intune

[Abril de 2020](#april-2020)

Bueno, lo hicimos. Hemos dado el segundo paso hacia una experiencia de roles unificados y ahora puede administrar los roles de Intune en el Centro de administración de Microsoft 365. También puede aprovechar características como la capacidad de buscar roles y ver permisos de roles. Esto significa que no necesita dos herramientas independientes para administrar roles para Microsoft 365 e Intune. Al iniciar sesión en el Centro de administración de Microsoft 365, verá que hay dos tablas dinámicas en la página Roles, una para Azure AD y otra para Intune.

![Página roles con la tabla dinámica de Intune seleccionada](../media/MAC-WN-IntuneRoles.png)

### <a name="sync-message-center-posts-to-planner"></a>Sincronizar publicaciones del Centro de mensajes con Planner

A partir de mayo, los administradores que estén en la versión dirigida empezarán a ver el botón "Sincronización de Planner" en el centro de mensajes. Ahora puede realizar un seguimiento de los mensajes que necesitan acción, seleccionar el tipo de mensajes que le gustaría realizar un seguimiento, asignar mensajes para realizar un seguimiento como tareas y etiquetar mensajes para su atención posterior.

[Unirse a la versión dirigida](manage/release-options-in-office-365.md) para empezar.

### <a name="need-help-launched-in-teams-admin-center--security-and-compliance-centers"></a>"¿Necesita ayuda?" iniciado en el Centro de administración de Teams & de seguridad y cumplimiento

El Centro de administración de Teams, el Centro de seguridad y el Centro de cumplimiento ahora usan el mismo "¿Necesita ayuda?" que el Centro de administración de Microsoft 365 usa para buscar ayuda y ponerse en contacto con el soporte técnico. Hemos recibido una gran cantidad de comentarios de los administradores que deseabas el mismo nivel de ayuda y soporte técnico y estamos encantados de llevarte esto. Pruébalo y danos tus comentarios.

#### <a name="need-chat"></a>¿Necesita chat?

Nuestros agentes de soporte técnico han estado trabajando desde casa a la vez que siguen teniendo casos de clientes y limitaciones en el ancho de banda de Internet mientras trabajan desde casa pueden afectar a la calidad de las llamadas de los clientes. Para seguir recibiendo soporte técnico, hemos lanzado la opción de soporte de chat en directo para clientes comerciales en el Centro de administración de Microsoft 365.

Al crear una solicitud de servicio, ahora verá el chat como una opción, además del teléfono y el correo electrónico. Seleccione el chat como canal de comunicación preferido y cree la solicitud. Una vez que haya creado la solicitud, puede iniciar el chat cuando esté listo para chatear con los agentes de Microsoft.

### <a name="teams-updates"></a>Actualizaciones de Teams

Con el aumento del uso de Teams, hemos agregado algunas características que le ayudarán a administrarlas.

- Una nueva tarjeta de recomendación en la página principal del centro de administración muestra qué usuarios no han usado Activamente Teams durante 30 días. Puede enviar a esos usuarios un correo electrónico de aprendizaje para que puedan empezar a usar Teams.
- **Reunir a** los usuarios  con los equipos: vaya a configuración para ver una nueva página que le ayudará a activar Teams para usuarios con licencia y permitir el acceso de invitados, para que pueda trabajar con clientes externos en Teams.
- Una tarjeta de Microsoft Teams ahora está anclada de forma predeterminada a la página principal. Muestra si Teams está activado y si se permite el acceso de invitado. También le permite comprobar el estado de configuración de los usuarios de Teams recién con licencia y comprobar si los problemas de red pueden afectar a los usuarios de Teams.
- Por último, Teams es ahora un paso en el flujo de configuración inicial si compró una licencia que incluye Teams.

### <a name="productivity-score"></a>Puntuación de productividad

La puntuación de productividad ofrece información sobre cómo los usuarios usan los servicios en la nube de Microsoft y las experiencias de tecnología que los admiten. La puntuación refleja el rendimiento de su organización frente a las medidas de experiencia de empleados y tecnología y compara su puntuación con organizaciones como la de su organización. Este mes presentamos los siguientes conceptos nuevos para la experiencia de vista previa:

- Vista de tendencias de información principal en las páginas principales y de detalles de categorías:Endpoint Analytics y las categorías de conectividad de red agregadas a la experiencia de tecnología
- Información relevante sobre la experiencia tecnológica que se muestra en las categorías de experiencia del empleado
- Nueva categoría de comunicaciones como parte de la experiencia del empleado
- Detalles de usuario con metadatos de la organización en categorías de experiencia del empleado

Si quiere obtener más información, consulte el blog: Medir y mejorar la experiencia de [Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/measure-and-improve-the-microsoft-365-experience-with-microsoft/ba-p/1348618)con la puntuación de productividad de Microsoft. La puntuación de productividad se encuentra actualmente en versión preliminar privada. [Únase a la vista previa privada de la puntuación de](https://aka.ms/productivityscorepreview) productividad para empezar.

### <a name="groups-updates"></a>Actualizaciones de grupos

Tenemos dos actualizaciones para Grupos este mes:

- Ahora puede editar las direcciones de correo electrónico de los grupos de Office 365 (también conocidos como grupos en Outlook y que pronto se conocerán como grupos de Microsoft 365).
- Hemos escuchado sus comentarios y hemos agregado mensajes de error más claros para saber por qué no puede convertir un grupo en un equipo de Microsoft.

### <a name="docs-videos-and-training-april"></a>Documentos, vídeos y aprendizaje (abril)

Novedades de la serie de vídeos de **Microsoft 365:** este mes, tratamos sugerencias y recursos para ayudar a las pequeñas empresas a realizar la transición al trabajo remoto, incluida la implementación de Microsoft Teams, los recursos de formación para el trabajo remoto para mantenerse conectados con clientes y partners, y el nuevo plan de Microsoft 365 Business Voice. [Novedades de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

#### <a name="for-your-users"></a>Para los usuarios

- [Programar una reunión](https://support.microsoft.com/office/c61b4f61-ee62-4a06-8bf7-0a1cd302700a)
- [Unirse a una reunión de Teams](https://support.microsoft.com/office/078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [Crear un equipo de toda la organización](https://support.microsoft.com/office/037bb27a-bcc9-48fe-8d72-44d9482420a3)
- [Crear un equipo con invitados](https://support.microsoft.com/office/11fbb083-52ee-434d-8c6e-63711fdafac7)
- [Unirse a un equipo como invitado](https://support.microsoft.com/office/928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Crear una dirección de correo electrónico del grupo](https://support.microsoft.com/office/ded875f9-a9de-437f-b559-2ae4f235bb2b)

#### <a name="for-admins-and-business-owners"></a>Para administradores y propietarios de empresas

- [Dar poder a su pequeña empresa con el trabajo remoto](https://support.microsoft.com/office/9b91a85a-39b4-40a6-a590-0f9bea0ba8e6)
- [Ejecutar una pequeña empresa remota](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Registrarse en Microsoft Business Basic](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Configuración del inicio de sesión en dos factores](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)

## <a name="march-2020"></a>Marzo de 2020

### <a name="featured-feedback-fix-improve-add-user-reliability-for-licensing"></a>Corrección de comentarios destacados: mejorar la confiabilidad de "agregar usuario" para licencias

Recibimos una gran cantidad de comentarios de los administradores sobre lo difícil que es asignar licencias al agregar usuarios. Hemos realizado la primera actualización de esta corrección y hemos migrado a un servicio en segundo plano más confiable para procesar esas solicitudes. Y si algo va mal, ahora verá un mensaje de error que le permite intentarlo de nuevo.

![Agregue la página de confirmación del usuario con el error.](../media/MAC-WN-ImprovedLicensing.png)

### <a name="microsoft-teams-home-page-card"></a>Tarjeta de página principal de Microsoft Teams

Con el uptick en el uso de Teams, algunas organizaciones recibirán una tarjeta de panel anclada que hace que la activación de Teams sea más reconocible. La tarjeta también tiene vínculos a cursos de aprendizaje y documentos para ayudar a su organización a realizar la transición al trabajo remoto. Solo tiene que ir a **la página** principal para ver la nueva tarjeta.

![Tarjeta de página principal de Microsoft Teams](../media/MAC-WN-TeamsCard.PNG)

### <a name="customize-your-organizations-sharepoint-mobile-app-theme"></a>Personalizar el tema de la aplicación móvil de SharePoint de su organización

Con el Centro de administración de Microsoft 365, ahora puede personalizar el tema de su organización en la aplicación móvil de SharePoint para iOS y la aplicación móvil de SharePoint para Android. Esta característica proporciona cómodamente una experiencia de aplicación de intranet móvil que puede coincidir con SharePoint Online para los empleados en cualquier lugar. La personalización del tema incluye la imagen del logotipo, el color de la barra de navegación, los colores de texto e icono, y los colores de énfeño, lo que facilita el reconocimiento.

![Diagrama que asigna la configuración del centro de administración a la aplicación móvil.](../media/MAC-WN-CustThemeSP.png)

### <a name="improvements-to-the-add-a-group-wizard"></a>Mejoras en el asistente para agregar un grupo

Cuando los administradores crearon un nuevo grupo y lo hicieron un equipo al mismo tiempo, podían asignar propietarios que no tienen una licencia que incluya Teams. Y eso creó algunos quebrabras de cabeza. Hemos actualizado el flujo del asistente para comprobar que los propietarios tienen una licencia de Teams y si no tienen la opción de convertir el grupo en un equipo está deshabilitado.

### <a name="microsoft-365-offerings-for-small-and-medium-businesses"></a>Ofertas de Microsoft 365 para pequeñas y medianas empresas

Sabemos que se trata de un anuncio para el próximo mes, pero queremos asegurarnos de que está preparado.

A partir del 21 de abril, estamos realizando cambios relacionados con nuestras suscripciones de Office 365 para pequeñas y medianas empresas y con Office 365 ProPlus. Estos productos ahora usarán la marca Microsoft 365.

Los nuevos nombres de producto entrarán en vigor el 21 de abril de 2020. Este es un cambio solo en el nombre del producto y no hay ningún cambio de precios o características en este momento.

|Nombre actual |Nuevo nombre  |
|---------|---------|
|Office 365 Empresa Essentials     |   Microsoft 365 Empresa Básico      |
|Office 365 Empresa Premium     |    Microsoft 365 Empresa Estándar     |
|Microsoft 365 Empresa     |    Microsoft 365 Empresa Premium     |
|Office 365 Empresa     |    Aplicaciones de Microsoft 365 para negocios       |
|Office 365 ProPlus    |   Aplicaciones de Microsoft 365 para empresas      |

### <a name="videos-training-and-docs"></a>Vídeos, cursos y documentos

Novedades de la serie web de [Microsoft 365:](https://go.microsoft.com/fwlink/p/?linkid=2118096)en el episodio de este mes, destacamos el aniversario de 3 años de Microsoft Teams y abarcamos nuevas características, como la calidad de audio mejorada en las reuniones en línea, las comunicaciones dirigidas para los administradores de primera línea con la aplicación Turnos, la interoperabilidad de los consumidores de Teams y Skype, y mucho más.

## <a name="february-2020"></a>Febrero de 2020

### <a name="featured-feedback-fix-multi-organization-switcher"></a>Corrección de comentarios destacados: conmutador de varias organizaciones

Recibimos una gran cantidad de comentarios de partners y administradores sobre los desafíos de administrar varias organizaciones en la nube de Microsoft. Una de nuestras primeras características de administración multi org es el conmutador de **organización,** que le permite cambiar entre las organizaciones que administra en tan solo 2 clics.
> [!TIP]
> No tiene que hacer nada para que el conmutador de organización aparezca siempre que sea el partner de registro de al menos una organización.

1. En el Centro de administración de Microsoft 365, seleccione el nombre de la organización.
![Captura de pantalla: en la parte superior de la página principal que muestra el nombre del perfil de la organización con el icono de conmutador.](../media/MAC-Organization-switcher.png)

2. En el conmutador de organización, seleccione la organización que desea administrar.
![Captura de pantalla: Conmutador de inquilinos de Mis organizaciones con el inquilino Consolidated Messenger resaltado](../media/MAC-OrgSwitcherSelected.png)

Eso es literalmente!!!

### <a name="groups"></a>Grupos

Un par de cambios en el área de grupos este mes:

- **Ordenar por nombre de grupo:** puede ordenar la lista de grupos alfabéticamente, seleccionando la columna **Nombre de** grupo.
- **Restaurar grupos de Microsoft 365** eliminados: ya no tiene que ir al Centro de administración de Exchange para restaurar los grupos de Microsoft 365 eliminados. Vaya a Grupos eliminados del Centro de administración de **Microsoft 365** \>  \>  \> (seleccione un grupo de la lista) \> **Restaurar grupo.** Restaurará el grupo a  la lista de grupos y restaurará el correo electrónico, las conversaciones, el bloc de notas, los archivos y el calendario del grupo.

### <a name="videos-training-and-docs-february"></a>Vídeos, cursos y documentos (febrero)

- Novedades de la serie de vídeos de **Microsoft 365:** este mes, nos centramos en las capacidades de búsqueda personalizadas para SharePoint Online, la característica de administración "Novedades" de Office que le permite mostrar u ocultar características específicas de los usuarios finales a través del panel de ayuda desde la aplicación, las últimas actualizaciones de seguridad y cumplimiento de Yammer y mucho más. Este es el último episodio: [Novedades de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

- **Movimiento de documentos:** combinamos los artículos web de administración de Office 365 con el contenido de Microsoft 365 y es posible que haya observado la nueva dirección URL. Por ejemplo, este artículo se solía hospedar en: **docs.microsoft.com/Office365/Admin/whats-new-in-preview**, pero la dirección URL es ahora: **docs.microsoft.com/microsoft-365/admin/whats-new-in-preview**. Si ha marcado páginas, debe actualizar los vínculos; sin embargo, los vínculos de contenido se redirigirán al nuevo repositorio de contenido.

## <a name="january-2020---happy-new-year"></a>Enero de 2020: Feliz año nuevo

> [!NOTE]
> ¿Sabe que hay una serie de vídeos de [Novedades de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096) en YouTube? Destaca las características más recientes que hemos lanzado a los usuarios. Cada mes, empezaremos a vincular al último episodio de la sección [Vídeos, aprendizaje y documentos.](#videos-training-and-docs) <br> <br> Este es el último episodio: [Novedades de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

### <a name="dark-mode"></a>Modo oscuro

Cuando se lanzó el modo oscuro por primera vez, solo estaba disponible en la página principal. El modo oscuro ya no está en versión preliminar y está en versión dirigida en la mayoría de las páginas del centro de administración.

1. En primer lugar, tendrá que activar La versión dirigida: Vaya **a** Configuración configuración de las preferencias de versión de \>  \> **perfil de** \> **la organización.**
1. Y, a continuación, para activar el modo oscuro, ve a **la** página principal y, a continuación, selecciona el **botón Modo** oscuro. (Está junto al **campo** De búsqueda y este artículo es el vínculo **Novedades).**
1. Para cualquier página que tenga el modo oscuro disponible, el botón está en la parte superior de la página, junto al nuevo botón de alternancia **del centro de administración.**

### <a name="office-whats-new-management"></a>Administración de novedades de Office

Los administradores quieren controlar cómo Microsoft comunica "Novedades" a sus usuarios en las aplicaciones de Office y ahora tiene ese control. Vaya a **Configuración** \> **de Office Novedades de la vista previa de administración.** Seleccione una característica para ver sus detalles  y, a continuación, puede seleccionar el botón Ocultar a los usuarios si no desea que los usuarios vean un mensaje "novedades" determinado. Por ejemplo, es posible que su organización esté esperando que los usuarios conozcan una característica hasta que todos los miembros de su organización se entren en ella.

![Captura de pantalla de la vista previa novedad de Office con el panel de detalles de una característica abierto.](../media/whatsnew-officemgmt-preview.png)

Esta característica se publicó por primera vez en versión preliminar en noviembre, pero ha habido algunas actualizaciones de características que debería conocer: las actualizaciones de vista previa de administración de [Novedades](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-preview/ba-p/1020438) de Office ahora están disponibles

### <a name="partners"></a>Asociados

Howdy, Partners! (No se pudo ayudar a mí mismo). We've got an update for you this month, as well. Hay una nueva característica que permite a los partners ofrecer a los clientes de  CSP la opción de aceptar su Contrato de cliente de Microsoft (MCA) en la sección Cuentas de facturación del centro de administración. En esta nueva experiencia:

1. El cliente recibe un correo electrónico de invitación con un vínculo para aceptar la relación de partner y el MCA.
2. Después de que el cliente inicia sesión, puede ver y aceptar los permisos de MCA y partner, directamente desde el centro de administración.

### <a name="resource-mailboxes"></a>Buzones de recursos

La lista de buzones de recursos se ha actualizado al nuevo estilo. En el Centro de administración de Microsoft 365, vaya **a** Salas \> **de & equipo.**

### <a name="videos-training-and-docs-january"></a>Vídeos, cursos y documentos (enero)

Echa un vistazo a la formación para administradores de pequeñas empresas que lanzamos en enero:

- [Crear un sitio web empresarial](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)
- [Encontrar respuestas y ayuda](https://support.microsoft.com/office/7f681212-c649-4a3e-a43b-32b1d1e58988)
- [Obtener ayuda o soporte técnico](https://support.microsoft.com/office/18948a4c-3eb1-4b30-b1bc-a4cc29eb7655)
- [Eliminar un usuario](https://support.microsoft.com/office/6bcdad7b-732a-4260-997a-8c176bc3d9d6)
- [Elegir una suscripción de Microsoft](https://support.microsoft.com/office/b9f7c78e-430f-4117-89ec-2eeb1dced2ca)
- [Introducción a la seguridad de Microsoft 365 para empresas](https://support.microsoft.com/office/3274b159-a825-46d7-9421-7d6e209389d1)

## <a name="november-and-december-2019"></a>Noviembre y diciembre de 2019

Estamos combinando las noticias de noviembre y de diciembre porque después de Ignite tenemos muy pocos anuncios que hacer. Nos vemos en el año nuevo.

### <a name="change-from-credit-card-to-invoice-payment"></a>Cambiar de tarjeta de crédito a pago facturado

Hemos empezado a implantar la capacidad de cambiar el método de pago de una tarjeta de crédito a una factura. Vaya  a \> **Facturación de sus productos,**  seleccione una suscripción y, a continuación, seleccione el vínculo Editar junto al pago con tarjeta de crédito.

![Captura de pantalla: sección de facturación de la tarjeta de suscripción con una tarjeta de crédito como método de pago.](../media/MAC-BillingEditCreditCard.png)

¿Desea obtener más información sobre esto? [Cambiar de tarjeta de crédito o cuenta bancaria a factura](../commerce/billing-and-payments/change-payment-method.md)

### <a name="global-reader"></a>Lector global

Mencionamos el rol de lector global en la edición octubre [de 2019 - Ignite,](#october-2019---ignite-edition)pero a medida que se está implementando de forma más amplia, vamos a analizar algunos detalles:

- El rol lector global es el equivalente de solo lectura del rol de administrador global. El lector global puede ver todo lo que el administrador global tiene permiso para hacer.
- Con algunas excepciones, como algunas características de cumplimiento y seguridad, los lectores globales tienen acceso para ver todos los centros de administración en la nube de Microsoft que su organización tiene licencia para usar.
- Asigne el rol de lector global a los usuarios que lo necesiten para la planeación, las auditorías y las investigaciones.
- También puede combinar el rol de lector global con otro rol que tenga menos permisos. Por ejemplo, un propietario de pequeña empresa podría tener asignados los roles de lector global de administrador de facturación para que puedan pagar las facturas y mantenerse al día de los cambios en  +   su organización en la nube.
- Los lectores globales pueden ir a cualquier página en el Centro de administración de Microsoft 365. Cuando abran una página editable, habrá una advertencia en la parte superior en la que se les mostrará que no tienen permiso para guardar los cambios y se deshabilitará el botón Guardar.

Nos encantaría recibir sus comentarios sobre el rol de lector global y cualquiera de los permisos basados en roles que le gustaría ver en el futuro. [Enviar comentarios sobre permisos basados en roles](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/10115430-have-a-consistent-experience-when-assigning-admin)

### <a name="new-settings-page"></a>Página Nueva configuración

El **perfil de** organización, la seguridad  **&** privacidad y las páginas & complementos de servicios se han combinado en una sola página con 3 pestañas verticales. Y la mejor parte: desde una sola ubicación, ahora puede buscar toda la configuración.
![Captura de pantalla: página de configuración con el campo "Buscar en toda la configuración" resaltado en la parte superior de la página.](../media/MAC-SettingsMultiPivotSearch.png)

### <a name="training--docs"></a>Documentación & aprendizaje

Esta sección es una nueva característica de este artículo, donde empezaremos a vincular a la nueva formación y documentación que creemos que le interesará.

En noviembre, lanzamos varias rutas de aprendizaje en el sitio web de [Microsoft Learn](https://docs.microsoft.com/learn/) para ayudar a los profesionales de TI a obtener información sobre Microsoft 365 y recibir formación sobre él. Echa un vistazo a ellos:

- [Aspectos básicos de Microsoft 365](https://docs.microsoft.com/learn/paths/m365-fundamentals/)
- [Ampliar los aspectos básicos de Office](https://docs.microsoft.com/learn/paths/extend-office-fundamentals/)
- [Microsoft 365: modernizar la implementación empresarial con Windows 10 y Aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/learn/paths/m365-getmodern/)
- [Administre el despliegue de su empresa con Microsoft 365](https://docs.microsoft.com/learn/paths/manage-enterprise-deployment-m365/)
- [Actualice Microsoft Office para la TI a escala](https://docs.microsoft.com/learn/paths/m365-office-for-it/)
- [Entregar aplicaciones y escritorios remotos desde Azure con Windows Virtual Desktop ](https://docs.microsoft.com/learn/paths/m365-wvd/)
- [Modernice su área de trabajo con Microsoft 365 y Surface para la Empresa](https://docs.microsoft.com/learn/paths/modernize-workplace-with-m365-and-surface/)
- [Proteger la identidad y el acceso con Microsoft 365](https://docs.microsoft.com/learn/paths/m365-identity/)
- [Proteger la información de la empresa con Microsoft 365](https://docs.microsoft.com/learn/paths/m365-information-protection/)
- [Administrar la seguridad con Microsoft 365](https://docs.microsoft.com/learn/paths/m365-security-management/)
- [Defenderse contra amenazas con Microsoft 365 Defender](https://docs.microsoft.com/learn/paths/m365-security-threat-protection/)
- [Administración de la colaboración en grupo con Microsoft Teams](https://docs.microsoft.com/learn/paths/m365-manage-team-collaboration/)
- [Colaborar con SharePoint en Microsoft 365](https://docs.microsoft.com/learn/paths/m365-teams-sharepoint/)

## <a name="october-2019---ignite-edition"></a>Octubre de 2019 - Ignite Edition

Bienvenido a la edición Ignite de las novedades del Centro de administración de Microsoft 365. Por supuesto, no se trata de una lista completa de anuncios, pero estos son algunos aspectos destacados. Además, echa un vistazo a los blogs de Ignite para obtener más información sobre las versiones:

- [ADMIN: mejoras de seguridad, productividad y red para Microsoft 365.](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/ADMIN-Security-Productivity-and-Network-Enhancements-for/ba-p/964019)
- [Novedades de Microsoft Teams - Ignite 2020](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-New-in-Microsoft-Teams-Ignite-2019/ba-p/937025).

### <a name="role-based-access-control"></a>Control de acceso basado en funciones

Ha habido una gran cantidad de cambios para roles en el centro de administración desde que empezamos a implementar en junio:

- **Comparar roles:** seleccione hasta 3 roles para comparar los permisos de cada uno. Esto le ayudará a encontrar el rol menos permisivo que se asignará a los usuarios. Vaya a **Roles**, use la casilla de selección múltiple en la primera columna para elegir hasta 3 roles y, a continuación, **seleccione Comparar roles.**

    ![Comparación de los roles de administrador de Exchange, administrador del departamento de soporte técnico y administrador de usuarios.](../media/RBAC-CompareRoles.png)

- Favoritos: puedes agregar una estrella a tus roles favoritos o más **usados,** para que puedas encontrarlos fácilmente ordenando la columna o creando un filtro.
- **Usuarios activos**  >  **Administrar roles:** se ha actualizado para que se alinee con los cambios en Roles. Al igual que con la lista roles, hemos limitado la lista predeterminada de roles a la más útil, pero puede ver todos los roles expandiendo Mostrar todo **por categoría.**
- **Rol de lector global:** lo ha solicitado. ¡Lo tienes! El [rol lector](add-users/about-admin-roles.md) global.

### <a name="report-an-issue"></a>Informar de un problema

El estado del servicio se ha actualizado al nuevo estilo y, si se ve afectado  por un problema que no aparece en el panel de estado del servicio, puede informar de un problema para informar a Microsoft. Vaya al **estado del** servicio  >  **de mantenimiento.**

### <a name="viral-subscriptions"></a>Suscripciones "Desc".

Como ya sabe, los usuarios pueden activar suscripciones gratuitas para una gran cantidad de productos como Power BI y App Connect. Ahora puede ver las "suscripciones de suscripción" que los usuarios han estado intentando. Vaya a  >  **Facturación de sus productos.** Selecciona el **filtro de tipo de** cuenta en la pestaña suscripciones para ver las suscripciones compradas por el usuario. Si es necesario, ahora tienes la capacidad de quitar estas suscripciones de tu cuenta.

### <a name="user-templates"></a>Plantillas de usuario

Las plantillas le permiten agregar fácilmente muchos usuarios guardando y reutilizando la configuración compartida para estos usuarios. Puede guardar valores para roles, licencias asignadas, información de contacto, ubicación y mucho más. Cuando se usa la plantilla para crear un nuevo usuario, se obtiene automáticamente el valor guardado para esta configuración. Vaya a **Usuarios**  >  **activos y,** a continuación, seleccione **Plantillas de usuario** para probarlo.

### <a name="office-whats-new-management-preview"></a>Administración "Novedades" de Office (versión preliminar)

Cuando se lanza una característica importante de Office en una aplicación de Office, los usuarios recibirán una tarjeta "Novedades" para obtener información sobre la nueva característica. Si no desea que los usuarios vean la tarjeta, puede ocultarla. También puedes elegir cuándo quieres que los usuarios vean la tarjeta mostrándole. Vaya a **Configuración** de la administración de Novedades  >  **de Office** para des consultarlo.

### <a name="sharepoint-url-change"></a>Cambio de dirección URL de SharePoint

Técnicamente, esta no es la novedad del Centro de administración de Microsoft 365, pero estamos muy contentos de que quisiesemos asegurarnos de que ves estas noticias:
> [!IMPORTANT]
> Ahora puede acceder al Centro de administración de SharePoint con una dirección URL normal: [https://admin.microsoft.com/SharePoint](https://admin.microsoft.com/SharePoint)

Para obtener más información, vea [Novedades en el Centro de administración de SharePoint.](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)

## <a name="september-2019"></a>Septiembre de 2019

We are ramping up for some exciting feature releases at Ignite 2019, so we're only announcing a few new features that were released in September. Pero manténgase atento al artículo del mes que viene, se publicará el primer día de Ignite.

### <a name="featured-feedback-fix--the-option-to-convert-the-deleted-users-mailbox-to-a-shared-mailbox-is-back"></a>Corrección de comentarios destacados: se ha vuelto a la opción de convertir el buzón del usuario eliminado en un buzón compartido

Hemos escuchado sus comentarios en voz alta y clara y hemos vuelto a ofrecer a otra persona acceso al buzón de un usuario eliminado al convertirlo en un **buzón compartido.** Agregar esto de nuevo al asistente para eliminar usuarios le permite decidir qué hacer con los datos:

- Correo electrónico: para que otra persona obtenga acceso al buzón del usuario eliminado, conviéndolo en un buzón compartido.
- Archivos: guarde sus archivos de OneDrive y dé acceso a otra persona.
- Permisos: quite los permisos si otros usuarios tenían acceso a este buzón.
- Alias: quite los alias de correo electrónico para que estén disponibles para su uso inmediato para otro usuario.
![Captura de pantalla: Asistente para eliminar usuario con alias de correo electrónico, permisos, OneDrive y opciones de correo electrónico mostradas](../media/WhatsNew-DeleteUserWiz.png)

### <a name="initial-setup"></a>Configuración inicial

Ha habido una actualización de otro de nuestros asistentes de configuración inicial: Microsoft 365 para empresas. Los pasos se han simplificado y hemos movido dos de las tareas de configuración a la página de instalación:

- **Proteger equipos con Windows 10:** configura directivas para proteger mejor tus dispositivos Windows 10 de virus, malware y ataques de hackers.
- **Instalar Office** automáticamente: cuando se activa y los usuarios conectan sus equipos a Microsoft 365 Empresa, sus equipos se actualizarán automáticamente a las aplicaciones de Office más recientes y se mantendrán actualizados.

## <a name="august-2019"></a>Agosto de 2019

### <a name="billing"></a>Facturación

Este mes tenemos algunas actualizaciones de facturación y suscripciones:

- Suscripciones basadas en dispositivos: puede asignar o desasignir licencias de Aplicaciones de **Microsoft 365** para educación (dispositivo) a dispositivos en el Centro de administración de Microsoft 365. **Aplicaciones de Microsoft 365** para educación (dispositivo) es una licencia de complemento que le permitirá asignar una licencia a un dispositivo. Vaya a  >  **Facturación de sus productos** para buscar y comprar la licencia.
- Administración de licencias basadas en usuarios: hemos actualizado cómo asignar licencias en Usuarios  >  **activos a** un nuevo estilo. Para obtener más información, vea:
  - [Asignar licencias a usuarios](manage/assign-licenses-to-users.md)
  - [Cancelar asignación a licencias de usuarios](manage/remove-licenses-from-users.md)

### <a name="setup-page-updates"></a>Actualizaciones de la página de instalación

El programa de instalación ahora  tiene categorías y secciones, incluida una sección Recomendada para usted en la que sugerimos de forma inteligente el siguiente paso para activar las características y configurar la organización. También hemos agregado una nueva característica para configurar:

- **Microsoft Defender para Office 365:** si su organización tiene licencia para usar Microsoft Defender para Office 365 y aún no la ha configurado o activado, verá esta página. Vaya al **programa de** instalación para probarlo.

### <a name="report-an-issue-august"></a>Notificar un problema (agosto)

Si se ve afectado por un problema que no aparece  en el panel de estado del servicio, la característica Informar de un problema le proporcionará una forma rápida y sencilla de informarnos. Vaya al **estado del** servicio  >  **de mantenimiento.**

## <a name="july-2019"></a>Julio de 2019

### <a name="message-center"></a>Centro de mensajes

El Centro de mensajes se ha actualizado al nuevo diseño y tiene un aspecto increíble.

![Captura de pantalla: Centro de mensajes actualizado con la pestaña "Todos los mensajes activos" seleccionada y el menú Filtro abierto.](../media/MAC-MessageCenterUpdated.png)

- Ahora puede ver mensajes **por estado.** Solo tiene que seleccionar una de las pestañas: **Todos los mensajes** activos , Alta **importancia**, **Mensajes no** leídos y **Mensajes descartados.**
- También puede filtrar por categoría Privacidad de **datos**, **Planear** el cambio, Evitar o **corregir problemas** y Mantener **informadas** las categorías de mensajes.
- Seleccione un mensaje de la lista y tiene algunas opciones en la barra de comandos: **Descartar** **,** Marcar como leído o Marcar como **no** leído o **Compartir.**
- Y cuando abre un mensaje, tiene aún más opciones:
  - Copie un vínculo del mensaje en el Portapapeles para guardarlo más tarde o para compartirlo con sus compañeros.
  - Marcar mensajes como **leídos** **o no leídos.**
  - Envía comentarios sobre un  mensaje seleccionando Me gusta o No me gusta **,** se abre un panel de comentarios que te pide que proporciones comentarios específicos sobre lo que te gusta o no te gusta sobre este mensaje.

### <a name="navigation-pane-intelligence"></a>Inteligencia del panel de navegación

 El panel de navegación ahora recuerda las últimas acciones y muestra el panel en el último estado en el que lo dejó. También hará que los elementos usados con frecuencia sean visibles de forma predeterminada.

### <a name="initial-setup--the-setup-page"></a>Configuración inicial & página de instalación

Tenemos algunos cambios interesantes que le ayudarán a configurar su organización. En primer lugar, vamos a analizar la diferencia entre **el programa de instalación** y la página de **instalación.** **El** programa de instalación hace referencia al asistente de configuración inicial que usó para incorporarse a los servicios en línea de Microsoft. Normalmente, esto incluye tres pasos específicos: **Conectar un dominio,** **Agregar usuarios** y Descargar las aplicaciones de **Office.** La **página** de instalación es la página del centro de administración que ha recomendado configurar tareas para asegurarse de que está sacar el máximo partido a sus suscripciones, como activar las características para las que ha comprado licencias.

- **Instalación:** se ha actualizado el asistente de configuración inicial para las suscripciones de **Microsoft 365 para** empresas. Este nuevo diseño ayudará a las nuevas organizaciones a pasar por el asistente con mayor rapidez y éxito.
- **Página de instalación:** la **página de** instalación le ayuda a terminar de configurar y proteger los servicios que vienen con las suscripciones. También puede ver las recomendaciones descartadas en la **página de** instalación. Para ver si está disponible para sus suscripciones todavía, vaya a la configuración del Centro de administración de **Microsoft 365.**  >  

### <a name="billing--subscriptions"></a>Facturación & suscripciones

- **Tipo** de producto de software: ahora puedes ver los productos de software comprados a través de un proveedor de servicios en la nube (CSP). Para ver las descargas y las claves, vaya a **Facturación**  >  **de la pestaña** Software  >  **de** sus productos.
- Puede ver los productos y servicios modernos de Azure desde el Centro de administración de Microsoft 365, independientemente de si los compró a Microsoft o a un proveedor de terceros. Ejemplos de productos modernos de Azure incluidos:
  - Instancias virtuales reservadas de Azure
  - Planes de soporte técnico de Azure
  - Ventajas de uso híbrido de Azure (AHUB)
  - Administrar aplicaciones
  - Servicios de dispositivos
  - Suscripciones de Azure

### <a name="simplify-multi-factor-authentication"></a>Simplificar la autenticación multifactor

Los administradores tienen acceso a información confidencial en su organización. Requerir que todos los administradores usen la autenticación multifactor al iniciar sesión. El nuevo asistente le ayuda a hacerlo con un solo paso. To try it out, go to **Setup**  >  **Strengthen sign-in security**.

### <a name="users"></a>Usuarios

Las **páginas Usuarios eliminados** **y Usuarios invitados** se actualizaron al nuevo estilo.

- **Usuarios invitados:** puede agregar usuarios invitados invitándolos a ver o compartir archivos desde SharePoint o OneDrive. Puede ver usuarios invitados de **usuarios**  >  **invitados.**
- **Usuarios eliminados:**  en la página usuarios eliminados actualizada, puede realizar todas las acciones que pudiera en el centro de administración anterior, pero ahora agrega y quita columnas. Y tenemos muchas opciones de columna entre las que elegir. De hecho, son las mismas columnas que puede elegir en la **página Usuarios activos.**

## <a name="june-2019"></a>Junio de 2019

### <a name="featured-feedback-request---dark-mode"></a>Solicitud de comentarios destacados: modo oscuro

Ver el centro de administración en modo oscuro está en versión preliminar. Solo puede probarlo en la **página** principal en este momento. En la **página** principal, el **botón Modo** oscuro está en la barra de comandos junto al **vínculo** Novedades.

### <a name="roles-management"></a>Administración de roles

A finales de junio empezamos a implementar una nueva forma de administrar roles de administrador. Cuando esté disponible, vaya a   >  **Roles.** Hasta entonces, echa un vistazo: ¡es fantástico!
<br> ![Captura de pantalla: lista de roles de administrador con el panel de detalles del rol de administrador de usuario resaltado.](../media/MAC-AdminRoles-Featured.png) <br>

Esta nueva experiencia facilita ver quién tiene permisos de administrador y asignar roles que conceden el nivel correcto de acceso a los administradores. Y también hemos agregado más roles de Azure AD para que no pierdas tiempo yendo a varios centros de administración.
¿Qué más puede hacer aquí?

- Exporte una lista de todos los administradores de su organización que tienen asignados roles de Azure Active Directory en Microsoft 365.  
- Ver todos los administradores asignados a un rol específico, agregar o quitar administradores de un rol específico, buscar roles por nombre y palabra clave, y obtener más información sobre lo que cada rol permite a un usuario hacer.
- Busque rápidamente un rol específico y cree filtros.

### <a name="payment-method"></a>Método de pago

Hemos actualizado cómo pagas las suscripciones. Vaya a **Facturación**  >  **de facturación & métodos de pago** de  >  **pagos.** Puede ver los métodos de pago en una vista de lista. Seleccione cualquier elemento de la lista para quitarlo, editarlo y ver fácilmente a qué suscripción está asociada ese método de pago.

## <a name="may-2019"></a>Mayo de 2019

### <a name="mays-featured-fix---case-sensitivity"></a>Corrección destacado de mayo: confidencialidad de mayúsculas y minúsculas

Ahora, cuando busca buzones compartidos, contactos, recursos y permisos de buzón, los términos de búsqueda no tienen que distinguen mayúsculas de minúsculas.

**Administración de usuarios y grupos** Este mes, actualizamos **Bloquear** **usuario,** Restablecer **contraseña,** Vista  de lista de **contactos,** Vista de lista de grupos y las páginas de detalles grupos al nuevo estilo del centro de administración.

- Con la nueva **vista** de lista grupos, obtiene datos más completos sobre los grupos y puede personalizar la forma en que ve los datos, y la lista de grupos recuerda cómo desea ver los datos. Por ejemplo, ahora puede filtrar por Grupos con **Teams** para ver si los grupos forman parte de un equipo y puede agregar la columna de estado **de Teams.**
- La lista de grupos también incluye todas las mejoras realizadas en la experiencia de lista en la administración de usuarios, incluidas las acciones rápidas y la barra de comandos contextual.

**Recomendaciones**<br>
You might see a new recommendation pop-up in your admin center - we just added 4 new ones. Por supuesto, solo verá recomendaciones si creemos que beneficiará a su organización. Pero no esperes hasta que te mostramos la recomendación: puedes agregarla desde la biblioteca de tarjetas.

- **Expiración de contraseña:** se recomienda que las contraseñas se establezcan en **No expirar nunca.** Y si su organización tiene una configuración diferente, es posible que solo vea esta recomendación.
- **Demasiados** administradores globales: dado que tener demasiados administradores globales es una amenaza para la seguridad, si tiene más de 4 administradores globales, verá esta recomendación. Se recomienda dar a los usuarios solo el acceso que necesitan para realizar su trabajo.
- **Protección** de dispositivos Intune: si las licencias incluyen Intune y detectamos que no has terminado de configurar Intune o has inscrito los dispositivos, te recomendamos que crees una directiva de Intune para proteger los archivos de la organización cuando los usuarios accedan a ellos desde sus dispositivos móviles.
- **Obtener actualizaciones mensuales** de características de Office: hemos recibido comentarios de nuestros clientes muy pequeños que cuando obtienen actualizaciones mensuales de características de Office, sus usuarios son agradables. Por lo tanto, si es una empresa muy pequeña y actualmente recibe las actualizaciones de características de Office cada seis meses, verá esta recomendación.

**Configuración** <br>
En cuanto a la configuración, se han realizado algunos cambios. Principalmente, solo se actualiza la configuración existente al nuevo estilo del centro de administración. A medida que avanzamos y agregamos nuevas opciones de configuración que nunca antes habías visto, empezaremos a mencionarlas aquí. Y tenemos una configuración completa para anunciar: **autenticación moderna.** Sí, hay una nueva configuración para activar la **autenticación moderna.** To check it out, go to **Settings**  >  **Services & add-ins**  >  **Modern authentication**.

## <a name="april-2019"></a>Abril de 2019

Las cosas están muy bien para el centro de administración. Hemos estado leyendo sus comentarios y sugerencias, respondiendo a la mayoría de ellos y realmente tomando todo lo que tiene que decir al corazón. Por supuesto, todavía estamos haciendo el trabajo para asegurarnos de que todo está en función de la paridad con el antiguo centro de administración. Recuerde que, a medida que se lanzan nuevas características, es posible que no la obtenga inmediatamente.

### <a name="featured-feature---add-users"></a>Característica característica: agregar usuarios

Para abril, presentamos el **Asistente** para agregar usuarios que le guiará a través de... espere por él... agregar usuarios. Es paso a paso agregar la información básica del usuario, como el correo electrónico y el nombre para mostrar, asignando una licencia y un rol, agregando su información de contacto y, a continuación, revisando la cuenta del usuario antes de confirmarlo. **¿Por qué hemos hecho este cambio?** Hemos escuchado sus comentarios que no le gusta el desplazamiento casi infinito para agregar usuarios en la experiencia anterior.
<br> ![Captura de pantalla del Asistente para agregar usuarios.](../media/MAC-AddUserWizard.png) <br>

Hay dos formas de des echar un vistazo: <br>

1. En la **página principal,** seleccione **Agregar usuario desde** la tarjeta de administración **de** usuarios. El asistente se abre aquí mismo, por lo que no tienes que navegar desde ningún trabajo que estés realizando en la **página** principal.
2. Vaya a **Usuarios**  >  **activos y,** a continuación, **seleccione Agregar usuario** en la barra de comandos.
<br><br>

Hemos realizado algunos cambios más en la administración de **usuarios,** esta es una lista rápida:

- El **panel Administrar roles** se ha actualizado al nuevo estilo y es accesible. También hemos actualizado los paneles  **Bloquear usuario** y Eliminar usuario al nuevo estilo.
- **Administrar la posición cambiada de** licencias de producto en la barra de comandos.
- Ahora es más fácil cambiar la foto de un usuario. En **Active, los** usuarios seleccionan un usuario y, a continuación, **cambian la foto** debajo de su imagen.

### <a name="but-wait-theres-more"></a>Pero espera. Hay más

- Hay un nuevo banner de  configuración en la página principal que verá si no ha terminado los pasos de configuración, como agregar un dominio, agregar usuarios y descargar las aplicaciones de Office.
- La **lista** de grupos y el panel de detalles se han actualizado al nuevo estilo. Vaya a **Grupos**  >  **para** ver los cambios.
  - Hablando de grupos, también hemos agregado una pestaña de **Microsoft Teams** al panel de detalles de grupos, donde puede convertir cualquier grupo de Microsoft 365 en un equipo. Para "agrupar" un grupo seleccione cualquier grupo de Microsoft 365 de la lista, seleccione la pestaña **Microsoft Teams** y, a continuación, **cree un equipo.** Si el grupo ya es un equipo, verá un vínculo para administrarlo desde el Centro **de administración de Teams.**
  - Por último, puede agregar el estado **de Teams** a la **lista de** grupos. En el encabezado de columna, seleccione **Elegir columnas Estado** de  >  **Teams**  >  **Guardar**.
- **Nuevos roles de administrador limitados:** hemos liberado algunos roles de administrador nuevos para que pueda dar a los usuarios solo el acceso que necesitan.
  - **Administrador de Kaizala:** los usuarios de este rol tienen permiso para realizar todas las tareas de administración dentro de Microsoft Kaizala, como crear y administrar usuarios en el directorio de Kaizala, administrar grupos de Kaizala, administrar tarjetas de acción y conectores y crear solicitudes de servicio.
  - **Administrador de búsqueda:** los usuarios de este rol tienen acceso completo a todas las características de administración de Búsqueda de Microsoft en el Centro de administración de Microsoft 365. Los administradores de búsqueda pueden delegar los roles de administrador de búsqueda y editor de búsqueda a los usuarios, y crear y administrar contenido, como marcadores, preguntas&Elementos A y ubicaciones. Además, estos usuarios pueden ver el centro de mensajes, supervisar el estado del servicio y crear solicitudes de servicio.
  - **Editor de** búsqueda: los usuarios de este rol pueden crear, administrar y eliminar contenido para Microsoft Search en el Centro de administración de Microsoft 365, incluidos marcadores, preguntas&Elementos A y ubicaciones.
- Hay una gran cantidad de **cambios** en la facturación este mes...
  - Ahora puede actualizar el CVV de las tarjetas de crédito existentes sin tener que eliminarlo y agregarlo de nuevo. Puede actualizar el CVV yendo a **métodos de**  >  **pago de facturas.**
    - Hemos hecho que sea más fácil localizar sus **facturas** y comprender los problemas de facturación que pueda tener su cuenta. Y ahora puede ver sus facturas en el explorador web en lugar de tener que descargar el PDF. Vaya a  >  **Facturas facturas.**
    - En la **página Sus productos,** ahora agregamos la información de la suscripción si tiene varias suscripciones del mismo tipo.

## <a name="march-2019---weve-officially-released-the-admin-center"></a>Marzo de 2019: Hemos publicado oficialmente el Centro de administración

Bueno, si se perdió las noticias interesantes, hemos lanzado oficialmente el nuevo y mejorado Centro de administración de Microsoft 365. Esta es la entrada de blog donde lo anunciamos: el nuevo Centro de administración de [Microsoft 365 disponible hoy.](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870) Para marzo, nos basaremos en la entrada de blog para que vea las características publicadas; además, también puede leer la publicación de las características que se van a publicar próximamente, lo cual no podemos hacer en el contenido principal.
<br> ![Captura de pantalla de la página principal del Centro de administración de Microsoft 365.](../media/M365AC-HomePage.png) <br>
Tenemos un cambio en  el área de suscripciones & facturación que nos gustaría mencionar. Es decir, no ha pensado que hemos terminado de mejorarlo, ¿verdad? ¡Porque no lo estamos haciendo! De hecho, este mes hemos agregado la capacidad de administrar las relaciones de partners a las cuentas **de**  >  **facturación de facturación.** Desde aquí, puedes revisar las relaciones de partners entre el Asesor, CSP y los revendedores indirectos. También puede aceptar nuevas solicitudes de relación de socio, incluidos los permisos de administrador delegado.

Como siempre, sus comentarios son importantes para nosotros, así que siga viniendo. En cualquier página del centro de administración,  puedes enviar comentarios seleccionando Enviar comentarios en la parte inferior derecha, junto **a ¿Necesitas ayuda?**

## <a name="february-2019---billing--subscriptions-edition"></a>Febrero de 2019: Facturación & Subscriptions Edition

Este mes, nos centraremos en todas las mejoras que hemos realizado en las áreas conocidas como "Facturación y suscripciones". En el pasado, probablemente no se refiría a esas cosas, pero creemos que lo hará ahora...

- **Métodos de** pago: hemos escuchado sus comentarios que la actualización de su método de pago era difícil y hemos realizado una gran cantidad de cambios en torno a él. Vaya a **Métodos de**  >  **pago de facturación.** Puede ver fácilmente los métodos de pago, como su tarjeta Visa, y con qué suscripción está asociada. En la lista de métodos de pago, selecciona el menú Más (3 pequeños puntos junto a la fecha de expiración) y, a continuación, **selecciona Ver suscripciones.**  También puedes editar y eliminar los métodos de pago mediante el **menú** Más.
- **Cuenta de facturación:** los clientes de la versión dirigida verán primero la nueva página de la cuenta de facturación y, a continuación, la publicaremos en todo el mundo. Cuando esté disponible para usted, vaya a la cuenta **de**  >  **facturación de facturación.** ¿Qué puede hacer en la página de la nueva cuenta de facturación? Me complace que hayas pedido:
  - Actualice la dirección y otra información de contacto del perfil de la organización directamente desde esta página. No tiene que ir al perfil **de** la organización de  >  **configuración,** a menos que lo desee.
  - Y estamos haciendo que la vida sea más fácil para los clientes de licencias directas o por volumen, puedes aceptar y revisar los contratos de cliente desde cuentas **de facturación.** También puede conectarse con otras organizaciones, lo que le permite vincular las organizaciones para compartir licencias y recursos.
- También hemos realizado algunas mejoras más pequeñas y correcciones de errores:
  - Reactivar una suscripción con un pago de factura
  - Editar la dirección de uso del servicio para las suscripciones
  - Y en la página Detalles del inventario, hemos agregado algunas mejoras de notificación, te vinculamos a la página real donde puedes realizar el trabajo y hay más acciones en la tarjeta de detalles del inventario. Vaya a Los **detalles de la**  >  **vista**  >  **Facturación** de facturación en cualquier factura.

## <a name="january-2019---happy-new-year"></a>Enero de 2019: Año nuevo feliz

- Aún agregando **servicios &** complementos: hemos actualizado más de las páginas De configuración **> servicios & complementos.** Pruebe los informes o aplicaciones integradas para ver la versión más reciente.
- **¿Está buscando mejoras?** No busque más que el **cuadro de** búsqueda en la barra de comandos. Se ha actualizado para que le permita buscar tareas. Por ejemplo, pruebe "restablecimiento de contraseña" o "agregar un usuario".

### <a name="featured-feedback-fix---licenses-and-apps"></a>Corrección de comentarios destacados: licencias y aplicaciones

Re combinamos licencias **y aplicaciones en** el panel de detalles del usuario en función de sus comentarios. Inicialmente separamos las dos características para proporcionar espacio para los detalles de todas las posibilidades de licencia y todas las aplicaciones. Nos hemos enterado de que separar licencias y aplicaciones en dos paneles agregó confusión. Escuchamos y hemos vuelto a reunir licencias y aplicaciones en una sola pestaña. Ahora puedes asegurarte de que una aplicación está desactivada en todas las licencias asignadas a un usuario en un panel. Anda y cookies. Licencias y aplicaciones. Lo tenemos ahora.

Descódalo: **los usuarios > usuarios activos** > editar o agregar aplicaciones y licencias de **>** usuario
