---
title: Administración de acceso con privilegios para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- tier3
- M365-security-compliance
ms.custom: Ent_TLGs
description: Use esta guía de laboratorio de pruebas para habilitar la administración de acceso con privilegios en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 39c7a9bd2d964e40d7dea410fd91a2fb912e2c03
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68188953"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Administración de acceso con privilegios para el entorno de prueba de Microsoft 365 para empresas

*Esta guía de laboratorio de pruebas se puede usar para Microsoft 365 para entornos de prueba empresariales y Office 365 Enterprise.*

En este artículo se describe cómo configurar la administración de acceso con privilegios para aumentar la seguridad en el entorno de prueba de Microsoft 365 para empresas.

La configuración de la administración de acceso con privilegios implica tres fases:

- [Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configuración de la administración de acceso con privilegios](#phase-2-configure-privileged-access-management)
- [Fase 3: Comprobar que la aprobación es necesaria para tareas con privilegios elevados y con privilegios](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para enterprise Test Lab Guide Stack (Pila de guía del laboratorio de pruebas empresariales).](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas

Si desea configurar la administración de acceso con privilegios de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar la administración de acceso con privilegios en una empresa simulada, siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de la administración de acceso con privilegios no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory. Se proporciona aquí como una opción para que pueda probar la administración de acceso con privilegios y experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Configuración de la administración de acceso con privilegios

En esta fase, configure un grupo de aprobadores y habilite la administración de acceso con privilegios para el entorno de prueba de Microsoft 365 para empresas. Para más información y información general sobre la administración de acceso con privilegios, consulte [Administración de acceso con privilegios](../compliance/privileged-access-management-overview.md).

Para configurar y usar el acceso con privilegios en su organización, siga estos pasos.

### <a name="step-1-create-an-approvers-group"></a>[Paso 1: Crear el grupo de un aprobador](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Antes de empezar a usar el acceso con privilegios, determine quién tendrá autoridad de aprobación para las solicitudes entrantes de acceso a tareas con privilegios elevados y con privilegios. Todos los usuarios que forman parte del grupo de aprobadores pueden aprobar solicitudes de acceso. Para usar el acceso con privilegios, debe crear un grupo de seguridad habilitado para correo en Microsoft 365. En el entorno de prueba, asigne al nuevo grupo de seguridad el nombre "Aprobadores de acceso con privilegios" y agregue el "Usuario 3" que se creó anteriormente en los pasos anteriores de la guía del laboratorio de pruebas.

### <a name="step-2-enable-privileged-access"></a>[Paso 2: Habilitar el acceso con privilegios](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

El acceso con privilegios debe activarse explícitamente en Microsoft 365 con el grupo de aprobadores predeterminado y debe incluir un conjunto de cuentas del sistema que quiera excluir del control de acceso de administración de acceso con privilegios. Asegúrese de habilitar el acceso con privilegios en su organización antes de iniciar la fase 3 de esta guía.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Comprobar que la aprobación es necesaria para tareas con privilegios elevados y con privilegios

En esta fase, compruebe que la directiva de acceso con privilegios funciona y que los usuarios necesitan aprobación para ejecutar tareas definidas con privilegios elevados y con privilegios.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Probar la capacidad de ejecutar una tarea NO definida en una directiva de acceso con privilegios

En primer lugar, intente crear una nueva regla de diario en Exchange Online PowerShell. La tarea [New-JournalRule](/powershell/module/exchange/new-journalrule) no está definida actualmente en una directiva de acceso con privilegios para su organización.

1. En el equipo local, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) mediante credenciales con el rol Administración de roles de Exchange para el entorno de prueba.
2. Cree una nueva regla de diario para su organización mediante la ejecución del siguiente comando:

   ```PowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

3. Compruebe que la nueva regla de diario se creó correctamente:

   ```PowerShell
   Get-JournalRule -Identity "JournalRule1"
   ```

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Creación de una nueva directiva de acceso con privilegios para la tarea New-JournalRule

> [!NOTE]
> Si aún no ha completado los pasos 1 y 2 de la fase 2 de esta guía, asegúrese de seguir los pasos para crear un grupo de aprobadores denominado "Aprobadores de acceso con privilegios" para habilitar el acceso con privilegios en el entorno de prueba.

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales con el rol Administración de roles de Exchange para el entorno de prueba.
2. En el Centro de Administración, vaya a **Configuración** > **Seguridad & acceso****con privilegios** de privacidad > .
3. Seleccione **Administrar directivas y solicitudes de acceso**.
4. Seleccione **Configurar directivas** y, a continuación, **agregar una directiva**.
5. En los campos desplegables, seleccione o escriba los valores siguientes:

    **Tipo de directiva**:  **Ámbito de directiva** de tarea:  **Nombre de la directiva** de Exchange: Nuevo  **tipo de aprobación** de regla de diario:  **Grupo de aprobación** manual: Aprobadores de acceso con privilegios

6. Seleccione **Crear** y, a continuación, seleccione **Cerrar**. La directiva puede tardar unos minutos en configurarse y habilitarse completamente. Asegúrese de permitir el tiempo necesario para que la directiva esté totalmente habilitada antes de probar el requisito de aprobación en el paso siguiente.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprobación de pruebas para la tarea de New-JournalRule definida en una directiva de acceso con privilegios

1. En el equipo local, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) mediante credenciales con el rol Administración de roles de Exchange para el entorno de prueba.

2. En Exchange Online PowerShell, cree una nueva regla de diario para su organización:

   ```PowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Vea el error "Permisos insuficientes" en Exchange Online PowerShell:

   ```PowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitar acceso para crear una nueva regla de diario mediante la tarea New-JournalRule

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales con el rol Administración de roles de Exchange para el entorno de prueba.

2. En el Centro de Administración, vaya a **Configuración** > **Seguridad & acceso****con privilegios** de privacidad > .

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione **Nueva solicitud**. En los campos desplegables, seleccione los valores adecuados para su organización:

    **Tipo de solicitud**:  **Ámbito de solicitud** de tarea: Solicitud de Exchange  **para**: Nueva duración de regla  **de diario (horas):** 2  **Comentarios**: Solicitar permiso para crear una nueva regla de diario

5. Seleccione **Guardar** y, después, **Cerrar**. La solicitud se enviará al grupo del aprobador por correo electrónico.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprobación de una solicitud de acceso con privilegios para la creación de una nueva regla de diario

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con las credenciales del usuario 3 en el entorno de prueba (miembro del grupo de seguridad "Aprobadores de acceso con privilegios" en el entorno de prueba).

2. En el Centro de Administración, vaya a **Configuración** > **Seguridad & acceso****con privilegios** de privacidad > .

3. Seleccione **Administrar directivas y solicitudes de acceso**.

4. Seleccione la solicitud pendiente y, a continuación, seleccione **Aprobar** para conceder acceso a la cuenta de usuario para crear una nueva regla de diario. La cuenta (el usuario solicitante) recibirá una confirmación por correo electrónico de que se ha concedido la aprobación.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Prueba de la creación de una nueva regla de diario con acceso con privilegios aprobado para la tarea New-JournalRule

1. En el equipo local, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) mediante credenciales con el rol Administración de roles de Exchange para el entorno de prueba.

2. En Exchange Online PowerShell, cree una nueva regla de diario para su organización:

   ```PowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Compruebe que la nueva regla de diario se creó correctamente:

   ```PowerShell
   Get-JournalRule -Identity "JournalRule2"
   ```

## <a name="next-step"></a>Paso siguiente

Explore características y funcionalidades adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) en el entorno de prueba.

## <a name="see-also"></a>Vea también

- [Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)
- [Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)
- [Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)
