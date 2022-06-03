---
title: Directivas de Cumplimiento de comunicaciones
description: Obtenga más información sobre las directivas de cumplimiento de comunicaciones.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, cumplimiento de comunicaciones
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
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 44b177d0215acaa2e637aacda22db3eb16ee7168
ms.sourcegitcommit: 5fe7f2954a89406245416fc1a218cf4bf19abb85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65864526"
---
# <a name="communication-compliance-policies"></a>Directivas de Cumplimiento de comunicaciones

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

## <a name="policies"></a>Directivas

> [!IMPORTANT]
> No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas en la [solución de cumplimiento de comunicaciones](https://compliance.microsoft.com/supervisoryreview).

Puede crear directivas de cumplimiento de comunicaciones para organizaciones de Microsoft 365 en el portal de cumplimiento de Microsoft Purview. Las directivas de cumplimiento de comunicaciones definen qué comunicaciones y usuarios están sujetos a revisión en su organización, definen qué condiciones personalizadas deben cumplir las comunicaciones y especifican quién debe realizar revisiones. Los usuarios asignados al rol *de cumplimiento de comunicaciones Administración* pueden configurar directivas y cualquier persona que tenga asignado este rol puede acceder a la página **Cumplimiento de comunicaciones** y a la configuración global de la portal de cumplimiento Microsoft Purview. Si es necesario, puede exportar el historial de modificaciones a una directiva a un archivo .csv (valores separados por comas) que también incluya el estado de las alertas pendientes de revisión, elementos escalados y elementos resueltos. No se puede cambiar el nombre de las directivas y se pueden eliminar cuando ya no se necesiten.

## <a name="policy-templates"></a>Plantillas de directiva

Las plantillas de directiva son configuraciones de directiva predefinidas que puede usar para crear directivas rápidamente para abordar escenarios de cumplimiento comunes. Cada una de estas plantillas tiene diferencias en las condiciones y el ámbito, y todas las plantillas usan los mismos tipos de señales de examen. Puede elegir entre las siguientes plantillas de directiva:

|**Área**|**Plantilla de directiva**|**Detalles**|
|:-----|:-----|:-----|
| **Texto inadecuado** | Detección de texto inadecuado | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interno <br> - Porcentaje de revisión: 100% <br> - Condiciones: clasificadores de amenazas, discriminación y acoso dirigido |
| **Imágenes inapropiadas** | Detección de imágenes inapropiadas | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interno <br> - Porcentaje de revisión: 100% <br> - Condiciones: clasificadores de imágenes para adultos y racy |
| **Información confidencial** | Supervisión de información confidencial | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente, interno <br> - Porcentaje de revisión: 10 % <br> - Condiciones: información confidencial, patrones de contenido integrados y tipos, opción de diccionario personalizado, datos adjuntos de más de 1 MB |
| **Cumplimiento normativo** | Supervisión del cumplimiento normativo | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: entrante, saliente <br> - Porcentaje de revisión: 10 % <br> - Condiciones: opción de diccionario personalizado, datos adjuntos mayores que 1 MB |
| **Conflicto de intereses** | Supervisión de conflictos de interés | - Ubicaciones: Exchange Online, Microsoft Teams, Yammer, Skype Empresarial <br> - Dirección: Interno <br> - Porcentaje de revisión: 100% <br> - Condiciones: Ninguna |

Las comunicaciones se examinan cada 24 horas a partir del momento en que se crean las directivas. Por ejemplo, si crea una directiva de contenido inadecuado a las 11:00 a.m., la directiva recopilará señales de cumplimiento de comunicaciones cada 24 horas a las 11:00 a.m. todos los días. La edición de una directiva no cambia esta vez. Para ver la fecha y hora del último examen de una directiva, vaya a la columna *Último examen de directiva* de la página **Directiva** . Después de crear una nueva directiva, puede tardar hasta 24 horas en ver la primera fecha y hora del examen de directivas. La fecha y hora del último examen se convierten en la zona horaria del sistema local.

## <a name="pause-a-policy-preview"></a>Pausar una directiva (versión preliminar)

Después de crear una directiva de cumplimiento de comunicaciones, la directiva puede pausarse temporalmente si es necesario. Pausar una directiva puede usarse para probar o solucionar problemas de coincidencias de directivas, o para optimizar las condiciones de la directiva. En lugar de eliminar una directiva en estas circunstancias, pausar una directiva también conserva las alertas y los mensajes de directiva existentes para las investigaciones y revisiones en curso. Pausar una directiva impide la inspección y la generación de alertas para todas las condiciones de mensaje de usuario definidas en la directiva durante el tiempo en que se pausa la directiva. Para pausar o reiniciar una directiva, los usuarios deben ser miembros del grupo de roles *Cumplimiento de la comunicación Administración*.

Para pausar una directiva, vaya a la página **Directiva** , seleccione una directiva y, a continuación, seleccione **Pausar directiva** en la barra de herramientas de acciones. En el panel **Pausar directiva** , confirme que desea pausar la directiva; para ello, seleccione **Pausar**. En algunos casos, una directiva puede tardar hasta 24 horas en pausa. Una vez que la directiva está en pausa, no se crean alertas de mensajes que coincidan con la directiva. Sin embargo, los mensajes asociados a las alertas que se crearon antes de pausar la directiva siguen estando disponibles para su investigación, revisión y corrección.

El estado de la directiva de las directivas en pausa puede indicar varios estados:

- **Activo**: la directiva está activa
- **En pausa**: la directiva está totalmente en pausa.
- **Pausa:** la directiva está en proceso de pausa.
- **Reanudación**: directiva en proceso de reanudación.
- **Error al reanudar**: se ha encontrado un error al reanudar la directiva. Para el seguimiento de la pila de errores, mantenga el mouse sobre el error *al reanudar* el estado en la columna Estado de la página Directiva.
- **Error al pausar**: se ha encontrado un error al pausar la directiva. Para el seguimiento de la pila de errores, mantenga el mouse sobre el error *al pausar* el estado en la columna Estado de la página Directiva.

Para reanudar una directiva, vaya a la página **Directiva** , seleccione una directiva y, a continuación, seleccione **Reanudar directiva** en la barra de herramientas de acciones. En el panel **Reanudar directiva** , confirme que desea reanudar la directiva; para ello, seleccione **Reanudar**. En algunos casos, una directiva puede tardar hasta 24 horas en reanudarse. Una vez reanudada la directiva, se crearán alertas para los mensajes que coincidan con la directiva y estarán disponibles para la investigación, revisión y corrección.

## <a name="copy-a-policy-preview"></a>Copia de una directiva (versión preliminar)

En el caso de las organizaciones con directivas de cumplimiento de comunicaciones existentes, puede ser útil crear una nueva directiva a partir de una directiva existente. La copia de una directiva crea un duplicado exacto de una directiva existente, incluidos todos los usuarios dentro del ámbito, todos los revisores asignados y todas las condiciones de directiva. Algunos escenarios pueden incluir:

- **Límite de almacenamiento de directivas alcanzado**: las directivas de cumplimiento de comunicaciones activas tienen límites de almacenamiento de mensajes. Cuando se alcanza el límite de almacenamiento de una directiva, la directiva se desactiva automáticamente. Las organizaciones que necesitan seguir detectando, capturando y actuando en mensajes inadecuados cubiertos por la directiva desactivada pueden crear rápidamente una nueva directiva con una configuración idéntica.
- **Detectar y revisar mensajes inadecuados para diferentes grupos de usuarios**: es posible que algunas organizaciones prefieran crear varias directivas con la misma configuración, pero que incluyan diferentes usuarios dentro del ámbito y revisores diferentes para cada directiva.
- **Directivas similares con pequeños cambios**: en el caso de las directivas con configuraciones o condiciones complejas, puede ahorrar tiempo crear una nueva directiva a partir de una directiva similar.

Para copiar una directiva, los usuarios deben ser miembros de los grupos de roles *Cumplimiento de comunicaciones* o *Cumplimiento de comunicaciones Administración*. Después de crear una nueva directiva a partir de una directiva existente, puede tardar hasta 24 horas en ver los mensajes que coinciden con la nueva configuración de directiva.

Para copiar una directiva y crear una nueva, siga estos pasos:

1. Seleccione la directiva que desea copiar.
2. Seleccione **el botón Copiar** barra de comandos de la directiva en la barra de comandos o seleccione **Copiar directiva** en el menú de acciones de la directiva.
3. En el panel **Copiar directiva** , puede aceptar el nombre predeterminado de la directiva en el campo **Nombre de** directiva o cambiar el nombre de la directiva. El nombre de la directiva de la nueva directiva no puede ser el mismo que una directiva activa o desactivada existente. Complete el campo **Descripción** según sea necesario.
4. Si no necesita más personalización de la directiva, seleccione **Copiar directiva** para completar el proceso. Si necesita actualizar la configuración de la nueva directiva, seleccione **Personalizar directiva**. Esto inicia el Asistente para directivas para ayudarle a actualizar y personalizar la nueva directiva.

## <a name="user-reported-messages-policy"></a>Directiva de mensajes notificados por el usuario

>[!NOTE]
>Los mensajes notificados por el usuario comenzarán a estar disponibles para las organizaciones con licencia para [cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-configure#subscriptions-and-licensing) y Microsoft Teams a partir de mayo de 2022. Esta característica debe estar disponible para todas las organizaciones con licencia antes del 31 de agosto de 2022.

Como parte de una defensa por capas para detectar y corregir mensajes inadecuados en su organización, puede complementar las directivas de cumplimiento de comunicaciones con los mensajes notificados por el usuario en Microsoft Teams. Esta característica permite a los usuarios de su organización informar por sí solos de mensajes inadecuados, como acoso o amenazante, uso compartido de contenido para adultos y uso compartido de información confidencial o confidencial, para ayudar a fomentar un entorno de trabajo seguro y compatible.

Habilitada de forma predeterminada en el [centro de administración de Teams](/microsoftteams/manage-teams-in-modern-portal), la opción *Notificar una preocupación* en Teams mensajes permite a los usuarios de su organización enviar mensajes inadecuados para que los revisores de cumplimiento de comunicaciones revisen la directiva. Estos mensajes son compatibles con una directiva de sistema predeterminada que admite la generación de informes de mensajes en Teams canales, grupos y chats privados.

![Cumplimiento de comunicaciones Informe de un problema.](../media/communication-compliance-report-a-concern-full-menu.png)

Cuando un usuario envía un mensaje de chat de Teams para su revisión, el mensaje se copia en la directiva de mensajes notificados por el usuario. Los mensajes notificados inicialmente permanecen visibles para todos los miembros del chat y no hay ninguna notificación a los miembros del chat o al remitente de que se ha notificado un mensaje en chats de canal, privados o grupales. Un usuario no puede notificar el mismo mensaje más de una vez y el mensaje permanece visible para todos los usuarios incluidos en la sesión de chat durante el proceso de revisión de directivas. 

Durante el proceso de revisión, los revisores de cumplimiento de comunicaciones pueden realizar todas las acciones de corrección estándar en el mensaje, incluida la [eliminación](/microsoft-365/compliance/communication-compliance-investigate-remediate#step-3-decide-on-a-remediation-action) del mensaje del chat de Teams. En función de cómo se corrijan los mensajes, el remitente y los destinatarios del mensaje verán diferentes [mensajes de notificación](/microsoftteams/communication-compliance#act-on-inappropriate-messages-in-microsoft-teams) en Teams chats después de la revisión.

![Directiva de mensajes notificados por el usuario de cumplimiento de comunicaciones.](../media/communication-compliance-user-reported-messages-policy.png)

Los mensajes notificados por el usuario de Teams chats son los únicos mensajes procesados por la directiva de mensajes notificados por el usuario y solo se pueden modificar los revisores asignados para la directiva. Todas las demás propiedades de directiva no son editables. Cuando se crea la directiva, los revisores iniciales asignados a la directiva son todos miembros del grupo de roles *Administradores de cumplimiento de comunicaciones* (si se rellenan con al menos un usuario) o todos los miembros del grupo de roles *Global Administración* de la organización. El creador de directivas es un usuario seleccionado aleatoriamente del grupo de roles *Administradores de cumplimiento de comunicaciones* (si se rellena con al menos un usuario) o un usuario seleccionado aleatoriamente del grupo de roles *Global Administración* de la organización.  

Los administradores deben asignar inmediatamente revisores personalizados a esta directiva según corresponda para su organización. Esto puede incluir revisores como el oficial de cumplimiento, el responsable de riesgos o los miembros del departamento de recursos humanos. Para personalizar los revisores de los mensajes de chat enviados como mensajes notificados por el usuario, complete los pasos siguientes:

1. Inicie sesión en [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/) con las credenciales de una cuenta de administrador en su organización de Microsoft 365.
2. En el portal de cumplimiento, vaya a **Cumplimiento de comunicaciones**.
3. En la pestaña **Directiva** , seleccione la directiva *Mensajes notificados* por el usuario y seleccione **Editar**.
4. En el panel **Supervisión de mensajes notificados por el usuario** , asigne revisores para la directiva. Los revisores deben tener buzones hospedados en Exchange Online. Cuando los revisores se agregan a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.
5. Seleccione **Guardar**.

La opción *Notificar un problema* está habilitada de forma predeterminada y se puede controlar mediante Teams directivas de mensajería en el [Centro de Teams Administración](/microsoftteams/manage-teams-in-modern-portal). Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Edite la configuración de la directiva global o cree y asigne una o varias directivas personalizadas para activar o desactivar la opción *Notificar una preocupación* . Para más información, consulte [Administración de directivas de mensajería en Teams](/microsoftteams/messaging-policies-in-teams).  

>[!IMPORTANT]
>Si usa PowerShell para activar o desactivar la opción **Informes de usuario final** en el Centro de Teams Administración, debe usar [Microsoft Teams módulo cmdlets versión 4.2.0](/MicrosoftTeams/teams-powershell-release-notes) o posterior.

## <a name="storage-limit-notification-preview"></a>Storage notificación de límite (versión preliminar)

Cada directiva de cumplimiento de comunicaciones tiene un tamaño de límite de almacenamiento de 100 GB o 1 millón de mensajes, lo que se alcance primero. A medida que la directiva se acerca a estos límites, los correos electrónicos de notificación se envían automáticamente a los usuarios asignados a los grupos de roles *De cumplimiento de comunicaciones* o *cumplimiento de comunicaciones Administración*. Los mensajes de notificaciones se envían cuando el tamaño de almacenamiento o el recuento de mensajes alcanzan el 80, el 90 y el 95 por ciento del límite. Cuando se alcanza el límite de directivas, la directiva se desactiva automáticamente y la directiva deja de procesar mensajes para las alertas.

>[!IMPORTANT]
>Si se desactiva una directiva debido a que se alcanzan los límites de almacenamiento y mensajes, asegúrese de evaluar cómo administrar la directiva desactivada. Si elimina la directiva, todos los mensajes, los datos adjuntos asociados y las alertas de mensajes se eliminarán permanentemente. Si necesita mantener estos elementos para su uso futuro, no elimine la directiva desactivada.

Para administrar directivas que se acercan a los límites de almacenamiento y mensajes, considere la posibilidad de realizar una copia de la directiva para mantener la continuidad de la cobertura o realizar las siguientes acciones para ayudar a minimizar el tamaño de almacenamiento de directivas y los recuentos de mensajes actuales:

- Considere la posibilidad de reducir el número de usuarios asignados a la directiva. Quitar usuarios de la directiva o crear directivas diferentes para distintos grupos de usuarios puede ayudar a ralentizar el crecimiento del tamaño de la directiva y del total de mensajes.
- Examine la directiva en busca de alertas excesivas de falsos positivos. Considere la posibilidad de agregar excepciones o cambios a las condiciones de directiva para pasar por alto las alertas comunes de falsos positivos.
- Si una directiva ha alcanzado los límites de almacenamiento o mensaje y se ha desactivado, realice una copia de la directiva para seguir detectando y realizando acciones para las mismas condiciones y usuarios.

## <a name="policy-settings"></a>Configuración de la directiva

### <a name="users"></a>Usuarios

Puede elegir seleccionar **Todos los usuarios** o definir usuarios específicos en una directiva de cumplimiento de comunicaciones. Al seleccionar **Todos los usuarios**, se aplica la directiva a todos los usuarios y a todos los grupos en los que se incluya cualquier usuario como miembro. Al definir usuarios específicos, la directiva se aplica a los usuarios definidos y a todos los grupos en los que los usuarios definidos se incluyan como miembro.

### <a name="direction"></a>Dirección

De forma predeterminada, se muestra la condición **Direction is (Dirección)** y no se puede quitar. La configuración de la dirección de comunicación de una directiva se elige de forma individual o conjunta:

- **Entrante**: detecta las comunicaciones enviadas **a** los usuarios supervisados desde remitentes externos e internos, incluidos otros usuarios supervisados de la directiva.
- **Saliente**: detecta las comunicaciones enviadas **desde** usuarios supervisados a destinatarios externos e internos, incluidos otros usuarios supervisados de la directiva.
- **Interno**: detecta las comunicaciones **entre** los usuarios o grupos supervisados de la directiva.

### <a name="sensitive-information-types"></a>Tipos de información confidencial

Tiene la opción de incluir tipos de información confidencial como parte de la directiva de cumplimiento de comunicaciones. Los tipos de información confidencial son tipos de datos predefinidos o personalizados que pueden ayudar a identificar y proteger los números de tarjeta de crédito, los números de cuenta bancaria, los números de pasaporte y mucho más. Como parte de [Learn about Prevención de pérdida de datos de Microsoft Purview](dlp-learn-about-dlp.md), la configuración de información confidencial puede usar patrones, proximidad de caracteres, niveles de confianza e incluso tipos de datos personalizados para ayudar a identificar y marcar el contenido que puede ser confidencial. Los tipos de información confidencial predeterminados son:

- Financiera
- Medicina y salud
- Privacidad
- Tipo de información personalizada

> [!IMPORTANT]
> Los SIT tienen dos formas diferentes de definir los parámetros de recuento de instancias únicos máximos. Para obtener más información, consulte [Valores admitidos de recuento de instancias para SIT](create-a-custom-sensitive-information-type.md#instance-count-supported-values-for-sit).

Para obtener más información sobre los detalles de información confidencial y los patrones incluidos en los tipos [predeterminados, consulte Definiciones de entidades de tipo de información confidencial](sensitive-information-type-entity-definitions.md).

### <a name="custom-keyword-dictionaries"></a>Diccionarios de palabras clave personalizadas

Configure diccionarios de palabras clave personalizadas (o léxicos) para proporcionar una administración sencilla de palabras clave específicas de su organización o sector. Los diccionarios de palabras clave admiten hasta 100 KB de términos (después de la compresión) en el diccionario y admiten cualquier idioma. El límite de inquilino también es de 100 KB después de la compresión. Si es necesario, puede aplicar varios diccionarios de palabras clave personalizadas a una sola directiva o tener un único diccionario de palabras clave por directiva. Estos diccionarios se asignan en una directiva de cumplimiento de comunicaciones y se pueden obtener de un archivo (como un .csv o una lista de .txt) o de una lista que puede [importar en el Centro de cumplimiento](create-a-keyword-dictionary.md). Use diccionarios personalizados cuando necesite admitir términos o idiomas específicos de su organización y directivas.

### <a name="classifiers"></a>Clasificadores

[Los clasificadores integrados y globales](/microsoft-365/compliance/classifier-learn-about) examinan los mensajes enviados o recibidos en todos los canales de comunicación de la organización para detectar diferentes tipos de problemas de cumplimiento. Los clasificadores usan una combinación de inteligencia artificial y de palabras clave para identificar lenguaje en los mensajes que es probable que infrinja las directivas contra el acoso. Los clasificadores integrados admiten actualmente la identificación de palabras clave del mensaje en varios idiomas:

- Árabe
- Chino (simplificado)
- Chino (tradicional)
- Neerlandés
- Inglés
- Francés
- Alemán
- Italiano
- Coreano
- Japonés
- Portugués
- Español

Los clasificadores globales y entrenables integrados de cumplimiento de comunicaciones examinan las comunicaciones en busca de términos, imágenes y opiniones para los siguientes tipos de lenguaje y contenido:

- **Imágenes para adultos**: busca imágenes que sean sexualmente explícitas en la naturaleza.
- **Quejas de clientes**: examina los comentarios y las quejas realizadas sobre los productos o servicios de su organización.
- **Discriminación**: busca un lenguaje discriminatorio explícito y es particularmente sensible al lenguaje discriminatorio contra las comunidades afroamericanas y negras en comparación con otras comunidades.
- **Imágenes de Gory**: busca imágenes que represente la violencia y el gore.
- **Acoso**: busca conductas ofensivas dirigidas a personas relacionadas con la raza, el color, la religión, el origen nacional.
- **Blasfemia**: busca expresiones soeces que avergüencen a la mayoría de las personas.
- **Imágenes de Racy**: busca imágenes que son sexualmente sugerentes en la naturaleza, pero que contienen contenido menos explícito que las imágenes que se consideran adultos.
- **Amenaza**: busca amenazas para cometer violencia o daños físicos a una persona o propiedad.

Los clasificadores de imágenes *Adult*, *Racy* y *Gory* examinan los archivos en formatos .jpeg, .png, .gif y .bmp. El tamaño de los archivos de imagen debe ser inferior a 4 megabytes (MB) y las dimensiones de las imágenes deben ser mayores que 50x50 píxeles y mayores que 50 kilobytes (KB) para que la imagen pueda calificar para la evaluación. La identificación de imágenes se admite para Exchange Online mensajes de correo electrónico y canales de Microsoft Teams y chats.

Los clasificadores integrados y globales que se pueden entrenar no proporcionan una lista exhaustiva de términos o imágenes en estas áreas. Además, los estándares lingüísticos y culturales cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar clasificadores a su discreción. Aunque los clasificadores pueden ayudar a su organización a supervisar estas áreas, los clasificadores no están diseñados para proporcionar el único medio de su organización de supervisar o abordar dicho lenguaje o imágenes. Su organización, no Microsoft, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, el examen y el bloqueo del lenguaje y las imágenes en estas áreas, incluido el cumplimiento de la privacidad local y otras leyes aplicables. Microsoft anima a consultar con el asesor legal antes de la implementación y el uso.

> [!NOTE]
> Las directivas que usan clasificadores inspeccionarán y evaluarán los mensajes con un recuento de palabras de seis o más. Los mensajes que contienen menos de seis palabras no se evalúan en las directivas mediante clasificadores. Para identificar y tomar medidas en los mensajes más cortos que contienen contenido inadecuado, se recomienda incluir un diccionario de palabras clave personalizado para la supervisión de directivas de cumplimiento de comunicaciones para este tipo de contenido.

### <a name="optical-character-recognition-ocr"></a>Reconocimiento óptico de caracteres (OCR)

Configure directivas de cumplimiento de comunicaciones integradas o personalizadas para examinar e identificar texto impreso o manuscrito a partir de imágenes que pueden ser inapropiadas en su organización. La compatibilidad integrada con [Azure Cognitive Services y el examen óptico](/azure/cognitive-services/computer-vision/overview-ocr) para identificar texto en las imágenes ayudan a los analistas e investigadores a detectar y actuar en instancias en las que se puede perder una conducta inapropiada en las comunicaciones que principalmente no son textuales.

Puede habilitar el reconocimiento óptico de caracteres (OCR) en nuevas directivas a partir de plantillas, directivas personalizadas o actualizar directivas existentes para expandir la compatibilidad con el procesamiento de imágenes incrustadas y datos adjuntos. Cuando se habilita en una directiva creada a partir de una plantilla de directiva, el examen automático se admite para imágenes insertadas o adjuntas en el correo electrónico y Microsoft Teams mensajes de chat. En el caso de las imágenes incrustadas en archivos de documento, no se admite el examen OCR. En el caso de las directivas personalizadas, se debe configurar una o varias opciones condicionales asociadas a palabras clave, clasificadores integrados o tipos de información confidencial en la directiva para habilitar la selección del examen OCR.

Las imágenes de 50 KB a 4 MB en los siguientes formatos de imagen se examinan y procesan:

- .jpg/.jpeg (grupo conjunto de expertos fotográficos)
- .png (gráficos de red portátiles)
- .bmp (mapa de bits)
- .tiff (formato de archivo de imagen de etiqueta)
- .pdf (formato de documento portátil)

> [!NOTE]
> Actualmente, el examen y la extracción de imágenes .pdf insertadas y adjuntas solo se admiten para mensajes de correo electrónico.

Al revisar las alertas pendientes de las directivas con OCR habilitado, las imágenes identificadas y coincidentes con las condiciones de directiva se muestran como elementos secundarios para las alertas asociadas. Puede ver la imagen original para evaluar el texto identificado en contexto con el mensaje original. Las imágenes detectadas pueden tardar hasta 48 horas en estar disponibles con alertas.

### <a name="conditional-settings"></a>Configuración condicional
<a name="ConditionalSettings"> </a>

Las condiciones que elija para la directiva se aplican a las comunicaciones desde el correo electrónico y los orígenes de terceros de su organización (por ejemplo, desde Instant Bloomberg).

En la tabla siguiente se explica más sobre cada condición.

|**Condition**|**Cómo usar esta condición**|
|:-----|:-----|
| **El contenido coincide con cualquiera de estos clasificadores** | Se aplica a la directiva cuando se incluyen o excluyen los clasificadores en un mensaje. Algunos clasificadores están predefinidos en el inquilino y los clasificadores personalizados deben configurarse por separado antes de que estén disponibles para esta condición. Solo se puede definir un clasificador como condición en una directiva. Para obtener más información sobre la configuración de clasificadores, consulte [Más información sobre los clasificadores entrenables (versión preliminar).](classifier-learn-about.md) |
| **El contenido contiene cualquiera de estos tipos de información confidencial** | Se aplica a la directiva cuando se incluyen o excluyen los tipos de información confidencial en un mensaje. Algunos clasificadores se definen previamente en el inquilino y los clasificadores personalizados se pueden configurar por separado o como parte del proceso de asignación de condición. Cada tipo de información confidencial que elija se aplica por separado y solo se debe aplicar uno de estos tipos de información confidencial para que la directiva se aplique al mensaje. Para obtener más información sobre los tipos de información confidencial personalizados, consulte [Información sobre los tipos de información confidencial](sensitive-information-type-learn-about.md). |
| **El mensaje se recibe de cualquiera de estos dominios**  <br><br> **El mensaje no se recibe de ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios o direcciones de correo electrónico específicos en los mensajes recibidos. Escriba cada dominio o dirección de correo electrónico y separe varios dominios o direcciones de correo electrónico con una coma. Cada dominio o dirección de correo electrónico especificado se aplica por separado, solo se debe aplicar una dirección de dominio o correo electrónico para que la directiva se aplique al mensaje. <br><br> Si desea examinar todo el correo electrónico de un dominio específico, pero desea excluir los mensajes que no necesitan revisión (boletines, anuncios, etc.), debe configurar que **no se reciba un mensaje de ninguna de estas condición de dominios** que excluya la dirección de correo electrónico (por ejemplo, "newsletter@contoso.com"). |
| **El mensaje se envía a cualquiera de estos dominios**  <br><br> **El mensaje no se envía a ninguno de estos dominios** | Aplique la directiva para incluir o excluir dominios específicos en los mensajes enviados. Escriba cada dominio y separe varios dominios con una coma. Cada dominio se aplica por separado, solo se debe aplicar un dominio para que la directiva se aplique al mensaje. <br><br> Si desea excluir todos los correos electrónicos enviados a dos dominios específicos, configurará que el **mensaje no se envíe a ninguna de estas condición de dominios** con los dos dominios (por ejemplo, "contoso.com,wingtiptoys.com"). |
| **El mensaje se clasifica con cualquiera de estas etiquetas**  <br><br> **El mensaje no se clasifica con ninguna de estas etiquetas** | Para aplicar la directiva cuando se incluyen o excluyen determinadas etiquetas de retención en un mensaje. Las etiquetas de retención deben configurarse por separado y las etiquetas configuradas se eligen como parte de esta condición. Cada etiqueta que elija se aplica por separado (solo se debe aplicar una de estas etiquetas para que la directiva se aplique al mensaje). Para obtener más información sobre las etiquetas de retención, consulte [Información sobre las directivas de retención y las etiquetas de retención](retention.md).|
| **El mensaje contiene cualquiera de estas palabras**  <br><br> **El mensaje no contiene ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en un mensaje, escriba cada palabra separada por una coma. Para frases de dos palabras o más, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo se debe aplicar una palabra para que la directiva se aplique al mensaje). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-policies.md#Matchwords).|
| **Los datos adjuntos contienen cualquiera de estas palabras**  <br><br> **Los datos adjuntos no contienen ninguna de estas palabras** | Para aplicar la directiva cuando se incluyan o excluyan determinadas palabras o frases en los datos adjuntos de un mensaje (por ejemplo, un documento de Word), escriba cada palabra separada por una coma. Para frases de dos palabras o más, use comillas alrededor de la frase. Cada palabra o frase que escriba se aplica por separado (solo se debe aplicar una palabra para que la directiva se aplique a los datos adjuntos). Para obtener más información sobre cómo escribir palabras o frases, consulte la sección siguiente [Matching words and phrases to emails or attachments](communication-compliance-policies.md#Matchwords).|
| **Los datos adjuntos son cualquiera de estos tipos de archivo.**  <br><br> **Los datos adjuntos no son ninguno de estos tipos de archivo.** | Para supervisar las comunicaciones que incluyen o excluyen tipos específicos de datos adjuntos, escriba las extensiones de archivo (como .exe o .pdf). Si desea incluir o excluir varias extensiones de archivo, escriba tipos de archivo separados por una coma (por ejemplo *,.exe,.pdf,.zip*). Solo debe coincidir una extensión de datos adjuntos para que se aplique la directiva.|
| **El tamaño del mensaje es mayor que**  <br><br> **El tamaño del mensaje no es mayor que** | Para revisar los mensajes en función de un tamaño determinado, use estas condiciones para especificar el tamaño máximo o mínimo que puede tener un mensaje antes de que esté sujeto a revisión. Por ejemplo, si especifica que **el tamaño del mensaje es mayor que** \> **1,0 MB**, todos los mensajes de 1,01 MB y más grandes están sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|
| **Los datos adjuntos son mayores que**  <br><br> **Los datos adjuntos no son mayores que** | Para revisar los mensajes en función del tamaño de sus datos adjuntos, especifique el tamaño máximo o mínimo que pueden tener los datos adjuntos antes de que el mensaje y sus datos adjuntos estén sujetos a revisión. Por ejemplo, si especifica **Datos adjuntos de más de** \> **2,0 MB**, todos los mensajes con datos adjuntos de 2,01 MB o más están sujetos a revisión. Puede elegir bytes, kilobytes, megabytes o gigabytes para esta condición.|

#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Coincidencia de palabras y frases para mensajes de correo electrónico o datos adjuntos
<a name="Matchwords"> </a>

Cada palabra que escriba y separe con una coma se aplica por separado (solo se debe aplicar una palabra para que la condición de directiva se aplique al correo electrónico o a los datos adjuntos). Por ejemplo, vamos a usar la condición, **Message contiene cualquiera de estas palabras**, con las palabras clave "banker", "confidential" y "insider trading" separadas por una coma (banker, confidential, "insider trading"). La política se aplica a cualquier mensaje que incluya la palabra "banker", "confidential" o la frase "insider trading". Solo una de estas palabras o frases debe aparecer para que esta condición de directiva se aplique. Las palabras del mensaje o los datos adjuntos deben coincidir exactamente con lo que escriba.

> [!IMPORTANT]
>
> Al importar un archivo de diccionario personalizado, cada palabra o frase debe separarse con un retorno de carro y en una línea independiente. Por ejemplo:
>
> *Banquero* <br>
> *Confidencial* <br>
> *trading de insider*

Para examinar los mensajes de correo electrónico y los datos adjuntos en busca de las mismas palabras clave, cree un [diccionario de palabras clave personalizado](create-a-keyword-dictionary.md) para los términos que desea examinar en los mensajes. Esta configuración de directiva identifica palabras clave definidas que aparecen en el mensaje de correo electrónico **O** en los datos adjuntos del correo electrónico. El uso de la configuración de directiva condicional estándar (*Message contiene cualquiera de estas palabras* y *Attachment contiene cualquiera de estas palabras*) para identificar términos en los mensajes y en los datos adjuntos requiere que los términos estén presentes tanto en el mensaje **como** en los datos adjuntos.

#### <a name="enter-multiple-conditions"></a>Especificar varias condiciones

Si especifica varias condiciones, Microsoft 365 usa todas las condiciones juntas para determinar cuándo aplicar la directiva de cumplimiento de comunicaciones a los elementos de comunicación. Al configurar varias condiciones, se deben cumplir todas las condiciones para que se aplique la directiva, a menos que escriba una excepción. Por ejemplo, necesita una directiva que se aplique si un mensaje contiene la palabra "trade" y es mayor que 2 MB. Sin embargo, si el mensaje también contiene las palabras "Aprobado por Contoso financial", la directiva no debe aplicarse. En este ejemplo, las tres condiciones se definirían de la siguiente manera:

- **El mensaje contiene cualquiera de estas palabras**, con la palabra clave "trade"
- **El tamaño del mensaje es mayor que**, con el valor 2 MB
- **El mensaje no contiene ninguna de estas palabras**, con las palabras clave "Aprobado por el equipo financiero de Contoso".

### <a name="review-percentage"></a>Porcentaje de revisión

Si desea reducir la cantidad de contenido que se va a revisar, puede especificar un porcentaje de todas las comunicaciones que se rigen por una directiva de cumplimiento de comunicaciones. Se selecciona una muestra de contenido aleatoria en tiempo real del porcentaje total de contenido que coincida con las condiciones de directiva elegidas. Si quiere que los revisores revisen todos los elementos, puede configurar el **100 %** en una directiva de cumplimiento de comunicaciones.

## <a name="alert-policies"></a>Directivas de alerta

Después de configurar una directiva, se crea automáticamente una directiva de alerta correspondiente y se generan alertas para los mensajes que coinciden con las condiciones definidas en la directiva. La creación de una directiva puede tardar hasta 24 horas en recibir alertas de indicadores de actividad. De forma predeterminada, a todas las directivas que coincidan con los desencadenadores de alerta se les asigna un nivel de gravedad medio en la directiva de alertas asociada. Las alertas se generan para una directiva de cumplimiento de comunicaciones una vez que se cumple el nivel de umbral del desencadenador de agregación en la directiva de alertas asociada. Una única notificación por correo electrónico se envía una vez cada 24 horas para las alertas, independientemente del número de mensajes individuales que coincidan con las condiciones de la directiva. Por ejemplo, Contoso tiene habilitada una directiva de contenido inadecuado y, para el 1 de enero, había 100 coincidencias de directivas que generaron seis alertas. A finales del 1 de enero se envía una única notificación por correo electrónico para las seis alertas.

En el caso de las directivas de cumplimiento de comunicaciones, los siguientes valores de directiva de alerta se configuran de forma predeterminada:

|**Desencadenador de directiva de alertas**|**Valor predeterminado**|
|:-----|:-----|
| Agregación | Agregación simple |
| Umbral | Valor predeterminado: 4 actividades <br> Mínimo: 3 actividades <br> Máximo: 2.147.483.647 actividades |
| Window | Valor predeterminado: 60 minutos <br> Mínimo: 60 minutos <br> Máximo: 10 000 minutos |

> [!NOTE]
> La configuración del desencadenador de umbral de directiva de alerta para las actividades admite un valor mínimo de 3 o superior para las directivas de cumplimiento de comunicaciones.

Puede cambiar la configuración predeterminada de los desencadenadores en el número de actividades, el período de las actividades y para usuarios específicos de las directivas de alertas en la página **Directivas de alerta** del portal de cumplimiento Microsoft Purview.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Cambio del nivel de gravedad de una directiva de alerta

Si desea cambiar el nivel de gravedad asignado en una directiva de alertas para una directiva de cumplimiento de comunicaciones específica, siga estos pasos:

1. Inicie sesión en [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en su organización de Microsoft 365.

2. En el portal de cumplimiento Microsoft Purview, vaya a **Directivas**.

3. Seleccione **Office 365 alerta** en la página **Directivas** para abrir la página **Directivas de alertas**.

4. Active la casilla de la directiva de cumplimiento de comunicaciones que desea actualizar y, a continuación, seleccione **Editar directiva**.

5. En la pestaña **Descripción** , seleccione la lista desplegable **Gravedad** para configurar el nivel de alerta de directiva.

6. Seleccione **Guardar** para aplicar el nuevo nivel de gravedad a la directiva.

7. Seleccione **Cerrar** para salir de la página de detalles de la directiva de alertas.
