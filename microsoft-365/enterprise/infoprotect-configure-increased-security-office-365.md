---
title: 'Paso 3: configurar Microsoft 365 con una mayor seguridad'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entender y configurar cómo lograr mayores niveles de seguridad con Microsoft 365.
ms.openlocfilehash: 81c39eb6a51e7596a72721c72084f1f255f7f451
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073640"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="b8656-103">Paso 3: configurar Microsoft 365 con una mayor seguridad</span><span class="sxs-lookup"><span data-stu-id="b8656-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="b8656-104">*Este paso es obligatorio y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b8656-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="b8656-105">Para asegurarse de que su suscripción a Microsoft 365 y sus datos estén protegidos contra amenazas desde el principio, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8656-105">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="b8656-106">Ajustar las directivas de administración de amenazas</span><span class="sxs-lookup"><span data-stu-id="b8656-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="b8656-107">Configuración adicional de Exchange Online aplicable a todos los espacios empresariales</span><span class="sxs-lookup"><span data-stu-id="b8656-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="b8656-108">Directivas de uso compartidas aplicable a todo en el Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b8656-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="b8656-109">Configuración de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b8656-109">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="b8656-110">Una vez configurada, puede obtener información sobre el estado de la seguridad desde:</span><span class="sxs-lookup"><span data-stu-id="b8656-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="b8656-111">Paneles e informes en el centro de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b8656-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="b8656-112">Puntuación de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b8656-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="b8656-113">[La Protección contra amenazas avanzada de Office 365 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) es una característica de seguridad adicional que ayuda a su organización a colaborar de forma más segura. Lo hace de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b8656-113">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="b8656-114">Protegiendo [vínculos](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) y [datos adjuntos](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b8656-114">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="b8656-115">Ofreciendo una respuesta inteligente contra la suplantación de identidad (spoofing y phishing) por correo electrónico en Exchange Online y [para los archivos de SharePoint Online, OneDrive para la Empresa y Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="b8656-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="b8656-116">Office 365 ATP solo está disponible con Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="b8656-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="b8656-118">Guía del laboratorio de prueba: configurar una mayor seguridad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b8656-118">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="b8656-119">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="b8656-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b8656-120">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="b8656-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="b8656-121">Configurar Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="b8656-121">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


