---
title: 'Paso 3: configurar Microsoft 365 con una mayor seguridad'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entender y configurar cómo lograr mayores niveles de seguridad con Microsoft 365.
ms.openlocfilehash: a1976a9305c40d721bd56a4b21b8a52552c1a9dc
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285088"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="8833c-103">Paso 3: configurar Microsoft 365 con una mayor seguridad</span><span class="sxs-lookup"><span data-stu-id="8833c-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="8833c-104">*Este paso es obligatorio y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="8833c-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="8833c-105">Para asegurarse de que su suscripción a Microsoft 365 y sus datos estén protegidos contra amenazas desde el principio, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8833c-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see Configure your Office 365 tenant for increased security and configure the following additional security:</span></span>

- [<span data-ttu-id="8833c-106">Ajustar las directivas de administración de amenazas</span><span class="sxs-lookup"><span data-stu-id="8833c-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="8833c-107">Configuración adicional de Exchange Online aplicable a todos los espacios empresariales</span><span class="sxs-lookup"><span data-stu-id="8833c-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="8833c-108">Directivas de uso compartidas aplicable a todo en el Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="8833c-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="8833c-109">Configuración de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8833c-109">CORS support in Microsoft Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="8833c-110">Una vez configurada, puede obtener información sobre el estado de la seguridad desde:</span><span class="sxs-lookup"><span data-stu-id="8833c-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="8833c-111">Paneles e informes en el centro de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8833c-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="8833c-112">Puntuación de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8833c-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="8833c-113">[La Protección contra amenazas avanzada de Office 365 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) es una característica de seguridad adicional que ayuda a su organización a colaborar de forma más segura. Lo hace de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8833c-113">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="8833c-114">Protegiendo [vínculos](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) y [datos adjuntos](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8833c-114">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="8833c-115">Ofreciendo una respuesta inteligente contra la suplantación de identidad (spoofing y phishing) por correo electrónico en Exchange Online y [para los archivos de SharePoint Online, OneDrive para la Empresa y Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="8833c-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

<span data-ttu-id="8833c-116">Office 365 ATP solo está disponible con Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="8833c-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="8833c-118">Guía del laboratorio de prueba: configurar una mayor seguridad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8833c-118">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="8833c-119">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step4) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="8833c-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8833c-120">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="8833c-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="8833c-121">Configurar Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="8833c-121">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


