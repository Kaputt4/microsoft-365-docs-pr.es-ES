---
title: Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Use esta guía de laboratorio de prueba para habilitar la administración con privilegios de acceso a su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871167"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise

Con las instrucciones de este artículo, configurar la administración del acceso con privilegios para aumentar la seguridad en su entorno de prueba de Microsoft 365 Enterprise.

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea configurar la administración de acceso con privilegios en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar la administración de acceso con privilegios en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Prueba de administración con privilegios de acceso no requiere que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Aquí se proporciona como una opción para que pueda probar con privilegios de acceso a la administración y experimentar con él en un entorno que representa una organización típica. 

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Configuración de administración con privilegios de acceso

En esta fase, configurar un grupo de aprobadores y habilitar la administración con privilegios de acceso para el entorno de prueba de Microsoft 365 Enterprise. Para obtener más información y una visión general de con privilegios de administración de acceso, consulte [administración de acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Siga estos pasos para configurar y utilizar con privilegios de acceso de la organización de Office 365:

- [Paso 1: Crear el grupo del aprobador](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    Antes de empezar a usar acceso con privilegios, determinar quién tendrá la autoridad de aprobación para las solicitudes entrantes para el acceso a las tareas con privilegios elevados y con privilegios. Cualquier usuario que forma parte del grupo de los aprobadores podrán aprobar las solicitudes de acceso. Esto se habilita mediante la creación de un grupo de seguridad habilitados para correo en Office 365. Crear un nuevo grupo de seguridad denominado "Aprobadores con privilegios de acceso" en su entorno de prueba y agregar el "usuario 3" creado anteriormente en los pasos de guía de laboratorio de prueba anterior.

- [Paso 2: Habilitar el acceso con privilegios](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    Acceso con privilegios debe habilitarse explícitamente en Office 365 con el grupo de aprobadores predeterminada y, incluido un conjunto de cuentas del sistema que desea que se deben excluir desde el control de acceso de administración con privilegios de acceso. Asegúrese de habilitar el acceso con privilegios en su organización de Office 365 antes de iniciar la fase 3 de esta guía.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Compruebe que se necesita aprobación para tareas con privilegios elevados y con privilegios
En esta fase, compruebe que funciona la directiva de acceso con privilegios y los usuarios requieren aprobación para ejecutar tareas con privilegios elevados y con privilegios definidas.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Probar la capacidad de ejecutar una tarea no definida en una directiva de acceso con privilegios

En primer lugar, conéctese a Exchange Management PowerShell con las credenciales de un usuario configurado como un administrador Global en su entorno de prueba e intenta crear una nueva regla de diario. Actualmente, no se define la tarea de [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) en una directiva de acceso con privilegios para su organización.

1. En el equipo local, abra e inicie sesión en el la Exchange Online PowerShell módulo remoto en **Microsoft Corporation** > cuenta de**Microsoft Exchange Online PowerShell módulo remoto** con el administrador Global de su entorno de prueba.

2. En Exchange Management Powershell, cree una nueva regla de diario para su organización:

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. Vista de que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Crear una nueva directiva de acceso con privilegios para la tarea de New-JournalRule

> [!NOTE]
> Si aún no ha completado los pasos 1 y 2 de la fase 2 de esta guía, ser asegúrese de seguir los pasos para crear grupo del aprobador denominado "Privilegio acceso aprobadores" y para habilitar el acceso con privilegios en su entorno de prueba.

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con las credenciales de la cuenta de administrador Global para su entorno de prueba.

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Seleccione **las solicitudes y administrar las directivas de acceso**.

4. Seleccione **la configuración de directivas** y seleccione **Agregar una directiva**.

5. En los campos de lista desplegable, seleccione o introduzca los siguientes valores:
    
    **Tipo de directiva**: tarea

    **Ámbito de directiva**: Exchange

    **Nombre de la directiva**: nueva regla de diario

    **Tipo de aprobación**: Manual

    **Grupo de aprobación**: aprobadores con privilegios de acceso

6. Seleccione **crear** y, a continuación, en **Cerrar**. Puede tardar unos minutos para la directiva ser totalmente configurado y habilitado. Asegúrese de permitir tiempo para la directiva a habilitarse completamente antes de probar el requisito de aprobación en el paso siguiente.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprobación de prueba para la tarea de New-JournalRule definida en una directiva de acceso con privilegios

1. En el equipo local, abra e inicie sesión en el la Exchange Online PowerShell módulo remoto en **Microsoft Corporation** > cuenta de**Microsoft Exchange Online PowerShell módulo remoto** mediante un uso de la administración Global de la prueba entorno.

2. En Exchange Management Powershell, cree una nueva regla de diario para su organización:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Ver el error "No hay suficiente permisos" en PowerShell de administración de Exchange:

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitud de acceso para crear una nueva regla de diario mediante la tarea de New-JournalRule

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con la cuenta de administrador Global para su entorno de prueba.

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Seleccione **las solicitudes y administrar las directivas de acceso**.

4. Seleccione **nueva solicitud**. En los campos de lista desplegable, seleccione los valores apropiados para su organización:

    **Tipo de solicitud**: tarea

    **Ámbito de solicitud**: Exchange

    **Solicitud para**: nueva regla de diario

    **Duración (horas)**: 2

    **Comentarios**: solicitar permiso para crear una nueva regla de diario

5. Seleccione **Guardar** y, a continuación, en **Cerrar**. La solicitud se enviará al grupo del aprobador a través de correo electrónico.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprobar solicitudes de acceso con privilegios para la creación de una nueva regla de diario

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://portal.office.com) con las credenciales para el usuario 3 en su entorno de prueba (miembros del grupo de seguridad "Aprobadores con privilegios de acceso" en su entorno de prueba).

2. En el centro de administración, vaya a **configuración de** > **de seguridad y privacidad** > **con privilegios de acceso**.

3. Seleccione **las solicitudes y administrar las directivas de acceso**.

4. Seleccione la solicitud pendiente y seleccione **Aprobar** para conceder acceso a la cuenta de administrador Global para crear una nueva regla de diario. Se enviará un correo electrónico de notificación que confirma que se ha concedido la aprobación para la cuenta de administrador Global (el usuario solicitante).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Crear una nueva regla de diario con acceso con privilegios aprobado para la tarea de New-JournalRule de prueba

1. En el equipo local, abra e inicie sesión en el la Exchange Online PowerShell módulo remoto en **Microsoft Corporation** > cuenta de**Microsoft Exchange Online PowerShell módulo remoto** con el administrador Global de su entorno de prueba.

2. En Exchange Management Powershell, cree una nueva regla de diario para su organización:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Vista de que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.

## <a name="next-step"></a>Paso siguiente

Explorar las características adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)