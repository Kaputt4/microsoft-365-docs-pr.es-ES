---
title: Instalar Microsoft Project o Microsoft Visio en dispositivos de Escritorio administrado de Microsoft
description: Información sobre la instalación de Microsoft Project o Microsoft Visio en dispositivos de Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950537"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar Microsoft Project o Microsoft Visio en dispositivos de Escritorio administrado de Microsoft

Microsoft Project y Microsoft Visio requieren pasos específicos para instalarse en dispositivos de Escritorio administrado de Microsoft. En este tema se documenta los requisitos previos y el proceso de instalación de estas aplicaciones.

## <a name="prerequisites"></a>Requisitos previos

Los administradores deben comprobar que cumplen estos requisitos previos:
- **Cantidades de licencias:** la cantidad correcta de licencias de Microsoft Project y Microsoft Visio debe estar disponible para los usuarios. Actualmente, escritorio administrado de Microsoft solo admite versiones de 64 bits de estas aplicaciones. 
- **Nombres de licencia:** los nombres de licencia adecuados para estas aplicaciones son:
    - **Microsoft Project:** Project Online Professional o Project Online Premium
    - **Microsoft Visio-** Visio Online Plan 2
- **Portal de** empresa: el Portal de empresa debe estar disponible en el espacio empresarial para que los usuarios instalen estas aplicaciones. Si el Portal de empresa no está implementado en su espacio empresarial, consulte [Portal de empresa.](company-portal.md)

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implementar Project y Visio para dispositivos de escritorio administrado de Microsoft
Escritorio administrado de Microsoft agregará Microsoft Project y Microsoft Visio como dos aplicaciones win32 en Microsoft Intune. También crearemos dos grupos en Azure Active Directory que se asignarán a la aplicación correspondiente con la intención "Disponible". 

**Para implementar Project y Visio** Agregue el usuario al grupo adecuado y la aplicación estará disponible en el Portal de empresa. La sincronización puede tardar unos minutos, pero los usuarios pueden instalar las aplicaciones desde el Portal de empresa. 

Nombre del grupo de Azure AD | ¿Qué usuarios asignar?   
 --- | ---
Modern Workplace-Office-Project_Install | Usuarios que necesitan Project
Modern Workplace-Office-Visio_Install | Usuarios que necesitan Visio

## <a name="communicate-changes"></a>Comunicar cambios
Es importante que los administradores de TI sepan a los usuarios cómo instalar Project y Visio. Incluye lo siguiente: 
- Notificar a los usuarios cuándo están disponibles estas aplicaciones. 
- Instrucciones sobre cómo instalar estas aplicaciones desde el Portal de empresa.
