---
title: Solución de problemas de movilidad y seguridad básicas
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Pruebe estos pasos para realizar un seguimiento de los problemas básicos de movilidad y seguridad.
ms.openlocfilehash: 1b1b7d67eb07c67c320554c1d64701983da30e15
ms.sourcegitcommit: db1e48af88995193f15bbd5962f5101a6088074b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2022
ms.locfileid: "65636072"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Solución de problemas de movilidad y seguridad básicas

Si tiene problemas al intentar inscribir un dispositivo en Basic Mobility and Security, pruebe los pasos que se indican aquí para realizar un seguimiento del problema. Si los pasos generales no corrigen el problema, consulte una de las secciones posteriores con pasos específicos para el tipo de dispositivo.

## <a name="steps-to-try-first"></a>Pasos para intentarlo primero

Para empezar, compruebe lo siguiente:

- Asegúrese de que el dispositivo aún no está inscrito con otro proveedor de administración de dispositivos móviles, como Intune.

- Asegúrese de que el dispositivo está establecido en la fecha y hora correctas.

- Cambie a una red WIFI o de telefonía móvil diferente en el dispositivo.

- Para Android o iOS dispositivos, desinstale y vuelva a instalar la aplicación Portal de empresa de Intune en el dispositivo. 

## <a name="ios-phone-or-tablet"></a>iOS teléfono o tableta

- Asegúrese de que ha configurado un certificado APNs. Para obtener más información, consulte [Creación de un certificado de APNs para dispositivos iOS](create-an-apns-certificate-for-ios-devices.md).

- En **Configuración** >  **GeneralProfile** >  **(o Administración de dispositivos),** asegúrese de que un perfil de administración aún no está instalado. Si es así, quítelo.

- Si ve el mensaje de error "No se pudo inscribir el dispositivo", inicie sesión en Microsoft 365 y asegúrese de que se ha asignado una licencia que incluye Exchange Online al usuario que ha iniciado sesión en el dispositivo.

- Si ve el mensaje de error "No se pudo instalar el perfil", pruebe una de las siguientes acciones:

    - Asegúrese de que Safari es el explorador predeterminado del dispositivo y de que las cookies no están deshabilitadas.

    - Reinicie el dispositivo y, a continuación, vaya a portal.manage.microsoft.com. Inicie sesión con el identificador de usuario y la contraseña de Microsoft 365 e intente instalar el perfil manualmente.

## <a name="windows-rt"></a>Windows RT

- Asegúrese de que el dominio está configurado en Microsoft 365 para trabajar con Basic Mobility and Security. Para obtener más información, consulte [Configuración de Basic Mobility and Security](set-up.md).
    
- Asegúrese de que el usuario está eligiendo **Activar en** lugar de elegir **Unirse**.

## <a name="windows-10-pc"></a>Windows 10 PC

- Asegúrese de que el dominio está configurado en Microsoft 365 para trabajar con Basic Mobility and Security. Para obtener más información, consulte [Configuración de Basic Mobility and Security](set-up.md).
    
- A menos que tenga Azure Active Directory Premium, asegúrese de que el usuario elija **Inscribirse en Administración de dispositivos solo en** lugar de elegir **Conectar**.

## <a name="android-phone-or-tablet"></a>Android teléfono o tableta

- Asegúrese de que el dispositivo se está ejecutando Android.

- Asegúrese de que Chrome está actualizado y está establecido como el explorador predeterminado.

- Si ve el mensaje de error "No se pudo inscribir este dispositivo", inicie sesión en Microsoft 365 y asegúrese de que se ha asignado una licencia que incluye Exchange Online al usuario que ha iniciado sesión en el dispositivo.

- Compruebe el Área de notificación en el dispositivo para ver si hay alguna acción de usuario final necesaria pendiente y, si es así, complete las acciones.