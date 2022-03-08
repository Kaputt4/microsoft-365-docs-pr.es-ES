---
title: Quitar un dominio de otra cuenta
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
description: Obtenga información sobre cómo unirse a una cuenta no administrada creada por un registro de usuario de autoservicio en Microsoft 365.
ms.openlocfilehash: 0a7cf07a70e241c0b40f28159f31b0c86766bc1d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325675"
---
# <a name="perform-an-internal-admin-takeover"></a>Realizar una toma de administración interna

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si es un administrador y desea asumir una cuenta no administrada creada por un registro de usuario de autoservicio, puede hacerlo realizando una toma de posesión de administrador interna.

> [!NOTE]
> Un registro de autoservicio para cualquier servicio en la nube que use Azure AD agrega al usuario a un directorio de Azure AD no administrado o "sombra" y crea una cuenta no administrada. Una cuenta no administrada es un directorio sin un administrador global. Para determinar si una cuenta está administrada o no administrada, consulte [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="before-you-begin"></a>Antes de empezar

A veces no puede agregar un dominio a la cuenta de la organización porque otra persona ya se ha registrado en Microsoft 365 con una dirección de correo electrónico asociada con ese nombre de dominio. Pero puede quitar el dominio de la otra cuenta no administrada y agregarlo a la cuenta administrada de la organización.

Sin embargo, para poder quitar el dominio de la otra cuenta y agregarlo a su cuenta, debe unirse a la cuenta no administrada y convertirse en administrador de esa cuenta. A continuación, quitará el dominio de la cuenta no administrada, volverá a iniciar sesión en la cuenta y agregará el dominio a la cuenta administrada.

Los pasos de este artículo describen solo cómo unirse a la otra cuenta (pasos 1 y 2) y seguir los pasos del Asistente para la toma de posesión de administrador para convertirse en el administrador de la cuenta no administrada (paso 3).

Después de convertirse en administrador de la cuenta no administrada, puede quitar el dominio de la cuenta no administrada y agregarlo a la cuenta. 

## <a name="step-1-verify-your-email-address"></a>Paso 1: Comprobar la dirección de correo electrónico

> [!NOTE]
> Si el autoservicio está habilitado en su cuenta, los usuarios pueden suscribirse a servicios gratuitos, como Power BI, por su cuenta. Estos servicios se usan específicamente en casos en los que una suscripción de usuario de autoservicio haya creado la cuenta no administrada que desea asumir como administrador. En el paso 1, se crea una cuenta de usuario para el dominio que desea quitar mediante Power BI para iniciar el Asistente para la toma de posesión de administrador para que pueda convertirse en el administrador de la cuenta de dominio no administrada.

1. Para registrarse para Power BI, vaya al sitio Power BI y seleccione Iniciar [](https://powerbi.com) prueba gratuita **de FreeStart** >  (en Compartir con Power BI Pro). 

2. Registrarse con una cuenta de usuario que use el nombre de dominio de su organización (como `powerbiadmin@contoso.com`). Si tu cuenta ya está en uso, inicia sesión con la contraseña actual.

3. Compruebe el código de verificación **del** correo electrónico y escriba el código para validar la dirección de correo electrónico.

## <a name="step-2-create-a-new-account-for-admin-access"></a>Paso 2: Crear una nueva cuenta para el acceso de administrador

1. Cuando escriba el código de verificación, se le mostrará a una página donde puede crear una nueva cuenta.

2. Rellene los campos de nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, seleccione **Inicio**.

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Paso 3: Comprobar la propiedad del dominio y convertirse en administrador

1. Después de completar el paso 2, seleccione el icono del Centro de administración en el panel de navegación izquierdo (como alternativa, vaya a un explorador y escriba ).`https://admin.microsoft.com`

    Se le redirigirá al Asistente para la toma de posesión de administrador.

1. Seleccione **Siguiente** y compruebe que es el propietario del dominio que desea asumir agregando un registro TXT al registrador de dominios. 

    El asistente le proporcionará el registro TXT que desea agregar, así como un vínculo al sitio web del registrador y un vínculo a instrucciones paso a paso.

1. En la **página Ya eres administrador** , selecciona **Ir al Centro de administración**.

    Ahora tiene los privilegios de administrador necesarios para quitar el dominio de la otra cuenta. 
## <a name="related-content"></a>Contenido relacionado

YouTube: [3 pasos para realizar una](https://www.youtube.com/watch?v=xt5EsrQBZZk) toma de administración de TI para Power BI y Microsoft 365 (vídeo)\
[Toma de administración en Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (artículo)\
[Uso del registro de autoservicio en la organización](self-service-sign-up.md) (artículo)\
[Descripción del rol Power BI de administrador de servicio (](/power-bi/service-admin-role)artículo)
