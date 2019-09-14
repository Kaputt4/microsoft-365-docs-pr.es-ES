---
title: Instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft
description: Información sobre la instalación de Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft
keywords: Escritorio administrado por Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 30374e603350ecf9d5e5542263f004a22ccb0a67
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981711"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft

Microsoft Project y Microsoft Visio requieren que se instalen pasos específicos en dispositivos de escritorio administrados por Microsoft. En este tema se documentan los requisitos previos y el proceso de instalación de estas aplicaciones.

## <a name="prerequisites"></a>Requisitos previos

Los administradores deben comprobar que cumplen estos requisitos previos:
- **Cantidades de licencias** : la cantidad correcta de licencias de Microsoft Project y Microsoft Visio debe estar disponible para los usuarios. Actualmente, Microsoft Managed Desktop solo admite versiones de 64 bits de estas aplicaciones. 
- **Nombres de licencia** : los nombres de licencia apropiados para estas aplicaciones son los siguientes:
    - **Microsoft Project** -Project Online Professional o Project online Premium
    - **Microsoft Visio** -Visio online plan 2
- **Portal de empresa** : el portal de empresa debe estar disponible en el espacio empresarial para que los usuarios instalen estas aplicaciones. Si el portal de la empresa no está implementado en el espacio empresarial, consulte [Company Portal](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implementación de Project y Visio para dispositivos de escritorio administrados por Microsoft
Después de enviar su solicitud de soporte técnico, el escritorio administrado de Microsoft creará tres grupos de Azure AD y tres implementaciones de aplicaciones a través de Microsoft Intune para implementar las aplicaciones en su espacio empresarial.  

**Para implementar Project y Visio**
1. **Archivar una solicitud de soporte técnico** Los administradores de TI deben presentar una solicitud de soporte técnico para que estas aplicaciones estén disponibles para los usuarios. Para obtener información sobre cómo ponerse en contacto con el escritorio administrado de Microsoft, consulte [soporte de administración para escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md).
2. **Asignar usuarios a los nuevos grupos de Azure ad** Microsoft Managed Desktop creará 3 grupos de Azure AD en el espacio empresarial y tres implementaciones de aplicaciones correspondientes. Los administradores de TI deben asignar los usuarios a los grupos adecuados.

>[!NOTE]
>Asigne usuarios a solo uno de estos grupos de Azure AD. 

Nombre de grupo de Azure AD | ¿Qué usuarios va a asignar?   
 --- | ---
Espacio de trabajo moderno-Office-Project_Install | Los usuarios solo necesitan un proyecto
Espacio de trabajo moderno-Office-Visio_Install | Usuarios que solo necesitan Visio
Espacio de trabajo moderno-Office-Visio_Project_Install | Usuarios que necesiten tanto Project como Visio

Una vez asignada a estos grupos, las aplicaciones estarán disponibles en el portal de la empresa. La sincronización puede tardar unos minutos, pero los usuarios pueden instalar las aplicaciones desde el portal de la empresa. 

## <a name="communicate-changes"></a>Comunicar los cambios
Es importante que los administradores de ti permitan a sus usuarios saber cómo instalar Project y Visio. Esto incluye: 
- Notificar a los usuarios cuando estas aplicaciones están disponibles para ellos. 
- Instrucciones sobre cómo instalar estas aplicaciones desde el portal de la empresa.

>[!NOTE]
>Los usuarios deben cerrar todas las aplicaciones de Office antes de instalar Microsoft Project o Microsoft Visio desde el portal de empresa. 
