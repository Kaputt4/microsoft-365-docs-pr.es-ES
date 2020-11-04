---
title: Colaborar con personas fuera de la organización
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: Obtenga información sobre cómo configurar las aplicaciones de Microsoft 365 como Teams, OneDrive y SharePoint para la colaboración con personas de fuera de la organización.
ms.openlocfilehash: 9a15ea06cec6982977ec88edf5ee95b35591a33c
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906994"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="f467b-103">Colaborar con personas fuera de la organización</span><span class="sxs-lookup"><span data-stu-id="f467b-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="f467b-104">Las capacidades de uso compartido externo de Microsoft 365 proporcionan una oportunidad para que los usuarios de su organización colaboren con socios, proveedores, clientes y otros usuarios que no tengan una cuenta en su directorio.</span><span class="sxs-lookup"><span data-stu-id="f467b-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="f467b-105">Puede compartir los equipos o sitios completos con personas de fuera de la organización, o solo con archivos individuales.</span><span class="sxs-lookup"><span data-stu-id="f467b-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="f467b-106">La colaboración con personas fuera de la organización consta de dos componentes principales:</span><span class="sxs-lookup"><span data-stu-id="f467b-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="f467b-107">**Habilitar uso compartido** : Configure los controles de uso compartido en Azure Active Directory, Teams, Microsoft 365 Groups y SharePoint para permitir el nivel de uso compartido que desea para su organización.</span><span class="sxs-lookup"><span data-stu-id="f467b-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="f467b-108">**Habilitar seguridad adicional** : mientras que las características básicas de uso compartido se pueden configurar para que los usuarios externos a la organización puedan autenticarse, Microsoft 365 ofrece muchas características adicionales de seguridad y cumplimiento para ayudarle a proteger sus datos y mantener sus directivas de Gobierno mientras comparte de forma externa.</span><span class="sxs-lookup"><span data-stu-id="f467b-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="f467b-109">Habilitar el uso compartido</span><span class="sxs-lookup"><span data-stu-id="f467b-109">Enable sharing</span></span>

<span data-ttu-id="f467b-110">De forma predeterminada, en Microsoft 365, el uso compartido con personas de fuera de la organización está habilitado para SharePoint y OneDrive, pero está deshabilitado para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f467b-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="f467b-111">Muchos escenarios de uso compartido externo de SharePoint y SharePoint funcionan sin una configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="f467b-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="f467b-112">Para confirmar la configuración de un escenario que está usando o para habilitar una nueva, elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f467b-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="f467b-113">[Colaborar en documentos](collaborate-on-documents.md) : Obtenga información sobre cómo configurar Microsoft 365 para permitir el uso compartido y la colaboración con personas de fuera de la organización (tanto invitados como no autenticados) en archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="f467b-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="f467b-114">[Colaborar en un sitio](collaborate-in-site.md) : Obtenga información sobre cómo configurar Microsoft 365 para habilitar el uso compartido de sitios de SharePoint con invitados.</span><span class="sxs-lookup"><span data-stu-id="f467b-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="f467b-115">[Colaborar como un equipo](collaborate-as-team.md) : Obtenga información sobre cómo configurar Microsoft 365 para habilitar la colaboración de invitado en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f467b-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="f467b-116">Para obtener una visión completa de la configuración de uso compartido de invitados disponible en Microsoft 365, consulte [microsoft 365 Guest Sharing Settings Reference](microsoft-365-guest-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f467b-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="f467b-117">Habilitar seguridad adicional</span><span class="sxs-lookup"><span data-stu-id="f467b-117">Enable additional security</span></span>

<span data-ttu-id="f467b-118">Una vez que haya habilitado el escenario que desea usar para el uso compartido con personas de fuera de la organización, considere otras medidas de protección para proteger el contenido de un uso compartido inapropiado o accidental o intencionado.</span><span class="sxs-lookup"><span data-stu-id="f467b-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="f467b-119">[Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md) : Obtenga información sobre los procedimientos recomendados para compartir con usuarios no autenticados.</span><span class="sxs-lookup"><span data-stu-id="f467b-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="f467b-120">[Limitar exposición accidental](share-limit-accidental-exposure.md) : Obtenga información sobre cómo reducir las posibilidades de compartir accidentalmente contenido confidencial con personas de fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="f467b-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="f467b-121">[Crear un entorno de uso compartido de invitado seguro](create-secure-guest-sharing-environment.md) : Obtenga información sobre las herramientas proporcionadas en Microsoft 365 para ayudar a garantizar que el uso compartido con personas de fuera de la organización se realiza de forma segura y segura, y cumple los requisitos de gobierno.</span><span class="sxs-lookup"><span data-stu-id="f467b-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="f467b-122">Colaborar con empresas asociadas</span><span class="sxs-lookup"><span data-stu-id="f467b-122">Collaborate with partner companies</span></span>

<span data-ttu-id="f467b-123">Cuando trabaja en un proyecto grande que involucra a muchos invitados de otra organización, o si tiene una relación de proveedor continua en la que los invitados suelen cambiar, puede usar la administración de derechos en Azure Active Directory para simplificar la administración de invitados y permitir que la empresa asociada comparta en esa responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="f467b-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="f467b-124">Consulte [Create a B2B extranet with Managed Guests](b2b-extranet.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f467b-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="f467b-125">Limitar el uso compartido</span><span class="sxs-lookup"><span data-stu-id="f467b-125">Limit sharing</span></span>

<span data-ttu-id="f467b-126">Si algunas de las características de uso compartido de Microsoft 365 entran en conflicto con las directivas de gobierno, vea [limitar el uso compartido en microsoft 365](microsoft-365-limit-sharing.md) para obtener información sobre las opciones para limitar el uso compartido.</span><span class="sxs-lookup"><span data-stu-id="f467b-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f467b-127">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f467b-127">Related topics</span></span>

[<span data-ttu-id="f467b-128">Introducción a la colaboración de archivos en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f467b-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="f467b-129">Planeación de la colaboración de archivos en SharePoint con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f467b-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
