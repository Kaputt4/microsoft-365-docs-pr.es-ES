---
title: Implementación de Teams a escala para trabajadores de primera línea
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Obtenga información sobre cómo implementar Teams a escala para los trabajadores de primera línea de su organización.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: b20933e98870ffaca7dee5c46922cec49dbaed13
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68535958"
---
# <a name="deploy-teams-at-scale-for-frontline-workers"></a>Implementación de Teams a escala para trabajadores de primera línea

## <a name="overview"></a>Información general

¿Su organización usa un gran número de equipos para impulsar la comunicación y la colaboración entre los trabajadores de primera línea? Este artículo es para usted si necesita crear y administrar equipos a escala.

Puede usar PowerShell para implementar hasta 500 equipos y agregar hasta 25 usuarios por equipo a la vez. También puede agregar y quitar usuarios de equipos existentes a escala. Use esta solución para satisfacer las necesidades de escala de su organización y reducir significativamente el tiempo de implementación.

La implementación de Teams a escala le permite:

- Crear equipos mediante plantillas predefinidas o sus propias plantillas personalizadas.
- Agregue usuarios a los equipos como propietarios o miembros.
- Administre los equipos a escala agregando o quitando usuarios de los equipos existentes.
- Reciba una notificación por correo electrónico, incluidos la finalización, el estado y los errores (si los hubiera). Puede optar por notificar hasta cinco personas sobre el estado de cada lote de equipos que implemente. Los propietarios y miembros del equipo reciben una notificación automática cuando se agregan a un equipo.

En este artículo se explica cómo implementar Teams a escala.

:::image type="content" source="media/deploy-teams-at-scale.png" alt-text="Introducción a los pasos para implementar Teams a escala.":::

## <a name="set-up-and-deploy-your-teams"></a>Configuración e implementación de equipos

> [!IMPORTANT]
> Los propietarios del equipo deben tener una licencia de Teams. Antes de usar estos pasos para implementar los equipos, asegúrese de que todos los propietarios de los equipos tienen una licencia.

Siga estos pasos para implementar hasta 500 equipos a la vez.

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

### <a name="step-2-set-up-your-environment"></a>Paso 2: Configuración del entorno

Siga estos pasos para instalar y conectarse a la versión más reciente del módulo de PowerShell de Teams.

1. Instale PowerShell versión 7 o posterior. Para obtener instrucciones paso a paso, consulte [Instalar PowerShell en Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Ejecute PowerShell en modo de administrador.
1. Ejecute lo siguiente para desinstalar cualquier módulo de PowerShell de Teams instalado anteriormente.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Si recibe un mensaje de error, significa que ya está establecido. Vaya al paso siguiente.
1. Descargue e instale la [versión más reciente del módulo de PowerShell de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Debe ejecutar la versión 4.7.0 (versión preliminar) o una versión posterior.  

1. Ejecute lo siguiente para conectarse a Teams.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Cuando se le solicite, inicie sesión con sus credenciales de administrador.

1. Ejecute lo siguiente para obtener una lista de los comandos en el módulo de PowerShell de Teams.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Compruebe que ```New-CsBatchTeamsDeployment``` y ```Get-CsBatchTeamsDeploymentStatus``` aparecen en la lista.

### <a name="step-3-deploy-your-teams"></a>Paso 3: Implementación de los equipos

Ahora que ha creado los archivos CSV y configurado el entorno, está listo para implementar los equipos.

Use el cmdlet [New-CsBatchTeamsDeployment](/powershell/module/teams/New-CsBatchTeamsDeployment) para enviar un lote de equipos para crear. Se genera un Id. de orquestación para cada lote. Después, puede usar el cmdlet [Get-CsBatchTeamsDeploymentStatus](/powershell/module/teams/Get-CsBatchTeamsDeploymentstatus) para realizar un seguimiento del progreso y el estado de cada lote.

1. Ejecute lo siguiente para implementar un lote de equipos. En este comando, especificará la ruta de acceso a los archivos CSV y las direcciones de correo electrónico de hasta cinco destinatarios para notificar sobre esta implementación.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    Los destinatarios recibirán notificaciones por correo electrónico sobre el estado de la implementación. El correo electrónico contiene el Id. de orquestación del lote que envió y los errores que puedan haberse producido.

    Por ejemplo:

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

1. Ejecute lo siguiente para comprobar el estado del lote que envió.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="related-articles"></a>Artículos relacionados

- [New-CsBatchTeamsDeployment](/powershell/module/teams/New-CsBatchTeamsDeployment)
- [Get-CsBatchTeamsDeploymentStatus](/powershell/module/teams/Get-CsBatchTeamsDeploymentstatus)
- [Descripción de PowerShell para Teams](/microsoftteams/teams-powershell-overview)
- [Obtenga información sobre dónde empezar con una implementación de primera línea](flw-deploy-overview.md)
