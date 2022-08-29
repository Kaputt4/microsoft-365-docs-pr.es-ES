---
title: Implementar equipos a escala para los trabajadores de primera línea en Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo implementar equipos a escala para los trabajadores de primera línea de su organización.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 9a06b695d6e9cffe03ed2a42590c1489f3678056
ms.sourcegitcommit: 6f565d9e0f91ebc76fd13d7005619531391ab5f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2022
ms.locfileid: "67439594"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Implementar equipos a escala para los trabajadores de primera línea en Microsoft Teams

> [!NOTE]
> Esta característica está disponible actualmente en versión preliminar pública. Si desea participar, póngase en contacto con nosotros en [dscale@microsoft.com](mailto:dscale@microsoft.com).

## <a name="overview"></a>Información general
 
Su organización puede tener una gran cantidad de equipos empleados para impulsar la comunicación y la colaboración entre los trabajadores de primera línea, que se distribuyen entre diferentes tiendas, ubicaciones y roles. Actualmente, no hay una solución sencilla para implementar, configurar y administrar estos equipos y usuarios a escala.

Estamos creando una solución para permitir que los administradores implementen y administren equipos a escala.

Esta es una introducción a las funciones disponibles hoy en día para crear y administrar un gran número de equipos a la vez y lo que planeamos para el futuro próximo.

||Disponible hoy |Más adelante en 2022  |
|---------|---------|---------|
|**Número de equipos que puede crear por lote**|Hasta 100 GB |Hasta 500|
|**Número de usuarios que puede agregar por equipo**|Hasta 25|Hasta 25|

La implementación de equipos a escala le permite:

- Crear equipos mediante plantillas predefinidas o sus propias plantillas personalizadas.
- Agregue usuarios a los equipos como propietarios o miembros.
- Administre los equipos a escala agregando o quitando usuarios de los equipos existentes.
- Reciba una notificación por correo electrónico, incluidos la finalización, el estado y los errores (si los hubiera). Puede optar por notificar hasta cinco personas sobre el estado de cada lote de equipos que implemente. Los propietarios y miembros del equipo reciben una notificación automática cuando se agregan a un equipo.

## <a name="how-to-deploy-teams-at-scale"></a>Cómo implementar equipos a escala

> [!NOTE]
> Antes de implementar los equipos, asegúrese de que todos los propietarios de los equipos cuenten con una licencia de Teams.

Siga estos pasos para implementar un gran número de equipos a la vez.

### <a name="step-1-prepare-your-csv-files"></a>Paso 1: Preparación de los archivos CSV

Tendrá que crear dos archivos CSV para cada lote de equipos que implemente:

- **Un archivo CSV que define los equipos que va a crear**. Este archivo debe contener estas columnas indispensablemente, en el siguiente orden, empezando por la primera columna:

    |Nombre de columna  |Descripción  |
    |---------|---------|
    |**Nombre del equipo**|El nombre del equipo.|
    |**Id. de equipo existente**|Si va a agregar o quitar usuarios de un equipo existente, especifique el Id. del equipo.|
    |**Visibility**|Si el equipo es público (cualquier persona de su organización puede unirse) o privado (los usuarios necesitan la aprobación de los propietarios del equipo para unirse). Las opciones son **Pública** y **Privada**.|
    |**Id. de plantilla de equipo**|Si va a crear un equipo a partir de una plantilla predefinida o personalizada, especifique el Id. de plantilla de equipo. Consulte [Introducción a las plantillas de equipo en el Centro de administración de Teams](/microsoftteams/get-started-with-teams-templates-in-the-admin-console) para obtener una lista de plantillas predefinidas e Id. de equipo, Si desea usar la plantilla de equipo predeterminada estándar, deje esto en blanco.|

- **Un archivo CSV que asigna los usuarios que va a agregar a cada equipo**. Este archivo debe contener estas columnas indispensablemente, en el siguiente orden, empezando por la primera columna:

    |Nombre de columna  |Descripción  |
    |---------|---------|
    |**Nombre completo del usuario**|El nombre para mostrar del usuario.|
    |**UPN o Id. de usuario**|El nombre principal del usuario (UPN) o Id. del usuario. Por ejemplo, averyh@contoso.com.|
    |**Nombre del equipo**|El nombre del equipo.|
    |**ActionType**|Independientemente de si va a agregar o quitar al usuario del equipo. Las opciones son **AddMember** y **RemoveMember**.|
    |**Propietario o miembro**|Si el usuario es propietario del equipo o miembro del equipo. Las opciones son **Propietario** y **Miembro**.|

#### <a name="examples"></a>Ejemplos

Use los siguientes ejemplos para ayudarle a crear los archivos CSV. Aquí hemos llamado a los archivos, Teams.csv y Users.csv.

**Teams.csv**

|Nombre del equipo|Id. de equipo existente|Visibilidad|Id. de plantilla de equipo|
|---------|---------|---------|---------|
|Tienda Contoso 1||Public|com.microsoft.teams.template.retailStore|
|Tienda Contoso 2||Public|com.microsoft.teams.template.retailStore|
|Tienda Contoso 3||Public|com.microsoft.teams.template.retailStore|
|Tienda Contoso 4||Public|com.microsoft.teams.template.retailStore|
|Tienda Contoso 5||Public|com.microsoft.teams.template.ManageAProject|
|Tienda Contoso 6||Public|com.microsoft.teams.template.ManageAProject|
|Tienda Contoso 7||Public||
|Tienda Contoso 8||Private|com.microsoft.teams.template.OnboardEmployees|
|Tienda Contoso 9||Private|com.microsoft.teams.template.OnboardEmployees|
|Tienda Contoso 10||Private|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|Nombre completo del usuario |UPN o Id. de usuario|Nombre del equipo|ActionType|Propietario o miembro|
|---------|---------|---------|---------|---------|
|Avery Howard|averyh@contoso.com|Tienda Contoso 1|AddMember|Propietario|
|Casey Jensen|caseyj@contoso.com|Tienda Contoso 2|AddMember|Propietario|
|Jessie Irwin|jessiei@contoso.com|Tienda Contoso 3|AddMember|Propietario|
|Manjeet Bhatia|manjeetb@contoso.com|Tienda Contoso 4|AddMember|Propietario|
|Mikaela Lee|mikaelal@contoso.com|Tienda Contoso 5|AddMember|Propietario|
|Morgan Conners|morganc@contoso.com|Tienda Contoso 6|AddMember|Member|
|Oscar Ward|oscarw@contoso.com|Tienda Contoso 7|AddMember|Member|
|Rene Pelletier|renep@contoso.com|Tienda Contoso 8|AddMember|Member|
|Sydney Mattos|sydneym@contoso.com|Tienda Contoso 9|AddMember|Member|
|Violet Martinez|violetm@contoso.com|Tienda Contoso 10|AddMember|Member|

### <a name="step-2-deploy-your-teams"></a>Paso 2: Implementar el sitio aislado

Ahora que ha creado los archivos CSV, está listo para configurar el entorno e implementar los equipos.

Use el ```New-CsBatchTeamsDeployment``` cmdlet para enviar un lote de equipos para crear. Se genera un Id. de orquestación para cada lote. A continuación, puede usar el ```Get-CsBatchTeamsDeployment``` cmdlet para realizar un seguimiento del progreso y el estado de cada lote.

1. Instale PowerShell versión 7 o posterior. Para obtener instrucciones paso a paso, consulte [Instalar PowerShell en Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Ejecute PowerShell en modo de administrador.
1. Ejecute lo siguiente para desinstalar cualquier módulo de PowerShell de Teams instalado anteriormente.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Si recibe un mensaje de error, significa que ya está establecido. Vaya al paso siguiente.
1. Descargue e instale la [versión preliminar más reciente del módulo de PowerShell de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Debe ejecutar la versión 4.3.1 (versión preliminar) o una versión preliminar posterior.  

1. Ejecute lo siguiente para conectarse a Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Cuando se le solicite, inicie sesión con sus credenciales de administrador.

1. Ejecute lo siguiente para obtener una lista de los comandos en el módulo de PowerShell de Teams.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Compruebe que ```New-CsBatchTeamsDeployment``` y ```Get-CsBatchTeamsDeployment``` aparecen en la lista.

1. Ejecute lo siguiente para implementar un lote de equipos. En este comando, especificará la ruta de acceso a los archivos CSV y las direcciones de correo electrónico de hasta cinco destinatarios para notificar sobre esta implementación.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    Por ejemplo:

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    Los destinatarios recibirán notificaciones por correo electrónico sobre el estado de la implementación. El correo electrónico contiene el Id. de orquestación del lote que envió y los errores que puedan haberse producido.

1. Ejecute lo siguiente para comprobar el estado del lote que envió.

    ```powershell
    Get-CsBatchTeamsDeployment -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Enviarnos comentarios

Valoramos sus comentarios. Facilidad de uso, confiabilidad, rendimiento&mdash;¡lo agradecemos todo!

Email [dscale@microsoft.com](mailto:dscale@microsoft.com) e incluya el Id. de orquestación y el archivo de error, si lo tiene.

## <a name="related-articles"></a>Artículos relacionados

- [Descripción de PowerShell para Teams](/microsoftteams/teams-powershell-overview)
