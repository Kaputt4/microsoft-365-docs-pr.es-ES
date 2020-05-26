---
title: Referencia de la característica de cumplimiento de comunicación
description: Referencia de características para el cumplimiento de la comunicación en Microsoft 365. Obtenga información detallada y especificaciones para cada uno de los componentes de la característica.
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
ms.openlocfilehash: b524001f848a106ec2832c698b474cfce8ceb24b
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352093"
---
# <a name="communication-compliance-feature-reference"></a>Referencia de la característica de cumplimiento de comunicación

## <a name="policies"></a>Directivas

>[!Important]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas de la [solución Microsoft 365 Communication Compliance](https://compliance.microsoft.com/supervisoryreview).

Puede crear directivas de cumplimiento de comunicaciones para organizaciones de Microsoft 365 en el centro de cumplimiento de Microsoft 365. Las directivas de cumplimiento de comunicaciones definen qué comunicaciones y usuarios están sujetos a revisión en la organización, definen las condiciones personalizadas que deben cumplir las comunicaciones y especifican quién debe realizar revisiones. Los usuarios incluidos en el grupo de roles **Administrador de revisión de supervisión** pueden configurar directivas y cualquier persona con este rol asignado puede tener acceso a la página cumplimiento en la **comunicación** en el centro de cumplimiento de Microsoft 365. Si es necesario, puede exportar el historial de modificaciones de una directiva a un archivo. csv que también incluye el estado de las alertas revisión pendiente, elementos escalados y elementos resueltos. No se puede cambiar el nombre de las directivas y eliminarse cuando ya no se necesiten.

>[!NOTE]
>Las directivas de supervisión creadas en el centro de seguridad & cumplimiento para las suscripciones de Office 365 no se pueden migrar a Microsoft 365. Si va a migrar desde una suscripción de Office 365 a una suscripción de Microsoft 365, tendrá que crear nuevas directivas de cumplimiento de comunicaciones para reemplazar las directivas de supervisión existentes.

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de Directiva son opciones de directiva predefinidas que puede usar para crear rápidamente directivas para cumplir escenarios de cumplimiento comunes. Cada una de estas plantillas tiene diferencias en las condiciones y el ámbito, y todas las plantillas usan los mismos tipos de señales de detección. Puede elegir entre las siguientes plantillas de directiva:

|**Área**|**Plantilla de Directiva**|**Detalles**|
|:-----|:-----|:-----|
| **Idioma ofensivo y Antiacoso** | Supervisar las comunicaciones para un lenguaje ofensivo | -Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype empresarial <br> -Direction: entrante, saliente, interno <br> -Porcentaje de revisión: 100% <br> -Condiciones: clasificador de idioma ofensivo |
| **Información confidencial** | Supervisión de las comunicaciones para información confidencial | -Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype empresarial <br> -Direction: entrante, saliente, interno <br> -Porcentaje de revisión: 10% <br> -Condiciones: información confidencial, patrones de contenido prejuntos y tipos, opción de diccionario personalizado, datos adjuntos mayores de 1 MB |
| **Cumplimiento normativo** | Supervisión de las comunicaciones para obtener información relacionada con el cumplimiento de normativas financieras | -Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype empresarial <br> -Direction: entrante, saliente <br> -Porcentaje de revisión: 10% <br> -Condiciones: opción de diccionario personalizado, datos adjuntos mayores de 1 MB |

## <a name="supervised-users"></a>Usuarios supervisados

Antes de empezar a usar el cumplimiento de la comunicación, debe determinar quién necesita que se revisen sus comunicaciones. En la Directiva, las direcciones de correo electrónico de usuario identifican a los individuos o grupos de personas que deben supervisarse. Algunos ejemplos de estos grupos son los grupos de Microsoft 365, las listas de distribución basadas en Exchange, las comunidades de Yammer y los canales de Microsoft Teams. También puede excluir usuarios o grupos específicos del análisis con un grupo de exclusión específico o con una lista de grupos.

>[!IMPORTANT]
>Los usuarios a los que se aplican las directivas de cumplimiento de comunicaciones deben tener una licencia de cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento de cumplimiento avanzado o incluirse en una suscripción a Office 365 Enterprise E5. Si no tiene un plan existente de Enterprise E5 y desea probar el cumplimiento de la comunicación, puede [registrarse para obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Reviewers

Al crear una directiva de cumplimiento de la comunicación, debe determinar quién revisa los mensajes de los usuarios supervisados. En la Directiva, las direcciones de correo electrónico de usuario identifican personas o grupos de personas para revisar las comunicaciones supervisadas. Todos los revisores deben tener buzones de correo hospedados en Exchange Online y deben tener asignados los roles de **Administración de casos** y **revisión** . Cuando se agregan revisores a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la Directiva y proporciona vínculos a la información sobre el proceso de revisión.

## <a name="groups-for-supervised-users-and-reviewers"></a>Grupos de usuarios supervisados y revisores

Para simplificar la configuración, cree grupos para los usuarios que necesitan sus comunicaciones revisadas y grupos para los usuarios que revisen dichas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, si desea examinar las comunicaciones entre dos grupos de personas distintos, o si desea especificar un grupo que no está supervisado.

Al seleccionar un grupo de 365 de Microsoft para los usuarios supervisados, la Directiva examina el contenido del buzón compartido y los canales de Microsoft Teams asociados con el grupo. Al seleccionar una lista de distribución, la Directiva examina los buzones de correo de los usuarios individuales. La adición de grupos y listas de distribución a las directivas de cumplimiento de comunicaciones forma parte del conjunto de reglas y condiciones generales, por lo que el número máximo de grupos y listas de distribución que admite una directiva varía en función del número de condiciones que se agreguen también a la Directiva. Cada Directiva debe admitir aproximadamente 20 grupos o listas de distribución, según el número de condiciones adicionales presentes en la Directiva.

## <a name="supported-communication-types"></a>Tipos de comunicación admitidos

Con las directivas de cumplimiento de la comunicación, puede elegir analizar los mensajes en una o varias de las plataformas de comunicación siguientes como un grupo o como orígenes independientes. Las comunicaciones capturadas en estas plataformas se conservan durante siete años para cada directiva de forma predeterminada, incluso si los usuarios dejan la organización y sus buzones de correo se eliminan.

- **Microsoft Teams**: se pueden analizar las comunicaciones de chat y los datos adjuntos asociados tanto en canales públicos y privados de Microsoft Teams como en chats individuales. Chats y datos adjuntos de Microsoft teams que cumplan las condiciones de la Directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Use las siguientes configuraciones de administración de grupos para supervisar los chats de usuarios individuales y las comunicaciones de canal en Microsoft Teams:

    - **Para las comunicaciones de chat de Microsoft Teams:** Asigne usuarios individuales o asigne un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la Directiva de cumplimiento de la comunicación. Esta configuración es para relaciones de usuario y chat uno a uno o uno a varios.
    - **Para las comunicaciones de canal de Teams:** Asigne cada canal de Microsoft Teams o grupo de Microsoft 365 que desee analizar que contenga un usuario específico a la Directiva de cumplimiento de la comunicación. Si agrega el mismo usuario a otros canales de Microsoft Teams o a grupos de Microsoft 365, asegúrese de agregar estos nuevos canales y grupos a la Directiva de cumplimiento de la comunicación.

- **Correo electrónico de Exchange**: los buzones hospedados en Exchange online como parte de su suscripción a Microsoft 365 u Office 365 son aptos para el análisis de mensajes. Los mensajes de correo electrónico de Exchange y los datos adjuntos que cumplen las condiciones de la Directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Los tipos de datos adjuntos admitidos para el cumplimiento de la comunicación son los mismos que los [tipos de archivo compatibles con las visitas de contenido de reglas de flujo de correo de Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Yammer**: se pueden examinar mensajes privados y conversaciones públicas y datos adjuntos asociados en comunidades de Yammer. Cuando se agrega un usuario a una directiva de cumplimiento de la comunicación que incluye Yammer como un canal definido, las comunicaciones de todas las comunidades de Yammer a las que pertenece el usuario se incluyen en el proceso de detección. Chats y datos adjuntos de Yammer que cumplen las condiciones de la Directiva de cumplimiento de comunicaciones pueden tardar hasta 24 horas en procesarse. Yammer debe estar en [modo nativo](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) para las directivas de cumplimiento de comunicaciones para supervisar las comunicaciones y los datos adjuntos de Yammer. En el modo nativo, todos los usuarios de Yammer están en Azure Active Directory (AAD), todos los grupos son Grupos de Office 365 y todos los archivos se almacenan en SharePoint Online.

- **Skype empresarial online**: las comunicaciones de chat y los datos adjuntos asociados en Skype empresarial online pueden supervisarse. Chats de Skype empresarial online la coincidencia de las condiciones de la Directiva de cumplimiento de comunicaciones puede tardar hasta 24 horas en procesarse. Las conversaciones de chat supervisadas se han originado a partir de [conversaciones anteriores guardadas en Skype empresarial online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Use la siguiente configuración de administración de grupos para supervisar las comunicaciones de chat de los usuarios en Skype empresarial online:

    - **Para las comunicaciones de chat de Skype empresarial online**: asigne usuarios individuales o asigne un [grupo de distribución](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) a la Directiva de cumplimiento de la comunicación. Esta configuración es para relaciones de usuario y chat uno a uno o uno a varios.

- **Orígenes de terceros**: puede examinar las comunicaciones de orígenes de terceros para los datos importados en buzones de la organización de Microsoft 365. Los conectores admiten los siguientes recursos de terceros:

    - [Bloomberg instantáneo](archive-instant-bloomberg-data.md)
    - [Facebook](archive-facebook-data-with-sample-connector.md)
    - [LinkedIn](archive-linkedin-data.md)
    - [Twitter](archive-twitter-data-with-sample-connector.md)
    - [Conector de datos personalizado](archiving-third-party-data.md)

Debe configurar un conector de terceros para la organización de Microsoft 365 antes de poder asignar el conector a una directiva de cumplimiento de la comunicación. La sección **orígenes de terceros** del Asistente para la Directiva de cumplimiento de comunicaciones solo muestra los conectores de terceros configurados actualmente.

## <a name="transitioning-from-supervision-in-office-365"></a>Transición desde la supervisión en Office 365

Las organizaciones que usan directivas de supervisión en Office 365 y la planeación de la transición a directivas de cumplimiento de comunicaciones en Microsoft 365 necesitan comprender estos puntos importantes:

- Ambas soluciones pueden usarse en paralelo en la organización, pero las directivas que se usan en cada solución deben tener nombres de directiva únicos. Los grupos y los diccionarios de palabras clave personalizados se pueden compartir entre las soluciones durante un período de transición.
- Los mensajes guardados en la supervisión de las coincidencias de directivas de Office 365 no se pueden mover ni compartir con el cumplimiento de la comunicación en Microsoft 365.
- La solución de supervisión de Office 365 se reemplazará completamente por la solución de cumplimiento de comunicaciones en Microsoft 365. Se recomienda crear nuevas directivas en el cumplimiento de la comunicación que tengan la misma configuración que las directivas de supervisión existentes para usar las nuevas mejoras de investigación y corrección. Al realizar la transición al cumplimiento de la comunicación en Microsoft 365, debe planear la exportación de los datos de informes desde la supervisión en Office 365 si tiene requisitos internos de la Directiva de retención de cumplimiento.

Para obtener información de jubilación para la supervisión en Office 365, consulte el [mapa de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obtener más información.

## <a name="policy-settings"></a>Configuración de directivas

### <a name="users"></a>Usuarios

Tiene la opción de seleccionar **todos los usuarios** o de definir usuarios específicos en una directiva de cumplimiento de la comunicación. La selección de **todos los usuarios** aplica la Directiva a todos los usuarios y a todos los grupos en los que cualquier usuario se incluye como miembro. La definición de usuarios específicos aplica la Directiva a los usuarios definidos y a todos los grupos de los que los usuarios definidos se incluyen como miembros.

### <a name="direction"></a>Dirección

De forma predeterminada, la condición **es la dirección** se muestra y no se puede quitar. La configuración de la dirección de la comunicación en una directiva se eligen de forma individual o conjunta:

- **Entrante**: puede elegir **entrante** para revisar las comunicaciones enviadas **a** las personas que haya elegido supervisar.
- **Saliente**: puede elegir **saliente** si desea revisar las comunicaciones enviadas **por** las personas que ha elegido supervisar.
- **Interno**: puede elegir **interna** para revisar las comunicaciones enviadas **entre** las personas que identificó en la Directiva.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la Directiva de cumplimiento en la comunicación. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuentas bancarias, números de pasaporte, etc. Como parte de la [prevención de pérdida de datos (DLP)](data-loss-prevention-policies.md), la configuración de información confidencial puede usar patrones, proximidad de caracteres, niveles de confianza e incluso tipos de datos personalizados para ayudar a identificar y marcar contenido que pueda ser confidencial. Los tipos de información confidencial predeterminados son:

- Financiera
- Médico y salud
- Privacidad
- Tipo de información personalizada

Para obtener más información acerca de los detalles de información confidencial y los patrones incluidos en los tipos predeterminados, vea tipos de [información confidencial definiciones de entidad](sensitive-information-type-entity-definitions.md).

### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizados

Configure diccionarios de palabras clave personalizados (o léxicos) para proporcionar una administración sencilla de palabras clave específicas de la organización o del sector. Los diccionarios de palabras clave admiten hasta 100.000 términos por Diccionario y admiten cualquier idioma. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizados a una sola directiva o tener un diccionario de palabras clave único por directiva. Estos diccionarios se asignan en una directiva de cumplimiento de la comunicación y pueden originarse a partir de un archivo (como una lista. csv o. txt) o de una lista que se puede [importar en el centro de cumplimiento](create-a-keyword-dictionary.md). Use diccionarios personalizados cuando necesite admitir términos o idiomas específicos de la organización y las directivas.

### <a name="classifiers"></a>Clasificadores

Los clasificadores integrados examinan los mensajes enviados o recibidos en todos los canales de comunicación de la organización para diferentes tipos de problemas de cumplimiento. Los clasificadores usan una combinación de inteligencia artificial y palabras clave para identificar el idioma de los mensajes que puedan infringir las directivas Antiacoso. Actualmente, los clasificadores integrados solo admiten palabras clave en inglés en los mensajes.

Cumplimiento en comunicación los clasificadores integrados examinan las comunicaciones de términos y sentimientos para los siguientes tipos de idiomas:

- **Amenaza**: busca amenazas para confirmar violencia o daño físico a una persona o propiedad.
- **Acosar**: explora una conducta ofensiva dirigida a personas relacionadas con la raza, el color, la religión y el origen nacional.
- **Blasfemias**: explora las expresiones irreverentes que avergonzan a la mayoría de las personas.

Los clasificadores integrados no proporcionan una lista exhaustiva de términos en estas áreas. Además, los estándares de idioma y culturales cambian continuamente y, teniendo en cuenta estas realidades, Microsoft se reserva el derecho de actualizar los clasificadores según su criterio. Aunque los clasificadores pueden ayudar a su organización a supervisar estas áreas, los clasificadores no están diseñados para proporcionar el único medio para la supervisión o el direccionamiento de ese idioma para su organización. Su organización, no Microsoft, sigue siendo responsable de todas las decisiones relacionadas con el lenguaje de análisis y bloqueo en estas áreas.

Para obtener información acerca de los clasificadores en Microsoft 365, consulte [Classifiers](classifier-getting-started-with.md).

### <a name="conditional-settings"></a>Configuración condicional
<a name="ConditionalSettings"> </a>

Las condiciones que elija para la Directiva se aplican a las comunicaciones de los orígenes de correo electrónico y de terceros de la organización (como en Facebook o DropBox).

La siguiente tabla explica más sobre cada condición.
  
|**Condición**|**Cómo usar esta condición**|
|:-----|:-----|
| **El contenido coincide con cualquiera de estos clasificadores** | Se aplican a la Directiva cuando se incluyen o excluyen clasificadores en un mensaje. Algunos clasificadores están predefinidos en su espacio empresarial y los clasificadores personalizados deben configurarse por separado antes de que estén disponibles para esta condición. Solo se puede definir un clasificador como condición en una directiva. Para obtener más información acerca de la configuración de clasificadores, consulte [Classifiers](classifier-getting-started-with.md). |
| **El contenido contiene cualquiera de estos tipos de información confidencial** | Se aplican a la Directiva cuando se incluyen o excluyen tipos de información confidencial en un mensaje. Algunos clasificadores están predefinidos en su espacio empresarial y los clasificadores personalizados se pueden configurar por separado o como parte del proceso de asignación de condición. Cada tipo de información confidencial que elija se aplica por separado y solo uno de estos tipos de información confidencial se debe aplicar para que la Directiva se aplique al mensaje. Para obtener más información acerca de los tipos personalizados de información confidencial, vea [tipos personalizados de información confidencial](custom-sensitive-info-types.md). |
| **Se recibe el mensaje desde cualquiera de estos dominios**  <br><br> **No se recibe el mensaje desde ninguno de estos dominios** | Aplicar la Directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes recibidos. Escriba cada dominio o dirección de correo electrónico y separe los distintos dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico que se escriba se aplica por separado, solo se debe solicitar un dominio o una dirección de correo electrónico para que la Directiva se aplique al mensaje. <br><br> Si desea analizar todo el correo electrónico de un dominio específico, pero desea excluir los mensajes que no necesitan revisión (boletines, anuncios, etc.), debe configurar un mensaje que **no se reciba de ninguna de estas** condiciones de dominio que excluya la dirección de correo electrónico (por ejemplo, "Newsletter@contoso.com"). |
| **El mensaje se envía a cualquiera de estos dominios**  <br><br> **El mensaje no se envía a ninguno de estos dominios** | Aplicar la Directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes enviados. Escriba cada dominio o dirección de correo electrónico y separe los distintos dominios o direcciones de correo electrónico con una coma. Cada dirección de correo electrónico o dominio se aplica por separado, solo se debe solicitar un dominio o una dirección de correo electrónico para que la Directiva se aplique al mensaje. <br><br> Si desea analizar todo el correo electrónico enviado a un dominio específico, pero quiere excluir los mensajes enviados que no necesitan revisión, debe configurar dos condiciones: <br> - **Se envía un mensaje a cualquiera de estas condiciones de los dominios** que define el dominio ("contoso.com") y <br> -Un **mensaje no se envía a ninguna condición de dominio** que excluya la dirección de correo electrónico ("subscriptions@contoso.com"). |
| **El mensaje se clasifica con cualquiera de estas etiquetas**  <br><br> **El mensaje no está clasificado con ninguna de estas etiquetas** | Para aplicar la Directiva cuando se incluyen o excluyen determinadas etiquetas de retención en un mensaje. Las etiquetas de retención se deben configurar por separado y las etiquetas configuradas se eligen como parte de esta condición. Cada etiqueta que elija se aplica por separado (solo una de estas etiquetas se debe aplicar para que la Directiva se aplique al mensaje). Para obtener más información acerca de la configuración de etiquetas de retención, consulte [Overview of Retention Labels](labels.md).|
| **El mensaje contiene alguna de estas palabras**  <br><br> **El mensaje no contiene ninguna de estas palabras** | Para aplicar la Directiva cuando se incluyan o excluyan ciertas palabras o frases en un mensaje, escriba cada palabra separada por una coma. Para las frases de dos palabras o más, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo se debe aplicar una palabra para que la Directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Los datos adjuntos contienen alguna de estas palabras**  <br><br> **Los datos adjuntos no contienen ninguna de estas palabras** | Para aplicar la Directiva cuando se incluyan o excluyan ciertas palabras o frases en un adjunto de mensaje (por ejemplo, un documento de Word), escriba cada palabra separada por una coma. Para las frases de dos palabras o más, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo se debe aplicar una palabra para que la Directiva se aplique a los datos adjuntos). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Los datos adjuntos son cualquiera de estos tipos de archivo**  <br><br> **Datos adjuntos no es ninguno de estos tipos de archivo** | Para supervisar las comunicaciones que incluyan o excluyan tipos de datos adjuntos específicos, escriba las extensiones de archivo (por ejemplo,. exe o. pdf). Si desea incluir o excluir varias extensiones de archivo, indíquela en líneas separadas. Para que se aplique la Directiva, solo debe coincidir una extensión de datos adjuntos.|
| **El tamaño del mensaje es mayor que**  <br><br> **El tamaño del mensaje no es mayor que** | Para revisar los mensajes según un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que se someta a revisión. Por ejemplo, si especifica que **el tamaño del mensaje es superior a** \> **1,0 MB**, todos los mensajes que tengan 1,01 MB o más, estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
| **El dato adjunto es mayor que**  <br><br> **Los datos adjuntos no tienen un tamaño superior a** | Para revisar los mensajes en función del tamaño de los datos adjuntos, especifique el tamaño máximo o mínimo que pueden tener los datos adjuntos antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. Por ejemplo, si especifica que el **dato adjunto es superior** a \> **2,0 MB**, todos los mensajes con datos adjuntos 2,01 MB y sobre estarán sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada palabra que escriba y separe con una coma se aplica por separado (solo se debe aplicar una palabra para que la condición de la Directiva se aplique al correo electrónico o los datos adjuntos). Por ejemplo, vamos a usar la condición, el **mensaje contiene cualquiera de estas palabras**, con las palabras clave "Banker", "Confidential" y "Insider comercia" separadas por una coma (Banker, Confidential, "transacciones de Insiders"). La Directiva se aplica a todos los mensajes que incluyan la palabra "Banker", "Confidential" o la frase "comercio Insider". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o del archivo adjunto deben coincidir exactamente con lo que se especifique.

>[!IMPORTANT]
>Al importar un archivo de diccionario personalizado, cada palabra o frase debe separarse con un retorno de carro y en una línea independiente. <br> Por ejemplo: <br><br>
>*Banco* <br>
>*confidencial* <br>
>*Comercio de Insiders*

Para analizar los mensajes de correo electrónico y los datos adjuntos de las mismas palabras clave, cree una [Directiva de prevención de pérdida de datos](create-test-tune-dlp-policy.md) con un diccionario de [palabras clave personalizado](create-a-keyword-dictionary.md) para los términos que desee analizar en los mensajes. Esta configuración de directiva identifica las palabras clave definidas que aparecen en el mensaje de correo electrónico **o** en los datos adjuntos del correo electrónico. El uso de la configuración de directivas condicionales estándar (el*mensaje contiene alguna de estas palabras* y *datos adjuntos contiene alguna de estas palabras*) para **identificar los términos** de los mensajes y en los datos adjuntos requiere que los términos estén presentes en el mensaje y los datos adjuntos.
  
#### <a name="enter-multiple-conditions"></a>Escribir varias condiciones

Si escribe varias condiciones, Microsoft 365 usa todas las condiciones de forma conjunta para determinar cuándo debe aplicarse la Directiva de cumplimiento de comunicaciones a los elementos de comunicación. Al configurar varias condiciones, se deben cumplir todas las condiciones para que se aplique la Directiva, a menos que se especifique una excepción. Por ejemplo, necesita una directiva que se aplique si un mensaje contiene la palabra "Trade" y su tamaño es superior a 2 MB. Sin embargo, si el mensaje también contiene las palabras "aprobado por contoso Financial", la Directiva no debe aplicarse. En este ejemplo, las tres condiciones se definirían de la siguiente manera:
  
- El **mensaje contiene cualquiera de estas palabras**, con las palabras clave "Trade"
- El **tamaño del mensaje es mayor que**, con el valor de 2 MB
- El **mensaje no contiene ninguna de estas palabras**, con las palabras clave "aprobado por el equipo financiero de Contoso"

### <a name="review-percentage"></a>Porcentaje de revisión

Si desea reducir la cantidad de contenido que se va a revisar, puede especificar un porcentaje de todas las comunicaciones regidas por una directiva de cumplimiento de la comunicación. Se selecciona un ejemplo aleatorio en tiempo real del contenido del porcentaje total de contenido que coincide con las condiciones de la directiva elegida. Si desea que los revisores revisen todos los elementos, puede configurar **100%** en una directiva de cumplimiento de la comunicación.

## <a name="notices"></a>Avisos

Puede crear plantillas de notificación si desea enviar a los usuarios una notificación de recordatorio de correo electrónico para las coincidencias de directivas como parte del proceso de resolución de problemas. Los avisos solo pueden enviarse a la dirección de correo electrónico del empleado asociada con la Directiva que generó la alerta específica para la corrección. Al seleccionar una plantilla de notificación para aplicar a una infracción de directiva como parte del flujo de trabajo de corrección, puede optar por aceptar los valores de campo definidos en la plantilla o sobrescribir los campos según sea necesario.

Las plantillas de notificaciones son plantillas de correo electrónico personalizadas donde puede definir los siguientes campos de mensaje:

|**Field**|**Required**| **Detalles** |
|:-----|:-----|:-----|
|**Nombre de la plantilla** | Sí | Nombre descriptivo de la plantilla de aviso que seleccionará en el flujo de trabajo Notify durante la corrección, admite caracteres de texto. |
| **Dirección del remitente** | Sí | La dirección de uno o más usuarios o grupos que envían el mensaje al empleado con una coincidencia de Directiva, seleccionada en Active Directory de la suscripción. |
| **Direcciones CC y CCO** | No | Que los usuarios o grupos opcionales reciban una notificación de la coincidencia de la Directiva, seleccionada en Active Directory de la suscripción. |
| **Asunto** | Sí | La información que aparece en la línea de asunto del mensaje admite caracteres de texto. |
| **Cuerpo del mensaje** | Sí | La información que aparece en el cuerpo del mensaje admite texto o valores HTML. |

### <a name="html-for-notices"></a>HTML para avisos

Si desea crear más de un mensaje de correo electrónico basado en texto sencillo para las notificaciones, puede crear un mensaje más detallado usando HTML en el campo cuerpo del mensaje de una plantilla de notificación. El siguiente ejemplo proporciona el formato del cuerpo del mensaje para una plantilla básica de notificación de correo electrónico basada en HTML:

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

>[!NOTE]
>La implementación de atributos de href HTML en las plantillas de notificación de cumplimiento de la comunicación solo admiten comillas simples, en lugar de comillas dobles para las referencias a direcciones URL.

## <a name="filters"></a>Filtros

Los filtros de cumplimiento de comunicaciones le permiten filtrar y ordenar los mensajes de alerta para obtener una investigación más rápida y acciones de corrección. El filtrado está disponible en las pestañas **pendientes** y **resueltas** para cada Directiva. Para guardar un filtro o un conjunto de filtros como una consulta de filtro guardada, se deben configurar uno o más valores como selecciones de filtro. En la tabla siguiente se describen los detalles del filtro:

|**Filter**|**Detalles**|
|:-----|:-----|
| **Fecha** | La fecha en la que un usuario de la organización envió o recibió el mensaje. |
| **Clase File** | La clase del mensaje en función del tipo de mensaje, ya sea *mensaje* o *datos adjuntos*. |
| **Tiene datos adjuntos** | La presencia de datos adjuntos en el mensaje. |
| **Clase Item** | El origen del mensaje en función del tipo de mensaje, el correo electrónico, Microsoft Team chat, Bloonmberg, etc. |
| **Dominios de destinatarios** | El dominio al que se envió el mensaje. Este dominio suele ser su dominio de suscripción de Microsoft 365 de forma predeterminada. |
| **Destinatario** | El usuario al que se envió el mensaje. |
| **Sender** | La persona que envió el mensaje. |
| **Dominio del remitente** | El dominio que envió el mensaje. |
| **Tamaño** | El tamaño del mensaje en KB. |
| **Asunto/título** | El asunto del mensaje o el título del chat. |
| **Tags** | Las etiquetas asignadas a un mensaje, ya sea *dudosa*, *compatible*o *no compatible*. |
| **Remitir a** | El nombre de usuario de la persona incluida como parte de una acción de elevación de mensajes. |
| **Clasificadores** | El nombre de los clasificadores integrados y personalizados que se aplican al mensaje. Algunos ejemplos son el *lenguaje ofensivo*, el *acoso dirigido*, la *blasfemia*, la *amenaza*y mucho más.

## <a name="alert-policies"></a>Directivas de alerta

Después de configurar una directiva, se crea automáticamente una directiva de alerta correspondiente y se generan alertas para los mensajes que coinciden con las condiciones definidas en la Directiva. De forma predeterminada, todas las directivas coinciden con los activadores de alertas a los que se asigna un nivel de gravedad medio en la Directiva de alerta asociada. Las alertas se generan para una directiva de cumplimiento de la comunicación una vez que se cumple el nivel umbral del desencadenador de agregación en la Directiva de alerta asociada.

Para las directivas de cumplimiento de la comunicación, los siguientes valores de la Directiva de alerta están configurados de forma predeterminada:

|**Desencadenador de la Directiva de alerta**|**Valor predeterminado**|
|:-----|:-----|
| Cronológica | Agregación sencilla |
| Umbral | 4 actividades |
| Window | de 60 minutos |

>[!Note]
>La configuración de desencadenadores de umbral de la Directiva de alerta para actividades admite un valor mínimo de 3 o superior para las directivas de cumplimiento de la comunicación.

Puede cambiar la configuración predeterminada de los desencadenadores en el número de actividades, el período de las actividades y los usuarios específicos de las directivas de alertas en la página **directivas de alertas** del centro de seguridad & cumplimiento.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Cambiar el nivel de gravedad de una directiva de alerta

Si desea cambiar el nivel de gravedad asignado en una directiva de alertas para una directiva de cumplimiento de comunicaciones específica, siga estos pasos:

1. Inicie sesión [https://compliance.microsoft.com](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el centro de cumplimiento de Microsoft 365, vaya a **directivas**.

3. Seleccione **office 365 Alert** en la página **directivas** para abrir la página **directivas de alertas** en el centro de **seguridad & cumplimiento de Office 365**.

4. Marque la casilla de verificación de la Directiva de cumplimiento de comunicaciones que quiera actualizar y, después, seleccione **Editar Directiva**.

5. En la ficha **Descripción** , seleccione la lista desplegable **gravedad** para configurar el nivel de alerta de la Directiva.

6. Seleccione **Guardar** para aplicar el nuevo nivel de gravedad a la Directiva.

7. Seleccione **cerrar** para salir de la página Detalles de la Directiva de alerta.

## <a name="audit"></a>Auditoría

En algunos casos, debe proporcionar información a los auditores reglamentarios o de cumplimiento para probar la supervisión de las comunicaciones y las actividades de los empleados. Esta información puede ser un resumen de todas las actividades asociadas con una directiva de organización definida o cada vez que cambia una directiva de cumplimiento de la comunicación. Las directivas de cumplimiento de comunicaciones tienen pistas de auditoría integradas para una preparación completa de las auditorías internas o externas. Los historiales de auditoría detallados de cada acción de creación, edición y eliminación son capturados por las directivas de comunicación para proporcionar una prueba de los procedimientos de supervisión.

>[!Important]
>La auditoría debe estar habilitada para su organización antes de que se registren los eventos de cumplimiento de comunicaciones. Para habilitar la auditoría, consulte [Habilitar el registro de auditoría](communication-compliance-configure.md#step-2-required-enable-the-audit-log).

Para ver las actividades de la Directiva de cumplimiento de comunicaciones, seleccione el control **exportar actividades de revisión** en la Página principal de cualquier directiva. Esta acción genera un archivo de auditoría en el formato. csv que contiene la siguiente información:

|**Field**|**Detalles**|
|:-----|:-----|
| **CreationDate** | Fecha en que se realizó la actividad en una directiva. |
| **UserIds** | El usuario que realizó la actividad en una directiva. |
| **Operations** | Las operaciones realizadas en la Directiva. |
| **AuditData** | Este campo es el origen de datos principal para todas las actividades de la Directiva. Todas las actividades se registran y se separan mediante delimitadores de coma. |

También puede ver actividades de auditoría en el registro de auditoría unificado o con el cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) PowerShell.

Por ejemplo, en el siguiente ejemplo, se devuelven las actividades de todas las actividades de revisión de supervisión (directivas y reglas):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

En este ejemplo se devuelven las actividades de actualización de las directivas de cumplimiento de comunicaciones:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>¿Está listo para empezar?

Para configurar el cumplimiento de comunicaciones para la organización de Microsoft 365, vea [Configure Communication Compliance for your microsoft 365 Organization](communication-compliance-configure.md).
