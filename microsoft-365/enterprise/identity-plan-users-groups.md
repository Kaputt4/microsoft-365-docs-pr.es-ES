---
title: 'Paso 1: Planear los usuarios y grupos'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Planee el conjunto de usuarios y grupos que funcionarán para su organización.
ms.openlocfilehash: 1f879c789e6b531dec7163fa252e0f85459c823d
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072180"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="5951b-103">Paso 1: Planear los usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="5951b-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="5951b-104">*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5951b-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5951b-p101">En este paso, creará una infraestructura de identidades que combine usuarios, grupos y pertenencia a grupos, con características de seguridad en la configuración correcta. Esto le permite:</span><span class="sxs-lookup"><span data-stu-id="5951b-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="5951b-107">Mantener el control sobre quién tiene acceso a recursos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="5951b-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="5951b-108">Proteger el acceso con controles que ofrecen garantías seguras de identidad (usuarios que son quienes afirman ser) y el acceso desde dispositivos seguros.</span><span class="sxs-lookup"><span data-stu-id="5951b-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="5951b-109">Aprovisionar los recursos de su entorno con permisos adecuados que reducen los posibles daños y pérdidas de datos.</span><span class="sxs-lookup"><span data-stu-id="5951b-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="5951b-110">Supervisar el entorno para detectar comportamientos de usuario anómalos y tomar medidas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5951b-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="5951b-111">Planear el proveedor de identidades principal</span><span class="sxs-lookup"><span data-stu-id="5951b-111">Plan your primary identity provider</span></span>

<span data-ttu-id="5951b-p102">Para crear una infraestructura de identidades, designará un proveedor de identidades principal. Este servicio almacena cuentas de usuario y sus atributos, grupos y pertenencias, y facilita la administración continuada de estos.</span><span class="sxs-lookup"><span data-stu-id="5951b-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="5951b-114">Cuando su organización adopte Microsoft 365 Enterprise, el proveedor de identidades principal será:</span><span class="sxs-lookup"><span data-stu-id="5951b-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="5951b-115">**Active Directory Domain Services (AD DS)**, un proveedor de identidades de intranet hospedado en equipos que ejecutan Windows Server.</span><span class="sxs-lookup"><span data-stu-id="5951b-115">**Active Directory Domain Services (AD DS)**, an intranet identity provider hosted on computers running Windows Server.</span></span> <span data-ttu-id="5951b-116">Normalmente lo usan organizaciones que tienen un proveedor de identidades local existente.</span><span class="sxs-lookup"><span data-stu-id="5951b-116">This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="5951b-117">**Azure Active Directory (Azure AD)**, una identidad como servicio (IDaaS) basada en la nube que ofrece una amplia variedad de funciones para administrar y proteger su entorno.</span><span class="sxs-lookup"><span data-stu-id="5951b-117">**Azure Active Directory (Azure AD)**, a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment.</span></span> <span data-ttu-id="5951b-118">Esta opción suelen usarla las organizaciones que no tienen una infraestructura local existente.</span><span class="sxs-lookup"><span data-stu-id="5951b-118">This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="5951b-119">Si su organización ya cuenta con un proveedor de identidades local, necesita sincronizar las cuentas de usuario y grupos de AD DS con Azure AD para ofrecer un acceso más fluido a los servicios basados en la nube de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5951b-119">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from AD DS to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="5951b-120">También puede usar Azure AD para crear y administrar grupos que solo existan en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5951b-120">You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="5951b-121">Cuando tenga los usuarios y grupos en Azure AD, puede:</span><span class="sxs-lookup"><span data-stu-id="5951b-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="5951b-122">Administrar todas las cuentas de Azure AD para todas sus aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="5951b-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="5951b-123">Usar el mismo conjunto de controles para proteger el acceso a aplicaciones en su entorno.</span><span class="sxs-lookup"><span data-stu-id="5951b-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="5951b-124">Colaborar con socios externos.</span><span class="sxs-lookup"><span data-stu-id="5951b-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="5951b-125">Supervisar comportamientos de cuenta anómalos, como intentos de inicio de sesión sospechosos, y tomar medidas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5951b-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="5951b-126">Siga las instrucciones que se indican en las dos secciones siguientes para planear e implementar las cuentas de usuario y grupos.</span><span class="sxs-lookup"><span data-stu-id="5951b-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="5951b-127">Clasificar por categorías los usuarios</span><span class="sxs-lookup"><span data-stu-id="5951b-127">Categorize your users</span></span>
<span data-ttu-id="5951b-p106">Los usuarios de las organizaciones se pueden clasificar por categorías de distintas formas. Por ejemplo, algunos son empleados y tienen un estado permanente. Otros son proveedores, contratistas o socios que tienen un estado temporal. Y otros son usuarios externos que no tienen cuentas de usuario, pero a los que es necesario conceder acceso a servicios y recursos específicos para facilitar la interacción y la colaboración. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5951b-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="5951b-133">Cuentas de espacio empresarial que representan a usuarios de su organización a los que asigna una licencia para servicios en la nube</span><span class="sxs-lookup"><span data-stu-id="5951b-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="5951b-134">Cuentas entre empresas (B2B) que representan a usuarios externos a la organización a los que invita a participar en colaboración</span><span class="sxs-lookup"><span data-stu-id="5951b-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="5951b-p107">Cuente el número de tipos de usuario de su organización. ¿Cuáles son las agrupaciones? Por ejemplo, puede agrupar usuarios por funciones de alto nivel o finalidades para su organización.</span><span class="sxs-lookup"><span data-stu-id="5951b-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="5951b-p108">Además, algunos servicios en la nube se pueden compartir con usuarios externos a la organización sin cuentas de usuario. También necesitará identificar estos grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="5951b-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a><span data-ttu-id="5951b-140">Planear grupos de AD DS y Azure AD</span><span class="sxs-lookup"><span data-stu-id="5951b-140">Plan for AD DS and Azure AD groups</span></span>

<span data-ttu-id="5951b-p109">Puede usar grupos en Azure AD para distintas finalidades que simplifiquen la administración de su entorno de nube. Por ejemplo, para grupos de Azure AD, puede:</span><span class="sxs-lookup"><span data-stu-id="5951b-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="5951b-143">Use licencias basadas en grupos para asignar licencias de Office 365 y Enterprise Mobility + Security (EMS) a sus cuentas de usuario automáticamente en cuanto se agreguen a Azure AD o se sincronicen desde AD DS.</span><span class="sxs-lookup"><span data-stu-id="5951b-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from AD DS.</span></span> 
- <span data-ttu-id="5951b-144">Agregar cuentas de usuario a grupos específicos dinámicamente basándose en los atributos de cuenta de usuario, como el departamento.</span><span class="sxs-lookup"><span data-stu-id="5951b-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="5951b-145">Aprovisionar automáticamente usuarios para aplicaciones de software como servicio (SaaS) y proteger el acceso a esas aplicaciones con autenticación multifactor y otras reglas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="5951b-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="5951b-p110">Aprovisionar permisos y niveles de acceso para sitios de grupo de SharePoint Online. Los grupos de Azure AD también se pueden usar con directivas de Azure Information Protection con ámbito para proteger archivos con cifrado y permisos.</span><span class="sxs-lookup"><span data-stu-id="5951b-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="5951b-148">Resultados</span><span class="sxs-lookup"><span data-stu-id="5951b-148">Results</span></span>

<span data-ttu-id="5951b-149">Cuando complete este paso, tendrá:</span><span class="sxs-lookup"><span data-stu-id="5951b-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="5951b-150">Una lista de cuentas de usuario en Azure AD que se corresponde con los empleados de su organización y los proveedores, contratistas y socios externos que trabajan para su organización o con su organización.</span><span class="sxs-lookup"><span data-stu-id="5951b-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="5951b-151">Un conjunto de grupos y sus pertenencias en Azure AD que reflejan conjuntos lógicos de cuentas de usuario y otros grupos para el aprovisionamiento de licencias automáticas de opciones de configuración de seguridad para Servicios en la nube de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5951b-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="5951b-152">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-user-groups) de este paso.</span><span class="sxs-lookup"><span data-stu-id="5951b-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>

<span data-ttu-id="5951b-153">Una vez que se creen los usuarios y los grupos de Azure AD, podrá empezar a asignar licencias y usar Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5951b-153">Once your Azure AD users and groups are created, you can start assigning licenses and using Exchange Online.</span></span> <span data-ttu-id="5951b-154">Para implementar Exchange Online a los usuarios, vea [Deploy Exchange Online for Microsoft 365 Enterprise](exchangeonline-workload.md) (Implementación de Exchange Online para Microsoft 365 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="5951b-154">To roll out Exchange Online to your users, see [Deploy Exchange Online for Microsoft 365 Enterprise](exchangeonline-workload.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="5951b-155">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5951b-155">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="5951b-156">Protección de identidades con privilegios</span><span class="sxs-lookup"><span data-stu-id="5951b-156">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |

