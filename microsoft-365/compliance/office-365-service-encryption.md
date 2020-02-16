---
title: Cifrado de servicio de Office 365
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
ms.openlocfilehash: ec7f794a62a910fadaece890cf73451644d44109
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071117"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="d3b60-103">Cifrado de servicio de Office 365</span><span class="sxs-lookup"><span data-stu-id="d3b60-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="d3b60-104">Además de usar el cifrado de nivel de volumen, Exchange Online, Skype empresarial, SharePoint Online y OneDrive para la empresa también usan el cifrado de servicio para cifrar los datos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="d3b60-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="d3b60-105">El cifrado del servicio permite dos opciones de administración de claves:</span><span class="sxs-lookup"><span data-stu-id="d3b60-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="d3b60-106">Microsoft administra todas las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="d3b60-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="d3b60-107">(Esta opción está disponible actualmente en SharePoint Online, OneDrive para la empresa y Skype empresarial).</span><span class="sxs-lookup"><span data-stu-id="d3b60-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="d3b60-108">El cliente suministra claves raíz que se usan con el cifrado de servicio y el cliente administra estas claves mediante Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="d3b60-108">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault.</span></span> <span data-ttu-id="d3b60-109">Microsoft administra todas las demás claves.</span><span class="sxs-lookup"><span data-stu-id="d3b60-109">Microsoft manages all other keys.</span></span> <span data-ttu-id="d3b60-110">Esta opción se denomina clave de cliente y actualmente está disponible para Exchange Online, SharePoint Online y OneDrive para la empresa.</span><span class="sxs-lookup"><span data-stu-id="d3b60-110">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="d3b60-111">(Anteriormente denominado cifrado avanzado con BYOK.</span><span class="sxs-lookup"><span data-stu-id="d3b60-111">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="d3b60-112">Consulte [mejorar la transparencia y el control para clientes de Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para el anuncio original).</span><span class="sxs-lookup"><span data-stu-id="d3b60-112">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="d3b60-113">El cifrado de servicio ofrece varias ventajas.</span><span class="sxs-lookup"><span data-stu-id="d3b60-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="d3b60-114">Por ejemplo, clave de cliente:</span><span class="sxs-lookup"><span data-stu-id="d3b60-114">For example, Customer Key:</span></span>

- <span data-ttu-id="d3b60-115">Proporciona características de protección y administración de derechos sobre la protección de cifrado de alta seguridad.</span><span class="sxs-lookup"><span data-stu-id="d3b60-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="d3b60-116">Incluye una opción de clave de cliente que permite que los servicios multiinquilinos proporcionen administración de claves por espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="d3b60-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="d3b60-117">Proporciona la separación de los administradores del sistema operativo Windows del acceso a los datos de clientes almacenados o procesados por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d3b60-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="d3b60-118">Mejora la capacidad de Office 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento relacionados con el cifrado.</span><span class="sxs-lookup"><span data-stu-id="d3b60-118">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="d3b60-119">Clave del cliente</span><span class="sxs-lookup"><span data-stu-id="d3b60-119">Customer Key</span></span>

<span data-ttu-id="d3b60-120">Mediante la clave de cliente, puede generar sus propias claves criptográficas mediante un módulo de servicio de hardware (HSM) local o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="d3b60-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="d3b60-121">Independientemente de cómo genere la clave, use AKV para controlar y administrar las claves criptográficas que usa Office 365.</span><span class="sxs-lookup"><span data-stu-id="d3b60-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="d3b60-122">Una vez que las claves se almacenan en AKV, se pueden usar como la raíz de una de las llaves que cifran los archivos o datos de buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="d3b60-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="d3b60-123">Otra ventaja de la clave de cliente es el control que tiene sobre la posibilidad de que Microsoft procese sus datos.</span><span class="sxs-lookup"><span data-stu-id="d3b60-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="d3b60-124">Si desea quitar datos de Office 365, por ejemplo, si desea finalizar el servicio con Microsoft o quitar una parte de los datos almacenados en la nube, puede hacerlo y usar la clave de cliente como control técnico.</span><span class="sxs-lookup"><span data-stu-id="d3b60-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="d3b60-125">Esto garantiza que nadie, incluido Microsoft, puede tener acceso a los datos o procesarlos.</span><span class="sxs-lookup"><span data-stu-id="d3b60-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="d3b60-126">La clave de cliente es adicional y complemental a la caja de caja del cliente que se usa para controlar el acceso a los datos por parte del personal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3b60-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="d3b60-127">Para obtener información sobre cómo configurar la clave de cliente de Office 365 para Exchange Online, Skype empresarial, SharePoint Online, incluidos los sitios de grupo y OneDrive para la empresa, consulte estos artículos:</span><span class="sxs-lookup"><span data-stu-id="d3b60-127">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="d3b60-128">Cifrado de servicios con clave de cliente en Office 365</span><span class="sxs-lookup"><span data-stu-id="d3b60-128">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="d3b60-129">Configurar la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="d3b60-129">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="d3b60-130">Administrar la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="d3b60-130">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="d3b60-131">Rollo o rotación de una clave de cliente o una clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="d3b60-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="d3b60-132">Descripción de la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="d3b60-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
