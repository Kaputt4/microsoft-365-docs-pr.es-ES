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
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: comprenda el cifrado de datos en la capa de servicio en Microsoft Office 365.'
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193466"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="31694-103">Cifrado de servicio de Office 365</span><span class="sxs-lookup"><span data-stu-id="31694-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="31694-104">Además de usar BitLocker para el cifrado de nivel de volumen, Exchange Online, Skype empresarial, SharePoint Online, OneDrive para la empresa y Teams también usan el cifrado de servicio para cifrar los datos de clientes.</span><span class="sxs-lookup"><span data-stu-id="31694-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="31694-105">El cifrado del servicio permite dos opciones de administración de claves:</span><span class="sxs-lookup"><span data-stu-id="31694-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="31694-106">Microsoft administra todas las claves de cifrado.</span><span class="sxs-lookup"><span data-stu-id="31694-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="31694-107">Esta opción está disponible actualmente en chats de SharePoint Online, OneDrive para la empresa, Skype empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31694-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="31694-108">Los datos se cifran de forma predeterminada con las claves administradas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31694-108">Your data is encrypted by default with Microsoft managed keys.</span></span>

- <span data-ttu-id="31694-109">La organización proporciona las claves raíz.</span><span class="sxs-lookup"><span data-stu-id="31694-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="31694-110">Estas claves se administran con Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="31694-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="31694-111">Esta opción se denomina clave de cliente.</span><span class="sxs-lookup"><span data-stu-id="31694-111">This option is called Customer Key.</span></span> <span data-ttu-id="31694-112">La clave de cliente está disponible actualmente para los archivos de Exchange Online, SharePoint Online, OneDrive para la empresa, Skype empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="31694-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="31694-113">Si usa la clave de cliente, estas claves reemplazan las claves administradas de Microsoft para cifrar los datos.</span><span class="sxs-lookup"><span data-stu-id="31694-113">If you use Customer Key, these keys replace Microsoft managed keys to encrypt your data.</span></span>

<span data-ttu-id="31694-114">Independientemente de la opción que elija, el cifrado de servicio ofrece varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="31694-114">Regardless of the option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="31694-115">Exige la autenticación del usuario para recuperar y descifrar los datos solicitados por un usuario autorizado.</span><span class="sxs-lookup"><span data-stu-id="31694-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="31694-116">Proporciona la separación de los administradores del sistema operativo Windows del acceso a los datos de clientes almacenados o procesados por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="31694-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="31694-117">Mejora la capacidad de Office 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento relacionados con el cifrado.</span><span class="sxs-lookup"><span data-stu-id="31694-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="31694-118">Para obtener información sobre cómo configurar la clave de cliente de Office 365 para los archivos de Exchange Online, Skype empresarial, SharePoint Online, OneDrive para la empresa y Microsoft Teams, vea estos artículos:</span><span class="sxs-lookup"><span data-stu-id="31694-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="31694-119">Cifrado de servicios con clave de cliente en Office 365</span><span class="sxs-lookup"><span data-stu-id="31694-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="31694-120">Configurar la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="31694-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="31694-121">Administrar la clave de cliente de Office 365</span><span class="sxs-lookup"><span data-stu-id="31694-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="31694-122">Rollo o rotación de una clave de cliente o una clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="31694-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="31694-123">Descripción de la clave de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="31694-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
