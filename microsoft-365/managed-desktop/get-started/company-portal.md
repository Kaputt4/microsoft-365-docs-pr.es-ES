---
title: Instalar Intune Company Portal en dispositivos
description: Información sobre cómo instalar la aplicación del portal de empresa en dispositivos de Escritorio administrado de Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, Portal de empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925779"
---
# <a name="install-intune-company-portal-on-devices"></a>Instalar Intune Company Portal en dispositivos

Microsoft Managed Desktop requiere que los administradores de TI instalen Intune Company Portal para sus usuarios con dispositivos de Escritorio administrado de Microsoft. Estas son algunas ventajas para su organización:
- Los usuarios tienen un lugar para examinar e instalar aplicaciones disponibles. 
- Los administradores de TI pueden organizar las aplicaciones por categorías para sus usuarios.  
- Algunas aplicaciones (como Microsoft Project y Microsoft Visio) requieren que el Portal de empresa se implemente con Microsoft Managed Desktop.
- Los administradores de TI pueden personalizar el Portal de empresa para su organización. Esto incluye la creación de imágenes de marca, la adición de contactos de soporte técnico local y mucho más. Para obtener más información, [vea How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).   

En este tema se documenta el proceso de implementación del Portal de empresa de Intune para los usuarios de Escritorio administrado de Microsoft. El proceso general tiene este aspecto:
1. Comprar portal de empresa en Microsoft Store para empresas y sincronizar con Intune
2. Asignar portal de empresa a los usuarios
3. Comunicar el cambio a los usuarios

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Paso 1: Comprar portal de empresa de Microsoft Store para empresas y sincronizar con Intune
Para obtener información sobre cómo comprar las aplicaciones y sincronizarlas con Intune, consulta Aplicaciones de [Microsoft Store](deploy-apps.md#msfb-apps) para empresas en Implementar aplicaciones en dispositivos de Escritorio administrado *de Microsoft.*

En este tema se proporciona información sobre cómo: 
- Comprar portal de empresa en Microsoft Store para empresas 
- Forzar la sincronización entre Intune y Microsoft Store para empresas
- Comprobar la sincronización activa entre Intune y Microsoft Store para empresas 

## <a name="step-2---assign-company-portal-to-your-users"></a>Paso 2: Asignar portal de empresa a los usuarios
Después de la inscripción en Microsoft Managed Desktop, Microsoft Managed Desktop Operations implementará automáticamente el Portal de empresa en el inquilino e instalará la aplicación en dispositivos de Escritorio administrado de Microsoft en su organización.

## <a name="step-3---communicate-change-to-your-users"></a>Paso 3: Comunicar el cambio a los usuarios
Como administrador de TI de su organización, es importante que los usuarios sepan cómo usar el Portal de empresa en su organización. Microsoft Managed Desktop recomienda:
- Pasos para instalar aplicaciones desde el Portal de empresa. Para obtener más información, consulta [Instalar y compartir aplicaciones en el dispositivo.](/intune-user-help/install-apps-cpapp-windows)
- Cómo enviar solicitudes a los administradores de TI para aplicaciones que no están disponibles actualmente. Para obtener más información, [consulta Solicitar una aplicación para el trabajo o la escuela.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. Implementar Intune Company Portal (este tema)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)