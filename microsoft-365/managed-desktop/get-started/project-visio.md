---
title: Instalar Microsoft Project o Microsoft Visio en Escritorio administrado de Microsoft dispositivos
description: Información sobre la instalación de Microsoft Project o Microsoft Visio en Escritorio administrado de Microsoft dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: d20731d1f732ad76795cd26f862b2aff36409b6b3644a50391660517d171d1c3
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53857936"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar Microsoft Project o Microsoft Visio en Escritorio administrado de Microsoft dispositivos

Microsoft Project y Microsoft Visio requieren pasos específicos para instalarse en Escritorio administrado de Microsoft dispositivos. En este tema se documenta los requisitos previos y el proceso de instalación de estas aplicaciones.

## <a name="prerequisites"></a>Requisitos previos

Los administradores deben comprobar que cumplen estos requisitos previos:
- **Cantidades de licencia:** la cantidad correcta de licencias Microsoft Project y Microsoft Visio deben estar disponibles para los usuarios. Escritorio administrado de Microsoft actualmente solo admite versiones de 64 bits de estas aplicaciones. 
- **Nombres de licencia:** los nombres de licencia adecuados para estas aplicaciones son:
    - **Microsoft Project:** Project Online Professional o Project Online Premium
    - **Microsoft Visio:** Visio Online Plan 2
- **Portal de empresa:** el Portal de empresa debe estar disponible en el espacio empresarial para que los usuarios instalen estas aplicaciones. Si el Portal de empresa no se implementa en el espacio empresarial, vea [Portal de empresa](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implementar Project y Visio para Escritorio administrado de Microsoft dispositivos
Escritorio administrado de Microsoft agregará Microsoft Project y Microsoft Visio como dos aplicaciones win32 en Microsoft Intune. También crearemos dos grupos en Azure Active Directory que se asignarán a la aplicación correspondiente con la intención "Disponible". 

**Para implementar Project y Visio** Agregue el usuario al grupo adecuado y la aplicación estará disponible en el Portal de empresa. Puede tardar unos minutos en sincronizarse, pero los usuarios pueden instalar las aplicaciones desde Portal de empresa. 

Nombre del grupo de Azure AD | ¿Qué usuarios asignar?   
 --- | ---
Workplace-Office-Project_Install | Usuarios que necesitan Project
Workplace-Office-Visio_Install | Usuarios que necesitan Visio

## <a name="communicate-changes"></a>Comunicar cambios
Es importante que los administradores de TI sepan a sus usuarios cómo instalar Project y Visio. Esto incluye lo siguiente: 
- Notificar a los usuarios cuando estas aplicaciones están disponibles para ellos. 
- Instrucciones sobre cómo instalar estas aplicaciones desde el Portal de empresa.
