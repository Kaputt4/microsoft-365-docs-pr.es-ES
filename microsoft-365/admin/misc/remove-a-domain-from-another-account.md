---
title: Eliminación de un dominio de otra cuenta
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
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
ms.openlocfilehash: 3f8a508f799e845c56584b32af294df69eaba330
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68718686"
---
# <a name="perform-an-internal-admin-takeover"></a>Realizar una adquisición de administrador interna

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si es administrador y quiere asumir una cuenta no administrada creada por un registro de usuario de autoservicio, puede hacerlo realizando una adquisición de administrador interna.

> [!NOTE]
> Un registro de autoservicio para cualquier servicio en la nube que use Azure AD agrega el usuario a un directorio de Azure AD no administrado o "sombra" y crea una cuenta no administrada. Una cuenta no administrada es un directorio sin un administrador global. Para determinar si una cuenta está administrada o no administrada, consulte [Determinación del tipo de inquilino](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="before-you-begin"></a>Antes de empezar

A veces no puede agregar un dominio a la cuenta de su organización porque otra persona ya se ha registrado en Microsoft 365 mediante una dirección de correo electrónico asociada a ese nombre de dominio. Pero puede quitar el dominio de la otra cuenta no administrada y agregarlo a la cuenta administrada de la organización.

Sin embargo, para poder quitar el dominio de la otra cuenta y agregarlo a la cuenta, debe unirse a la cuenta no administrada y convertirse en administrador de esa cuenta. A continuación, quitará el dominio de la cuenta no administrada, volverá a iniciar sesión en la cuenta y agregará el dominio a la cuenta administrada.

En los pasos de este artículo se describe solo cómo unirse a la otra cuenta (pasos 1 y 2) y seguir los pasos del Asistente para la adquisición de administrador para convertirse en el administrador de la cuenta no administrada (paso 3).

Después de convertirse en administrador de la cuenta no administrada, puede quitar el dominio de la cuenta no administrada y agregarlo a la cuenta. 

## <a name="step-1-verify-your-email-address"></a>Paso 1: Comprobar la dirección de correo electrónico

> [!NOTE]
> Si el autoservicio está habilitado en su cuenta, los usuarios pueden suscribirse a servicios gratuitos, como Power BI, por su cuenta. Estos servicios se usan específicamente en casos en los que una suscripción de usuario de autoservicio ha creado la cuenta no administrada que quiere asumir como administrador. En el paso 1, cree una cuenta de usuario para el dominio que desea quitar mediante Power BI para iniciar el Asistente para la adquisición de administrador para que pueda convertirse en el administrador de la cuenta de dominio no administrada.

1. Para registrarse en Power BI, vaya al [sitio de Power BI](https://powerbi.com) y seleccione **Iniciar** prueba **gratuita de inicio gratis** >  (en el cuadro Compartir con Power BI Pro). 

2. Regístrese con una cuenta de usuario que use el nombre de dominio de su organización (por ejemplo `powerbiadmin@contoso.com`, ). Si su cuenta ya está en uso, inicie sesión con la contraseña actual.

3. Compruebe el **código de verificación** en su correo electrónico y escriba el código para validar su dirección de correo electrónico.

## <a name="step-2-create-a-new-account-for-admin-access"></a>Paso 2: Creación de una nueva cuenta para el acceso de administrador

1. Al escribir el código de verificación, se le mostrará una página en la que puede crear una cuenta nueva.

2. Rellene los campos nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, seleccione **Iniciar**.

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Paso 3: Comprobar la propiedad del dominio y convertirse en el administrador

1. Después de completar el paso 2, seleccione el icono del Centro de administración en el panel de navegación izquierdo (como alternativa, vaya a un explorador y escriba `https://admin.microsoft.com`).

    Se le redirigirá al asistente para la adquisición de administración.

1. Seleccione **Siguiente** y compruebe que es el propietario del dominio que desea asumir agregando un registro TXT al registrador de dominios. 

    El asistente le proporcionará el registro TXT que se va a agregar, así como un vínculo al sitio web del registrador y un vínculo a las instrucciones paso a paso.

1. En la página **Ahora es el administrador** , seleccione **Ir al centro de administración**.

    Ahora tiene los privilegios de administrador necesarios para quitar el dominio de la otra cuenta. 
## <a name="related-content"></a>Contenido relacionado

YouTube: [3 pasos para realizar una adquisición de TI Administración para Power BI y Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (vídeo)\
[Administración adquisición en Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (artículo)\
[Uso del registro de autoservicio en su organización](self-service-sign-up.md) (artículo)\
[Descripción del rol de administrador servicio Power BI](/power-bi/service-admin-role) (artículo)
