---
title: 'Paso 9: Simplificar las actualizaciones de contraseñas'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la escritura diferida de contraseñas para entornos híbridos.
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871341"
---
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="e0b26-103">Paso 9: Simplificar las actualizaciones de contraseñas</span><span class="sxs-lookup"><span data-stu-id="e0b26-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="e0b26-104">*Este paso es opcional para los entornos híbridos y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e0b26-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="e0b26-p101">En este paso, permitirá que los usuarios restablezcan sus contraseñas a través de Azure Active Directory (AD), que se replica después en la instancia local de Windows Server Active Directory (AD). Este proceso se conoce como escritura diferida de contraseñas. Con la escritura diferida de contraseñas, los usuarios no necesitan actualizar sus contraseñas a través de la instancia local de Windows Server AD donde se almacenan las cuentas de usuario y sus atributos. Esto resulta útil para los usuarios remotos o en itinerancia que no tengan una conexión de acceso remoto a la red local.</span><span class="sxs-lookup"><span data-stu-id="e0b26-p101">In this step, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). This process is known as password writeback. With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored. This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="e0b26-109">La escritura diferida de contraseñas es necesaria para utilizar por completo las funcionalidades de la característica de Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando se haya detectado un alto riesgo de que la cuenta se haya visto comprometida.</span><span class="sxs-lookup"><span data-stu-id="e0b26-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="e0b26-110">Para obtener más información e instrucciones de configuración, vea [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) (SSPR de Azure AD con escritura diferida de contraseñas).</span><span class="sxs-lookup"><span data-stu-id="e0b26-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="e0b26-p102">Actualice a la última versión de Azure AD Connect para garantizar que tiene la mejor experiencia posible y nuevas características cuando se publican. Para obtener más información, vea [Instalación personalizada de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="e0b26-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

<span data-ttu-id="e0b26-113">Como control interno, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-pw-writeback) de este paso.</span><span class="sxs-lookup"><span data-stu-id="e0b26-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e0b26-114">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e0b26-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="e0b26-115">Simplificar el inicio de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="e0b26-115">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

