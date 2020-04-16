---
title: Perfil de dispositivo en el portal de seguridad 365 de Microsoft
description: Ver los niveles de riesgo y exposición de un dispositivo en la organización. Analice las amenazas pasadas y presentes y proteja el dispositivo con las actualizaciones más recientes.
keywords: seguridad, malware, Microsoft 365, M365, protección contra amenazas de Microsoft, MTP, centro de seguridad, ATP de Microsoft defender, Office 365 ATP, ATP de Azure, página de dispositivo, perfil de dispositivo, página de equipo, perfil de máquina
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: db6109fb73f0e208ab4403e2469bc955a1a01b38
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "43517073"
---
# <a name="device-profile-page"></a>Página de Perfil de dispositivo

El portal de seguridad 365 de Microsoft proporciona páginas de Perfil de dispositivo para que pueda evaluar rápidamente el estado y el estado de los dispositivos de la red.

> [!IMPORTANT]
> La página de Perfil de dispositivo puede aparecer ligeramente diferente en función de si el dispositivo está inscrito en ATP de Microsoft defender, en ATP de Azure o en ambas.

Si el dispositivo está inscrito en ATP de Microsoft defender, también puede usar la página Perfil de dispositivo para realizar algunas tareas de seguridad comunes.

## <a name="navigating-the-device-profile-page"></a>Navegación por la página de Perfil de dispositivo

La página de perfil se divide en varias secciones generales.

![Imagen de la página de Perfil de dispositivo con (1) área de la ficha (2) sidebar y (3) acciones resaltadas en rojo](../../media/mtp-device-profile/hybrid-device-overall.png)

La barra lateral (1) enumera los detalles básicos sobre el dispositivo.

El área de contenido principal (2) contiene pestañas que se pueden alternar para ver distintos tipos de información sobre el dispositivo.

Si el dispositivo está inscrito en ATP de Microsoft defender, también verá una lista de acciones de respuesta (3). Las acciones de respuesta le permiten realizar tareas comunes relacionadas con la seguridad.

## <a name="sidebar"></a>-

Junto al área de contenido principal de la página de perfil del dispositivo se encuentra la barra lateral.

![Imagen de la pestaña de la barra lateral para Perfil de dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

La barra lateral muestra el nombre completo y el nivel de exposición del dispositivo. También se proporciona información básica importante en subsecciones pequeñas que se pueden alternar abiertas o cerradas, por ejemplo:

* **Etiquetas** : cualquier ATP de Microsoft defender, ATP de Azure o etiquetas personalizadas asociadas con el dispositivo. Las etiquetas de Azure ATP no se pueden editar.
* **Información de seguridad** : incidentes abiertos y alertas activas. Los dispositivos inscritos en ATP de Microsoft defender también mostrarán el nivel de exposición y el nivel de riesgo.

> [!TIP]
> El nivel de exposición está relacionado con la medida en que el dispositivo cumple con las recomendaciones de seguridad, mientras que el nivel de riesgo se calcula en función de una serie de factores, incluidos los tipos y la gravedad de las alertas activas.

* **Detalles del dispositivo** : dominio, so, marca de tiempo para cuando se ha visto el dispositivo por primera vez, direcciones IP y recursos. Los dispositivos inscritos en Microsoft defender ATP también muestran el estado de mantenimiento. Los dispositivos inscritos en ATP de Azure mostrarán el nombre SAM y una marca de hora para cuando se creó el dispositivo por primera vez.
* **Actividad de red** : marcas de tiempo para la primera y última vez que el dispositivo se ve en la red.
* **Datos del directorio** (*solo para dispositivos inscritos en ATP de Azure*): marcas [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) , [SPN](https://docs.microsoft.com/windows/win32/ad/service-principal-names)y pertenencias a grupos.

## <a name="response-actions"></a>Acciones de respuesta

Las acciones de respuesta ofrecen una forma rápida de defenderse y analizar las amenazas.

![Imagen de la barra de acciones para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * [Las acciones de respuesta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) solo están disponibles si el dispositivo está inscrito en ATP de Microsoft defender.
> * Los dispositivos inscritos en ATP de Microsoft defender pueden mostrar diferentes números de acciones de respuesta según el sistema operativo del dispositivo y el número de versión.

Las acciones disponibles en la página de Perfil de dispositivo incluyen:

* **Administrar etiquetas** : actualiza las etiquetas personalizadas que hayas aplicado a este dispositivo.
* **Aislar dispositivo** : aísla el dispositivo de la red de su organización y conserva la conexión con la protección contra amenazas avanzada de Microsoft defender. Puede elegir permitir que se ejecuten Outlook, Teams y Skype empresarial mientras el dispositivo está aislado, con fines de comunicación.
* **Centro de actividades** : ver el estado de las acciones enviadas. Solo está disponible si ya se ha seleccionado otra acción.
* **Restringir la ejecución** de la aplicación: evita que se ejecuten las aplicaciones que Microsoft no ha firmado.
* **Ejecutar detección de virus** : actualiza las definiciones de antivirus de Windows Defender y ejecuta inmediatamente un examen de antivirus. Elija entre análisis rápido o análisis completo.
* **Recopilar el paquete de investigación** : recopila información sobre el dispositivo. Una vez completada la investigación, puede descargarla.
* **Iniciar sesión de respuesta activa** : carga un shell remoto en el dispositivo para [investigaciones de seguridad en profundidad](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).
* **Iniciar investigación automatizada** : [investiga y corrige](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)automáticamente las amenazas. Aunque puede desencadenar de forma manual investigaciones automáticas para que se ejecuten desde esta página, [algunas directivas de alertas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) desencadenan investigaciones automáticas por su cuenta.
* **Centro de actividades** : muestra información sobre las acciones de respuesta que se están ejecutando actualmente.

## <a name="tabs-section"></a>Sección Tabulaciones

Las fichas de Perfil de dispositivo permiten alternar entre una introducción a los detalles de seguridad del dispositivo y las tablas que contienen una lista de alertas.

Los dispositivos inscritos en ATP de Microsoft defender también mostrarán pestañas que incluyen una escala de tiempo, una lista de recomendaciones de seguridad, un inventario de software, una lista de vulnerabilidades descubiertas y los KB (actualizaciones de seguridad) que faltan.

### <a name="overview-tab"></a>Ficha Información general

La pestaña predeterminada es **información general**. Proporciona una visión rápida del hecho de seguridad más importante sobre el dispositivo.

![Imagen de la ficha Información general de Perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

Aquí puede ver rápidamente las alertas activas del dispositivo y cualquier usuario que haya iniciado sesión en ese momento.

Si el dispositivo está inscrito en ATP de Microsoft defender, también verá el nivel de riesgo del dispositivo y los datos disponibles en las evaluaciones de seguridad. Las evaluaciones de seguridad describen el nivel de exposición del dispositivo, proporcionan recomendaciones de seguridad y enumeran el software afectado y las vulnerabilidades detectadas.

### <a name="alerts-tab"></a>Ficha Alertas

La pestaña **alertas** contiene una lista de las alertas que se han generado en el dispositivo, tanto de ATP de Azure como de ATP de Microsoft defender.

![Imagen de la pestaña de alertas para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

Puede personalizar el número de elementos mostrados, así como qué columnas se muestran para cada elemento. El comportamiento predeterminado es enumerar treinta elementos por página.

Las columnas de esta pestaña incluyen información sobre la gravedad de la amenaza que desencadenó la alerta, así como el estado, el estado de investigación y a quién se ha asignado la alerta.

La columna *entidades afectadas* se refiere al dispositivo (entidad) cuyo perfil está viendo actualmente, además de otros dispositivos de la red que se ven afectados.

Al seleccionar un elemento de esta lista, se abrirá un control flotante que contiene todavía más información sobre la alerta seleccionada.

Esta lista se puede filtrar por gravedad, estado o a quién se ha asignado la alerta.

### <a name="timeline-tab"></a>Ficha escala de tiempo

La ficha **escala de tiempo** incluye un gráfico cronológico interactivo de todos los eventos que se producen en el dispositivo. Moviendo el área resaltada del gráfico a la izquierda o a la derecha, puede ver los eventos durante distintos períodos de tiempo. También puede elegir un intervalo de fechas personalizado en el menú desplegable entre el gráfico interactivo y la lista de eventos.

Debajo del gráfico hay una lista de eventos para el intervalo de fechas seleccionado.

![Imagen de la pestaña escala de tiempo para Perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

El número de elementos mostrados y las columnas de la lista se pueden personalizar. Las columnas predeterminadas muestran el tiempo del evento, el usuario activo, el tipo de acción, las entidades (procesos) y la información adicional sobre el evento.

Al seleccionar un elemento de esta lista, se abrirá un control flotante que muestra un gráfico de entidades de evento, donde se muestran los procesos primarios y secundarios implicados en el evento.

La lista se puede filtrar por el tipo específico de evento; por ejemplo, eventos de registro o eventos de pantalla inteligente.

La lista también se puede exportar a un archivo CSV, para su descarga. Aunque el archivo no está limitado por el número de eventos, el intervalo de tiempo máximo que puede elegir para exportar es de siete días.

### <a name="security-recommendations-tab"></a>Ficha recomendaciones de seguridad

La ficha **recomendaciones de seguridad** enumera las acciones que puede realizar para proteger el dispositivo. Al seleccionar un elemento de esta lista, se abrirá un control flotante donde puede obtener instrucciones sobre cómo aplicar la recomendación.

![Imagen de la ficha recomendaciones de seguridad para Perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

Como en las pestañas anteriores, el número de elementos que se muestran por página, así como las columnas que están visibles, se pueden personalizar.

La vista predeterminada incluye columnas que detallan las debilidades de seguridad tratadas, la amenaza asociada, el componente o software relacionado con la amenaza, entre otros. Los elementos se pueden filtrar por el estado de la recomendación.

### <a name="software-inventory"></a>Inventario de software

La ficha **inventario de software** enumera el software instalado en el dispositivo.

![Imagen de la ficha inventario de software para Perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

La vista predeterminada muestra el proveedor de software, el número de versión instalado, el número de debilidades de software conocidos, la información sobre amenazas, el código de producto y las etiquetas. El número de elementos mostrados y las columnas que se muestran pueden personalizarse.

Al seleccionar un elemento de esta lista, se abre un control flotante que contiene más detalles sobre el software seleccionado, así como la ruta de acceso y la marca de tiempo de la última vez que se encontró el software.

Esta lista se puede filtrar por código de producto.

### <a name="discovered-vulnerabilities-tab"></a>Ficha vulnerabilidades detectadas

En la ficha **vulnerabilidades detectadas** se muestran las vulnerabilidades y los puntos débiles comunes (CVE) que pueden afectar al dispositivo.

![Imagen de la pestaña vulnerabilidades detectadas para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

La vista predeterminada muestra la gravedad de CVE, la puntuación de vulnerabilidad común (CVS), el software relacionado con el CVE, Cuándo se publicó el CVE, Cuándo se actualizó por última vez el CVE y las amenazas asociadas con el CVE.

Como en las pestañas anteriores, se puede personalizar el número de elementos que se muestran y las columnas que son visibles.

Al seleccionar un elemento de esta lista, se abrirá un control flotante que describe el CVE.

### <a name="missing-kbs"></a>KB faltantes

La ficha **KB que falta** muestra una lista de las actualizaciones de Microsoft que aún no se han aplicado al dispositivo. Los "KB" en cuestión son [artículos de Knowledge Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que describen estas actualizaciones; por ejemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).

![Imagen de la ficha de KB que falta para el perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

La vista predeterminada enumera el boletín que contiene las actualizaciones, la versión del sistema operativo, los productos afectados, CVE dirección, el número de KB y las etiquetas.

Se puede personalizar el número de elementos que se muestran por página y qué columnas se muestran.

Al seleccionar un elemento, se abrirá un control flotante que se vincula a la actualización.

## <a name="related-topics"></a>Temas relacionados

* [Introducción a la Protección contra amenazas de Microsoft](microsoft-threat-protection.md)
* [Habilitar la Protección contra amenazas de Microsoft](mtp-enable.md)
* [Investigar entidades en dispositivos usando la respuesta activa](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [Investigación y respuesta automatizadas (AIR) en Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
