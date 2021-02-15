---
title: Instalar el Portal de empresa de Intune en dispositivos
description: Información sobre la instalación de la aplicación portal de empresa en dispositivos de Escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Portal de empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939289"
---
# <a name="install-intune-company-portal-on-devices"></a>Instalar el Portal de empresa de Intune en dispositivos

Escritorio administrado de Microsoft requiere que los administradores de TI instalen el Portal de empresa de Intune para sus usuarios con dispositivos de Escritorio administrado de Microsoft. Estas son algunas ventajas para su organización:
- Los usuarios tienen un lugar donde examinar e instalar las aplicaciones disponibles. 
- Los administradores de TI pueden organizar las aplicaciones por categorías para sus usuarios.  
- Algunas aplicaciones (como Microsoft Project y Microsoft Visio) requieren que el Portal de empresa se implemente con escritorio administrado de Microsoft.
- Los administradores de TI pueden personalizar el Portal de empresa para su organización. Esto incluye la creación de imágenes de marca, la adición de contactos de soporte técnico local y mucho más. Para obtener más información, [vea Cómo configurar la aplicación Portal de empresa de Microsoft Intune.](https://docs.microsoft.com/intune/company-portal-app)   

En este tema se documenta el proceso para implementar el Portal de empresa de Intune para los usuarios de Escritorio administrado de Microsoft. El proceso general tiene este aspecto:
1. Comprar portal de empresa en la Microsoft Store para Empresas y sincronizar con Intune
2. Asignar el Portal de empresa a los usuarios
3. Comunicar el cambio a los usuarios

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Paso 1: Comprar el Portal de empresa en la Microsoft Store para Empresas y sincronizar con Intune
Para obtener información sobre cómo comprar las aplicaciones y sincronizarlas con Intune, consulta Aplicaciones de la [Microsoft Store](deploy-apps.md#msfb-apps) para Empresas en Implementar aplicaciones en dispositivos de Escritorio administrado *de Microsoft.*

En este tema se proporciona información sobre cómo: 
- Comprar portal de empresa en la Microsoft Store para Empresas 
- Forzar la sincronización entre Intune y la Microsoft Store para Empresas
- Comprobar la sincronización activa entre Intune y la Microsoft Store para Empresas 

## <a name="step-2---assign-company-portal-to-your-users"></a>Paso 2: Asignar el Portal de empresa a los usuarios
Después de la inscripción en el Escritorio administrado de Microsoft, Operaciones de escritorio administrado de Microsoft implementará automáticamente el Portal de empresa en su espacio empresarial e instalará la aplicación en los dispositivos de Escritorio administrado de Microsoft de su organización.

## <a name="step-3---communicate-change-to-your-users"></a>Paso 3: Comunicar el cambio a los usuarios
Como administrador de TI de su organización, es importante que los usuarios sepan cómo usar el Portal de empresa en su organización. El Escritorio administrado de Microsoft recomienda lo siguiente:
- Pasos para instalar aplicaciones desde el Portal de empresa. Para obtener más información, consulta [Instalar y compartir aplicaciones en el dispositivo.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)
- Cómo enviar solicitudes a los administradores de TI para las aplicaciones que no están disponibles actualmente. Para obtener más información, consulta [Solicitar una aplicación para trabajo o escuela.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar a usar el Escritorio administrado de Microsoft

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. Implementar el Portal de empresa de Intune (este tema)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)
