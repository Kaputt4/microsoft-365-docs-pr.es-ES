---
title: Cifrado de servicio
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: comprenda la resistencia de datos en Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058553"
---
# <a name="service-encryption"></a><span data-ttu-id="11ddf-103">Cifrado de servicio</span><span class="sxs-lookup"><span data-stu-id="11ddf-103">Service Encryption</span></span>

<span data-ttu-id="11ddf-104">Además de usar el cifrado de nivel de volumen, Exchange Online, Microsoft Teams, SharePoint Online y OneDrive para la Empresa también usan el cifrado de servicio para cifrar los datos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="11ddf-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="11ddf-105">El cifrado de servicio permite dos opciones de administración de claves:</span><span class="sxs-lookup"><span data-stu-id="11ddf-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="11ddf-106">Claves administradas por Microsoft</span><span class="sxs-lookup"><span data-stu-id="11ddf-106">Microsoft-managed keys</span></span>
<span data-ttu-id="11ddf-107">Microsoft administra todas las claves criptográficas, incluidas las claves raíz para el cifrado del servicio.</span><span class="sxs-lookup"><span data-stu-id="11ddf-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="11ddf-108">Esta opción está habilitada actualmente de forma predeterminada para Exchange Online, SharePoint Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="11ddf-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="11ddf-109">Las claves administradas por Microsoft proporcionan cifrado de servicio predeterminado a menos que decida incorporar con la clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="11ddf-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="11ddf-110">Si, en una fecha posterior, decide dejar de usar la clave de cliente sin seguir la ruta de depuración de datos, los datos permanecen cifrados con las claves administradas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11ddf-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="11ddf-111">Los datos siempre se cifran en este nivel predeterminado como mínimo.</span><span class="sxs-lookup"><span data-stu-id="11ddf-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="11ddf-112">Clave de cliente</span><span class="sxs-lookup"><span data-stu-id="11ddf-112">Customer Key</span></span>
<span data-ttu-id="11ddf-113">Las claves raíz que se usan con el cifrado de servicio se suministran y se administran mediante Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="11ddf-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="11ddf-114">Microsoft administra el resto de claves.</span><span class="sxs-lookup"><span data-stu-id="11ddf-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="11ddf-115">Esta opción se denomina clave de cliente y actualmente está disponible para Exchange Online, SharePoint Online y OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="11ddf-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="11ddf-116">(Anteriormente denominado cifrado avanzado con BYOK.</span><span class="sxs-lookup"><span data-stu-id="11ddf-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="11ddf-117">Consulte Mejorar la transparencia y el control para los clientes de [Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para el anuncio original).</span><span class="sxs-lookup"><span data-stu-id="11ddf-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="11ddf-118">El cifrado de servicio proporciona varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="11ddf-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="11ddf-119">Proporciona una capa de protección adicional sobre BitLocker.</span><span class="sxs-lookup"><span data-stu-id="11ddf-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="11ddf-120">Proporciona una separación entre los administradores del sistema operativo Windows y el acceso a los datos de la aplicación almacenados o procesados por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="11ddf-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="11ddf-121">Incluye una opción de clave de cliente que permite que los servicios multiinquilino proporcionen administración de claves por inquilino.</span><span class="sxs-lookup"><span data-stu-id="11ddf-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="11ddf-122">Mejora la capacidad de Microsoft 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento específicos relacionados con el cifrado.</span><span class="sxs-lookup"><span data-stu-id="11ddf-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="11ddf-123">Con la clave de cliente, puede generar sus propias claves criptográficas mediante un módulo de servicio de hardware (MATE) local o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="11ddf-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="11ddf-124">Independientemente de cómo genere la clave, use AKV para controlar y administrar las claves criptográficas que usa Office 365.</span><span class="sxs-lookup"><span data-stu-id="11ddf-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="11ddf-125">Una vez que las claves se almacenan en AKV, se pueden usar como la raíz de una de las cadenas de claves que cifra los archivos o datos del buzón.</span><span class="sxs-lookup"><span data-stu-id="11ddf-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="11ddf-126">Otra ventaja de la clave de cliente es el control que tiene sobre la capacidad de Microsoft para procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="11ddf-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="11ddf-127">Si desea quitar datos de Office 365, como si desea finalizar el servicio con Microsoft o quitar una parte de los datos almacenados en la nube, puede hacerlo y usar la clave de cliente como control técnico.</span><span class="sxs-lookup"><span data-stu-id="11ddf-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="11ddf-128">La eliminación de datos garantiza que nadie, incluido Microsoft, pueda acceder o procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="11ddf-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="11ddf-129">La clave de cliente es además y complementaria de la Caja de seguridad del cliente que se usa para controlar el acceso a los datos por parte del personal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11ddf-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="11ddf-130">Para obtener información sobre cómo configurar la clave de cliente para Microsoft 365 para Exchange Online, Microsoft Teams, SharePoint Online, incluidos los sitios de grupo y OneDrive para la Empresa, vea estos artículos:</span><span class="sxs-lookup"><span data-stu-id="11ddf-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="11ddf-131">Cifrado de servicio con clave de cliente</span><span class="sxs-lookup"><span data-stu-id="11ddf-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="11ddf-132">Configurar la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="11ddf-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="11ddf-133">Administrar clave de cliente</span><span class="sxs-lookup"><span data-stu-id="11ddf-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="11ddf-134">Roll or rotate a customer key or an availability key</span><span class="sxs-lookup"><span data-stu-id="11ddf-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="11ddf-135">Comprender la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="11ddf-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
