---
title: Preparar el entorno para experiencias de temas (versión preliminar)
description: Prepare el entorno para que pueda proporcionar todo el contenido posible a sus usuarios con experiencias de tema (vista previa).
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX
ms.openlocfilehash: 19112b222be328eb75b7eea807bea94e524fd56d
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683469"
---
# <a name="get-your-environment-ready-for-topic-experiences-preview"></a>Preparar el entorno para experiencias de temas (versión preliminar)

> [!Note]
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información acerca del Project Cortex](https://aka.ms/projectcortex).

Para aprovechar al máximo las experiencias de los temas, desea incluir tantos contenidos como sea posible para la detección de temas, de modo que pueda tener un amplio conjunto de temas para los usuarios. Pero, ¿qué contenido se debe usar para la detección de temas? ¿Cómo se puede maximizar el contenido que se indiza mientras que el control permanece en el control? Cuanto más contenido se encuentra en el ámbito, mejor es la información que la inteligencia artificial puede generar. Este artículo le guiará por los pasos de planeación para asegurarse de que incluye el contenido adecuado y de que dispone de las personas y los recursos adecuados para que los usuarios tengan una buena experiencia.

Para planear las experiencias del tema (versión preliminar), debe:

![Migrar, conectar, modernizar, proteger e identificar los pasos para la incorporación a la administración del conocimiento](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrar contenido a SharePoint](#1-migrate-content-to-microsoft-365)
    - La minería de temas solo incluye contenido en los sitios de SharePoint.
      - Cuando sea posible, migre contenido valioso a SharePoint Online desde orígenes externos.
      - Priorizar orígenes de contenido con alta probabilidad de conocimiento de tácitas.
      - Resalte The Benefits of Knowledge Management para animar a los usuarios a mover contenido de OneDrive a los sitios de SharePoint.

2. [Conectar información a Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - En el futuro, el contenido externo puede incorporarse al gráfico de conocimientos y estar disponible.
    - Para el contenido que no se puede mover, considere la posibilidad de usar conectores de Graph para mejorar la búsqueda y preparar la inclusión futura.

3. [Modernizar páginas de SharePoint](#3-modernize-sharepoint-pages)
    - Las tarjetas de tema solo se pueden exponer en las páginas modernas.
    - Identificar las páginas clásicas de perfil alto que son candidatos de modernización.

4. [Proteger el contenido adecuadamente](#4-secure-content-appropriately)
    - Los recursos de temas se recortan por seguridad en función de los permisos de un usuario.
    - Identifique cualquier contenido que pueda tener de forma incorrecta permisos amplios o restrictivos:
      - Incentive a los propietarios de sitios para que usen los informes de uso compartido para revisar los permisos
      - Hacer que los administradores audirán contenido compartido ampliamente mediante la búsqueda
      - Anime a los propietarios de contenido a compartir contenido que no sea confidencial y que pueda tener un mayor beneficio para la organización.
    - Revise la configuración de Microsoft Graph en usuarios y contenido:
      - La minería de temas respeta la configuración con exclusión de contenido de la búsqueda o Delve. Revise si estas configuraciones siguen siendo relevantes.

5. [Identificación de los temas y los administradores del conocimiento](#5-identify-knowledge-managers-and-topics)
    - Use las taxonomías existentes para crear manualmente los temas.
    - Identificación de expertos en la materia (SME) para temas anticipados o inicializados.
    - Identificar los sitios que cubren un gran volumen de datos valiosos que se pueden usar para la extracción de temas piloto.
    - Atraer a los administradores de conocimiento y las comunidades de prácticas.

## <a name="1-migrate-content-to-microsoft-365"></a>1. migrar contenido a Microsoft 365

Hay varias herramientas y servicios para ayudarle con la migración: puede obtener información general e información sobre cómo migrar en [migrar el contenido a Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online). Las herramientas de migración incluyen:

- [Administrador de migración](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [Herramienta de migración de SharePoint (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Herramientas y servicios de migración de asociados](https://www.microsoft.com/solution-providers)

Aprovechar al máximo la migración:

- Migre a un sitio moderno, que incluya a Microsoft Teams. Aunque la indización puede producirse en cualquier sitio de SharePoint (clásico o moderno), Mostrar temas a los usuarios a través de las resaltadas y las tarjetas solo se produce en las páginas modernas.
- Mantener nombres de usuario: la mayoría de las herramientas de migración le permiten asignar identidades de usuario en la migración, de modo que las propiedades como creadas o modificadas por se mantengan después de la migración. Esto es importante para los temas porque la creación de archivos se usa para identificar a los expertos que se agregan a una página de tema o tarjeta. 
- Hacer que los nombres de cuenta de servicio sean descriptivos: hay algunos casos en los que no es posible mantener nombres de usuario. Por ejemplo, si va a migrar contenido creado por alguien que ya no es un empleado de la organización. En este caso, la mayoría de las herramientas de migración moverán un archivo como si se hubiera creado mediante una cuenta de administrador o una cuenta de servicio. Si esto ocurre con frecuencia, la cuenta de servicio podría aparecer en la lista de temas como experto. Aquí es donde se convierte en realmente importante el nombre de esa cuenta. Si lo convierte en un tema descriptivo, la presencia de estas cuentas no humanas será comprensible para los usuarios que consumen temas.

## <a name="2-connect-information-to-microsoft-graph"></a>2. conectar información a Microsoft Graph

Si no puede migrar algún contenido, conéctelo con Microsoft Graph:

- Considere la posibilidad de implementar [conectores de contenido de gráficos](https://docs.microsoft.com/microsoftsearch/connectors-overview). Con los conectores, el contenido externo se puede indizar en Microsoft Graph, donde los usuarios pueden descubrirlo a través de Microsoft Search.
- Los futuros desarrollos proporcionarán datos externos a las experiencias de los temas.

## <a name="3-modernize-sharepoint-pages"></a>3. modernizar páginas de SharePoint

Como las tarjetas de temas y los resaltados solo pueden aparecer en las páginas modernas, actualice las páginas que desee incluir en las experiencias de los temas de Classic a moderna. Consulte [modernizar los sitios de SharePoint clásicos](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites). Puede usar el [analizador de modernización de SharePoint](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) para preparar los sitios clásicos para modernizar.

Si tiene una gran cantidad de sitios clásicos, dé prioridad a las páginas de perfil alto para convertirlas a modernas.

## <a name="4-secure-content-appropriately"></a>4. proteger el contenido adecuadamente

Cuando los usuarios interactúan con una tarjeta de tema o una página de tema, es posible que vean recursos diferentes. Esto se debe a que tienen acceso a distintos archivos asociados con el tema. Si los permisos subyacentes son demasiado estrictos, puede reducirse la Serendipitous? a los aspectos de la detección de información a través de temas. Por otra parte, si son demasiado amplias, un tema podría exponer contenido a un usuario que no desea que vean.
La administración de permisos adecuados es fundamental aquí. Y la administración de permisos correctos se basa en una asociación continua entre los administradores y los propietarios de contenido. Aunque esto puede ser una actividad en curso, hay algunos pasos prácticos que puede tomar al preparar los temas:

- Anime a los propietarios del sitio a revisar el uso compartido y los permisos.

  Los propietarios de sitios de SharePoint pueden revisar un informe de uso compartido de su sitio que muestra todos los detalles de todos los permisos y de los vínculos de uso compartido configurados en el sitio, consulte [Sharing Reports](https://docs.microsoft.com/sharepoint/sharing-reports). Enumera los usuarios internos y externos (invitados).

  Los propietarios de sitios también pueden ver quién tiene permisos para el sitio yendo a la página **permisos del sitio** y **Configuración avanzada de permisos** .

  1. En el sitio, elija **configuración** de  >  **permisos del sitio**. Compruebe quién aparece en propietarios de sitios, miembros del sitio y visitantes del sitio. Compruebe si hay algún usuario invitado.
  2. En la página **permisos** , elija **Configuración avanzada de permisos**. Puede comprobar los permisos únicos y ver quién tiene acceso limitado a los elementos del sitio.

- Audite Microsoft 365 grupos y equipos para asegurarse de que están correctamente establecidos como grupos o equipos públicos o privados. Los nuevos grupos Teams y Microsoft 365 se establecen en Private de forma predeterminada, pero cuando se publica por primera vez público de forma predeterminada. Si había adoptado anteriormente estas tecnologías, es posible que desee revisar. Además, la función de un equipo evoluciona a menudo a lo largo de su ciclo de vida y es posible que sea necesario actualizar la configuración para reflejar el uso actual del equipo.
- Revise el uso de "todos", "todos excepto los usuarios externos" o grupos de seguridad amplios. El contenido se puede compartir incorrectamente con estos valores. Para revisar el uso de estos grupos, puede:
  - Crear una cuenta que no tenga pertenencias a grupos
  - Use la búsqueda con esta cuenta para descubrir contenido que se comparte ampliamente.
  - Si el contenido inadecuado es visible para esta cuenta a través de la búsqueda, puede trabajar con los propietarios del sitio para corregir la configuración de permisos.

Además de los permisos, también puede controlar el ámbito de lo que se puede detectar a través de los temas. Siempre tiene control sobre lo que se indiza.

Los administradores pueden configurar la indización en el centro de administración de Microsoft 365. Al configurar la [Administración del conocimiento](set-up-topic-experiences.md), puede:

- Permitir la detección en todos los sitios de SharePoint o especificar los sitios que se van a incluir o excluir como orígenes de temas.
- Si tiene términos confidenciales, también puede excluir los temas por nombre. Por ejemplo, si tiene el nombre de un proyecto confidencial en el que no desea que aparezca el resaltado o la tarjeta, independientemente de los permisos del usuario, puede excluir ese nombre de proyecto.

En el nivel de contenido, también puede controlar lo que se puede detectar. Cualquier configuración que haya hecho para excluir contenido de la búsqueda también se usará en la detección de contenido. Así, por ejemplo, si ha excluido una biblioteca de documentos específica de la que aparece en los resultados de búsqueda, esta biblioteca de documentos no se utilizará para la detección de temas.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. identificar a los administradores y los temas de conocimiento

La administración de temas implica tres funciones clave, entre las que se incluyen dos nuevos roles de Azure Active Directory (AAD): administrador de conocimiento y administrador de conocimiento:

- El administrador de la información (KA) es un rol técnico, que suele encontrarse en este. Este rol permite configurar las experiencias de los temas en el centro de administración de M365, así como la configuración del descubrimiento y la visibilidad de los temas.
- El administrador de conocimientos (KM) trabaja con los temas ellos mismos y supervisa la calidad y la integridad.
- Los colaboradores de temas (ect) no se basan en un rol de AAD, sino en los del centro de administración. Son expertos en la materia que pueden curater el contenido de los temas y agregar recursos y personas.

En función de su organización, es posible que tenga algunas o muchas personas que actúen en estas funciones. Para algunas organizaciones, pueden ser las mismas personas.

| Administrador de conocimiento | Administrador de conocimiento | Colaborador de temas |
|:-------|:-------|:-------|:-------|
| Rol de AAD | Rol de AAD | ESPECIALIZADOS |
| Tiene acceso al centro de administración | Tiene acceso al centro de administración | Sin acceso al centro de administración |
| Configura las experiencias de los temas | Posee la administración y la calidad de los temas | Contribuye a los temas en función de su experiencia. |
| Garantiza que se apliquen los estándares de seguridad y cumplimiento y que comprenda el contrato de licencia.| Realiza tareas de administración de temas como crear, editar, eliminar y rechazar temas. Admite colaboradores de temas con sus tareas. | Curates la información y el contenido de las páginas del tema, incluidos qué personas y recursos están anclados a ese tema. |

Los elementos destacados y las tarjetas se mostrarán a los usuarios en el contexto de su trabajo, por ejemplo, cuando exploren páginas modernas en SharePoint. Puede controlar la experiencia del usuario final para los temas.

- ¿Quién puede ver los temas? La visibilidad del tema está configurada en el centro de administración de Microsoft 365. Elija los grupos a los que desea permitir ver los temas:
  - Todos los usuarios de mi organización. "Todos" no incluye invitados, es todos los usuarios internos de su directorio
  - Solo personas seleccionadas o grupos de seguridad (esta opción es buena si sigue implantando experiencias de tema, por lo que puede realizar pruebas con un subconjunto de usuarios). Si desea que los invitados vean temas, tendrá que usar la opción "personas o grupos de seguridad seleccionados" y concederles una licencia.
  - Con nadie.

    Todos los usuarios, incluso los usuarios invitados, tendrán que aplicar una licencia para ver la experiencia del tema. Recuerde que los permisos siempre controlan lo que se puede ver.

- ¿Qué temas están visibles? Puede elegir entre:
  - Mostrar todos los temas del candidato.
  - Mostrar solo temas confirmados.

Ahora que tenemos los administradores, los expertos y los usuarios, podemos hablar sobre los propios temas.

- Es recomendable inicializar los temas en la lista de temas. La calidad y la cantidad de temas se basan en el contenido; solo se creará como tema si se incluye en el contenido que se encuentra en el ámbito. Si hay información suficiente y evidencia para el tema, se creará en el AI. La inicialización de temas es donde el administrador de conocimientos y los expertos en el tema pueden ayudarle. La combinación de los conocimientos humanos con AI es la mejor ruta para los temas de calidad. Por lo tanto, si tiene temas que prevé, puede crearlas manualmente en el centro de temas. Al hacerlo, se proporcionará a los AI una señal fuerte de la relevancia de ese tema y se identificarán los recursos y las personas que se asociarán con ese tema.
- Use las taxonomías existentes para ayudarle en la planeación de temas, ya sea desde SharePoint o desde cualquier lugar. Las taxonomías existentes a menudo incluyen términos organizativos, productos, áreas de temas, etc. Los orígenes de temas también pueden provenir de listas de proyectos, marcadores de búsqueda existentes, etc.
