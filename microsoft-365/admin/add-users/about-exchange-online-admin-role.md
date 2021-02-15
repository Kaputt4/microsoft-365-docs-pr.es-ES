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
description: 'Los administradores de Exchange Online administran el correo electrónico y los buzones de correo de su organización. Por ejemplo, recuperan elementos eliminados en el buzón de un usuario. '
ms.openlocfilehash: 8e332e886ca25221fefbbc5d1bb790bd4f513f00
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527518"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="08c6c-104">Acerca del rol de administrador de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08c6c-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="08c6c-105">Para ayudarle a administrar Microsoft 365, puede asignar a los usuarios permisos para administrar el correo electrónico y los buzones de correo de su organización desde el [Centro de administración de Exchange.](https://go.microsoft.com/fwlink/p/?LinkID=271807) [](assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="08c6c-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="08c6c-106">Para ello, asígnelos al rol de administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="08c6c-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="08c6c-107">**Sugerencia:** Cuando asigne a alguien al rol de administrador de Exchange, también puede asignarlo al rol de administrador del servicio.</span><span class="sxs-lookup"><span data-stu-id="08c6c-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="08c6c-108">De esta forma, pueden ver información importante en el Centro de administración de Microsoft 365, como el estado del servicio Exchange Online, y cambiar y publicar notificaciones.</span><span class="sxs-lookup"><span data-stu-id="08c6c-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="08c6c-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="08c6c-109">Before you begin</span></span>

<span data-ttu-id="08c6c-110">Estas son algunas de las tareas clave que los usuarios pueden realizar cuando se les asigna el rol de administrador de Exchange:</span><span class="sxs-lookup"><span data-stu-id="08c6c-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="08c6c-111">Recuperar elementos eliminados en un buzón de usuario: ayuda para administradores</span><span class="sxs-lookup"><span data-stu-id="08c6c-111">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/recover-deleted-items-in-a-mailbox)

- <span data-ttu-id="08c6c-112">[Configure una directiva de archivo y eliminación para los buzones de la organización.](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="08c6c-112">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>

- <span data-ttu-id="08c6c-113">Configure características de buzón como la directiva de uso compartido de buzones: cómo los usuarios pueden compartir información de calendario y contactos con otras personas fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="08c6c-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="08c6c-114">Configure los[delegados](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" Enviar como " y["Enviar en](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)nombre de" para el buzón de correo de alguien.</span><span class="sxs-lookup"><span data-stu-id="08c6c-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="08c6c-115">Por ejemplo, un ejecutivo puede querer que su asistente tenga la capacidad de enviar correo en su nombre.</span><span class="sxs-lookup"><span data-stu-id="08c6c-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="08c6c-116">[Cree un buzón compartido para](../email/create-a-shared-mailbox.md) que un grupo de personas pueda supervisar y enviar correo electrónico desde una dirección de correo electrónico común.</span><span class="sxs-lookup"><span data-stu-id="08c6c-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="08c6c-117">[Protección contra correo electrónico no deseado y](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) filtros de malware para la organización.</span><span class="sxs-lookup"><span data-stu-id="08c6c-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="08c6c-118">Administrar grupos de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="08c6c-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="08c6c-119">Grupos de roles de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="08c6c-119">Exchange Online role groups</span></span>

<span data-ttu-id="08c6c-120">Si tiene una organización grande, es posible que el administrador de Exchange desee asignar usuarios a grupos de roles de Exchange.</span><span class="sxs-lookup"><span data-stu-id="08c6c-120">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups.</span></span> <span data-ttu-id="08c6c-121">Cuando un administrador agrega un usuario a un grupo de roles, el usuario obtiene permisos para realizar determinadas funciones empresariales que solo pueden hacer los miembros de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="08c6c-121">When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="08c6c-122">Por ejemplo, el administrador de Exchange puede asignar a alguien al grupo de roles Administración de detección para que pueda realizar búsquedas de buzones de datos que cumplan ciertos criterios.</span><span class="sxs-lookup"><span data-stu-id="08c6c-122">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria.</span></span> <span data-ttu-id="08c6c-123">Para obtener más información, [consulte Permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) y Administrar grupos de [roles.](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="08c6c-123">To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="08c6c-124">Más información sobre otros roles de administrador</span><span class="sxs-lookup"><span data-stu-id="08c6c-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="08c6c-125">Acerca de los roles de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="08c6c-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="08c6c-126">Acerca del rol de administrador de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c6c-126">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="08c6c-127">Acerca del rol de administrador de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="08c6c-127">About the Skype for Business admin role</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="08c6c-128">Usar el rol de administrador de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08c6c-128">Use Microsoft Teams admin role</span></span>](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles) 
