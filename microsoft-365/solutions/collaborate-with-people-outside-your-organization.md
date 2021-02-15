---
title: Colaborar con personas ajenas a la organización
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: Obtenga información sobre cómo configurar aplicaciones de Microsoft 365 como Teams, OneDrive y SharePoint para colaborar con personas ajenas a su organización.
ms.openlocfilehash: 374ad8f5ec37fc0900fb38cb4e0f4743a02c4da4
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613459"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="73d91-103">Colaborar con personas ajenas a la organización</span><span class="sxs-lookup"><span data-stu-id="73d91-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="73d91-104">Las capacidades de uso compartido externo de Microsoft 365 proporcionan una oportunidad para que las personas de su organización colaboren con socios, proveedores, clientes y otras personas que no tienen una cuenta en el directorio.</span><span class="sxs-lookup"><span data-stu-id="73d91-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="73d91-105">Puede compartir equipos o sitios completos con personas ajenas a la organización o solo archivos individuales.</span><span class="sxs-lookup"><span data-stu-id="73d91-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="73d91-106">La colaboración con personas ajenas a la organización consta de dos componentes principales:</span><span class="sxs-lookup"><span data-stu-id="73d91-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="73d91-107">**Habilitar el uso** compartido: configure los controles de uso compartido en Azure Active Directory, Teams, Grupos de Microsoft 365 y SharePoint para permitir el nivel de uso compartido que desea para su organización.</span><span class="sxs-lookup"><span data-stu-id="73d91-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="73d91-108">Habilitar seguridad **adicional:** aunque las características básicas de uso compartido se pueden configurar para requerir que las personas fuera de su organización se autentiquen, Microsoft 365 proporciona muchas características adicionales de seguridad y cumplimiento para ayudarle a proteger los datos y mantener las directivas de gobierno mientras se comparten externamente.</span><span class="sxs-lookup"><span data-stu-id="73d91-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="73d91-109">Habilitar el uso compartido</span><span class="sxs-lookup"><span data-stu-id="73d91-109">Enable sharing</span></span>

<span data-ttu-id="73d91-110">De forma predeterminada, en Microsoft 365, el uso compartido con personas de fuera de su organización está habilitado para SharePoint y OneDrive, pero deshabilitado para Teams.</span><span class="sxs-lookup"><span data-stu-id="73d91-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="73d91-111">Muchos escenarios de uso compartido externo de SharePoint y OneDrive funcionan sin ninguna configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="73d91-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="73d91-112">Para confirmar la configuración de un escenario que está usando o habilitar una nueva, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="73d91-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="73d91-113">[Colaborar en](collaborate-on-documents.md) documentos: obtenga información sobre cómo configurar Microsoft 365 para permitir el uso compartido y la colaboración con personas ajenas a la organización (invitados y usuarios no autenticados) en archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="73d91-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="73d91-114">[Colaborar en un sitio:](collaborate-in-site.md) aprenda a configurar Microsoft 365 para habilitar el uso compartido de sitios de SharePoint con invitados.</span><span class="sxs-lookup"><span data-stu-id="73d91-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="73d91-115">[Colaborar como equipo:](collaborate-as-team.md) obtenga información sobre cómo configurar Microsoft 365 para habilitar la colaboración de invitados en Teams.</span><span class="sxs-lookup"><span data-stu-id="73d91-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="73d91-116">Para obtener una visión completa de la configuración de uso compartido de invitados disponible en Microsoft 365, consulte la referencia de configuración de uso compartido de [invitados de Microsoft 365.](microsoft-365-guest-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73d91-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="73d91-117">Habilitar seguridad adicional</span><span class="sxs-lookup"><span data-stu-id="73d91-117">Enable additional security</span></span>

<span data-ttu-id="73d91-118">Una vez que haya habilitado el escenario que desea usar para compartir con personas de fuera de su organización, considere medidas de seguridad adicionales para ayudar a proteger su contenido del uso compartido inadecuado accidental o intencionado.</span><span class="sxs-lookup"><span data-stu-id="73d91-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="73d91-119">[Procedimientos recomendados para](best-practices-anonymous-sharing.md) compartir archivos y carpetas con usuarios no autenticados: obtenga información sobre los procedimientos recomendados para compartir con usuarios no autenticados.</span><span class="sxs-lookup"><span data-stu-id="73d91-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="73d91-120">[Limitar la exposición accidental:](share-limit-accidental-exposure.md) aprenda a reducir las posibilidades de compartir accidentalmente contenido confidencial con personas de fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="73d91-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="73d91-121">Crear un entorno de uso compartido de invitados seguro: obtenga información sobre las herramientas proporcionadas en Microsoft 365 para ayudar a garantizar que el uso compartido con personas ajenas [a](create-secure-guest-sharing-environment.md) su organización se realiza de forma segura y cumple los requisitos de gobierno.</span><span class="sxs-lookup"><span data-stu-id="73d91-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="73d91-122">Colaborar con empresas asociadas</span><span class="sxs-lookup"><span data-stu-id="73d91-122">Collaborate with partner companies</span></span>

<span data-ttu-id="73d91-123">Cuando trabaja en un proyecto grande en el que participan muchos invitados de otra organización, o si tiene una relación de proveedor continua en la que los invitados suelen cambiar, puede usar la administración de derechos en Azure Active Directory para simplificar la administración de invitados y permitir que la compañía asociada comparta esa responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="73d91-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="73d91-124">Consulte [Crear una extranet B2B con invitados administrados para](b2b-extranet.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="73d91-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="73d91-125">Limitar el uso compartido</span><span class="sxs-lookup"><span data-stu-id="73d91-125">Limit sharing</span></span>

<span data-ttu-id="73d91-126">Si algunas de las características de uso compartido de Microsoft 365 están en conflicto con las directivas de gobierno, vea Limitar el uso compartido en [Microsoft 365](microsoft-365-limit-sharing.md) para obtener información sobre las opciones para limitar el uso compartido.</span><span class="sxs-lookup"><span data-stu-id="73d91-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="73d91-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="73d91-127">Related topics</span></span>

[<span data-ttu-id="73d91-128">Introducción a la colaboración de archivos en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73d91-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="73d91-129">Planear la colaboración de archivos en SharePoint con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73d91-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
