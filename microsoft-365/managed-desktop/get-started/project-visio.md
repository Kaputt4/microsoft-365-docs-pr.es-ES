---
title: Instalar Microsoft Project o Microsoft Visio dispositivos de Escritorio administrado de Microsoft
description: Información sobre cómo instalar Microsoft Project o Microsoft Visio dispositivos de Escritorio administrado de Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ebba2983e584e3b7d445d8962fb8dc0536d360f3
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034586"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar Microsoft Project o Microsoft Visio dispositivos de Escritorio administrado de Microsoft

Microsoft Project y Microsoft Visio requieren pasos específicos para instalarse en dispositivos de Escritorio administrado de Microsoft. En este tema se documenta los requisitos previos y el proceso de instalación de estas aplicaciones.

## <a name="prerequisites"></a>Requisitos previos

Los administradores deben comprobar que cumplen estos requisitos previos:
- **Cantidades de licencia:** la cantidad correcta de licencias Microsoft Project y Microsoft Visio deben estar disponibles para los usuarios. Microsoft Managed Desktop actualmente solo admite versiones de 64 bits de estas aplicaciones. 
- **Nombres de licencia:** los nombres de licencia adecuados para estas aplicaciones son:
    - **Microsoft Project:** Project Online Professional o Project Online Premium
    - **Microsoft Visio:** Visio Online Plan 2
- **Portal de empresa:** el Portal de empresa debe estar disponible en el espacio empresarial para que los usuarios instalen estas aplicaciones. Si el Portal de empresa no se implementa en el espacio empresarial, vea [Portal de empresa](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implementar Project y Visio dispositivos de Escritorio administrado de Microsoft
Microsoft Managed Desktop agregará Microsoft Project y Microsoft Visio como dos aplicaciones win32 en Microsoft Intune. También crearemos dos grupos en Azure Active Directory que se asignarán a la aplicación correspondiente con la intención "Disponible". 

**Para implementar Project y Visio** Agregar el usuario al grupo adecuado y la aplicación estará disponible en el Portal de empresa. Puede tardar unos minutos en sincronizarse, pero los usuarios pueden instalar las aplicaciones desde Portal de empresa. 

Azure AD de grupo | ¿Qué usuarios asignar?   
 --- | ---
Workplace-Office-Project_Install | Usuarios que necesitan Project
Workplace-Office-Visio_Install | Usuarios que necesitan Visio

## <a name="communicate-changes"></a>Comunicar cambios
Es importante que los administradores de TI sepan a sus usuarios cómo instalar Project y Visio. Esto incluye lo siguiente: 
- Notificar a los usuarios cuando estas aplicaciones están disponibles para ellos. 
- Instrucciones sobre cómo instalar estas aplicaciones desde el Portal de empresa.
