---
title: Solucionar problemas de movilidad y seguridad básicas
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
description: Pruebe estos pasos para realizar un seguimiento de los problemas básicos de movilidad y seguridad
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876857"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Solucionar problemas de movilidad y seguridad básicas

Si tienes problemas al intentar inscribir un dispositivo en Movilidad básica y seguridad, sigue estos pasos para realizar un seguimiento del problema. Si los pasos generales no solucionan el problema, consulta una de las secciones posteriores con pasos específicos para el tipo de dispositivo.

## <a name="steps-to-try-first"></a>Pasos para probar primero

Para empezar, compruebe lo siguiente:

- Asegúrese de que el dispositivo aún no está inscrito en otro proveedor de administración de dispositivos móviles, como Intune.

- Asegúrate de que el dispositivo esté establecido en la fecha y hora correctas.

- Cambie a una red WIFI o móvil diferente en el dispositivo.

- Para dispositivos Android o iOS, desinstale y vuelva a instalar la Portal de empresa de Intune en el dispositivo. 

## <a name="ios-phone-or-tablet"></a>Teléfono o tableta iOS

- Asegúrese de que ha configurado un certificado de APNs. Para obtener más información, consulta [Crear un certificado APNs para dispositivos iOS.](create-an-apns-certificate-for-ios-devices.md)

- En **Configuración** general (o administración de   >  ****   >  **dispositivos),** asegúrese de que un perfil de administración no esté instalado. Si es así, quítela.

- Si ves el mensaje de error "El dispositivo no se inscribió", inicia sesión en Microsoft 365 y asegúrate de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.

- Si ve el mensaje de error"No se pudo instalar el perfil", pruebe uno de los siguientes procedimientos:

    - Asegúrese de que Safari es el explorador predeterminado en el dispositivo y de que las cookies no están deshabilitadas.

    - Reinicie el dispositivo y, a continuación, vaya a portal.manage.microsoft.com. Inicie sesión con su Microsoft 365 de usuario y contraseña e intente instalar el perfil manualmente.

## <a name="windows-rt"></a>Windows RT

- Asegúrese de que el dominio está configurado en Microsoft 365 para trabajar con movilidad y seguridad básicas. Para obtener más información, consulta [Configurar movilidad básica y seguridad.](set-up.md)
    
- Asegúrese de que el usuario elige **Activar en** lugar de   elegir **Unirse.**

## <a name="windows-10-pc"></a>Windows 10 PC

- Asegúrese de que el dominio está configurado en Microsoft 365 para trabajar con movilidad y seguridad básicas. Para obtener más información, consulta [Configurar movilidad básica y seguridad.](set-up.md)
    
- A menos que haya Azure Active Directory Premium, asegúrese de que el usuario elija **Inscribirse** en administración de dispositivos solo en lugar de elegir    **Conectar**.

## <a name="android-phone-or-tablet"></a>Teléfono o tableta Android

- Asegúrate de que el dispositivo ejecuta Android 4.4 o posterior.

- Asegúrate de que Chrome esté actualizado y esté configurado como el explorador predeterminado.

- Si ves el mensaje de error "No pudimos inscribir este dispositivo", inicia sesión en Microsoft 365 y asegúrate de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.

- Comprueba el Área de notificaciones en el dispositivo para ver si hay acciones necesarias del usuario final pendientes y, si lo están, completa las acciones.