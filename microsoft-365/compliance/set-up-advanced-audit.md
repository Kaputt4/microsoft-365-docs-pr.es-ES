---
title: Configurar auditoría avanzada en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo configurar la auditoría avanzada para que pueda realizar investigaciones forenses cuando las cuentas de usuario estén en peligro o investigar otros incidentes relacionados con la seguridad.
ms.openlocfilehash: 34ae98eaafcc3eeb3d6a25a457f017999b8c6078
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192072"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>Configurar auditoría avanzada en Microsoft 365

Si su organización tiene una suscripción y una licencia de usuario final compatible con la auditoría avanzada, siga estos pasos para configurar y usar las capacidades adicionales en Auditoría avanzada.

![Flujo de trabajo para configurar la auditoría avanzada.](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a>Paso 1: Configurar auditoría avanzada para usuarios

Las características de Auditoría avanzada, como la capacidad para registrar eventos fundamentales, como MailItemsAccessed y Send, requieren una licencia adecuada de E5 asignada a los usuarios. Además, se debe habilitar la aplicación o el plan de servicio de Auditoría avanzada para estos usuarios. Para comprobar que la aplicación de Auditoría avanzada está asignada a los usuarios, realice estos pasos para cada usuario:

1. En el Centro de administración de Microsoft 365, vaya a **Usuarios**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**usuarios activos**</a>y seleccione un usuario.

2. En la página flotante de propiedades de usuario, haga clic en **Licencias y aplicaciones**.

3. En la **sección Licencias,** compruebe que al usuario se le asignó una licencia E5 o que se le asignó una licencia de complemento adecuada. Para obtener una lista de licencias compatibles con la auditoría avanzada, vea [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).

4. Expanda la sección **Aplicaciones** y compruebe que está seleccionada la casilla de verificación de **Auditoría avanzada de Microsoft 365**.

5. Si la casilla no está seleccionada, selecciónelo y, a continuación, haga clic **en Guardar cambios.**

   El registro de registros de auditoría de MailItemsAccessed y Send empezará en 24 horas. Debe realizar el paso 3 para iniciar el registro de otros dos eventos de auditoría avanzada: SearchQueryInitiatedExchange y SearchQueryInitiatedSharePoint.

En el caso de las organizaciones que asignan licencias a grupos de usuarios mediante licencias basadas en grupos, tiene que desactivar la asignación de licencias para la Auditoría avanzada de Microsoft 365 para el grupo. Una vez que haya guardado los cambios, compruebe que está desactivada la Auditoría avanzada de Microsoft 365 para el grupo. Después, vuelva a activar la asignación de licencias para el grupo. Para obtener instrucciones sobre las licencias basadas en grupos, vea [Asignar licencias a usuarios por la pertenencia a grupos en Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).

Además, si ha personalizado las acciones de buzón que han iniciado sesión en buzones de usuario o buzones compartidos, los nuevos eventos de auditoría avanzada publicados por Microsoft no se auditarán automáticamente en esos buzones. Para información sobre cómo cambiar las acciones de buzón de correo que se auditan para cada tipo de inicio de sesión, consulte la sección "Cambiar o restaurar acciones de buzón registradas de forma predeterminada" en [Administrar la auditoría de buzón](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).

## <a name="step-2-enable-advanced-audit-events"></a>Paso 2: Habilitar eventos de auditoría avanzada

Debe habilitar dos eventos de auditoría avanzada (SearchQueryInitiatedExchange y SearchQueryInitiatedSharePoint) para registrar cuando los usuarios realizan búsquedas en Exchange Online y SharePoint Online. Para permitir que estos dos eventos se auditan para los usuarios, ejecute el siguiente comando (para cada usuario) [en Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

En un entorno multige geográfico, debe ejecutar el comando **Set-Mailbox** anterior en el bosque donde se encuentra el buzón del usuario. Para identificar la ubicación del buzón del usuario, ejecute el siguiente comando: 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

Si el comando para habilitar la auditoría de las consultas de búsqueda se ejecutó anteriormente en un bosque que es diferente al que se encuentra en el buzón del usuario, debe quitar el valor SearchQueryInitiated del buzón del usuario ejecutándose y, a continuación, agregarlo al buzón del usuario en el bosque donde se encuentra el buzón del `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` usuario.

## <a name="step-3-set-up-audit-retention-policies"></a>Paso 3: Configurar directivas de retención de auditoría

Además de la directiva predeterminada que conserva los registros de auditoría de Exchange, SharePoint y Azure AD durante un año, puede crear otras directivas de retención de registros de auditoría para cumplir los requisitos de los equipos de operaciones de seguridad, TI y cumplimiento de su organización. Para obtener más información, vea [administrar directivas de retención de los registros de auditoría](audit-log-retention-policies.md).

## <a name="step-4-search-for-advanced-audit-events"></a>Paso 4: Buscar eventos de auditoría avanzada

Ahora que ya tiene la auditoría avanzada configurada para su organización, puede buscar eventos cruciales de auditoría avanzada y otras actividades al llevar a cabo investigaciones forenses. Después de completar los pasos 1 y 2, puede buscar en el registro de auditoría eventos de auditoría avanzada y otras actividades durante las investigaciones forenses de cuentas comprometidas y otros tipos de investigaciones de seguridad o cumplimiento. Para obtener más información acerca de cómo llevar a cabo una investigación forense de cuentas de usuario comprometidas mediante el evento Auditoría avanzada MailItemsAccessed, vea Usar auditoría avanzada para investigar cuentas [comprometidas.](mailitemsaccessed-forensics-investigations.md)
