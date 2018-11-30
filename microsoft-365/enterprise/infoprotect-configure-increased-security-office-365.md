---
title: 'Paso 3: Configurar una mayor seguridad para Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure una mayor seguridad para Office 365, incluida ATP de Office 365.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871685"
---
# <a name="step-3-configure-increased-security-for-office-365"></a><span data-ttu-id="99ec1-103">Paso 3: Configurar una mayor seguridad para Office 365</span><span class="sxs-lookup"><span data-stu-id="99ec1-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="99ec1-104">*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="99ec1-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="99ec1-105">Para asegurarse de que su suscripción a Office 365 y sus datos no tienen amenazas malintencionadas y permanecerán seguros ante ellas, consulte [Configurar el espacio empresarial de Office 365 para una mayor seguridad](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) y configure la seguridad adicional siguiente:</span><span class="sxs-lookup"><span data-stu-id="99ec1-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) and configure the following additional security:</span></span>

- <span data-ttu-id="99ec1-106">Directivas de administración de amenazas en el Centro de seguridad y cumplimiento de Office 365</span><span class="sxs-lookup"><span data-stu-id="99ec1-106">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="99ec1-107">Configuración adicional de todo el espacio empresarial de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="99ec1-107">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="99ec1-108">Directivas de uso compartidas de todo el espacio empresarial en el Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="99ec1-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>
- <span data-ttu-id="99ec1-109">Configuración en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="99ec1-109">Settings in Azure Active Directory</span></span>

<span data-ttu-id="99ec1-110">Una vez configurada, puede obtener información sobre el estado de la seguridad desde:</span><span class="sxs-lookup"><span data-stu-id="99ec1-110">Once configured, you can obtain information about your security status from:</span></span>

- <span data-ttu-id="99ec1-111">Paneles e informes en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="99ec1-111">Dashboards and reports in the Security & Compliance Center</span></span>
- [<span data-ttu-id="99ec1-112">Puntuación segura de Office 365</span><span class="sxs-lookup"><span data-stu-id="99ec1-112">Office 365 Secure Score</span></span>](https://securescore.office.com/)
 
  <span data-ttu-id="99ec1-113">Para obtener acceso a esta página, debe haber iniciado sesión como administrador de espacios empresariales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="99ec1-113">To access this page, you must be signed in as an Office 365 tenant admin.</span></span>

<span data-ttu-id="99ec1-114">También puede usar Cloud App Security u Office 365 Cloud App Security para controlar eventos de seguridad y actuar. Para obtener más información, vea [Información general sobre Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span><span class="sxs-lookup"><span data-stu-id="99ec1-114">You can also use Cloud App Security or Office 365 Cloud App Security to monitor for security events and act. For more information, see [Overview of Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>

<span data-ttu-id="99ec1-115">Una característica de seguridad adicional es la Protección contra amenazas avanzada (ATP) de Office 365, que ayuda a su organización a colaborar de forma más segura al:</span><span class="sxs-lookup"><span data-stu-id="99ec1-115">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="99ec1-116">Proteger los vínculos y datos adjuntos de los correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="99ec1-116">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="99ec1-117">Proporcionar funcionalidades de inteligencia contra suplantación de identidad y de protección contra suplantación de identidad (anti-phishing) para el correo electrónico en Exchange Online y archivos en SharePoint Online, OneDrive para la Empresa y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="99ec1-117">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

>[!Note]
><span data-ttu-id="99ec1-p101">ATP de Office 365 se incluye con Microsoft 365 Enterprise E5. Si tiene Microsoft 365 Enterprise E3, puede comprar licencias individuales de ATP.</span><span class="sxs-lookup"><span data-stu-id="99ec1-p101">Office 365 ATP is included with Microsoft 365 Enterprise E5. If you have Microsoft 365 Enterprise E3, you can purchase individual licenses for ATP.</span></span>
>

<span data-ttu-id="99ec1-120">Para habilitar ATP de Office 365, vea [Cómo activarla](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="99ec1-120">To enable Office 365 ATP, see [Turn it on](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="99ec1-121">Para obtener más información, vea [ATP de Office 365 para SharePoint, OneDrive y Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span><span class="sxs-lookup"><span data-stu-id="99ec1-121">For more information, see [Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span></span>


|||
|:-------|:-----|
|![Guías del laboratorio de pruebas de la nube de Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="99ec1-123">Guía del laboratorio de pruebas: Configurar una mayor seguridad para Office 365</span><span class="sxs-lookup"><span data-stu-id="99ec1-123">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="99ec1-124">Como control interno, consulte los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step4) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="99ec1-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="99ec1-125">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="99ec1-125">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="99ec1-126">Configurar Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="99ec1-126">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


