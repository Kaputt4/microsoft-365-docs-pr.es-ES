---
title: Instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft
description: Información sobre la instalación de Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft
keywords: Escritorio administrado por Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
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
Microsoft Managed Desktop agregará Microsoft Project y Microsoft Visio como dos aplicaciones Win32 en Microsoft Intune. También se crean dos grupos en Azure Active Directory que se asignarán a la aplicación correspondiente con el propósito "disponible". 

**Para implementar Project y Visio** Agregue el usuario al grupo adecuado y la aplicación estará disponible en el portal de la empresa. La sincronización puede tardar unos minutos, pero los usuarios pueden instalar las aplicaciones desde el portal de la empresa. 

Nombre de grupo de Azure AD | ¿Qué usuarios va a asignar?   
 --- | ---
Espacio de trabajo moderno: Project_Install de Office | Usuarios que necesitan Project
Espacio de trabajo moderno: Visio_Install de Office | Usuarios que necesitan Visio

## <a name="communicate-changes"></a>Comunicar los cambios
Es importante que los administradores de ti permitan a sus usuarios saber cómo instalar Project y Visio. Incluye lo siguiente: 
- Notificar a los usuarios cuando estas aplicaciones están disponibles para ellos. 
- Instrucciones sobre cómo instalar estas aplicaciones desde el portal de la empresa.
