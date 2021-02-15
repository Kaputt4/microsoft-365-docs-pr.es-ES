---
title: Restringir el acceso a los temas de Los temas de Microsoft Viva
description: Cómo excluir temas para evitar que se descubran.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 6b3d2a4b6cbfc67623cea58b73681b7af7cc4889
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107163"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="6f060-103">Restringir el acceso a los temas de Los temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="6f060-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="6f060-104">En Microsoft Viva, es posible que las partes interesadas de su organización quieran asegurarse de que no se descubran temas específicos y se exponicen a los usuarios con licencia.</span><span class="sxs-lookup"><span data-stu-id="6f060-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="6f060-105">Por ejemplo, es posible que esté trabajando en un proyecto sobre el que aún no desea exponer información.</span><span class="sxs-lookup"><span data-stu-id="6f060-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="6f060-106">Aunque los permisos de Office 365 en sitios, archivos y otros recursos impedirán que los usuarios de experiencias de tema puedan ver información confidencial en los temas, existen medidas de seguridad adicionales para evitar que se descubran temas específicos.</span><span class="sxs-lookup"><span data-stu-id="6f060-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="6f060-107">Aunque los administradores de conocimientos controlan la configuración de la red de conocimiento para evitar que se descubran temas, los administradores de conocimientos y otras partes interesadas necesitan saber cómo se hace para que puedan trabajar en colaboración.</span><span class="sxs-lookup"><span data-stu-id="6f060-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="6f060-108">En este artículo se describen formas de evitar que los temas se identifiquen a través de la inteligencia artificial o se visualmente en su entorno como una protección de seguridad adicional.</span><span class="sxs-lookup"><span data-stu-id="6f060-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="6f060-109">Es importante tener en cuenta que en Temas Viva, los usuarios no pueden ver nada en un tema al que no tienen permiso de acceso a través de los permisos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f060-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="6f060-110">Incluso si un usuario puede ver un tema, sus archivos, sitios y páginas que no tienen permisos de Office 365 para ver no serán visibles para ellos.</span><span class="sxs-lookup"><span data-stu-id="6f060-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="6f060-111">Asegurarse de que los permisos de los archivos confidenciales están correctamente establecidos debe ser la protección de seguridad principal.</span><span class="sxs-lookup"><span data-stu-id="6f060-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="6f060-112">Impedir que se identifiquen los temas</span><span class="sxs-lookup"><span data-stu-id="6f060-112">Prevent topics from being identified</span></span>

<span data-ttu-id="6f060-113">El administrador del conocimiento puede restringir el acceso a temas específicos impidiendo que se encuentran en la indización inicial.</span><span class="sxs-lookup"><span data-stu-id="6f060-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="6f060-114">Hay dos formas de realizar esta tarea en la configuración de administración de Knowledge Network en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f060-114">There are two ways to do this task in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="6f060-115">[Seleccione sitios de SharePoint para excluirlos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)de la detección de temas: puede usar esta configuración para evitar que determinados sitios de SharePoint se rastreen en temas.</span><span class="sxs-lookup"><span data-stu-id="6f060-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="6f060-116">[Excluir temas por nombre:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)los administradores pueden usar esta configuración para evitar que determinados temas se descubran por nombre.</span><span class="sxs-lookup"><span data-stu-id="6f060-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="6f060-117">En la configuración de administración de Knowledge Network, un administrador puede cargar una lista de temas que se excluirán en un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="6f060-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="6f060-118">Puede excluir los temas que tengan coincidencias exactas o parciales de un nombre de tema.</span><span class="sxs-lookup"><span data-stu-id="6f060-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="6f060-119">Impedir que usuarios específicos puedan ver los temas</span><span class="sxs-lookup"><span data-stu-id="6f060-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="6f060-120">Los administradores de conocimientos [también pueden seleccionar quién puede ver los temas de su organización.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="6f060-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="6f060-121">Esta configuración le permite seleccionar qué usuarios con licencia pueden ver todos los temas.</span><span class="sxs-lookup"><span data-stu-id="6f060-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="6f060-122">Por ejemplo, en un entorno piloto, es posible que solo desee permitir que un pequeño grupo de usuarios pueda ver temas.</span><span class="sxs-lookup"><span data-stu-id="6f060-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="6f060-123">Quitar temas de la visualización</span><span class="sxs-lookup"><span data-stu-id="6f060-123">Remove topics from being viewed</span></span>

<span data-ttu-id="6f060-124">Los administradores de conocimientos [pueden elegir quitar temas](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) para que los usuarios ya no puedan verlos.</span><span class="sxs-lookup"><span data-stu-id="6f060-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="6f060-125">En la **página Administrar temas** del Centro de temas, los administradores de conocimientos pueden elegir rechazar temas específicos para evitar que se puedan ver. </span><span class="sxs-lookup"><span data-stu-id="6f060-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="6f060-126">Los temas se pueden quitar independientemente de si están en un estado sugerido o confirmado.</span><span class="sxs-lookup"><span data-stu-id="6f060-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="6f060-127">Los temas eliminados se pueden volver a agregar más adelante como temas visualizables si es necesario.</span><span class="sxs-lookup"><span data-stu-id="6f060-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="6f060-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f060-128">See also</span></span>



  






