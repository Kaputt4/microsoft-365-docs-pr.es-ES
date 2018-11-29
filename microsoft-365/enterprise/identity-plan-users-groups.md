---
title: 'Paso 1: Planear los usuarios y grupos'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Planee el conjunto de usuarios y grupos que funcionarán para su organización.
ms.openlocfilehash: 8062cc2b681f0ae45a8114a6d827f5d1ece2fe3e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871151"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="2e7e3-103">Paso 1: Planear los usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="2e7e3-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="2e7e3-104">*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2e7e3-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="2e7e3-p101">En este paso, creará una infraestructura de identidades que combine usuarios, grupos y pertenencia a grupos, con características de seguridad en la configuración correcta. Esto le permite:</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="2e7e3-107">Mantener el control sobre quién tiene acceso a recursos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="2e7e3-108">Proteger el acceso con controles que ofrecen garantías seguras de identidad (usuarios que son quienes afirman ser) y el acceso desde dispositivos seguros.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="2e7e3-109">Aprovisionar los recursos de su entorno con permisos adecuados que reducen los posibles daños y pérdidas de datos.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="2e7e3-110">Supervisar el entorno para detectar comportamientos de usuario anómalos y tomar medidas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="2e7e3-111">Planear el proveedor de identidades principal</span><span class="sxs-lookup"><span data-stu-id="2e7e3-111">Plan your primary identity provider</span></span>

<span data-ttu-id="2e7e3-p102">Para crear una infraestructura de identidades, designará un proveedor de identidades principal. Este servicio almacena cuentas de usuario y sus atributos, grupos y pertenencias, y facilita la administración continuada de estos.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="2e7e3-114">Cuando su organización adopte Microsoft 365 Enterprise, el proveedor de identidades principal será:</span><span class="sxs-lookup"><span data-stu-id="2e7e3-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="2e7e3-p103">**Windows Server Active Directory (AD)**, un proveedor de identidades de intranet hospedado en equipos que ejecutan Windows Server. Esta opción suelen usarla las organizaciones que tienen un proveedor de identidades local existente.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p103">**Windows Server Active Directory (AD)**, an intranet identity provider hosted on computers running Windows Server. This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="2e7e3-p104">**Azure Active Directory (Azure AD)**, una identidad como servicio (IDaaS) basada en la nube que ofrece una amplia variedad de funciones para administrar y proteger su entorno. Esta opción suelen usarla las organizaciones que no tienen una infraestructura local existente.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p104">**Azure Active Directory (Azure AD**), a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment. This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="2e7e3-p105">Si su organización ya cuenta con un proveedor de identidades local, necesita sincronizar las cuentas de usuario y grupos de Windows Server AD con Azure AD para ofrecer un acceso más fluido a los servicios basados en la nube de Microsoft 365 Enterprise. También puede usar Azure AD para crear y administrar grupos que solo existan en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p105">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from Windows Server AD to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise. You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="2e7e3-121">Cuando tenga los usuarios y grupos en Azure AD, puede:</span><span class="sxs-lookup"><span data-stu-id="2e7e3-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="2e7e3-122">Administrar todas las cuentas de Azure AD para todas sus aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="2e7e3-123">Usar el mismo conjunto de controles para proteger el acceso a aplicaciones en su entorno.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="2e7e3-124">Colaborar con socios externos.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="2e7e3-125">Supervisar comportamientos de cuenta anómalos, como intentos de inicio de sesión sospechosos, y tomar medidas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="2e7e3-126">Siga las instrucciones que se indican en las dos secciones siguientes para planear e implementar las cuentas de usuario y grupos.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="2e7e3-127">Clasificar por categorías los usuarios</span><span class="sxs-lookup"><span data-stu-id="2e7e3-127">Categorize your users</span></span>
<span data-ttu-id="2e7e3-p106">Los usuarios de las organizaciones se pueden clasificar por categorías de distintas formas. Por ejemplo, algunos son empleados y tienen un estado permanente. Otros son proveedores, contratistas o socios que tienen un estado temporal. Y otros son usuarios externos que no tienen cuentas de usuario, pero a los que es necesario conceder acceso a servicios y recursos específicos para facilitar la interacción y la colaboración. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="2e7e3-133">Cuentas de espacio empresarial que representan a usuarios de su organización a los que asigna una licencia para servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="2e7e3-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="2e7e3-134">Cuentas entre empresas (B2B) que representan a usuarios externos a la organización a los que invita a participar en colaboración</span><span class="sxs-lookup"><span data-stu-id="2e7e3-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="2e7e3-p107">Cuente el número de tipos de usuario de su organización. ¿Cuáles son las agrupaciones? Por ejemplo, puede agrupar usuarios por funciones de alto nivel o finalidades para su organización.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="2e7e3-p108">Además, algunos servicios en la nube se pueden compartir con usuarios externos a la organización sin cuentas de usuario. También necesitará identificar estos grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-windows-server-ad-and-azure-ad-groups"></a><span data-ttu-id="2e7e3-140">Planear grupos de Azure AD y Windows Server AD</span><span class="sxs-lookup"><span data-stu-id="2e7e3-140">Plan for Windows Server AD and Azure AD groups</span></span>

<span data-ttu-id="2e7e3-p109">Puede usar grupos en Azure AD para distintas finalidades que simplifiquen la administración de su entorno de nube. Por ejemplo, para grupos de Azure AD, puede:</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="2e7e3-143">Usar licencias basadas en grupos para asignar licencias de Office 365 y Enterprise Mobility + Security (EMS) a sus cuentas de usuario automáticamente en cuanto se agreguen a Azure AD o se sincronicen desde Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from Windows Server AD.</span></span> 
- <span data-ttu-id="2e7e3-144">Agregar cuentas de usuario a grupos específicos dinámicamente basándose en los atributos de cuenta de usuario, como el departamento.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="2e7e3-145">Aprovisionar automáticamente usuarios para aplicaciones de software como servicio (SaaS) y proteger el acceso a esas aplicaciones con autenticación multifactor y otras reglas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="2e7e3-p110">Aprovisionar permisos y niveles de acceso para sitios de grupo de SharePoint Online. Los grupos de Azure AD también se pueden usar con directivas de Azure Information Protection con ámbito para proteger archivos con cifrado y permisos.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="2e7e3-148">Resultados</span><span class="sxs-lookup"><span data-stu-id="2e7e3-148">Results</span></span>

<span data-ttu-id="2e7e3-149">Cuando complete este paso, tendrá:</span><span class="sxs-lookup"><span data-stu-id="2e7e3-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="2e7e3-150">Una lista de cuentas de usuario en Azure AD que se corresponde con los empleados de su organización y los proveedores, contratistas y socios externos que trabajan para su organización o con su organización.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="2e7e3-151">Un conjunto de grupos y sus pertenencias en Azure AD que reflejan conjuntos lógicos de cuentas de usuario y otros grupos para el aprovisionamiento de licencias automáticas de opciones de configuración de seguridad para Servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="2e7e3-152">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-user-groups) de este paso.</span><span class="sxs-lookup"><span data-stu-id="2e7e3-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="2e7e3-153">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2e7e3-153">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="2e7e3-154">Proteger las cuentas de administrador global</span><span class="sxs-lookup"><span data-stu-id="2e7e3-154">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |

