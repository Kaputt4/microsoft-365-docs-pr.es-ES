---
title: Microsoft Teams
description: Cómo se instala Teams en dispositivos y se actualiza posteriormente
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de LÍNEA DEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950962"
---
# <a name="microsoft-teams"></a><span data-ttu-id="99ac7-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="99ac7-104">Microsoft Teams</span></span>

<span data-ttu-id="99ac7-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) es una [aplicación de mensajería](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) para su organización que también proporciona un área de trabajo para la colaboración y comunicación en tiempo real, reuniones y uso compartido de archivos y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="99ac7-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="99ac7-106">Implementación inicial</span><span class="sxs-lookup"><span data-stu-id="99ac7-106">Initial deployment</span></span>

<span data-ttu-id="99ac7-107">La mayoría de los proveedores de hardware aún no incluyen Teams como parte de sus imágenes, por lo que Escritorio administrado de Microsoft implementa Teams en sus dispositivos mediante Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="99ac7-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="99ac7-108">Todos los dispositivos administrados tienen instalado el paquete .msi de [Teams,](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) lo que garantiza que todos los usuarios que inicien sesión en un dispositivo tengan Microsoft Teams listo para usarse.</span><span class="sxs-lookup"><span data-stu-id="99ac7-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="99ac7-109">Cuando el paquete termina de instalarse por primera vez, Teams se inicia automáticamente y agrega un acceso directo al escritorio.</span><span class="sxs-lookup"><span data-stu-id="99ac7-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="99ac7-110">Cambios de Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="99ac7-110">Microsoft Intune changes</span></span>

<span data-ttu-id="99ac7-111">Escritorio administrado de Microsoft agrega dos aplicaciones a su organización de Azure AD para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="99ac7-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="99ac7-112">Se implementan en clientes de 64 o 32 bits según corresponda para el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="99ac7-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="99ac7-113">Modern Workplace– Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="99ac7-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="99ac7-114">Modern Workplace– Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="99ac7-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="99ac7-115">Actualizaciones</span><span class="sxs-lookup"><span data-stu-id="99ac7-115">Updates</span></span>

<span data-ttu-id="99ac7-116">Teams sigue una ruta de actualización independiente de Aplicaciones de Microsoft 365 para empresas y el cliente de escritorio se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="99ac7-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="99ac7-117">Teams comprueba si hay actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de forma silenciosa.</span><span class="sxs-lookup"><span data-stu-id="99ac7-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="99ac7-118">El grupo de productos de Teams no permite a los administradores controlar las actualizaciones, por lo que Escritorio administrado de Microsoft usa el [canal de actualización automática estándar.](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)</span><span class="sxs-lookup"><span data-stu-id="99ac7-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="99ac7-119">Actualización manual de Teams</span><span class="sxs-lookup"><span data-stu-id="99ac7-119">Manually updating Teams</span></span>

<span data-ttu-id="99ac7-120">Los usuarios individuales también pueden descargar actualizaciones seleccionando Buscar actualizaciones en el menú desplegable Perfil de la parte superior   derecha de la \*\*\*\*   aplicación.</span><span class="sxs-lookup"><span data-stu-id="99ac7-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="99ac7-121">Si hay una actualización disponible, se descargará y se instalará silenciosamente cuando el equipo esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="99ac7-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="99ac7-122">Optimización de distribución de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="99ac7-122">Delivery optimization of updates</span></span>

<span data-ttu-id="99ac7-123">La optimización de distribución para las actualizaciones de Teams está activada de forma predeterminada y no requiere ninguna acción de los administradores o usuarios.</span><span class="sxs-lookup"><span data-stu-id="99ac7-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 