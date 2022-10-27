---
title: Realizar una adquisición de administrador interna
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
description: Obtenga información sobre cómo comprobar la propiedad del dominio y el correo electrónico para hacerse cargo de una cuenta no administrada creada por un registro de usuario de autoservicio en Microsoft 365.
ms.openlocfilehash: 271304cf66ffec8503a711be7b5eedbfb9776bc1
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734239"
---
# <a name="internal-admin-takeover"></a>Adquisición del administrador interno

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si es administrador y quiere asumir una cuenta no administrada creada por un registro de usuario de autoservicio, puede realizar una adquisición de administrador interna siguiendo los pasos de este artículo.

> [!NOTE]
> Un registro de autoservicio para cualquier servicio en la nube que use Azure AD agrega el usuario a un directorio de Azure AD no administrado o "sombra" y crea una cuenta no administrada. Una cuenta no administrada es un directorio sin un administrador global. Para determinar si una cuenta está administrada o no administrada, consulte [Determinación del tipo de inquilino](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="before-you-begin"></a>Antes de empezar

Cuando un usuario se registra en los servicios de Microsoft 365 mediante una dirección de correo electrónico, se crea automáticamente una cuenta para ellos. Si un administrador quiere administrar los usuarios de la cuenta o comprar servicios de Microsoft 365 adicionales, debe convertirse en administrador de la cuenta siguiendo estos pasos para realizar una adquisición de administrador.

## <a name="step-1-verify-your-email-address"></a>Paso 1: Comprobar la dirección de correo electrónico

> [!NOTE]
> Si el autoservicio está habilitado en su cuenta, los usuarios pueden suscribirse a servicios gratuitos, como Power BI, por su cuenta. Estos servicios se usan específicamente en casos en los que una suscripción de usuario de autoservicio ha creado la cuenta no administrada que quiere asumir como administrador. En el paso 1, cree una cuenta de usuario para el dominio que desea quitar mediante Power BI para iniciar el Asistente para la adquisición de administrador para que pueda convertirse en el administrador de la cuenta de dominio no administrada.

1. Para registrarse en Power BI, vaya al [sitio de Power BI](https://powerbi.com) y seleccione **Iniciar** prueba **gratuita de inicio gratis** >  (en el cuadro Compartir con Power BI Pro). 

2. Regístrese con una cuenta de usuario que use el nombre de dominio de su organización (por ejemplo `powerbiadmin@contoso.com`, ). Si su cuenta ya está en uso, inicie sesión con la contraseña actual.

3. Compruebe el **código de verificación** en su correo electrónico y escriba el código para validar su dirección de correo electrónico.

## <a name="step-2-create-a-new-account-for-admin-access"></a>Paso 2: Creación de una nueva cuenta para el acceso de administrador

1. Al escribir el código de verificación, se le mostrará una página en la que puede crear una cuenta nueva.

2. Rellene los campos de nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, complete los pasos para crear la cuenta.

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Paso 3: Comprobar la propiedad del dominio y convertirse en el administrador

1. Después de completar el paso 2, seleccione el icono del Centro de administración en el panel de navegación izquierdo (como alternativa, vaya a un explorador y escriba `https://admin.microsoft.com`).

    Se le redirigirá al asistente para la adquisición de administración.

2. Seleccione **Siguiente** y compruebe que es el propietario del dominio que desea asumir agregando un registro TXT al registrador de dominios.

    El asistente le proporcionará el registro TXT que se va a agregar, así como un vínculo al sitio web del registrador y un vínculo a las instrucciones paso a paso.

3. En la página **Ahora es el administrador** , seleccione **Ir al centro de administración**.

    Tiene los privilegios de administrador necesarios para administrar la cuenta en el centro de administración. Por ejemplo, puede administrar usuarios y grupos de cuentas, comprar nuevas suscripciones, realizar asignaciones de usuarios y administrar los dominios de cuenta.

    Si desea quitar el dominio de esta cuenta para poder agregarlo a otra cuenta, consulte [Eliminación de un dominio de otra cuenta](remove-a-domain-from-another-account.md).
  
## <a name="related-content"></a>Contenido relacionado

YouTube: [tres pasos para realizar una adquisición de ti Administración para Power BI y Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (vídeo)\
[Administración adquisición en Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (artículo)\
[Uso del registro de autoservicio en su organización](self-service-sign-up.md) (artículo)\
[Descripción del rol de administrador servicio Power BI](/power-bi/service-admin-role) (artículo)