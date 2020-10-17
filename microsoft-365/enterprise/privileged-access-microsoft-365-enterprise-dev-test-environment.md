---
title: Administración del acceso con privilegios para el entorno de prueba de Microsoft 365 para empresas
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
description: Use esta guía del laboratorio de pruebas para habilitar la administración del acceso con privilegios en su entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487593"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Administración del acceso con privilegios para el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*

En este artículo se describe cómo configurar la administración del acceso con privilegios para aumentar la seguridad en el entorno de prueba de Microsoft 365 para empresas.

La configuración de la administración de acceso privilegiada implica tres fases:
- [Fase 1: crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurar la administración del acceso con privilegios](#phase-2-configure-privileged-access-management)
- [Fase 3: comprobar que la aprobación es necesaria para las tareas elevadas y privilegiadas](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si desea configurar la administración del acceso con privilegios de manera ligera con los requisitos mínimos, siga las instrucciones de la [configuración básica ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar la administración del acceso con privilegios en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>La comprobación de la administración del acceso con privilegios no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory. Se proporciona aquí como una opción para poder probar la administración de acceso privilegiado y experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: configurar la administración del acceso con privilegios

En esta fase, configure un grupo aprobadores y habilite la administración del acceso con privilegios para el entorno de prueba de Microsoft 365 para empresas. Para obtener información adicional y una introducción a la administración del acceso con privilegios, consulte [privileged Access Management](../compliance/privileged-access-management-overview.md).

Para configurar y usar el acceso con privilegios en su organización, siga estos pasos.

#### <a name="step-1-create-an-approvers-group"></a>[Paso 1: crear un grupo de aprobadores](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Antes de empezar a usar el acceso con privilegios, determine quién tendrá autoridad de aprobación para obtener acceso a tareas elevadas y privilegiadas. Todos los usuarios que forman parte del grupo de aprobadores pueden aprobar solicitudes de acceso. Para usar el acceso con privilegios, debe crear un grupo de seguridad habilitado para correo en Microsoft 365. En su entorno de prueba, denomine "aprobadores de acceso privilegiados" al nuevo grupo de seguridad y agregue el "usuario 3" que se creó anteriormente en los pasos anteriores de la guía del entorno de pruebas.

#### <a name="step-2-enable-privileged-access"></a>[Paso 2: habilitar el acceso con privilegios](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

El acceso privilegiado debe estar activado explícitamente en Microsoft 365 con el grupo de aprobador predeterminado y debe incluir un conjunto de cuentas de sistema que desea excluir del control de acceso privilegiado de la administración de acceso. Asegúrese de habilitar el acceso con privilegios en su organización antes de iniciar la fase 3 de esta guía.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: comprobar que la aprobación es necesaria para las tareas elevadas y privilegiadas

En esta fase, compruebe que la Directiva de acceso privilegiado funciona y que los usuarios necesitan aprobación para ejecutar las tareas elevadas y privilegiadas definidas.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Probar la capacidad de ejecutar una tarea no definida en una directiva de acceso privilegiada

En primer lugar, conéctese a PowerShell de administración de Exchange con las credenciales de un usuario configurado como administrador global en el entorno de prueba e intente crear una nueva regla de diario. La tarea [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) no se define actualmente en una directiva de acceso privilegiada para su organización.

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange online en el módulo de PowerShell remoto de Microsoft **Corporation**  >  **Microsoft Exchange Online** con la cuenta de administrador global para su entorno de prueba.

1. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Vista que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Crear una nueva Directiva de acceso privilegiado para la tarea de New-JournalRule

>[!NOTE]
>Si todavía no ha completado los pasos 1 y 2 de la fase 2 de esta guía, asegúrese de seguir los pasos para crear un grupo de aprobadores denominado "aprobadores de acceso de privilegios" para habilitar el acceso privilegiado en el entorno de prueba.

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales de la cuenta de administrador global para su entorno de prueba.

2. En el centro de administración, vaya a **configuración**  >  **seguridad &**  >  **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **configurar directivas**y, a continuación, seleccione **Agregar una directiva**.

5. En los campos desplegables, seleccione o escriba los siguientes valores:

    **Tipo de directiva**: tarea

    **Ámbito de directiva**: Exchange

    **Nombre de directiva**: nueva regla de diario

    **Tipo de aprobación**: manual

    **Grupo de aprobación**: aprobadores de acceso privilegiados

6. Seleccione **crear**y, a continuación, haga clic en **cerrar**. La Directiva puede tardar unos minutos en estar totalmente configurada y habilitada. Asegúrese de dejar tiempo para que la Directiva esté totalmente habilitada antes de probar el requisito de aprobación en el paso siguiente.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprobación de prueba para la tarea de New-JournalRule definida en una directiva de acceso privilegiado

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange online en el módulo de PowerShell remoto de Microsoft **Corporation**  >  **Microsoft Exchange Online** usando un con la cuenta de administrador global para su entorno de prueba.

2. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Vea el error "permisos insuficientes" en Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitar acceso para crear una nueva regla de diario mediante la tarea New-JournalRule

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con la cuenta de administrador global para su entorno de prueba.

2. En el centro de administración, vaya a **configuración**  >  **seguridad &**  >  **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **nueva solicitud**. En los campos desplegables, seleccione los valores adecuados para su organización:

    **Tipo de solicitud**: tarea

    **Ámbito de solicitud**: Exchange

    **Solicitud de**: nueva regla de diario

    **Duración (horas)**: 2

    **Comentarios**: solicitar permiso para crear una nueva regla de diario

5. Seleccione **Guardar**y, después, haga clic en **cerrar**. La solicitud se enviará al grupo del aprobador a través del correo electrónico.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprobar la solicitud de acceso con privilegios para la creación de una nueva regla de diario

1. Inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales del usuario 3 en su entorno de prueba (miembro del grupo de seguridad "aprobadores de acceso con privilegios" en su entorno de prueba).

2. En el centro de administración, vaya a **configuración**  >  **seguridad &**  >  **acceso privilegiado a**la privacidad.

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione la solicitud pendiente y, a continuación, seleccione **aprobar** para conceder acceso a la cuenta de administrador global para crear una nueva regla de diario. La cuenta de administrador global (el usuario que realiza la solicitud) recibirá una confirmación por correo electrónico de que se ha concedido la aprobación.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Probar la creación de una nueva regla de diario con acceso con privilegios aprobado para la tarea de New-JournalRule

1. En el equipo local, abra e inicie sesión en el módulo de PowerShell remoto de Exchange online en el módulo de PowerShell remoto de Microsoft **Corporation**  >  **Microsoft Exchange Online** con la cuenta de administrador global para su entorno de prueba.

1. En Exchange Management PowerShell, cree una nueva regla de diario para su organización:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Vista que la nueva regla de diario se ha creado correctamente en Exchange Management PowerShell.

## <a name="next-step"></a>Paso siguiente

Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
