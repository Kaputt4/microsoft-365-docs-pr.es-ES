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
description: Pruebe estos pasos para realizar un seguimiento de los problemas de movilidad y seguridad básicas
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876857"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Solucionar problemas de movilidad y seguridad básicas

Si tiene problemas al intentar inscribir un dispositivo en Movilidad y Seguridad básica, siga estos pasos para realizar un seguimiento del problema. Si los pasos generales no solucionan el problema, consulta una de las secciones posteriores con pasos específicos para el tipo de dispositivo.

## <a name="steps-to-try-first"></a>Pasos para probar primero

Para empezar, compruebe lo siguiente:

- Asegúrate de que el dispositivo no esté inscrito con otro proveedor de administración de dispositivos móviles, como Intune.

- Asegúrate de que el dispositivo está establecido en la fecha y hora correctas.

- Cambia a otra red WIFI o de telefonía móvil en el dispositivo.

- Para dispositivos Android o iOS, desinstale y vuelva a instalar la aplicación Portal de empresa de Intune en el dispositivo. 

## <a name="ios-phone-or-tablet"></a>Teléfono o tableta iOS

- Asegúrese de que ha configurado un certificado de APNs. Para obtener más información, consulta [Crear un certificado APNs para dispositivos iOS.](create-an-apns-certificate-for-ios-devices.md)

- En **Configuración** de perfil general (o administración de   >  ****   >  **dispositivos),** asegúrese de que un perfil de administración no esté instalado todavía. Si es así, quítela.

- Si ve el mensaje de error "El dispositivo no se inscribió", inicie sesión en Microsoft 365 y asegúrese de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.

- Si aparece el mensaje de error "No se pudo instalar el perfil", pruebe uno de los siguientes procedimientos:

    - Asegúrese de que Safari es el explorador predeterminado en el dispositivo y de que las cookies no están deshabilitadas.

    - Reinicia el dispositivo y, a continuación, navega hasta portal.manage.microsoft.com. Inicie sesión con su identificador de usuario y contraseña de Microsoft 365 e intente instalar el perfil manualmente.

## <a name="windows-rt"></a>Windows RT

- Asegúrese de que su dominio está configurado en Microsoft 365 para trabajar con movilidad y seguridad básicas. Para obtener más información, consulta [Configurar movilidad y seguridad básicas.](set-up.md)
    
- Asegúrese de que el usuario elige **Activar** en lugar de   elegir **Unirse.**

## <a name="windows-10-pc"></a>Windows 10 PC

- Asegúrese de que su dominio está configurado en Microsoft 365 para trabajar con movilidad y seguridad básicas. Para obtener más información, consulta [Configurar movilidad y seguridad básicas.](set-up.md)
    
- A menos que tenga Azure Active Directory Premium, **** asegúrese de que el usuario elija Inscribirse en la administración de dispositivos solo en lugar de   elegir **Conectar.**

## <a name="android-phone-or-tablet"></a>Teléfono o tableta Android

- Asegúrate de que el dispositivo ejecuta Android 4.4 o posterior.

- Asegúrese de que Chrome está actualizado y está configurado como explorador predeterminado.

- Si ve el mensaje de error "No hemos podido inscribir este dispositivo", inicie sesión en Microsoft 365 y asegúrese de que se haya asignado una licencia que incluya Exchange Online al usuario que ha iniciado sesión en el dispositivo.

- Comprueba el área de notificación del dispositivo para ver si hay alguna acción necesaria del usuario final pendiente y, si es así, completa las acciones.