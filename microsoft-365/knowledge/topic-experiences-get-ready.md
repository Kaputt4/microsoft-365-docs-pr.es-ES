---
title: Preparar el entorno para los temas de Microsoft Viva
description: Prepare el entorno para que pueda proporcionar todo el contenido posible a los usuarios con Temas de Microsoft Viva.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 2db8654bf7bb1bc5ef4759c1617a84ae2153553a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917397"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Preparar el entorno para los temas de Microsoft Viva

Para disfrutar al máximo de Los temas de Viva, desea incluir todo el contenido posible para la detección de temas, de modo que pueda tener un amplio conjunto de temas para los usuarios. Pero, ¿qué contenido se debe usar para la detección de temas? ¿Cómo se maximiza el contenido indizado mientras se mantiene el control? Entre más contenido esté en el ámbito, mejor será la información que pueda descubrir la inteligencia artificial. Este artículo le guía por los pasos de planeación para asegurarse de que está incluyendo el contenido adecuado y de que tiene las personas y recursos adecuados para realizar una buena experiencia para los usuarios.

Para planear temas de Viva, debe:

![Migrar, conectar, modernizar, proteger e identificar los pasos para la incorporación a la administración de conocimientos](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrar contenido a SharePoint](#1-migrate-content-to-microsoft-365)
    - La indización de temas solo incluye contenido en sitios de SharePoint.
      - Siempre que sea posible, migre contenido valioso a SharePoint Online desde orígenes externos.
      - Priorizar orígenes de contenido con alto potencial para conocimientos tácitos.
      - Resalte las ventajas de la administración de conocimientos para animar a los usuarios a mover contenido de OneDrive a sitios de SharePoint.

2. [Conectar información a Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - En el futuro, el contenido externo puede entrar en el gráfico de conocimientos y estar disponible.
    - Para el contenido que no se puede mover, considere la posibilidad de usar Graph Connectors para mejorar la búsqueda y prepararse para la inclusión futura.

3. [Modernizar páginas de SharePoint](#3-modernize-sharepoint-pages)
    - Las tarjetas de tema solo se pueden ver en páginas modernas.
    - Identificar páginas clásicas de alto perfil que son candidatas a la modernización.

4. [Proteger el contenido adecuadamente](#4-secure-content-appropriately)
    - Los recursos de tema se recortan en función de los permisos de un usuario.
    - Identifique cualquier contenido que pueda tener permisos incorrectos amplios o restrictivos:
      - Animar a los propietarios de sitios a usar los informes de uso compartido para revisar los permisos
      - Hacer que los administradores auditan el contenido compartido ampliamente mediante la búsqueda
      - Anime a los propietarios de contenido a compartir contenido que no sea confidencial y que pueda tener un beneficio más amplio para la organización.
    - Revise la configuración de Microsoft Graph en usuarios y contenido:
      - La indización de temas respeta la configuración excluyendo el contenido de Search o Delve (por ejemplo, NOINDEX). Revise si estas configuraciones siguen siendo relevantes.

5. [Identificar los jefes de conocimiento y los temas](#5-identify-knowledge-managers-and-topics)
    - Use taxonomías existentes para crear manualmente temas o ayuda para confirmar temas sugeridos por AI.
    - Identificar expertos en la materia (PYME) para temas anticipados o seedados.
    - Identifique los sitios que cubren un gran número de datos valiosos que se pueden usar para la minería de temas piloto.
    - Interactúe con los administradores de conocimientos y las comunidades de prácticas.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrar contenido a Microsoft 365

Hay varias herramientas y servicios que le ayudarán con la migración: puede obtener información general e información sobre cómo migrar en Migrar el contenido a [Microsoft 365](/sharepointmigration/migrate-to-sharepoint-online). Las herramientas de migración incluyen:

- [Administrador de migración](/sharepointmigration/mm-get-started)
- [Herramienta de migración de SharePoint (SPMT)](/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Servicios y herramientas de migración de partners](https://www.microsoft.com/solution-providers)

A su vez, realice la migración al máximo:

- Migrar a un sitio moderno, que incluye Microsoft Teams. Aunque la indización puede ocurrir en cualquier sitio de SharePoint (clásico o moderno), mostrar temas a los usuarios a través de resaltados y tarjetas solo ocurre en páginas modernas.
- Mantener nombres de usuario: la mayoría de las herramientas de migración le permiten asignar identidades de usuario en toda la migración, de modo que las propiedades como Created By o Modified By se mantengan después de la migración. Esto es importante para los temas porque la autoría de archivos se usa para identificar los expertos que se agregan a una página o tarjeta de tema. 
- Hacer que los nombres de cuenta de servicio sean descriptivos: habrá algunos casos en los que no sea posible mantener nombres de usuario. Por ejemplo, si está migrando contenido creado por alguien que ya no es empleado de la organización. En este caso, la mayoría de las herramientas de migración moverán un archivo como si lo hubiera creado una cuenta de administrador o una cuenta de servicio. Si esto ocurre con frecuencia, esa cuenta de servicio se podría enumerar en temas como experto. Aquí es donde el nombre de esa cuenta se vuelve realmente importante. Si lo hace descriptivo, la presencia de estas cuentas no humanas será comprensible para los usuarios que consumen temas.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Conectar información a Microsoft Graph

Si no puede migrar contenido, conéctelo a Microsoft Graph:

- Considere la posibilidad de implementar [Graph Content Connectors](/microsoftsearch/connectors-overview). Con conectores, el contenido externo se puede indizar en Microsoft Graph, donde los usuarios pueden descubrirlo a través de Microsoft Search.
- Los desarrollos futuros aportarán datos externos a Los temas de Viva.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernizar páginas de SharePoint

Dado que las tarjetas de temas y los resaltados solo pueden aparecer en páginas modernas, actualice las páginas que desee incluir en Temas de Viva de clásico a moderno. Vea [Modernizar los sitios clásicos de SharePoint](/sharepoint/dev/transform/modernize-classic-sites). Puede usar el escáner de modernización de [SharePoint](/sharepoint/dev/transform/modernize-scanner) para preparar los sitios clásicos para la modernización.

Si tiene una gran cantidad de sitios clásicos, priorice las páginas de perfil alto para convertir a modernas.

## <a name="4-secure-content-appropriately"></a>4. Proteger el contenido adecuadamente

Cuando los usuarios interactúan con una tarjeta de tema o una página de tema, pueden ver recursos diferentes. Esto se debe a que tienen acceso a diferentes archivos asociados con el tema. Si los permisos subyacentes son demasiado estrictos, los aspectos serenos de la detección de información a través de los temas podrían disminuir. Por otra parte, si son demasiado amplios, un tema podría llegar contenido a un usuario que no quieres que vea.
La buena administración de permisos es fundamental aquí. Y la buena administración de permisos se basa en una asociación continua entre administradores y propietarios de contenido. Aunque puede tratarse de una actividad continua, hay algunos pasos prácticos que puede seguir al prepararse para los temas:

- Anime a los propietarios de sitios a revisar el uso compartido y los permisos.

  Los propietarios de sitios de SharePoint pueden revisar un informe de uso compartido para su sitio que muestre todos los detalles de todos los permisos y vínculos de uso compartido configurados en el [sitio,](/sharepoint/sharing-reports)vea Informes de uso compartido . Esto enumera usuarios internos y externos (invitados).

  Los **propietarios** del sitio también pueden ver quién tiene permisos para el sitio yendo a las páginas Permisos del sitio y Configuración **avanzada de** permisos.

  1. En el sitio, elija **Configuración**  >  **Permisos del sitio**. Compruebe quién aparece en Propietarios del sitio, Miembros del sitio y Visitantes del sitio. Compruebe si hay usuarios invitados.
  2. En la **página Permisos,** elija **Configuración avanzada de permisos**. Puede comprobar si hay permisos únicos y ver quién tiene acceso limitado a los elementos del sitio.

- Audite Grupos y Equipos de Microsoft 365 para asegurarse de que están configurados correctamente como grupos o equipos públicos o privados. Los nuevos grupos de Teams y Microsoft 365 se establecen como privados de forma predeterminada, pero cuando se publicaron por primera vez eran públicos de forma predeterminada. Si antes eras adoptantes de estas tecnologías, es posible que quieras revisar. Además, la función de un equipo a menudo evoluciona a lo largo de su ciclo de vida y es posible que la configuración deba actualizarse para reflejar el uso actual del equipo.
- Revise el uso de "todos", "todos excepto los usuarios externos" o grupos de seguridad amplios. El contenido puede compartirse incorrectamente con estos valores. Para revisar el uso de estos grupos, puede:
  - Crear una cuenta que no tenga pertenencias a grupos
  - Use la búsqueda con esta cuenta para detectar el contenido que se comparte ampliamente.
  - Si el contenido inadecuado es visible para esta cuenta mediante la búsqueda, puede trabajar con los propietarios del sitio para corregir la configuración de permisos.

Además de los permisos, también puede controlar el ámbito de lo que se puede detectar a través de los temas. Siempre tiene el control de lo que está indizado.

Los administradores pueden configurar la indización en el Centro de administración de Microsoft 365. Al configurar Administración [de conocimientos,](set-up-topic-experiences.md)puede:

- Permitir la detección en todos los sitios de SharePoint o especificar sitios para incluir o excluir como orígenes de temas.
- Cuando tenga términos confidenciales, también puede excluir temas por su nombre. Por ejemplo, si tiene el nombre de un proyecto confidencial, donde no desea que aparezca un resaltado o una tarjeta, independientemente de los permisos del usuario, puede excluir ese nombre de proyecto.

En el nivel de contenido, también puede controlar lo que se puede detectar. La detección de contenido también usará cualquier configuración que hayas realizado para excluir contenido de la búsqueda. Por lo tanto, por ejemplo, si ha excluido una biblioteca de documentos específica para que no aparezca en los resultados de búsqueda, esta biblioteca de documentos no se usará para la detección de temas.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Identificar los jefes de conocimiento y los temas

La administración de temas implica tres roles clave, incluidos dos nuevos roles de Azure Active Directory (AAD): Administrador de conocimientos y Administrador de conocimientos:

- El administrador de conocimientos (KA) es un rol técnico, normalmente en TI. Este rol permite configurar los Temas de Viva en el Centro de administración de M365, así como la configuración de la detección y visibilidad de los temas.
- El Administrador de conocimientos (KM) trabaja con los propios temas y supervisa su calidad y integridad.
- Los colaboradores de temas (TCs) no se basan en un rol de AAD, sino en permisos en el Centro de administración. Son expertos en la materia capaces de curar el contenido de los temas, agregando recursos y personas.

Dependiendo de la organización, es posible que haya pocas o muchas personas que actúen en estos roles. Para algunas organizaciones, pueden ser las mismas personas.

| Administrador de conocimientos | Administrador de conocimientos | Colaborador de temas |
|:-------|:-------|:-------|:-------|
| Rol AAD | Rol AAD | SME |
| Tiene acceso al Centro de administración | Tiene acceso al Centro de administración | Sin acceso al Centro de administración |
| Configurar temas de Viva | Posee la administración y la calidad de los temas | Contribuye a temas basados en su experiencia. |
| Garantiza que se cumplan los estándares de seguridad y cumplimiento y comprende el contrato de licencia.| Realiza tareas de administración de temas como crear, editar, eliminar y rechazar temas. Admite colaboradores de temas con sus tareas. | Cura la información y el contenido de las páginas de temas, incluidas las personas y los recursos anclados a ese tema. |

Los puntos destacados y las tarjetas aparecerán para los usuarios en el contexto de su trabajo, por ejemplo, mientras exploran páginas modernas en SharePoint. Puede controlar la experiencia del usuario final para los temas.

- ¿Quién puede ver temas? La visibilidad del tema se configura en el Centro de administración de Microsoft 365. Elija qué grupos permitir ver temas:
  - Todos en mi organización. "Todos" no incluye invitados, son todos los usuarios internos del directorio
  - Solo personas seleccionadas o grupos de seguridad (esta opción es buena mientras sigues implementando Temas de Viva, para que puedas probar con un subconjunto de usuarios). Si desea que los invitados consulten Temas, tendrá que usar la opción "personas seleccionadas o grupos de seguridad" y concederles una licencia.
  - Con nadie.

    Todos los usuarios, incluso los usuarios invitados, tendrán que tener una licencia aplicada para ver la experiencia del tema. Y recuerde que los permisos siempre controlan lo que se puede ver.

- ¿Qué temas están visibles? Puede elegir:
  - Mostrar todos los temas de candidatos.
  - Mostrar solo temas confirmados.

Ahora que tenemos a los administradores, expertos y usuarios, podemos hablar de los temas en sí.

- Es una buena práctica que se edimente temas en la lista de temas. La calidad y la cantidad de temas se basan en el contenido: solo se creará como un tema si se incluye en el contenido que está en el ámbito. Si hay suficiente información y pruebas para el tema, la AI la creará. Los temas de seeding son los que pueden ayudar el Administrador de conocimientos y los expertos en la materia. Combinar el conocimiento humano con la inteligencia artificial es la mejor ruta para los temas de calidad. Por lo tanto, si hay temas que prevé que puede crear manualmente en el Centro de temas. Al hacerlo, la inteligencia artificial será una señal sólida de la relevancia de ese tema y se identificarán los recursos y las personas que se asociarán con ese tema.
- Use taxonomías existentes para ayudar a planear el tema, ya sea desde SharePoint o desde otro lugar. Las taxonomías existentes suelen incluir términos de la organización, productos, áreas de asunto, entre otros. Los orígenes de temas también pueden venir de listas de proyectos, marcadores de búsqueda existentes, y así sucesivamente.