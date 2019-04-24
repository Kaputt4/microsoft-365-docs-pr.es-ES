---
title: Requisitos de la aplicación de escritorio administrada de Microsoft
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278340"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="3802a-103">Requisitos de la aplicación de escritorio administrada de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3802a-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="3802a-104">Las aplicaciones de línea de negocio que desea implementar en los dispositivos de escritorio administrados por Microsoft deben cumplir los requisitos de este tema.</span><span class="sxs-lookup"><span data-stu-id="3802a-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="3802a-105">Condición de aplicación</span><span class="sxs-lookup"><span data-stu-id="3802a-105">Application condition</span></span>

<span data-ttu-id="3802a-106">Es importante que las aplicaciones no afecten negativamente al entorno de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3802a-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="3802a-107">A continuación, se indican los requisitos que debe cumplir una aplicación para que Microsoft la implemente.</span><span class="sxs-lookup"><span data-stu-id="3802a-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="3802a-108">Para cualquier aplicación o controlador, Microsoft puede renunciar a cualquier requisito ofrecido en este documento.</span><span class="sxs-lookup"><span data-stu-id="3802a-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="3802a-109">Microsoft puede decidir quitar cualquier aplicación o controlador que tenga un impacto negativo en el rendimiento y la confiabilidad de los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3802a-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="3802a-110">Implementable con tecnologías de Microsoft</span><span class="sxs-lookup"><span data-stu-id="3802a-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="3802a-111">Microsoft manAged Desktop usa Intune, Microsoft Store y Microsoft Store for Business para implementar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3802a-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="3802a-112">Por lo tanto, las aplicaciones deben empaquetarse de una manera que pueda ser implementada por la versión actual de dichos servicios.</span><span class="sxs-lookup"><span data-stu-id="3802a-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="3802a-113">Clases de aplicaciones prohibidas</span><span class="sxs-lookup"><span data-stu-id="3802a-113">Prohibited app classes</span></span>

<span data-ttu-id="3802a-114">Ciertos tipos de aplicaciones no se permiten en dispositivos de escritorio administrados por Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3802a-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="3802a-115">software antivirus, de seguridad o de auditoría de terceros</span><span class="sxs-lookup"><span data-stu-id="3802a-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="3802a-116">exploradores Web de terceros</span><span class="sxs-lookup"><span data-stu-id="3802a-116">3rd party web browsers</span></span>
- <span data-ttu-id="3802a-117">Versiones de Microsoft Office anteriores a Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="3802a-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="3802a-118">Aplicaciones que instalan o agrupan otro software de terceros</span><span class="sxs-lookup"><span data-stu-id="3802a-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="3802a-119">Comportamientos de aplicación restringidos</span><span class="sxs-lookup"><span data-stu-id="3802a-119">Restricted app behaviors</span></span>

<span data-ttu-id="3802a-120">Algunos comportamientos de la aplicación pueden perjudicar la experiencia del usuario o presentar un riesgo de seguridad a los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3802a-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="3802a-121">Las aplicaciones no deben presentar los siguientes comportamientos o características:</span><span class="sxs-lookup"><span data-stu-id="3802a-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="3802a-122">Experiencia del usuario:</span><span class="sxs-lookup"><span data-stu-id="3802a-122">User Experience:</span></span>
- <span data-ttu-id="3802a-123">Instalar servicios en segundo plano o generar procesos en segundo plano de ejecución prolongada</span><span class="sxs-lookup"><span data-stu-id="3802a-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="3802a-124">Agregarse a sí mismo a la ruta de acceso de inicio de Windows</span><span class="sxs-lookup"><span data-stu-id="3802a-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="3802a-125">Seguridad:</span><span class="sxs-lookup"><span data-stu-id="3802a-125">Security:</span></span>
- <span data-ttu-id="3802a-126">Llamar a las API de Windows o de Office no documentadas o realizar dependencias en estructuras de datos internas de Windows u Office</span><span class="sxs-lookup"><span data-stu-id="3802a-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="3802a-127">Actuar como una tienda de aplicaciones o tener un administrador de extensiones integrado</span><span class="sxs-lookup"><span data-stu-id="3802a-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="3802a-128">Elevar los privilegios del usuario final</span><span class="sxs-lookup"><span data-stu-id="3802a-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="3802a-129">Tener vulnerabilidades de seguridad conocidas</span><span class="sxs-lookup"><span data-stu-id="3802a-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="3802a-130">Firmado con un certificado que no se acumula en una raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="3802a-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="3802a-131">Cifrar o restringir el acceso a los datos del usuario final</span><span class="sxs-lookup"><span data-stu-id="3802a-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="3802a-132">Modificar código del sistema operativo en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3802a-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="3802a-133">Implementación de controladores</span><span class="sxs-lookup"><span data-stu-id="3802a-133">Driver deployment</span></span>

<span data-ttu-id="3802a-134">A menos que un controlador esté disponible en Windows Update o que esté firmado por separado por el laboratorio de calidad de hardware de Windows (WHQL), Microsoft debe aprobar un controlador antes de que Microsoft implemente el controlador en los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3802a-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
