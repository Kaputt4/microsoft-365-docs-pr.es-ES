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
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) es una [aplicación de mensajería](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) para su organización que también proporciona un área de trabajo para la colaboración y comunicación en tiempo real, reuniones y uso compartido de archivos y aplicaciones.

## <a name="initial-deployment"></a>Implementación inicial

La mayoría de los proveedores de hardware aún no incluyen Teams como parte de sus imágenes, por lo que Escritorio administrado de Microsoft implementa Teams en sus dispositivos mediante Microsoft Intune. Todos los dispositivos administrados tienen instalado el paquete .msi de [Teams,](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) lo que garantiza que todos los usuarios que inicien sesión en un dispositivo tengan Microsoft Teams listo para usarse. Cuando el paquete termina de instalarse por primera vez, Teams se inicia automáticamente y agrega un acceso directo al escritorio.

### <a name="microsoft-intune-changes"></a>Cambios de Microsoft Intune

Escritorio administrado de Microsoft agrega dos aplicaciones a su organización de Azure AD para Microsoft Teams. Se implementan en clientes de 64 o 32 bits según corresponda para el dispositivo:  

- Modern Workplace– Teams Machine Wide Installer x64  
- Modern Workplace– Teams Machine Wide Installer x32

## <a name="updates"></a>Actualizaciones

Teams sigue una ruta de actualización independiente de Aplicaciones de Microsoft 365 para empresas y el cliente de escritorio se actualiza automáticamente. Teams comprueba si hay actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de forma silenciosa.  

El grupo de productos de Teams no permite a los administradores controlar las actualizaciones, por lo que Escritorio administrado de Microsoft usa el [canal de actualización automática estándar.](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Actualización manual de Teams

Los usuarios individuales también pueden descargar actualizaciones seleccionando Buscar actualizaciones en el menú desplegable Perfil de la parte superior   derecha de la ****   aplicación. Si hay una actualización disponible, se descargará y se instalará silenciosamente cuando el equipo esté inactivo.

## <a name="delivery-optimization-of-updates"></a>Optimización de distribución de actualizaciones

La optimización de distribución para las actualizaciones de Teams está activada de forma predeterminada y no requiere ninguna acción de los administradores o usuarios. 