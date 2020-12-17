---
title: Restringir el acceso a los temas
description: Cómo excluir temas para evitar que se detecten.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699066"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="89793-103">Restringir el acceso a temas en experiencias de temas</span><span class="sxs-lookup"><span data-stu-id="89793-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="89793-104">En las experiencias de los temas, es posible que las partes interesadas de la organización deseen asegurarse de que no se detecten temas específicos y que se expongan a los usuarios con licencia.</span><span class="sxs-lookup"><span data-stu-id="89793-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="89793-105">Por ejemplo, puede estar trabajando en un proyecto en el que no desea exponer información todavía.</span><span class="sxs-lookup"><span data-stu-id="89793-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="89793-106">Aunque los permisos de Office 365 en sitios, archivos y otros recursos impiden que los usuarios vean información confidencial en los temas, existen protecciones adicionales para evitar que se detecten temas específicos.</span><span class="sxs-lookup"><span data-stu-id="89793-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="89793-107">Mientras que los administradores de conocimientos controlan la configuración de la red de conocimiento para evitar que se detecten temas, los administradores de conocimiento y otras partes interesadas deben saber cómo se realiza esta tarea para que puedan trabajar en colaboración.</span><span class="sxs-lookup"><span data-stu-id="89793-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="89793-108">En este artículo se describen formas de evitar que los temas se identifiquen a través de AI o que se vean en el entorno como protección de seguridad adicional.</span><span class="sxs-lookup"><span data-stu-id="89793-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="89793-109">Es importante tener en cuenta que en las experiencias de los temas, los usuarios no tienen permiso para ver nada en un tema que no tienen permiso de acceso a través de los permisos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="89793-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="89793-110">Incluso si un usuario puede ver un tema, los archivos, los sitios y las páginas que no tienen permisos de Office 365 para ver no serán visibles para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="89793-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="89793-111">Asegurarse de que los permisos para los archivos confidenciales se establezcan correctamente debe ser la protección de seguridad principal.</span><span class="sxs-lookup"><span data-stu-id="89793-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="89793-112">Impedir la identificación de los temas</span><span class="sxs-lookup"><span data-stu-id="89793-112">Prevent topics from being identified</span></span>

<span data-ttu-id="89793-113">El administrador de conocimiento puede restringir el acceso a temas específicos evitando que se encuentren en la indización inicial.</span><span class="sxs-lookup"><span data-stu-id="89793-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="89793-114">Hay dos formas de hacerlo en la configuración de administración de la red de conocimientos en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89793-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="89793-115">[Seleccione sitios de SharePoint para excluirlos del descubrimiento de](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)temas: puede usar esta opción para evitar que se rastreen sitios específicos de SharePoint en busca de temas.</span><span class="sxs-lookup"><span data-stu-id="89793-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="89793-116">[Excluir temas por nombre](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): los administradores pueden usar esta configuración para evitar que se detecten temas específicos por nombre.</span><span class="sxs-lookup"><span data-stu-id="89793-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="89793-117">En la configuración de administración de la red de conocimiento, un administrador puede cargar una lista de temas que se excluirán en un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="89793-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="89793-118">Puede excluir los temas que contengan coincidencias exactas o parciales de un nombre de tema.</span><span class="sxs-lookup"><span data-stu-id="89793-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="89793-119">Impedir que determinados usuarios vean los temas</span><span class="sxs-lookup"><span data-stu-id="89793-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="89793-120">Los administradores del conocimiento también pueden [seleccionar quién puede ver los temas de la organización](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span><span class="sxs-lookup"><span data-stu-id="89793-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="89793-121">Esta opción le permite seleccionar qué usuarios con licencia pueden ver todos los temas.</span><span class="sxs-lookup"><span data-stu-id="89793-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="89793-122">Por ejemplo, en un entorno piloto, es posible que quiera permitir que un pequeño grupo de usuarios pueda ver temas.</span><span class="sxs-lookup"><span data-stu-id="89793-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="89793-123">Quitar temas que se van a ver</span><span class="sxs-lookup"><span data-stu-id="89793-123">Remove topics from being viewed</span></span>

<span data-ttu-id="89793-124">Los administradores de conocimiento pueden elegir [quitar temas](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) para que los usuarios ya no puedan verlos.</span><span class="sxs-lookup"><span data-stu-id="89793-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="89793-125">En la página **administrar temas** del **Centro** de temas, los administradores de conocimiento pueden rechazar temas específicos para evitar que se vean.</span><span class="sxs-lookup"><span data-stu-id="89793-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="89793-126">Los temas se pueden quitar independientemente de si están en un estado sugerido o confirmado.</span><span class="sxs-lookup"><span data-stu-id="89793-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="89793-127">Los temas eliminados se pueden volver a agregar posteriormente como temas visibles si es necesario.</span><span class="sxs-lookup"><span data-stu-id="89793-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="89793-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89793-128">See also</span></span>



  






