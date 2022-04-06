---
title: Microsoft Teams
description: Cómo Teams se instala en dispositivos y se actualiza después
keywords: Microsoft Managed Desktop, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de línea de negocio, aplicaciones de LOB
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: ITPro
ms.openlocfilehash: 469edf3e8ae856ea6e94bada8ffb9d6c97ba8b66
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634479"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) es una aplicación [de mensajería](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) que también proporciona un área de trabajo para la colaboración y comunicación en tiempo real, reuniones y uso compartido de archivos y aplicaciones.

## <a name="initial-deployment"></a>Implementación inicial

La mayoría de los proveedores de hardware aún no incluyen Teams como parte de sus imágenes. Microsoft Managed Desktop implementa Teams en los dispositivos mediante Microsoft Intune. Todos los dispositivos [administrados tienen Teams .msi paquete instalado](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works). El .msi garantiza que todos los usuarios, que inician sesión en un dispositivo, Microsoft Teams estén listos para su uso. Cuando el paquete termina de instalarse por primera vez, Teams se inicia automáticamente y agrega un acceso directo al escritorio.

### <a name="microsoft-intune-changes"></a>Microsoft Intune cambios

Microsoft Managed Desktop agrega Microsoft Teams a su inquilino: Modern Workplace - Teams Machine Wide Installer x64  

## <a name="updates"></a>Actualizaciones

Teams sigue una ruta de actualización independiente de Aplicaciones Microsoft 365 para empresas. El cliente de escritorio se actualiza automáticamente. Teams busca actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de forma silenciosa.  

El Teams producto no permite a los administradores controlar las actualizaciones, por lo que Microsoft Managed Desktop el [canal de actualización automática estándar](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).

### <a name="manually-updating-teams"></a>Actualización manual de Teams

Los usuarios individuales también pueden descargar actualizaciones. En la parte superior derecha de la aplicación, en la lista desplegable Perfil, selecciona **Buscar actualizaciones**. Si hay una actualización disponible, se descargará y se instalará de forma silenciosa cuando el equipo esté inactivo.

## <a name="delivery-optimization-of-updates"></a>Optimización de entrega de actualizaciones

La optimización de Teams actualizaciones está activada de forma predeterminada y no requiere ninguna acción de los administradores o usuarios.
