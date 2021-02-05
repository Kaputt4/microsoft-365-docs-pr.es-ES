---
title: Preparar el entorno para los temas de Microsoft Viva
description: Prepare su entorno para que pueda proporcionar todo el contenido posible a los usuarios con Temas de Microsoft Viva.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 5a13af3e78848471b436d44ab051eca945176c74
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107701"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Preparar el entorno para los temas de Microsoft Viva

Para obtener el máximo partido de Los temas Viva, desea incluir todo el contenido posible para la detección de temas, de modo que pueda tener un amplio conjunto de temas para los usuarios. Pero, ¿qué contenido se debe usar para la detección de temas? ¿Cómo se maximiza el contenido que se indiza mientras se mantiene el control? Cuando más contenido esté en el ámbito, mejor será la información que pueda descubrir la inteligencia artificial. Este artículo le guiará a través de los pasos de planeación para asegurarse de que está incluyendo el contenido adecuado y de que tiene las personas y los recursos adecuados para lograr una buena experiencia para los usuarios.

Para planear temas de Viva, debe:

![Migrar, conectar, modernizar, proteger e identificar los pasos para la incorporación a la administración del conocimiento](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Migrar contenido a SharePoint](#1-migrate-content-to-microsoft-365)
    - La indización de temas solo incluye contenido en sitios de SharePoint.
      - Siempre que sea posible, migre contenido valioso a SharePoint Online desde orígenes externos.
      - Dar prioridad a los orígenes de contenido con un alto potencial de conocimientos técnicos.
      - Resalte las ventajas de la administración del conocimiento para animar a los usuarios a mover contenido de OneDrive a sitios de SharePoint.

2. [Conectar información a Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - En el futuro, el contenido externo se puede traer al gráfico de conocimientos y estar disponible.
    - Para el contenido que no se puede mover, considere la posibilidad de usar conectores de Graph para mejorar la búsqueda y prepararse para la inclusión futura.

3. [Modernizar páginas de SharePoint](#3-modernize-sharepoint-pages)
    - Las tarjetas de tema solo se pueden ver en páginas modernas.
    - Identificar páginas clásicas de alto perfil que son candidatos de modernización.

4. [Proteger el contenido adecuadamente](#4-secure-content-appropriately)
    - Los recursos de tema se recortan en función de los permisos de un usuario.
    - Identifique cualquier contenido que pueda tener permisos incorrectos amplios o restrictivos:
      - Animar a los propietarios de sitios a usar los informes de uso compartido para revisar los permisos
      - Hacer que los administradores auditan el contenido compartido ampliamente mediante la búsqueda
      - Anime a los propietarios de contenido a compartir contenido que no sea confidencial y que pueda tener un beneficio más amplio para la organización.
    - Revise la configuración de Microsoft Graph en usuarios y contenido:
      - La indización de temas respeta la configuración excluyendo el contenido de Search o Delve (por ejemplo, NOINDEX). Revise si estas configuraciones siguen siendo relevantes.

5. [Identificación de temas y administradores de conocimientos](#5-identify-knowledge-managers-and-topics)
    - Use taxonomías existentes para crear manualmente temas o ayude a confirmar los temas sugeridos por IA.
    - Identificar expertos en la materia (MIME) para temas anticipados o seedados.
    - Identifique los sitios que cubren un gran número de datos valiosos que se pueden usar para la minería de temas piloto.
    - Involucra a los administradores de conocimientos y a las comunidades de prácticas.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Migrar contenido a Microsoft 365

Hay varias herramientas y servicios que le ayudarán con la migración: puede obtener información general e información sobre cómo migrar el contenido a [Microsoft 365.](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) Las herramientas de migración incluyen:

- [Administrador de migración](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [Herramienta de migración de SharePoint (SPMT)](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Herramientas y servicios de migración de asociados](https://www.microsoft.com/solution-providers)

Realice la mayor parte de la migración:

- Migrar a un sitio moderno, que incluye Microsoft Teams. Aunque la indización puede producirse en cualquier sitio de SharePoint (clásico o moderno), mostrar temas a los usuarios a través de resaltados y tarjetas solo se produce en páginas modernas.
- Mantener nombres de usuario: la mayoría de las herramientas de migración le permiten asignar identidades de usuario a lo largo de la migración, de modo que las propiedades como Creado por o Modificado por se mantengan después de la migración. Esto es importante para los temas porque la autoría de archivos se usa para identificar los expertos que se agregan a una página o tarjeta de tema. 
- Hacer que los nombres de cuenta de servicio sean descriptivos: habrá algunos casos en los que no sea posible mantener nombres de usuario. Por ejemplo, si va a migrar contenido creado por alguien que ya no es empleado de la organización. En este caso, la mayoría de las herramientas de migración moverán un archivo como si lo hubiera creado una cuenta de administrador o una cuenta de servicio. Si esto ocurre con frecuencia, esa cuenta de servicio podría aparecer en la lista de temas como experto. Aquí es donde el nombre de esa cuenta se vuelve realmente importante. Si lo hace descriptivo, los usuarios que consuman temas comprenderán la presencia de estas cuentas no humanas.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Conectar información a Microsoft Graph

Si no puede migrar contenido, conéctelo a Microsoft Graph:

- Considere la posibilidad de implementar [conectores de contenido de Graph.](https://docs.microsoft.com/microsoftsearch/connectors-overview) Con conectores, el contenido externo se puede indizar en Microsoft Graph, donde los usuarios pueden detectarlo a través de Microsoft Search.
- Los desarrollos futuros aportarán datos externos a Los temas de Viva.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernizar páginas de SharePoint

Dado que las tarjetas de temas y los resaltados solo pueden aparecer en páginas modernas, actualice las páginas que desee incluir en Temas de Viva de clásico a moderno. Vea [Modernizar los sitios clásicos de SharePoint.](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites) Puede usar el escáner de modernización de [SharePoint](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) para preparar los sitios clásicos para la modernización.

Si tiene una gran cantidad de sitios clásicos, priorice las páginas de perfil alto para convertir a modernas.

## <a name="4-secure-content-appropriately"></a>4. Proteger el contenido correctamente

Cuando los usuarios interactúan con una tarjeta de tema o una página de tema, es posible que vean diferentes recursos. Esto se debe a que tienen acceso a diferentes archivos asociados con el tema. Si los permisos subyacentes son demasiado estrictos, los aspectos serendipitous de la detección de información a través de los temas podrían disminuir. Por otro lado, si son demasiado amplios, un tema podría dar contenido a un usuario que no pretendes que vea.
Una buena administración de permisos es fundamental aquí. Y una buena administración de permisos se basa en una asociación continua entre administradores y propietarios de contenido. Aunque puede tratarse de una actividad continua, existen algunos pasos prácticos que puede realizar al prepararse para los temas:

- Anime a los propietarios de sitios a revisar el uso compartido y los permisos.

  Los propietarios de sitios de SharePoint pueden revisar un informe de uso compartido de su sitio que muestra todos los detalles de todos los permisos y vínculos de uso compartido configurados en el sitio, vea [Informes de uso compartido.](https://docs.microsoft.com/sharepoint/sharing-reports) Se enumeran los usuarios internos y externos (invitados).

  Los propietarios de sitios también pueden ver quién tiene permisos para el sitio yendo a las páginas Permisos **del** sitio y Configuración **avanzada de permisos.**

  1. En el sitio, elija **Permisos**  >  **del sitio de configuración.** Compruebe quién aparece en Propietarios del sitio, Miembros del sitio y Visitantes del sitio. Compruebe si hay usuarios invitados.
  2. En la **página Permisos,** elija **Configuración avanzada de permisos.** Puede comprobar si hay permisos únicos y ver quién tiene acceso limitado a los elementos del sitio.

- Audite Grupos de Microsoft 365 y Teams para asegurarse de que están configurados correctamente como grupos o equipos públicos o privados. Los nuevos equipos y grupos de Microsoft 365 se establecen como privados de forma predeterminada, pero cuando se publicó por primera vez eran públicos de forma predeterminada. Si eras usuarios anteriores de estas tecnologías, es posible que quieras revisar. Además, la función de un equipo a menudo evoluciona a lo largo de su ciclo de vida y es posible que sea necesario actualizar la configuración para reflejar el uso actual del equipo.
- Revise el uso de "todos", "todos excepto los usuarios externos" o grupos de seguridad amplios. Es posible que el contenido se comparta incorrectamente con estos valores. Para revisar el uso de estos grupos, puede:
  - Crear una cuenta que no tenga pertenencias a grupos
  - Use la búsqueda con esta cuenta para detectar contenido que se comparte ampliamente.
  - Si el contenido inapropiado es visible para esta cuenta a través de la búsqueda, puede trabajar con los propietarios del sitio para corregir la configuración de permisos.

Además de los permisos, también puede controlar el ámbito de lo que se puede detectar a través de los temas. Siempre tiene el control de lo que se indiza.

Los administradores pueden configurar la indización en el Centro de administración de Microsoft 365. Al configurar administración de [conocimientos,](set-up-topic-experiences.md)puede:

- Permitir la detección en todos los sitios de SharePoint o especificar sitios para incluir o excluir como orígenes de temas.
- Si tiene términos confidenciales, también puede excluir temas por nombre. Por ejemplo, si tiene el nombre de un proyecto confidencial, donde no desea que aparezca un resaltado o una tarjeta, independientemente de los permisos del usuario, puede excluir ese nombre de proyecto.

En el nivel de contenido, también puede controlar lo que se puede detectar. La detección de contenido también usará cualquier configuración que haya realizado para excluir contenido de la búsqueda. Por lo tanto, por ejemplo, si ha excluido una biblioteca de documentos específica para que no aparezca en los resultados de la búsqueda, esta biblioteca de documentos no se usará para la detección de temas.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Identificar los administradores de conocimientos y los temas

La administración de temas implica tres roles clave, incluidos dos nuevos roles de Azure Active Directory (AAD): administrador de conocimientos y administrador de conocimientos:

- El administrador del conocimiento (KA) es un rol técnico, normalmente en TI. Este rol permite la configuración de los temas De Viva en el Centro de administración de M365, así como la configuración de la visibilidad y la detección de temas.
- El Administrador de conocimientos (KM) trabaja con los propios temas y supervisa su calidad e integridad.
- Los colaboradores de temas (TCs) no se basan en un rol de AAD, sino en permisos en el centro de administración. Son expertos en la materia capaces de resalte el contenido de los temas, agregando recursos y personas.

Según la organización, puede que haya pocas personas o muchas que actúen en estos roles. Para algunas organizaciones, pueden ser las mismas personas.

| Administrador de conocimientos | Administrador de conocimientos | Colaborador de temas |
|:-------|:-------|:-------|:-------|
| Rol AAD | Rol AAD | SME |
| Tiene acceso al centro de administración | Tiene acceso al centro de administración | Sin acceso al centro de administración |
| Configura temas de Viva | Posee la administración y la calidad de los temas | Contribuye a los temas en función de su experiencia. |
| Garantiza que se cumplan los estándares de seguridad y cumplimiento y comprende el contrato de licencia.| Realiza tareas de administración de temas como crear, editar, eliminar y rechazar temas. Admite colaboradores de temas con sus tareas. | Conserva la información y el contenido de las páginas del tema, incluidos los contactos y recursos que se anclan a ese tema. |

Los resaltados y las tarjetas se mostrarán a los usuarios en el contexto de su trabajo, por ejemplo, mientras exploran páginas modernas en SharePoint. Puede controlar la experiencia del usuario final para los temas.

- ¿Quién puede ver los temas? La visibilidad del tema está configurada en el Centro de administración de Microsoft 365. Elige qué grupos permitir ver los temas:
  - Todos los miembros de mi organización. "Todos" no incluye invitados, todos los usuarios internos del directorio
  - Solo las personas seleccionadas o los grupos de seguridad (esta opción es buena mientras sigue implementando Temas Viva, para que pueda probar con un subconjunto de usuarios). Si desea que los invitados consulten Temas, deberá usar la opción "Usuarios o grupos de seguridad seleccionados" y concederles una licencia.
  - Con nadie.

    Todos los usuarios, incluso los invitados, tendrán que aplicar una licencia para poder ver la experiencia del tema. Y recuerde que los permisos siempre controlan lo que se puede ver.

- ¿Qué temas están visibles? Puede elegir:
  - Mostrar todos los temas de candidatos.
  - Mostrar solo los temas confirmados.

Ahora que tenemos los administradores, expertos y usuarios, podemos hablar sobre los propios temas.

- Es una buena práctica que se edimente los temas en la lista de temas. La calidad y la cantidad de temas se basa en el contenido; solo se creará como un tema si se incluye en el contenido que está en el ámbito. Si hay suficiente información y evidencia para el tema, la AI la creará. Los temas de edación son los que pueden ayudar el Administrador de conocimientos y los expertos en la materia. Combinar el conocimiento humano con la inteligencia artificial es la mejor ruta para los temas de calidad. Por lo tanto, si hay temas que prevé que puede crear manualmente en el Centro de temas. Al hacerlo, la inteligencia artificial será una señal segura de la relevancia de ese tema y se identificarán los recursos y las personas que se asociarán con ese tema.
- Use taxonomías existentes para ayudar a planear el tema, ya sea desde SharePoint o desde otro lugar. Las taxonomías existentes suelen incluir términos de la organización, productos, áreas de asunto, entre otros. Los orígenes de los temas también pueden provienen de listas de proyectos, marcadores de búsqueda existentes, entre otros.
