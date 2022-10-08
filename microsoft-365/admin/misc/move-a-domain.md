---
title: Mover un dominio comprobado en una cuenta no administrada
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Obtenga información sobre cómo unirse a una cuenta no administrada para quitar el dominio de la cuenta y agregar el dominio a la cuenta.
ms.openlocfilehash: 7b7befdae4279b4b08ff076b88ed552b2bc411c3
ms.sourcegitcommit: c757f434da78bae71d4b476e14836fdf4da9f31e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2022
ms.locfileid: "67884384"
---
# <a name="move-a-domain-verified-in-an-unmanaged-account"></a>Mover un dominio comprobado en una cuenta no administrada

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si es administrador y ha intentado agregar un dominio a su cuenta de Microsoft 365, pero está bloqueado porque el dominio se comprueba para una cuenta no administrada, puede convertirse en el administrador de la cuenta no administrada para quitar el dominio y agregarlo a su cuenta.

> [!NOTE]
> Un registro de autoservicio para cualquier servicio en la nube que use Azure AD agrega el usuario a un directorio de Azure AD no administrado o "sombra" y crea una cuenta no administrada. Una cuenta no administrada es un directorio sin un administrador global. Para determinar si una cuenta está administrada o no administrada, consulte [Determinación del tipo de inquilino](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).
  
## <a name="before-you-begin"></a>Antes de empezar

A veces no puede agregar un dominio a la cuenta de su organización porque otra persona ya se ha registrado en Microsoft 365 mediante una dirección de correo electrónico asociada a ese nombre de dominio. Pero puede quitar el dominio de la otra cuenta no administrada y agregarlo a la cuenta de la organización.

En primer lugar, deberá unirse a la cuenta no administrada y convertirse en administrador de esa cuenta (pasos del 1 al 3). A continuación, puede quitar el dominio de la cuenta (paso 4), volver a iniciar sesión en la cuenta de la organización y agregar el dominio a su cuenta (paso 5).

## <a name="step-1-get-an-invitation-to-join-the-unmanaged-account"></a>Paso 1: Obtener una invitación para unirse a la cuenta no administrada

Después de intentar agregar un dominio a su cuenta, es posible que reciba un mensaje que indica que alguien ya se ha registrado en Microsoft 365 mediante la dirección de correo electrónico. El paso 1 consiste en solicitar una invitación para unirse a la otra cuenta e iniciar el proceso de realización de una adquisición de administrador.

1. Vaya a la Centro de administración de Microsoft 365 >**Dominios** >  **de configuración** > **+ Agregar dominio** y agregue el nombre de dominio.

1. Si ve un mensaje que indica que no puede agregar el dominio porque otras personas ya se han registrado con una dirección de correo electrónico para el dominio, escriba el nombre de usuario de la cuenta y, a continuación, seleccione **Enviarme la invitación**.

1. Cierre la sesión de la cuenta actual para que pueda iniciar sesión en la cuenta no administrada.

    Compruebe el correo electrónico para obtener una invitación que le ayude a unirse a la cuenta no administrada y seleccione el vínculo proporcionado en el correo electrónico.

    Escriba el **código de verificación** del correo electrónico para validar su dirección de correo electrónico.

## <a name="step-2-complete-signup-with-email-instructions"></a>Paso 2: Completar el registro con instrucciones de correo electrónico

1. Al escribir el código de verificación, se le mostrará una página en la que puede crear una cuenta nueva.

2. Rellene los campos nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, complete los pasos para crear la cuenta.

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Paso 3: Comprobar la propiedad del dominio y convertirse en el administrador

1. Después de completar el paso 2, seleccione el icono del Centro de administración en el panel de navegación izquierdo (como alternativa, vaya a un explorador y escriba `https://admin.microsoft.com`).

    Se le redirigirá al asistente para la adquisición de administración.

1. Seleccione **Siguiente** y compruebe que es el propietario del dominio que desea asumir agregando un registro TXT al registrador de dominios.

    El asistente le proporcionará el registro TXT que se va a agregar, así como un vínculo al sitio web del registrador y un vínculo a las instrucciones paso a paso.

1. En la página **Ahora es el administrador** , seleccione **Ir al centro de administración**.

    Ahora tiene los privilegios de administrador necesarios para quitar el dominio de la cuenta anteriormente no administrada.

## <a name="step-4-remove-a-domain-from-the-unmanaged-account"></a>Paso 4: Quitar un dominio de la cuenta no administrada

1. Vaya a **Usuarios** > **usuarios activos** para la cuenta que ha unido en el paso 2 y, a continuación, seleccione el nombre para mostrar del nombre de usuario con el que ha iniciado sesión.

1. En **Nombre de usuario**, seleccione **Administrar nombre de usuario** y mueva el usuario al dominio de onmicrosoft eligiendo el dominio onmicrosoft.com en la lista desplegable.

1. Cierre la sesión de la cuenta y vuelva a iniciar sesión con el nuevo `username@account.onmicrosoft.com`.

1. Seleccione **Dominios de configuración** > , busque el dominio que desea agregar a la otra cuenta y seleccione **Quitar dominio**.

    Si se le pide que seleccione otro dominio como predeterminado, elija el dominio onmicrosoft.com.

    Si otros usuarios usan el dominio, debe quitarlos. Elija entre las opciones **quitar automáticamente**, mover manualmente los usuarios a su dominio o quitar los usuarios por completo.

   > [!NOTE]
   > Vuelva a comprobarlo, ya que el dominio puede tardar algún tiempo en quitarse de la cuenta. La eliminación se completa cuando el dominio desaparece de la cuenta.

1. Cierre la sesión de la cuenta.

## <a name="step-5-add-the-domain-to-your-account"></a>Paso 5: Agregar el dominio a su cuenta

1. Inicie sesión en la cuenta donde desea agregar el dominio.

1. Seleccione **Dominios** >  **de configuración** > **+ Agregar dominio** y, a continuación, escriba el nombre de dominio para continuar con los pasos del asistente para comprobar la propiedad del dominio en esta cuenta y completar la adición del dominio a su cuenta.
  
## <a name="related-content"></a>Contenido relacionado

[Realizar una adquisición de administrador interno](become-the-admin.md) (artículo)
