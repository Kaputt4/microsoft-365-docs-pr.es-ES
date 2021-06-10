---
title: Microsoft Teams
description: Cómo Teams se instala en dispositivos y se actualiza después
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de línea de negocio, aplicaciones de LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920661"
---
# <a name="microsoft-teams"></a><span data-ttu-id="6d764-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d764-104">Microsoft Teams</span></span>

<span data-ttu-id="6d764-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) es una aplicación [de](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) mensajería para su organización que también proporciona un área de trabajo para la colaboración y comunicación en tiempo real, reuniones y uso compartido de archivos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6d764-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="6d764-106">Implementación inicial</span><span class="sxs-lookup"><span data-stu-id="6d764-106">Initial deployment</span></span>

<span data-ttu-id="6d764-107">La mayoría de los proveedores de hardware aún no incluyen Teams como parte de sus imágenes, por lo que Escritorio administrado de Microsoft implementa Teams en los dispositivos mediante Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6d764-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="6d764-108">Todos los dispositivos administrados [tienen el paquete Teams .msi](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) instalado, lo que garantiza que todos los usuarios que inician sesión en un dispositivo Microsoft Teams listo para su uso.</span><span class="sxs-lookup"><span data-stu-id="6d764-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="6d764-109">Cuando el paquete termina de instalarse por primera vez, Teams se inicia automáticamente y agrega un acceso directo al escritorio.</span><span class="sxs-lookup"><span data-stu-id="6d764-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="6d764-110">Microsoft Intune cambios</span><span class="sxs-lookup"><span data-stu-id="6d764-110">Microsoft Intune changes</span></span>

<span data-ttu-id="6d764-111">Escritorio administrado de Microsoft agrega dos aplicaciones a la organización de Azure AD para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d764-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="6d764-112">Se implementan en clientes de 64 o 32 bits según corresponda para el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6d764-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="6d764-113">Modern Workplace: Teams machine wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="6d764-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="6d764-114">Modern Workplace: Teams machine wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="6d764-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="6d764-115">Actualizaciones</span><span class="sxs-lookup"><span data-stu-id="6d764-115">Updates</span></span>

<span data-ttu-id="6d764-116">Teams sigue una ruta de actualización independiente de Aplicaciones Microsoft 365 para empresas y el cliente de escritorio se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6d764-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="6d764-117">Teams busca actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de forma silenciosa.</span><span class="sxs-lookup"><span data-stu-id="6d764-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="6d764-118">El Teams de productos no permite a los administradores controlar las actualizaciones, por lo que Escritorio administrado de Microsoft el [canal de actualización automática estándar.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="6d764-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="6d764-119">Actualización manual de Teams</span><span class="sxs-lookup"><span data-stu-id="6d764-119">Manually updating Teams</span></span>

<span data-ttu-id="6d764-120">Los usuarios individuales también pueden descargar actualizaciones seleccionando **Buscar** actualizaciones en el menú desplegable Perfil en   la parte superior derecha de la  \*\*\*\*   aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d764-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="6d764-121">Si hay una actualización disponible, se descargará y se instalará silenciosamente cuando el equipo esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="6d764-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="6d764-122">Optimización de entrega de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="6d764-122">Delivery optimization of updates</span></span>

<span data-ttu-id="6d764-123">La optimización de Teams actualizaciones está activada de forma predeterminada y no requiere ninguna acción de los administradores o usuarios.</span><span class="sxs-lookup"><span data-stu-id="6d764-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>