---
title: Configuración de auditoría (Premium) en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: En este artículo se describe cómo configurar auditoría (Premium) para que pueda realizar investigaciones forenses cuando las cuentas de usuario están en peligro o para investigar otros incidentes relacionados con la seguridad.
ms.openlocfilehash: adffd696a3eca2d51fb5325cd79c1ba26e58936c
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66639344"
---
# <a name="set-up-microsoft-purview-audit-premium"></a>Configurar Auditoría de Microsoft Purview (Premium)

Si su organización tiene una suscripción y licencias de usuario final que admiten Audit (Premium), realice los pasos siguientes para configurar y usar las funcionalidades adicionales de Auditoría (Premium).

![Flujo de trabajo para configurar Auditoría (Premium).](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-audit-premium-for-users"></a>Paso 1: Configurar auditoría (Premium) para usuarios

Las características de auditoría (Premium) como la capacidad para registrar eventos fundamentales, como MailItemsAccessed y Send, requieren una licencia adecuada de E5 asignada a los usuarios. Además, se debe habilitar la aplicación o el plan de servicio de Auditoría avanzada para estos usuarios. Para comprobar que la aplicación de Auditoría avanzada está asignada a los usuarios, realice estos pasos para cada usuario:

1. En el Centro de administración de Microsoft 365, vaya a **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**usuarios activos**</a> y seleccione un usuario.

2. En la página flotante de propiedades de usuario, haga clic en **Licencias y aplicaciones**.

3. En la sección **Licencias** , compruebe que al usuario se le asigna una licencia E5 o que se le asigna una licencia de complemento adecuada. Para obtener una lista de licencias compatibles con Audit (Premium), consulte [Requisitos de licencias de auditoría (Premium](auditing-solutions-overview.md#audit-premium-1)).

4. Expanda la sección **Aplicaciones** y compruebe que está seleccionada la casilla de verificación de **Auditoría avanzada de Microsoft 365**.

5. Si la casilla no está seleccionada, selecciónela y haga clic en **Guardar cambios.**

   El registro de registros de auditoría para MailItemsAccessed y Send comenzará en un plazo de 24 horas. Debe realizar el paso 3 para iniciar el registro de otros dos eventos de auditoría (Premium): SearchQueryInitiatedExchange y SearchQueryInitiatedSharePoint.

Además, si ha personalizado las acciones de buzón que han iniciado sesión en buzones de usuario o buzones compartidos, los nuevos eventos de auditoría (Premium) publicados por Microsoft no se auditarán automáticamente en esos buzones. Para información sobre cómo cambiar las acciones de buzón de correo que se auditan para cada tipo de inicio de sesión, consulte la sección "Cambiar o restaurar acciones de buzón registradas de forma predeterminada" en [Administrar la auditoría de buzón](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).

## <a name="step-2-enable-audit-premium-events"></a>Paso 2: Habilitar eventos de auditoría (Premium)

Debe habilitar dos eventos Audit (Premium) (SearchQueryInitiatedExchange y SearchQueryInitiatedSharePoint) para que se registren cuando los usuarios realicen búsquedas en Exchange Online y SharePoint Online. Para permitir que estos dos eventos se auditan para los usuarios, ejecute el siguiente comando (para cada usuario) en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

En un entorno multigeográfico, debe ejecutar el comando **Set-Mailbox** anterior en el bosque donde se encuentra el buzón del usuario. Para identificar la ubicación del buzón del usuario, ejecute el siguiente comando: 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

Si el comando para habilitar la auditoría de consultas de búsqueda se ejecutó anteriormente en un bosque distinto del que se encuentra en el buzón del usuario, debe quitar el valor SearchQueryInitiated del buzón del usuario ejecutándolo `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` y, a continuación, agregarlo al buzón del usuario en el bosque donde se encuentra el buzón del usuario.

## <a name="step-3-set-up-audit-retention-policies"></a>Paso 3: Configurar directivas de retención de auditoría

Además de la directiva predeterminada que conserva los registros de auditoría de Exchange, SharePoint y Azure AD durante un año, puede crear otras directivas de retención de registros de auditoría para cumplir los requisitos de los equipos de operaciones de seguridad, TI y cumplimiento de su organización. Para obtener más información, vea [administrar directivas de retención de los registros de auditoría](audit-log-retention-policies.md).

## <a name="step-4-search-for-audit-premium-events"></a>Paso 4: Buscar eventos de auditoría (Premium)

Ahora que tiene la auditoría (Premium) configurada para su organización, puede buscar eventos de auditoría (Premium) cruciales y otras actividades al realizar investigaciones forenses. Después de completar los pasos 1 y 2, puede buscar en el registro de auditoría eventos de auditoría (Premium) y otras actividades durante las investigaciones forenses de cuentas en peligro y otros tipos de investigaciones de seguridad o cumplimiento. Para obtener más información sobre cómo realizar una investigación forense de cuentas de usuario en peligro mediante el evento MailItemsAccessed Audit (Premium), vea [Usar auditoría (Premium) para investigar cuentas en peligro](mailitemsaccessed-forensics-investigations.md).
