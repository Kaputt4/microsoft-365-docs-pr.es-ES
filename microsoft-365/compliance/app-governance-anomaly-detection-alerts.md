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
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Investigar las alertas de detección de anomalías.
ms.openlocfilehash: d3876900e1dfa26e80550e699dd00d6034d8e6d7
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588118"
---
# <a name="investigate-anomaly-detection-alerts"></a>Investigar las alertas de detección de anomalías

 El gobierno de aplicaciones de Microsoft proporciona detecciones de seguridad y alertas de actividades maliciosas. El objetivo de esta guía es proporcionarle información general y práctica sobre cada alerta, para ayudarle en sus tareas de investigación y corrección. En esta guía se incluye información general sobre las condiciones de activación de las alertas. Dado que las detecciones de anomalías no son deterministas por naturaleza, sólo se activan cuando hay un comportamiento que se desvía de la norma. Por último, algunas alertas pueden estar en previsión, así que revise regularmente la documentación oficial para conocer el estado actualizado de las alertas.

## <a name="mitre-attck"></a>MITRE ATT&CK

Para facilitar la relación entre las alertas de gobernanza de aplicaciones y la conocida matriz ATT&CK de MITRE, hemos clasificado las alertas según su correspondiente táctica ATT&CK de MITRE. Esta referencia adicional facilita la comprensión de la técnica de ataque sospechosa potencialmente en uso cuando se activa la alerta de gobernanza de aplicaciones.

Esta guía proporciona información sobre cómo investigar y solucionar las alertas de gobernanza de aplicaciones en las siguientes categorías.

- [Acceso inicial](#initial-access-alerts)
- Ejecución
- [Persistencia](#persistence-alerts)
- Elevación de privilegios
- Evasión de defensa
- Acceso a credenciales
- [Descubrimiento](#discovery-alerts)
- Movimiento lateral
- [Colección](#collection-alerts)
- Filtración
- Impacto

## <a name="security-alert-classifications"></a>Clasificación de las alertas de seguridad

Tras una investigación adecuada, todas las alertas de gobernanza de aplicaciones pueden clasificarse como uno de los siguientes tipos de actividad:

- Verdadero positivo (TP): una alerta sobre una actividad maliciosa confirmada.
- Verdadero positivo benigno (B-TP): una alerta sobre una actividad sospechosa pero no maliciosa, como una prueba de penetración u otra acción sospechosa autorizada.
- Falso positivo (FP): una alerta sobre una actividad no maliciosa.

## <a name="general-investigation-steps"></a>Pasos generales de la investigación

Utilice las siguientes directrices generales cuando investigue cualquier tipo de alerta para obtener una comprensión más clara de la amenaza potencial antes de aplicar la acción recomendada.

- Revise el nivel de gravedad de la aplicación y compárelo con el resto de aplicaciones en su inquilino. Esta revisión le ayudará a identificar qué aplicaciones de su inquilino suponen un mayor riesgo.
- Si identifica un verdadero positivo (TP), revise todas las actividades de la aplicación para comprender el impacto. Por ejemplo, revise la siguiente información de la aplicación:

  - Ámbitos de acceso concedidos
  - Comportamiento inusual  
  - Dirección IP y ubicación

## <a name="initial-access-alerts"></a>Alertas de acceso inicial

Esta sección describe las alertas que indican que una aplicación maliciosa puede estar intentando mantenerse en su organización.  

### <a name="app-created-recently-has-low-consent-rate"></a>La aplicación creada recientemente tiene una tasa de consentimiento baja

**Gravedad**: baja

Esta detección identifica una aplicación de OAuth creada recientemente que tiene una tasa de consentimiento baja. Podría indicar que es una aplicación malintencionada o de riesgo que atraerá a los usuarios para que den su consentimiento de forma ilícita.

**¿TP o FP?**

- **Verdadero positivo (TP)**: si se confirma que la aplicación OAuth procede de un origen desconocido, se indica un verdadero positivo (TP).

  **Acción recomendada**: revise el nombre para mostrar, las direcciones URL de respuesta y los dominios de la aplicación. Basándose en su investigación, puede optar por prohibir el acceso a esta aplicación. Revise el nivel de permiso solicitado por esta aplicación y qué usuarios han concedido el acceso.

- **Falso positivo (FP)**: Si tras la investigación, puede confirmar que la aplicación tiene un uso empresarial legítimo en la organización.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise todas las actividades realizadas por la aplicación.  
1. Si sospecha de una aplicación, le recomendamos que investigue el nombre de la aplicación y el dominio de respuesta en diferentes tiendas de aplicaciones. Cuando compruebe las tiendas de aplicaciones, céntrese en los siguientes tipos de aplicaciones:
   - Aplicaciones que se han creado recientemente
   - Aplicación con nombre para mostrar inusual
   - Aplicaciones con un dominio de respuesta sospechoso
1. Si todavía cree que una aplicación es sospechosa, puede investigar el nombre para mostrar y el dominio de respuesta de la aplicación.

### <a name="app-with-bad-url-reputation"></a>Aplicación con URL de mala reputación

**Gravedad**: media

Esta detección identifica una aplicación de OAuth cuya dirección URL tiene una mala reputación.  

**¿TP o FP?**

- **Verdadero positivo (TP)**: si se confirma que la aplicación de OAuth procede de un origen desconocido y redirige a una dirección URL sospechosa, se indica un verdadero positivo (TP).

  **Acción recomendada**: revise la dirección URL de respuesta y los ámbitos solicitados por la aplicación. Basándose en su investigación, puede optar por prohibir el acceso a esta aplicación. Revise el nivel de permiso solicitado por esta aplicación y qué usuarios han concedido el acceso.

- **Falso positivo (FP)**: Si tras la investigación, puede confirmar que la aplicación tiene un uso empresarial legítimo en la organización.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise todas las actividades realizadas por la aplicación.  
1. Si sospecha de una aplicación, le recomendamos que investigue el nombre de la aplicación y el dominio de respuesta en diferentes tiendas de aplicaciones. Cuando compruebe las tiendas de aplicaciones, céntrese en los siguientes tipos de aplicaciones:
   - Aplicaciones que se han creado recientemente
   - Aplicación con nombre para mostrar inusual
   - Aplicaciones con un dominio de respuesta sospechoso
1. Si todavía cree que una aplicación es sospechosa, puede investigar el nombre para mostrar y el dominio de respuesta de la aplicación.

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a>Nombre de la aplicación codificado con ámbitos de consentimiento sospechosos

**Gravedad**: media

**Descripción**: esta detección identifica aplicaciones OAuth con caracteres (como Unicode o caracteres codificados) solicitados para ámbitos de consentimiento sospechosos y que accedieron a las carpetas de correo de los usuarios a través de la Graph API. Esta alerta puede indicar un intento de camuflar una aplicación maliciosa como una aplicación conocida y de confianza para que los adversarios puedan engañar a los usuarios para que den su consentimiento a la aplicación maliciosa.

**¿TP o FP?**

- **Verdadero positivo (TP)**: si puede confirmar que la aplicación de OAuth ha codificado el nombre para mostrar con ámbitos sospechosos entregados desde un origen desconocido, se indica un verdadero positivo.  

  **Acción recomendada**: revise el nivel de permiso solicitado por esta aplicación y los usuarios a los que se les ha concedido acceso. Basándose en su investigación, puede optar por prohibir el acceso a esta aplicación.

  Para prohibir el acceso a la aplicación, en la página de aplicaciones OAuth, en la fila en la que aparece la aplicación que quieres prohibir, selecciona el icono de prohibición. Puedes elegir si quieres informar a los usuarios de que la aplicación que instalaron y autorizaron ha sido prohibida. La notificación permite a los usuarios saber que la aplicación se desactivará y no tendrán acceso a la aplicación conectada. Si no quiere que lo sepan, anule la selección de la opción Notificar a los usuarios que han concedido acceso a esta aplicación prohibida en el cuadro de diálogo. Le recomendamos que haga saber a los usuarios de la aplicación que su uso está a punto de ser prohibido.

- **FP**: si debe confirmar que la aplicación tiene un nombre codificado pero tiene un uso empresarial legítimo en la organización.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

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

**Comprender el alcance de la infracción**

1. Revise todas las actividades realizadas por la aplicación.
1. Si sospecha de una aplicación, le recomendamos que investigue el nombre de la aplicación y la URL de respuesta en diferentes tiendas de aplicaciones. Cuando compruebe las tiendas de aplicaciones, céntrese en los siguientes tipos de aplicaciones:
   - Aplicaciones que se han creado recientemente.
   - Aplicaciones con una URL de respuesta sospechosa
   - Aplicaciones que no han sido actualizadas recientemente. La falta de actualizaciones puede indicar que la aplicación ya no es compatible.
1. Si todavía sospecha que una aplicación es sospechosa, puede investigar el nombre de la aplicación, el nombre del editor y la URL de respuesta en línea  

### <a name="app-with-unusual-display-name-and-unusual-tld-inreply-domain"></a>Aplicación con un nombre para mostrar inusual y un dominio de primer nivel inusual en el dominio de respuesta  

**Gravedad**: media  

Esta detección identifica la aplicación con un nombre para mostrar inusual y redirige a un dominio de respuesta sospechoso con un dominio de primer nivel (TLD) inusual a través de la Graph API. Esto puede indicar un intento de camuflar una aplicación maliciosa o de riesgo como una aplicación conocida y de confianza para que los adversarios puedan engañar a los usuarios y que den su consentimiento a la aplicación maliciosa o de riesgo.  

**¿TP o FP?**

- **Verdadero positivo (TP)**: si puede confirmar que la aplicación con un nombre para mostrar inusual se entrega desde un origen desconocido y redirige a un dominio sospechoso que tiene un dominio inusual de nivel superior  

    **Acción recomendada**: revise el nombre para mostrar y el dominio de respuesta de la aplicación. Basándose en su investigación, puede optar por prohibir el acceso a esta aplicación. Revise el nivel de permiso solicitado por esta aplicación y qué usuarios han concedido el acceso.

- **Falso positivo (FP)**: Si tras la investigación, puede confirmar que la aplicación tiene un uso empresarial legítimo en la organización.

    **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

Revise todas las actividades realizadas por la aplicación. Si sospecha de una aplicación, le recomendamos que investigue el nombre de la aplicación y el dominio de respuesta en diferentes tiendas de aplicaciones. Cuando compruebe las tiendas de aplicaciones, céntrese en los siguientes tipos de aplicaciones:

- Aplicaciones que se han creado recientemente
- Aplicación con nombre para mostrar inusual
- Aplicaciones con un dominio de respuesta sospechoso

Si todavía cree que una aplicación es sospechosa, puede investigar el nombre para mostrar y el dominio de respuesta de la aplicación.

## <a name="persistence-alerts"></a>Alertas de persistencia

Esta sección describe las alertas que indican que un actor malicioso puede estar intentando mantener su posición en su organización.

### <a name="app-made-anomalous-graph-calls-to-exchange-workload-post-certificate-update-or-addition-of-new-credentials"></a>La aplicación realizó llamadas anómalas de Graph a la carga de trabajo de Exchange después de actualizar certificados o añadir nuevas credenciales

**Gravedad**: media

**ID. DE MITRE**: T1098.001, T1114

Esta detección desencadena una alerta cuando una aplicación de línea de negocio (LOB) ha actualizado el certificado o los secretos o cuando agrega nuevas credenciales y unos días después se observan actividades inusuales o un gran volumen de uso en la carga de trabajo de Exchange a través de la API de Graph mediante el algoritmo de aprendizaje automático.

**¿TP o FP?**

- **Verdadero positivo (TP)**: si se confirma que la aplicación de línea de negocio ha realizado actividades inusuales o experimentado un gran volumen de uso para la carga de trabajo de Exchange a través de la API de Graph  

  **Acción recomendada**: deshabilite temporalmente la aplicación, restablezca la contraseña y vuelva a habilitarla.

- **FP**: si se confirma que ninguna aplicación de línea de negocio ha realizado actividades inusuales o si la aplicación está diseñada para realizar un volumen inusualmente elevado de llamadas de grafo.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise toda la actividad realizada por esta aplicación.
1. Revise los alcances otorgados por la aplicación.
1. Revise la actividad de usuario asociada a esta aplicación.

### <a name="app-with-suspicious-oauth-scope-was-flagged-high-risk-by-machine-learning-model-made-graph-calls-to-read-email-and-created-inbox-rule"></a>La aplicación con ámbito de OAuth sospechoso se marcó como de alto riesgo por el modelo de aprendizaje automático, realizó llamadas de grafo para leer el correo electrónico y creó la regla de la Bandeja de entrada

**Gravedad**: media

**ID. DE MITRE**: T1137.005, T1114

Esta detección identifica una aplicación de OAuth que se marcó como de alto riesgo por el modelo de aprendizaje automático y que ha dado consentimiento a ámbitos sospechosos, ha creado una regla de la Bandeja de entrada sospechosa y luego ha accedido a las carpetas de correo de los usuarios y a los mensajes a través de la API de Graph. Las reglas de la bandeja de entrada, como el reenvío de todos los correos electrónicos o de algunos específicos a otra cuenta de correo electrónico, y las llamadas de Graph para acceder a los correos electrónicos y enviarlos a otra cuenta de correo electrónico, pueden ser un intento de filtrar información de su organización.

**¿TP o FP?**

- **Verdadero positivo (TP)**: si se puede confirmar que la regla de la bandeja de entrada fue creada por una aplicación de OAuth de terceros con ámbitos sospechosos procedentes de origen desconocido, se indica un verdadero positivo (TP).

  **Acción recomendada**: deshabilitar y quitar la aplicación, restablecer la contraseña y quitar la regla de bandeja de entrada.

Siga el tutorial sobre cómo restablecer una contraseña utilizando Azure Active Directory y siga el tutorial sobre cómo quitar la regla de la bandeja de entrada.

- **FP**: Si puede confirmar que la aplicación creó una regla de bandeja de entrada a una cuenta de correo electrónico externa nueva o personal por razones legítimas.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise todas las actividades realizadas por la aplicación.
1. Revise los alcances otorgados por la aplicación.
1. Revise la acción y la condición de la regla de entrada creada por la aplicación.

### <a name="app-with-suspicious-oauth-scope-made-graph-calls-to-read-email-and-created-inbox-rule"></a>La aplicación con ámbito de OAuth sospechoso realizó llamadas de Graph para leer el correo electrónico y creó la regla de la Bandeja de entrada  

**Gravedad**: media

**Id. MITRE ID**: T1137.005, T1114  

Esta detección identifica una aplicación OAuth que consiente ámbitos sospechosos, crea una regla de bandeja de entrada sospechosa y luego accede a las carpetas de correo de los usuarios y a los mensajes a través de la Graph API. Las reglas de la bandeja de entrada, como el reenvío de todos los correos electrónicos o de algunos específicos a otra cuenta de correo electrónico, y las llamadas de Graph para acceder a los correos electrónicos y enviarlos a otra cuenta de correo electrónico, pueden ser un intento de filtrar información de su organización.  

**¿TP o FP?**

- **TP**: si puede confirmar que la regla de la bandeja de entrada fue creada por una aplicación de terceros OAuth con alcances sospechosos entregados desde una fuente desconocida, entonces se indica un verdadero positivo.

  **Acción recomendada**: deshabilitar y quitar la aplicación, restablecer la contraseña y quitar la regla de bandeja de entrada.

  Siga el tutorial sobre cómo restablecer una contraseña utilizando Azure Active Directory y siga el tutorial sobre cómo quitar la regla de la bandeja de entrada.

- **FP**: Si puede confirmar que la aplicación creó una regla de bandeja de entrada a una cuenta de correo electrónico externa nueva o personal por razones legítimas.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise todas las actividades realizadas por la aplicación.
1. Revise los alcances otorgados por la aplicación.
1. Revise la acción y la condición de la regla de entrada creada por la aplicación.

### <a name="app-accessed-from-unusual-location-post-certificate-update"></a>Aplicación a la que se accede desde una ubicación inusual después de la actualización del certificado

**Gravedad**: baja

**ID de MITRE**: T1098

Esta detección desencadena una alerta cuando una aplicación de línea de negocio (LOB) ha actualizado el certificado o secreto y, unos días después de la actualización del certificado, se accede a la aplicación desde una ubicación inusual que no se ha visto recientemente o a la que nunca se ha accedido en el pasado.

**¿TP o FP?**

- **Verdadero positivo (TP)**: si puede confirmar que la aplicación LOB accedió desde una ubicación inusual y realizó actividades inusuales a través de la Graph API.

    **Acción recomendada**: deshabilite temporalmente la aplicación, restablezca la contraseña y vuelva a habilitarla.

- **Falso positivo (FP)**: si puede confirmar que la aplicación LOB accedió desde una ubicación inusual con fines legítimos y no se realizaron actividades inusuales.

    **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise toda la actividad realizada por esta aplicación.
1. Revise los alcances otorgados por la aplicación.
1. Revise la actividad de usuario asociada a esta aplicación.

### <a name="app-accessed-from-unusual-location-made-anomalous-graph-calls-post-certificate-update"></a>La aplicación a la que se ha accedido desde una ubicación inusual ha realizado llamadas anómalas de Graph después de la actualización del certificado

**Gravedad**: media

**ID de MITRE**: T1098

Esta detección desencadena una alerta cuando una aplicación de línea de negocio (LOB) actualiza el certificado o secreto y, pocos días después de la actualización del certificado, se accede a la aplicación desde una ubicación inusual que no se ha visto recientemente o a la que nunca se ha accedido en el pasado y se observan actividades o usos inusuales a través de la Graph API mediante el algoritmo de aprendizaje automático.

**¿TP o FP?**

- **Verdadero positivo (TP)**: si puede confirmar que la aplicación LOB realizó actividades o usos inusuales a través de la Graph API desde una ubicación inusual.

    **Acción recomendada**: deshabilite temporalmente la aplicación, restablezca la contraseña y vuelva a habilitarla.

- **Falso positivo (FP)**: si puede confirmar que la aplicación LOB accedió desde una ubicación inusual con fines legítimos y no se realizaron actividades inusuales.

    **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise toda la actividad realizada por esta aplicación.
1. Revise los alcances otorgados por la aplicación.
1. Revise la actividad de usuario asociada a esta aplicación.

## <a name="discovery-alerts"></a>Alertas de detección

### <a name="app-performed-drive-enumeration"></a>La aplicación ha realizado enumeración de unidades de disco

**Gravedad**: media

**ID. DE MITRE**: T1087

Esta detección identifica una aplicación de OAuth detectada por el modelo de aprendizaje automático que realiza enumeraciones en archivos de OneDrive mediante la API de Graph.  

**¿TP o FP?**

- **Verdadero positivo (TP)**: si se confirma que la aplicación de línea de negocio ha realizado actividades o un uso inusual de OneDrive a través de la API de Graph.

  **Acción recomendada**: deshabilitar y quitar la aplicación y restablecer la contraseña.

- **FP**: si se confirma que la aplicación no ha realizado ninguna actividad inusual.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise toda la actividad realizada por esta aplicación.
1. Revise los alcances otorgados por la aplicación.
1. Revise la actividad de usuario asociada a esta aplicación.

### <a name="suspicious-enumeration-activities-performed-using-aad-powershell"></a>Actividades de enumeración sospechosas realizadas con AAD de PowerShell

**Gravedad**: media

**ID. DE MITRE**: T1087

Esta detección identifica un gran volumen de actividades de enumeración sospechosas realizadas en un corto período de tiempo a través de una aplicación AAD de PowerShell.

**¿TP o FP?**

- **TP**: si puede confirmar que la aplicación ADD de PowerShell realizó actividades de enumeración sospechosas o inusuales.

  **Acción recomendada**: deshabilitar y quitar la aplicación y restablecer la contraseña.

- **FP**: si se confirma que la aplicación no ha realizado ninguna actividad inusual.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise toda la actividad realizada por esta aplicación.
1. Revise la actividad del usuario asociada a esta aplicación.

## <a name="collection-alerts"></a>Alertas de recopilación

Esta sección describe las alertas que indican que un actor malicioso puede estar intentando recopilar datos de interés para su objetivo desde su organización.

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a>La aplicación hizo llamadas anómalas a Graph para leer el correo electrónico

**Gravedad**: media

**Id. MITRE**: T1114

Esta detección identifica cuando la aplicación OAuth de la línea de negocio (LOB) accede a un volumen inusual y elevado de carpetas de correo y mensajes de los usuarios a través de la Graph API, lo que puede indicar un intento de violación de su organización.

**¿TP o FP?**

- **TP**: si puede confirmar que la actividad gráfica inusual fue realizada por la aplicación OAuth de la línea de negocio (LOB), entonces se indica un verdadero positivo.

  **Acciones recomendadas**: deshabilite temporalmente la aplicación, restablezca la contraseña y vuelva a habilitarla. Siga el tutorial sobre cómo restablecer una contraseña utilizando Azure Active Directory.

- **FP**: si puede confirmar que la aplicación está destinada a hacer un volumen inusualmente alto de llamadas gráficas.

  **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise el registro de actividad de los eventos realizados por esta aplicación para obtener una mejor comprensión de otras actividades de Graph para leer correos electrónicos e intentar recopilar información de correo electrónico confidencial de los usuarios.
1. Supervisa si se agregan credenciales inesperadas a la aplicación.

### <a name="app-creates-inbox-rule-and-made-unusual-email-searches-activities"></a>La aplicación crea una regla de bandeja de entrada y realiza actividades inusuales de búsqueda de correo electrónico

**Gravedad**: media

**Id. de MITRE**: T1137 , T1114  

Esta detección identifica la aplicación consentida en el ámbito de privilegios elevados, crea una regla de bandeja de entrada sospechosa y realiza actividades de búsqueda de correo electrónico inusuales en las carpetas de correo de los usuarios a través de la Graph API. Esto puede indicar un intento de vulneración de su organización, como adversarios que intentan buscar y recopilar correos electrónicos específicos de su organización a través de la Graph API.

**¿TP o FP?**

- **Verdadero positivo (TP)**: si puede confirmar cualquier búsqueda y recopilación de correos electrónicos específica realizada a través de la Graph API por parte de una aplicación de OAuth con un ámbito de privilegios elevados y la aplicación se entrega desde un origen desconocido.

    **Acción recomendada**: deshabilitar y quitar la aplicación, restablecer la contraseña y quitar la regla de bandeja de entrada.

- **Falso positivo (FP)**: si puede confirmar que la aplicación ha realizado búsquedas y recopilaciones de correo electrónico específicas a través de la Graph API y ha creado una regla de bandeja de entrada para una cuenta de correo electrónico externa nueva o personal por motivos legítimos.

    **Acción recomendada**: descartar la alerta.

**Comprender el alcance de la infracción**

1. Revise todas las actividades realizadas por la aplicación.
1. Revise los alcances otorgados por la aplicación.
1. Revise cualquier acción de regla de bandeja de entrada creada por la aplicación.
1. Revise las actividades de búsqueda de correo electrónico realizadas por la aplicación.

### <a name="appmade-onedrive--sharepoint-search-activities-and-created-inbox-rule"></a>La aplicación realizó actividades de búsqueda de OneDrive o SharePoint y creó una regla de la Bandeja de entrada  

**Gravedad**: media

**Id. de MITRE**: T1137, T1213

Esta detección identifica si una aplicación consiente el ámbito de privilegios elevados, creó una regla de la Bandeja de entrada sospechosa y realizó actividades de búsqueda inusuales de SharePoint o OneDrive a través de Graph API. Esto puede indicar un intento de vulneración de su organización, como adversarios que intentan buscar y recopilar datos específicos de SharePoint o OneDrive de su organización a través de Graph API.  

**¿TP o FP?**

- **TP**: si puede confirmar datos específicos de la búsqueda y recopilación de SharePoint o OneDrive realizada a través de Graph API mediante una aplicación de OAuth con un ámbito de privilegios alto y la aplicación se entrega desde un origen desconocido.  

  **Acción recomendada**: deshabilitar y quitar la aplicación, restablecer la contraseña y quitar la regla de la Bandeja de entrada.  

- **FP**: si puede confirmar que la aplicación ha ejecutado datos específicos de búsqueda y recopilación de SharePoint o OneDrive a través de Graph API por una aplicación de OAuth y ha creado una regla de la Bandeja de entrada para una cuenta de correo electrónico externa nueva o personal por motivos legítimos.  

  **Acción recomendada**: descartar la alerta  

**Comprender el alcance de la infracción**

1. Revise todas las actividades realizadas por la aplicación.  
1. Revise los alcances otorgados por la aplicación.  
1. Revise cualquier acción de regla de bandeja de entrada creada por la aplicación.  
1. Revise las actividades de búsqueda de SharePoint o OneDrive realizadas por la aplicación.

### <a name="app-made-high-volume-of-importance-mail-read-and-created-inbox-rule"></a>La aplicación realizó un gran volumen de lectura de correo importante y creó la regla de bandeja de entrada

**Gravedad**: media  

**Id. de MITRE**: T1137, T1114

Esta detección identifica que una aplicación consiente el ámbito de privilegios elevados, crea una regla de bandeja de entrada sospechosa y ha realizado un gran volumen de lectura de correos importantes a través de la API de Graph. Esto puede indicar un intento de vulneración de seguridad en su organización, por ejemplo, un rival que intenta leer el correo electrónico importante de su organización a través de la API de Graph.  

**¿TP o FP?**

- **TP**: si se puede confirmar que se ha leído un gran volumen de correo electrónico importante a través de la API de Graph mediante una aplicación de OAuth con un ámbito de privilegios alto y que se entrega desde un origen desconocido.  

  **Acción recomendada**: deshabilitar y quitar la aplicación, restablecer la contraseña y quitar la regla de bandeja de entrada.  

- **FP**: si se puede confirmar que la aplicación ha leído un gran volumen de correo electrónico importante a través de la API de Graph y ha creado una regla de bandeja de entrada para una cuenta de correo electrónico externa nueva o personal por motivos legítimos.  

  **Acción recomendada**: descartar la alerta  

**Comprender el alcance de la infracción**

1. Revise todas las actividades realizadas por la aplicación.  
1. Revise los alcances otorgados por la aplicación.  
1. Revise cualquier acción de regla de bandeja de entrada creada por la aplicación.  
1. Revise cualquier actividad de lectura de correo electrónico importante realizada por la aplicación.  
