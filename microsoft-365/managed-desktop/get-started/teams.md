---
title: Microsoft Teams
description: Cómo se instala Teams en los dispositivos y se actualiza posteriormente
keywords: Escritorio administrado por Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de LOB
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
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) es una [aplicación de mensajería](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) para su organización que también proporciona un área de trabajo para la comunicación y la colaboración en tiempo real, las reuniones y el uso compartido de archivos y aplicaciones.

## <a name="initial-deployment"></a>Implementación inicial

La mayoría de los proveedores de hardware todavía no incluyen a teams como parte de sus imágenes, por lo que Microsoft Managed Desktop implementa Teams en sus dispositivos con Microsoft Intune. Todos los dispositivos administrados tienen instalado el [paquete Teams. msi](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) , lo que garantiza que todos los usuarios que inicien sesión en un dispositivo hayan preparado Microsoft Teams para su uso. Cuando el paquete termina de instalarse por primera vez, Teams se inicia automáticamente y agrega un acceso directo al escritorio.

### <a name="microsoft-intune-changes"></a>Cambios de Microsoft Intune

Microsoft Managed Desktop agrega dos aplicaciones a la organización de Azure AD para Microsoft Teams. Se implementan en clientes de 64 bits o de 32 bits según corresponda para el dispositivo:  

- Espacio de trabajo moderno – Teams para el instalador en todo el equipo x64  
- Espacio de trabajo moderno – equipo de instalación en todo el equipo x32

## <a name="updates"></a>Actualizaciones

Teams sigue una ruta de actualización independiente de las aplicaciones de Microsoft 365 para empresas y el cliente de escritorio se actualiza automáticamente. Microsoft Teams comprueba las actualizaciones cada pocos horas, las descarga y, a continuación, espera que el equipo esté inactivo antes de instalar silenciosamente la actualización.  

El grupo de productos Teams no permite que los administradores controlen las actualizaciones, por lo que Microsoft Managed Desktop usa el [canal de actualización automática estándar](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).

### <a name="manually-updating-teams"></a>Actualización manual de Teams

Los usuarios individuales también pueden descargar actualizaciones seleccionando **Buscar actualizaciones**   en el **Profile**   menú desplegable de perfiles en la parte superior derecha de la aplicación. Si hay una actualización disponible, se descargará y se instalará en modo silencioso cuando el equipo esté inactivo.

## <a name="delivery-optimization-of-updates"></a>Optimización de entrega de actualizaciones

La optimización de entrega para las actualizaciones de Teams está activada de forma predeterminada y no requiere ninguna acción por parte de los administradores o los usuarios. 