---
title: Introducción a los casos de eDiscovery (Estándar) en Microsoft Purview
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: Describe cómo empezar a usar eDiscovery (Estándar) en Microsoft Purview. Después de asignar permisos de eDiscovery y crear un caso, puede agregar miembros, crear retenciones de exhibición de documentos electrónicos y, a continuación, buscar y exportar contenido relevante para la investigación.
ms.openlocfilehash: 27a7cb97e659b1a35e32d2df76a80ebd3e4da4b9
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851642"
---
# <a name="get-started-with-ediscovery-standard-in-microsoft-purview"></a>Introducción a eDiscovery (Estándar) en Microsoft Purview

Microsoft Purview eDiscovery (estándar) en Microsoft Purview proporciona una herramienta básica de exhibición de documentos electrónicos que las organizaciones pueden usar para buscar y exportar contenido en Microsoft 365 y Office 365. También puede usar eDiscovery (Estándar) para colocar una suspensión de exhibición de documentos electrónicos en ubicaciones de contenido, como buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y Microsoft Teams. No se necesita nada para implementar eDiscovery (Estándar), pero hay algunas tareas de requisitos previos que un administrador de TI y un administrador de eDiscovery deben completar antes de que la organización pueda empezar a usar eDiscovery (Estándar) para buscar, exportar y conservar contenido.

En este artículo se describen los pasos necesarios para configurar eDiscovery (Estándar). Esto incluye garantizar las licencias adecuadas necesarias para acceder a eDiscovery (Estándar) y colocar una suspensión de eDiscovery en ubicaciones de contenido, así como asignar permisos a su equipo de TI, legal e investigación para que puedan acceder a los casos y administrarlos. En este artículo también se proporciona información general de alto nivel sobre el uso de casos para buscar y exportar contenido.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Paso 1: Comprobar y asignar las licencias adecuadas

Las licencias para eDiscovery (Estándar) requieren la suscripción de la organización adecuada y las licencias por usuario.

- **Suscripción a la organización:** Para acceder a eDiscovery (Estándar) en el portal de cumplimiento Microsoft Purview y usar las características de suspensión y exportación, la organización debe tener una suscripción de Exchange Online Plan 2 o Microsoft 365 E3 o Office 365 E3 o superior. Las organizaciones de primera línea de Microsoft 365 deben tener una suscripción A5.

- **Licencias por usuario:** Para colocar una suspensión de eDiscovery en buzones y sitios, se debe asignar a los usuarios una de las licencias siguientes, en función de la suscripción de la organización:

  -  Licencia del plan 2 de Exchange Online

   O
   
  - Una licencia de Microsoft 365 E3 o Office 365 E3 o superior

   O
   
  - licencia de Microsoft 365 Empresa Premium (solo Exchange)
  

   O

  - licencia de Office 365 E1 con una licencia de complemento Exchange Online Plan 2 o Archivado de Exchange Online

   O

  - Microsoft 365 Frontline F5 Compliance or F5 Security & Compliance add-on license  

  Y

  - licencia de Office 365 E1 con una licencia de complemento de Plan 2 o OneDrive para la Empresa Plan 2 de SharePoint Online
  
  Para obtener información sobre cómo asignar licencias, consulte [Asignación de licencias a usuarios](../admin/manage/assign-licenses-to-users.md).

Para obtener información e instrucciones sobre seguridad y cumplimiento:

- Descargue y vea la sección eDiscovery and auditing (Exhibición de documentos electrónicos y auditoría) en la [tabla Comparación de Microsoft 365](https://aka.ms/M365EnterprisePlans).

- Consulte las [instrucciones de Microsoft 365 para el cumplimiento de & de seguridad: descripciones de servicio | Microsoft Docs](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="step-2-assign-ediscovery-permissions"></a>Paso 2: Asignar permisos de exhibición de documentos electrónicos

Para acceder a eDiscovery (Estándar) o agregarse como miembro de un caso de exhibición de documentos electrónicos (Estándar), se deben asignar a un usuario los permisos adecuados. En concreto, se debe agregar un usuario como miembro del grupo de roles administrador de exhibición de documentos electrónicos en el portal de cumplimiento. Los miembros de este grupo de roles pueden crear y administrar casos de exhibición de documentos electrónicos (estándar). Pueden agregar y quitar miembros, colocar una suspensión de eDiscovery en los usuarios, crear y editar búsquedas y exportar contenido desde un caso de exhibición de documentos electrónicos (estándar).

Complete los pasos siguientes para agregar usuarios al grupo de roles del Administrador de exhibición de documentos electrónicos:

1. Vaya al portal de cumplimiento e inicie sesión con las credenciales de una cuenta de administrador en su organización de Microsoft 365 o Office 365.

2. En la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**Permisos**</a> , seleccione el grupo **de roles administrador de exhibición de documentos electrónicos** .

3. En la página desplegable Administrador de exhibición de documentos electrónicos, haga clic en **Editar** junto a la sección **Administrador de exhibición de documentos electrónicos** .

4. En la página **Elegir administrador de exhibición de documentos electrónicos** del Asistente para editar grupos de roles, haga clic en **Elegir administrador de detección**.

5. Haga clic en **Agregar** y seleccione la casilla para todos los usuarios que quiera agregar al grupo de roles.

6. Haga clic en **Agregar** para agregar los usuarios seleccionados y, a continuación, haga clic en **Listo**.

7. Haga clic en **Guardar** para agregar los usuarios al grupo de roles y, a continuación, haga clic en **Cerrar** para completar el paso.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Más información sobre el grupo de roles del Administrador de exhibición de documentos electrónicos

Hay dos subgrupos en el grupo de roles del Administrador de exhibición de documentos electrónicos. La diferencia entre estos subgrupos se basa en el ámbito.

- **Administrador de exhibición de documentos** electrónicos: puede ver y administrar los casos de exhibición de documentos electrónicos (estándar) de los que crean o de los que son miembros. Si otro Administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo Administrador de exhibición de documentos electrónicos como miembro de ese caso, el segundo Administrador de exhibición de documentos electrónicos no podrá ver ni abrir el caso en la página eDiscovery (Estándar) del centro de cumplimiento. En general, la mayoría de las personas de la organización se pueden agregar al subgrupo administrador de exhibición de documentos electrónicos.

- **Administrador de eDiscovery**: puede realizar todas las tareas de administración de casos que un Administrador de exhibición de documentos electrónicos puede realizar. Además, un administrador de exhibición de documentos electrónicos puede:

  - Vea todos los casos que aparecen en la página eDiscovery (Estándar).
  
  - Administre cualquier caso en la organización después de que se agreguen como miembro del caso.

  - Acceda y exporte datos de casos en cualquier caso de la organización.
  
  - Quitar miembros de un caso de eDiscovery. Solo un administrador de eDiscovery puede quitar miembros de un caso. Los usuarios que son miembros del subgrupo administrador de exhibición de documentos electrónicos no pueden quitar miembros de un caso, incluso si el usuario creó el caso.

  Debido a la amplia gama de acceso que tiene que tener una organización, solo unos pocos administradores que sean miembros del subgrupo de administradores de eDiscovery.

Para obtener más información sobre los permisos de eDiscovery y una descripción de cada rol asignado al grupo de roles del Administrador de exhibición de documentos electrónicos, vea [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-ediscovery-standard-case"></a>Paso 3: Crear un caso de exhibición de documentos electrónicos (estándar)

El siguiente paso es crear un caso y empezar a usar eDiscovery (Estándar). Complete los pasos siguientes para crear un caso y agregar miembros. El usuario que crea el caso se agrega automáticamente como miembro.

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento</a> e inicie sesión con las credenciales de una cuenta de usuario a la que se hayan asignado los permisos de exhibición de documentos electrónicos adecuados. Los miembros del grupo de roles Administración de la organización también pueden crear casos de exhibición de documentos electrónicos (estándar).

2. En el panel de navegación izquierdo del portal de cumplimiento, haga clic en **Mostrar todo** y, a continuación, haga clic en **eDiscovery** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2174007" target="_blank">**Core**</a>.

3. En la página **eDiscovery (Estándar),** haga clic en **Crear un caso**.

4. En la página flotante **Nuevo caso** , asigne un nombre (obligatorio) al caso y escriba una descripción opcional. El nombre del caso debe ser único en su organización.

5. Haga clic en **Guardar** para crear el caso.

   El nuevo caso se crea y se muestra en la página eDiscovery (estándar). Es posible que tenga que hacer clic en **Actualizar** para mostrar el nuevo caso.

## <a name="step-4-optional-add-members-to-a-ediscovery-standard-case"></a>Paso 4 (opcional): Agregar miembros a un caso de exhibición de documentos electrónicos (estándar)

Si crea un caso en el paso 3 y es la única persona que usará el caso, no tendrá que realizar este paso. Puede empezar a usar el caso para crear retenciones de eDiscovery, buscar contenido y exportar resultados de búsqueda. Realice este paso si desea proporcionar a otros usuarios (o grupos de roles) acceso al caso.

1. En la página **eDiscovery (Estándar)** del portal de cumplimiento, haga clic en el nombre del caso al que desea agregar miembros.

2. En la página principal del caso, seleccione la pestaña **Configuración** y, a continuación, seleccione **Acceso & permisos**.

3. En la página flotante **Access & permissions (Permisos de access &** ), en **Miembros**, haga clic en **Agregar** para agregar miembros al caso.

    También puede elegir agregar grupos de roles como miembros de un caso. En **Grupos de roles**, haga clic en **Agregar**. Solo puede asignar los grupos de roles de los que es miembro a un caso. Esto se debe a que los grupos de roles controlan quién puede asignar miembros a un caso de exhibición de documentos electrónicos.

4. En la lista de personas o grupos de roles que se pueden agregar como miembros del caso, haga clic a la izquierda del nombre de las personas (o grupos de roles) que desea agregar. Si tiene una lista grande de personas o grupos de roles que se pueden agregar como miembros, use el cuadro **Buscar** para buscar una persona o grupo de roles específico en la lista.
  
5. Después de seleccionar las personas o grupos de roles que se van a agregar como miembros del caso, haga clic en **Guardar** para guardar los nuevos miembros o grupos de roles.

> [!IMPORTANT]
>
>- Si se agrega o quita un rol de un grupo de roles que ha agregado como miembro de un caso, el grupo de roles se quitará automáticamente como miembro del caso (o en cualquier caso, el grupo de roles es miembro de ). El motivo es proteger su organización frente a proporcionar permisos adicionales involuntariamente a los miembros de un caso. De forma similar, si se elimina un grupo de roles, se quitará de todos los casos de los que era miembro. Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases). 
>
>- Como se explicó anteriormente, solo un administrador de exhibición de documentos electrónicos puede quitar miembros de un caso. Los usuarios que son miembros del subgrupo administrador de exhibición de documentos electrónicos no pueden quitar miembros de un caso, incluso si el usuario creó el caso.
>

## <a name="explore-the-ediscovery-standard-workflow"></a>Exploración del flujo de trabajo de eDiscovery (estándar)

Para empezar a usar eDiscovery (Estándar), este es un flujo de trabajo sencillo de creación de retenciones de exhibición de documentos electrónicos para personas de interés, búsqueda de contenido relevante para la investigación y, a continuación, exportación de esos datos para su posterior revisión. En cada uno de estos pasos, también resaltaremos algunas funciones de exhibición de documentos electrónicos extendidas (estándar) que puede explorar.

![Flujo de trabajo de eDiscovery (estándar).](../media/CoreEdiscoveryWorkflow.png)

1. **[Cree una suspensión de eDiscovery](create-ediscovery-holds.md)**. El primer paso después de crear un caso es colocar una suspensión (también denominada *suspensión de exhibición de documentos electrónicos*) en las ubicaciones de contenido de las personas de interés en la investigación. Las ubicaciones de contenido incluyen buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y los buzones y sitios asociados a Microsoft Teams y Grupos de Microsoft 365. Aunque este paso es opcional, la creación de una suspensión de exhibición de documentos electrónicos conserva el contenido que puede ser relevante para el caso durante la investigación. Al crear una suspensión de eDiscovery, puede conservar todo el contenido en ubicaciones de contenido específicas o puede crear una suspensión basada en consultas para conservar solo el contenido que coincida con una consulta de suspensión. Además de conservar el contenido, otra buena razón para crear retenciones de exhibición de documentos electrónicos es buscar rápidamente las ubicaciones de contenido en espera (en lugar de tener que seleccionar cada ubicación para buscar) al crear y ejecutar búsquedas en el paso siguiente. Después de completar la investigación, puede liberar cualquier retención que haya creado.

2. **[Busque contenido](search-for-content-in-core-ediscovery.md)**. Después de crear retenciones de eDiscovery, use la herramienta de búsqueda integrada para buscar en las ubicaciones de contenido en espera. También puede buscar en otras ubicaciones de contenido datos que puedan ser relevantes para el caso. Puede crear y ejecutar búsquedas diferentes asociadas al caso. Las palabras clave, las propiedades y las condiciones se usan para [crear consultas de búsqueda](keyword-queries-and-search-conditions.md) que devuelven resultados de búsqueda con los datos que probablemente sean relevantes para el caso. También puede:

   - Vea las estadísticas de búsqueda que pueden ayudarle a refinar una consulta de búsqueda para restringir los resultados.

   - Obtenga una vista previa de los resultados de la búsqueda para comprobar rápidamente si se encuentran los datos pertinentes.

   - Revise una consulta y vuelva a ejecutar la búsqueda.

3. **[Exporte y descargue los resultados de la búsqueda](export-content-in-core-ediscovery.md)**. Después de buscar y buscar datos relevantes para la investigación, puede exportarlos fuera de Office 365 para que los revisen personas ajenas al equipo de investigación. La exportación de datos es un proceso de dos pasos. El primer paso es exportar los resultados de una búsqueda en el caso de Office 365. Para ello, copie los resultados de una búsqueda en una ubicación de Azure Storage proporcionada por Microsoft. El siguiente paso es usar la herramienta eDiscovery Export para descargar el contenido en un equipo local. Además de los archivos de datos exportados, el paquete de exportación contiene un informe de exportación, un informe de resumen y un informe de errores.
