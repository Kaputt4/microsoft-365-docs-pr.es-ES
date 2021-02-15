---
title: Administración de acceso con privilegios para su entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
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
description: Use esta guía del entorno de pruebas para habilitar la administración de acceso con privilegios en el entorno de pruebas de Microsoft 365 para empresas.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126422"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Administración de acceso con privilegios para su entorno de prueba de Microsoft 365 para empresas

*Esta Guía del entorno de pruebas se puede usar tanto para entornos de prueba de Microsoft 365 para empresas como de Office 365 Enterprise.*

En este artículo se describe cómo configurar la administración del acceso con privilegios para aumentar la seguridad en el entorno de prueba de Microsoft 365 para empresas.

La configuración de la administración de accesos privilegiados consta de tres fases:
- [Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar la administración del acceso con privilegios](#phase-2-configure-privileged-access-management)
- [Fase 3: Comprobar que la aprobación es necesaria para tareas con privilegios elevados y elevados](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear el entorno de prueba de Microsoft 365 para empresas

Si desea configurar la administración de acceso con privilegios de forma ligera con los requisitos mínimos, siga las instrucciones de [la configuración básica ligera.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Si desea configurar la administración de acceso con privilegios en una empresa simulada, siga las instrucciones de autenticación [de paso a través.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>Las pruebas de administración de acceso con privilegios no requieren el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory. Se proporciona aquí como una opción para que pueda probar la administración de acceso con privilegios y experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Configurar la administración del acceso con privilegios

En esta fase, configure un grupo de aprobadores y habilite la administración del acceso con privilegios para su entorno de prueba de Microsoft 365 para empresas. Para obtener más información y una introducción a la administración del acceso con privilegios, consulte [Privileged access management](../compliance/privileged-access-management-overview.md).

Para configurar y usar el acceso con privilegios en la organización, siga estos pasos.

#### <a name="step-1-create-an-approvers-group"></a>[Paso 1: Crear un grupo de aprobadores](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Antes de empezar a usar el acceso con privilegios, determine quién tendrá autoridad de aprobación para las solicitudes entrantes de acceso a tareas con privilegios elevados y con privilegios. Todos los usuarios que forman parte del grupo aprobadores pueden aprobar solicitudes de acceso. Para usar el acceso con privilegios, debe crear un grupo de seguridad habilitado para correo en Microsoft 365. En el entorno de prueba, asigne al nuevo grupo de seguridad el nombre "Aprobadores de acceso con privilegios" y agregue el "Usuario 3" que se creó anteriormente en los pasos de guía del entorno de pruebas anteriores.

#### <a name="step-2-enable-privileged-access"></a>[Paso 2: Habilitar el acceso con privilegios](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

El acceso con privilegios debe estar activado explícitamente en Microsoft 365 con el grupo de aprobadores predeterminado y debe incluir un conjunto de cuentas del sistema que desea excluir del control de acceso de administración de acceso con privilegios. Asegúrese de habilitar el acceso con privilegios en su organización antes de iniciar la fase 3 de esta guía.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Comprobar que la aprobación es necesaria para tareas con privilegios elevados y elevados

En esta fase, compruebe que la directiva de acceso con privilegios funciona y que los usuarios necesitan la aprobación para ejecutar tareas definidas con privilegios elevados y con privilegios.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Probar la capacidad de ejecutar una tarea NO definida en una directiva de acceso con privilegios

En primer lugar, conéctese a PowerShell de administración de Exchange con las credenciales de un usuario configurado como administrador global en su entorno de prueba e intente crear una nueva regla de diario. La [tarea New-JournalRule](/powershell/module/exchange/new-journalrule) no está definida actualmente en una directiva de acceso con privilegios para su organización.

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto de PowerShell con la cuenta de administrador global para su entorno  >   de prueba.

1. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Ver que la nueva regla de diario se creó correctamente en Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Crear una nueva directiva de acceso con privilegios para la New-JournalRule de acceso

>[!NOTE]
>Si aún no ha completado los pasos 1 y 2 de la fase 2 de esta guía, asegúrese de seguir los pasos para crear un grupo de aprobadores denominado "Aprobadores de acceso con privilegios" para habilitar el acceso con privilegios en el entorno de prueba.

1. Inicie sesión en el Centro [de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de la cuenta de administrador global del entorno de prueba.

2. En el Centro de administración, vaya **a** Configuración  >  **de seguridad & acceso con**  >  **privilegios de privacidad.**

3. Seleccione **Administrar directivas de acceso y solicitudes.**

4. Seleccione **Configurar directivas** y, a continuación, seleccione Agregar una **directiva.**

5. En los campos desplegables, seleccione o escriba los siguientes valores:

    **Tipo de directiva**: tarea

    **Ámbito de directiva:** Exchange

    **Nombre de directiva:** nueva regla de diario

    **Tipo de aprobación:** Manual

    **Grupo de aprobación:** Aprobadores de acceso con privilegios

6. Seleccione **Crear** y, a continuación, **seleccione Cerrar**. La directiva puede tardar unos minutos en configurarse y habilitarse completamente. Asegúrese de dejar tiempo para que la directiva esté completamente habilitada antes de probar el requisito de aprobación en el siguiente paso.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprobación de prueba para New-JournalRule tarea definida en una directiva de acceso con privilegios

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto  >  **de PowerShell** con una cuenta de administrador global para su entorno de prueba.

2. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Vea el error "Permisos insuficientes" en PowerShell de administración de Exchange:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitar acceso para crear una nueva regla de diario mediante la New-JournalRule tarea

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global del entorno de prueba.

2. En el Centro de administración, vaya **a** Configuración  >  **de seguridad & acceso con**  >  **privilegios de privacidad.**

3. Seleccione **Administrar directivas de acceso y solicitudes.**

4. Seleccione **Nueva solicitud.** En los campos desplegables, seleccione los valores adecuados para su organización:

    **Tipo de solicitud**: tarea

    **Ámbito de solicitud:** Exchange

    **Solicitud de**: Nueva regla de diario

    **Duración (horas):** 2

    **Comentarios:** solicitar permiso para crear una nueva regla de diario

5. Seleccione **Guardar** y, a continuación, **seleccione Cerrar**. Su solicitud se enviará al grupo del aprobador por correo electrónico.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprobar la solicitud de acceso con privilegios para la creación de una nueva regla de diario

1. Inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con las credenciales del usuario 3 del entorno de prueba (miembro del grupo de seguridad "Aprobadores de acceso con privilegios" en el entorno de prueba).

2. En el Centro de administración, vaya **a** Configuración  >  **de seguridad & acceso con**  >  **privilegios de privacidad.**

3. Seleccione **Administrar directivas de acceso y solicitudes.**

4. Seleccione la solicitud pendiente y, a continuación, seleccione **Aprobar** para conceder acceso a la cuenta de administrador global para crear una nueva regla de diario. La cuenta de administrador global (el usuario solicitante) recibirá una confirmación por correo electrónico de que se ha concedido la aprobación.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Probar la creación de una nueva regla de diario con acceso con privilegios aprobado para la New-JournalRule tarea

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto de PowerShell con la cuenta de administrador global para su entorno  >   de prueba.

1. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Ver que la nueva regla de diario se creó correctamente en Exchange Management PowerShell.

## <a name="next-step"></a>Paso siguiente

Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#information-protection) de protección de la información en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)
