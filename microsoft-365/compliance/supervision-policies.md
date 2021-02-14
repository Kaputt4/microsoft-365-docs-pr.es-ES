---
title: Directivas de supervisión
description: Obtenga información sobre el uso de directivas de supervisión en Microsoft 365 para capturar las comunicaciones de los empleados para su examen por parte de revisores designados.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom: seo-marvel-apr2020
titleSuffix: Microsoft 365 Compliance
ms.openlocfilehash: 27c4d4603396089cb58cfed192f09d0db70cac5a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547590"
---
# <a name="supervision-policies"></a>Directivas de supervisión

>[!IMPORTANT]
>Tras la publicación del cumplimiento de las comunicaciones en Cumplimiento de Microsoft 365 en febrero de 2020, se retirará la supervisión en Office 365. Las directivas de supervisión ya no estarán disponibles para su creación y, finalmente, se quitarán después de un período prolongado de acceso de solo lectura.
>
>Si usa supervisión, tenga en cuenta lo siguiente:
>
>- A partir del 15 de junio de 2020, los inquilinos no podrán crear nuevas directivas de supervisión.
>- A partir del 31 de agosto de 2020, las directivas existentes dejarán de capturar mensajes nuevos.
>- A partir del 26 de octubre de 2020, se eliminarán las directivas existentes.
>
>Animamos activamente a los clientes que actualmente exploran o usan [](communication-compliance.md) la supervisión en Office 365 a usar la nueva solución de cumplimiento de comunicaciones para abordar los requisitos normativos o de supervisión de comunicaciones con un conjunto mucho más amplio de capacidades inteligentes.

Las directivas de supervisión de Microsoft 365 le permiten capturar las comunicaciones de los empleados para que las examinan los revisores designados. Puede definir directivas específicas que capturen correo electrónico interno y externo, Microsoft Teams o comunicaciones de terceros en su organización. A continuación, los revisores pueden examinar los mensajes para asegurarse de que cumplen con los estándares de mensajes de su organización y resolverlos con el tipo de clasificación.

Estas directivas también pueden ayudarle a superar muchos desafíos de cumplimiento modernos, entre los que se incluyen:

- Supervisión de tipos crecientes de canales de comunicación
- El volumen creciente de datos de mensajes
- Cumplimiento normativo & el riesgo de multas

En algunas organizaciones, puede haber una separación de tareas entre el soporte técnico de TI y el grupo de administración de cumplimiento. Microsoft 365 admite la separación entre la configuración de características de directiva de supervisión y la configuración de directivas para comunicaciones capturadas. Por ejemplo, el grupo de TI de una organización puede ser responsable de configurar grupos y permisos de roles para admitir directivas de supervisión configuradas y administradas por el equipo de cumplimiento de la organización.

Para obtener una introducción rápida a las directivas de supervisión, vea el [vídeo de](https://youtu.be/C3Y8WZ7o_dI) directiva de supervisión en el canal de [Microsoft Mechanics.](https://www.youtube.com/user/OfficeGarageSeries)

## <a name="transitioning-from-supervision"></a>Transición desde la supervisión

Las organizaciones que usan directivas de supervisión y planean la transición a directivas de cumplimiento de comunicaciones en [Microsoft 365](communication-compliance.md) deben comprender estos puntos importantes:

- La solución de supervisión de Microsoft 365 se reemplazará completamente por la solución de cumplimiento de comunicaciones de Microsoft 365. Para las organizaciones que transiciónn al cumplimiento de comunicaciones desde las  directivas de supervisión, se recomienda crear nuevas directivas de cumplimiento de comunicaciones que tengan las mismas condiciones que las directivas de supervisión existentes para permitir nuevas mejoras de investigación y corrección. Al realizar la transición al cumplimiento de comunicaciones en Microsoft 365, debe planear la exportación de datos de informes desde la supervisión si tiene requisitos de directiva de retención de cumplimiento interno.
- Mientras tanto, las organizaciones pueden usar ambas soluciones en paralelo hasta que se migren completamente, pero las directivas usadas en cada solución deben tener nombres *de directiva únicos.* Los grupos y los diccionarios de palabras clave personalizadas se pueden compartir entre soluciones durante el período de transición.
- Los mensajes guardados en supervisión en las coincidencias de directivas de Microsoft 365 no se pueden mover ni compartir en el cumplimiento de las comunicaciones en Microsoft 365.

Para obtener información sobre la retirada para la supervisión en Office 365, consulte la guía básica de [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener más información.

## <a name="scenarios-for-supervision-policies"></a>Escenarios para directivas de supervisión

Las directivas de supervisión pueden ayudar a supervisar las comunicaciones de la organización en varias áreas:

- **Directivas corporativas**

    Los empleados deben cumplir con un uso aceptable, estándares éticos y otras directivas corporativas en todas sus comunicaciones relacionadas con la empresa. Las directivas de supervisión pueden detectar infracciones de directivas y ayudarle a tomar medidas correctivas para ayudar a mitigar estos tipos de incidentes. Por ejemplo, puede supervisar posibles violaciones de recursos humanos, como acoso o el uso de lenguaje inapropiado u ofensivo en las comunicaciones de los empleados.

- **Administración de riesgos**

    Las organizaciones son responsables de todas las comunicaciones distribuidas en toda su infraestructura y sistemas de red corporativos. El uso de directivas de supervisión para ayudar a identificar y administrar posibles riesgos y exposición legal puede ayudar a minimizar los riesgos antes de que puedan dañar las operaciones corporativas. Por ejemplo, puede supervisar su organización en busca de comunicaciones no autorizadas para proyectos confidenciales, como próximas adquisiciones, fusiones, divulgación de ganancias, reorganizaciones o cambios en el equipo directivo.

- **Cumplimiento normativo**

    La mayoría de las organizaciones deben cumplir con algún tipo de estándar de cumplimiento normativo como parte de sus procedimientos de funcionamiento normales. Estas normativas a menudo requieren que las organizaciones implementen algún tipo de proceso de supervisión o supervisión para la mensajería adecuada para su sector. La Regla 3110 de la Autoridad Reguladora de la Industria Financiera (FINRA) es un buen ejemplo de un requisito para que las organizaciones tengan procedimientos de supervisión para supervisar las actividades de sus empleados y los tipos de empresas en las que participa. Otro ejemplo puede ser la necesidad de supervisar a los agentes-distribuidores de la organización para protegerse contra posibles actividades de tráfico de dinero, tráfico interno, colusión o negociación. Las directivas de supervisión pueden ayudar a su organización a cumplir estos requisitos proporcionando un proceso para supervisar e informar sobre las comunicaciones corporativas.

## <a name="components"></a>Componentes

### <a name="supervision-policy"></a>Directiva de supervisión

Las directivas de supervisión se crean en el Centro de cumplimiento. Estas directivas definen qué comunicaciones y usuarios están sujetos a revisión en su organización, definen condiciones personalizadas que deben cumplir las comunicaciones y especifican quién debe realizar revisiones. Los usuarios incluidos en el grupo de roles Revisión de supervisión pueden configurar directivas y cualquier persona que tenga asignado este rol puede acceder a la página Supervisión en el Centro de cumplimiento.

### <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar la supervisión, debe determinar quién necesita revisar sus comunicaciones. En la directiva, las direcciones de correo electrónico de usuario identifican a personas o grupos de personas que se deben supervisar. Algunos ejemplos de estos grupos son Grupos de Microsoft 365, listas de distribución basadas en Exchange y canales de Microsoft Teams. También puede excluir usuarios o grupos específicos de la supervisión con un grupo supervisado o una lista de grupos.

>[!IMPORTANT]
>Los usuarios supervisados por directivas de supervisión deben tener una licencia de Cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento cumplimiento avanzado, o estar incluidos en una suscripción de Office 365 Enterprise E5, o estar incluidos en una suscripción de Microsoft 365 E5. Si no tiene un plan Enterprise E5 existente y desea probar la supervisión, puede registrarse para obtener una versión de prueba de [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)

### <a name="reviewers"></a>Reviewers

Al crear una directiva de supervisión, debe determinar quién realizará las revisiones de los mensajes de los usuarios supervisados. En la directiva, las direcciones de correo electrónico de los usuarios identifican a personas o grupos de personas para revisar las comunicaciones supervisadas. Todos los revisores deben tener buzones hospedados en Exchange Online.

### <a name="groups-for-supervised-users-and-reviewers"></a>Grupos para usuarios y revisores supervisados

Para simplificar la configuración, cree grupos para las personas que necesitan revisar sus comunicaciones y grupos para las personas que revisan dichas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si desea supervisar las comunicaciones entre dos grupos distintos de personas o si desea especificar un grupo que no esté supervisado.

Cuando selecciona un grupo de Microsoft 365 para usuarios supervisados, la directiva supervisa el contenido del buzón compartido y los canales de Microsoft Teams asociados al grupo. Al seleccionar una lista de distribución, la directiva supervisa los buzones de usuario individuales.

### <a name="supported-communication-types"></a>Tipos de comunicación admitidos

Con las directivas de supervisión, puede elegir supervisar los mensajes en una o varias de las siguientes plataformas de comunicación:

- **Correo electrónico de Exchange:** Todos los buzones hospedados en Exchange Online como parte de su suscripción a Microsoft 365 son aptos para la supervisión de mensajes. Los correos electrónicos y los datos adjuntos que coinciden con las condiciones de la directiva de supervisión están disponibles al instante para la supervisión y en los informes de supervisión. Los tipos de datos adjuntos admitidos para la supervisión son los mismos que los tipos de archivo admitidos para las inspecciones de contenido de reglas [de flujo de correo de Exchange.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)

- **Microsoft Teams:** Las comunicaciones de chat y los datos adjuntos asociados en los canales públicos y privados de Microsoft Teams y los chats individuales se pueden supervisar. Los chats de Teams que coinciden con las condiciones de la directiva de supervisión se procesan una vez cada 24 horas y, a continuación, están disponibles para supervisión y en informes de supervisión. Use las siguientes configuraciones de administración de grupos para supervisar los chats de usuarios individuales y las comunicaciones de canal en Teams:

    - **Para la supervisión de chat de Teams:** Asignar usuarios individuales o asignar un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la directiva de supervisión. Esta configuración es para relaciones de usuario/chat de 1 a 1 o de uno a varios.
    - **Para las comunicaciones del Canal de Teams:** Asigne todos los canales de Microsoft Team o grupos de Microsoft 365 que desee supervisar que contengan un usuario específico a la directiva de supervisión. Si agrega el mismo usuario a otros canales de Microsoft Teams o grupos de Microsoft 365, asegúrese de agregar estos nuevos canales y grupos a la directiva de supervisión.

- **Skype Empresarial Online:** Las comunicaciones de chat y los datos adjuntos asociados en Skype Empresarial Online se pueden supervisar. Los chats de Skype Empresarial Online que coinciden con las condiciones de la directiva de supervisión se procesan una vez cada 24 horas y, a continuación, están disponibles para la supervisión y los informes de supervisión. Las conversaciones de chat supervisadas se encuentran en conversaciones [anteriores guardadas en Skype Empresarial Online.](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)  Use la siguiente configuración de administración de grupos para supervisar las comunicaciones de chat de usuario en Skype Empresarial Online:

    - **Para la supervisión de chat de Skype Empresarial Online:** Asignar usuarios individuales o asignar un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la directiva de supervisión. Esta configuración es para relaciones de usuario/chat de 1 a 1 o de uno a varios.

- **Orígenes de terceros:** Puede supervisar las comunicaciones de orígenes de terceros (como Facebook o DropBox) para los datos importados en los buzones de la organización. [Obtenga información sobre cómo importar datos](archiving-third-party-data.md)de terceros.

Las comunicaciones capturadas en estas plataformas se conservan durante siete años para cada directiva de forma predeterminada, incluso si los usuarios abandonan su organización y su buzón se elimina.

### <a name="policy-settings"></a>Configuración de directivas

#### <a name="direction"></a>Dirección

De forma predeterminada, **se muestra la** condición Dirección y no se puede quitar. La configuración de la dirección de comunicación en una directiva se elige de forma individual o conjunta:

- **Entrante:** puede elegir **Entrante** para  revisar las comunicaciones  enviadas a las personas que eligió supervisar de personas que no están incluidas en la directiva.
- **Saliente:** puede elegir **Saliente** si desea  revisar las comunicaciones  enviadas desde las personas que eligió supervisar a las personas que no están incluidas en la directiva.
- **Interno:** puede elegir **Interno** para revisar las comunicaciones enviadas **entre** las personas que identificó en la directiva.

#### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la directiva de supervisión. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger números de tarjeta de crédito, números de cuentas bancarias, números de pasaporte y mucho más. Como parte de la prevención de pérdida de datos [(DLP),](data-loss-prevention-policies.md)la configuración de información confidencial puede usar patrones, proximidad de caracteres, niveles de confianza e incluso tipos de datos personalizados para ayudar a identificar y marcar el contenido que puede ser confidencial. Los tipos de información confidencial predeterminados son:

- Financiera
- Médica y de salud
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los patrones incluidos en los tipos predeterminados, vea Definiciones de entidad de tipo [de información confidencial.](sensitive-information-type-entity-definitions.md)

#### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizadas

Configure diccionarios de palabras clave personalizados (o léxicos) para proporcionar una administración sencilla de palabras clave específicas de su organización o sector. Los diccionarios de palabras clave admiten hasta 100 KB de términos (compresión posterior) en el diccionario y admiten cualquier idioma. El límite del espacio empresarial también es de 100 KB después de la compresión. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizadas a una sola directiva o tener un único diccionario de palabras clave por directiva. Estos diccionarios se asignan en una directiva de supervisión y pueden obtenerse de un archivo (como una lista .csv o .txt) o de una lista que puede importar en el Centro de [cumplimiento.](create-a-keyword-dictionary.md)

#### <a name="offensive-language"></a>Lenguaje ofensivo

Supervise los mensajes de correo electrónico enviados o recibidos en su organización para obtener un idioma ofensivo. El modelo usa una combinación de aprendizaje automático, inteligencia artificial y palabras clave para identificar el idioma de los mensajes de correo electrónico que probablemente infrinjan las directivas contra acosos y acosos. El modelo de idioma ofensivo admite actualmente palabras clave en inglés y supervisa el cuerpo de los mensajes de correo electrónico.

>[!NOTE]
>Cree una [directiva de prevención de pérdida](create-test-tune-dlp-policy.md) de datos con un diccionario de palabras clave [personalizado](create-a-keyword-dictionary.md) de términos bloqueados si necesita:
>
>- supervisar las comunicaciones de Microsoft Teams en su organización en busca de lenguaje ofensivo
>- impedir o bloquear el lenguaje ofensivo en las comunicaciones de la organización

El modelo no proporciona una lista exhaustiva del lenguaje ofensivo. Además, los estándares culturales y de idioma cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar el modelo según su criterio. Aunque el modelo puede ayudar a su organización a supervisar el lenguaje ofensivo, el modelo no está diseñado para proporcionar el único medio de supervisión o direccionamiento de dicho idioma de su organización. Su organización, no Microsoft, sigue siendo responsable de todas las decisiones relacionadas con la supervisión y el bloqueo del lenguaje ofensivo.

El modelo de lenguaje ofensivo supervisa el correo electrónico en busca de opiniones asociadas con los siguientes tipos de idioma:

|**Tipo**|**Descripción**|
|:-----|:-----|
| **Blasfedades** | Expresiones que enaltez a la mayoría de los usuarios. |
| **Slurs** | Expresiones que expresan el perjuicio contra determinados grupos (por ejemplo, carrera, etnicidad, orientación sexual, discapacidad). |
| **Convergents** | Expresiones que provocan, provocan, ridiculen o podrían causar frustración o violencia. |
| **Expresiones camufladas** | Expresiones para las que el significado o la pronunciación es igual que otro término más ofensivo. |

#### <a name="conditional-settings"></a>Configuración condicional
<a name="ConditionalSettings"> </a>

Las condiciones que elija para la directiva se aplican a las comunicaciones de correo electrónico y fuentes de terceros de su organización (como facebook o DropBox).

En la tabla siguiente se explica más acerca de cada condición.
  
|**Condition**|**Cómo usar esta condición**|
|:-----|:-----|
| **El mensaje se recibe desde cualquiera de estos dominios** <br><br> **El mensaje no se recibe de ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes recibidos. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico especificado se aplica por separado, solo debe aplicarse un dominio o dirección de correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea supervisar todo el correo electrónico de un dominio específico pero desea excluir los mensajes que no necesitan  revisión (boletines, anuncios, etc.), debe configurar la condición de que no se reciba un mensaje de ninguna de estas condiciones de dominios que excluya la dirección de correo electrónico (por ejemplo, "newsletter@contoso.com"). |
| **El mensaje se envía a cualquiera de estos dominios** <br><br> **El mensaje no se envía a ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes enviados. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico se aplica por separado, solo debe aplicarse un dominio o dirección de correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea supervisar todo el correo electrónico enviado a un dominio específico pero desea excluir los mensajes enviados que no necesitan revisión, debe configurar dos condiciones: <br> - Se **envía un mensaje a cualquiera de estos dominios** condición que define el dominio ("contoso.com"), AND <br> - No **se envía un mensaje a ninguna condición de estos** dominios que excluya la dirección de correo electrónico ("subscriptions@contoso.com"). |
| **El mensaje se clasifica con cualquiera de estas etiquetas** <br><br> **El mensaje no se clasifica con ninguna de estas etiquetas** | Para aplicar la directiva cuando determinadas etiquetas de retención se incluyen o excluyen en un mensaje. Las etiquetas de retención deben configurarse por separado y las etiquetas configuradas se eligen como parte de esta condición. Cada etiqueta que elija se aplica por separado (solo debe aplicarse una de estas etiquetas para que la directiva se aplique al mensaje). Para obtener más información acerca de las etiquetas de retención, vea [Más información sobre las directivas de retención y las etiquetas de retención.](retention.md)|
| **El mensaje contiene cualquiera de estas palabras** <br><br> **El mensaje no contiene ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en un mensaje, escriba cada palabra o frase y separe con una coma. Cada palabra que escriba se aplica por separado (solo debe aplicarse una palabra para que la directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
| **Los datos adjuntos contienen cualquiera de estas palabras** <br><br> **Los datos adjuntos no contienen ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en un archivo adjunto de mensaje (como un documento de Word), escriba cada palabra o frase y separe con una coma. Cada palabra que escriba se aplica por separado (solo debe aplicarse una palabra para que la directiva se aplique a los datos adjuntos). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
| **Los datos adjuntos son cualquiera de estos tipos de archivo** <br><br> **Los datos adjuntos no son ninguno de estos tipos de archivo** | Para supervisar las comunicaciones que incluyen o excluyen tipos específicos de datos adjuntos, escriba las extensiones de archivo (como .exe o .pdf). Si desea incluir o excluir varias extensiones de archivo, escriba estas en líneas independientes. Solo debe coincidir una extensión de datos adjuntos para que se aplique la directiva.|
| **El tamaño del mensaje es mayor que** <br><br> **El tamaño del mensaje no es mayor que** | Para revisar los mensajes en función de un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que esté sujeto a revisión. Por ejemplo, si  especifica que el tamaño del mensaje es superior a \> **1,0 MB,** todos los mensajes de 1,01 MB o más estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
| **Los datos adjuntos son más grandes que** <br><br> **Los datos adjuntos no son mayores que** | Para revisar los mensajes en función del tamaño de sus datos adjuntos, especifique el tamaño máximo o mínimo que puede tener un archivo adjunto antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. Por ejemplo, si  especifica datos adjuntos de más de \> **2,0 MB,** todos los mensajes con datos adjuntos de 2,01 MB o más estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"></a> Cada palabra que escriba y separe con una coma se aplica por separado (solo debe aplicarse una palabra para que la condición de directiva se aplique al correo electrónico o los datos adjuntos). Por ejemplo, vamos a usar la condición, **Message** contiene cualquiera de estas palabras, con las palabras clave "banker" y "insider trading" separadas por una coma (banker, insider trading). La directiva se aplica a cualquier mensaje que incluya la palabra "banker" o la frase "insider trading". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o los datos adjuntos deben coincidir exactamente con lo que escriba.

Para examinar los mensajes de correo electrónico y los datos adjuntos [](create-a-keyword-dictionary.md) de las mismas palabras clave, cree una directiva de prevención de pérdida de datos con un diccionario de palabras clave personalizado para los [términos](create-test-tune-dlp-policy.md) que desea supervisar. Esta configuración de directiva identifica palabras clave definidas que aparecen en el mensaje de correo **electrónico O** en los datos adjuntos del correo electrónico. El uso de la configuración de directiva condicional estándar *(el* mensaje contiene cualquiera de estas palabras y  *Datos* adjuntos contiene cualquiera de estas palabras) para identificar los términos de los mensajes y los datos adjuntos requiere que los términos estén presentes en el mensaje y en los datos adjuntos.
  
##### <a name="enter-multiple-conditions"></a>Especificar varias condiciones

Si especifica varias condiciones, Microsoft 365 usa todas las condiciones juntas para determinar cuándo aplicar la directiva a los elementos de comunicación. Al configurar varias condiciones, se deben cumplir todas las condiciones para que se aplique la directiva, a menos que escriba una excepción. Por ejemplo, necesita una directiva que se aplique si un mensaje contiene la palabra "trade" y es superior a 2 MB. Sin embargo, si el mensaje también contiene las palabras "Aprobado por Contoso financial", la directiva no debe aplicarse. Por lo tanto, en este caso, las tres condiciones serían las siguientes:
  
- **El mensaje contiene cualquiera de estas palabras,** con la palabra clave "trade"

- **El tamaño del mensaje es mayor que**, con el valor 2 MB

- **El mensaje no contiene ninguna de estas palabras,** con las palabras clave "Aprobado por el equipo financiero de Contoso"

#### <a name="review-percentage"></a>Porcentaje de revisión

Si desea reducir la cantidad de contenido que se va a revisar, puede especificar un porcentaje de todas las comunicaciones regida por una directiva de supervisión. Se selecciona una muestra aleatoria en tiempo real del contenido del porcentaje total de contenido que coincide con las condiciones de directiva elegidas. Si desea que los revisores revisen todos los elementos, puede escribir **el 100 %** en una directiva de supervisión.

## <a name="monitor--manage"></a>Supervisar & administrar

Es fácil supervisar los resultados de las directivas de supervisión y aplicar una etiqueta de resolución. Puede ver rápidamente:

- El estado de los elementos revisados
- Usuarios y grupos bajo supervisión
- Usuarios y grupos designados como revisores

### <a name="supervision-policy-dashboard"></a>Panel de directivas de supervisión

Use el panel de directivas de supervisión para administrar los resultados de la directiva de supervisión y resolver los elementos pendientes. Este panel permite a los revisores ver los elementos que deben revisarse, actuar en un elemento y revisar los resultados de los elementos revisados y resueltos anteriormente para cada directiva de supervisión. Puede obtener acceso al panel de la directiva de supervisión en el Centro de cumplimiento **en Supervisión** de su  >  *directiva personalizada*  >  **abierta.**

#### <a name="dashboard-home"></a>Inicio del panel

La página **principal del** panel tiene varias secciones que le ayudarán a actuar rápidamente en las directivas de supervisión. Aquí puede:

- Revisar rápidamente los aspectos destacados pendientes y resueltos de la semana
- Ver una lista de los usuarios supervisados y grupos supervisados para la directiva seleccionada
- Ver una lista de los revisores y revisar los equipos para la directiva seleccionada
- Ver qué plataformas de comunicación tienen contenido bajo supervisión para la directiva

#### <a name="review-tab"></a>Pestaña Revisar

La **pestaña** Revisar es donde los revisores clasifican y resuelven los elementos identificados por la directiva seleccionada. Aquí puede:

- Filtra por elementos pendientes, conformes, no compatibles e questionables.
- Etiquete un solo elemento como compatible, no compatible o questionable. También puede grabar un comentario con el elemento para ayudar a aclarar la acción de etiquetado realizada.
- Etiquetar de forma masiva varios elementos como compatibles, no compatibles o questionables. También puede grabar un comentario con varios elementos para ayudar a aclarar la acción de etiquetado realizada.
- Ver el historial de las etiquetas de un solo elemento. Incluye quién resolvió el elemento, la fecha y hora de la acción, la etiqueta de resolución y los comentarios incluidos.
- Reclasifique los elementos revisados anteriormente como compatibles, no compatibles o questionables. También puede grabar un comentario con uno o varios elementos para ayudar a aclarar la acción de reclasificación realizada.

#### <a name="resolved-items-tab"></a>Pestaña Elementos resueltos

La **pestaña Elementos resueltos** es donde los revisores pueden ver todos los elementos resueltos anteriormente para la directiva seleccionada. Aquí puede:

- Ver y ordenar rápidamente el asunto, el remitente y la fecha de los elementos resueltos
- Ver la clasificación y el historial de comentarios de cualquier elemento seleccionado

## <a name="reports"></a>Informes

Use los informes de supervisión para ver la actividad de revisión en el nivel de directiva y revisor. Para cada directiva, también puede ver estadísticas en directo sobre el estado actual de la actividad de revisión. Puede usar los informes de supervisión para:
  
- Compruebe que las directivas funcionan según lo previsto.
- Descubra cuántas comunicaciones se deben revisar.
- Descubra cuántas comunicaciones no son compatibles y cuáles pasan revisión. Esta información puede ayudarle a decidir si ajustar las directivas o cambiar el número de revisores.

### <a name="view-the-supervision-report"></a>Ver el informe de supervisión

1. Inicie sesión en el [Centro de cumplimiento](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador con permisos para ver informes de supervisión.
2. Vaya al panel **de informes** o a la supervisión para ver el widget de informes de supervisión para obtener un resumen de la actividad de la directiva de supervisión \>  actual. 
3. Seleccione el widget **Supervisión** para abrir la página del informe detallado.

>[!NOTE]
>Si no puede tener acceso  a la página Informes, compruebe que es miembro del grupo de roles Revisión de supervisión, como se describe en Hacer que la supervisión esté disponible en [su organización.](configure-supervision-policies.md) La inclusión en este grupo de roles le permite crear y administrar las políticas de supervisión y ejecutar el informe.
  
### <a name="how-to-use-the-report"></a>Cómo usar el informe

Este informe enumera cada directiva y el número de comunicaciones en cada fase del proceso de revisión. Use el informe para:
  
- Ver datos de todas las directivas o directivas específicas.
- Ver datos agrupados por tipo de etiqueta, revisor o tipo de mensaje.
- Exportar datos a un archivo CSV en función de la fecha de actividad, la directiva y la actividad del revisor.
- Filtrar datos según la fecha de actividad, el tipo de etiqueta, el revisor y el tipo de mensaje.

Este es un desglose de los valores que se muestran en la **columna Tipo de** etiqueta.
  
|**Tipo de etiqueta**|**Qué significa**|
|:-----|:-----|
| **No revisado** | El número de correos electrónicos que aún no se han revisado. Estos correos electrónicos esperan su revisión en el panel de supervisión de Microsoft 365.
| **Compliant** | El número de correos electrónicos revisados y marcados como compatibles. Estos mensajes aún necesitan resolución. |
| **Questionable** | El número de correos electrónicos revisados y marcados como cuestionables. Sirve como marca para que otros revisores le ayuden a comprobar si un correo electrónico necesita investigar el cumplimiento. Estos mensajes aún necesitan resolución. |
| **No compatible (activo)** | El número de mensajes de correo electrónico no compatibles que los revisores están investigando actualmente. |
| **No compatible (resuelto)** | El número de mensajes de correo electrónico no compatibles que los revisores investigaron y resolvieron. |
| **Directiva de acceso** | El número total (diario) de mensajes de Exchange, Teams y orígenes de datos de terceros que coincidían con una o más condiciones definidas en una directiva de supervisión |
| **En Purview** | El número total (diario) de mensajes de Exchange, Teams y orígenes de datos de terceros analizados por una directiva de supervisión |
| **Resuelto** | El número total de mensajes de Exchange, Teams y orígenes de datos de terceros clasificados como **resueltos**|

>[!NOTE]
>Las directivas de supervisión deben aprovisionarse antes de que aparezcan en los informes. Si se eliminan las directivas, aún se muestran los datos históricos. Sin embargo, se indican como una "directiva inexistente" y la **función Export** no está disponible.

## <a name="audit"></a>Auditoría

En algunos casos, debe proporcionar información a auditores normativos o de cumplimiento para demostrar la supervisión de las actividades y comunicaciones de los empleados. Esta información puede ser un resumen de todas las actividades de supervisión asociadas a una directiva definida o en cualquier momento en que cambie una directiva de supervisión. Las directivas de supervisión tienen pistas de auditoría integradas para una preparación completa para las auditorías internas o externas. Los historiales detallados de auditoría de todas las acciones supervisadas por las directivas de supervisión proporcionan pruebas de los procedimientos de supervisión.

Vea las actividades de auditoría en el registro de auditoría unificado o con el cmdlet [de PowerShell Search-UnifiedAuditLog.](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog)

Por ejemplo, en el siguiente ejemplo se devuelven las actividades de todas las actividades de revisión de supervisión (directivas y reglas) y se muestra información detallada para cada una:

```PowerShell
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

En este ejemplo se devuelven las actividades de actualización de las directivas de cumplimiento de comunicaciones:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeletedAuditData
```

Además de la información proporcionada en los informes y registros de supervisión, también puede usar el cmdlet de PowerShell [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/get-supervisoryreviewactivity) para devolver una lista detallada completa de todas las actividades de la directiva de supervisión.

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar directivas de supervisión para su organización, consulte [Configurar directivas de supervisión.](configure-supervision-policies.md)
