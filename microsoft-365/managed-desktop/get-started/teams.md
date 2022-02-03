---
title: Microsoft Teams
description: Cómo Teams se instala en dispositivos y se actualiza después
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de línea de negocio, aplicaciones de LOB
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: ITPro
ms.openlocfilehash: 21d69770fb16ac40b25cd9ff4fefd5ccf5b2f0fb
ms.sourcegitcommit: babc2dad1c0e08a9237dbe4956ffd21c0214db83
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62345944"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) es una aplicación [de mensajería](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) que también proporciona un área de trabajo para la colaboración y comunicación en tiempo real, reuniones y uso compartido de archivos y aplicaciones.

## <a name="initial-deployment"></a>Implementación inicial

La mayoría de los proveedores de hardware aún no incluyen Teams como parte de sus imágenes. Microsoft Managed Desktop implementa Teams en los dispositivos mediante Microsoft Intune. Todos los dispositivos administrados [tienen Teams .msi paquete instalado](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works). El .msi garantiza que todos los usuarios, que inician sesión en un dispositivo, Microsoft Teams estén listos para su uso. Cuando el paquete termina de instalarse por primera vez, Teams se inicia automáticamente y agrega un acceso directo al escritorio.

### <a name="microsoft-intune-changes"></a>Microsoft Intune cambios

Microsoft Managed Desktop agrega dos aplicaciones a su Azure AD organización para Microsoft Teams. Se implementan en clientes de 64 o 32 bits según corresponda para el dispositivo:  

- Modern Workplace: Teams machine wide Installer x64  
- Modern Workplace: Teams machine wide Installer x32

## <a name="updates"></a>Actualizaciones

Teams sigue una ruta de actualización independiente de Aplicaciones Microsoft 365 para empresas. El cliente de escritorio se actualiza automáticamente. Teams busca actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de forma silenciosa.  

El Teams producto no permite a los administradores controlar las actualizaciones, por lo que Microsoft Managed Desktop usa el [canal de actualización automática estándar](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).

### <a name="manually-updating-teams"></a>Actualización manual de Teams

Los usuarios individuales también pueden descargar actualizaciones. En la parte superior derecha de la aplicación, en la lista desplegable Perfil, selecciona **Buscar actualizaciones**. Si hay una actualización disponible, se descargará y se instalará silenciosamente cuando el equipo esté inactivo.

## <a name="delivery-optimization-of-updates"></a>Optimización de entrega de actualizaciones

La optimización de Teams actualizaciones está activada de forma predeterminada y no requiere ninguna acción de los administradores o usuarios.
