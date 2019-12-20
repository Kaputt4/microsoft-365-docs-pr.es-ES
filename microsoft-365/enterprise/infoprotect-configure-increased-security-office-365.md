---
title: 'Paso 3: configurar Microsoft 365 con una mayor seguridad'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entender y configurar cómo lograr mayores niveles de seguridad con Microsoft 365.
ms.openlocfilehash: 15a4121315a81e1169e7cf1fa1c7ed079201b67b
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801685"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="a3724-103">Paso 3: configurar Microsoft 365 con una mayor seguridad</span><span class="sxs-lookup"><span data-stu-id="a3724-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="a3724-104">*Este paso es obligatorio y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a3724-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: Protección de la información](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="a3724-106">Para asegurarse de que su suscripción a Microsoft 365 y sus datos estén protegidos contra amenazas desde el principio, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3724-106">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="a3724-107">Ajustar las directivas de administración de amenazas</span><span class="sxs-lookup"><span data-stu-id="a3724-107">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [<span data-ttu-id="a3724-108">Configuración adicional de Exchange Online aplicable a todos los espacios empresariales</span><span class="sxs-lookup"><span data-stu-id="a3724-108">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="a3724-109">Directivas de uso compartidas aplicable a todo en el Centro de administración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="a3724-109">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="a3724-110">Configuración de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a3724-110">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="a3724-111">Una vez configurada, puede obtener información sobre el estado de la seguridad desde:</span><span class="sxs-lookup"><span data-stu-id="a3724-111">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="a3724-112">Paneles e informes en el centro de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a3724-112">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [<span data-ttu-id="a3724-113">Puntuación de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="a3724-113">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="a3724-114">[La Protección contra amenazas avanzada de Office 365 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) es una característica de seguridad adicional que ayuda a su organización a colaborar de forma más segura. Lo hace de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a3724-114">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="a3724-115">Protegiendo [vínculos](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) y [datos adjuntos](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a3724-115">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="a3724-116">Ofreciendo una respuesta inteligente contra la suplantación de identidad (spoofing y phishing) por correo electrónico en Exchange Online y [para los archivos de SharePoint Online, OneDrive para la Empresa y Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="a3724-116">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="a3724-117">Office 365 ATP solo está disponible con Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="a3724-117">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Guías del laboratorio de pruebas para la nube de Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="a3724-119">Guía del laboratorio de prueba: configurar una mayor seguridad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a3724-119">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="a3724-120">Como punto de control provisional, vea los [criterios de salida](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondientes a este paso.</span><span class="sxs-lookup"><span data-stu-id="a3724-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a3724-121">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="a3724-121">Next step</span></span>


|||
|:-------|:-----|
|![Paso 4](./media/stepnumbers/Step4.png)|[<span data-ttu-id="a3724-123">Configurar Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="a3724-123">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


