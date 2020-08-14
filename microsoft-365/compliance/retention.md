---
title: Obtenga información sobre directivas y etiquetas de retención para retener o eliminar automáticamente el contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre directivas y etiquetas de retención que le ayudarán a conservar lo que necesita y eliminar el contenido innecesario.
ms.openlocfilehash: ff99e61c82f0427d79d8aca99acc82a338f79b8a
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649157"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a>Más información sobre directivas y etiquetas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Para la mayoría de las organizaciones, el volumen y la complejidad de los datos se incrementa diariamente: correo electrónico, documentos, mensajes instantáneos y mucho más. Administrar o gobernar esta información es importante, ya que necesita:
  
- **Cumplir de forma proactiva con las normas del sector y las directivas internas** que le exigen retener contenido durante un período mínimo de tiempo. Por ejemplo, la ley Sarbanes-Oxley puede exigirle que retenga determinados tipos de contenido durante siete años. 
- **Reducir el riesgo en caso de litigio o una infracción de seguridad** al eliminar de forma permanente contenido antiguo que ya no es necesario mantener. 
    
- **Ayudar a su organización a compartir los conocimientos de manera eficaz y ser más ágil** al asegurarse de que los usuarios trabajan solo con contenido actualizado y relevante para ellos. 
    
Las opciones de retención que configure pueden ayudarle a lograr todos estos objetivos. Por lo general, administrar el contenido requiere dos acciones:
  
- **Conservar** contenido para que no pueda eliminarse de forma permanente antes del fin del período de retención. 
    
- **Eliminar** contenido de forma permanente al final del período de retención. 
    

Con estas dos acciones de retención, puede establecer la configuración de retención para los siguientes resultados:

- Solo conservar: conserve el contenido para siempre o durante un determinado período de tiempo.
- Solo eliminar: elimine el contenido al cabo de un determinado período de tiempo.
- Conservar y, después, eliminar el contenido: conserve el contenido durante un determinado período de tiempo y, a continuación, elimínelo.

Esta configuración de retención funciona con contenido local y le ahorra los costes generales adicionales de crear y configurar almacenamiento añadido cuando necesita conservar contenido por motivos de cumplimiento. Además, no es necesario implementar procesos personalizados para copiar y sincronizar estos datos.

## <a name="how-retention-settings-work-with-content-in-place"></a>Cómo funciona la configuración de retención con el contenido local

Cuando se establece la configuración de retención, el contenido permanece en su ubicación original. Los usuarios pueden seguir trabajando con sus documentos o buzones como si nada hubiera cambiado. Sin embargo, si modifican o eliminan contenido que esté incluido en la directiva de retención, se retendrá automáticamente una copia del contenido tal como era cuando se aplicó la configuración de retención.
  
- Para sitios de SharePoint y OneDrive: la copia se conserva en la biblioteca de **Suspensión para conservación**.

- Para buzones de Exchange: la copia se conserva en la carpeta **Elementos recuperables**. 

- Para mensajes de chat y canales de Teams: la copia se conserva en una carpeta oculta dentro de la carpeta **Elementos recuperables** de Exchange.

> [!NOTE]
> La biblioteca de Suspensión para conservación consume almacenamiento que no está exento de la cuota de almacenamiento de un sitio. Es posible que tenga que aumentar el almacenamiento al usar la configuración de retención para los grupos de Microsoft 365 y SharePoint.
> 
Ni estas ubicaciones seguras ni el contenido retenido son visibles para la mayoría de los usuarios. En la mayoría de los casos, ni siquiera es necesario que los usuarios sepan que su contenido está sujeto a la configuración de retención.

Para obtener información más detallada sobre cómo funciona la configuración de retención con distintas cargas de trabajo, consulte los artículos siguientes:

- [Más información sobre las directivas de retención de SharePoint y OneDrive](retention-policies-sharepoint.md)
- [Más información sobre las directivas de retención para Microsoft Teams](retention-policies-teams.md)
- [Más información sobre las directivas de retención de Exchange](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a>Directivas de retención y etiquetas de retención

Puede usar tanto las directivas de retención como las etiquetas de retención para asignar la configuración de retención al contenido. 

Use una directiva de retención para asignar la misma configuración de retención al contenido en el nivel de sitio o buzón y use una etiqueta de retención para asignar la configuración de retención en el nivel de elemento (carpeta, documento o correo electrónico).

Por ejemplo, si es necesario conservar todos los documentos de un sitio de SharePoint durante cinco años, es más eficaz usar una directiva de retención que aplicar la misma etiqueta de retención a todos los documentos del sitio. Sin embargo, si algunos documentos del sitio se deben conservar durante cinco años y otros durante 10 años, no es posible hacerlo con una directiva de retención. Cuando tenga que especificar la configuración de retención en el nivel de elemento, use etiquetas de retención. 

A diferencia de las directivas de retención, la configuración de retención de las etiquetas de retención se mantiene con el contenido si se copia o se mueve a una ubicación diferente de Microsoft 365. Además, las etiquetas de retención tienen las siguientes funcionalidades que no son compatibles con las directivas de retención: 
 
- Opciones para iniciar el período de retención desde el momento en que se etiquetó el contenido o en función de un evento, en lugar de la antigüedad del contenido o cuando se modificó por última vez.

- Uso de [clasificadores que se pueden entrenar](classifier-getting-started-with.md) para identificar el contenido que se va a etiquetar.

- Aplicación de una etiqueta predeterminada a los documentos de SharePoint.

- Soporte de [revisión para eliminación](disposition-reviews.md)  para revisar el contenido antes de que se elimine de forma permanente.

- Marcado del contenido como un [registro](records.md) como parte de la configuración de la etiqueta para disponer siempre de una  [prueba de eliminación](disposition.md#disposition-of-records) cuando el contenido se elimine al final de su período de retención.

### <a name="retention-policies"></a>Directivas de retención

Las directivas de retención se pueden aplicar a las siguientes ubicaciones:
- Correo electrónico de Exchange
- Sitio de SharePoint
- Cuentas de OneDrive
- Grupos de Microsoft 365
- Skype Empresarial
- Carpetas públicas de Exchange
- Mensajes de canal de Teams
- Chats de Teams

Puede aplicar una sola directiva en varias ubicaciones, o bien en determinadas ubicaciones o usuarios.
    
También puede aplicar una directiva a todo el contenido o solo cuando cumpla ciertas condiciones, como contener palabras clave o [tipos de información confidencial](sensitive-information-type-entity-definitions.md).

#### <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>Usar el bloqueo de conservación para cumplir los requisitos normativos

Algunas organizaciones podrían tener que cumplir con las reglas que definen los organismos reguladores, como la regla 17a-4 de la SEC (Comisión de intercambio y valores), lo que requiere que, después de activar una directiva de retención, esta no se pueda desactivar ni hacer menos restrictiva. 

El bloqueo de conservación garantiza que su organización cumpla con los requisitos normativos, ya que bloquea una directiva de retención de forma que nadie, incluido el administrador, pueda desactivar la directiva, eliminar la directiva o hacer que sea menos restrictiva.
  
Cuando una directiva de retención está bloqueada:

- Nadie puede desactivarla
- Las ubicaciones se pueden agregar pero no quitar
- El contenido sujeto a la directiva no se puede modificar ni eliminar durante el período de retención.
- Puede ampliar un período de retención, pero no disminuirlo

En resumen, una directiva de retención bloqueada se puede incrementar o ampliar, pero no se puede reducir ni desactivar.
  
> [!IMPORTANT]
> Antes de bloquear una directiva de retención, es importante que comprenda el impacto y confirme si es necesario para que la organización cumpla con los requisitos normativos. Los administradores no podrán deshabilitar ni eliminar una directiva de retención cuando se haya aplicado el bloqueo de conservación.

Usted aplica un Bloqueo de conservación después de crear la directiva de retención usando PowerShell. Las instrucciones se incluyen en [Crear y configurar las directivas de retención](create-retention-policies.md).

#### <a name="releasing-a-retention-policy"></a>Publicar una directiva de retención

El uso de la directiva de retención no tiene un bloqueo de conservación, puede desactivar o eliminar una directiva de retención en cualquier momento. 

Al hacerlo, el contenido de SharePoint o de OneDrive que se retiene en la biblioteca de conservación de documentos se elimina de forma inmediata y permanente. A partir de ahora, y para evitar pérdidas accidentales de datos, existe un período de gracia de 30 días durante el cual la expiración del contenido para esa directiva no se produce en la biblioteca de conservación de documentos, de modo que puede restaurar desde allí el contenido si lo ve necesario. Además, no puede eliminar manualmente este contenido durante el período de gracia.

Puede activar la directiva de retención durante el período de gracia y no se eliminará ningún contenido para esa directiva.

Este periodo de gracia de 30 días en SharePoint y OneDrive corresponde a la retención de retraso de 30 días de Exchange. Para obtener más información, consulte [Gestionar buzón con una retención de retraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

### <a name="retention-labels"></a>Etiquetas de retención

Use las etiquetas de retención para diferentes tipos de contenido que requieran una configuración de retención diferente. Por ejemplo:
  
- Formularios fiscales que deben conservarse durante un período mínimo de tiempo. 
    
- Materiales de prensa que deben eliminarse de forma permanente cuando alcanzan una antigüedad específica. 
    
- Información sobre la competencia que sea necesario conservar durante un determinado período de tiempo y, después, eliminar de forma permanente. 
    
- Visados de trabajo que tengan que marcarse como registros para que no se puedan editar ni eliminar. 
    
En todos estos casos, las etiquetas de retención le permiten aplicar la configuración de retención para el control de gobernanza en el nivel de elemento (documento o correo electrónico).
  
Con las etiquetas de retención, puede:
  
- **Permitir que personas de la organización apliquen una etiqueta de retención manualmente** a contenido en Outlook y Outlook en la Web, OneDrive, SharePoint y grupos de Microsoft 365. Los usuarios a menudo conocen mejor el tipo de contenido con el que están trabajando, por lo que pueden clasificarlo y aplicar la configuración de retención correspondiente. 
    
- **Aplicar etiquetas de retención a contenido automáticamente** si coincide con condiciones específicas, como: 
    - Tipos específicos de información confidencial.
    - Palabras clave específicas que coinciden con una consulta que haya creado.
    - Coincidencias de patrón para un clasificador que se puede entrenar.

- **Iniciar el período de retención desde el momento en que se etiquetó el contenido** para los documentos de los sitios de SharePoint y las cuentas de OneDrive, así como para elementos de correo electrónico salvo los elementos de calendario. Si aplica una etiqueta de retención con esta configuración a un elemento del calendario, el período de retención comienza desde el momento en que se envía.

- **Iniciar el período de retención cuando se produzca un evento**, por ejemplo, cuando los empleados abandonan la organización o cuando vencen los contratos.

- ** Aplicar una etiqueta de retención predeterminada a una biblioteca, carpeta o conjunto de documentos** en SharePoint, de modo que todos los documentos almacenados en esa ubicación hereden la etiqueta de retención predeterminada.

Además, las etiquetas de retención admiten la [administración de registros](records-management.md) de correo electrónico y documentos en todas las aplicaciones y servicios de Microsoft 365. Puede usar las etiquetas de retención para clasificar el contenido como un registro. Cuando ocurre esto y el contenido permanece en Microsoft 365, la etiqueta coloca otras restricciones en el contenido que podrían ser necesarias por razones reglamentarias. Para obtener más información, incluida una comparación de las acciones permitidas o bloqueadas, consulte [Información acerca de los registros](records.md).

Las etiquetas de retención, al igual que las [etiquetas de confidencialidad de ](sensitivity-labels.md), no se conservan si el contenido se mueve fuera de Microsoft 365.

No hay límite en el número de etiquetas de retención que se apoyan para un inquilino. Sin embargo, 10 000 es el número máximo de directivas que se admiten para un inquilino y éstas incluyen las directivas que aplican las etiquetas (directivas de etiquetas de retención y directivas de retención de aplicación automática), así como las directivas de retención.

#### <a name="classifying-content-without-applying-any-actions"></a>Clasificar contenido sin aplicar acciones

Aunque el propósito principal de las etiquetas de retención es conservar o eliminar contenido, también puede usar las etiquetas de retención sin activar la retención u otras acciones. En este caso, se puede utilizar una etiqueta de retención simplemente como una etiqueta de texto, sin imponer ninguna acción.
  
Por ejemplo, puede crear y aplicar una etiqueta de retención denominada "revisar más adelante" sin acciones y, a continuación, usar esa etiqueta para buscar el contenido posteriormente.
  
![Página “Configuración de etiquetas” con la retención desactivada](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Usar una etiqueta de retención como condición en una directiva DLP

Puede especificar una etiqueta de retención como condición en una directiva de prevención de pérdida de datos (DLP) para los documentos de SharePoint. Por ejemplo, configure una directiva DLP para evitar que los documentos se compartan fuera de la organización si se les aplicó una etiqueta de retención específica.

Para obtener más información, vea [Usar una etiqueta de retención como condición en una directiva DLP](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).

#### <a name="retention-labels-and-policies-that-apply-them"></a>Etiquetas de retención y directivas que se aplican a ellas

Las etiquetas de retención son bloques de creación independientes y reutilizables. La finalidad principal de una directiva de etiqueta es agrupar un conjunto de etiquetas de retención y especificar las ubicaciones donde quiere que aparezcan. Luego, los administradores y usuarios pueden aplicar esas etiquetas al contenido de estas ubicaciones.
  
![Diagrama de etiquetas, directivas de etiquetas y ubicaciones](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
Cuando se publican las etiquetas de retención, se incluyen en una directiva de etiqueta de retención que permite a los administradores y usuarios realizar ciertas selecciones:

- Se puede incluir una única etiqueta de retención en varias directivas de etiquetas de retención.

- Las directivas de etiquetas de retención especifican las ubicaciones donde se publicarán las etiquetas de retención.

- También puede incluirse una sola ubicación en numerosas directivas de etiquetas de retención.

Además de las directivas de etiquetas de retención, también puede crear una o varias directivas de aplicación automática, cada una con una sola etiqueta de retención. Con esta directiva, se aplica una etiqueta de retención automáticamente cuando se cumplan las condiciones especificadas en la directiva. 

#### <a name="retention-label-policies-and-locations"></a>Ubicaciones y directivas de etiquetas de retención

En función de la finalidad de las etiquetas de retención, pueden publicarse en distintas ubicaciones.
  
| Si la etiqueta de retención... | Entonces, se puede aplicar la directiva de etiqueta a... |
|:-----|:-----|
|Se publica para administradores y usuarios finales  <br/> |Exchange, SharePoint, OneDrive, Grupos de Microsoft 365  <br/> |
|Se aplica automáticamente en función de los tipos de información confidencial o clasificadores que se pueden entrenar  <br/> |Exchange (solo todos los buzones), SharePoint, OneDrive  <br/> |
|Se aplica automáticamente basándose en una consulta  <br/> |Exchange, SharePoint, OneDrive, Grupos de Microsoft 365  <br/> |
   
En Exchange, las etiquetas de aplicación automática solo se aplican a mensajes nuevos enviados (datos en tránsito), no a todos los elementos que estén actualmente en el buzón (datos en reposo). Además, las etiquetas de aplicación automática para tipos de información confidencial y clasificadores que se pueden entrenar solo se pueden aplicar a todos los buzones; es decir, no puede seleccionar buzones concretos.
  
Las carpetas públicas de Exchange, Skype y los chats y mensajes de canal de Teams no admiten etiquetas de retención. Para conservar y eliminar contenido de estas ubicaciones, use en cambio directivas de retención.

#### <a name="only-one-retention-label-at-a-time"></a>Solo una etiqueta de retención a la vez

Solo se puede asignar una etiqueta de retención al contenido (como un correo electrónico o un documento) a la vez:
  
- En el caso de las etiquetas de retención asignadas manualmente por los administradores o usuarios finales, estos pueden quitar o cambiar la etiqueta de retención asignada.
    
- Si el contenido tiene asignado una etiqueta de aplicación automática, esta etiqueta puede reemplazarse por una etiqueta de retención publicada.
    
- Si el contenido tiene asignado una etiqueta de retención publicada, no puede reemplazarse con una etiqueta de aplicación automática.
    
- Si hay varias reglas que asignan una etiqueta de aplicación automática y el contenido cumple las condiciones de varias reglas, se asignará la etiqueta de retención de la regla más antigua.
    
Para comprender cómo y por qué se aplica una etiqueta de retención en lugar de otra, es útil comprender la diferencia entre asignar explícitamente una etiqueta y asignar implícitamente una etiqueta:

- Las etiquetas de retención aplicadas desde una directiva de etiqueta se asignan explícitamente
- Las etiquetas de retención que se aplican automáticamente desde una directiva de aplicación automática se asignan implícitamente

Una etiqueta de retención asignada explícitamente tiene prioridad sobre una etiqueta de retención asignada implícitamente. Para más información, consulte la sección [Los principios de la retención, ¿o qué tiene prioridad?](retention.md#the-principles-of-retention-or-what-takes-precedence)en esta página.

#### <a name="monitoring-retention-labels"></a>Supervisar las etiquetas de retención

Desde el Centro de cumplimiento de Microsoft 365, utilice la **Información general** > **sobre la clasificación de datos** para supervisar la forma en que se usan las etiquetas de retención en su inquilino e identificar el lugar en el que se ubican los elementos etiquetados. Para obtener más información, incluyendo requisitos previos importantes, consulte [Conozca sus datos: información general sobre la clasificación de datos](data-classification-overview.md).

Posteriormente, podrá profundizar en los detalles mediante el [explorador de contenido](data-classification-content-explorer.md) y el [explorador de actividades](data-classification-activity-explorer.md).

> [!TIP]
>Considere la posibilidad de usar cierta información sobre la clasificación de datos, como los clasificadores capacitados y los tipos de información confidencial, para ayudarle a identificar el contenido que podría necesitar retener, eliminar o administrar como registro.

El Centro de seguridad y cumplimiento de Office 365 tiene la información general equivalente para las etiquetas de retención de **Gobierno de información** > **Panel**, así como información más detallada sobre el **Gobierno de información** > **Explorador de actividad de etiquetas**. Para obtener más información acerca de cómo supervisar las etiquetas de retención de este antiguo centro de administración, consulte la siguiente documentación:
- [Ver los informes de gobierno de datos](view-the-data-governance-reports.md)
- [Ver el uso de etiquetas con el análisis de etiquetas](label-analytics.md)
- [Ver la actividad de etiquetas de documentos](view-label-activity-for-documents.md)

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label"></a>Usar la Búsqueda de contenido para encontrar todo el contenido relacionado con una etiqueta de retención específica

Después de asignar las etiquetas de retención al contenido (ya sea a través de los usuarios o aplicadas automáticamente), puede usar la Búsqueda de contenido para encontrar todo los elementos clasificados bajo una etiqueta de retención específica.

Cuando cree una búsqueda de contenido, elija la condición de **Etiqueta de retención**, y luego introduzca el nombre completo de la etiqueta de retención o parte del nombre de la etiqueta y utilice un comodín. Para obtener más información, consulte [Consultas de palabras clave y condiciones de búsqueda para la Búsqueda de Contenido](keyword-queries-and-search-conditions.md).
  
![Condición de la etiqueta de retención](../media/retention-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a>Comparar las funcionalidades de las directivas de retención y las etiquetas de retención

La siguiente tabla le ayudará a identificar si debe usar una directiva de retención o una etiqueta de retención, según sus funcionalidades.

|Funcionalidad|Directiva de retención |Etiqueta de retención|
|:-----|:-----|:-----|:-----|
|Configuración de retención que puede conservar y, después, eliminar, solo conservar o solo eliminar. |Sí |Sí |
|Cargas de trabajo compatibles: <br />- Exchange <br />- SharePoint <br />- OneDrive <br />- Grupos de Microsoft 365 <br />- Skype Empresarial <br />- Teams|<br /> Sí <br /> Sí <br /> Sí <br /> Sí <br /> Sí <br /> Sí | <br /> Sí, excepto carpetas públicas <br /> Sí <br /> Sí <br /> Sí <br /> No <br /> No  |
|Retención aplicada automáticamente | Sí | Sí |
|Retención aplicada manualmente | No | Sí |
|Presencia de interfaz de usuario para usuarios finales | No | Sí |
|Se mantiene si el contenido se mueve | No | Sí, con Microsoft 365 |
|Declara el elemento como un registro| No | Sí |
|Inicio del período de retención cuando se etiqueta o basado en un evento | No | Sí |
|Revisión para eliminación | No| Sí |
|Prueba de eliminación durante un máximo de 7 años | No |Sí, cuando el elemento se declara como registro|
|Auditoría de las actividades administrativas| Sí | Sí|
|Identificación de elementos sujetos a la retención: <br /> - Búsqueda de contenido <br /> - Página clasificación de datos, explorador de contenido, explorador de actividad | <br /> No <br /> No | <br /> Sí <br /> Sí|

Tenga en cuenta que puede usar tanto directivas de retención como etiquetas de retención como métodos de retención complementarios. Por ejemplo:

1. Puede crear y configurar una directiva de retención que elimine el contenido automáticamente al cabo de cinco años de la última modificación y aplicar la directiva a todas las cuentas de OneDrive.

2. Puede crear y configurar una etiqueta de retención que mantenga el contenido para siempre y agregarla a una directiva de etiquetas que publique en todas las cuentas de OneDrive. Debe explicar a los usuarios cómo aplicar manualmente esta etiqueta a documentos específicos que se deban excluir de la eliminación automática si no se modifican después de cinco años.

Para obtener más información acerca de cómo funcionan las directivas de retención y las etiquetas de retención conjuntamente y cómo determinar el resultado combinado, vea la siguiente sección en la que se explican los principios de la retención y las prioridades.

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Los principios de retención o qué tiene precedencia

Es posible o incluso probable que el contenido tenga varias etiquetas y directivas de retención aplicadas, cada una con una acción (conservar, eliminar o conservar y, después, eliminar) y un período de retención diferentes. ¿Qué tiene prioridad? 

A grandes rasgos, la retención siempre tiene prioridad sobre la eliminación y después tiene prioridad el período de retención más largo. 

Sin embargo, hay algunos factores más a tener en cuenta. El siguiente flujo le ayudará a entender el resultado; cada nivel actúa como un separador de nivel superior a inferior: si el resultado está determinado por el primer nivel, no es necesario pasar al nivel siguiente y así sucesivamente. El flujo se desplaza al siguiente nivel para determinar el resultado para el que la configuración de retención tiene prioridad solo si las reglas del nivel anterior no pueden determinar el resultado.

![Diagrama de los principios de retención](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Explicación de los cuatro niveles diferentes:
  
1. **La retención gana a la eliminación.** Suponga que una directiva de retención está configurada para eliminar el correo electrónico de Exchange después de tres años, pero otra directiva de retención está configurada para que se conserve el correo electrónico de Exchange durante cinco años y después se elimine. Todo el contenido que llegue a tres años de antigüedad se eliminará y quedará oculto de la vista de los usuarios, pero se mantendrá en la carpeta elementos recuperables hasta que llegue a la antigüedad de cinco años, cuando se elimine de forma permanente. 
2. **El período de retención más largo gana**. Si el contenido está sujeto a varias configuraciones de retención que conservan contenido durante distintos períodos de tiempo, el contenido se conservará hasta el final del período de retención más largo.
    
3. **La inclusión explícita gana a la inclusión implícita**. Esto significa que: 
    
    1. Si un usuario asigna manualmente una etiqueta de retención con configuración de retención a un elemento, como un correo electrónico de Exchange o un documento de OneDrive, esa etiqueta de retención tiene prioridad sobre una directiva de retención asignada en el nivel de sitio o buzón y una etiqueta de retención predeterminada asignada por la biblioteca de documentos. Por ejemplo, si la etiqueta de retención explícita está configurada para conservar el contenido durante diez años, pero una directiva de retención asignada al sitio está configurada para que la conservación sea de solo cinco años, la etiqueta de retención tendrá prioridad. Las etiquetas de retención de aplicación automática se consideran implícitas en lugar de explícitas, porque Microsoft 365 las aplica automáticamente.
    
    2. Si una directiva de retención incluye una ubicación específica, como el buzón de un usuario específico o una cuenta de OneDrive, esa directiva de retención tiene prioridad sobre otra directiva de retención que se aplica a los buzones de todos los usuarios o a las cuentas de OneDrive pero que no incluye específicamente el buzón de ese usuario.
    
4. **El período de eliminación más corto gana.** De forma similar, si el contenido está sujeto a varias configuraciones de retención que eliminan contenido sin un período de retención, se eliminará el contenido al final del período de retención más corto. 

Por último, una directiva o etiqueta de retención no puede eliminar permanentemente ningún contenido que esté en espera para eDiscovery. Cuando se libera la retención, el contenido vuelve a ser apto para el proceso de limpieza descrito anteriormente.

## <a name="auditing-retention-configuration"></a>Auditar la configuración de retención

Las acciones del administrador en cuanto a las directivas y a las etiquetas de retención se guardan en el registro de auditoría cuando la [auditoría está habilitada](turn-audit-log-search-on-or-off.md). Por ejemplo, se genera un evento de auditoría cuando se crea, se configura o se elimina alguna directiva o etiqueta de retención. Para obtener la lista completa, consulte las [Actividades de las directivas y etiquetas de retención](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a>Cmdlets de PowerShell para directivas de retención y etiquetas de retención

Para usar los cmdlets de retención, primero debe [conectarse a PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). A continuación, use cualquiera de los siguientes cmdlets:

- [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a>Usar directivas de retención y etiquetas de retención en lugar de características más antiguas

Si tiene que conservar o eliminar contenido en 365 Microsoft de manera proactiva para la gobernanza de la información, le recomendamos que use las directivas de retención y las etiquetas de retención en lugar de las siguientes características antiguas. 
  
Si actualmente usa esas características más antiguas, estas seguirán funcionando en paralelo con las directivas de retención y las etiquetas de retención. Sin embargo, le recomendamos que, en adelante, utilice directivas de retención y etiquetas de retención. Proporcionan un mecanismo único para administrar centralmente tanto la retención como la eliminación de contenido en Microsoft 365.

**Características anteriores de Exchange Online:**

- [Conservación local y Retención por juicio](https://go.microsoft.com/fwlink/?linkid=846124) (suspensión de eDiscovery) 

- [Cómo identificar el tipo de retención en un buzón de Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Etiquetas de retención y directivas de retención](https://go.microsoft.com/fwlink/?linkid=846125), lo que también se conoce como [administración de registros de mensajes (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (solo eliminación)
    
Vea también [Retirada de herramientas heredadas de eDiscovery](legacy-ediscovery-retirement.md)


**Características anteriores de SharePoint y OneDrive:**

- [Agregar contenido a un caso y poner orígenes en suspensión en el Centro de eDiscovery](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (suspensión de eDiscovery) 
    
- [Directivas de eliminación de documentos](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (solo eliminación)
    
- [Configuración de administración de registros local](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retención) 
    
- [Usar las directivas de cierre y eliminación de sitio](https://support.microsoft.com/es-ES/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (solo eliminación) 
    
- [Directivas de administración de información](intro-to-info-mgmt-policies.md) (solo eliminación)
     
Si ha usado previamente cualquiera de las retenciones de eDiscovery con el propósito del gobierno de información, debe usar en su lugar una directiva de retención para el cumplimiento proactivo. Use eDiscovery solo para retenciones.
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>Directivas de retención y directivas de tipo de contenido de SharePoint o directivas de administración de información

Si ha configurado los sitios de SharePoint para directivas de tipo de contenido o directivas de administración de información para conservar el contenido de una lista o biblioteca, estas directivas se omiten cuando se aplica una directiva de retención. 

## <a name="related-information"></a>Información relacionada

- [Límites de SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Límites y especificaciones para Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Cumplir con la norma SEC 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>Pasos siguientes

Si está listo para crear directivas de retención, vea [Crear y configurar directivas de retención](create-retention-policies.md).

Para crear y aplicar etiquetas de retención:
- [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
- [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)

