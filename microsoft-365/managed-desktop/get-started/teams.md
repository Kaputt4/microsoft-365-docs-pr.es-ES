---
title: Microsoft Teams
description: Cómo se instala Teams en dispositivos y se actualiza después
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones lob
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
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) es una [aplicación de mensajería](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) para su organización que también proporciona un área de trabajo para la colaboración y comunicación en tiempo real, reuniones y uso compartido de archivos y aplicaciones.

## <a name="initial-deployment"></a>Implementación inicial

La mayoría de los proveedores de hardware aún no incluyen Teams como parte de sus imágenes, por lo que Microsoft Managed Desktop implementa Teams en sus dispositivos mediante Microsoft Intune. Todos los dispositivos administrados tienen instalado el paquete .msi de [Teams,](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) lo que garantiza que todos los usuarios que inicien sesión en un dispositivo tengan Microsoft Teams listo para usar. Cuando el paquete termina de instalarse por primera vez, Teams se inicia automáticamente y agrega un acceso directo al escritorio.

### <a name="microsoft-intune-changes"></a>Cambios de Microsoft Intune

Microsoft Managed Desktop agrega dos aplicaciones a la organización de Azure AD para Microsoft Teams. Se implementan en clientes de 64 o 32 bits según corresponda para el dispositivo:  

- Modern Workplace: Teams Machine Wide Installer x64  
- Modern Workplace: Teams Machine Wide Installer x32

## <a name="updates"></a>Actualizaciones

Teams sigue una ruta de actualización independiente de Aplicaciones de Microsoft 365 para empresas y el cliente de escritorio se actualiza automáticamente. Teams busca actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de forma silenciosa.  

El grupo de productos de Teams no permite a los administradores controlar las actualizaciones, por lo que Microsoft Managed Desktop usa el [canal de actualización automática estándar.](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)

### <a name="manually-updating-teams"></a>Actualización manual de Teams

Los usuarios individuales también pueden descargar actualizaciones seleccionando **Buscar** actualizaciones en el menú desplegable Perfil en   la parte superior derecha de la  ****   aplicación. Si hay una actualización disponible, se descargará y se instalará silenciosamente cuando el equipo esté inactivo.

## <a name="delivery-optimization-of-updates"></a>Optimización de entrega de actualizaciones

La optimización de entrega para las actualizaciones de Teams está activada de forma predeterminada y no requiere ninguna acción de los administradores o usuarios.