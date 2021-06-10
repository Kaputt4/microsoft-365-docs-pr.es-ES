---
title: Restringir el acceso a los temas de Temas de Microsoft Viva
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
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500880"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="4fd1e-103">Restringir el acceso a los temas de Temas de Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="4fd1e-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="4fd1e-104">En Microsoft Viva, es posible que las partes interesadas de la organización quieran asegurarse de que los temas específicos no se descubran y se exponan a los usuarios con licencia.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="4fd1e-105">Por ejemplo, es posible que esté trabajando en un proyecto sobre el que aún no desea exponer ninguna información.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="4fd1e-106">Aunque Office 365 permisos en sitios, archivos y otros recursos impedirán que los usuarios de Experiencias de tema puedan ver información confidencial en los temas, existen medidas de seguridad adicionales para evitar que se descubran temas específicos.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="4fd1e-107">Aunque los administradores de conocimientos controlan la configuración para evitar que se descubran los temas, los administradores de conocimientos y otras partes interesadas necesitan saber cómo se hace para que puedan trabajar en colaboración.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-107">While knowledge admins control the settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="4fd1e-108">En este artículo se describen maneras de evitar que los temas se identifiquen a través de la IA o se visualizó en su entorno como una protección de seguridad adicional.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="4fd1e-109">Es importante tener en cuenta que, en Temas de Viva, los usuarios no pueden ver nada en un tema al que no se les permite acceder a través de Office 365 permisos.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="4fd1e-110">Incluso si un usuario es capaz de ver un tema, sus archivos, sitios y páginas que no tienen Office 365 permisos para ver no serán visibles para ellos.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="4fd1e-111">Asegurarse de que los permisos de los archivos confidenciales están configurados correctamente debe ser la protección de seguridad principal.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="4fd1e-112">Impedir que los temas se identifiquen</span><span class="sxs-lookup"><span data-stu-id="4fd1e-112">Prevent topics from being identified</span></span>

<span data-ttu-id="4fd1e-113">El administrador de conocimientos puede restringir el acceso a temas específicos impidiendo que se puedan encontrar en la indización inicial.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="4fd1e-114">Hay dos maneras de realizar esta tarea en la configuración de administración de Temas de Viva en el centro Microsoft 365 administración.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-114">There are two ways to do this task in the Viva Topics admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="4fd1e-115">[Seleccione SharePoint sitios para excluir](./topic-experiences-discovery.md#select-sharepoint-topic-sources)de la detección de temas: puede usar esta configuración para evitar que sitios de SharePoint específicos se rastreen para los temas.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-115">[Select SharePoint sites to exclude from topic discovery](./topic-experiences-discovery.md#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="4fd1e-116">[Excluir temas por nombre:](./topic-experiences-discovery.md#exclude-topics-by-name)los administradores pueden usar esta configuración para evitar que determinados temas se descubran por su nombre.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-116">[Exclude topics by name](./topic-experiences-discovery.md#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="4fd1e-117">En la configuración de administración de Temas de Viva, un administrador puede cargar una lista de temas que se excluirán en un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-117">In the Viva Topics admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="4fd1e-118">Puede excluir temas que tengan coincidencias exactas o parciales de un nombre de tema.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="4fd1e-119">Impedir que los usuarios específicos puedan ver temas</span><span class="sxs-lookup"><span data-stu-id="4fd1e-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="4fd1e-120">Los administradores de conocimientos también [pueden seleccionar quién puede ver los temas de su organización.](./topic-experiences-knowledge-rules.md)</span><span class="sxs-lookup"><span data-stu-id="4fd1e-120">Knowledge admins can also [select who can view topics in your organization](./topic-experiences-knowledge-rules.md).</span></span> <span data-ttu-id="4fd1e-121">Esta configuración le permite seleccionar qué usuarios con licencia pueden ver todos los temas.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="4fd1e-122">Por ejemplo, en un entorno piloto, es posible que solo desee permitir que un pequeño grupo de usuarios pueda ver temas.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="4fd1e-123">Quitar temas de visualización</span><span class="sxs-lookup"><span data-stu-id="4fd1e-123">Remove topics from being viewed</span></span>

<span data-ttu-id="4fd1e-124">Los administradores de conocimientos pueden [elegir quitar temas](./manage-topics.md) para que los usuarios ya no puedan verlos.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-124">Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them.</span></span> <span data-ttu-id="4fd1e-125">En la **página Administrar temas** del Centro de temas, los administradores de conocimientos pueden optar por rechazar temas específicos para evitar que se puedan ver. </span><span class="sxs-lookup"><span data-stu-id="4fd1e-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="4fd1e-126">Los temas se pueden quitar independientemente de si están en un estado sugerido o confirmado.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="4fd1e-127">Los temas eliminados se pueden agregar más adelante como temas que se pueden ver si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4fd1e-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="4fd1e-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4fd1e-128">See also</span></span>



