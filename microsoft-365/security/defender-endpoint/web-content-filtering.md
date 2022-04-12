---
title: Filtrado de contenido web
description: Use el filtrado de contenido web en Microsoft Defender para punto de conexión para realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido.
keywords: protección web, protección contra amenazas web, exploración web, supervisión, informes, tarjetas, lista de dominios, seguridad, phishing, malware, vulnerabilidad de seguridad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 01000e08153e96042e6873dc45fcb0627ea82e47
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782993"
---
# <a name="web-content-filtering"></a>Filtrado de contenido web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

El filtrado de contenido web forma parte de las funcionalidades de [protección web](web-protection-overview.md) de Microsoft Defender para punto de conexión. Permite a su organización realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido. Muchos de estos sitios web, aunque no son malintencionados, pueden ser problemáticos debido a las regulaciones de cumplimiento, el uso del ancho de banda u otros problemas.

Configure directivas en los grupos de dispositivos para bloquear determinadas categorías. El bloqueo de una categoría impide que los usuarios de grupos de dispositivos especificados accedan a las direcciones URL asociadas a la categoría. Para cualquier categoría que no esté bloqueada, las direcciones URL se auditan automáticamente. Los usuarios pueden acceder a las direcciones URL sin interrupciones y recopilará estadísticas de acceso para ayudar a crear una decisión de directiva más personalizada. Los usuarios verán una notificación de bloque si un elemento de la página que están viendo realiza llamadas a un recurso bloqueado.

El filtrado de contenido web está disponible en los principales exploradores web, con bloques realizados por Windows Defender SmartScreen (Microsoft Edge) y Network Protection (Chrome, Firefox, Brave y Opera). Para obtener más información sobre la compatibilidad con exploradores, consulte la sección requisitos previos.

## <a name="benefits-of-web-content-filtering"></a>Ventajas del filtrado de contenido web

- Se impide que los usuarios accedan a sitios web en categorías bloqueadas, ya sea que naveguen de forma local o fuera.

- El equipo de seguridad puede implementar directivas cómodamente en grupos de usuarios mediante grupos de dispositivos definidos en [Microsoft Defender para punto de conexión configuración de control de acceso basado en rol](/microsoft-365/security/defender-endpoint/rbac).

- El equipo de seguridad puede acceder a los informes web en la misma ubicación central, con visibilidad sobre los bloques reales y el uso web.

## <a name="prerequisites"></a>Requisitos previos

Antes de probar esta característica, asegúrese de cumplir los siguientes requisitos:

- La suscripción incluye una de las siguientes opciones: Windows 10 Enterprise E5, Microsoft 365 E5, Seguridad de Microsoft 365 E5, Microsoft 365 E3 o Microsoft Defender para punto de conexión licencia independiente. 

- Tiene acceso a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>.

- Los dispositivos de la organización ejecutan Windows 10 actualización de aniversario (versión 1607) o posterior, o Windows 11 con las [actualizaciones antivirus o antimalware más recientes](manage-updates-baselines-microsoft-defender-antivirus.md).

- Windows Defender SmartScreen y Network Protection están habilitados en los dispositivos de la organización.

## <a name="data-handling"></a>Control de datos

Los datos se almacenan en la región seleccionada como parte de la [configuración de control de datos de Microsoft Defender para punto de conexión](data-storage-privacy.md). Los datos no abandonarán el centro de datos de esa región. Además, sus datos no se compartirán con terceros, incluidos nuestros proveedores de datos.

## <a name="turn-on-web-content-filtering"></a>Activar el filtrado de contenido web

En el panel de navegación izquierdo de <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>, seleccione **Configuración** \> **Características avanzadas** **generales** \> de **puntos** \> de conexión. Desplácese hacia abajo hasta que vea la entrada para **el filtrado de contenido web**. Cambie el botón de alternancia a Las **preferencias** **Activado** y Guardar.

### <a name="configure-web-content-filtering-policies"></a>Configuración de directivas de filtrado de contenido web

Las directivas de filtrado de contenido web especifican qué categorías de sitio están bloqueadas en qué grupos de dispositivos. Para administrar las directivas, vaya a **Configuración** \> **Filtrado de contenido web** de **puntos** \> de conexión (en **Reglas**).

Las directivas se pueden implementar para bloquear cualquiera de las siguientes categorías primarias o secundarias:

<details>
<summary>Contenido para adultos</summary>

**Cultos**: Sitios relacionados con grupos o movimientos cuyos miembros demuestran pasión por un sistema de creencias que es diferente de los que son socialmente aceptados. 

**Juegos de azar**: juegos de azar en línea y sitios que promueven las habilidades y la práctica del juego.

**Desnudez**: sitios que proporcionan imágenes o vídeos totalmente frontales y semi-desnudos, normalmente en forma artística, y pueden permitir la descarga o venta de dichos materiales.

**Pornografía/ Sexualmente explícita**: sitios que contienen contenido sexualmente explícito en un formato textual o basado en imágenes. Cualquier forma de material orientado sexualmente también se enumera aquí.

**Educación sexual**: Sitios que analizan el sexo y la sexualidad de forma informativa y no voyeurística, incluyendo sitios que proporcionan educación sobre reproducción humana y anticoncepción, sitios que ofrecen consejos sobre la prevención de infecciones por enfermedades sexuales, y sitios que ofrecen consejos sobre asuntos de salud sexual.

**Insípido**: Sitios orientados a contenidos inadecuados para que los escolares puedan ver o que un empleador se sienta incómodo con el acceso de su personal, pero no necesariamente violento o pornográfico.

**Violencia**: Sitios que muestran o promueven contenido relacionado con la violencia contra humanos o animales.

</details>

<details>
<summary>Ancho de banda alto</summary>

**Descargar sitios**: sitios cuya función principal es permitir a los usuarios descargar contenido multimedia o programas, como programas informáticos.

**Uso compartido de** imágenes: sitios que se usan principalmente para buscar o compartir fotos, incluidos los que tienen aspectos sociales.

**Punto a punto**: sitios que hospedan software punto a punto (P2P) o facilitan el uso compartido de archivos mediante el software P2P.

**Streaming multimedia & descargas**: sitios cuya función principal es la distribución de medios de streaming o sitios que permiten a los usuarios buscar, ver o escuchar contenido multimedia de streaming.
  
</details>

<details>
<summary>Responsabilidad legal</summary>

**Imágenes de abuso infantil**: sitios que incluyen imágenes de abuso infantil o pornografía. 

**Actividad criminal**: Sitios que dan instrucciones, consejos o promoción de actividades ilegales.

**Piratería**: Sitios que proporcionan recursos para el uso ilegal o cuestionable de software o hardware informático, incluidos los sitios que distribuyen material protegido por derechos de autor que se ha descifrado.

**Odio & intolerancia**: Sitios que promueven opiniones agresivas, degradantes o abusivas sobre cualquier sección de la población que pueda identificarse por raza, religión, género, edad, nacionalidad, discapacidad física, situación económica, preferencias sexuales o cualquier otra elección de estilo de vida.

**Drogas ilegales**: Sitios que venden sustancias ilegales o controladas, promueven el abuso de sustancias o venden parafernalia relacionada.

**Software ilegal**: sitios que contienen o promueven el uso de malware, spyware, botnets, estafas de phishing o piratería & robo de derechos de autor.

**Trampas en la escuela**: sitios relacionados con plagio o trampas en la escuela. 

**Autolesión**: sitios que promueven autolesión, incluidos sitios de ciberacoso que contienen mensajes abusivos o amenazantes hacia los usuarios.

**Armas**: cualquier sitio que vende armas o promueve el uso de armas, incluyendo pero no limitado a armas, cuchillos y municiones.

</details>

<details>
<summary>Ocio</summary>

**Chat**: sitios que son principalmente salas de chat basadas en web.

**Juegos**: Sitios relacionados con videojuegos o juegos de ordenador, incluyendo sitios que promueven juegos a través de hospedaje servicios en línea o información relacionada con juegos.

**Mensajería instantánea**: sitios que se pueden usar para descargar software de mensajería instantánea o mensajería instantánea basada en cliente.

**Professional red**: sitios que proporcionan servicios de red profesionales.

**Redes sociales**: sitios que proporcionan servicios de redes sociales.

**Correo electrónico basado en web**: sitios que ofrecen servicios de correo web.
  
</details>

<details>
<summary>Uncategorized</summary>

**Dominios recién registrados**: sitios que se han registrado recientemente en los últimos 30 días y que aún no se han movido a otra categoría.

**Dominios estacionados**: sitios que no tienen contenido o están estacionados para su uso posterior.
  
**NOTA**: Uncategorized solo contiene dominios recién registrados y dominios estacionados, y no incluye todos los demás sitios fuera de estas categorías.
  
</details>

### <a name="create-a-policy"></a>Crear una directiva

Para agregar una nueva directiva, siga estos pasos:

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, elija **Configuración** >  **Filtro de** >  contenido web **+ Agregar directiva**.

2. Especifique un nombre.

3. Seleccione las categorías que desea bloquear. Use el icono expandir para expandir por completo cada categoría primaria y seleccionar categorías de contenido web específicas.

4. Especifique el ámbito de la directiva. Seleccione los grupos de dispositivos para especificar dónde aplicar la directiva. Solo se impedirá que los dispositivos de los grupos de dispositivos seleccionados accedan a sitios web de las categorías seleccionadas.

5. Revise el resumen y guarde la directiva. La actualización de la directiva puede tardar hasta 2 horas en aplicarse a los dispositivos seleccionados.

> [!NOTE]
>
> - Puede implementar una directiva sin seleccionar ninguna categoría en un grupo de dispositivos. Esta acción creará una directiva de solo auditoría para ayudarle a comprender el comportamiento del usuario antes de crear una directiva de bloque.
> - Si va a quitar una directiva o cambiar grupos de dispositivos al mismo tiempo, esto podría provocar un retraso en la implementación de directivas.
> - El bloqueo de la categoría "Sin categoría" puede dar lugar a resultados inesperados y no deseados.

## <a name="end-user-experience"></a>Experiencia del usuario final

La experiencia de bloqueo para exploradores compatibles con terceros la proporciona Network Protection, que proporciona un mensaje de nivel de sistema que notifica al usuario una conexión bloqueada. Para obtener una experiencia más fácil de usar en el explorador, considere la posibilidad de usar Microsoft Edge.

### <a name="allow-specific-websites"></a>Permitir sitios web específicos

Es posible invalidar la categoría bloqueada en el filtrado de contenido web para permitir un único sitio mediante la creación de una directiva de indicadores personalizada. La directiva de indicador personalizado reemplazará a la directiva de filtrado de contenido web cuando se aplique al grupo de dispositivos en cuestión.

Para definir un indicador personalizado, siga estos pasos:

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, vaya a **Configuración** \> **dirección URL** **de indicadores** \> \> de **puntos de conexión** o **Agregar elemento de** dominio\>.

2. Escriba el dominio del sitio.

3. Establezca la acción de directiva en **Permitir**.

### <a name="dispute-categories"></a>Categorías de disputas

Si encuentra un dominio que se ha clasificado incorrectamente, puede disputar la categoría directamente desde el portal.

Para disputar la categoría de un dominio, vaya a **Informes** \> Dominios de **detalles** \> de filtrado de contenido **web de protección** \> web **.** En la pestaña dominios de los informes de filtrado de contenido web, verá los puntos suspensivos junto a cada uno de los dominios. Mantenga el puntero sobre estos puntos suspensivos y seleccione **Categoría de disputa**.

Se abrirá un panel donde puede seleccionar la prioridad y agregar más detalles, como la categoría sugerida para la recategorización. Una vez completado el formulario, seleccione **Enviar**. Nuestro equipo revisará la solicitud dentro de un día laborable. Para desbloquear inmediatamente, cree un [indicador de permiso personalizado](indicator-ip-domain.md).

## <a name="web-content-filtering-cards-and-details"></a>Tarjetas y detalles de filtrado de contenido web

Seleccione Protección **web** **de informes** \> para ver tarjetas con información sobre el filtrado de contenido web y la protección contra amenazas web. Las tarjetas siguientes proporcionan información de resumen sobre el filtrado de contenido web.

### <a name="web-activity-by-category"></a>Actividad web por categoría

En esta tarjeta se enumeran las categorías de contenido web principales con el mayor aumento o disminución en el número de intentos de acceso. Comprenda los cambios drásticos en los patrones de actividad web de su organización de los últimos 30 días, 3 meses o 6 meses. Seleccione un nombre de categoría para ver más información.

En los primeros 30 días de uso de esta característica, es posible que la organización no tenga suficientes datos para mostrar esta información.

:::image type="content" source="images/web-activity-by-category600.png" alt-text="La actividad web por tarjeta de categoría" lightbox="images/web-activity-by-category600.png":::

### <a name="web-content-filtering--summary-card"></a>Tarjeta de resumen de filtrado de contenido web

Esta tarjeta muestra la distribución de los intentos de acceso bloqueado en las distintas categorías de contenido web primario. Seleccione una de las barras coloreadas para ver más información sobre una categoría web primaria específica.

:::image type="content" source="images/web-content-filtering-summary.png" alt-text="Tarjeta de resumen de filtrado de contenido web" lightbox="images/web-content-filtering-summary.png":::

### <a name="web-activity-summary-card"></a>Tarjeta de resumen de actividad web

Esta tarjeta muestra el número total de solicitudes de contenido web en todas las direcciones URL.

:::image type="content" source="images/web-activity-summary.png" alt-text="Tarjeta de resumen de actividad web" lightbox="images/web-activity-summary.png":::

### <a name="view-card-details"></a>Visualización de los detalles de la tarjeta

Puede acceder a los **detalles del informe** de cada tarjeta seleccionando una fila de tabla o una barra de color del gráfico de la tarjeta. La página de detalles del informe de cada tarjeta contiene amplios datos estadísticos sobre categorías de contenido web, dominios de sitio web y grupos de dispositivos.

:::image type="content" source="images/web-protection-report-details.png" alt-text="Detalles del informe de protección web" lightbox="images/web-protection-report-details.png":::

- **Categorías web**: enumera las categorías de contenido web que han tenido intentos de acceso en su organización. Seleccione una categoría específica para abrir un control flotante de resumen.

- **Dominios**: enumera los dominios web a los que se ha accedido o bloqueado en la organización. Seleccione un dominio específico para ver información detallada sobre ese dominio.

- **Grupos de dispositivos**: enumera todos los grupos de dispositivos que han generado actividad web en su organización.

Use el filtro de intervalo de tiempo en la parte superior izquierda de la página para seleccionar un período de tiempo. También puede filtrar la información o personalizar las columnas. Seleccione una fila para abrir un panel flotante con más información sobre el elemento seleccionado.

### <a name="known-issues-and-limitations"></a>Problemas y limitaciones conocidos

Solo se admite Microsoft Edge si la configuración del sistema operativo del dispositivo es Server (**cmd** \> **Systeminfo** \> **OS Configuration**). La protección de red solo se admite en el modo inspeccionar en dispositivos de servidor, que es responsable de proteger el tráfico entre exploradores de terceros compatibles.

Solo se admiten Microsoft Edge y Protección de red no se admite en Windows 10 hosts de sesión múltiple de Azure Virtual Desktop.

Protección de red no admite actualmente la inspección SSL, lo que puede dar lugar a que algunos sitios estén permitidos por el filtrado de contenido web que normalmente se bloquearía. Los sitios se permitirían debido a la falta de visibilidad del tráfico cifrado después de que se haya producido el protocolo de enlace TLS y a la imposibilidad de analizar determinadas redirecciones.  Esto incluye redireccionamientos desde algunas páginas de inicio de sesión de correo basadas en web a la página del buzón. Como solución alternativa aceptada, puede crear un indicador de bloque personalizado para la página de inicio de sesión para asegurarse de que ningún usuario pueda acceder al sitio. Tenga en cuenta que esto puede bloquear su acceso a otros servicios asociados con el mismo sitio web. 

## <a name="see-also"></a>Vea también

- [Introducción a protección web](web-protection-overview.md)
- [Protección contra amenazas web](web-threat-protection.md)
- [Supervisar la seguridad web](web-protection-monitoring.md)
- [Responder a amenazas web](web-protection-response.md)
- [Requisitos para la protección de red](web-content-filtering.md)
