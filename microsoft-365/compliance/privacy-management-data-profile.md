---
title: Buscar y visualizar datos personales en administración de privacidad de Microsoft (versión preliminar)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre la información general y el perfil de datos en la administración de privacidad y cómo obtener información sobre los datos personales en el entorno Microsoft 365 organización.
ms.openlocfilehash: d8ea8d3306840244aff7621a12702d0ca19062c0
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378592"
---
# <a name="find-and-visualize-personal-data-in-privacy-management-preview"></a>Buscar y visualizar datos personales en la administración de privacidad (versión preliminar)

En este artículo: obtenga información  sobre las características de las páginas de información general y de perfil de **datos** y cómo pueden proporcionar información sobre los datos.

## <a name="purpose-of-the-overview-and-data-profile"></a>Finalidad de la información general y el perfil de datos

Microsoft 365 privacidad le proporciona capacidades para buscar y visualizar los datos personales en su entorno. La solución automatiza la detección de activos de datos personales en Exchange, SharePoint, OneDrive y Teams, y proporciona paneles que proporcionan información clave sobre los datos. Los administradores de privacidad pueden actuar según estos conocimientos para reforzar el enfoque de la organización en la privacidad y reducir los riesgos.

### <a name="overview-page"></a>Página Información general

La página Información general sirve como un panel general para la solución de administración de privacidad, que ofrece información dinámica sobre el ecosistema de datos personales de su organización. Los administradores de privacidad pueden supervisar las tendencias y actividades de los datos, identificar e investigar posibles riesgos en los datos personales y entrar en actividades clave, como la administración de directivas o las acciones de solicitud de derechos del sujeto. Para obtener más información en la página de información general, [vea Explorar la página de información general](#explore-the-overview-page).

### <a name="data-profile-page"></a>Página perfil de datos

La página de perfil de datos de la administración de privacidad proporciona una vista instantánea de los datos personales que la organización almacena en Microsoft 365. Esto le ayuda a visualizar dónde se encuentran los datos personales, qué tipos son los más frecuentes en su organización y cuántos tipos diferentes existen en todos los Microsoft 365 servicios. También podrá explorar datos personales desde esta ubicación. Para obtener más información, vea [Explorar la página de perfil de datos](#explore-the-data-profile-page).

## <a name="explore-the-overview-page"></a>Explorar la página de información general

La página de información general consta de tres secciones principales. Los iconos de la parte superior de la página proporcionan estadísticas recientes esenciales sobre los datos. La sección de información clave proporciona oportunidades de investigación sobre tendencias y áreas de interés clave. Para obtener más perspectiva sobre el entorno de datos, consulte los gráficos de línea de tendencia. Para obtener más información sobre estas áreas, consulte las secciones siguientes.

### <a name="top-tiles"></a>Iconos superiores

#### <a name="policy-matches-over-past-7-days"></a>Coincidencias de directivas en los últimos 7 días

Cuando las directivas se establecen en la administración de privacidad, los datos se evaluarán para determinadas condiciones que pueden presentar riesgos de privacidad. Las coincidencias de directiva indican descubrimientos de datos que pueden necesitar más revisión o corrección. Esta tarjeta muestra el recuento de las coincidencias de directiva que se han producido en los últimos siete días. Las coincidencias se mostrarán aquí si las directivas están activadas o se están ejecutando en modo de prueba, de modo que pueda ver los resultados de todas las directivas activas. Hacer clic en este icono te llevará a una vista filtrada de la página Directivas de administración de privacidad, que muestra las directivas que han tenido una coincidencia en los últimos siete días.

#### <a name="items-with-personal-data"></a>Elementos con datos personales

Para ver las funciones de detección automatizada de la solución de administración de privacidad en el trabajo, revise el icono Elementos con datos personales. Esto mostrará cuántos elementos nuevos que contienen datos personales se han detectado en el entorno de Microsoft 365 de la organización en los últimos siete días. Al hacer clic en este icono, se cargará una vista de los 100 elementos más nuevos detectados.

#### <a name="subject-rights-requests"></a>Solicitudes de derechos de sujeto

Los iconos superiores de la página de información general incluyen dos iconos relacionados con solicitudes de derechos de sujeto. La primera muestra el recuento de solicitudes creadas en los últimos siete días. El segundo icono se hace cargo de las solicitudes que están vencidas y que pueden necesitar atención inmediata. Al hacer clic en estos iconos, los usuarios tendrán los permisos adecuados para la página de solicitud de derechos del sujeto de la administración de privacidad.

### <a name="key-insights"></a>Información clave

#### <a name="content-items-with-the-most-personal-data"></a>Elementos de contenido con los datos más personales

El contenido del entorno de Microsoft 365 de la organización que contiene una gran cantidad de datos personales puede presentar un mayor riesgo de exposición. Es posible que desee revisar estos elementos para asegurarse de que están cubiertos por una directiva de administración de privacidad. Para ayudar a llamar la atención sobre estos elementos, la página de información general proporciona una vista de los elementos de contenido que contienen los datos más personales. Aquí puede ver el número de tipos de datos personales únicos detectados, cuántos propietarios de contenido únicos se han identificado y cuántos interesados se han identificado de acuerdo con la configuración de coincidencia de datos para solicitudes de derechos del sujeto.

Seleccione Ver resumen para obtener una vista resumida de los elementos encontrados. También puede elegir explorar estos resultados para obtener una vista previa de los archivos individuales. Esta vista muestra un máximo de 100 elementos. Los usuarios del grupo de roles Administración de privacidad pueden seleccionar archivos para revisar detalles y determinar la relevancia, y exportar la lista en .csv formato de referencia.

#### <a name="policies-with-the-most-matches-in-the-last-week"></a>Directivas con más coincidencias en la última semana

Esta información muestra qué directivas se han emparejado con más frecuencia en los últimos siete días, ya sea en modo "On" o "Testing". Esto ayuda a ilustrar el rendimiento de las directivas y los efectos del trabajo en curso a medida que los usuarios de administración de privacidad reciben formación y tienen la capacidad de resolver problemas con el contenido y refinar sus comportamientos de privacidad.

Seleccione Ver resumen para obtener un resumen de las 10 directivas principales coincidentes y los propietarios de contenido del contenido asociado. También verá cuántas notificaciones de usuario se enviaron debido a estas coincidencias de directiva y el número de acciones de usuario realizadas. Seleccione Investigar para ver la página directivas en la administración de privacidad, filtrada para mostrar las directivas desde la vista de resumen. Esta vista de investigación mostrará estadísticas de toda la vigencia de la directiva. Selecciónelo para ver detalles como cuándo se detectaron inicialmente elementos coincidentes.

#### <a name="users-with-the-most-policy-matched-in-the-last-week"></a>Usuarios con la directiva más coincidente en la última semana

Esta información también aborda las coincidencias de las directivas en modo "Prueba" o "On". Le permite ver un resumen de los usuarios con más coincidencias de directiva en la última semana y qué directivas coinciden. Esto incluye totales de los propietarios de contenido únicos, las notificaciones enviadas a estos usuarios y cuántas acciones se realizaron desde esas notificaciones. Si selecciona Investigar, se le llevará a la página directivas, filtrada para mostrar las directivas desde la vista de resumen. En la vista de investigación, no encontrará información del usuario, pero puede seleccionar una directiva para ver los detalles de la directiva relacionados con estas coincidencias.

#### <a name="items-with-the-most-data-subject-content"></a>Elementos con más contenido del interesado

Esta información tiene en cuenta la información de la característica de coincidencia de datos en solicitudes de derechos de sujeto y presenta elementos detectados dentro de Microsoft 365 que contienen la mayoría de los interesados dentro de su contenido. Para obtener más información acerca de esta configuración, vea [Administrar solicitudes de derechos de sujeto](privacy-management-subject-rights-requests.md).

Estos elementos pueden ayudar a confirmar la configuración de coincidencia de datos y ayudarle a mitigar los riesgos de privacidad relacionados con estos elementos. Seleccione Ver resumen para una vista de resumen. Seleccione Explorar para obtener una vista detallada de hasta 100 de estos elementos. Aquí puede obtener una vista previa de estos elementos y determinar la relevancia y exportar la lista en .csv formato.

### <a name="trendline-graphs"></a>Gráficos de línea de tendencia

Para ver las visualizaciones dinámicas de las tendencias encontradas en los datos de la organización, consulte los gráficos de línea de tendencia. Estos gráficos se pueden filtrar por características relevantes para la información proporcionada, como intervalos de tiempo, tipo de datos o ubicaciones de datos. Usa los desplegables proporcionados para ajustar la vista. Mantener el mouse sobre las líneas del gráfico te permitirá ver estadísticas relacionadas con ese punto específico en el tiempo.

Los resultados relacionados con las directivas incluirán datos de directivas en modo "Prueba" y "On". Si no hay directivas de un tipo determinado activas, los gráficos relacionados no mostrarán resultados.

#### <a name="active-policy-alerts"></a>Alertas de directivas activas

Esta área muestra una instantánea de alertas activas desencadenadas por coincidencias de directiva. Con el tiempo, esta vista puede ayudarle a detectar más fácilmente anomalías, como picos grandes en el volumen. Seleccione Ver alertas para navegar a la página directivas de la administración de privacidad, donde puede investigar más a fondo las alertas y crear problemas para la corrección.

#### <a name="personal-data-found-in-organization"></a>Datos personales encontrados en la organización

Este gráfico muestra tendencias en la cantidad de datos personales que se han detectado con el tiempo en el entorno Microsoft 365 y dónde se encuentran. Empezará a rellenarse después de que la administración de privacidad se haya estado ejecutando durante suficiente tiempo y después de que se haya encontrado contenido con datos personales en SharePoint, OneDrive, Teams y/o Exchange.

#### <a name="data-transfers-detected-in-organization"></a>Transferencias de datos detectadas en la organización

Este gráfico está relacionado con las directivas de transferencia de datos. Proporciona una vista de cómo se mueven los datos dentro de la organización, ya sea entre departamentos o entre regiones para organizaciones multige geográficas.

#### <a name="unused-personal-data"></a>Datos personales sin usar

Este gráfico está relacionado con las directivas de minimización de datos. Proporciona información sobre cómo su organización almacena contenido que contiene datos personales y cómo las directivas pueden mejorar el tratamiento de estos datos con el tiempo.

#### <a name="overexposed-personal-data"></a>Datos personales sobreexpuestos

Este gráfico está relacionado con directivas de sobreexposición de datos. Puede ayudarle a identificar comportamientos de uso compartido a lo largo del tiempo dentro de su organización y ubicaciones en las que el contenido con datos personales puede estar sobreexpuesto, por ejemplo, si se comparte públicamente, se comparte con un usuario externo o se comparte ampliamente dentro de la organización.

#### <a name="subject-rights-requests-by-regulation"></a>Solicitudes de derechos de sujeto por reglamento

Esta vista proporciona información sobre las normativas que más impulsan las solicitudes de derechos de sujeto con el tiempo. La leyenda de este gráfico muestra varias normativas. Si se mantiene el mouse sobre las líneas de tendencia, se mostrarán los totales de solicitudes de derechos de sujeto abiertas para dicho reglamento durante el tiempo seleccionado.

#### <a name="subject-rights-requests-by-status"></a>Solicitudes de derechos de sujeto por estado

En este gráfico se muestra cómo está su organización completando solicitudes de derechos de sujeto, divididas en solicitudes que son Active, Closed o Overdue. Los resultados aquí pueden ayudar a indicar dónde podría beneficiarse de la asignación de más recursos para cerrar sus solicitudes y objetivos de reunión.

### <a name="additional-data-views"></a>Vistas de datos adicionales

#### <a name="subject-rights-requests-at-a-glance"></a>Solicitudes de derechos de sujeto de un vistazo

Esta vista proporciona una vista de alto nivel de las solicitudes de derechos de sujeto activas, incluido el tiempo que queda para completar las solicitudes según sus plazos definidos. Resume cuántas solicitudes totales tiene, cuántas están activas y cuántas están cerradas. Seleccione Ver todas las solicitudes para ir a la página solicitud de derechos del sujeto, donde puede ver más detalles y trabajar en las solicitudes activas para avanzar hacia su finalización.

#### <a name="subject-rights-requests-by-residency"></a>Solicitudes de derechos de sujeto por residencia

Esta vista de mapa le ayuda a visualizar el volumen de solicitudes de derechos de sujeto por la residencia de los interesados. Al pasar el puntero sobre una burbuja se identificará la región y el total de solicitudes de derechos de sujeto abiertas en nombre de los residentes allí.

## <a name="explore-the-data-profile-page"></a>Explorar la página de perfil de datos

### <a name="personal-data-type-instances-detected-in-microsoft-365"></a>Instancias de tipo de datos personales detectadas en Microsoft 365

Esta tarjeta le ayuda a visualizar la cantidad de datos personales que existe en su entorno de Microsoft 365 y cómo se distribuyen los datos entre Exchange, OneDrive, SharePoint y Teams.

El gráfico de barras muestra el recuento agregado aproximado de instancias de tipo de datos personales únicos que se encuentran en el contenido. Algunos ejemplos de tipos de datos pueden incluir elementos como números de tarjeta de crédito y números de seguridad social. Por lo tanto, un archivo detectado que contiene tres números de tarjeta de crédito y un número de seguridad social contendrá dos tipos de datos personales únicos y cuatro instancias. La persona inferior de esta tarjeta muestra los tipos de datos personales únicos dentro de cada Microsoft 365 ubicación. Proporciona una vista de la diversidad de tipos de datos personales detectados en el contenido de la organización.

### <a name="top-personal-data-types-across-your-organization"></a>Tipos de datos personales principales en toda la organización

Esta tarjeta proporciona una instantánea de los principales tipos de datos personales detectados en su entorno, junto con información sobre cuántos elementos contienen ese tipo de datos personales y en qué ubicaciones.

### <a name="personal-data-by-region"></a>Datos personales por región

Para entornos multige geográficos, esta tarjeta agrega regionalmente instancias de tipo de datos personales que se encuentran en el contenido, en función de las regiones en las que se hospeda este contenido. Para las organizaciones de una sola región, esta tarjeta mostrará un punto que representa la Microsoft 365 de servicio. Si se mantiene el mouse sobre puntos en el mapa, se mostrará el recuento aproximado de instancias de tipo de datos personales detectadas en esa región.

### <a name="exploring-content"></a>Explorar contenido

Si selecciona **Explorar** en cualquier tarjeta de perfil de datos, se abrirá el explorador de contenido. En este momento, no puede buscar un elemento de contenido específico y no verá Teams datos en esta vista. Esto significa que es posible que los números del explorador de contenido no coincidan con los números que se muestran en la página de perfil de datos, ya que la página de perfil de datos incluye Teams contenido. Los administradores de privacidad que desean obtener más información sobre sus datos de privacidad pueden hacerlo aquí en función del tipo de datos personales (tipo de información confidencial) o por ubicación (Exchange, OneDrive o SharePoint).
