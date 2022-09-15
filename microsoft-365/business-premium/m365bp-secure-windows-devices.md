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
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: high
ms.date: 08/16/2022
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo proteger los dispositivos Windows de su empresa mediante la configuración integrada.
ms.openlocfilehash: 32632b416b79ae6f1c58b91fbed2035b44690694
ms.sourcegitcommit: db89873e22a12705ed313964c1bc2fa19d4fe719
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67712652"
---
# <a name="secure-windows-devices"></a>Proteger dispositivos Windows

El objetivo aquí es configurar las opciones que forman parte de la directiva de dispositivo predeterminada para Windows 10 o 11. Todos los usuarios que conecten un dispositivo Windows, incluidos los dispositivos móviles y los equipos, iniciando sesión con su cuenta profesional recibirán automáticamente esta configuración. Recomendamos que acepte la directiva predeterminada durante la configuración y que, posteriormente, agregue directivas para grupos de usuarios específicos.

## <a name="before-you-begin"></a>Antes de empezar

Para poder configurar dispositivos Windows para los usuarios Premium de Microsoft 365 Business, asegúrese de que todos los dispositivos Windows estén ejecutando Windows 10 Pro.

Windows 10 Pro es un requisito previo para implementar Windows 10 Business, que es un conjunto de servicios en la nube y funcionalidades de administración de dispositivos que complementan Windows 10 Pro y Windows 11 Pro, y permiten la administración centralizada y los controles de seguridad de Microsoft 365 Empresa Premium.

[Obtenga más información sobre los requisitos de Microsoft 365 Empresa Premium](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab).

## <a name="windows-10-pro"></a>Windows 10 Pro

Si hay dispositivos Windows que ejecuten versiones anteriores de Windows, como Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, la suscripción a Microsoft 365 Empresa Premium da derecho a actualizar esos dispositivos a Windows 10 Pro o Windows 11 Pro.
  
Para obtener más información sobre cómo actualizar dispositivos Windows, vea [actualizar dispositivos Windows a Windows 10 Pro](m365bp-upgrade-windows-10-pro.md).

## <a name="secure-your-windows-10-and-11-devices"></a>Proteger los dispositivos Windows 10 y 11

De forma predeterminada, todas las opciones de configuración están **activadas**. Estas son las opciones de configuración disponibles:

|Configuración |Descripción |
|:-----|:-----|
|Ayudar a proteger los equipos frente a virus y otras amenazas mediante el Antivirus de Microsoft Defender  |Requiere que Antivirus de Microsoft Defender esté activado para proteger los equipos de los peligros de estar conectados a Internet.   |
|Ayudar a proteger los equipos frente a amenazas basadas en web en Microsoft Edge   |Activa opciones de configuración en Edge para proteger a los usuarios de sitios y descargas malintencionados.  |
|Ayudar a proteger archivos y carpetas en equipos contra el acceso no autorizado con BitLocker  |BitLocker protege los datos al cifrar los discos duros del equipo y proteger ante la exposición de datos en caso de robo o pérdida de un equipo. Para más información, vea [Preguntas más frecuentes sobre BitLocker](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).    |
|Apagar la pantalla del dispositivo cuando esté inactivo durante esta cantidad de tiempo  |Garantiza que los datos de la compañía estén protegidos si un usuario está inactivo. Puede que un usuario trabaje en una ubicación pública, como una cafetería, y se aparte o se distraiga durante un momento, lo que dejaría su dispositivo vulnerable ante miradas indiscretas. Esta configuración le permite controlar cuánto tiempo puede estar inactivo un usuario antes de que se apague la pantalla.  |

## <a name="next-objective"></a>Siguiente objetivo

[Administrar dispositivos Windows](m365bp-manage-windows-devices.md)
