---
title: ¿Cuáles son las novedades del centro de administración de Microsoft 365?
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
description: 'Centro de administración de Microsoft 365: Obtenga información sobre las características que se agregaron este mes.'
ms.custom:
- MACDashWhatsNew
- AdminSurgePortfolio
ms.openlocfilehash: 11a48ecf78c09c8e597d94821f747bf6ebd7e444
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602014"
---
# <a name="whats-new-in-the-microsoft-365-admin-center"></a>Novedades en el centro de administración de 365 de Microsoft

::: moniker range="o365-21vianet"

> [!NOTE]
> Es posible que parte de la información de este artículo no se aplique a Office 365 operado por 21Vianet.

::: moniker-end

Estamos agregando de forma continuada nuevas características al [centro de administración de Microsoft 365](microsoft-365-admin-center-preview.md), solucionando los problemas que aprendemos y realizando cambios en función de sus comentarios. Eche un vistazo a la parte inferior para ver lo que está disponible hoy mismo. Algunas características se implementan a los clientes a velocidades diferentes. Si aún no ve una característica, [pruebe a agregarse a la versión dirigida](manage/release-options-in-office-365.md).

> [!IMPORTANT]
> **Retiro del centro de administración de "Classic" a partir de marzo**<br><br>
Al iniciar sesión en el centro de administración de 365 de Microsoft, ahora va al nuevo centro de administración cada vez. Y, en marzo, empezamos a deshabilitar la capacidad de volver al centro de administración clásico. Por ahora, puede cambiar de nuevo, pero a medida que el nuevo centro de administración se refiere a la paridad (y lo supera), desactivamos el conmutador para todas las organizaciones. <br><br> *Última actualización: 11 de mayo de 2020*

Y si quiere conocer las novedades de otros servicios en la nube de Microsoft:

- [Novedades de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/whats-new)
- [Novedades en el centro de administración de Exchange](https://docs.microsoft.com/Exchange/whats-new)
- [Novedades de Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/whats-new)
- [Novedades en el centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/whats-new)
- [Novedades de Protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)
- [Novedades en el centro de administración de SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)
- [Actualizaciones de Office](https://docs.microsoft.com/OfficeUpdates/)

## <a name="may-2020"></a>Mayo de 2020

### <a name="new-update-channel-for-office"></a>Nuevo canal de actualización para Office

El 12 de mayo, anunciamos la disponibilidad de un nuevo canal de actualización para Office: canal de empresa mensual. Este canal de actualización proporciona a los usuarios nuevas características de Office una vez al mes, el 2º martes del mes.

Si permite que los usuarios instalen Office automáticamente desde el portal, puede seleccionar el canal de empresa mensual para ellos. Para ello, inicie sesión en el centro de administración de Microsoft 365 y vaya a **Mostrar todas las**opciones de configuración de la organización de los servicios configuración de  > **Settings**  >  **Org settings**  >  **Services**  >  **descarga de software de Office**. Si selecciona una **vez al mes (el canal de empresa mensual)**, cualquier instalación nueva de Office se configurará para usar el canal de empresa mensual.

En combinación con la versión del canal de empresa mensual, también se revisan los nombres de los canales de actualización existentes. Por ejemplo, se cambia el nombre del canal mensual al canal actual. Los nuevos nombres entrarán en vigor el 9 de junio de 2020.

Para obtener más información, consulte [cambios en los canales de actualización de las aplicaciones de Microsoft 365](https://docs.microsoft.com/DeployOffice/update-channels-changes).

### <a name="new-admin-roles"></a>Nuevos roles de administrador

Hemos agregado algunos nuevos roles de administrador de Azure Active Directory al centro de administración de Microsoft 365.

- El rol de administrador de identidades híbridas concede permisos a los usuarios para administrar el aprovisionamiento de la nube y los servicios de autenticación.
- El rol de administrador de red permite a los usuarios administrar ubicaciones de red y revisar información sobre la red para el software de Microsoft 365 como aplicaciones de servicio.
- El rol administrador de impresoras concede permiso para administrar todos los aspectos de las impresoras y las conexiones de impresora.
- El técnico de la impresora es un subconjunto del rol de administrador de la impresora donde estos usuarios pueden registrar y anular el registro de impresoras, y actualizar el estado de la impresora.
Para obtener más información acerca de estos roles, consulte [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

### <a name="export-groups-list"></a>Exportar lista de grupos

Hemos oído de muchos administradores que necesitan compartir información sobre los grupos y su uso a personas que no tienen acceso a los centros de administración. Ahora puede exportar la lista de grupos a un archivo CSV con fines de auditoría, lo que significa que puede desechar el script de PowerShell antiguo. Para probarlo, **vaya a grupos**  >  **Groups**de grupos y, a continuación, seleccione **exportar grupos** en la barra de comandos.

### <a name="microsoft-365-solution-and-architecture-center"></a>Centro de soluciones y arquitectura de Microsoft 365

Este mes hemos lanzado un nuevo sitio [https://docs.microsoft.com](https://docs.microsoft.com) denominado [Microsoft 365 Solution and Architecture Center](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center), que reúne la orientación técnica que necesita para comprender, planear e implementar soluciones integradas de Microsoft 365 para colaboración segura y conforme. En este centro, encontrarás:

- Guía de la solución básica
- Soluciones de carga de trabajo y guía del escenario
- Ilustraciones de soluciones y arquitecturas (los pósteres!!!)
- Instrucciones específicas del sector
- Entidades de diseño de arquitectura empresarial

### <a name="docs-training-and-videos"></a>Documentos, cursos y vídeos

- **What's New in Microsoft 365 video series**: este mes, se describe la nueva experiencia de soporte en los centros de administración de seguridad y cumplimiento de Teams, la integración de Planner con el centro de mensajes y el nuevo diseño de vídeo 3X3 en Microsoft Teams. [Novedades de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)
- La página central de [ayuda del centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/) se actualizó para ayudarle a encontrar lo que necesita con mayor rapidez. Además, si echa el vistazo a esa página ahora, hemos agregado una tarjeta para informarle de las actualizaciones y los cambios importantes.

## <a name="april-2020"></a>Abril de 2020

### <a name="intune-roles-management"></a>Administración de roles de Intune

[Abril de 2020](#april-2020)

Bueno, lo hicimos. Hemos asumido el segundo paso hacia una experiencia de roles unificada y ahora puede administrar los roles de Intune en el centro de administración de Microsoft 365. También puede aprovechar características como la capacidad de buscar roles y ver permisos de roles. Esto significa que no necesita dos herramientas independientes para administrar funciones para Microsoft 365 e Intune. Al iniciar sesión en el centro de administración de 365 de Microsoft, verá que hay dos elementos dinámicos en la página roles, uno para Azure AD y otro para Intune.

![Página roles con la función dinámica de Intune seleccionada](../media/MAC-WN-IntuneRoles.png)

### <a name="sync-message-center-posts-to-planner"></a>Sincronizar las publicaciones del centro de mensajes con Planner

A partir de mayo, los administradores que estén en versión de destino empezarán a ver el botón "sincronización de Planner" en el centro de mensajes. Ahora puede realizar un seguimiento de los mensajes que necesiten acción, seleccionar el tipo de mensajes a los que desea realizar un seguimiento, asignar mensajes para realizar un seguimiento de las tareas y etiquetar los mensajes para una atención posterior.

[Unirse a la versión dirigida](manage/release-options-in-office-365.md) para empezar.

### <a name="need-help-launched-in-teams-admin-center--security-and-compliance-centers"></a>"¿Necesita ayuda?" Iniciado en el centro de administración de Microsoft Teams & centros de seguridad y cumplimiento

El centro de administración de Microsoft Teams, el centro de seguridad y el centro de cumplimiento ahora usan la misma sección "¿necesita ayuda?". característica que usa el centro de administración de Microsoft 365 para buscar ayuda y ponerse en contacto con el soporte técnico. Hemos recibido muchos comentarios de los administradores a los que quería el mismo nivel de ayuda y soporte técnico, y nos alegramos de llevarle el mismo. Pruébelo y envíenos sus comentarios.

#### <a name="need-chat"></a>¿Necesita chat?

Nuestros agentes de soporte técnico han estado trabajando desde casa mientras se siguen teniendo en cuenta los casos de clientes y limitaciones en el ancho de banda de Internet mientras trabajan desde casa pueden afectar a la calidad de las llamadas de los clientes. Para seguir teniendo la asistencia, hemos lanzado la opción de soporte de chat en vivo para los clientes comerciales en el centro de administración de Microsoft 365.

Al crear una solicitud de servicio, ahora verá chat como una opción, además del teléfono y el correo electrónico. Seleccione chat como el canal de comunicación preferido y cree la solicitud. Una vez que haya creado la solicitud, puede iniciar el chat cuando esté listo para chatear con los agentes de Microsoft.

### <a name="teams-updates"></a>Actualizaciones de Microsoft Teams

Con el mayor uso de Teams, hemos agregado algunas características para ayudarle a administrarlas.

- Una nueva tarjeta de recomendación en la Página principal del centro de administración muestra los usuarios que no han usado activamente Teams durante 30 días. Puede enviar a dichos usuarios un correo electrónico de aprendizaje para que los usuarios empiecen a usar Microsoft Teams.
- **Incorpore a los usuarios con Microsoft Teams**: vaya a **configuración** para ver una página nueva que le ayude a activar Microsoft Teams para los usuarios con licencia y permitir el acceso de invitado, de modo que pueda trabajar con clientes externos en Microsoft Teams.
- Una tarjeta de Microsoft Teams está ahora anclada a la Página principal de forma predeterminada. Muestra si Teams está activado y si se permite el acceso de invitado. También le permite comprobar el estado de configuración de los usuarios de Microsoft Teams recién licenciados y comprobar si los problemas de red pueden afectar a los usuarios de Teams.
- Por último, Teams es ahora un paso en el flujo de configuración inicial si ha adquirido una licencia que incluye a teams.

### <a name="productivity-score"></a>Puntuación de productividad

La puntuación de productividad ofrece información sobre cómo los usuarios usan los servicios en la nube de Microsoft y las experiencias tecnológicas que los admiten. La puntuación refleja el rendimiento de su organización con respecto a las medidas de experiencia de empleado y tecnología, y compara su puntuación con organizaciones como la suya. Este mes, presentamos los siguientes conceptos nuevos a la experiencia de vista previa:

- Vista de tendencia de la información principal de las páginas de página principal y de detalles de categorías-análisis de extremos y categorías de conectividad de red agregados a la experiencia tecnológica
- Información relevante sobre la experiencia tecnológica que se muestra en las categorías de experiencia de empleados
- Nueva categoría de comunicaciones como parte de la experiencia de los empleados
- Detalles del usuario con metadatos de la organización en categorías de experiencia del empleado

Si quiere obtener más información, consulte el blog: [medir y mejorar la experiencia de microsoft 365 con la puntuación de productividad de Microsoft](https://techcommunity.microsoft.com/t5/microsoft-365-blog/measure-and-improve-the-microsoft-365-experience-with-microsoft/ba-p/1348618). La puntuación de productividad está actualmente en versión preliminar privada. [Únase a la vista previa privada de la puntuación de productividad](https://aka.ms/productivityscorepreview) para empezar.

### <a name="groups-updates"></a>Actualizaciones de grupos

Tenemos dos actualizaciones para los grupos este mes:

- Ahora puede editar las direcciones de correo electrónico de los grupos de Office 365 (también conocidos como grupos en Outlook, y en cuanto se conoce como grupos de Microsoft 365).
- Hemos oído sus comentarios y hemos agregado mensajes de error más claros por los motivos por los que no puede convertir un grupo en un equipo de Microsoft.

### <a name="docs-videos-and-training-april"></a>Documentos, vídeos y formación (abril)

**Novedades de la serie de vídeos de 365 de Microsoft**: este mes, se incluyen sugerencias y recursos para ayudar a las pequeñas empresas a realizar la transición a un trabajo remoto, incluida la implementación de Microsoft Teams, los recursos de aprendizaje de trabajo remoto para estar conectados a clientes y socios, y el nuevo plan de voz empresarial de Microsoft 365. [Novedades de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

#### <a name="for-your-users"></a>Para los usuarios

- [Programar una reunión](https://support.microsoft.com/office/c61b4f61-ee62-4a06-8bf7-0a1cd302700a)
- [Unirse a una reunión de Microsoft Teams](https://support.microsoft.com/office/078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [Crear un equipo de toda la organización](https://support.microsoft.com/office/037bb27a-bcc9-48fe-8d72-44d9482420a3)
- [Crear un equipo con invitados](https://support.microsoft.com/office/11fbb083-52ee-434d-8c6e-63711fdafac7)
- [Unirse a un equipo como invitado](https://support.microsoft.com/office/928d1eef-61e2-49ec-b754-c2fe86b34824)
- [Crear una dirección de correo electrónico de grupo](https://support.microsoft.com/office/ded875f9-a9de-437f-b559-2ae4f235bb2b)

#### <a name="for-admins-and-business-owners"></a>Para administradores y propietarios de empresas

- [Permita que su pequeña empresa tenga trabajo remoto](https://support.microsoft.com/office/9b91a85a-39b4-40a6-a590-0f9bea0ba8e6)
- [Ejecución de una pequeña empresa remota](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Registrarse en Microsoft Business Basic](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)
- [Configurar el inicio de sesión en dos fases](https://support.microsoft.com/office/9ac1a0f1-789b-4143-b954-5821d5d89298)

## <a name="march-2020"></a>Marzo de 2020

### <a name="featured-feedback-fix-improve-add-user-reliability-for-licensing"></a>Revisión de comentarios destacados: mejorar la confiabilidad del "Agregar usuario" para las licencias

Hemos recibido muchos comentarios de los administradores sobre el grado de dificultad para asignar licencias al agregar usuarios. Hemos realizado la primera actualización de esta corrección y hemos migrado a un servicio de segundo plano más confiable para procesar esas solicitudes. Y si algo va mal, ahora recibirá un mensaje de error que le permitirá volver a intentarlo.

![Página de confirmación de adición de usuario con el error.](../media/MAC-WN-ImprovedLicensing.png)

### <a name="microsoft-teams-home-page-card"></a>Tarjeta de página principal de Microsoft Teams

Con el valor de arriba en el uso de Teams, algunos organizaciones recibirán una tarjeta de panel anclada que permite que los equipos de escritorio sean más detectables. La tarjeta también tiene vínculos a formación y documentos para ayudar a su organización a realizar la transición al trabajo remoto. Solo tiene que ir a la página **principal** para ver la tarjeta nueva.

![Tarjeta de página principal de Microsoft Teams](../media/MAC-WN-TeamsCard.PNG)

### <a name="customize-your-organizations-sharepoint-mobile-app-theme"></a>Personalizar el tema de la aplicación móvil de SharePoint de la organización

Con el centro de administración de 365 de Microsoft, ahora puede personalizar el tema de su organización en aplicación móvil de SharePoint para iOS y aplicación móvil de SharePoint para Android. Esta característica proporciona convenientemente una experiencia de la aplicación de intranet móvil que puede coincidir con SharePoint Online para los empleados en marcha. La personalización del tema incluye la imagen del logotipo, el color de la barra de navegación, los colores del texto y el icono y los colores de énfasis, lo que facilita el reconocimiento.

![Diagrama asignar la configuración del centro de administración a la aplicación móvil.](../media/MAC-WN-CustThemeSP.png)

### <a name="improvements-to-the-add-a-group-wizard"></a>Mejoras en el asistente "agregar un grupo"

Cuando los administradores crearon un nuevo grupo y lo convierten en un equipo al mismo tiempo, podrían asignar a los propietarios que no tienen una licencia que incluya a teams. Y eso ha creado algunos problemas. Hemos actualizado el flujo del Asistente para comprobar que los propietarios tienen una licencia de Teams y si no la opción para convertir el grupo en un equipo está deshabilitada.

### <a name="microsoft-365-offerings-for-small-and-medium-businesses"></a>Ofertas de Microsoft 365 para pequeñas y medianas empresas

Sabemos que se trata de un anuncio para el próximo mes, pero queremos asegurarnos de que está preparado.

A partir del 21 de abril, estamos realizando cambios relacionados con nuestras suscripciones de Office 365 para pequeñas y medianas empresas, y con Office 365 ProPlus. Estos productos usarán ahora la marca 365 de Microsoft.

Los nombres de producto nuevos entrarán en vigor el 21 de abril de 2020. Este es un cambio en el nombre del producto solamente y no hay cambios en los precios o las características en este momento.

|Nombre actual |Nuevo nombre  |
|---------|---------|
|Office 365 Empresa Essentials     |   Microsoft 365 Empresa Básico      |
|Office 365 Empresa Premium     |    Microsoft 365 Empresa Estándar     |
|Microsoft 365 Empresa     |    Microsoft 365 Empresa Premium     |
|Office 365 Empresa     |    Aplicaciones de Microsoft 365 para negocios       |
|Office 365 ProPlus    |   Microsoft 365 apps for Enterprise      |

### <a name="videos-training-and-docs"></a>Vídeos, formación y documentos

Novedades [de la serie web de microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096): en el episodio de este mes, destacamos el aniversario de 3 años de Microsoft Teams y cubren nuevas características que incluyen una mejor calidad de audio en las reuniones en línea, las comunicaciones dirigidas a los administradores de Firstline con la aplicación de turnos, la interoperabilidad de clientes de Microsoft Teams y Skype y mucho más.

## <a name="february-2020"></a>Febrero de 2020

### <a name="featured-feedback-fix-multi-organization-switcher"></a>Corrección de comentarios destacados: conmutador de varias organizaciones

Hemos recibido muchos comentarios de socios y administradores sobre los retos de administrar varios organizaciones en la nube de Microsoft. Una de las primeras características de administración multiempresa es el **conmutador**de la organización, que permite cambiar entre los organizaciones que se administran en solo 2 clics.
> [!TIP]
> No tiene que hacer nada para que el conmutador de la organización aparezca siempre que sea el socio de registro de al menos una organización.

1. En el centro de administración de Microsoft 365, seleccione el nombre de la organización.
![Captura de pantalla: parte superior de la Página principal donde se muestra el nombre del perfil de la organización con el icono del conmutador.](../media/MAC-Organization-switcher.png)

2. En el conmutador de la organización, seleccione el organigrama que desea administrar.
![Captura de pantalla: parte superior de la Página principal donde se muestra el nombre del perfil de la organización con el icono del conmutador.](../media/MAC-OrgSwitcherSelected.png)

Esto es literalmente!!!

### <a name="groups"></a>Grupos

Un par de cambios en el área grupos este mes:

- **Ordenar por nombre de grupo**: puede ordenar la lista grupos alfabéticamente, seleccionando la columna **nombre del grupo** .
- **Restaurar los grupos de microsoft 365 eliminados**: ya no es necesario ir al centro de administración de Exchange para restaurar los grupos de Microsoft 365 eliminados. Vaya a **Microsoft 365 administración del centro de administración** \> **grupos** \> **eliminados** \> (seleccione un grupo de la lista) \> **grupo de restauración**. Volverá a restaurar el grupo en la lista de **grupos** y restaurará el correo electrónico, las conversaciones, el Bloc de notas, los archivos y el calendario del grupo.

### <a name="videos-training-and-docs-february"></a>Vídeos, aprendizaje y documentos (febrero)

- **What's New in Microsoft 365 video series**: este mes, nos centramos en las capacidades de búsqueda personalizadas de SharePoint Online, la característica de administración de "what's New" de Office que permite mostrar u ocultar características específicas de los usuarios finales a través del panel de ayuda en la aplicación, las últimas actualizaciones de seguridad y cumplimiento de Yammer, entre otras. Este es el último episodio: [novedades de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

- **Movimiento de documentos**: hemos combinado los artículos web de administración de Office 365 con el contenido de Microsoft 365 y es posible que haya observado la nueva dirección URL. Por ejemplo, este artículo solía estar hospedado en: **docs.Microsoft.com/Office365/admin/Whats-New-in-Preview**, pero la dirección URL ahora es: **docs.Microsoft.com/Microsoft-365/admin/Whats-New-in-Preview**. Si tiene páginas con marcadores, debe actualizar los vínculos; sin embargo, los vínculos de contenido se redirigirán al repositorio de contenido nuevo.

## <a name="january-2020---happy-new-year"></a>Enero 2020-feliz año nuevo

> [!NOTE]
> ¿Sabía que hay una de las novedades de la serie de vídeos de [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096) en YouTube? Se resaltan las características más recientes que se han implementado para los usuarios. Cada mes empezaremos a vincular al episodio más reciente en la sección [vídeos, cursos y documentos](#videos-training-and-docs) . <br> <br> Este es el último episodio: [novedades de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2118096)

### <a name="dark-mode"></a>Modo oscuro

La primera vez que se implementó el modo oscuro, solo estaba disponible en la Página principal. El modo oscuro ahora está fuera de la vista previa y se encuentra en la versión de destino en la mayoría de las páginas del centro de administración.

1. En primer lugar, tendrá que activar la versión dirigida: vaya a **configuración** Settings Perfil de la organización opciones de \> **Settings** \> **Organization profile** \> **versión**.
1. Y luego activa el modo oscuro, ve a la página **principal** y, a continuación, selecciona el botón **modo oscuro** . (Se encuentra junto al campo de **búsqueda** y este artículo es el vínculo de **what's New** ).
1. Para cualquier página que tenga el modo oscuro disponible, el botón se encuentra en la parte superior de la página, junto a la nueva opción de alternancia **del centro de administración** .

### <a name="office-whats-new-management"></a>La nueva administración de Office

Los administradores quieren controlar el modo en que Microsoft comunica "What's New" a sus usuarios en las aplicaciones de Office y ahora tiene ese control. Vaya a **configuración** \> **Office what's New Management Preview**. Seleccione una característica para ver sus detalles y, a continuación, seleccione el botón **ocultar a los usuarios** si no desea que los usuarios vean un mensaje "what's New" en particular. Por ejemplo, es posible que su organización esté en espera de informar a los usuarios sobre una característica hasta que todos los usuarios de la organización reciban formación sobre ella.

![Captura de pantalla de la vista previa de la nueva versión de Office con el panel de detalles de una característica abierta.](../media/whatsnew-officemgmt-preview.png)

Esta característica se presentó por primera vez en la versión preliminar en noviembre, pero ha habido algunas actualizaciones de características que debería conocer: [Office What's New Management Preview ya disponible](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-preview/ba-p/1020438)

### <a name="partners"></a>Asociados

Howdy, Partners! (No se puede ayudar a mí mismo). También tenemos una actualización para usted este mes. Hay una nueva característica que permite a los partners dar a los clientes de CSP la opción de aceptar su acuerdo de cliente de Microsoft (MCA) en la sección **cuentas de facturación** del centro de administración. En esta nueva experiencia:

1. El cliente recibe un correo electrónico de invitación con un vínculo para aceptar la relación de socio y MCA.
2. Una vez que el cliente inicia sesión, puede ver y aceptar los permisos de MCA y Partner-Right desde el centro de administración.

### <a name="resource-mailboxes"></a>Buzones de recursos

La lista de buzones de recursos se ha actualizado con el nuevo estilo. En el centro de administración de Microsoft 365, vaya a **recursos** \> **salones de & equipo**.

### <a name="videos-training-and-docs-january"></a>Vídeos, cursos y documentos (enero)

Consulte el curso de administración de la pequeña empresa que publicamos en enero:

- [Crear el sitio web de su empresa](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9)
- [Buscar respuestas y ayuda](https://support.microsoft.com/office/7f681212-c649-4a3e-a43b-32b1d1e58988)
- [Obtener ayuda o soporte técnico](https://support.microsoft.com/office/18948a4c-3eb1-4b30-b1bc-a4cc29eb7655)
- [Eliminar un usuario](https://support.microsoft.com/office/6bcdad7b-732a-4260-997a-8c176bc3d9d6)
- [Elegir una suscripción de Microsoft](https://support.microsoft.com/office/b9f7c78e-430f-4117-89ec-2eeb1dced2ca)
- [Información general de Microsoft 365 para la seguridad de la empresa](https://support.microsoft.com/office/3274b159-a825-46d7-9421-7d6e209389d1)

## <a name="november-and-december-2019"></a>Noviembre y 2019 de diciembre

Estamos combinando las noticias de noviembre y diciembre porque, después de inflamarse, tenemos muy pocos anuncios que realizar. ¡ Vea el año nuevo!

### <a name="change-from-credit-card-to-invoice-payment"></a>Cambiar de tarjeta de crédito a pago de factura

Hemos comenzado a implementar la capacidad de cambiar el método de pago de la tarjeta de crédito a una factura. Vaya a **facturación** \> **de los productos**, seleccione una suscripción y, a continuación, seleccione el vínculo **Editar** junto al pago con tarjeta de crédito.

![Captura de pantalla: sección facturación de la tarjeta de suscripción con tarjeta de crédito como forma de pago.](../media/MAC-BillingEditCreditCard.png)

¿Desea más información? [Cambiar de tarjeta de crédito o cuenta bancaria a factura](../commerce/billing-and-payments/change-payment-method.md)

### <a name="global-reader"></a>Lector global

Mencionamos el rol lector global en la [edición de octubre de 2019-inflamable](#october-2019---ignite-edition), pero, a medida que se implementa con mayor detalle, vamos a analizar algunos detalles:

- El rol lector global es el homólogo de solo lectura del rol de administrador global. El lector global puede ver todo lo que el administrador global tiene permiso para hacer.
- Con algunas excepciones, como algunas características de seguridad y cumplimiento, los lectores globales tienen acceso para ver todos los centros de administración de la nube de Microsoft que su organización tiene licencia de uso.
- Asigne el rol de lector global a los usuarios que lo necesiten para la planeación, las auditorías y las investigaciones.
- También puede combinar el rol lector global con otro rol que tenga menos permisos. Por ejemplo, un propietario de pequeña empresa puede tener asignados los **Billing admin**  +  roles de**lector global** de administrador de facturación para que puedan pagar las facturas y permanecer al tanto de los cambios en la organización en la nube.
- Los lectores globales pueden ir a cualquier página del centro de administración de Microsoft 365. Al abrir una página modificable, aparecerá una advertencia en la parte superior en la que se indica que no tienen permiso para guardar los cambios y que el botón Guardar se deshabilitará.

Nos encantaría recibir sus comentarios sobre el rol lector global y los permisos basados en roles que le gustaría ver en el futuro. [Proporcionar comentarios sobre permisos basados en roles](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/10115430-have-a-consistent-experience-when-assigning-admin)

### <a name="new-settings-page"></a>Página nueva configuración

El **perfil**de la organización, la **seguridad & privacidad**y los **servicios & las páginas de complementos** se han combinado en una página con tres tabulaciones verticales. Y la mejor parte: desde una sola ubicación, ahora puede buscar todas las opciones de configuración.
![Captura de pantalla: Página de configuración con el campo "Buscar en todas las configuraciones" resaltado en la parte superior de la página.](../media/MAC-SettingsMultiPivotSearch.png)

### <a name="training--docs"></a>Documentos de & de aprendizaje

Esta sección es una nueva característica de este artículo, en la que empezaremos a vincular a la nueva formación y a la documentación que creemos que le resultará interesante.

En noviembre, se publicaron algunas caminos de aprendizaje en el sitio web de [Microsoft](https://docs.microsoft.com/learn/) Learning para ayudar a los profesionales de ti a aprender y obtener formación sobre Microsoft 365. Compruebe lo siguiente:

- [Conceptos básicos de Microsoft 365](https://docs.microsoft.com/learn/paths/m365-fundamentals/)
- [Ampliar las bases de Office](https://docs.microsoft.com/learn/paths/extend-office-fundamentals/)
- [Microsoft 365-modernizar la implementación de la empresa con Windows 10 y Microsoft 365 apps for Enterprise](https://docs.microsoft.com/learn/paths/m365-getmodern/)
- [Administre el despliegue de su empresa con Microsoft 365](https://docs.microsoft.com/learn/paths/manage-enterprise-deployment-m365/)
- [Actualice Microsoft Office para la TI a escala](https://docs.microsoft.com/learn/paths/m365-office-for-it/)
- [Entrega de aplicaciones y escritorios remotos desde Azure con el escritorio virtual de Windows](https://docs.microsoft.com/learn/paths/m365-wvd/)
- [Modernice su área de trabajo con Microsoft 365 y Surface para la Empresa](https://docs.microsoft.com/learn/paths/modernize-workplace-with-m365-and-surface/)
- [Proteger la identidad y el acceso con Microsoft 365](https://docs.microsoft.com/learn/paths/m365-identity/)
- [Proteger la información de la empresa con Microsoft 365](https://docs.microsoft.com/learn/paths/m365-information-protection/)
- [Administrar la seguridad con Microsoft 365](https://docs.microsoft.com/learn/paths/m365-security-management/)
- [Defiéndase contra las amenazas con Microsoft 365 y la protección contra amenazas de Microsoft](https://docs.microsoft.com/learn/paths/m365-security-threat-protection/)
- [Administración de la colaboración en grupo con Microsoft Teams](https://docs.microsoft.com/learn/paths/m365-manage-team-collaboration/)
- [Colaborar con SharePoint en Microsoft 365](https://docs.microsoft.com/learn/paths/m365-teams-sharepoint/)

## <a name="october-2019---ignite-edition"></a>Edición de octubre de 2019-inflamation

¡ Bienvenido a la edición de encendido de las novedades del centro de administración de Microsoft 365! Por supuesto, esta no es una lista completa de anuncios, pero estos son algunos aspectos destacados. Consulte también los blogs de encendido para obtener más información sobre las versiones:

- [Administración: mejoras en la red, la productividad y la seguridad para Microsoft 365](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/ADMIN-Security-Productivity-and-Network-Enhancements-for/ba-p/964019).
- [What's New in Microsoft Teams: encendido 2020](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-New-in-Microsoft-Teams-Ignite-2019/ba-p/937025).

### <a name="role-based-access-control"></a>Control de acceso basado en funciones

Ha habido muchos cambios para roles en el centro de administración desde que empezamos a implementar en junio:

- **Comparar roles** : seleccione hasta 3 roles para comparar los permisos de cada uno de ellos. Esto le ayudará a encontrar el rol menos permisivo que se asignará a los usuarios. Vaya a **roles**, use la casilla de verificación de selección múltiple en la primera columna para elegir hasta 3 roles y, después, seleccione **comparar roles**.

    ![Comparación de los roles de administrador de Exchange, administrador del Departamento de soporte técnico y administrador de usuarios.](../media/RBAC-CompareRoles.png)

- **Favoritos** : puede Agregar una estrella a sus roles favoritos o más usados, de modo que pueda encontrarlos fácilmente ordenando la columna o creando un filtro.
- **Usuarios activos**  >  **Administrar roles** : esto se ha actualizado para alinearse con los cambios en los roles. Al igual que con la lista roles, hemos definido el ámbito de la lista predeterminada de funciones para que sea más útil, pero puede ver todos los roles expandiendo **Mostrar todos por categoría**.
- **Rol de lector global** : ¡ le ha pedido! ¡ Lo consiguió! El rol [lector global](add-users/about-admin-roles.md) .

### <a name="report-an-issue"></a>Informar de un problema

El estado del servicio se ha actualizado al nuevo estilo y si se ve afectado por un problema que no se muestra en el panel de estado del servicio, puede **informar de un problema** para que Microsoft lo sepa. Vaya al **Health**  >  **Estado del servicio**de mantenimiento.

### <a name="viral-subscriptions"></a>Suscripciones "viral"

Como sabe, los usuarios pueden activar suscripciones gratuitas a una infinidad de productos, como Power BI y app Connect. Ahora puede ver las "suscripciones virales" que han intentado sus usuarios. Vaya a **facturación**  >  **de los productos**. Seleccione el filtro **tipo de cuenta** en la ficha suscripciones para ver las suscripciones compradas por el usuario. Si es necesario, ahora tiene la posibilidad de quitar estas suscripciones de su cuenta.

### <a name="user-templates"></a>Plantillas de usuario

Las plantillas le permiten agregar fácilmente varios usuarios al guardar y reutilizar la configuración compartida para estos usuarios. Puede guardar valores para roles, licencias asignadas, información de contacto, ubicación, etc. Cuando use la plantilla para crear un nuevo usuario, se obtendrá automáticamente el valor guardado de esta configuración. Vaya a **usuarios**  >  **activos**y, a continuación, seleccione **plantillas de usuario** para probarlo.

### <a name="office-whats-new-management-preview"></a>Administración de "What's New" de Office (versión preliminar)

Cuando se publica una característica importante de Office en una aplicación de Office, los usuarios obtendrán una tarjeta "What's New" para obtener información sobre la nueva característica. Si no desea que los usuarios vean la tarjeta, puede ocultarla. También puede elegir cuándo desea que los usuarios vean la tarjeta mostrándola. Vaya a **configuración**  >  **Office ¿qué es la nueva administración** para desprotegerla?

### <a name="sharepoint-url-change"></a>Cambio de dirección URL de SharePoint

Técnicamente, no se trata de las noticias del centro de administración de Microsoft 365 para decirle, pero estamos tan entusiasmados que queríamos que nos aseguremos de que vea esta noticia:
> [!IMPORTANT]
> Ahora puede obtener acceso a su centro de administración de SharePoint con una dirección URL normal:[https://admin.microsoft.com/SharePoint](https://admin.microsoft.com/SharePoint)

Para obtener más información, consulte [what's New in the SharePoint admin Center](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center).

## <a name="september-2019"></a>Septiembre de 2019

Estamos realizando un seguimiento de las fantásticas versiones de las características en el encendido de 2019, por lo que solo anunciamos algunas de las nuevas características que se publicaron en septiembre. Pero esté atento al artículo del próximo mes, se publicará el primer día de inflamabilidad.

### <a name="featured-feedback-fix--the-option-to-convert-the-deleted-users-mailbox-to-a-shared-mailbox-is-back"></a>Corrección de comentarios destacados: la opción para convertir el buzón de correo del usuario eliminado en un buzón compartido vuelve a estar

Hemos oído que sus comentarios son fuertes y claros, y hemos vuelto la capacidad de dar a otra persona acceso al buzón de correo de un usuario eliminado convirtiéndolo en un **buzón compartido**. Al volver a agregar el Asistente para eliminar usuarios, podrá decidir qué hacer con los datos:

- Email: conceder a otra persona acceso al buzón de correo del usuario eliminado convirtiéndolo en un buzón compartido.
- Archivos: guardar los archivos de OneDrive y proporcionar acceso a otro usuario.
- Permisos: quitar permisos si otros usuarios han tenido acceso a este buzón.
- Alias: quitar alias de correo electrónico para que estén disponibles para su uso por otro usuario inmediatamente.
![Captura de pantalla: Asistente para eliminar usuario con alias de correo electrónico, permisos, OneDrive y opciones de correo electrónico mostradas](../media/WhatsNew-DeleteUserWiz.png)

### <a name="initial-setup"></a>Configuración inicial

Ha habido una actualización a otro de nuestros asistentes de instalación inicial: Microsoft 365 para empresas. Los pasos se han simplificado y hemos movido dos de las tareas de configuración a la página de configuración:

- **Proteger equipos con Windows 10** : establezca directivas para proteger mejor sus dispositivos con Windows 10 de virus, malware y ataques de piratas informáticos.
- **Instalar Office automáticamente** : cuando se activa esta opción y los usuarios han conectado sus equipos a Microsoft 365 Business, sus equipos se actualizarán automáticamente a las últimas aplicaciones de Office y se mantendrán al día.

## <a name="august-2019"></a>Agosto de 2019

### <a name="billing"></a>Facturación

Tenemos algunas actualizaciones de facturación y suscripciones este mes:

- Suscripciones basadas en dispositivos: puede asignar o cancelar la asignación de licencias **de aplicaciones para el ámbito educativo (dispositivo) de 365 de Microsoft** a los dispositivos del centro de administración de Microsoft 365. **Microsoft 365 apps for Education (Device)** es una licencia de complemento que le permitirá asignar una licencia a un dispositivo. Vaya a **facturación**  >  **de productos** para buscar y adquirir la licencia.
- Administración de licencias basada en el usuario: hemos actualizado la forma en que se asignan licencias a los usuarios activos de **los usuarios**  >  **Active users** al nuevo estilo. Para obtener más información, vea:
  - [Asignar licencias a usuarios](manage/assign-licenses-to-users.md)
  - [Cancelar asignación a licencias de usuarios](manage/remove-licenses-from-users.md)

### <a name="setup-page-updates"></a>Instalación de actualizaciones de la página

El programa de instalación ahora tiene categorías y secciones, incluida una sección **recomendada para usted** donde recomendamos de forma inteligente el siguiente paso para activar las características y configurar la organización. También hemos agregado una nueva característica para configurar:

- **Protección contra amenazas avanzada de Office** : Si su organización tiene una licencia para usar ATP de Office y no la ha configurado o la ha activado todavía, verá esta página. Vaya al **programa de instalación** para probarlo.

### <a name="report-an-issue-august"></a>Informar de un problema (agosto)

Si se ve afectado por un problema que no se muestra en el panel de estado del servicio, el informe de una característica de problema le proporcionará una forma rápida y sencilla de que nos **informen** . Vaya al **Health**  >  **Estado del servicio**de mantenimiento.

## <a name="july-2019"></a>Julio de 2019

### <a name="message-center"></a>Centro de mensajes

El centro de mensajes se ha actualizado al nuevo diseño y parece asombroso.

![Captura de pantalla: Centro de mensajes actualizado con la pestaña "todos los mensajes activos" seleccionada y el menú filtro abierto.](../media/MAC-MessageCenterUpdated.png)

- Ahora puede ver **los mensajes por estado**. Solo tiene que seleccionar una de las pestañas: **todos los mensajes activos**, **importancia alta**, **mensajes no leídos**y **mensajes desechados**.
- También puede filtrar por privacidad de los **datos**de la categoría, **planear cambios**, **evitar o corregir problemas**y **mantenerse** a la vanguardia de las categorías de mensajes.
- Seleccione un mensaje de la lista y tiene algunas opciones en la barra de comandos: **descartar**, **marcar como leído** o **marcar como no leído**o **compartir**.
- Al abrir un mensaje, tiene incluso más opciones:
  - Copie un vínculo del mensaje en el portapapeles para guardarlo para más tarde o para compartirlo con compañeros.
  - Marcar los mensajes como **leídos** o no **leídos**.
  - Enviar comentarios sobre un mensaje seleccionando **like** o **Unlike**, se abrirá un panel de comentarios en el que se le pedirá que proporcione comentarios específicos sobre lo que le gustó o que no le gusta este mensaje.

### <a name="navigation-pane-intelligence"></a>Inteligencia del panel de navegación

 Ahora, el panel de navegación recuerda sus últimas acciones y muestra el panel en el último estado en el que lo dejó. También hará que los elementos que se usan con frecuencia sean visibles de forma predeterminada.

### <a name="initial-setup--the-setup-page"></a>Configuración inicial & la página de configuración

Tenemos algunos cambios interesantes que le ayudarán a configurar la organización. En primer lugar, vamos a analizar la diferencia entre la **configuración** y la **Página de configuración**. El **programa de instalación** hace referencia al asistente de instalación inicial que usó para incorporarse a los servicios en línea de Microsoft. Esto suele incluir tres pasos específicos: **conectar un dominio**, **Agregar usuarios**y **descargar las aplicaciones de Office**. La **Página de configuración** es la página del centro de administración que ha recomendado configurar las tareas para asegurarse de que se saca el máximo partido a las suscripciones, como la activación de las características para las que ha comprado licencias.

- **Setup** -el Asistente de instalación inicial se ha actualizado para las suscripciones de **Microsoft 365 para empresas** . Este nuevo diseño ayudará a las nuevas organizaciones a pasar por el asistente con mayor rapidez y tendrá un éxito mayor.
- **Página de instalación** : la página de **configuración** ayuda a finalizar la configuración y la protección de los servicios que vienen con las suscripciones. También puede ver las recomendaciones que se han desechado en la página de **configuración** . Para ver si todavía está disponible para sus suscripciones, vaya a la instalación del **centro de administración de 365 de Microsoft**  >  **Setup**.

### <a name="billing--subscriptions"></a>Suscripciones de & de facturación

- Tipo de producto de **software** : ahora puede ver los productos de software adquiridos a través de un proveedor de servicios en la nube (CSP). Para ver las descargas y las claves, vaya a **facturación**  >  **de la**  >  ficha**software** de productos.
- Puede ver los productos y servicios de Azure modernos desde el centro de administración de Microsoft 365, ya haya adquiridolos de Microsoft o de un proveedor de terceros. Ejemplos de productos modernos de Azure incluidos:
  - Instancias virtuales reservadas de Azure
  - Planes de soporte de Azure
  - Ventajas de Azure Hybrid use (AHUB)
  - Administrar aplicaciones
  - Servicios de dispositivos
  - Suscripciones de Azure

### <a name="simplify-multi-factor-authentication"></a>Simplificación de la autenticación multifactor

Los administradores tienen acceso a información confidencial de la organización. Requerir que todos los administradores usen la autenticación multifactor al iniciar sesión. El asistente nuevo le ayudará a hacerlo con un solo paso. Para probarlo, vaya a **configuración**  >  **reforzar la seguridad de inicio de sesión**.

### <a name="users"></a>Usuarios

Las páginas **usuarios eliminados** e **invitado** se actualizaron al nuevo estilo.

- **Usuarios invitados**: los usuarios invitados se agregan al invitarles a ver o compartir archivos desde SharePoint o OneDrive. Puede ver a los usuarios invitados a los usuarios invitados de **los usuarios**  >  **Guest users**.
- **Usuarios eliminados**: en la página **usuarios eliminados** actualizados, puede realizar todas las acciones que puede en el centro de administración anterior, pero ahora puede Agregar y quitar columnas. Y disponemos de muchas opciones de columna para elegir. De hecho, es la misma columna que puede elegir en la página **usuarios activos** .

## <a name="june-2019"></a>Junio de 2019

### <a name="featured-feedback-request---dark-mode"></a>Solicitud de comentarios destacados: modo oscuro

Ver el centro de administración en modo oscuro está en versión preliminar. Solo puede probarlo en la página **principal** en este momento. En la página **principal** , el botón **modo oscuro** se encuentra en la barra de comandos junto al vínculo **what's New** .

### <a name="roles-management"></a>Administración de roles

Al final de junio, empezamos a implementar una nueva forma de administrar los roles de administrador. Cuando esté disponible para usted, **vaya a roles de roles**  >  **Roles**. Hasta entonces, eche un vistazo, ¡ es increíble!
<br> ![Captura de pantalla: lista de roles de administración con el panel de detalles de rol de administrador de usuarios resaltado.](../media/MAC-AdminRoles-Featured.png) <br>

Esta nueva experiencia hace que sea más fácil ver quién tiene permisos de administrador y asignar roles que concedan el nivel correcto de acceso a los administradores. Además, agregamos más roles de Azure AD para que no pierda el tiempo dirigido a varios centros de administración.
¿Qué más puede hacer aquí?

- Exporte una lista de todos los administradores de la organización que tienen asignados roles de Azure Active Directory en Microsoft 365.  
- Permite ver todos los administradores asignados a un rol específico, agregar o quitar administradores de una función específica, buscar roles por nombre y palabra clave y obtener más información sobre lo que cada rol permite hacer a un usuario.
- Buscar rápidamente una función específica y crear filtros.

### <a name="payment-method"></a>Método de pago

Hemos actualizado la forma en que paga las suscripciones. Vaya a **facturación**  >  **facturas &**  >  **métodos de pago**de pagos. Puede ver los métodos de pago en una vista de lista. Seleccione cualquier elemento de la lista para quitarlo, editarlo y ver con facilidad la suscripción con la que está asociado el método de pago.

## <a name="may-2019"></a>Mayo de 2019

### <a name="mays-featured-fix---case-sensitivity"></a>Corrección de mayúsculas y minúsculas de mayo

Ahora, al buscar buzones de correo compartidos, contactos, recursos y permisos de buzón de correo, los términos de búsqueda no tienen que distinguir entre mayúsculas y minúsculas.

**Administración de usuarios y grupos** Este mes hemos actualizado el **bloqueo de usuario**, la **contraseña de restablecimiento**, la vista de lista de **contactos** , la vista de lista de **grupos** y las páginas de detalles de **grupos** al nuevo estilo de centro de administración.

- Con la vista de lista de nuevos **grupos** , obtendrá datos más completos sobre los grupos y podrá personalizar la forma en que ve sus datos, y la lista de grupos recuerda cómo desea ver los datos. Por ejemplo, ahora puede filtrar por **grupos con Teams** para ver si los grupos forman parte de un equipo y puede Agregar la columna **Estado de Teams** .
- La lista de grupos también aporta todas las mejoras que hemos realizado en la experiencia de lista en administración de usuarios, incluidas las acciones rápidas y la barra de comandos contextual.

**Recomendaciones**<br>
Es posible que vea una nueva recomendación emergente en el centro de administración: hemos agregado 4 nuevas. Por supuesto, solo verá recomendaciones si creemos que beneficiará a su organización. Pero no espere hasta que le muestren la recomendación: puede agregarla desde la biblioteca de tarjetas.

- **Expiración** de la contraseña: se recomienda que las contraseñas se configuran para que no **expiren nunca**. Y si su organización tiene una configuración diferente, es posible que solo vea esta recomendación.
- **Demasiados administradores globales** : como tener demasiados administradores globales es una amenaza de seguridad, si tiene más de 4 administradores globales, verá esta recomendación. Le sugerimos que proporcione a los usuarios solo el acceso que necesitan para realizar su trabajo.
- **Protección de dispositivos de Intune** : si las licencias incluyen Intune y se detecta que no ha terminado de configurar Intune o que se han inscrito en los dispositivos, le recomendamos que cree una directiva de Intune para proteger los archivos de su organización cuando los usuarios acceden a ellos desde sus dispositivos móviles.
- **Obtener actualizaciones de características mensuales de Office** -hemos recibido comentarios de nuestros clientes muy pequeños que, al obtener actualizaciones de características mensuales de Office, sus usuarios están más satisfechos. Por lo tanto, si es un negocio muy pequeño y actualmente tiene las actualizaciones de las características de Office cada seis meses, verá esta recomendación.

**Configuración** <br>
Como en el caso de la configuración, ha habido muy pocos cambios. Principalmente, solo tiene que actualizar la configuración existente al nuevo estilo del centro de administración. Como estamos avanzando y agregando nuevas opciones de configuración que nunca ha visto antes, empezaremos a mencionarlos aquí. Y tenemos una configuración completa para anunciar: **autenticación moderna**. Sí, hay una nueva configuración para activar la **autenticación moderna**. Para desprotegerla, vaya a **configuración**de los  >  **servicios &**  >  **autenticación moderna**de complementos.

## <a name="april-2019"></a>Abril de 2019

Las cosas tienen un buen aspecto para el centro de administración. Hemos sido leyendo sus comentarios y sugerencias, respondiendo a la mayoría de ellos y, en realidad, tenemos todo lo que tiene que decir como corazón. Por supuesto, todavía estamos trabajando para asegurarse de que todo está a la paridad con el centro de administración antiguo. Recuerde que, como se implementan las nuevas características, es posible que no las obtenga de inmediato.

### <a name="featured-feature---add-users"></a>Característica destacada: agregar usuarios

Para abril, estamos presentando el Asistente para **Agregar usuarios** que le guiará por el... espere... Agregar usuarios. Se trata de un paso paso a paso para agregar información básica del usuario como el correo electrónico y el nombre para mostrar, la asignación de una licencia y un rol, la adición de la información de contacto y la revisión de la cuenta del usuario antes de confirmarla. **¿Por qué hemos realizado este cambio?** Hemos leído sus comentarios que no me gustaron en el desplazamiento casi infinito para agregar usuarios en la experiencia anterior.
<br> ![Captura de pantalla del Asistente para agregar usuario.](../media/MAC-AddUserWizard.png) <br>

Hay dos formas en las que puede desproteger: <br>

1. En la página **principal** , seleccione **Agregar usuario** de la tarjeta de **Administración de usuarios** . El asistente se abrirá a la derecha, de modo que no tendrá que navegar desde cualquier trabajo que esté haciendo en la página **principal** .
2. Vaya a **usuarios**  >  **activos**y, a continuación, seleccione **Agregar usuario** en la barra de comandos.
<br><br>

Hemos realizado algunos cambios más en la **Administración de usuarios**, esta es una lista rápida:

- El panel **administrar roles** se ha actualizado al nuevo estilo y es accesible. También se han actualizado los paneles **bloquear usuario** y **eliminar usuario** para el nuevo estilo.
- La ubicación de **Administración de licencias de producto** cambia en la barra de comandos.
- Ahora es más fácil cambiar la foto de un usuario. En **usuarios activos** , seleccione un usuario y, a continuación, **cambie la foto** debajo de su imagen.

### <a name="but-wait-theres-more"></a>Pero espere. Hay más

- Hay un nuevo banner de configuración en la página **principal** que verá si no ha terminado los pasos de configuración, como agregar un dominio, agregar usuarios y descargar las aplicaciones de Office.
- La lista de **grupos** y el panel de detalles se han actualizado con el nuevo estilo. Vaya a **grupos**  >  **grupos** para ver los cambios.
  - Hablando de grupos, también hemos agregado una pestaña de **Microsoft Teams** al panel de detalles de grupos, en el que puede convertir cualquier grupo de Microsoft 365 en un equipo. Para "teamify" un grupo seleccione cualquier grupo de Microsoft 365 de la lista, seleccione la pestaña **Microsoft Teams** y, a continuación, **crear equipo**. Si el grupo ya es un equipo, recibirá un vínculo para administrarlo desde el **centro de administración de Teams**.
  - Por último, puede Agregar el **Estado de Teams** a la lista de **grupos** . En el encabezado de columna, seleccione **elegir columnas**  >  **Estado del equipo**-  >  **Guardar**.
- **Nuevos roles de administrador limitados** : hemos realizado algunos nuevos roles de administrador para que pueda proporcionar a los usuarios solo el acceso que necesitan.
  - **Administrador de Kaizala**: los usuarios de este rol tienen permiso para realizar todas las tareas de administración dentro de Microsoft Kaizala, incluidos crear y administrar usuarios en Kaizala, administrar Kaizala grupos, administrar tarjetas de acción y conectores y crear solicitudes de servicio.
  - **Administración de búsqueda**: los usuarios de este rol tienen acceso total a todas las características de administración de Microsoft Search en el centro de administración de Microsoft 365. Los administradores de búsqueda pueden delegar los roles de administrador de búsqueda y editor de búsqueda a los usuarios, así como crear y administrar contenido, como marcadores, preguntas&un elemento y ubicaciones. Además, estos usuarios pueden ver el centro de mensajes, supervisar el estado del servicio y crear solicitudes de servicio.
  - **Editor de búsqueda**: los usuarios de este rol pueden crear, administrar y eliminar contenido para Microsoft Search en el centro de administración de Microsoft 365, incluidos marcadores, Q&A elementos y ubicaciones.
- Hay un Bonanza de **facturación** que cambia este mes...
  - Ahora puede actualizar el CVV para tarjetas de crédito existentes sin tener que eliminarla y agregarla de nuevo. Puede actualizar el CVV yendo a métodos de **Bills**  >  **pago**de facturas.
    - Hemos hecho que sea más fácil encontrar sus **facturas** y comprender los problemas de facturación que pueda tener en su cuenta. Y ahora puede ver sus facturas en el explorador Web en lugar de tener que descargar el PDF. Vaya a **facturas**  >  **Invoices**.
    - En la página **sus productos** , ahora agregamos la información de la suscripción si tiene varias suscripciones del mismo tipo.

## <a name="march-2019---weve-officially-released-the-admin-center"></a>Marzo de 2019: hemos lanzado oficialmente el centro de administración

Bueno, si perdió las noticias emocionantes, hemos puesto oficialmente el nuevo y mejorado centro de administración de 365 de Microsoft. Esta es la entrada de blog donde la anunciamos: [el nuevo centro de administración de Microsoft 365 actualmente está disponible](https://techcommunity.microsoft.com/t5/Microsoft-365-Blog/The-new-Microsoft-365-admin-center-available-today/ba-p/377870). Para marzo, usaremos la entrada de blog para que revise las características publicadas, además, también puede leer la publicación de las características que se publican en un futuro próximo, que no se permiten en el contenido principal.
<br> ![Captura de pantalla de la Página principal del centro de administración de Microsoft 365.](../media/M365AC-HomePage.png) <br>
Tenemos un cambio en la **facturación & área de suscripciones** que nos gustaría mencionar. Me digo que y'all no pensó que se haya terminado con la mejora, ¿verdad? Porque no lo estamos. De hecho, este mes hemos agregado la capacidad de administrar sus relaciones con los socios **Billing**para  >  **las cuentas**de facturación de facturación. Desde aquí, puede revisar las relaciones con los socios entre asesores, CSP y revendedores indirectos. También puede aceptar nuevas solicitudes de relación de asociados, incluidos los permisos de administrador delegados.

Como siempre, sus comentarios son importantes para nosotros, así que háganos venir. En cualquier página del centro de administración, puede enviar comentarios seleccionando **Enviar comentarios** en la parte inferior derecha, junto a **¿necesita ayuda?**

## <a name="february-2019---billing--subscriptions-edition"></a>2019 de febrero-edición de suscripciones de & de facturación

Este mes nos centraremos en todas las mejoras que hemos realizado en las áreas affectionately denominadas "Billing and subscriptions". En el pasado, probablemente no hará referencia a esas cosas affectionately, pero creemos que ahora...

- **Métodos de pago** : hemos leído sus comentarios sobre cómo la actualización del método de pago era difícil y hemos realizado muchos cambios. Vaya a **Billing**  >  **métodos de pago**de facturación. Puede ver fácilmente los métodos de pago, como la tarjeta de Visa y la suscripción con la que está asociado. En la lista de métodos de pago, seleccione el menú **más** (3 pequeños puntos junto a la fecha de expiración) y, a continuación, seleccione **Ver suscripciones**. También puede editar y eliminar los métodos de pago desde el menú **más** .
- **Cuenta de facturación** -versión dirigida los clientes verán la nueva página cuenta de facturación en primer lugar y, a continuación, la entregaremos a todo el mundo. Cuando esté disponible para usted, vaya a la **Billing**  >  **cuenta de facturación**de facturación. ¿Qué puede hacer en la página nueva cuenta de facturación? Me alegro de que me pregunte:
  - Actualice la dirección y otra información de contacto en el perfil de la organización directamente desde esta página. No tiene que ir a **configuración**del  >  **perfil**de la organización, a menos que desee.
  - Además, estamos facilitando la vida para los clientes directos o de licencias por volumen, por lo que puede aceptar y revisar los contratos de clientes desde **cuentas de facturación**. También puede conectarse con otras organizaciones que le permiten vincular el organizaciones de forma conjunta para compartir licencias y recursos.
- También hemos realizado algunas mejoras más pequeñas y correcciones de errores:
  - Reactivar una suscripción con un pago de factura
  - Editar la dirección de uso del servicio para las suscripciones
  - En la página de detalles del inventario, hemos agregado algunas mejoras en las notificaciones, le vinculamos a la página real en la que puede realizar el trabajo y hay más acciones en la tarjeta de detalles de inventario. Ir a **Billing**  >  **facturas**  >  de facturación**Ver detalles** en cualquier factura.

## <a name="january-2019---happy-new-year"></a>Enero 2019-feliz año nuevo

- Todavía agregando **complementos & de servicios** : hemos actualizado más **Opciones > de los servicios & páginas de complementos** . Pruebe los informes o aplicaciones integradas para ver la última.
- **¿Busca mejoras?** No mire más allá del cuadro de **búsqueda** en la barra de comandos. Se ha actualizado para que pueda buscar tareas. Por ejemplo, pruebe con "Restablecer contraseña" o "agregar un usuario".

### <a name="featured-feedback-fix---licenses-and-apps"></a>Corrección de comentarios destacados: licencias y aplicaciones

Las **licencias y aplicaciones** se volverán a combinar en el panel de detalles del usuario en función de sus comentarios. Inicialmente separó las dos características para proporcionar espacio para los detalles de todas las licencias y todas las posibilidades de la aplicación. Hemos oído que, al separar las licencias y aplicaciones en dos paneles se ha agregado confusión. Hemos escuchado las licencias y las aplicaciones en una pestaña. Ahora puede asegurarse de que una aplicación esté desactivada en todas las licencias asignadas a un usuario en un panel. Leche y cookies. Licencias y aplicaciones. Ahora lo obtenemos.

Desproteger: **los usuarios > usuarios activos > editar** o **Agregar licencias y aplicaciones de > de usuario**
