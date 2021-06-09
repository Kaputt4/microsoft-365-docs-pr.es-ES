---
title: Administración de acceso con privilegios para Microsoft 365 entorno de prueba de empresa
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
description: Use esta Guía del laboratorio de pruebas para habilitar la administración de acceso con privilegios Microsoft 365 entorno de prueba empresarial.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126422"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Administración de acceso con privilegios para Microsoft 365 entorno de prueba de empresa

*Esta Guía del laboratorio de pruebas se puede usar tanto Microsoft 365 entornos de prueba empresariales como Office 365 Enterprise de prueba.*

En este artículo se describe cómo configurar la administración de acceso con privilegios para aumentar la seguridad Microsoft 365 entorno de prueba empresarial.

La configuración de la administración de acceso con privilegios implica tres fases:
- [Fase 1: Crear su Microsoft 365 entorno de prueba empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar la administración de acceso con privilegios](#phase-2-configure-privileged-access-management)
- [Fase 3: Comprobar que la aprobación es necesaria para tareas con privilegios y privilegios elevados](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Crear su Microsoft 365 entorno de prueba empresarial

Si desea configurar la administración de acceso con privilegios de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar la administración de acceso con privilegios en una empresa simulada, siga las instrucciones de [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Probar la administración de acceso con privilegios no requiere el entorno de prueba de empresa simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory. Se proporciona aquí como una opción para que pueda probar la administración de acceso con privilegios y experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Configurar la administración de acceso con privilegios

En esta fase, configure un grupo de aprobadores y habilite la administración de acceso con privilegios para su Microsoft 365 entorno de prueba empresarial. Para obtener más información y una introducción a la administración de acceso con privilegios, vea [Privileged access management](../compliance/privileged-access-management-overview.md).

Para configurar y usar el acceso con privilegios en la organización, siga estos pasos.

#### <a name="step-1-create-an-approvers-group"></a>[Paso 1: Crear un grupo de aprobadores](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Antes de empezar a usar el acceso con privilegios, determine quién tendrá autoridad de aprobación para las solicitudes entrantes de acceso a tareas con privilegios y privilegios elevados. Todos los usuarios que forman parte del grupo aprobadores pueden aprobar solicitudes de acceso. Para usar el acceso con privilegios, debe crear un grupo de seguridad habilitado para correo en Microsoft 365. En el entorno de prueba, asigne al nuevo grupo de seguridad el nombre "Aprobadores de acceso privilegiado" y agregue el "Usuario 3" que se creó anteriormente en los pasos de guía del laboratorio de pruebas anteriores.

#### <a name="step-2-enable-privileged-access"></a>[Paso 2: Habilitar el acceso con privilegios](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

El acceso con privilegios debe estar activado explícitamente en Microsoft 365 con el grupo de aprobadores predeterminado y debe incluir un conjunto de cuentas del sistema que desee excluir del control de acceso de administración de acceso con privilegios. Asegúrese de habilitar el acceso con privilegios en su organización antes de iniciar la fase 3 de esta guía.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Comprobar que la aprobación es necesaria para tareas con privilegios y privilegios elevados

En esta fase, compruebe que la directiva de acceso con privilegios funciona y que los usuarios necesitan la aprobación para ejecutar tareas definidas con privilegios y privilegios.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Probar la capacidad de ejecutar una tarea NO definida en una directiva de acceso con privilegios

En primer lugar, conéctese a Exchange PowerShell de administración con las credenciales de un usuario configurado como administrador global en el entorno de prueba e intente crear una nueva regla de diario. La [tarea New-JournalRule](/powershell/module/exchange/new-journalrule) no está definida actualmente en una directiva de acceso con privilegios para su organización.

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto de PowerShell con la cuenta de administrador global del entorno de  >   prueba.

1. En Exchange PowerShell de administración, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Vea que la nueva regla de diario se creó correctamente en powerShell Exchange administración.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Crear una nueva directiva de acceso con privilegios para la New-JournalRule de acceso

>[!NOTE]
>Si aún no ha completado los pasos 1 y 2 de la fase 2 de esta guía, asegúrese de seguir los pasos para crear un grupo de aprobadores denominado "Aprobadores de acceso de privilegios" para habilitar el acceso con privilegios en el entorno de prueba.

1. Inicie sesión en el [centro Microsoft 365 de administración](https://admin.microsoft.com) con las credenciales de la cuenta de administrador global del entorno de prueba.

2. En el Centro de administración, vaya **a Configuración** Seguridad &  >  **Acceso con**  >  **privilegios de privacidad.**

3. Seleccione **Administrar directivas y solicitudes de acceso.**

4. Seleccione **Configurar directivas** y, a continuación, seleccione Agregar una **directiva**.

5. En los campos desplegables, seleccione o escriba los siguientes valores:

    **Tipo de directiva**: Tarea

    **Ámbito de la directiva**: Exchange

    **Nombre de directiva**: Nueva regla de diario

    **Tipo de aprobación**: Manual

    **Grupo de aprobación:** Aprobadores de acceso con privilegios

6. Seleccione **Crear** y, a continuación, seleccione **Cerrar**. La directiva puede tardar unos minutos en estar totalmente configurada y habilitada. Asegúrese de permitir que la directiva esté totalmente habilitada antes de probar el requisito de aprobación en el siguiente paso.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprobación de prueba para la New-JournalRule definida en una directiva de acceso con privilegios

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto de PowerShell con una cuenta de administrador global para el entorno de  >   prueba.

2. En Exchange PowerShell de administración, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Vea el error "Permisos insuficientes" Exchange PowerShell de administración:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitar acceso para crear una nueva regla de diario mediante la New-JournalRule de registro

1. Inicie sesión en el [centro Microsoft 365 administración](https://admin.microsoft.com) con la cuenta de administrador global del entorno de prueba.

2. En el Centro de administración, vaya **a Configuración** Seguridad &  >  **Acceso con**  >  **privilegios de privacidad.**

3. Seleccione **Administrar directivas y solicitudes de acceso.**

4. Seleccione **Nueva solicitud**. En los campos desplegables, seleccione los valores adecuados para su organización:

    **Tipo de solicitud**: Tarea

    **Ámbito de la solicitud**: Exchange

    **Solicitud de**: Nueva regla de diario

    **Duración (horas):** 2

    **Comentarios:** solicitar permiso para crear una nueva regla de diario

5. Seleccione **Guardar** y, a continuación, **seleccione Cerrar**. La solicitud se enviará al grupo del aprobador por correo electrónico.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprobar la solicitud de acceso con privilegios para la creación de una nueva regla de diario

1. Inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con las credenciales del usuario 3 en el entorno de prueba (miembro del grupo de seguridad "Aprobadores de acceso privilegiado" en el entorno de prueba).

2. En el Centro de administración, vaya **a Configuración** Seguridad &  >  **Acceso con**  >  **privilegios de privacidad.**

3. Seleccione **Administrar directivas y solicitudes de acceso.**

4. Seleccione la solicitud pendiente y, a continuación, seleccione **Aprobar** para conceder acceso a la cuenta de administrador global para crear una nueva regla de diario. La cuenta de administrador global (el usuario solicitante) recibirá una confirmación por correo electrónico de que se concedió la aprobación.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Probar la creación de una nueva regla de diario con acceso con privilegios aprobado para la New-JournalRule trabajo

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange Online en **Microsoft Corporation** Microsoft Exchange Online Módulo remoto de PowerShell con la cuenta de administrador global del entorno de  >   prueba.

1. En Exchange PowerShell de administración, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Vea que la nueva regla de diario se creó correctamente en powerShell Exchange administración.

## <a name="next-step"></a>Paso siguiente

Explore características [y capacidades adicionales](m365-enterprise-test-lab-guides.md#information-protection) de protección de la información en el entorno de prueba.

## <a name="see-also"></a>Consulte también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)
