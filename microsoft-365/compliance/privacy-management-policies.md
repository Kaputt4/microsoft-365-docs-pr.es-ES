---
title: Crear y administrar directivas en administración de privacidad de Microsoft (versión preliminar)
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
description: Obtenga información sobre cómo crear y administrar directivas para controlar los datos personales de su organización en Microsoft 365, responder a alertas y solucionar problemas.
ms.openlocfilehash: 49f772119cfc25284fecd66b2f3a79e063f11c09
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186049"
---
# <a name="create-and-manage-policies-in-privacy-management-preview"></a>Crear y administrar directivas en la administración de privacidad (versión preliminar)

Las directivas le permiten definir los tipos de riesgos de privacidad que deben tener en cuenta en los datos de Microsoft 365 de su empresa y establecer los resultados preferidos para escenarios donde se encuentran coincidencias. Su organización puede trabajar desde las alertas resultantes para revisar los datos que coincidan y solucionar problemas, todo desde la solución de administración de privacidad.

La administración de privacidad proporciona plantillas para facilitar la creación de directivas y le permite ajustar el enfoque a través de amplias opciones de personalización. Entre los escenarios clave que se tratan en las plantillas de la administración de privacidad se incluyen los siguientes:

- **Sobreexposición de datos:** detecta datos personales sobreexpuestos y pide a los usuarios que los protejan.
- **Transferencia de datos:** detecta y ayuda a limitar las transferencias de datos personales a través de departamentos o fronteras regionales.
- **Minimización de datos:** ayuda a los usuarios a identificar y reducir la cantidad de datos personales no usados.

Para obtener más información sobre las capacidades de cada plantilla, vea a continuación.

## <a name="policy-types"></a>Tipos de directivas

### <a name="data-overexposure"></a>Sobreexposición de datos

La administración de privacidad puede ayudarle a detectar y controlar situaciones en las que los datos almacenados no son suficientemente seguros. Por ejemplo, si el acceso a un sitio interno está abierto a un grupo demasiado amplio o la configuración de permisos no se ha actualizado, los datos personales almacenados en ese sitio pueden ser vulnerables a una infracción. Puede usar la plantilla de directiva de datos de la administración de privacidad para evaluar los datos y alertar sobre posibles problemas.

### <a name="data-transfer"></a>Transferencia de datos

La transferencia de datos entre departamentos o fronteras regionales puede aumentar el riesgo de exposición a datos, por ejemplo, si se envía a través de correos electrónicos no cifrados o a destinatarios no autorizados. Estas acciones pueden tener un impacto normativo o pueden ir en contra de las prácticas establecidas para la privacidad. El uso de la plantilla de transferencia de datos para crear directivas de administración de privacidad puede detectar y limitar dichas transferencias.

> [!NOTE]
> Durante la versión preliminar pública, algunos inquilinos que ejecutan directivas de transferencia de datos para detectar transferencias entre regiones pueden encontrar problemas de sincronización que afectan a la visibilidad de las coincidencias de directivas en Exchange y Teams datos. Se recomienda centrarse en los datos SharePoint y OneDrive mientras se muestra una vista previa de este tipo de directiva.

### <a name="data-minimization"></a>Minimización de datos

Con el tiempo, las empresas pueden recopilar grandes cantidades de datos personales de clientes o empleados. En ocasiones, esto incluye datos que se recopilaron por encima de la necesidad o que, de lo contrario, no se usan y deben reducirse para limitar los riesgos de privacidad en torno a esa información. La plantilla de minimización de datos se puede usar para solucionar los riesgos de este tipo.

## <a name="get-started-with-default-templates"></a>Introducción a las plantillas predeterminadas

La administración de privacidad ayudará a iniciar el proceso de evaluación de datos creando tres directivas con la configuración predeterminada, usando las plantillas para la minimización de datos, la sobreexposición de datos y las transferencias de datos. Estas directivas estarán activas de forma predeterminada, pero no desencadenarán automáticamente los mensajes de notificación ni los mensajes de corrección. Después de la configuración inicial, puede continuar con la creación y personalización de sus propias directivas.

## <a name="create-a-privacy-management-policy"></a>Crear una directiva de administración de privacidad

Hay dos rutas para crear directivas de administración de privacidad. La primera opción es elegir entre el conjunto de plantillas predefinidas. También puede personalizar su propia directiva, con cualquiera de estas plantillas como punto de partida.

### <a name="create-a-policy-from-a-template"></a>Crear una directiva a partir de una plantilla

Para empezar inmediatamente con una directiva, seleccione uno de los tres tipos de directiva predefinidos. Para revisar los detalles sobre cualquiera de ellos, puede seleccionar Ver configuración para ver las propiedades específicas que la hacen, incluidos los tipos de datos, las ubicaciones de datos y las condiciones que desencadenan coincidencias de directiva.

Al crear una directiva directamente desde una plantilla, se elegirán automáticamente muchas opciones de configuración. Esto incluye activar la directiva de forma predeterminada. Si quieres obtener una vista previa de la directiva en acción antes de activarla completamente, en la lista después de crearla, edita la directiva y alterna al modo de prueba. Para obtener más información, vea [Test your policy](#test-your-policy).

### <a name="create-custom-policy"></a>Crear directiva personalizada

Para controlar pormenorización la configuración de una directiva, puede crear una directiva personalizada con una de las plantillas existentes como línea base. La administración de privacidad proporciona un asistente para guiarlo a través de estos pasos.

Las propiedades personalizables incluyen:

- **Nombre y tipo:** elija la plantilla sobre la que crear la directiva y, a continuación, asigne un nombre y describa la versión.
- **Datos para supervisar:** seleccione el tipo de datos personales que supervisará la directiva. Elija entre los grupos de clasificación disponibles o elija en la lista de tipos de información confidencial individuales. Para obtener más información, consulta Elegir opciones de supervisión de datos a continuación.
- **Usuarios:** seleccione si esta directiva se aplica a todos los usuarios o usuarios seleccionados. Si elige la segunda opción, puede seleccionar hasta 300 usuarios de la lista proporcionada.
- **Ubicaciones:** elija las ubicaciones dentro de Microsoft 365 que debe cubrir la directiva, como los datos SharePoint o Exchange de la organización.
- **Condiciones:** seleccione las condiciones relevantes para el tipo de directiva. Por ejemplo, puede especificar qué tipos de transferencias debe buscar una directiva de transferencia de datos o qué datos se han usado recientemente para una directiva de minimización de datos.
- **Resultados:** defina los resultados cuando se detecte una coincidencia de directiva. Las opciones dependen del tipo de directiva con el que estés empezando. Entre los posibles resultados se incluyen:
  - **Notificaciones de correo** electrónico: esta configuración le permite desencadenar notificaciones implícitas de correo electrónico, incluidos los vínculos a cursos relacionados. Para obtener más información, vea Set user email notifications below.
  - **Teams:** proporcionar a los usuarios Teams recomendaciones y sugerencias de directiva, junto con vínculos a cursos relacionados. Esta opción está disponible para las directivas de transferencia de datos.
- **Alertas:** decida la frecuencia de las alertas a los administradores cuando se detecte una coincidencia de directiva. Las opciones no incluyen alertas, alertas para cada coincidencia de directiva o alertas cuando se alcanza un umbral específico. Si elige la opción de umbral, establezca los parámetros que desee.
- **Modo:** decida si desea ejecutar primero una directiva en modo de prueba o activarla inmediatamente. Para obtener más información, consulte Probar la directiva.
Cuando haya pasado por todas las configuraciones del asistente, revise la configuración, realice las modificaciones finales si es necesario y guarde la directiva.

#### <a name="choose-data-monitoring-options"></a>Elegir opciones de supervisión de datos

Al configurar una directiva personalizada, se le pedirá que seleccione qué tipos de datos debe supervisar la directiva. A continuación se indican las opciones posibles:

- **Grupos de clasificación:** una lista de conjuntos de datos que se pueden buscar en función de las normativas clave de privacidad, como RGPD o HIPAA. Vea los detalles de cualquier grupo para ver qué tipos de información confidencial abarca. Seleccione uno o varios de estos conjuntos para usarlos tal como están. Los grupos disponibles actualmente son los siguientes:
  - Ley de registros de salud de Australia (ley HRIP) mejorada
  - Ley de privacidad de Australia mejorada
  - (UE) Reglamento general de protección de datos (RGPD) mejorado
  - Datos de información de identificación personal (PII) de Japón mejorados
  - Protección de la información personal mejorada en Japón
  - Ley Gramm-Leach-Bliley (GLBA) de Ee.UU. Mejorada
  - Ley de seguros de salud de ESTADOS UNIDOS (HIPAA) mejorada
  - Acto patriota de EE.UU. mejorado
  - Datos mejorados de información de identificación personal (PII) de EE.UU.
  - Mejoradas las leyes de notificación de infracciones de Estado de EE.UU.
- **Tipos individuales** de información confidencial: al elegir tipos específicos de información confidencial, como números de seguridad social o información de licencia de conducir, puede personalizar su propio grupo o grupos de datos para buscar. Este asistente le permite seleccionar de la lista completa de tipos de información confidencial dentro de la administración de privacidad. Cada tipo de información tiene sus propias propiedades. Usa el botón de información junto a cualquiera de ellos para obtener detalles y notas sobre la configuración recomendada. Si crea más de un grupo, el asistente le permite aplicar operadores booleanos para relacionarlos y definir su orden de operaciones.

Si usa grupos de clasificación predefinidos, no puede seleccionar tipos individuales ni crear sus propios grupos. Para mayor flexibilidad, elige tipos de información confidencial individuales. Para usar los estándares más comunes, elija entre los grupos de clasificación.

#### <a name="test-your-policy"></a>Probar la directiva

Si desea evaluar una nueva directiva antes de activarla por completo, establezca la directiva en modo de prueba. El modo de prueba permite buscar coincidencias de los últimos 30 días, medir el comportamiento de la directiva y revisar los tipos de alertas generadas. Se recomienda ejecutar directivas de prueba durante al menos cinco días para obtener resultados representativos. Tiene la opción durante la fase de prueba para editar y ajustar la configuración de la directiva. Una vez que haya obtenido información al ejecutar la prueba, puede continuar activando la directiva. Mientras se ejecuta una directiva en modo de prueba, no se entregará ningún correo de notificación de usuario.

#### <a name="set-user-email-notifications"></a>Establecer notificaciones de correo electrónico de usuario

Con las notificaciones por correo electrónico, los usuarios reciben notificaciones directas sobre las coincidencias de directivas y las tareas importantes que deben completarse. Los destinatarios recibirán resúmenes de correo electrónico que resumen los datos que se van a revisar y las posibles acciones, como hacer que los documentos sean privados, mantenerlos en el archivo, informar de las coincidencias de falsos positivos y agregar notas para futuras referencias. Estos correos electrónicos también incluyen vínculos para formar a los destinatarios sobre cómo tratar estos casos. Proporcionar estos vínculos es necesario al configurar inicialmente las notificaciones y debe apuntar a su propia documentación interna sobre procesos y procedimientos recomendados.

Las notificaciones se pueden habilitar para directivas individuales durante la creación de directivas personalizadas o al editar cualquier directiva. Use la sección Resultados para definir lo que sucede cuando se detecta una coincidencia de directiva, incluida la opción para habilitar estas notificaciones, y establezca la frecuencia con la que desea que se entreguen estos resúmenes.

La funcionalidad de notificación de correo electrónico se controla a nivel global en Configuración. Está habilitada de forma predeterminada. Si desactiva esta opción, se detendrán todos los correos electrónicos incluso si se han configurado notificaciones específicas en un nivel de directiva individual. Para obtener más información, vea [Administrar la configuración de administración de privacidad.](privacy-management-settings.md)

## <a name="view-policy-details"></a>Ver detalles de la directiva

Después de crear la directiva, selecciónelo en la página **Directivas** principales para ver su información general completa. La página de detalles de la directiva proporcionará información sobre los datos, le permitirá ver contenido sobre coincidencias de directivas específicas y le informará sobre los pasos siguientes. Si la directiva se ejecuta en modo de prueba, esta página también es donde puede activar la directiva cuando se completen las pruebas.

Después de que la directiva esté activa, puede seguir revisando su página de detalles de directiva para ver información continua sobre las áreas de problemas, la gravedad y las tendencias de alerta y las acciones correctivas que se han tomado.

## <a name="resolve-policy-alerts-and-issues"></a>Resolver alertas y problemas de directiva

Una vez activadas las directivas, la administración de privacidad te mantendrá al tanto de los descubrimientos importantes al avisarte de coincidencias de directivas, evaluar su gravedad y permitirte tomar medidas creando y resolviendo problemas.

La página Información general de la administración de privacidad proporciona una vista de estos hallazgos con actualizaciones dinámicas sobre áreas clave de interés, como las directivas con más coincidencias y las alertas de directivas activas actualmente. También puede obtener acceso a los detalles sobre sus alertas y problemas a través de la página directivas principales.

### <a name="alerts"></a>Alertas

Para evaluar las alertas activas y especificar qué problemas requieren seguimiento, accede a la página **Alertas.** Proporciona una lista filtrable de alertas generadas por las directivas, que puede revisar individualmente para determinar las circunstancias en las que se desencadenaron.

Al seleccionar cualquier alerta, se abrirá un panel de sobrevía con detalles adicionales, como el tipo de directiva, el número de elementos que coinciden y la gravedad según la configuración de la directiva. En la **pestaña Contenido,** puede revisar los archivos implicados en esta alerta. Esta información puede proporcionar información adicional sobre el evento específico que desencadenó la alerta, dónde residen los archivos y qué tipos de datos personales están implicados. Los desencadenadores de las alertas se determinan según las condiciones específicas de cada directiva. Por ejemplo, una alerta puede desencadenarse en una directiva de transferencia de datos si la administración de privacidad detecta una transferencia entre los departamentos o regiones especificados de la directiva.

Después de evaluar cualquier alerta de la lista, puede usar la acción Crear **problema** para solicitar más investigación y acción. Se le pedirá que asigne un nombre al problema y agregue cualquier comentario relevante para el contexto. También puede descartar alertas aquí si no requieren un seguimiento.

### <a name="issues"></a>Problemas

Como se describe en la sección Alertas, los problemas se crean al evaluar las alertas sobre las coincidencias de directivas. Para hacer un seguimiento y resolver las preocupaciones indicadas, visite la página Problemas. Desde aquí puede revisar los problemas individuales, investigar las condiciones de incitación, revisar los datos y realizar los pasos necesarios para cerrar el caso.

Esta página proporciona una lista de todos los problemas abiertos. Los problemas se enumeran por nombre y se ordenan por gravedad para ayudarle a priorizar los casos, incluidas las categorías alta, mediana y baja, junto con las categorías sin asignar. Seleccione cualquier problema de la lista para revisar su contenido y tomar medidas para resolverlo. Puede proporcionar a los problemas sin signo una clasificación de gravedad durante la revisión.

#### <a name="issue-overview"></a>Información general sobre problemas

Las páginas de detalles de problemas ayudan a guiarlo a través del proceso de abordar los riesgos de privacidad identificados y controlar correctamente los archivos indicados. En la **pestaña Información** general puede ver el paso actual que debe realizar, que indica el estado del problema y las siguientes acciones recomendadas. También puede revisar información esencial sobre el contenido implicado, la directiva asociada, los detalles sobre la alerta y la escala de tiempo.

Las pestañas posteriores proporcionan más detalles sobre las alertas y el contenido asociados, junto con las notas de otros usuarios del equipo que trabajan en el problema. Puede administrar la lista de colaboradores activos a través de la **pestaña Colaboradores.**

#### <a name="share-the-issue"></a>Compartir el problema

Agregar personas como colaboradores le permite compartir el problema con miembros adicionales de su empresa a través de un canal de Microsoft Teams seguro, correo electrónico de la empresa o mediante el uso compartido de un vínculo directamente a la página del problema en la administración de privacidad. Estas opciones están disponibles en el **botón** Compartir. Al compartir a través de Teams, se le pedirá que seleccione entre los equipos disponibles de su organización, seleccione el canal específico y deje un mensaje sobre el problema, que se compartirá con el canal especificado.

#### <a name="review-content-and-remediate"></a>Revisar contenido y corregir

Para revisar el contenido asociado a un problema, elija la acción Revisar **contenido** si se le solicita o abra la pestaña Contenido. Seleccione cualquier archivo de la lista para verlo en su totalidad. Aquí puede ver detalles sobre el archivo, cualquier actividad en el registro y su historial de corrección, si se han realizado pasos anteriores para administrar este archivo.

Use el **botón Corregir** para tomar sus propias decisiones de control de datos para este contenido. Si selecciona el botón, puede elegir entre una o varias acciones de corrección. Entre las opciones se incluyen:

**Todas las directivas**

- **Notificar**: Notificar al propietario del contenido sobre el problema detectado.
- **Aplicar etiqueta de retención:** agregue una etiqueta sobre la retención de datos para este elemento. 
- **Aplicar etiqueta de confidencialidad:** agregue una etiqueta sobre la confidencialidad de los datos de este elemento.
- **Marcar como no una coincidencia:** identifique un resultado de búsqueda como un falso positivo para quitar el elemento de contenido de consideración.

**Minimización de datos**

- **Reciclaje/eliminación:** use esta opción para eliminar los datos de forma suave. El contenido se mueve a la carpeta de elementos eliminados o a la papelera de reciclaje (Exchange, SharePoint, OneDrive) o se elimina con una opción para recuperar (Teams mensajes). La eliminación puede revertirse en un período de tiempo establecido, según la configuración del servicio.

**Sobreexposición de datos y transferencia de datos**

- **Descompartir:** deje de compartir un vínculo a este elemento de contenido.

Cada opción le pedirá que deje comentarios y cualquier otra información de soporte necesaria para el propietario del contenido antes de confirmar su elección.

Una vez que se hayan realizado todos los pasos de corrección y el problema esté listo para cerrarse, use el botón Resolver y agregue los comentarios finales antes de enviarlo.

## <a name="delete-a-policy"></a>Eliminar una directiva

Si necesita quitar una directiva de administración de privacidad existente, en la lista de la página Directivas, seleccione el menú acción (puntos suspensivos verticales) y elija la acción Eliminar directiva. Se le pedirá que confirme su elección antes de que la eliminación sea definitiva y la directiva se quite permanentemente. La eliminación de una directiva no afectará a los archivos evaluados anteriormente por la directiva y los problemas y alertas generados por la directiva permanecerán.
