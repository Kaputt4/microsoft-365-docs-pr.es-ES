---
title: Introducción a los casos principales de exhibición de documentos electrónicos en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Describe cómo empezar a usar eDiscovery principal en Microsoft 365. Después de asignar permisos de exhibición de documentos electrónicos y crear un caso, puede agregar miembros, crear retenciones de exhibición de documentos electrónicos y, a continuación, buscar y exportar contenido relevante para la investigación.
ms.openlocfilehash: 9466b2e3268a447a4008363e88290d4d02558c76
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341477"
---
# <a name="get-started-with-core-ediscovery-in-microsoft-365"></a>Introducción a la exhibición de documentos electrónicos principal en Microsoft 365

La exhibición de documentos electrónicos principal en Microsoft 365 proporciona una herramienta básica de exhibición de documentos electrónicos que las organizaciones pueden usar para buscar y exportar contenido en Microsoft 365 y Office 365. También puede usar eDiscovery principal para colocar una retención de exhibición de documentos electrónicos en ubicaciones de contenido, como buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y Microsoft Teams. No se necesita nada para implementar eDiscovery principal, pero hay algunas tareas de requisitos previos que un administrador de TI y un administrador de exhibición de documentos electrónicos deben completar antes de que su organización pueda empezar a usar eDiscovery principal para buscar, exportar y conservar contenido.

En este artículo se analizan los pasos necesarios para configurar la exhibición de documentos electrónicos principales. Esto incluye garantizar la licencia adecuada necesaria para tener acceso a eDiscovery principal y colocar una retención de exhibición de documentos electrónicos en ubicaciones de contenido, así como asignar permisos a su equipo de IT, legales e investigación para que puedan acceder y administrar casos. En este artículo también se proporciona información general de alto nivel sobre el uso de casos para buscar y exportar contenido.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Paso 1: Comprobar y asignar licencias adecuadas

Las licencias para la exhibición de documentos electrónicos principales requieren la suscripción de la organización adecuada y las licencias por usuario.

- **Suscripción a la organización:** Para tener acceso a la exhibición de documentos electrónicos principal en el centro de cumplimiento de Centro de cumplimiento de Microsoft 365 o Office 365 Security & y usar las características de retención y exportación, la organización debe tener una suscripción Microsoft 365 E3 o Office 365 E3 o superior.

- **Licencias por usuario:** Para colocar una retención de exhibición de documentos electrónicos en buzones y sitios, se debe asignar a un usuario una de las siguientes licencias, según la suscripción de la organización:

  - Una Microsoft 365 E3 o Office 365 E3 o posterior

   O

  - Office 365 E1 con una licencia Exchange Online plan 2 o Archivado de Exchange Online de complementos

  Y

  - Office 365 E1 licencia con una SharePoint de complemento de Plan 2 o OneDrive para la Empresa plan 2
  
  Para obtener información sobre cómo asignar licencias, vea [Asignar licencias a usuarios.](../admin/manage/assign-licenses-to-users.md)

Para obtener información sobre las licencias:

- Descargue y vea la solución "Descubrir & Responder" en el Microsoft 365 comparación de licencias [de cumplimiento.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

- Vea la [descripción del servicio & centro de seguridad y cumplimiento](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="step-2-assign-ediscovery-permissions"></a>Paso 2: Asignar permisos de exhibición de documentos electrónicos

Para obtener acceso a eDiscovery principal o agregarse como miembro de un caso de exhibición de documentos electrónicos principales, se deben asignar a un usuario los permisos adecuados. Específicamente, un usuario debe agregarse como miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de Office 365 seguridad & cumplimiento. Los miembros de este grupo de roles pueden crear y administrar casos principales de exhibición de documentos electrónicos. Pueden agregar y quitar miembros, colocar una retención de exhibición de documentos electrónicos en los usuarios, crear y editar búsquedas y exportar contenido desde un caso de exhibición de documentos electrónicos principal.

Siga estos pasos para agregar usuarios al grupo de roles administrador de exhibición de documentos electrónicos:

1. Vaya a e inicie sesión con las credenciales de una cuenta de administrador en su <https://compliance.microsoft.com/permissions> Microsoft 365 o Office 365 organización.

2. En la **página Permisos,** seleccione el grupo de **roles** Administrador de exhibición de documentos electrónicos.

3. En la página desplegable administrador de exhibición de documentos electrónicos, haga clic **en Editar** junto a la sección Administrador de **exhibición de documentos** electrónicos.

4. En la página **Elegir administrador de exhibición** de documentos electrónicos en el asistente para editar grupos de roles, haga clic **en Elegir administrador de detección.**

5. Haga **clic en** Agregar y seleccione la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Haga **clic en** Agregar para agregar los usuarios seleccionados y, a continuación, haga clic en **Listo**.

7. Haga **clic en** Guardar para agregar los usuarios al grupo de roles y, a continuación, haga clic **en** Cerrar para completar el paso.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Más información sobre el grupo de roles administrador de exhibición de documentos electrónicos

Hay dos subgrupos en el grupo de roles administrador de exhibición de documentos electrónicos. La diferencia entre estos subgrupos se basa en el ámbito.

- **Administrador de exhibición de documentos** electrónicos: puede ver y administrar los casos principales de exhibición de documentos electrónicos de los que crean o son miembros. Si otro administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo administrador de exhibición de documentos electrónicos como miembro de ese caso, el segundo administrador de exhibición de documentos electrónicos no podrá ver ni abrir el caso en la página eDiscovery principal del centro de cumplimiento. En general, la mayoría de las personas de la organización se pueden agregar al subgrupo del Administrador de exhibición de documentos electrónicos.

- **Administrador de exhibición de documentos electrónicos:** puede realizar todas las tareas de administración de casos que un administrador de exhibición de documentos electrónicos puede realizar. Además, un administrador de exhibición de documentos electrónicos puede:

  - Ver todos los casos que aparecen en la página eDiscovery principal.
  
  - Administre cualquier caso en la organización después de que se agreguen como miembro del caso.

  - Acceda y exporte datos de casos en cualquier caso de la organización.

  Debido a la amplia gama de acceso que tiene que tener una organización, solo unos pocos administradores que sean miembros del subgrupo de administradores de eDiscovery.

Para obtener más información acerca de los permisos de exhibición de documentos electrónicos y una descripción de cada función asignada al grupo de roles administrador de exhibición de documentos electrónicos, vea Asignar permisos de exhibición [de documentos electrónicos](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-core-ediscovery-case"></a>Paso 3: Crear un caso de exhibición de documentos electrónicos principal

El siguiente paso es crear un caso y empezar a usar eDiscovery principal. Complete los pasos siguientes para crear un caso y agregar miembros. El usuario que crea el caso se agrega automáticamente como miembro.

1. Vaya a e inicie sesión con las credenciales de una cuenta de usuario a la que se han asignado [https://compliance.microsoft.com](https://compliance.microsoft.com) los permisos de exhibición de documentos electrónicos adecuados. Los miembros del grupo de roles Administración de la organización también pueden crear casos principales de exhibición de documentos electrónicos.

2. En el panel de navegación izquierdo de la Centro de cumplimiento de Microsoft 365, haga clic en Mostrar todo y, a continuación, haga clic en **Exhibición de documentos electrónicos > Core**.

3. En la **página EDiscovery principal,** haga clic **en Crear un caso**.

4. En la **página desplegable** Nuevo caso, asigne al caso un nombre (obligatorio) y, a continuación, escriba una descripción opcional. El nombre del caso debe ser único en la organización.

5. Haga **clic en** Guardar para crear el caso.

   El nuevo caso se crea y se muestra en la página eDiscovery principal. Es posible que tenga que hacer clic **en Actualizar** para mostrar el nuevo caso.

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Paso 4 (opcional): Agregar miembros a un caso de exhibición de documentos electrónicos principal

Si crea un caso en el paso 3 y es la única persona que usará el caso, no tiene que realizar este paso. Puede empezar a usar el caso para crear retenciones de exhibición de documentos electrónicos, buscar contenido y exportar resultados de búsqueda. Realice este paso si desea proporcionar a otros usuarios (o grupos de roles) acceso al caso.

1. En la **página Exhibición** de documentos electrónicos principal de la Centro de cumplimiento de Microsoft 365, haga clic en el nombre del caso al que desea agregar miembros.

2. En la página principal del caso, seleccione la **Configuración** y, a continuación, **seleccione Access & permisos**.

3. En la **página desplegable & permisos** de acceso, en **Miembros,** haga clic en **Agregar** para agregar miembros al caso.

    También puede elegir agregar grupos de roles como miembros de un caso. En **Grupos de roles,** haga clic **en Agregar**. Solo puede asignar los grupos de roles de los que es miembro a un caso. Esto se debe a que los grupos de roles controlan quién puede asignar miembros a un caso de exhibición de documentos electrónicos.

4. En la lista de personas o grupos de roles que se pueden agregar como miembros del caso, haga clic a la izquierda del nombre de las personas (o grupos de roles) que desee agregar. Si tiene una lista grande de personas o grupos de  roles que pueden agregarse como miembros, use el cuadro Buscar para buscar una persona o un grupo de roles específicos en la lista.
  
5. Después de seleccionar las personas o grupos de roles  que se agregarán como miembros del caso, haga clic en Guardar para guardar los nuevos miembros o grupos de roles.

## <a name="explore-the-core-ediscovery-workflow"></a>Explorar el flujo de trabajo de eDiscovery principal

Para empezar a usar la exhibición de documentos electrónicos principal, este es un flujo de trabajo sencillo de crear retenciones de exhibición de documentos electrónicos para personas de interés, buscar contenido relevante para la investigación y, a continuación, exportar los datos para su revisión. En cada uno de estos pasos, también destacaremos algunas funciones de exhibición de documentos electrónicos principales extendidas que puede explorar.

![Flujo de trabajo de exhibición de documentos electrónicos principal](../media/CoreEdiscoveryWorkflow.png)

1. **[Crear una retención de exhibición de documentos electrónicos](create-ediscovery-holds.md)**. El primer paso después de crear un caso es colocar una retención (también denominada retención de *exhibición* de documentos electrónicos) en las ubicaciones de contenido de las personas de interés en la investigación. Las ubicaciones de contenido incluyen Exchange buzones de correo, SharePoint, cuentas de OneDrive y los buzones y sitios asociados con Microsoft Teams y Office 365 grupos. Aunque este paso es opcional, la creación de una retención de exhibición de documentos electrónicos conserva el contenido que puede ser relevante para el caso durante la investigación. Al crear una retención de exhibición de documentos electrónicos, puede conservar todo el contenido en ubicaciones de contenido específicas o puede crear una retención basada en consultas para conservar solo el contenido que coincida con una consulta de retención. Además de conservar el contenido, otra buena razón para crear retenciones de exhibición de documentos electrónicos es buscar rápidamente en las ubicaciones de contenido en espera (en lugar de tener que seleccionar cada ubicación para buscar) al crear y ejecutar búsquedas en el paso siguiente. Después de completar la investigación, puede liberar cualquier retención que haya creado.

2. **[Buscar contenido](search-for-content-in-core-ediscovery.md)**. Después de crear retenciones de exhibición de documentos electrónicos, use la herramienta de búsqueda integrada para buscar en las ubicaciones de contenido en espera. También puede buscar en otras ubicaciones de contenido datos que puedan ser relevantes para el caso. Puede crear y ejecutar distintas búsquedas asociadas con el caso. Se usan palabras clave, propiedades [](keyword-queries-and-search-conditions.md) y condiciones para crear consultas de búsqueda que devuelvan resultados de búsqueda con los datos que probablemente sean relevantes para el caso. También puede:

   - Ver estadísticas de búsqueda que pueden ayudarle a refinar una consulta de búsqueda para restringir los resultados.

   - Obtenga una vista previa de los resultados de la búsqueda para comprobar rápidamente si se encuentran los datos relevantes.

   - Revise una consulta y vuelva a ejecutar la búsqueda.

3. **[Exportar y descargar resultados de búsqueda](export-content-in-core-ediscovery.md)**. Después de buscar y encontrar datos relevantes para la investigación, puede exportarlos fuera de Office 365 para que los usuarios externos al equipo de investigación lo revisen. La exportación de datos es un proceso de dos pasos. El primer paso es exportar los resultados de una búsqueda en el caso de que no Office 365. Para ello, copie los resultados de una búsqueda en una ubicación Azure Storage Microsoft. El siguiente paso es usar la herramienta de exportación de exhibición de documentos electrónicos para descargar el contenido en un equipo local. Además de los archivos de datos exportados, el contenido del paquete de exportación también contiene un informe de exportación, un informe de resumen y un informe de errores.
