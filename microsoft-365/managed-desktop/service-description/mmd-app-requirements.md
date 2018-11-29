---
title: Requisitos de la aplicación de escritorio administrado de Microsoft
description: ''
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 71952a8b073f002890cc95883e717aeb04c0cd68
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871143"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="bdf39-103">Requisitos de la aplicación de escritorio administrado de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bdf39-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="bdf39-104">Las aplicaciones de línea de negocio que se van a implementar en los dispositivos de escritorio administrado de Microsoft deben cumplir los requisitos descritos en este tema.</span><span class="sxs-lookup"><span data-stu-id="bdf39-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="bdf39-105">Condición de la aplicación</span><span class="sxs-lookup"><span data-stu-id="bdf39-105">Application condition</span></span>

<span data-ttu-id="bdf39-p101">Es importante que las aplicaciones no impacto negativo en el entorno de escritorio administrado de Microsoft. Los siguientes son los requisitos que deben cumplir las aplicaciones en orden de Microsoft implementarlo. Para cualquier aplicación determinada o el controlador, Microsoft podrá renunciar a cualquier requisito proporcionada en este documento. Microsoft podría decidir quitar cualquier aplicación o controlador que afecta negativamente al rendimiento y la confiabilidad de los dispositivos de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bdf39-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="bdf39-110">Se puede implementar mediante tecnologías de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bdf39-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="bdf39-p102">Microsoft Managed Desktop utiliza Intune, Store de Microsoft y Microsoft Store para la empresa para implementar aplicaciones. Por consiguiente, se deben empaquetar aplicaciones de una manera pueden implementarse por medio de la versión actual de esos servicios.</span><span class="sxs-lookup"><span data-stu-id="bdf39-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="bdf39-113">Clases de aplicación prohibido</span><span class="sxs-lookup"><span data-stu-id="bdf39-113">Prohibited app classes</span></span>

<span data-ttu-id="bdf39-114">No se admiten ciertos tipos de aplicación en los dispositivos de escritorio administrado de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="bdf39-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="bdf39-115">3 º antivirus de terceros, la seguridad o software de auditoría</span><span class="sxs-lookup"><span data-stu-id="bdf39-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="bdf39-116">Versiones de Microsoft Office anteriores a Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="bdf39-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="bdf39-117">Aplicaciones que instalen o reúnen otro software de terceros 3ª</span><span class="sxs-lookup"><span data-stu-id="bdf39-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="bdf39-118">Comportamientos de aplicación restringidos</span><span class="sxs-lookup"><span data-stu-id="bdf39-118">Restricted app behaviors</span></span>

<span data-ttu-id="bdf39-p103">Algunos comportamientos de la aplicación pueden ser perjudiciales para la experiencia del usuario o supongan un riesgo de seguridad en los dispositivos de escritorio administrado de Microsoft. Las aplicaciones no presentará los comportamientos o las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="bdf39-p103">Certain application behaviors can be either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 
- <span data-ttu-id="bdf39-121">Instalar los servicios de fondo o que generan prolongados procesos en segundo plano</span><span class="sxs-lookup"><span data-stu-id="bdf39-121">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="bdf39-122">Agregarse a sí mismo a la ruta de acceso de inicio de Windows</span><span class="sxs-lookup"><span data-stu-id="bdf39-122">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="bdf39-123">Llamada sin documentar de Windows o las API de Office o tomar las dependencias en estructuras de datos internas de Windows o de Office</span><span class="sxs-lookup"><span data-stu-id="bdf39-123">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="bdf39-124">Actuar como un almacén de aplicación o tiene el Administrador de extensión incorporada</span><span class="sxs-lookup"><span data-stu-id="bdf39-124">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="bdf39-125">Elevar los privilegios del usuario final</span><span class="sxs-lookup"><span data-stu-id="bdf39-125">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="bdf39-126">Tener vulnerabilidades de seguridad conocidas</span><span class="sxs-lookup"><span data-stu-id="bdf39-126">Have known security vulnerabilities</span></span>
- <span data-ttu-id="bdf39-127">Firmado mediante un certificado que no resumir en una raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="bdf39-127">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="bdf39-128">Cifrar o restringir el acceso a los datos del usuario final</span><span class="sxs-lookup"><span data-stu-id="bdf39-128">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="bdf39-129">Modificar el código del sistema operativo en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bdf39-129">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="bdf39-130">Implementación de controlador</span><span class="sxs-lookup"><span data-stu-id="bdf39-130">Driver deployment</span></span>

<span data-ttu-id="bdf39-131">A menos que un controlador está disponible en Windows Update o por separado está firmado por el laboratorio de calidad de Hardware de Windows (WHQL), Microsoft debe aprobar un controlador antes de que Microsoft va a implementar el controlador en los dispositivos de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bdf39-131">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>