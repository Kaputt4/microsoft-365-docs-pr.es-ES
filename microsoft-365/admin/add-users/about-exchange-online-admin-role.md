---
title: Acerca del rol de administrador de Exchange Online
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Los administradores de Exchange Online administran el correo electrónico y los buzones de la organización. Por ejemplo, recuperan elementos eliminados en el buzón de un usuario. '
ms.openlocfilehash: 8e332e886ca25221fefbbc5d1bb790bd4f513f00
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527518"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="102e3-104">Acerca del rol de administrador de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="102e3-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="102e3-105">Para ayudarle a administrar Microsoft 365, puede [asignar](assign-admin-roles.md) permisos a los usuarios para administrar el correo electrónico y los buzones de la organización desde el [centro de administración de Exchange](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span><span class="sxs-lookup"><span data-stu-id="102e3-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="102e3-106">Para ello, debe asignarlos al rol de administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="102e3-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="102e3-107">**Sugerencia**: cuando asigne a un usuario al rol de administrador de Exchange, asígnelos también al rol de administrador del servicio.</span><span class="sxs-lookup"><span data-stu-id="102e3-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="102e3-108">De este modo, pueden ver información importante en el centro de administración de Microsoft 365, como el estado del servicio de Exchange Online, y cambiar y publicar notificaciones.</span><span class="sxs-lookup"><span data-stu-id="102e3-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="102e3-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="102e3-109">Before you begin</span></span>

<span data-ttu-id="102e3-110">Estas son algunas de las tareas clave que los usuarios pueden realizar cuando se asignan al rol de administrador de Exchange:</span><span class="sxs-lookup"><span data-stu-id="102e3-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="102e3-111">Recuperar elementos eliminados en un buzón de usuario: ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="102e3-111">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/recover-deleted-items-in-a-mailbox)

- <span data-ttu-id="102e3-112">[Configurar una directiva de archivo y eliminación para los buzones de la organización](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="102e3-112">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>

- <span data-ttu-id="102e3-113">Configurar características de buzón de correo, como la Directiva de uso compartido de buzones: cómo los usuarios pueden compartir información de calendario y contactos con otras personas fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="102e3-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="102e3-114">Configure delegados "[Enviar como](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" y "[enviar en nombre](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)de" para el buzón de un usuario.</span><span class="sxs-lookup"><span data-stu-id="102e3-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="102e3-115">Por ejemplo, es posible que un ejecutivo desee que su asistente tenga la capacidad de enviar correo en su nombre.</span><span class="sxs-lookup"><span data-stu-id="102e3-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="102e3-116">[Crear un buzón compartido](../email/create-a-shared-mailbox.md) para que un grupo de personas pueda supervisar y enviar correo electrónico desde una dirección de correo electrónico común.</span><span class="sxs-lookup"><span data-stu-id="102e3-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="102e3-117">Filtros de malware y [protección contra correo no deseado de correo electrónico](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) para la organización.</span><span class="sxs-lookup"><span data-stu-id="102e3-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="102e3-118">Administrar grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="102e3-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="102e3-119">Grupos de roles de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="102e3-119">Exchange Online role groups</span></span>

<span data-ttu-id="102e3-120">Si tiene una organización grande, es posible que el administrador de Exchange desee asignar usuarios a grupos de roles de Exchange.</span><span class="sxs-lookup"><span data-stu-id="102e3-120">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups.</span></span> <span data-ttu-id="102e3-121">Cuando un administrador agrega un usuario a un grupo de funciones, el usuario obtiene permisos para realizar determinadas funciones empresariales solo pueden hacer los miembros de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="102e3-121">When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="102e3-122">Por ejemplo, el administrador de Exchange podría asignar a un usuario al grupo de roles de administración de detección para que pueda realizar búsquedas en los buzones de datos que cumplan determinados criterios.</span><span class="sxs-lookup"><span data-stu-id="102e3-122">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria.</span></span> <span data-ttu-id="102e3-123">Para obtener más información, consulte [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) y [Manage role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="102e3-123">To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="102e3-124">Obtener información sobre otros roles de administrador</span><span class="sxs-lookup"><span data-stu-id="102e3-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="102e3-125">Acerca de los roles de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="102e3-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="102e3-126">Acerca del rol de administrador de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="102e3-126">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="102e3-127">Acerca del rol de administrador de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="102e3-127">About the Skype for Business admin role</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="102e3-128">Usar el rol de administrador de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="102e3-128">Use Microsoft Teams admin role</span></span>](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles) 
