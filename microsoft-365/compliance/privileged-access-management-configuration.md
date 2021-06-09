---
title: Introducción a la administración del acceso con privilegios
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Use este artículo para obtener más información sobre cómo habilitar y configurar la administración de acceso con privilegios en Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126537"
---
# <a name="get-started-with-privileged-access-management"></a>Introducción a la administración del acceso con privilegios

Este tema le guía a través de la habilitación y configuración de la administración de acceso con privilegios en su organización. Puede usar el Centro de administración Microsoft 365 o Exchange PowerShell de administración para administrar y usar el acceso con privilegios.

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar con la administración de acceso con privilegios, debe confirmar la [Microsoft 365 suscripción y](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) los complementos. Para obtener acceso y usar la administración de acceso con privilegios, la organización debe tener una de las siguientes suscripciones o complementos:

- Microsoft 365 E5 suscripción (versión de pago o de prueba)
- Microsoft 365 E3 (o Office 365 de E3 + Enterprise de movilidad y seguridad E3) + Cumplimiento de Microsoft 365 E5 complemento
- Cualquier Microsoft 365, Office 365, Exchange, SharePoint o OneDrive para la Empresa suscripción + el complemento de administración de riesgos Microsoft 365 E5 Insider  
- Microsoft 365 Suscripción A5 (versión de pago o de prueba)
- Microsoft 365 Suscripción A3 (o Office 365 A3 suscripción + Enterprise de movilidad y seguridad A3) + el complemento de cumplimiento de Microsoft A5
- Cualquier suscripción Microsoft 365, Office 365, Exchange, SharePoint o OneDrive para Educación + el complemento de administración de riesgos Microsoft 365 A5 Insider
- Office 365 Enterprise Suscripción E5 (versión de pago o de prueba)
- Office 365 Enterprise Suscripción E3 + Cumplimiento avanzado de Office 365 complemento (ya no está disponible para las nuevas suscripciones, vea la nota)

Los usuarios que envíen y respondan a solicitudes de administración de acceso con privilegios deben tener asignada una de las licencias anteriores.

>[!IMPORTANT]
>Cumplimiento avanzado de Office 365 ya no se vende como una suscripción independiente. Cuando expiran las suscripciones actuales, los clientes deben realizar la transición a una de las suscripciones anteriores, que contienen las mismas o adicionales características de cumplimiento.

Si no tiene un plan de Office 365 Enterprise E5 existente y desea probar la administración de acceso con privilegios, [](https://www.microsoft.com/microsoft-365/enterprise) puede agregar [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) a la suscripción Office 365 existente o registrarse para una prueba de Microsoft 365 Enterprise E5.

## <a name="enable-and-configure-privileged-access-management"></a>Habilitar y configurar la administración de acceso con privilegios

Siga estos pasos para configurar y usar el acceso con privilegios en su organización:

- [Paso 1: Crear un grupo de aprobadores](privileged-access-management-configuration.md#step1)

    Antes de empezar a usar el acceso con privilegios, determine quiénes necesitan la autoridad de aprobaciones para las solicitudes entrantes de acceso a tareas con privilegios o privilegios elevados. Cualquier usuario que forme parte del grupo de aprobadores podrá aprobar las solicitudes de acceso. Este grupo se habilita mediante la creación de un grupo de seguridad habilitado para correo en Office 365.

- [Paso 2: Habilitar el acceso con privilegios](privileged-access-management-configuration.md#step2)

    El acceso con privilegios debe habilitarse explícitamente en Office 365 con el grupo predeterminado de aprobadores, incluido el conjunto de cuentas del sistema que desee excluir del control de acceso de Privileged Access Management.

- [Paso 3: Crear una directiva de acceso](privileged-access-management-configuration.md#step3)

    La creación de una directiva de aprobación le permite definir requisitos de aprobación específicos para cada tarea. Las opciones de tipo de aprobación son **Automática** o **Manual**.

- [Paso 4: Enviar o aprobar solicitudes de acceso con privilegios](privileged-access-management-configuration.md#step4)

    Tras habilitar el acceso con privilegios, este requiere la aprobación de toda tarea que tenga una directiva de aprobación definida asociada a ella. En el caso de las tareas incluidas en una directiva de aprobación, los usuarios deberán solicitar y obtener la aprobación de acceso para contar con los permisos necesarios para ejecutar la tarea.

Una vez que se concede la aprobación, el usuario que realizó la solicitud puede ejecutar la tarea prevista y el acceso con privilegios autorizará y ejecutará la tarea en nombre del usuario. La aprobación será válida durante el período de tiempo solicitado (la duración predeterminada es de cuatro horas), a lo largo del cual el solicitante puede ejecutar la tarea prevista varias veces. Todas esas ejecuciones se registran y pasan a estar disponibles para las auditorías de seguridad y cumplimiento. 

>[!NOTE]
>Si desea usar PowerShell de administración de Exchange para habilitar y configurar el acceso con privilegios, siga los pasos de Conectar para Exchange Online PowerShell mediante la autenticación [multifactor](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) para conectarse Exchange Online PowerShell con sus credenciales Office 365. No es necesario habilitar la autenticación multifactor para que la organización use los pasos necesarios para habilitar el acceso con privilegios al conectarse Exchange Online PowerShell. La conexión con la autenticación multifactor crea un token de OAuth que usa el acceso con privilegios para firmar las solicitudes.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Paso 1: Crear un grupo de aprobadores

1. Inicie sesión en el [Microsoft 365 de administración](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de su organización.

2. En el Centro de administración, vaya a **Grupos**  >  **Agregar un grupo**.

3. Seleccione **grupo de seguridad habilitado para correo** y,  a continuación, complete los campos **Nombre,** Dirección de **correo electrónico** del grupo y Descripción del nuevo grupo.

4. Guarde el grupo.  La configuración completa del grupo y su aparición en el Centro de administración de Microsoft 365 pueden tardar unos minutos.

5. Seleccione el grupo del nuevo aprobador y **seleccione Editar** para agregar usuarios al grupo.

6. Guarde el grupo.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Paso 2: Habilitar el acceso con privilegios

### <a name="in-the-microsoft-365-admin-center"></a>En el Centro Microsoft 365 administración

1. Inicie sesión en el [Centro Microsoft 365 administración](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de su organización.

2. En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.

3. Habilite el **control Requerir aprobaciones para tareas con privilegios.**

4. Asigne el grupo del aprobador que creó en el paso 1 como **grupo Aprobadores predeterminados.**

5. **Guardar** y **cerrar**.

### <a name="in-exchange-management-powershell"></a>En Exchange PowerShell de administración

Para habilitar el acceso con privilegios y asignar el grupo del aprobador, ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Ejemplo:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>La característica cuentas del sistema está disponible para garantizar que ciertas automatizacións dentro de las organizaciones puedan funcionar sin dependencia del acceso con privilegios, pero se recomienda que estas exclusiones sean excepcionales y que las permitidas se aprueben y audite periódicamente.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Paso 3: Crear una directiva de acceso

Puede crear y configurar hasta 30 directivas de acceso con privilegios para su organización.

### <a name="in-the-microsoft-365-admin-center"></a>En el Centro Microsoft 365 administración

1. Inicie sesión en el [Centro Microsoft 365 administración](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de su organización.

2. En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.

3. Seleccione **Administrar directivas y solicitudes de acceso.**

4. Seleccione **Configurar directivas** y seleccione Agregar una **directiva**.

5. En los campos desplegables, seleccione los valores adecuados para su organización:
    
    **Tipo de directiva**: tarea, rol o grupo de roles

    **Ámbito de la directiva**: Exchange

    **Nombre de la directiva**: seleccionar entre las directivas disponibles

    **Tipo de aprobación**: manual o automática

    **Grupo de aprobación**: seleccionar el grupo de aprobadores creado en el paso 1

6. Seleccione **Crear** y, a continuación, **Cerrar**. La directiva puede tardar unos minutos en estar totalmente configurada y habilitada.

### <a name="in-exchange-management-powershell"></a>En Exchange PowerShell de administración

Para crear y definir una directiva de aprobación, ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Ejemplo:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Paso 4: Enviar o aprobar solicitudes de acceso con privilegios

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Solicitud de autorización de elevación para ejecutar tareas privilegiadas

Las solicitudes de acceso con privilegios son válidas hasta 24 horas después de que se hayan enviado. Si ni se aprueban ni se deniegan, las solicitudes expiran y el acceso no se aprueba.

#### <a name="in-the-microsoft-365-admin-center"></a>En el Centro Microsoft 365 administración

1. Inicie sesión en el [Centro Microsoft 365 administración](https://admin.microsoft.com) con sus credenciales.

2. En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.

3. Seleccione **Administrar directivas y solicitudes de acceso.**

4. Seleccione **Nueva solicitud**. En los campos desplegables, seleccione los valores adecuados para su organización:

    **Tipo de solicitud**: tarea, rol o grupo de roles

    **Ámbito de la solicitud**: Exchange

    **Solicitud de**: seleccionar entre las directivas disponibles

    **Duración (horas)**: número de horas del acceso solicitado No hay un límite en el número de horas que se pueden solicitar.

    **Comentarios:** Campo de texto para los comentarios relacionados con la solicitud de acceso

5. Seleccione **Guardar** y, a continuación, **Cerrar**. La solicitud se enviará al grupo del aprobador por correo electrónico.

#### <a name="in-exchange-management-powershell"></a>En Exchange PowerShell de administración

Ejecute el siguiente comando en Exchange Online PowerShell para crear y enviar una solicitud de aprobación al grupo del aprobador:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Ejemplo:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Ver el estado de las solicitudes de elevación

Después de crear una solicitud de aprobación, el estado de la solicitud de elevación se puede revisar en el Centro de administración o en powerShell de administración Exchange mediante el identificador de solicitud asociado.

#### <a name="in-the-microsoft-365-admin-center"></a>En el Centro de administración de Microsoft 365

1. Inicie sesión en el [Microsoft 365 de administración con](https://admin.microsoft.com) sus credenciales.

2. En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.

3. Seleccione **Administrar directivas y solicitudes de acceso.**

4. Seleccione **Ver** para filtrar las solicitudes enviadas por estado **Pendiente,** **Aprobado,** **Denegado** o **Caja de seguridad del** cliente.

#### <a name="in-exchange-management-powershell"></a>En Exchange PowerShell de administración

Ejecute el siguiente comando en Exchange Online PowerShell para ver el estado de una solicitud de aprobación para un identificador de solicitud específico:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Ejemplo:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Aprobar una solicitud de autorización de elevación

Cuando se crea una solicitud de aprobación, los miembros del grupo de aprobadores correspondiente reciben una notificación por correo electrónico y pueden aprobar la solicitud asociada con el identificador de solicitud. Se notificará al solicitante de la aprobación o denegación de la solicitud por correo electrónico.

#### <a name="in-the-microsoft-365-admin-center"></a>En el Centro de administración de Microsoft 365

1. Inicie sesión en el [Microsoft 365 de administración con](https://admin.microsoft.com) sus credenciales.

2. En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.

3. Seleccione **Administrar directivas y solicitudes de acceso.**

4. Seleccione una solicitud enumerada para ver los detalles y tomar medidas en la solicitud.

5. Seleccione **Aprobar** para aprobar la solicitud o **seleccione Denegar** para denegar la solicitud. Las solicitudes aprobadas anteriormente pueden tener acceso revocado seleccionando **Revocar**.

#### <a name="in-exchange-management-powershell"></a>En Exchange PowerShell de administración

Para aprobar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Ejemplo:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Para denegar una solicitud de autorización de elevación, ejecute el siguiente comando en Exchange Online PowerShell:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Ejemplo:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Eliminar una directiva de acceso con privilegios en Office 365

Si ya no es necesario en su organización, puede eliminar una directiva de acceso con privilegios.

### <a name="in-the-microsoft-365-admin-center"></a>En el Centro de administración de Microsoft 365

1. Inicie sesión en el [Microsoft 365 de administración](https://admin.microsoft.com) con las credenciales de una cuenta de administrador de su organización.

2. En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.

3. Seleccione **Administrar directivas y solicitudes de acceso.**

4. Seleccione **Configurar directivas**.

5. Seleccione la directiva que desea eliminar y, a continuación, **seleccione Quitar directiva**.

6. Seleccione **Cerrar**.

### <a name="in-exchange-management-powershell"></a>En Exchange PowerShell de administración

Para eliminar una directiva de acceso con privilegios, ejecute el siguiente comando en Exchange Online Powershell:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Deshabilitar el acceso con privilegios en Office 365

Si es necesario, puede deshabilitar la administración de acceso con privilegios para su organización. Deshabilitar el acceso con privilegios no elimina ninguna de las directivas de aprobación o grupos de aprobadores asociados.

### <a name="in-the-microsoft-365-admin-center"></a>En el Centro de administración de Microsoft 365

1. Inicie sesión en el [Microsoft 365 de administración](https://admin.microsoft.com) con credenciales para una cuenta de administrador de su organización.

2. En el Centro de administración, vaya **a Configuración**  >  **Org Configuración** Security &  >  **Privacy**  >  **Privileged access**.

3. Habilite requerir **aprobaciones para el** control de acceso con privilegios.

### <a name="in-exchange-management-powershell"></a>En Exchange PowerShell de administración

Para deshabilitar el acceso con privilegios, ejecute el siguiente comando en Exchange Online Powershell:

```PowerShell
Disable-ElevatedAccessControl
```
