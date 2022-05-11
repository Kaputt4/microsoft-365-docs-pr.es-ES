---
title: Configuración de dispositivos Windows para usuarios Microsoft 365 Empresa Premium
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Configure Windows dispositivos que ejecutan Windows 10 Pro para Microsoft 365 Empresa Premium usuarios, lo que permite controles de administración y seguridad centralizados.
ms.openlocfilehash: b9c8a5eb724a74959983e86dcdcb8f2f8f96b540
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65318588"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Configuración de dispositivos Windows para usuarios Microsoft 365 Empresa Premium

## <a name="before-you-begin"></a>Antes de empezar

Antes de configurar dispositivos Windows para Microsoft 365 Empresa Premium usuarios, asegúrese de que todos los dispositivos Windows ejecutan Windows 10 Pro, versión 1703 (Creators Update) o Windows 11 Pro. 

Windows 10 Pro (o Windows 11 Pro) es un requisito previo para implementar Windows 10 Business, que es un conjunto de servicios en la nube y funcionalidades de administración de dispositivos que complementan Windows 10 Pro y Windows 11 Pro y habilite los controles centralizados de administración y seguridad de Microsoft 365 Empresa Premium.

[Obtenga más información sobre los requisitos de Microsoft 365 Empresa Premium](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab).

## <a name="windows-10-pro-and-windows-11-pro"></a>Windows 10 Pro y Windows 11 Pro

Si tiene Windows dispositivos que ejecutan versiones anteriores de Windows, como Windows 7 Pro, Windows 8 Pro o Windows 8.1 Pro, la suscripción de Microsoft 365 Empresa Premium le da derecho a actualizar esos dispositivos a Windows 10 Pro o Windows 11 Pro.
  
Para obtener más información sobre cómo actualizar Windows dispositivos, consulte los artículos siguientes:

- [Actualice Windows Inicio a Windows Pro](https://support.microsoft.com/windows/upgrade-windows-home-to-windows-pro-ef34d520-e73f-3198-c525-d1a218cc2818)
- [Actualizar a Windows 10 Pro](https://support.microsoft.com/windows/upgrade-to-windows-10-pro-71ecc746-0f81-a4c0-bd4b-0db8559e0796)
  
Después de actualizar, consulte [Comprobación de que el dispositivo está conectado a Azure AD](#verify-the-device-is-connected-to-azure-ad) para comprobar que tiene la actualización o para asegurarse de que la actualización ha funcionado.

## <a name="join-windows-devices-to-your-organizations-azure-ad"></a>Unión de dispositivos Windows a Azure AD de la organización

Cuando todos los dispositivos Windows de la empresa ejecutan Windows 10 Pro o Windows 11 Pro, puede unir estos dispositivos a la Azure Active Directory de su organización (Azure AD). 

1. En un dispositivo Windows, seleccione el logotipo de Windows y, a continuación, el icono de Configuración.
  
2. En **Configuración**, vaya a **CuentasAcceso** >  a **la Conectar** **profesional o educativa**\>.
  
3. Escriba su dirección de correo electrónico y, a continuación, elija **Siguiente**.

4. Siga las indicaciones para completar el proceso.

## <a name="verify-the-device-is-connected-to-azure-ad"></a>Comprobar que un dispositivo está conectado a Azure AD

Para comprobar el estado de sincronización, en la página **Access work or school** **de Configuración**, seleccione el área **Conectado a** _ \<organization name\> _ para exponer los botones **Información** y **Desconectar**. Elija **Información** para obtener el estado de sincronización. 
  
En la página **Estado de sincronización** , elija **Sincronizar** para obtener las directivas de administración de dispositivos móviles más recientes en el equipo.  
  
## <a name="next-steps"></a>Siguientes pasos

Para configurar los dispositivos móviles, consulte [Configuración de dispositivos móviles para Microsoft 365 Empresa Premium usuarios](set-up-mobile-devices.md), 

Para aumentar la protección, consulte [Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../security-and-compliance/secure-your-business-data.md).
  

