---
title: Requisitos de la aplicación de escritorio administrada de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1ca08e84bf27a64ba7515b6f4c0307c94621601c
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280108"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="2002e-103">Requisitos de la aplicación de escritorio administrada de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2002e-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="2002e-104">Para garantizar el rendimiento, la fiabilidad y la capacidad de servicio de los dispositivos de escritorio administrados por Microsoft, las aplicaciones de línea de negocio del cliente no deben afectar seriamente a la experiencia del usuario final ni modificar la postura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2002e-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="2002e-105">Por lo tanto, las aplicaciones de línea de negocio que desea implementar en los dispositivos de escritorio administrados por Microsoft deben cumplir los requisitos de este tema.</span><span class="sxs-lookup"><span data-stu-id="2002e-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="2002e-106">Condición de aplicación</span><span class="sxs-lookup"><span data-stu-id="2002e-106">Application condition</span></span>

<span data-ttu-id="2002e-107">Es importante que las aplicaciones no afecten negativamente al entorno de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2002e-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="2002e-108">A continuación, se indican los requisitos que debe cumplir una aplicación para que se implemente una aplicación.</span><span class="sxs-lookup"><span data-stu-id="2002e-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="2002e-109">Para cualquier aplicación o controlador, Microsoft puede renunciar a cualquier requisito ofrecido en este documento.</span><span class="sxs-lookup"><span data-stu-id="2002e-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="2002e-110">Microsoft puede decidir quitar cualquier aplicación o controlador que tenga un impacto negativo en el rendimiento y la confiabilidad de los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2002e-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="2002e-111">Aplicaciones administradas centralmente</span><span class="sxs-lookup"><span data-stu-id="2002e-111">Centrally managed apps</span></span>

<span data-ttu-id="2002e-112">Todas las aplicaciones y los controladores instalados en los dispositivos administrados por Microsoft deben implementarse a través de Microsoft Intune, Microsoft Store o Microsoft Store para empresas; Si está disponible, los controladores también se implementan a través del servicio Windows Update.</span><span class="sxs-lookup"><span data-stu-id="2002e-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="2002e-113">Clases de aplicaciones prohibidas</span><span class="sxs-lookup"><span data-stu-id="2002e-113">Prohibited app classes</span></span>

<span data-ttu-id="2002e-114">Ciertos tipos de aplicaciones no se permiten en dispositivos de escritorio administrados por Microsoft:</span><span class="sxs-lookup"><span data-stu-id="2002e-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="2002e-115">software antivirus, de seguridad o de auditoría de terceros</span><span class="sxs-lookup"><span data-stu-id="2002e-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="2002e-116">Versiones de Microsoft Office anteriores a Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="2002e-116">Versions of Microsoft Office prior to Office 365 ProPlus</span></span>
- <span data-ttu-id="2002e-117">Aplicaciones que instalan o agrupan otro software de terceros</span><span class="sxs-lookup"><span data-stu-id="2002e-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="2002e-118">Comportamientos de aplicación restringidos</span><span class="sxs-lookup"><span data-stu-id="2002e-118">Restricted app behaviors</span></span>

<span data-ttu-id="2002e-119">Algunos comportamientos de la aplicación pueden afectar negativamente a la experiencia del usuario o pueden presentar un riesgo de seguridad para los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2002e-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2002e-120">No se permite que las aplicaciones con los siguientes comportamientos se ejecuten en el entorno de escritorio administrado por Microsoft sin una específica de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2002e-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific  from Microsoft.</span></span>

<span data-ttu-id="2002e-121">Experiencia del usuario:</span><span class="sxs-lookup"><span data-stu-id="2002e-121">User Experience:</span></span>
- <span data-ttu-id="2002e-122">Instalar los servicios en segundo plano</span><span class="sxs-lookup"><span data-stu-id="2002e-122">Install background services</span></span>
- <span data-ttu-id="2002e-123">Agregarse a sí mismo a la ruta de acceso de inicio de Windows</span><span class="sxs-lookup"><span data-stu-id="2002e-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="2002e-124">Aplicaciones que dependen de controladores</span><span class="sxs-lookup"><span data-stu-id="2002e-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="2002e-125">exploradores Web de terceros</span><span class="sxs-lookup"><span data-stu-id="2002e-125">3rd party web browsers</span></span>

<span data-ttu-id="2002e-126">Seguridad:</span><span class="sxs-lookup"><span data-stu-id="2002e-126">Security:</span></span>
- <span data-ttu-id="2002e-127">Elevar los privilegios del usuario final</span><span class="sxs-lookup"><span data-stu-id="2002e-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="2002e-128">Actuar como una tienda de aplicaciones o tener un administrador de extensiones integrado</span><span class="sxs-lookup"><span data-stu-id="2002e-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="2002e-129">Tener vulnerabilidades de seguridad conocidas</span><span class="sxs-lookup"><span data-stu-id="2002e-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="2002e-130">Cifrar o restringir el acceso a los datos del usuario final</span><span class="sxs-lookup"><span data-stu-id="2002e-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="2002e-131">No está firmado o está firmado con un certificado que no se acumula en una raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="2002e-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="2002e-132">Implementación de controladores</span><span class="sxs-lookup"><span data-stu-id="2002e-132">Driver deployment</span></span>

<span data-ttu-id="2002e-133">El escritorio administrado de Microsoft solo admite controladores de dispositivos que están disponibles a través de Windows Update o la bandeja de entrada instalada con el dispositivo administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2002e-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="2002e-134">Si una aplicación requiere un controlador o controladores específicos para ejecutarse, se considera una aplicación restringida y requiere que se implemente en el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2002e-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an  to be deployed to Microsoft Managed Desktop.</span></span> 

