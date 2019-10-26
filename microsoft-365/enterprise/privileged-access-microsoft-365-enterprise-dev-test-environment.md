---
title: Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Use esta guía del laboratorio de pruebas para habilitar la administración del acceso con privilegios en su entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: df3a2138de105b45f472ff0a862af2afe6dd2a34
ms.sourcegitcommit: 64a21c59d31a283ccbe87d16f0a174998e3aeba8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "37733429"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Administración del acceso con privilegios para el entorno de pruebas de Microsoft 365 Enterprise

Con las instrucciones de este artículo, se configura la administración del acceso con privilegios para aumentar la seguridad en el entorno de prueba de Microsoft 365 Enterprise.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise

Si solo quiere configurar la administración del acceso con privilegios de manera ligera con los requisitos mínimos, siga las instrucciones de [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar la administración del acceso con privilegios en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la administración del acceso con privilegios no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de AD DS. Se proporciona aquí como una opción para poder probar la administración de acceso privilegiado y experimentar con ella en un entorno que representa una organización típica. 

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: configurar la administración del acceso con privilegios

En esta fase, configurará un grupo aprobadores y habilitará la administración de acceso privilegiada para el entorno de prueba de Microsoft 365 Enterprise. Para obtener información adicional y una introducción a la administración del acceso con privilegios, consulte [Administración del acceso con privilegios en Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Siga estos pasos para configurar y usar el acceso con privilegios en su organización de Office 365:

- [Paso 1: crear un grupo de aprobadores](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    Antes de empezar a usar el acceso de privilegios, determine quién tendrá autoridad de aprobación para el acceso a las tareas elevadas y privilegiadas. Cualquier usuario que forme parte del grupo de aprobadores podrá aprobar solicitudes de acceso. Para habilitarlo, cree un grupo de seguridad habilitado para correo en Office 365. Cree un nuevo grupo de seguridad denominado "aprobadores de acceso privilegiados" en su entorno de prueba y agregue el "usuario 3" creado anteriormente en los pasos anteriores de la guía del entorno de pruebas.

- [Paso 2: habilitar el acceso con privilegios](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    El acceso privilegiado debe estar activado explícitamente en Office 365 con el grupo de aprobador predeterminado e incluir un conjunto de cuentas del sistema que se desea excluir del control de acceso privilegiado de la administración de acceso. Asegúrese de habilitar el acceso con privilegios en su organización de Office 365 antes de iniciar la fase 3 de esta guía.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: comprobar que la aprobación es necesaria para las tareas elevadas y privilegiadas
En esta fase, se comprueba que la Directiva de acceso privilegiado funciona y que los usuarios necesitan aprobación para ejecutar las tareas elevadas y privilegiadas definidas.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Probar la capacidad de ejecutar una tarea no definida en una directiva de acceso privilegiada

En primer lugar, conéctese a PowerShell de administración de Exchange con las credenciales de un usuario configurado como administrador global en el entorno de prueba e intente crear una nueva regla de diario. La tarea [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) no se define actualmente en una directiva de acceso privilegiada para su organización.

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange online en el módulo de PowerShell remoto de Microsoft **Corporation** > **Microsoft Exchange Online** con la cuenta de administrador global para su entorno de prueba.

2. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. Vista que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Crear una nueva Directiva de acceso con privilegios para la tarea New-JournalRule

> [!NOTE]
> Si todavía no ha completado los pasos 1 y 2 de la fase 2 de esta guía, asegúrese de seguir los pasos para crear un grupo de aprobadores denominado "aprobadores de acceso de privilegios" y para habilitar el acceso privilegiado en el entorno de prueba.

1. Inicie sesión en el [centro de administración de 365 de Microsoft](https://admin.microsoft.com) con las credenciales de la cuenta de administrador global para su entorno de prueba.

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **configurar directivas** y seleccione **Agregar una directiva**.

5. En los campos desplegables, seleccione o escriba los siguientes valores:
    
    **Tipo de directiva**: tarea

    **Ámbito de directiva**: Exchange

    **Nombre de directiva**: nueva regla de diario

    **Tipo de aprobación**: manual

    **Grupo de aprobación**: aprobadores de acceso privilegiados

6. Seleccione **crear** y, a continuación, **cerrar**. La Directiva puede tardar unos minutos en estar totalmente configurada y habilitada. Asegúrese de dejar tiempo para que la Directiva esté totalmente habilitada antes de probar el requisito de aprobación en el paso siguiente.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprobación de prueba para la tarea New-JournalRule definida en una directiva de acceso privilegiado

1. En el equipo local, abra e inicie sesión en el módulo Exchange Online Remote PowerShell Module en **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** Using a Using the Global admin Account for your test entorno.

2. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Vea el error "Insuffient Permissions" en Exchange Management PowerShell:

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitar acceso para crear una nueva regla de diario mediante la tarea New-JournalRule

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global para su entorno de prueba.

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **nueva solicitud**. En los campos desplegables, seleccione los valores adecuados para su organización:

    **Tipo de solicitud**: tarea

    **Ámbito de solicitud**: Exchange

    **Solicitud de**: nueva regla de diario

    **Duración (horas)**: 2

    **Comentarios**: solicitar permiso para crear una nueva regla de diario

5. Seleccione **Guardar** y, a continuación, **cerrar**. La solicitud se enviará al grupo del aprobador a través del correo electrónico.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprobar la solicitud de acceso con privilegios para la creación de una nueva regla de diario

1. Inicie sesión en el [centro de administración de 365 de Microsoft](https://admin.microsoft.com) con las credenciales del usuario 3 en su entorno de prueba (miembro del grupo de seguridad "aprobadores de acceso con privilegios" en su entorno de prueba).

2. En el centro de administración, vaya a **configuración** > **seguridad &** > **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione la solicitud pendiente y seleccione **aprobar** para conceder acceso a la cuenta de administrador global para crear una nueva regla de diario. Se enviará un correo electrónico de notificación para confirmar que la aprobación se ha concedido a la cuenta de administrador global (el usuario que realiza la solicitud).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Prueba de creación de una nueva regla de diario con acceso con privilegios aprobado para la tarea New-JournalRule

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange online en el módulo de PowerShell remoto de Microsoft **Corporation** > **Microsoft Exchange Online** con la cuenta de administrador global para su entorno de prueba.

2. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Vista que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.

## <a name="next-step"></a>Siguiente paso

Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)