---
title: Investigar las alertas de detección de anomalías
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Investigar las alertas de detección de anomalías.
ms.openlocfilehash: 41dd60de86d7583169845ae185f9f715011ea3e4
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53541378"
---
# <a name="investigate-anomaly-detection-alerts"></a>Investigar las alertas de detección de anomalías

 El gobierno de aplicaciones de Microsoft proporciona detecciones de seguridad y alertas de actividades maliciosas. El objetivo de esta guía es proporcionarle información general y práctica sobre cada alerta, para ayudarle en sus tareas de investigación y corrección. En esta guía se incluye información general sobre las condiciones de activación de las alertas. Dado que las detecciones de anomalías no son deterministas por naturaleza, sólo se activan cuando hay un comportamiento que se desvía de la norma. Por último, algunas alertas pueden estar en previsión, así que revise regularmente la documentación oficial para conocer el estado actualizado de las alertas.

## <a name="mitre-attck"></a>MITRE ATT&CK

Para facilitar la relación entre las alertas de gobernanza de aplicaciones de Microsoft y la conocida matriz ATT&CK de MITRE, hemos clasificado las alertas según su correspondiente táctica ATT&CK de MITRE. Esta referencia adicional facilita la comprensión de la técnica de ataque sospechosa potencialmente en uso cuando se activa la alerta de gobernanza de aplicaciones.

Esta guía proporciona información sobre cómo investigar y solucionar las alertas de gobernanza de aplicaciones en las siguientes categorías.

- Acceso inicial
- Ejecución
- Persistencia
- Elevación de privilegios
- Evasión de defensa
- Acceso a credenciales
- Colección
- Exfiltración
- Impacto

<!-->
## <a name="security-alert-classifications"></a>Clasificación de las alertas de seguridad

Tras una investigación adecuada, todas las alertas de gobernanza de aplicaciones de Microsoft pueden clasificarse como uno de los siguientes tipos de actividad:

- Verdadero positivo (TP): una alerta sobre una actividad maliciosa confirmada.
- Verdadero positivo benigno (B-TP): una alerta sobre una actividad sospechosa pero no maliciosa, como una prueba de penetración u otra acción sospechosa autorizada.
- Falso positivo (FP): una alerta sobre una actividad no maliciosa.
-->

## <a name="general-investigation-steps"></a>Pasos generales de la investigación

Utilice las siguientes directrices generales cuando investigue cualquier tipo de alerta para obtener una comprensión más clara de la amenaza potencial antes de aplicar la acción recomendada.

- Revise el nivel de gravedad de la aplicación y compárelo con el resto de la aplicación en su inquilino. Esta revisión le ayudará a identificar qué aplicaciones de su inquilino suponen un mayor riesgo.
- Si identifica un TP, revise todas las actividades de la aplicación para comprender el impacto. Por ejemplo, revise la siguiente información de la aplicación:

  - Ámbitos de acceso concedidos
  - Comportamiento inusual  
  - Dirección IP y ubicación

## <a name="initial-access-alerts"></a>Alertas de acceso inicial

Esta sección describe las alertas que indican que una aplicación maliciosa puede estar intentando mantenerse en su organización.  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a>Nombre de la aplicación codificado con ámbitos de consentimiento sospechosos

**Gravedad:** media

**Descripción**: esta detección identifica aplicaciones OAuth con caracteres, como Unicode o caracteres codificados, solicitados para ámbitos de consentimiento sospechosos y que accedieron a las carpetas de correo de los usuarios a través de la Graph API. Esta alerta puede indicar un intento de camuflar una aplicación maliciosa como una aplicación conocida y de confianza para que los adversarios puedan engañar a los usuarios para que den su consentimiento a la aplicación maliciosa.

**¿TP o FP?**

- **TP**: si puede confirmar que la aplicación de OAuth ha codificado el nombre para mostrar con ámbitos sospechosos entregados desde un origen desconocido, se indica un verdadero positivo.  

  **Acción recomendada**: revise el nivel de permiso solicitado por esta aplicación y los usuarios a los que se les ha concedido acceso. Basándose en su investigación, puede optar por prohibir el acceso a esta aplicación.

  Para prohibir el acceso a la aplicación, en la página de aplicaciones OAuth, en la fila en la que aparece la aplicación que quieres prohibir, selecciona el icono de prohibición. Puedes elegir si quieres informar a los usuarios de que la aplicación que instalaron y autorizaron ha sido prohibida. La notificación permite a los usuarios saber que la aplicación se desactivará y no tendrán acceso a la aplicación conectada. Si no quiere que lo sepan, anule la selección de la opción Notificar a los usuarios que han concedido acceso a esta aplicación prohibida en el cuadro de diálogo. Le recomendamos que haga saber a los usuarios de la aplicación que su uso está a punto de ser prohibido.

- **FP**: si debe confirmar que la aplicación tiene un nombre codificado pero tiene un uso empresarial legítimo en la organización.

  **Acción recomendada**: descartar la alerta.

#### <a name="understand-the-scope-of-the-breach"></a>Comprender el alcance de la infracción

Siga el tutorial sobre cómo [investigar aplicaciones de OAuth de riesgo](/cloud-app-security/investigate-risky-oauth).

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a>La aplicación OAuth con ámbitos de lectura tiene una URL de respuesta sospechosa

**Gravedad**: media

**Descripción**: esta detección identifica una aplicación OAuth con sólo ámbitos de lectura como User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared que redirige a una URL de respuesta sospechosa a través de Graph API. Esta actividad intenta indicar que una aplicación maliciosa con permisos de menor privilegio (como los ámbitos de lectura) podría ser explotada para llevar a cabo el reconocimiento de la cuenta de los usuarios.

**¿TP o FP?**

- **TP**: si puede confirmar que la aplicación OAuth con alcance de lectura se entrega desde una fuente desconocida, y redirige a una URL sospechosa, entonces se indica un verdadero positivo.

  **Acción recomendada**: revise la URL de respuesta y los ámbitos solicitados por la aplicación. Basándose en su investigación, puede optar por prohibir el acceso a esta aplicación. Revise el nivel de permiso solicitado por esta aplicación y qué usuarios han concedido el acceso.

  Para prohibir el acceso a la aplicación, en la página de aplicaciones OAuth, en la fila en la que aparece la aplicación que quieres prohibir, selecciona el icono de prohibición. Puedes elegir si quieres informar a los usuarios de que la aplicación que instalaron y autorizaron ha sido prohibida. La notificación permite a los usuarios saber que la aplicación se desactivará y no tendrán acceso a la aplicación conectada. Si no quiere que lo sepan, anule la selección de la opción Notificar a los usuarios que han concedido acceso a esta aplicación prohibida en el cuadro de diálogo. Le recomendamos que haga saber a los usuarios de la aplicación que su uso está a punto de ser prohibido.

- **FP**: Si tras la investigación, puede confirmar que la aplicación tiene un uso empresarial legítimo en la organización.

  **Acción recomendada**: descartar la alerta.

#### <a name="understand-the-scope-of-the-breach"></a>Comprender el alcance de la infracción 

1. Revise todas las actividades realizadas por la aplicación.
1. Si sospecha de una aplicación, le recomendamos que investigue el nombre de la aplicación y la URL de respuesta en diferentes tiendas de aplicaciones. Cuando compruebe las tiendas de aplicaciones, céntrese en los siguientes tipos de aplicaciones:
   - Aplicaciones que se han creado recientemente.
   - Aplicaciones con una URL de respuesta sospechosa
   - Aplicaciones que no han sido actualizadas recientemente. La falta de actualizaciones puede indicar que la aplicación ya no es compatible.
1. Si todavía sospecha que una aplicación es sospechosa, puede investigar el nombre de la aplicación, el nombre del editor y la URL de respuesta en línea  

## <a name="persistence-alerts"></a>Alertas de persistencia

Esta sección describe las alertas que indican que un actor malicioso puede estar intentando mantener su posición en su organización.

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a>La aplicación con un ámbito de OAuth sospechoso crea una regla de entrada  

**Gravedad**: media

**Id. MITRE ID**: T1137.005, T1114  

Esta detección identifica una aplicación OAuth que consiente ámbitos sospechosos, crea una regla de bandeja de entrada sospechosa y luego accede a las carpetas de correo de los usuarios y a los mensajes a través de la Graph API. Las reglas de la bandeja de entrada, como el reenvío de todos los correos electrónicos o de algunos específicos a otra cuenta de correo electrónico, y las llamadas de Graph para acceder a los correos electrónicos y enviarlos a otra cuenta de correo electrónico, pueden ser un intento de filtrar información de su organización.  

**¿TP o FP?**

- **TP**: si puede confirmar que la regla de la bandeja de entrada fue creada por una aplicación de terceros OAuth con alcances sospechosos entregados desde una fuente desconocida, entonces se indica un verdadero positivo.

  **Acción recomendada**: deshabilitar y quitar la aplicación, restablecer la contraseña y quitar la regla de bandeja de entrada.

  Siga el tutorial sobre cómo restablecer una contraseña utilizando Azure Active Directory y siga el tutorial sobre cómo quitar la regla de la bandeja de entrada.

- **FP**: Si puede confirmar que la aplicación creó una regla de bandeja de entrada a una cuenta de correo electrónico externa nueva o personal por razones legítimas.

  **Acción recomendada**: descartar la alerta.

#### <a name="understand-the-scope-of-the-breach"></a>Comprender el alcance de la infracción

1. Revise todas las actividades realizadas por la aplicación.
1. Revise los alcances otorgados por la aplicación.
1. Revise la acción y la condición de la regla de entrada creada por la aplicación.

## <a name="collection-alerts"></a>Alertas de recopilación

Esta sección describe las alertas que indican que un actor malicioso puede estar intentando recopilar datos de interés para su objetivo desde su organización.

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a>La aplicación hizo llamadas anómalas a Graph para leer el correo electrónico

**Gravedad**: media

**Id. MITRE**: T1114

Esta detección identifica cuando la aplicación OAuth de la línea de negocio (LOB) accede a un volumen inusual y elevado de carpetas de correo y mensajes de los usuarios a través de la Graph API, lo que puede indicar un intento de violación de su organización.

**¿TP o FP?**

- **TP**: si puede confirmar que la actividad gráfica inusual fue realizada por la aplicación OAuth de la línea de negocio (LOB), entonces se indica un verdadero positivo.

  **Acciones recomendadas**: deshabilite temporalmente la aplicación, restablezca la contraseña y vuelva a habilitarla.

  Siga el tutorial sobre cómo restablecer una contraseña utilizando Azure Active Directory.

- **FP**: si puede confirmar que la aplicación está destinada a hacer un volumen inusualmente alto de llamadas gráficas.

  **Acción recomendada**: descartar la alerta.

#### <a name="understand-the-scope-of-the-breach"></a>Comprender el alcance de la infracción

1. Revise el registro de actividad de los eventos realizados por esta aplicación para obtener una mejor comprensión de otras actividades de Graph para leer correos electrónicos e intentar recopilar información de correo electrónico confidencial de los usuarios.
1. Supervisa si se agregan credenciales inesperadas a la aplicación.
