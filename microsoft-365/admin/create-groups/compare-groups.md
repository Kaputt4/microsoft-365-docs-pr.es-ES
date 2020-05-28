---
title: Comparar grupos
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Obtenga más información sobre los tipos de grupos que puede usar.
ms.openlocfilehash: b81bb09efedc503b49d2ed4aa10b1e7153116f14
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44388034"
---
# <a name="compare-groups"></a><span data-ttu-id="085e4-103">Comparar grupos</span><span class="sxs-lookup"><span data-stu-id="085e4-103">Compare groups</span></span>

<span data-ttu-id="085e4-104">En la sección **Grupos** del Centro de administración de Microsoft 365, puede crear y administrar estos tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="085e4-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="085e4-105">**Los grupos de Microsoft 365** se usan para la colaboración entre usuarios, tanto dentro como fuera de la compañía.</span><span class="sxs-lookup"><span data-stu-id="085e4-105">**Microsoft 365 groups** are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="085e4-106">**Los grupos de distribución** se usan para enviar notificaciones a un grupo de personas.</span><span class="sxs-lookup"><span data-stu-id="085e4-106">**Distribution groups** are used for sending notifications to a group of people.</span></span>
- <span data-ttu-id="085e4-107">**Los grupos de seguridad** se usan para conceder acceso a los recursos como SharePoint.</span><span class="sxs-lookup"><span data-stu-id="085e4-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="085e4-108">**Los grupos de seguridad habilitados para correo** se usan para conceder acceso a recursos como SharePoint y enviar notificaciones por correo electrónico a estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="085e4-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="085e4-109">**Los buzones compartidos** se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico e información de la empresa.</span><span class="sxs-lookup"><span data-stu-id="085e4-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="microsoft-365-groups"></a><span data-ttu-id="085e4-110">Grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="085e4-110">Microsoft 365 groups</span></span>

<span data-ttu-id="085e4-111">Los grupos de Microsoft 365 se usan para la colaboración entre usuarios, tanto dentro como fuera de la compañía.</span><span class="sxs-lookup"><span data-stu-id="085e4-111">Microsoft 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="085e4-112">Con cada grupo de Microsoft 365, los miembros obtienen un correo electrónico de grupo y un área de trabajo compartida para las conversaciones, los archivos y los eventos de calendario y un Planner.</span><span class="sxs-lookup"><span data-stu-id="085e4-112">With each Microsoft 365 group, members get a group email and shared workspace for conversations, files, and calendar events, and a Planner.</span></span>

<span data-ttu-id="085e4-113">Puede agregar personas externas a su empresa a un grupo siempre y cuando esta opción se haya [habilitado por parte del administrador](manage-guest-access-in-groups.md).</span><span class="sxs-lookup"><span data-stu-id="085e4-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="085e4-114">También puede permitir que los remitentes externos puedan enviar correos electrónicos a la dirección de correo electrónico del grupo.</span><span class="sxs-lookup"><span data-stu-id="085e4-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="085e4-115">Los grupos de Microsoft 365 se pueden [configurar para la pertenencia dinámica en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), lo que permite que los miembros del grupo se agreguen o eliminen automáticamente en función de los atributos del usuario como el departamento, la ubicación, el puesto, etc.</span><span class="sxs-lookup"><span data-stu-id="085e4-115">Microsoft 365 groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="085e4-116">Se puede tener acceso a los grupos de Microsoft 365 a través de aplicaciones móviles como Outlook para iOS y Outlook para Android.</span><span class="sxs-lookup"><span data-stu-id="085e4-116">Microsoft 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="085e4-117">Los miembros del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del grupo si está opción ha sido [activada por el administrador](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span><span class="sxs-lookup"><span data-stu-id="085e4-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="085e4-118">Grupos de distribución</span><span class="sxs-lookup"><span data-stu-id="085e4-118">Distribution groups</span></span>

<span data-ttu-id="085e4-119">[Los grupos de distribución](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) se usan para enviar notificaciones a un grupo de personas.</span><span class="sxs-lookup"><span data-stu-id="085e4-119">[Distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="085e4-120">Pueden recibir correo electrónico externo si lo habilita el administrador.</span><span class="sxs-lookup"><span data-stu-id="085e4-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="085e4-121">Los grupos de distribución son mejores para las situaciones en las que necesita transmitir información a un grupo definido de personas, como "Usuarios del edificio A" o "Todos los usuarios de Contoso".</span><span class="sxs-lookup"><span data-stu-id="085e4-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

## <a name="security-groups"></a><span data-ttu-id="085e4-122">Grupos de seguridad</span><span class="sxs-lookup"><span data-stu-id="085e4-122">Security groups</span></span>

<span data-ttu-id="085e4-123">[Los grupos de seguridad](../email/create-edit-or-delete-a-security-group.md) se usan para conceder acceso a los recursos de Microsoft 365, como SharePoint.</span><span class="sxs-lookup"><span data-stu-id="085e4-123">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Microsoft 365 resources, such as SharePoint.</span></span> <span data-ttu-id="085e4-124">Pueden simplificar la administración, ya que solo necesita administrar el grupo, en lugar de agregar usuarios a cada recurso por separado.</span><span class="sxs-lookup"><span data-stu-id="085e4-124">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="085e4-125">Los grupos de seguridad pueden contener usuarios o dispositivos.</span><span class="sxs-lookup"><span data-stu-id="085e4-125">Security groups can contain users or devices.</span></span> <span data-ttu-id="085e4-126">Se puede usar la creación de un grupo de seguridad para dispositivos con servicios de administración de dispositivos móviles, como Intune.</span><span class="sxs-lookup"><span data-stu-id="085e4-126">Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="085e4-127">Los grupos de seguridad se pueden [configuran para la pertenencia dinámica en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), lo que permite que los miembros del grupo o los dispositivos se agreguen o eliminen automáticamente en función de los atributos del usuario, como el departamento, la ubicación o el título; o los atributos del dispositivo, como la versión del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="085e4-127">Security groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="085e4-128">Grupos de seguridad habilitados para correo</span><span class="sxs-lookup"><span data-stu-id="085e4-128">Mail-enabled security groups</span></span>

<span data-ttu-id="085e4-129">Los grupos de seguridad habilitados para correo funcionan de la misma manera que los grupos de seguridad normales, excepto que no se pueden administrar dinámicamente a través de Azure Active Directory y no pueden contener dispositivos.</span><span class="sxs-lookup"><span data-stu-id="085e4-129">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="085e4-130">Incluyen la capacidad para enviar correo a todos los miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="085e4-130">They include the ability to send mail to all the members of the group.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="085e4-131">Buzones compartidos</span><span class="sxs-lookup"><span data-stu-id="085e4-131">Shared mailboxes</span></span>

<span data-ttu-id="085e4-132">[Los buzones compartidos](../email/create-a-shared-mailbox.md) se usan cuando varios usuarios necesitan tener acceso al mismo buzón, como la dirección de correo electrónico del soporte técnico o información de la empresa, el escritorio de recepción u otra función que puedan compartir varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="085e4-132">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="085e4-133">Los buzones compartidos pueden recibir mensajes externos si el administrador ha habilitado esta opción.</span><span class="sxs-lookup"><span data-stu-id="085e4-133">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="085e4-134">Los usuarios con permisos para el buzón del grupo pueden enviar como o enviar en nombre de la dirección de correo electrónico del buzón si el administrador le ha concedido permisos de usuario para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="085e4-134">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="085e4-135">Esto es especialmente útil para los buzones de ayuda y soporte técnico, ya que los usuarios pueden enviar mensajes de correo electrónico desde "Soporte técnico de Contoso" o "Escritorio de recepción del edificio A".</span><span class="sxs-lookup"><span data-stu-id="085e4-135">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="085e4-136">Actualmente, no es posible migrar un buzón compartido a un grupo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="085e4-136">Currently it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="085e4-137">¿Le gustaría que fuese posible?</span><span class="sxs-lookup"><span data-stu-id="085e4-137">Is this something you want?</span></span> <span data-ttu-id="085e4-138">Infórmenos.</span><span class="sxs-lookup"><span data-stu-id="085e4-138">Let us know.</span></span> <span data-ttu-id="085e4-139">**[Vote aquí](https://go.microsoft.com/fwlink/?linkid=871518)**.</span><span class="sxs-lookup"><span data-stu-id="085e4-139">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="085e4-140">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="085e4-140">Related articles</span></span>

[<span data-ttu-id="085e4-141">Obtener más información sobre los grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="085e4-141">Learn about Microsoft 365 groups</span></span>](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
