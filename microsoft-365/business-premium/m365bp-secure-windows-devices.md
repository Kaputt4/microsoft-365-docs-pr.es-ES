---
title: Proteger dispositivos Windows
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Obtenga información sobre cómo configurar las opciones de la directiva de dispositivo predeterminada que recibirá cualquier dispositivo Windows al iniciar sesión en su cuenta profesional o educativa.
ms.openlocfilehash: 5ac09788d609752d12a6ae6efadfa8739c5a4f9a
ms.sourcegitcommit: c216ffa5da8f431e4380bb133a234ae7d94144c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2022
ms.locfileid: "65893091"
---
# <a name="secure-windows-devices"></a>Proteger dispositivos Windows

El objetivo aquí es configurar las opciones que forman parte de la directiva de dispositivo predeterminada para Windows 10 o 11. Todos los usuarios que se conecten a un dispositivo Windows, incluidos dispositivos móviles y equipos PC, recibirán automáticamente esta configuración al iniciar sesión con su cuenta profesional. Recomendamos que acepte la directiva predeterminada durante la configuración y que, posteriormente, agregue directivas para grupos de usuarios específicos.

## <a name="before-you-begin"></a>Antes de empezar

Para poder configurar dispositivos Windows para usuarios de Microsoft 365 Empresa Premium, asegúrese de que todos los dispositivos Windows ejecutan Windows 10 Pro, versión 1703 (Creators Update) o Windows 11 Pro.

Windows 10 Pro (o Windows 11 Pro) es un requisito previo para implementar Windows 10 Business, que es un conjunto de servicios en la nube y funcionalidades de administración de dispositivos que complementan Windows 10 Pro y Windows 11 Pro, y permiten la administración centralizada y los controles de seguridad de Microsoft 365 Empresa Premium.

[Obtenga más información sobre los requisitos de Microsoft 365 Empresa Premium](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab).

## <a name="windows-10-pro-and-windows-11-pro"></a>Windows 10 Pro y Windows 11 Pro

Si hay dispositivos Windows que ejecuten versiones anteriores de Windows, como Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, la suscripción a Microsoft 365 Empresa Premium da derecho a actualizar esos dispositivos a Windows 10 Pro o Windows 11 Pro.
  
Para obtener más información sobre cómo actualizar dispositivos Windows, consulte los siguientes artículos:

- [Actualizar Windows Home a Windows 10 o Windows 11 Pro](https://support.microsoft.com/windows/upgrade-windows-home-to-windows-pro-ef34d520-e73f-3198-c525-d1a218cc2818)
- [Actualizar a Windows 10 Pro](https://support.microsoft.com/windows/upgrade-to-windows-10-pro-71ecc746-0f81-a4c0-bd4b-0db8559e0796)

<!---
Could not find the Win11 equivalent upgrade link.
---> 
  
## <a name="secure-your-windows-10-and-11-devices"></a>Proteger los dispositivos Windows 10 y 11

De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles:<br/><br/>

|Configuración  <br/> |Descripción  <br/> |
|:-----|:-----|
|Ayudar a proteger los equipos frente a virus y otras amenazas mediante Antivirus de Microsoft Defender  <br/> |Es necesario que el antivirus Microsoft Defender esté activado para proteger los equipos PC de los peligros de estar conectados a Internet.  <br/> |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.  <br/> |
|Ayudar a proteger archivos y carpetas en equipos PC ante el acceso no autorizado con BitLocker  <br/> |BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso de robo o pérdida de un equipo. Para más información, vea [Preguntas más frecuentes sobre BitLocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).  <br/> |
|Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo  <br/> |Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.  <br/> |

## <a name="next-objective"></a>Siguiente objetivo

[Administrar dispositivos Windows](m365bp-manage-windows-devices.md)
