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
description: 'Resumen: comprenda la resistencia de los datos en Microsoft Office 365.'
ms.openlocfilehash: 4759cfda13ab5044ddf5980d7e61004e9e7626fa
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024780"
---
# <a name="service-encryption"></a><span data-ttu-id="98911-103">Cifrado de servicio</span><span class="sxs-lookup"><span data-stu-id="98911-103">Service Encryption</span></span>

<span data-ttu-id="98911-104">Además de usar el cifrado de nivel de volumen, Exchange Online, Skype empresarial, SharePoint Online y OneDrive para la empresa también usan el cifrado de servicio para cifrar los datos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="98911-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="98911-105">El cifrado del servicio permite dos opciones de administración de claves:</span><span class="sxs-lookup"><span data-stu-id="98911-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="98911-106">Claves administradas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="98911-106">Microsoft managed keys</span></span>
<span data-ttu-id="98911-107">Microsoft administra todas las claves criptográficas, incluidas las claves raíz para el cifrado del servicio.</span><span class="sxs-lookup"><span data-stu-id="98911-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="98911-108">Esta opción está disponible actualmente en SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="98911-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="98911-109">Esta opción se está implementando actualmente para Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="98911-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="98911-110">Las claves administradas de Microsoft proporcionan cifrado de servicio predeterminado a menos que decida incorporarse con la clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="98911-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="98911-111">Si, en una fecha posterior, decide dejar de usar la clave de cliente sin seguir la ruta de acceso de purga de datos, los datos se cifran con las claves administradas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98911-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="98911-112">Los datos siempre se cifran en este nivel predeterminado como mínimo.</span><span class="sxs-lookup"><span data-stu-id="98911-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="98911-113">Clave de cliente</span><span class="sxs-lookup"><span data-stu-id="98911-113">Customer Key</span></span>
<span data-ttu-id="98911-114">Debe proporcionar las claves raíz que se usan con el cifrado de servicio y administrarlas con Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="98911-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="98911-115">Microsoft administra todas las demás claves.</span><span class="sxs-lookup"><span data-stu-id="98911-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="98911-116">Esta opción se denomina clave de cliente y actualmente está disponible para Exchange Online, SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="98911-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="98911-117">(Anteriormente denominado cifrado avanzado con BYOK.</span><span class="sxs-lookup"><span data-stu-id="98911-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="98911-118">Consulte [mejorar la transparencia y el control para clientes de Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para el anuncio original).</span><span class="sxs-lookup"><span data-stu-id="98911-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="98911-119">El cifrado de servicio ofrece varias ventajas.</span><span class="sxs-lookup"><span data-stu-id="98911-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="98911-120">Por ejemplo, clave de cliente:</span><span class="sxs-lookup"><span data-stu-id="98911-120">For example, Customer Key:</span></span>

- <span data-ttu-id="98911-121">Proporciona características de protección y administración de derechos sobre la protección de cifrado de alta seguridad.</span><span class="sxs-lookup"><span data-stu-id="98911-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="98911-122">Incluye una opción de clave de cliente que permite que los servicios multiinquilinos proporcionen administración de claves por espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="98911-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="98911-123">Proporciona la separación de los administradores del sistema operativo Windows del acceso a los datos de clientes almacenados o procesados por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="98911-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="98911-124">Mejora la capacidad de Microsoft 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento relacionados con el cifrado.</span><span class="sxs-lookup"><span data-stu-id="98911-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="98911-125">Mediante la clave de cliente, puede generar sus propias claves criptográficas mediante un módulo de servicio de hardware (HSM) local o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="98911-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="98911-126">Independientemente de cómo genere la clave, use AKV para controlar y administrar las claves criptográficas que usa Office 365.</span><span class="sxs-lookup"><span data-stu-id="98911-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="98911-127">Una vez que las claves se almacenan en AKV, se pueden usar como la raíz de una de las llaves que cifran los archivos o datos de buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="98911-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="98911-128">Otra ventaja de la clave de cliente es el control que tiene sobre la posibilidad de que Microsoft procese sus datos.</span><span class="sxs-lookup"><span data-stu-id="98911-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="98911-129">Si desea quitar datos de Office 365, por ejemplo, si desea finalizar el servicio con Microsoft o quitar una parte de los datos almacenados en la nube, puede hacerlo y usar la clave de cliente como control técnico.</span><span class="sxs-lookup"><span data-stu-id="98911-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="98911-130">Esto garantiza que nadie, incluido Microsoft, puede tener acceso a los datos o procesarlos.</span><span class="sxs-lookup"><span data-stu-id="98911-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="98911-131">La clave de cliente es adicional y complemental a la caja de caja del cliente que se usa para controlar el acceso a los datos por parte del personal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98911-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="98911-132">Para obtener información sobre cómo configurar la clave de cliente de Microsoft 365 para Exchange Online, Skype empresarial, SharePoint Online, incluidos los sitios de grupo y OneDrive para la empresa, consulte estos artículos:</span><span class="sxs-lookup"><span data-stu-id="98911-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="98911-133">Cifrado de servicio con clave de cliente</span><span class="sxs-lookup"><span data-stu-id="98911-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="98911-134">Configurar la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="98911-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="98911-135">Administrar la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="98911-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="98911-136">Rollo o rotación de una clave de cliente o una clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="98911-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="98911-137">Descripción de la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="98911-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

