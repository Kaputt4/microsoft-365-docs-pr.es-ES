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
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632245"
---
# <a name="service-encryption"></a><span data-ttu-id="a49cc-103">Cifrado de servicio</span><span class="sxs-lookup"><span data-stu-id="a49cc-103">Service Encryption</span></span>

<span data-ttu-id="a49cc-104">Además de usar el cifrado de nivel de volumen, Exchange Online, Skype empresarial, SharePoint Online y OneDrive para la empresa también usan el cifrado de servicio para cifrar los datos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="a49cc-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="a49cc-105">El cifrado del servicio permite dos opciones de administración de claves:</span><span class="sxs-lookup"><span data-stu-id="a49cc-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="a49cc-106">Microsoft administra todas las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="a49cc-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="a49cc-107">(Esta opción está disponible actualmente en SharePoint Online, OneDrive para la empresa y Skype empresarial).</span><span class="sxs-lookup"><span data-stu-id="a49cc-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="a49cc-108">La organización proporciona las claves raíz.</span><span class="sxs-lookup"><span data-stu-id="a49cc-108">Your organization supplies the root keys.</span></span> <span data-ttu-id="a49cc-109">Estas claves se administran con Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="a49cc-109">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="a49cc-110">Esta opción se denomina clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="a49cc-110">This option is called Customer Key.</span></span> <span data-ttu-id="a49cc-111">La clave de cliente está disponible actualmente para los archivos de Exchange Online, SharePoint Online, OneDrive para la empresa, Skype empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a49cc-111">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="a49cc-112">Si usa la clave de cliente, estas claves reemplazan las claves administradas por Microsoft para cifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="a49cc-112">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="a49cc-113">El cifrado de servicio ofrece varias ventajas.</span><span class="sxs-lookup"><span data-stu-id="a49cc-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="a49cc-114">Por ejemplo, clave de cliente:</span><span class="sxs-lookup"><span data-stu-id="a49cc-114">For example, Customer Key:</span></span>

- <span data-ttu-id="a49cc-115">Proporciona características de protección y administración de derechos sobre la protección de cifrado de alta seguridad.</span><span class="sxs-lookup"><span data-stu-id="a49cc-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="a49cc-116">Incluye una opción de clave de cliente que permite que los servicios multiinquilinos proporcionen administración de claves por espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="a49cc-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="a49cc-117">Proporciona la separación de los administradores del sistema operativo Windows del acceso a los datos de clientes almacenados o procesados por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a49cc-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="a49cc-118">Mejora la capacidad de Microsoft 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento relacionados con el cifrado.</span><span class="sxs-lookup"><span data-stu-id="a49cc-118">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="a49cc-119">Clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a49cc-119">Customer Key</span></span>

<span data-ttu-id="a49cc-120">Mediante la clave de cliente, puede generar sus propias claves criptográficas mediante un módulo de servicio de hardware (HSM) local o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="a49cc-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="a49cc-121">Independientemente de cómo genere la clave, use AKV para controlar y administrar las claves criptográficas que usa Office 365.</span><span class="sxs-lookup"><span data-stu-id="a49cc-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="a49cc-122">Una vez que las claves se almacenan en AKV, se pueden usar como la raíz de una de las llaves que cifran los archivos o datos de buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="a49cc-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="a49cc-123">Otra ventaja de la clave de cliente es el control que tiene sobre la posibilidad de que Microsoft procese sus datos.</span><span class="sxs-lookup"><span data-stu-id="a49cc-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="a49cc-124">Si desea quitar datos de Office 365, por ejemplo, si desea finalizar el servicio con Microsoft o quitar una parte de los datos almacenados en la nube, puede hacerlo y usar la clave de cliente como control técnico.</span><span class="sxs-lookup"><span data-stu-id="a49cc-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="a49cc-125">Esto garantiza que nadie, incluido Microsoft, puede tener acceso a los datos o procesarlos.</span><span class="sxs-lookup"><span data-stu-id="a49cc-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="a49cc-126">La clave de cliente es adicional y complemental a la caja de caja del cliente que se usa para controlar el acceso a los datos por parte del personal de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a49cc-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="a49cc-127">Para obtener información sobre cómo configurar la clave de cliente de Microsoft 365 para Exchange Online, Skype empresarial, SharePoint Online, incluidos los sitios de grupo y OneDrive para la empresa, consulte estos artículos:</span><span class="sxs-lookup"><span data-stu-id="a49cc-127">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="a49cc-128">Cifrado de servicio con clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a49cc-128">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="a49cc-129">Configurar la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a49cc-129">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="a49cc-130">Administrar la clave de cliente</span><span class="sxs-lookup"><span data-stu-id="a49cc-130">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="a49cc-131">Rollo o rotación de una clave de cliente o una clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="a49cc-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="a49cc-132">Descripción de la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="a49cc-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
