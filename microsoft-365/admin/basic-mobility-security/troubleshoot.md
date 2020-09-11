---
title: Solución de problemas de movilidad y seguridad básicas
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Pruebe estos pasos para realizar un seguimiento de los problemas básicos de la movilidad y la seguridad
ms.openlocfilehash: 43e7533e598f769dd5f2bcae28c4252f96a9be76
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430299"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Solución de problemas de movilidad y seguridad básicas

Si tiene problemas al intentar inscribir un dispositivo en la movilidad y la seguridad básica, siga los pasos que se indican a continuación para realizar un seguimiento del problema. Si los pasos generales no solucionan el problema, consulte una de las secciones posteriores con pasos específicos para el tipo de dispositivo.

## <a name="steps-to-try-first"></a>Pasos para probar primero

Para empezar, compruebe lo siguiente:

- Asegúrese de que el dispositivo todavía no está inscrito con otro proveedor de administración de dispositivos móviles, como Intune.
    
- Asegúrese de que el dispositivo está configurado con la fecha y hora correctas.
    
- Cambia a otra red de telefonía móvil o Wi-Fi en el dispositivo.
    
- Para dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación del portal de empresa de Intune en el dispositivo. 

## <a name="ios-phone-or-tablet"></a>tableta o teléfono iOS

- Asegúrese de que ha configurado un certificado de APNs. Para obtener más información, vea [crear un certificado de APNs para dispositivos iOS](create-an-apns-certificate-for-ios-devices.md).
    
- En **configuración**   >  **General**de   >  **perfil (o administración de dispositivos)**, asegúrese de que ya hay un perfil de Administración instalado. Si es así, quítela.
    
- Si ve el mensaje de error "el dispositivo no pudo inscribirse", inicie sesión en Microsoft 365 y asegúrese de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.
    
- Si aparece el mensaje de error "no se pudo instalar el perfil", pruebe una de las siguientes opciones:
    
    - Asegúrese de que Safari es el explorador predeterminado en el dispositivo y de que las cookies no están deshabilitadas.
    
    - Reinicie el dispositivo y, a continuación, vaya a portal.manage.microsoft.com. Inicie sesión con su identificador de usuario y contraseña de Microsoft 365 e intente instalar el perfil de forma manual.    

## <a name="windows-rt"></a>Windows RT

- Asegúrese de que su dominio está configurado en Microsoft 365 para trabajar con la movilidad y la seguridad básicas. Para obtener más información, consulte [set up Basic Mobility and Security](set-up.md).
    
- Asegúrese de que el usuario está seleccionando **activar en**   lugar de elegir **unirse**.    

## <a name="windows-10-pc"></a>PC con Windows 10

- Asegúrese de que su dominio está configurado en Microsoft 365 para trabajar con la movilidad y la seguridad básicas. Para obtener más información, consulte [set up Basic Mobility and Security](set-up.md).
    
- A menos que tenga Azure Active Directory Premium, asegúrese de que el usuario solo está seleccionando **inscribirse en la administración de dispositivos**en   lugar de elegir **conectar**.

## <a name="android-phone-or-tablet"></a>Tableta o teléfono Android

- Asegúrese de que el dispositivo está ejecutando Android 4,4 o posterior.
    
- Asegúrese de que Chrome está actualizado y establecido como explorador predeterminado.
    
- Si ve el mensaje de error "no se pudo inscribir este dispositivo", inicie sesión en Microsoft 365 y asegúrese de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.
    
- Compruebe el área de notificación en el dispositivo para ver si hay acciones del usuario final necesarias y, si es así, complete las acciones.