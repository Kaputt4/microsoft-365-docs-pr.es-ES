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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo configurar la auditoría avanzada para que pueda realizar investigaciones forenses cuando las cuentas de usuario estén en peligro o investigar otros incidentes relacionados con la seguridad.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314414"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="9724f-103">Configurar auditoría avanzada en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9724f-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="9724f-104">Si su organización tiene una suscripción y una licencia de usuario final compatible con la auditoría avanzada, siga estos pasos para configurar y usar las funciones adicionales en Auditoría avanzada.</span><span class="sxs-lookup"><span data-stu-id="9724f-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![Flujo de trabajo para configurar la auditoría avanzada](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a><span data-ttu-id="9724f-106">Paso 1: Configurar auditoría avanzada para usuarios</span><span class="sxs-lookup"><span data-stu-id="9724f-106">Step1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="9724f-107">Las características de Auditoría avanzada, como la capacidad para registrar eventos fundamentales, como MailItemsAccessed y Send, requieren una licencia adecuada de E5 asignada a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9724f-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="9724f-108">Además, se debe habilitar la aplicación o el plan de servicio de Auditoría avanzada para estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="9724f-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="9724f-109">Para comprobar que la aplicación de Auditoría avanzada está asignada a los usuarios, realice estos pasos para cada usuario:</span><span class="sxs-lookup"><span data-stu-id="9724f-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="9724f-110">En el [Centro de administración de Microsoft 365](https://admin.microsoft.com/Adminportal), vaya a **Usuarios** > **Usuarios activos** y seleccione un usuario.</span><span class="sxs-lookup"><span data-stu-id="9724f-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="9724f-111">En la página flotante de propiedades de usuario, haga clic en **Licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9724f-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="9724f-112">En la **sección Licencias,** compruebe que al usuario se le asignó una licencia E5 o que se le asignó una licencia de complemento adecuada.</span><span class="sxs-lookup"><span data-stu-id="9724f-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="9724f-113">Para obtener una lista de licencias compatibles con la auditoría avanzada, vea [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span><span class="sxs-lookup"><span data-stu-id="9724f-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="9724f-114">Expanda la sección **Aplicaciones** y compruebe que está seleccionada la casilla de verificación de **Auditoría avanzada de Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="9724f-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="9724f-115">Si la casilla no está seleccionada, selecciónelo y, a continuación, haga clic **en Guardar cambios.**</span><span class="sxs-lookup"><span data-stu-id="9724f-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="9724f-116">El registro de registros de auditoría de MailItemsAccessed y Send empezará en 24 horas.</span><span class="sxs-lookup"><span data-stu-id="9724f-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="9724f-117">Debe realizar el paso 3 para iniciar el registro de otros dos eventos cruciales de auditoría avanzada: SearchQueryInitiatedExchange y SearchQueryInitiatedSharePoint.</span><span class="sxs-lookup"><span data-stu-id="9724f-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="9724f-118">En el caso de las organizaciones que asignan licencias a grupos de usuarios mediante licencias basadas en grupos, tiene que desactivar la asignación de licencias para la Auditoría avanzada de Microsoft 365 para el grupo.</span><span class="sxs-lookup"><span data-stu-id="9724f-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="9724f-119">Una vez que haya guardado los cambios, compruebe que está desactivada la Auditoría avanzada de Microsoft 365 para el grupo.</span><span class="sxs-lookup"><span data-stu-id="9724f-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="9724f-120">Después, vuelva a activar la asignación de licencias para el grupo.</span><span class="sxs-lookup"><span data-stu-id="9724f-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="9724f-121">Para obtener instrucciones sobre las licencias basadas en grupos, vea [Asignar licencias a usuarios por la pertenencia a grupos en Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="9724f-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="9724f-122">Además, si ha personalizado las acciones de buzón que han iniciado sesión en buzones de usuario o buzones compartidos, los nuevos eventos cruciales publicados por Microsoft no se auditarán automáticamente en esos buzones.</span><span class="sxs-lookup"><span data-stu-id="9724f-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="9724f-123">Para información sobre cómo cambiar las acciones de buzón de correo que se auditan para cada tipo de inicio de sesión, consulte la sección "Cambiar o restaurar acciones de buzón registradas de forma predeterminada" en [Administrar la auditoría de buzón](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span><span class="sxs-lookup"><span data-stu-id="9724f-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="9724f-124">Paso 2: Habilitar eventos cruciales</span><span class="sxs-lookup"><span data-stu-id="9724f-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="9724f-125">Debe habilitar dos eventos cruciales (SearchQueryInitiatedExchange y SearchQueryInitiatedSharePoint) para registrar cuando los usuarios realizan búsquedas en Exchange Online y SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9724f-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="9724f-126">Para permitir que estos dos eventos se auditan para los usuarios, ejecute el siguiente comando (para cada usuario) [en Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="9724f-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="9724f-127">En un entorno multige geográfico, debe ejecutar el comando **Set-Mailbox** anterior en el bosque donde se encuentra el buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="9724f-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="9724f-128">Para identificar la ubicación del buzón del usuario, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9724f-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="9724f-129">Si el comando para habilitar la auditoría de las consultas de búsqueda se ejecutó anteriormente en un bosque que es diferente al que se encuentra en el buzón del usuario, debe quitar el valor SearchQueryInitiated del buzón del usuario ejecutándose y, a continuación, agregarlo al buzón del usuario en el bosque donde se encuentra el buzón del `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` usuario.</span><span class="sxs-lookup"><span data-stu-id="9724f-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="9724f-130">Paso 3: Configurar directivas de retención de auditoría</span><span class="sxs-lookup"><span data-stu-id="9724f-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="9724f-131">Además de la directiva predeterminada que conserva los registros de auditoría de Exchange, SharePoint y Azure AD durante un año, puede crear otras directivas de retención de registros de auditoría para cumplir los requisitos de los equipos de operaciones de seguridad, TI y cumplimiento de su organización.</span><span class="sxs-lookup"><span data-stu-id="9724f-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="9724f-132">Para obtener más información, vea [administrar directivas de retención de los registros de auditoría](audit-log-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9724f-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="9724f-133">Paso 4: Buscar eventos cruciales</span><span class="sxs-lookup"><span data-stu-id="9724f-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="9724f-134">Ahora que ya tiene la auditoría avanzada configurada para su organización, puede buscar eventos cruciales y otras actividades al llevar a cabo investigaciones forenses.</span><span class="sxs-lookup"><span data-stu-id="9724f-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="9724f-135">Después de completar los pasos 1 y 2, puede buscar en el registro de auditoría eventos cruciales y otras actividades durante las investigaciones forenses de cuentas comprometidas y otros tipos de investigaciones de seguridad o cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9724f-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="9724f-136">Para obtener más información acerca de la realización de una investigación forense de cuentas de usuario comprometidas mediante el evento crucial MailItemsAccessed, vea [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="9724f-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
