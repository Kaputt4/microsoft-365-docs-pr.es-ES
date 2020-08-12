---
title: Explorador de amenazas y detecciones en tiempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo usar Explorer y detección en tiempo real en el centro de seguridad y &amp; cumplimiento para investigar y responder a las amenazas de manera eficaz y eficaz.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 635f7f32d16f18f49aa1920d82efd77bf27dc328
ms.sourcegitcommit: 3f9aac62e79799eca751ba9c8510aad1fc3afc5d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46641646"
---
# <a name="threat-explorer-and-real-time-detections"></a>Explorador de amenazas y detecciones en tiempo real

Si su organización tiene [office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) y dispone de los [permisos necesarios](#required-licenses-and-permissions), tiene tanto **exploradores** como **detecciones en tiempo real** (anteriormente *informes en tiempo real* , [vea lo nuevo](#new-features-in-threat-explorer-and-real-time-detections)!). En el centro de seguridad & cumplimiento, vaya a **Administración de amenazas**y, a continuación, elija **Explorador** _o_ **detecciones en tiempo real**.

|Con el plan ATP 2, verá:|Con el plan ATP 1, verá:|
|---|---|
|![Explorador de amenazas](../../media/threatmgmt-explorer.png)|![Detecciones en tiempo real](../../media/threatmgmt-realtimedetections.png)|
|

Con el explorador (o detecciones en tiempo real), dispone de un informe eficaz que permite al equipo de operaciones de seguridad investigar y responder a las amenazas de manera eficaz y eficaz. El informe es similar a la siguiente imagen:

![Ir al explorador de administración de amenazas \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Con este informe, puede:

- [Ver malware detectado por las características de seguridad de Microsoft 365](#see-malware-detected-in-email-by-technology)
- [Ver datos sobre direcciones URL de suplantación de identidad y hacer clic en veredicto](#view-data-about-phishing-urls-and-click-verdict)
- [Iniciar un proceso de investigación y respuesta automatizado desde una vista del explorador](#start-automated-investigation-and-response) (solo planeación ATP 2)
- ... [Investigue el correo electrónico malintencionado y mucho más](#more-ways-to-use-explorer-or-real-time-detections).

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>Experimentar mejoras en el explorador de amenazas y detecciones en tiempo real

Como parte de la mejora del proceso de búsqueda, hemos realizado algunas actualizaciones en el explorador de amenazas y en las detecciones en tiempo real. Estas son mejoras de "experiencia" y se centran en hacer que la experiencia de búsqueda sea más coherente. Estos cambios se describen a continuación:

- [Mejoras en la zona horaria](#timezone-improvements)
- [Actualizar en el proceso de actualización](#update-in-the-refresh-process)
- [Desglose del gráfico para agregar a los filtros](#chart-drilldown-to-add-to-filters)
- [En actualizaciones de información del producto](#in-product-information-updates)

### <a name="timezone-improvements"></a>Mejoras en la zona horaria

Se mostrará la zona horaria para los registros de correo electrónico dentro del portal, así como para los datos exportados. La zona horaria será visible en todas las experiencias como cuadrícula de correo electrónico, flotante de detalles, escala de tiempo del correo electrónico y correos electrónicos similares, de modo que la zona horaria del conjunto de resultados quede clara para el usuario.

![Ver la zona horaria en el explorador](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Actualizar en el proceso de actualización

Hemos recibido comentarios sobre la confusión con la actualización automática (por ejemplo, para la fecha, en cuanto cambia la fecha, la página se actualizará) y la actualización manual (para otros filtros). De forma similar, la eliminación de filtros conduce a la actualización automática, lo que provoca situaciones en las que el cambio de distintos filtros mientras se modifica la consulta puede provocar experiencias de búsqueda incoherentes. Para solucionar esto, estamos cambiando a un mecanismo de filtrado manual.
Desde el punto de vista de la experiencia, el usuario puede aplicar y quitar los distintos intervalos de filtros (desde el conjunto de filtros y la fecha) y hacer clic en el botón actualizar para filtrar los resultados una vez que se han realizado con la definición de la consulta. El botón actualizar también se ha actualizado para llamarlo claramente en la pantalla. También hemos actualizado la información sobre herramientas y la documentación del producto sobre este cambio.

![Haga clic en actualizar para filtrar los resultados](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Desglose del gráfico para agregar a los filtros

Ahora, podrá hacer clic en los valores de leyenda de gráfico para agregar ese valor como filtro. Tenga en cuenta que aún tendrá que hacer clic en el botón actualizar para filtrar los resultados como parte del cambio descrito anteriormente.

![Obtener detalles de los gráficos para filtrar](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>En actualizaciones de información del producto

También debe ver detalles adicionales dentro del producto. Por ejemplo, el número total de resultados de búsqueda dentro de la cuadrícula (vea a continuación), así como mejoras en las etiquetas, los mensajes de error y la información sobre herramientas, para proporcionar más información sobre los filtros, la experiencia de búsqueda y el conjunto de resultados.

![Ver información del producto](../../media/ProductInfo.png)


## <a name="new-features-in-real-time-detections"></a>Nuevas características en detecciones en tiempo real

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nuevas características del explorador de amenazas y detecciones en tiempo real

Se agregaron tres nuevas características al explorador de amenazas y detecciones en tiempo real:

- [Vista previa del encabezado de correo electrónico y descarga del cuerpo](#preview-email-header-and-download-email-body)
- [Escala de tiempo de correo electrónico](#email-timeline)
- [Exportar dirección URL haga clic en datos](#export-url-click-data)

Estas nuevas características se describen a continuación.

### <a name="preview-email-header-and-download-email-body"></a>Vista previa del encabezado de correo electrónico y descarga del cuerpo

La posibilidad de obtener una vista previa de un encabezado de correo electrónico y descargar el cuerpo del correo electrónico son nuevas características disponibles en el explorador de amenazas. Los administradores podrán analizar los encabezados y mensajes de correo electrónico descargados en busca de amenazas. Como la descarga de mensajes de correo electrónico puede arriesgar la exposición de la información, este proceso se controla mediante el control de acceso basado en roles (RBAC). Un nuevo rol, *vista previa*, debe agregarse a otro grupo de roles (como operaciones de seguridad o administrador de seguridad) para poder descargar los correos electrónicos y obtener una vista previa de los encabezados en la vista de todos los mensajes de correo electrónico.

Pero el explorador (y las detecciones en tiempo real) también agrega nuevos campos nuevos diseñados para proporcionarle una imagen más completa de dónde se encuentran los mensajes de correo electrónico. Parte del objetivo de este cambio es facilitar la búsqueda para los operadores de seguridad, pero el resultado neto es conocer la ubicación de los mensajes de correo electrónico con problemas de un vistazo.

¿Cómo se hace esto? El estado de entrega ahora se divide en dos columnas:

- **Acción de entrega** : ¿Cuál es el estado de este correo electrónico?
- **Ubicación de entrega** : ¿Dónde se distribuyó este correo electrónico como resultado?

La acción de entrega es la acción que se realiza en un correo electrónico debido a las directivas o detecciones existentes. Estas son las posibles acciones que puede realizar un correo electrónico:

|Pronuncia|Correo electrónico no deseado|Blocked|Sustitui|
|---|---|---|---|
|El correo electrónico se entregó a la bandeja de entrada o a la carpeta de un usuario y el usuario puede acceder a él directamente.|El correo electrónico se envió a la carpeta de correo no deseado o a la carpeta eliminada del usuario y el usuario tiene acceso a los mensajes de correo electrónico de esas carpetas.|Los correos electrónicos que se han puesto en cuarentena, que no se han podido realizar o se han perdido. El usuario no tiene acceso completamente a esto.|Cualquier correo electrónico en el que se reemplacen archivos adjuntos malintencionados por archivos. txt que indiquen que los datos adjuntos eran malintencionados.|

|Pronuncia|Correo electrónico no deseado|Blocked|Sustitui|
|---|---|---|---|
|El correo electrónico se entregó en la bandeja de entrada del usuario o en otra carpeta, y el usuario puede acceder a él directamente.|El correo electrónico se envió a la carpeta de correo no deseado o a la carpeta eliminada del usuario y el usuario tiene acceso a los mensajes de correo electrónico de esas carpetas.|Los mensajes de correo electrónico que se han puesto en cuarentena, que no se han producido o se han quitado, y que el usuario no puede obtener acceso a ellos.|Los mensajes de correo electrónico en los que los datos adjuntos malintencionados fueron reemplazados por archivos. txt que indican que los datos adjuntos eran malintencionados.|
|

Y esto es lo que el usuario puede ver y lo que no puede:

|Accesible para los usuarios finales|Inaccesibles para los usuarios finales|
|---|---|
|Pronuncia|Blocked|
|Correo electrónico no deseado|Sustitui|

Ubicación de entrega muestra los resultados de las directivas y detecciones que se ejecutan después de la entrega. Está vinculado a una acción de entrega. Este campo se agregó para proporcionar información sobre la acción tomada cuando se encuentra un mensaje problemático. Estos son los valores posibles de la ubicación de entrega:

- **Bandeja de entrada o carpeta**: el correo electrónico está en la bandeja de entrada o en una carpeta (según las reglas de correo electrónico).
- **Local o externa**: el buzón no existe en la nube pero es local.
- **Carpeta de correo no deseado**: el correo electrónico está en la carpeta de correo no deseado de un usuario.
- **Carpeta elementos eliminados**: el correo electrónico en la carpeta elementos eliminados de un usuario.
- **Quarantine**: el correo electrónico en cuarentena y no se encuentra en el buzón de un usuario.
- **Error**: el correo electrónico no pudo llegar al buzón.
- **Quitado**: el correo electrónico se pierde en algún lugar del flujo de correo.

### <a name="email-timeline"></a>Escala de tiempo de correo electrónico

La **escala de tiempo de correo electrónico** es otra nueva característica de Explorer destinada a conseguir la experiencia de búsqueda mejor para los administradores. Reduce el proceso aleatorio porque se dedica menos tiempo a comprobar las distintas ubicaciones para tratar de comprender el evento. Cuando se producen varios eventos en, o cerca de, al mismo tiempo en un correo electrónico, esos eventos se mostrarán en una vista escala de tiempo. De hecho, algunos eventos que se producen después de la entrega a su correo se capturarán en la columna "acción especial". La combinación de la información de la escala de tiempo de ese correo con la acción especial tomada en la entrega posterior del correo proporcionará a los administradores información sobre cómo funcionan sus directivas, dónde se enrutó el correo finalmente y, en algunos casos, qué es la evaluación final.

Para obtener más información acerca de la investigación de mensajes de correo electrónico malintencionados, consulte [investigar y corregir el correo electrónico malintencionado que se entregó en Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Exportar dirección URL haga clic en datos

Además, ahora podrá exportar informes para los clics de direcciones URL a Microsoft Excel para ver tanto el identificador de mensaje de red como el veredicto de clic, lo que hace que la tarea de comprender dónde se ha originado el tráfico en la dirección URL sea más fácil. Así es cómo funciona. A partir de la administración de amenazas en el inicio rápido de Office 365, haga clic en esta cadena:

**Explorador** \> **Ver phish** \> **Hace clic en** \> **Direcciones URL principales o clics principales en URL** \> **Haga clic en cualquier registro para abrir el control flotante de dirección URL**

Al hacer clic en una dirección URL de la lista, verá un nuevo botón exportar en el panel desplegable. Use este botón para mover datos a una hoja de cálculo de Excel para facilitar la creación de informes.

Puede acceder a la misma ubicación en el informe de detecciones en tiempo real de la siguiente manera:

**Explorador** \> Detecciones en tiempo **real** \> **Ver phish** \> **Direcciones URL** \> **Direcciones URL principales o clics principales** \> **Haga clic en cualquier registro para abrir el control flotante** \> de dirección URL **Vaya a la pestaña clics.**

> [!TIP]
> IDENTIFICADOR de mensaje de red asigna el clic de nuevo a correos específicos cuando se realiza la búsqueda en el explorador o en las herramientas de terceros asociadas mediante el identificador de mensaje de red. La búsqueda en el identificador de mensaje de red dará a los administradores el correo electrónico específico asociado con un resultado de clic. En la exportación, la identificación de la identificación del mensaje de red facilita un análisis más rápido y eficaz.

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Ver malware detectado en correo electrónico por tecnología

Supongamos que desea ver el malware detectado en el correo electrónico con la tecnología de Microsoft 365. Para ello, use la vista [Email > malware](threat-explorer-views.md#email--malware) de Explorer (o detecciones en tiempo real).

1. En el centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ), elija **Threat Management**  >  **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el menú **Ver** , elija malware de **correo electrónico**  >  **Malware**.

   ![Menú Ver para el explorador](../../media/ExplorerViewEmailMalwareMenu.png)

3. Haga clic en **remitente**y, a continuación, elija tecnología de **Basic**  >  **detección**básica.

   Las tecnologías de detección están ahora disponibles como filtros para el informe.

   ![Tecnologías de detección de malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Seleccione una opción y, a continuación, haga clic en el botón **Actualizar** para aplicar ese filtro.

   ![Tecnología de detección seleccionada](../../media/ExplorerEmailMalwareDetectionTechATP.png)

El informe se actualiza para mostrar el malware de resultados detectado en el correo electrónico, usando la opción de tecnología que seleccionó. Desde aquí, puede realizar análisis adicionales.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Ver datos sobre direcciones URL de suplantación de identidad y hacer clic en veredicto

Supongamos que desea ver los intentos de suplantación de identidad mediante direcciones URL en el correo electrónico, incluida una lista de direcciones URL que se han permitido, bloqueado y reemplazado. La identificación de las direcciones URL en las que se hizo clic requiere que se configuren los [vínculos seguros de ATP](atp-safe-links.md) . Asegúrese de haber configurado [las directivas de vínculos seguros de ATP](set-up-atp-safe-links-policies.md) para la protección del tiempo de clic y el registro de los veredictos de clics por medio de vínculos seguros de ATP.

Para revisar direcciones URL de phish en mensajes y hacer clic en direcciones URL en mensajes de Phish, use la vista de [correo electrónico > phish](threat-explorer-views.md#email--phish) de detecciones en tiempo real.

1. En el centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ), elija **Threat Management**  >  **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el menú **Ver** , elija phishing de **correo electrónico**  >  **Phish**.

   ![Menú Ver para el explorador](../../media/ExplorerViewEmailPhishMenu.png)

3. Haga clic en **remitente**y, a continuación, elija **direcciones URL**,  >  **haga clic en veredicto**.

4. Seleccione una o más opciones, como **bloqueada** y **bloque invalidado**y, a continuación, haga clic en el botón **Actualizar** que se encuentra en la misma línea que las opciones para aplicar ese filtro. (No actualice la ventana del explorador).

   ![Direcciones URL y haga clic en veredictos](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    El informe se actualiza para mostrar dos tablas de direcciones URL diferentes en la ficha dirección URL del informe:

   - Las **direcciones URL principales** son las que se encuentran en los mensajes que se han filtrado y la acción de entrega de correo electrónico se recuento para cada dirección URL. En la vista correo phish, esta lista normalmente contendrá direcciones URL legítimas. Los atacantes incluyen una mezcla de direcciones URL buenas y incorrectas en sus mensajes para intentar entregarlos, pero harán que los vínculos malintencionados sean más interesantes para el usuario hacer clic en. La tabla de direcciones URL se ordena por el recuento de correo electrónico total (pero tenga en cuenta que esta columna está oculta para simplificar la vista).

   - Los **clics principales** son las direcciones URL contenidas en vínculos seguros en las que se hizo clic, ordenadas por número total de clics (esta columna tampoco se muestra para simplificar la vista). Número total de recuentos por columna indique los vínculos seguros haga clic en recuento de veredictos para cada dirección URL con clic. En la vista de correo electrónico phish, estos son direcciones URL sospechosas o malintencionadas, pero pueden incluir direcciones URL que no son amenazas pero que se encuentran en mensajes de phish. Los clics de dirección URL en vínculos desajustados no se mostrarán aquí.

   Las dos tablas de direcciones URL muestran las direcciones URL principales en los mensajes de correo electrónico de suplantación por acción y ubicación de entrega, y muestran los clics de direcciones URL que se bloquearon (o visitaron a pesar de una advertencia) para que pueda comprender los posibles vínculos no válidos que han recibido los usuarios e interactuar con ellos por los usuarios. Desde aquí, puede realizar análisis adicionales. Por ejemplo, debajo del gráfico, puede ver las direcciones URL principales en mensajes de correo electrónico que estaban bloqueados en el entorno de su organización.

   ![URL del explorador que se bloquearon](../../media/ExplorerPhishClickVerdictURLs.png)

   Seleccione una dirección URL para ver información más detallada.

   > [!NOTE]
   > En el cuadro de diálogo de URL flotante, se quita el filtrado de los mensajes de correo electrónico para mostrar la vista completa de la exposición de la URL en el entorno. Esto le permite filtrar los mensajes de correo electrónico en el explorador a aquellos que le interesan, encontrar direcciones URL específicas que son posibles amenazas y, a continuación, ampliar su comprensión de la exposición de URL en su entorno (a través del cuadro de diálogo de detalles de URL) sin tener que agregar filtros de URL a la vista del explorador.


**Interpretación de los veredictos de distintos clics**

En los controles flotantes de dirección URL o de correo electrónico, los clics principales, así como en nuestras experiencias de filtrado, verá valores de clic diferentes como parte de su experiencia de búsqueda. A continuación se muestran los valores posibles de los veredictos de clic y su interpretación:

- **None**: no se ha podido capturar el veredicto para la dirección URL. Es posible que el usuario haya acpulsado a través de la dirección URL.
- Se **permite**: el usuario tiene permiso para navegar a la dirección URL.
- **Bloqueado**: se ha bloqueado el usuario para navegar a la dirección URL.
- **Veredicto pendiente**: se presentó el usuario con la página detonación pendiente.
- **Bloqueado invalidado**: se ha bloqueado al usuario para que navegue a la dirección URL; sin embargo, el usuario overrode el bloque para desplazarse a la dirección URL.
- Se **omite el veredicto pendiente**: se ha presentado la página de detonación al usuario. sin embargo, el usuario overrode? a la p? gina para navegar a la direcci? n URL.
- **Error**: se ha presentado al usuario la página de error. Esto también puede significar que se ha producido un error al capturar el veredicto.
- **Error**: se ha producido una excepción desconocida al capturar el veredicto. Es posible que el usuario haya acpulsado a través de la dirección URL. 

## <a name="review-email-messages-reported-by-users"></a>Revisar los mensajes de correo electrónico enviados por los usuarios

Supongamos que desea ver los mensajes de correo electrónico que los usuarios de la organización han notificado como correo no deseado, correo no deseado o suplantación de identidad mediante el [complemento de mensajes de informe para Outlook y Outlook en la web](enable-the-report-message-add-in.md). Para ello, use el [correo electrónico > vista de envíos](threat-explorer-views.md#email--submissions) del explorador (o detecciones en tiempo real).

1. En el centro de seguridad & cumplimiento ( [https://protection.office.com](https://protection.office.com) ), elija **Threat Management**  >  **Explorer** (o **detecciones en tiempo real**). (En este ejemplo se usa el explorador).

2. En el menú **Ver** , elija **Email**  >  **envíos**de correo electrónico.

   ![Menú Ver para el explorador](../../media/explorer-view-menu-email-user-reported.png)

3. Haga clic en **remitente**y, a continuación, elija tipo de **Basic**  >  **Informe**básico.

4. Seleccione una opción, como **phish**y, a continuación, haga clic en el botón **Actualizar** .

   ![Phish notificados por el usuario](../../media/EmailUserReportedReportType.png)

El informe se actualiza para Mostrar datos sobre los mensajes de correo electrónico que las personas de su organización han notificado como un intento de suplantación de identidad. Puede usar esta información para realizar análisis adicionales y, si es necesario, ajustar las [directivas antiphishing de ATP](configure-atp-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Iniciar investigación y respuesta automatizadas

> [!NOTE]
> Las capacidades de investigación y respuesta automatizadas están disponibles en **office 365 ATP plan 2** y **Office 365 E5**.

(Nueva) La [investigación y la respuesta automatizadas](automated-investigation-response-office.md) pueden guardar el equipo de operaciones de seguridad con mucho tiempo y esfuerzo para investigar y mitigar cyberattacks. Además de configurar alertas que pueden desencadenar una guía de seguridad, puede iniciar un proceso de investigación y respuesta automatizado desde una vista en el explorador.

Para obtener más información sobre esto, consulte [ejemplo: un administrador de seguridad desencadena una investigación desde el explorador](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Más formas de usar Explorer (o detecciones en tiempo real)

Además de los escenarios descritos en este artículo, tiene muchas más opciones de informes disponibles con el explorador (o detecciones en tiempo real).

- [Buscar e investigar el correo electrónico malintencionado que se ha entregado](investigate-malicious-email-that-was-delivered.md)
- [Ver archivos malintencionados detectados en SharePoint Online, OneDrive y Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Obtener información general sobre las vistas en el explorador de amenazas (y detecciones en tiempo real)](threat-explorer-views.md)
- [Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarios

Debe tener [Office 365 ATP](office-365-atp.md) para obtener detecciones de Internet Explorer o en tiempo real.

- Explorer se incluye en el plan 2 de ATP de Office 365.
- El informe de detecciones en tiempo real se incluye en el plan 1 de ATP de Office 365.
- Planee la asignación de licencias para todos los usuarios que deberían estar protegidos por Office 365 ATP. (El explorador o detecciones en tiempo real muestra los datos de detección de los usuarios con licencia).

Para ver y usar el explorador o las detecciones en tiempo real, debe tener los permisos adecuados, como los que se han concedido a un administrador de seguridad o un lector de seguridad.

- Para el centro de seguridad &amp; y cumplimiento, debe tener asignada una de las siguientes funciones:

  - Administración de la organización
  - Administrador de seguridad (puede asignarse en el centro de administración de Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Lector de seguridad

- Para Exchange Online, debe tener una de las siguientes funciones asignadas en el centro de administración de Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) o con cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Administración de la organización
  - Administración de organización de solo lectura
  - Rol Destinatarios con permiso de vista
  - Administración de cumplimiento

Para obtener más información acerca de los roles y los permisos, vea los siguientes recursos:

- [Permisos en el centro de seguridad y &amp; cumplimiento](permissions-in-the-security-and-compliance-center.md)
- [Permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Algunas diferencias entre el explorador de amenazas y las detecciones en tiempo real

- El informe de **detecciones en tiempo real** está disponible en Office 365 ATP plan 1, mientras que **Threat Explorer** está disponible en Office 365 ATP plan 2.
- El informe de **detecciones en tiempo real** permite ver las detecciones en tiempo real. El **Explorador de amenazas** hace esto también, pero también le permite ver más detalles de un ataque determinado.
- La vista **todo el correo electrónico** está disponible en el **Explorador de amenazas** (y no se encuentra en el informe de **detecciones en tiempo real** ).
- En el **Explorador de amenazas**se incluyen más funciones de filtrado y acciones disponibles.

Para obtener más información, consulte [Office 365 ATP Service Description: disponibilidad de características en los planes de protección contra amenazas avanzada (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

