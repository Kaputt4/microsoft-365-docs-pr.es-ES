---
title: Instalar Portal de empresa de Intune dispositivos
description: Información sobre cómo instalar la aplicación del portal de empresa en Escritorio administrado de Microsoft dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, Portal de empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086690"
---
# <a name="install-intune-company-portal-on-devices"></a>Instalar Portal de empresa de Intune dispositivos

Escritorio administrado de Microsoft requiere que los administradores de TI instalen Portal de empresa de Intune para sus usuarios con Escritorio administrado de Microsoft dispositivos. Estas son algunas ventajas para su organización:
- Los usuarios tienen un lugar para examinar e instalar aplicaciones disponibles. 
- Los administradores de TI pueden organizar las aplicaciones por categorías para sus usuarios.  
- Algunas aplicaciones (como Microsoft Project y Microsoft Visio) requieren Portal de empresa implementar con Escritorio administrado de Microsoft.
- Los administradores de TI pueden personalizar Portal de empresa para su organización. Esto incluye la creación de imágenes de marca, la adición de contactos de soporte técnico local y mucho más. Para obtener más información, [consulta How to Configure the Microsoft Intune Portal de empresa app](/intune/company-portal-app).   

En este tema se documenta el proceso para implementar el Portal de empresa de Intune a los Escritorio administrado de Microsoft usuarios. El proceso general tiene este aspecto:
1. Comprar Portal de empresa desde Microsoft Store para Empresas y sincronizar con Intune
2. Asignar Portal de empresa a los usuarios
3. Comunicar el cambio a los usuarios

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Paso 1: comprar Portal de empresa desde Microsoft Store para Empresas y sincronizar con Intune
Para obtener información sobre cómo comprar las aplicaciones y sincronizarlas con Intune, consulta Microsoft Store para Empresas [aplicaciones en](deploy-apps.md#msfb-apps) Deploy apps to *Escritorio administrado de Microsoft devices*.

En este tema se proporciona información sobre cómo: 
- Comprar Portal de empresa desde Microsoft Store para Empresas 
- Forzar la sincronización entre Intune y Microsoft Store para Empresas
- Comprobar la sincronización activa entre Intune y Microsoft Store para Empresas 

## <a name="step-2---assign-company-portal-to-your-users"></a>Paso 2: Asignar Portal de empresa a los usuarios
Después de la inscripción en Escritorio administrado de Microsoft, implementaremos automáticamente Portal de empresa tu inquilino e instalaremos la aplicación en Escritorio administrado de Microsoft dispositivos de la organización.

## <a name="step-3---communicate-change-to-your-users"></a>Paso 3: Comunicar el cambio a los usuarios
Como administrador de TI de su organización, es importante que los usuarios sepan cómo usar Portal de empresa en su organización. Escritorio administrado de Microsoft recomienda:
- Pasos para instalar aplicaciones desde el Portal de empresa. Para obtener más información, consulta [Instalar y compartir aplicaciones en el dispositivo.](/intune-user-help/install-apps-cpapp-windows)
- Cómo enviar solicitudes a los administradores de TI para aplicaciones que no están disponibles actualmente. Para obtener más información, [consulta Solicitar una aplicación para el trabajo o la escuela.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Escritorio administrado de Microsoft

1. [Agregar y verificar los contactos de administración en el portal de administración ](add-admin-contacts.md)
2. [Ajustar el acceso condicional](conditional-access.md)
3. [Asignar licencias](assign-licenses.md)
4. Implementar Portal de empresa de Intune (este tema)
5. [Habilitar Enterprise State Roaming](enterprise-state-roaming.md)
6. [Instalar dispositivos](set-up-devices.md)
7. [Prepare a los usuarios para que usen los dispositivos](get-started-devices.md)
8. [Implementar aplicaciones](deploy-apps.md)
