---
title: Centro de mensajes
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 38fb3333-bfcc-4340-a37b-deda509c2093
description: Obtenga información general sobre el Microsoft 365 de mensajes y su rol en la administración de cambios.
ms.openlocfilehash: 01e43eb6fa9502c138bfc9ab3595c47ec33ad098
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537528"
---
# <a name="message-center"></a>Centro de mensajes

Para realizar un seguimiento de los próximos cambios, incluidas las características nuevas y modificadas, el mantenimiento planeado u otros anuncios importantes, vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">Centro de mensajes</a>.
  
Para abrir el Centro de mensajes:

::: moniker range="o365-worldwide"

- En el Centro de administración, vaya al **Centro de** mensajes > <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">de mantenimiento</a>.

::: moniker-end

::: moniker range="o365-germany"

- En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya al **Centro de** mensajes de > **mantenimiento**.

::: moniker-end

::: moniker range="o365-21vianet"

- En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya al **Centro de** mensajes de > **mantenimiento**.

::: moniker-end

También puedes usar la aplicación [Microsoft 365 administración](https://go.microsoft.com/fwlink/p/?linkid=627216) en el dispositivo móvil para ver el Centro de mensajes, que es una excelente manera de mantenerse al día con las notificaciones push.

Para cancelar la suscripción a los correos electrónicos del Centro de mensajes, consulte Cancelar la suscripción a los correos [electrónicos del Centro](#unsubscribe-from-message-center-emails) de mensajes en este artículo.

  
## <a name="frequently-asked-questions"></a>Preguntas frecuentes

|**Pregunta**|**Respuesta**|
|:-----|:-----|
|Quién puede ver las publicaciones en el Centro de mensajes  <br/> |La mayoría de los usuarios a los que se ha asignado un rol de administrador Microsoft 365 pueden ver las publicaciones del Centro de mensajes. [Esta es una lista de](#admin-roles-that-dont-have-access-to-the-message-center) roles de administrador que no tienen acceso al Centro de mensajes. También puede asignar el rol de lector del Centro de mensajes a los usuarios que deben poder leer y compartir publicaciones del Centro de mensajes sin tener ningún otro privilegio de administrador.<br/>|
|¿Es esta la única forma en que Microsoft comunicará los cambios Microsoft 365?  <br/> |No, pero el centro de mensajes es la forma principal de comunicar el momento de los cambios individuales en Microsoft 365. Consulta [Mantenerse al tanto de Microsoft 365 cambios para](stay-on-top-of-updates.md) obtener información sobre recursos adicionales.  <br/> |
|¿Cómo puedo ver publicaciones en mi idioma?  <br/> |Las publicaciones del centro de mensajes solo se escriben en inglés, pero puedes controlar si, de forma predeterminada, las publicaciones se muestran en inglés o se traducen automáticamente a tu idioma preferido. También puede seleccionar la traducción automática de publicaciones a cualquier idioma que admitamos. Consulta [Traducción de idioma para publicaciones del Centro de mensajes](language-translation-for-message-center-posts.md) para obtener más detalles.  <br/> |
|¿Puedo obtener una vista previa de los cambios o características antes de que se revierte en mi organización?  <br/> |Algunos cambios y nuevas características se pueden previsualizar optando por el programa de versión dirigida. Para participar, en el Centro de administración, vaya a configuración Configuración Configuración de la organización Preferencias de versión  >    >    >  **del perfil de la organización.** (En el Centro de administración, es posible que deba seleccionar **Mostrar** todo en la parte inferior del panel de navegación izquierdo para ver **Configuración**.) Puede elegir La versión dirigida para toda la organización o solo para los usuarios seleccionados. Vea [Opciones de versión estándar o dirigida](release-options-in-office-365.md) en Microsoft 365 para obtener más información sobre el programa.  <br/> |
|¿Puedo averiguar la fecha exacta en que estará disponible un cambio para mi organización?  <br/> |Desafortunadamente, no podemos decirle la fecha exacta en la que se realizará un cambio en su organización. En nuestra publicación del Centro de mensajes, proporcionaremos toda la información que podamos sobre el momento de la versión, en función de nuestro nivel de confianza. Estamos trabajando en mejoras para mejorar con ese nivel de detalle.  <br/> |
|¿Estos mensajes son específicos de mi organización?  <br/> |Hacemos todo lo posible para asegurarnos de que solo vea las publicaciones del Centro de mensajes que afectan a su organización. El Microsoft 365 plan de desarrollo incluye todas las características en las que estamos trabajando y implementando actualmente, pero no todas estas características se aplican a todas las organizaciones. <br/> |
|¿Puedo recibir mensajes del centro de mensajes por correo electrónico en su lugar?  <br/> |Sí Puede seleccionar que se le envíe un resumen semanal y hasta dos direcciones de correo electrónico más. El resumen semanal enviado por correo electrónico está activado de forma predeterminada. Si no estás obteniendo los resúmenes semanales, comprueba la carpeta de correo no deseado. Consulta la [sección Preferencias](#preferences) de este artículo para obtener más información sobre cómo configurar el resumen semanal.  <br/> |
|¿Cómo detén el resumen del centro de mensajes?  <br/> |Vaya al Centro de mensajes en el Centro de administración y seleccione **Preferencias**. En la **pestaña Correo** electrónico, desactive la opción Enviarme notificaciones por correo electrónico desde el centro **de mensajes**.   <br/> |
|¿Cómo puedo garantizar que los contactos adecuados de mi organización reciban notificaciones de privacidad de datos? <br/> |Como administrador global, recibirá mensajes de privacidad de datos para su organización. Además, puede asignar el rol de lector privacidad del Centro de mensajes a las personas que deben ver mensajes de privacidad de datos. Otros roles de administrador con acceso al Centro de mensajes no pueden ver mensajes de privacidad de datos.   <br/><br/>Para obtener más información, consulta [Preferencias](#preferences) en este artículo.<br/> |
|¿Por qué no puedo ver un mensaje que estaba allí anteriormente? <br/> |Para administrar el número de mensajes dentro del Centro de mensajes, cada mensaje expirará y se quitará después de un período de tiempo. Por lo general, los mensajes expiran 30 días después del período de tiempo descrito en el cuerpo del mensaje. <br/> |

## <a name="filter-messages"></a>Filtrar mensajes

El centro de mensajes presenta una vista de todos los mensajes activos en un formato de tabla. De forma predeterminada, muestra el mensaje más reciente en la parte superior de la lista. Puede seleccionar **Servicio para** ver los mensajes de varios servicios, como Aplicaciones Microsoft 365, SharePoint Online, etc.   En **Etiqueta** puede seleccionar **Impacto** de administrador **,** Privacidad de datos **,** Actualización de características , Actualización **principal,** **Nueva característica,** Retiro **o** Mensajes de **impacto del** usuario. En **Estado de mensaje,** puede seleccionar **Favoritos**, **No leídos** o **Mensajes actualizados.**

La pestaña Archivo muestra los mensajes que ha archivado. Para archivar un mensaje, en el panel de mensajes, seleccione **Archivo**.

::: moniker range="o365-worldwide"

Use los menús desplegables **Servicio**, **Etiqueta** y **Estado del mensaje**  para seleccionar una vista filtrada de los mensajes. Por ejemplo, en este diagrama los mensajes se etiquetan con la etiqueta **Impacto en el administrador**.

Puede seleccionar cualquier encabezado de columna, salvo **Servicio** y **Etiqueta** para ordenar los mensajes en orden ascendente o descendente.

:::image type="content" source="../../media/message-center-admin-impact1.png" alt-text="Vista del Centro de mensajes ordenada por Impacto del administrador.":::

::: moniker-end

::: moniker range="o365-germany"

Utilice el menú desplegable **Vista** para seleccionar una vista filtrada de los mensajes.

Puede seleccionar cualquier encabezado de columna para ordenar los mensajes en orden ascendente o descendente. Por ejemplo, en esta ilustración los mensajes se ordenan por fecha en **Acción hecha el**.

![Vista del Centro de mensajes ordenada por la etiqueta del Impacto del administrador](../../media/message-center-filter-act-by.png)

::: moniker-end

::: moniker range="o365-21vianet"

Use los menús desplegables **Servicio**, **Etiqueta** y **Estado del mensaje**  para seleccionar una vista filtrada de los mensajes. Por ejemplo, en este diagrama los mensajes se etiquetan con **Impacto en el administrador**.

Puede seleccionar cualquier encabezado de columna, salvo **Servicio** y **Etiquetas** para ordenar los mensajes en orden ascendente o descendente.

::: moniker-end

### <a name="major-updates"></a>Actualizaciones principales

Las actualizaciones principales se pueden revisar seleccionando la **actualización principal** de **la** lista desplegable Etiquetas.

Las actualizaciones principales se comunican con al menos 30 días de antelación cuando se requiere una acción y pueden incluir:
  
- Cambios en la productividad diaria, como bandeja de entrada, reuniones, delegaciones, uso compartido y acceso

- Cambios en temas, elementos web y otros componentes que pueden afectar a características personalizadas

- Aumenta o disminuye la capacidad visible, como el almacenamiento, el número de reglas, elementos o duraciones

- Cambios en la personalizado de marca del producto que pueden:

  - Causar confusión al usuario final,

  - Resultado en cambios en procesos de servicio de ayuda y material de referencia, o

  - Cambiar una dirección URL

- Un nuevo servicio o aplicación

- Cambios que requieren una acción de administrador (excluyendo los problemas de prevención o corrección)

- Cambios en el lugar donde se almacenan los datos
  
### <a name="preferences"></a>Preferencias

Si la administración se distribuye en toda la organización, es posible que no desee o necesite ver publicaciones sobre todos los Microsoft 365 servicios. Cada administrador puede:

- Establece las preferencias que controlan los mensajes que se muestran en el Centro de mensajes.
- Filtrar mensajes
- Establece las preferencias de correo electrónico para recibir una síntesis semanal de todos los mensajes, correos electrónicos solo para actualizaciones principales y correos electrónicos para mensajes de privacidad de datos.  

::: moniker range="o365-worldwide"

1. Seleccione **Preferencias** en la parte superior del Centro de mensajes.

2. En la **pestaña Vista personalizada,** asegúrese de que la casilla está activada para cada servicio que desee supervisar. Desactive las casillas de los servicios que desea filtrar fuera de la vista Centro de mensajes.

3. Los correos electrónicos de resumen están activados de forma predeterminada y se envían a su dirección de correo electrónico principal. Para dejar de recibir el resumen semanal, desactive la casilla **Enviarme** notificaciones por correo electrónico desde el centro de mensajes en la **pestaña Correo electrónico**. 

   También puede escribir hasta dos direcciones de correo electrónico, separadas por un punto y coma.

   También puede elegir los correos electrónicos que desea obtener, así como un resumen semanal de los servicios que seleccione.

4. Seleccione **Guardar** para conservar los cambios.
  
::: moniker-end

::: moniker range="o365-germany"

1. Seleccione **Editar preferencias del centro de** mensajes en la parte superior del Centro de mensajes.

2. Asegúrese de que la alternancia esté establecida en **On** para cada servicio que desee supervisar. Use la alternancia para cambiar la configuración a **Desactivado** para los servicios que desea filtrar fuera de la vista Centro de mensajes.

3. Los correos electrónicos de resumen están activados de forma predeterminada y se envían a su dirección de correo electrónico principal. Para dejar de recibir el resumen semanal, cambie la opción **Enviar una síntesis semanal de mis** mensajes a **Desactivado**. 

   La notificación por correo electrónico para actualizaciones principales es un control independiente. Si desea recibir notificaciones por correo electrónico acerca de las actualizaciones principales, compruebe que **Enviarme mensajes** de correo electrónico para actualizaciones principales está **en .** Cambia la configuración a **Desactivado para** dejar de recibir correo electrónico sobre las actualizaciones principales. 

   Para recibir avisos de correo electrónico sobre mensajes de privacidad de datos, compruebe que **Enviarme mensajes de correo electrónico** para mensajes de privacidad de datos está **en**. Para dejar de recibir estos avisos, cambie la configuración a **Desactivado**. (Los mensajes de privacidad de datos no se incluyen en el resumen semanal).

   Puede seleccionar o borrar la dirección de correo electrónico principal, pero no puede cambiarla. Para especificar otras direcciones de correo electrónico a las que se envía el resumen de correo electrónico semanal, compruebe que Enviar una síntesis **semanal de mis** mensajes es **On**. Escriba la dirección de correo electrónico de un grupo Microsoft 365 o una lista de distribución si más de dos personas deben obtener el correo electrónico de resumen.

4. Seleccione **Guardar** para conservar los cambios.<br/>

::: moniker-end

::: moniker range="o365-21vianet"

1. Seleccione **Preferencias** en la parte superior del Centro de mensajes.

2. En la **pestaña Vista personalizada,** asegúrese de que la casilla está activada para cada servicio que desee supervisar. Desactive las casillas de los servicios que desea filtrar fuera de la vista Centro de mensajes.

3. Los correos electrónicos de resumen están activados de forma predeterminada y se envían a su dirección de correo electrónico principal. Para dejar de recibir el resumen semanal, desactive la casilla **Enviarme** notificaciones por correo electrónico desde el centro de mensajes en la **pestaña Correo electrónico**.

   También puede escribir hasta dos direcciones de correo electrónico, separadas por un punto y coma. <br><br/>También puede elegir los correos electrónicos que desea obtener, así como un resumen semanal de los servicios que seleccione.

4. Seleccione **Guardar** para conservar los cambios.<br/>

::: moniker-end

### <a name="display-messages-in-your-preferred-language"></a>Mostrar mensajes en el idioma preferido
  
Usamos la traducción automática para mostrar automáticamente los mensajes en el idioma que prefieras. Lea [Traducción de idioma para las publicaciones del Centro de mensajes](language-translation-for-message-center-posts.md) para obtener más información sobre cómo establecer el idioma.
  
> [!NOTE]
> El resumen semanal y las publicaciones que se envían por correo electrónico se envían solo en inglés. Los destinatarios pueden usar [Traductor para Outlook](https://support.microsoft.com/office/3d7e12ed-99d6-406e-a453-b9db0d9653fa) para leer el mensaje en su idioma preferido.

## <a name="choose-columns"></a>Elegir columnas

Para elegir columnas, en la página Centro de mensajes, en  el extremo derecho, seleccione Elegir columnas y, en el panel Elegir columnas, seleccione las que desee que se muestren. 

Esta es una introducción rápida a la información que verá en cada columna.

### <a name="column-information"></a>Información de columna

|**Columna**|**Descripción**|
|:-----|:-----|
|Marca de verificación  <br/> |Si se selecciona la marca de verificación en la fila de encabezado de columna, se seleccionarán todos los mensajes que se muestran actualmente. Si selecciona la marca de verificación junto a uno o varios mensajes, podrá realizar acciones en esos mensajes.  <br/> |
|Título del mensaje  <br/> |Los títulos de los mensajes son breves descripciones de los próximos cambios. Si no se muestra el título completo, coloca el cursor sobre él y todo el título aparecerá en un cuadro emergente.  <br/> |
|Servicio <br/> |Los iconos indican la aplicación a la que se aplica el mensaje.<br/> |
|Más opciones <br/> |Más opciones te permiten descartar un mensaje, marcarlo como leído o no leído, o compartirlo con otro administrador. Para restaurar un mensaje archivado, seleccione **la** pestaña Archivo, seleccione la marca de verificación situada junto al mensaje y **seleccione Restaurar**. <br/> |
|Etiquetas <br/> |Puede elegir etiquetas en **la** lista desplegable Etiqueta para filtrar mensajes. Las etiquetas disponibles son: **Impacto de administrador**, Actualización **principal** **,** Privacidad de datos , Actualización de **características**, **Nueva característica,** Retiro **e** Impacto del **usuario.** <br/> |
|Categoría  <br/> | Esto no se muestra de forma predeterminada, pero se puede especificar en el panel **Elegir** columnas. Los mensajes se identifican mediante una de las tres categorías siguientes: <br/><br/> **Evitar o solucionar problemas:** le informa de los problemas conocidos que afectan a su organización y puede requerir que tome medidas para evitar interrupciones en el servicio. Evitar o solucionar problemas son diferentes de los mensajes de mantenimiento del servicio porque le piden que sea proactivo para evitar problemas. <br/> <br/> **Planear el cambio:** le informa de los cambios realizados Microsoft 365 que pueden requerir que actúe para evitar interrupciones en el servicio. Por ejemplo, le haremos saber sobre los cambios en los requisitos del sistema o sobre las características que se están quitando. Intentamos proporcionar al menos 30 días de aviso de cualquier cambio que requiera que un administrador actúe para mantener el servicio funcionando con normalidad. <br/> <br/> **Mantenerse informado:** le informa sobre las características nuevas o actualizadas que estamos activar en su organización. Las características normalmente se anuncian primero en el [Microsoft 365 guía básica](https://go.microsoft.com/fwlink/?linkid=2070821). <br/><br/>También puede que le permita saber sobre el mantenimiento planeado de acuerdo con nuestro Contrato de nivel de servicio. El mantenimiento planeado puede dar lugar a tiempo de inatención, donde usted o sus usuarios no pueden acceder a Microsoft 365, una característica específica o un servicio como correo electrónico o OneDrive para la Empresa.  <br/> |
|Actuar por  <br/> |Solo tendremos fechas aquí si estamos realizando un cambio que requiere que hagas una acción antes de una fecha límite determinada. Dado que rara vez usamos **la ley por** columna, si ves algo aquí, debes prestarle más atención.  <br/> |
|Actualizado por última vez  <br/> |Fecha en que el mensaje se publicó o se actualizó por última vez.  <br/> |
|Id. de mensaje  <br/> |Microsoft realiza un seguimiento de nuestras publicaciones del Centro de mensajes por identificador de mensaje. Puede hacer referencia a este identificador si desea enviar comentarios o si llama al soporte técnico sobre un mensaje en particular.  <br/> |

### <a name="admin-roles-that-dont-have-access-to-the-message-center"></a>Roles de administrador que no tienen acceso al Centro de mensajes

- Administrador de cumplimiento
- Administrador de acceso condicional
- Aprobador de acceso lockBox de cliente
- Administradores de dispositivos
- Lectores de directorios
- Cuentas de sincronización de directorios
- Escritores de directorios
- Administrador de servicios de Intune
- Administrador de roles con privilegios
- Lector de informes

## <a name="give-feedback-on-a-post"></a>Enviar comentarios en una publicación

En el Centro de mensajes, puede seleccionar un mensaje para ver los detalles.

Si quiere enviar comentarios en el mensaje, en el panel de detalles seleccione el icono **Me gusta** o **No me gusta** en la parte inferior del panel de detalles del mensaje y proporcione comentarios opcionales en el cuadro de texto que aparece. La información personal no debe ser proporcionada. De manera opcional, **Puede ponerse en contacto conmigo para obtener estos comentarios** y después seleccionar **Enviar**.

## <a name="share-a-message"></a>Compartir un mensaje

¿Ve algún mensaje sobre el que otra persona debe tomar acción? Puede compartir el contenido del mensaje con cualquier usuario por correo electrónico:
  
1. Seleccione el mensaje para abrirlo y después seleccione **Compartir**.
  
2. Para compartir el mensaje, escriba hasta dos direcciones de correo electrónico separadas por dos puntos. Puede enviar a direcciones de correo electrónico de forma individual o de grupo. Opcionalmente, puede optar por recibir una copia del mensaje en el correo electrónico (el mensaje irá a su dirección de correo electrónico principal) o bien agregar un mensaje personal para proporcionar a los destinatarios más contexto.
  
3. Seleccione **Compartir** para enviar el correo electrónico.

## <a name="get-a-link"></a>Obtener un vínculo

¿Necesita realizar un seguimiento con otro administrador para asegurarse de que es consciente de un cambio y de tomar medidas? Puede generar un vínculo para compartir mediante correo electrónico o mensajería instantánea, por ejemplo, que conectará al usuario directamente a ese mensaje. La persona con la que comparta el vínculo debe tener acceso al Centro de mensajes. Consulte [Roles de administrador que no tienen acceso al Centro de mensajes](message-center.md#admin-roles-that-dont-have-access-to-the-message-center) para obtener más información.

1. Seleccione el mensaje para abrirlo.

2. Seleccione **Copiar vínculo**.

3. Use Ctrl+V o haga clic con el botón derecho y seleccione **Pegar** para insertar el vínculo en el documento que quiera.

## <a name="read-and-unread-states"></a>Estados leídos y no leídos

Todos los mensajes del Centro de mensajes no leídos se mostrarán en negrita. Al abrir un mensaje, se marca como leído. Usted puede marcar un mensaje como no leído.


- En la página principal del Centro de mensajes, seleccione el icono de puntos suspensivos **Más opciones** junto a un mensaje y, después, seleccione **Marcar como no leído**.

También puede abrir un mensaje y marcarlo como no leído en el panel de detalles.
  
## <a name="archive-and-restore"></a>Archivar y restaurar

Si ve un mensaje cuyo contenido no le concierne, o sobre el cual ya realizara una acción, puede archivar el mensaje para eliminarlo de la Bandeja de entrada. La vista que se ve en el centro de mensajes es específica de su cuenta de usuario, por lo que archivar desde su vista no afecta a otros administradores. Hay dos formas de archivar un mensaje.

- En la página principal del Centro de mensajes, seleccione un mensaje y después **Archivar** encima de la lista de mensajes.

- Abra el mensaje y después seleccione **Archivar** en la parte superior del panel de mensajes.

¿Necesita recuperar un mensaje archivado? No pasa nada.
  
1. Seleccione la pestaña **Archivar** en la parte superior del Centro de mensajes. Aparecerá una lista de mensajes archivados.

2. Seleccione el mensaje, haga clic en **Restaurar** y el mensaje se restaurará a la Bandeja de entrada.

## <a name="favorite-messages"></a>Mensajes favoritos

Para marcar un mensaje como favorito, mueva el puntero sobre el título del mensaje y verá una estrella de **Favorito** :::image type="icon" source="../../media/favorite-star.png" border="false"::: que puede seleccionar justo después del signo de puntos suspensivos **Más opciones**. Una vez que haya marcado los mensajes como favoritos, también puede ordenarlos y filtrarlos.

## <a name="scroll-messages-in-the-message-pane"></a>Desplazarse por los mensajes en el panel de mensajes

Al abrir un mensaje en un panel de lectura, puede usar las flechas de **arriba** y **abajo** :::image type="icon" source="../../media/updownarrows.png" border="false"::: de la parte superior del panel para ir al siguiente mensaje o al mensaje anterior de la lista.

## <a name="track-your-message-center-tasks-in-planner"></a>Seguir las tareas del Centro de mensajes en Planner

En el Centro de mensajes de Microsoft 365 no deja de llegarle información útil sobre los cambios en los servicios de Microsoft 365. Puede resultar difícil hacer un seguimiento de los cambios que requieren tareas, cuándo y por quién, y seguir cada tarea hasta su finalización. También puede anotar algo y etiquetarlo para comprobarlo más adelante. Puede hacer todo esto y más si sincroniza sus mensajes del Centro de administración de Microsoft 365 con Microsoft Planner. Para obtener más información, vea [Seguir sus tareas del centro de mensajes en Planner](/office365/planner/track-message-center-tasks-planner).

Para obtener información general sobre el Centro de mensajes, vea [Centro de mensajes en Microsoft 365](message-center.md). O bien, para obtener información sobre cómo establecer sus preferencias de idioma para habilitar la traducción automática para publicaciones del Centro de mensajes, vea [Traducción de idioma para publicaciones del Centro de mensajes](language-translation-for-message-center-posts.md). Si desea programar una forma alternativa para obtener información sobre el estado del servicio en tiempo real y las comunicaciones del Centro de mensajes, vea [Información general de la API de comunicaciones del servicio de Microsoft 365](/previous-versions/office/developer/o365-enterprise-developers/jj984343(v=office.15)).

## <a name="unsubscribe-from-message-center-emails"></a>Cancelar suscripción a correos electrónicos del Centro de mensajes

1. Los correos electrónicos de resumen están activados de forma predeterminada y se envían a su dirección de correo electrónico principal. Para dejar de recibir el resumen semanal, seleccione **Preferencias** y, a continuación, **Correo electrónico**.
    - Desmarte la **casilla Enviar una síntesis semanal de mis mensajes.**
    - La notificación por correo electrónico para actualizaciones principales es un control independiente. Si no desea recibir notificaciones por correo electrónico sobre actualizaciones principales, compruebe que la casilla **Enviarme mensajes** de correo electrónico para actualizaciones principales no esté activada.
    -   Para dejar de recibir avisos de correo electrónico sobre mensajes de privacidad de datos, compruebe que la casilla **Enviarme mensajes** de privacidad de datos no esté activada.  (Los mensajes de privacidad de datos no se incluyen en el resumen semanal).

2. Seleccione **Guardar** para conservar los cambios.<br/>

## <a name="related-content"></a>Contenido relacionado

[Configurar las opciones de versión estándar o dirigida](../manage/release-options-in-office-365.md) (artículo)

[Administrar qué Office aparecen en Novedades](../manage/show-hide-new-features.md) (artículo)

[Suscripciones empresariales y documentación de facturación](../../commerce/index.yml) (vínculos)
