---
title: Instalar Microsoft Project o Microsoft Visio dispositivos de Escritorio administrado de Microsoft
description: Información sobre cómo instalar Microsoft Project o Microsoft Visio dispositivos de Escritorio administrado de Microsoft
keywords: 'Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio'
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
---

# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar Microsoft Project o Microsoft Visio dispositivos de Escritorio administrado de Microsoft

Microsoft Project y Microsoft Visio requieren pasos específicos para instalarse en dispositivos de Escritorio administrado de Microsoft. En este artículo se documenta los requisitos previos y el proceso de instalación de estas aplicaciones.

## <a name="prerequisites"></a>Requisitos previos

Los administradores deben comprobar que cumplen estos requisitos previos:

| Requisitos previos | Descripción |
| ------ | ------ |
| Cantidades de licencia | La cantidad correcta de Microsoft Project y licencias Visio microsoft deben estar disponibles para los usuarios. Microsoft Managed Desktop actualmente solo admite versiones de 64 bits de estas aplicaciones. |
| Nombres de licencia | Los nombres de licencia adecuados para estas aplicaciones son: <ul><li>**Microsoft Project**: Project Online Professional o Project Online Premium</li><li>**Microsoft Visio**: Visio Online Plan 2</li><ul> |
| Portal de empresa | El Portal de empresa debe estar disponible en el espacio empresarial para que los usuarios instalen estas aplicaciones. Si el Portal de empresa no se implementa en el espacio empresarial, consulte [Portal de empresa](company-portal.md). |

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implementar Project y Visio dispositivos de Escritorio administrado de Microsoft

Microsoft Managed Desktop agregará Microsoft Project y Microsoft Visio como dos aplicaciones win32 en Microsoft Intune. También crearemos dos grupos en Azure Active Directory. Los grupos se asignarán a la aplicación correspondiente con la intención "Disponible".

**Para implementar Project y Visio:**

Agregue el usuario al grupo adecuado y la aplicación estará disponible en el Portal de empresa. Puede tardar unos minutos en sincronizarse, pero los usuarios pueden instalar las aplicaciones desde Portal de empresa.

Azure AD de grupo | ¿Qué usuarios asignar?
 --- | ---
Workplace-Office-Project_Install | Usuarios que necesitan Project
Workplace-Office-Visio_Install | Usuarios que necesitan Visio

## <a name="communicate-changes"></a>Comunicar cambios

Es importante que los administradores de TI sepan a sus usuarios cómo instalar Project y Visio. Esta comunicación incluye:

- Notificar a los usuarios cuando estas aplicaciones están disponibles para ellos.
- Instrucciones sobre cómo instalar estas aplicaciones desde el Portal de empresa.
