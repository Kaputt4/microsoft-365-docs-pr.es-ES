---
title: Realizar una toma de administración interna
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
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
description: Obtenga información sobre cómo comprobar la propiedad del dominio y el correo electrónico para asumir una cuenta no administrada creada por un usuario de autoservicio que se inscriba en Microsoft 365.
ms.openlocfilehash: 1201ea967fb829e43433cb5ed49f073b1d862728
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806005"
---
# <a name="perform-an-internal-admin-takeover"></a>Realizar una toma de administración interna

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si es un administrador y desea asumir una cuenta no administrada creada por un registro de usuario de autoservicio, puede realizar una toma de posesión de administrador interna siguiendo los pasos descritos en este artículo.

> [!NOTE]
> Un registro de autoservicio para cualquier servicio en la nube que use Azure AD agrega al usuario a un directorio de Azure AD no administrado o "sombra" y crea una cuenta no administrada. Una cuenta no administrada es un directorio sin un administrador global. Para determinar si una cuenta está administrada o no administrada, consulte [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="before-you-begin"></a>Antes de empezar

Cuando un usuario se inscribe en Microsoft 365 con una dirección de correo electrónico, se crea automáticamente una cuenta para ellos. Si un administrador desea administrar los usuarios en la cuenta o comprar servicios Microsoft 365 adicionales, debe convertirse en administrador de la cuenta siguiendo estos pasos para realizar una toma de posesión de administrador.

## <a name="step-1-verify-your-email-address"></a>Paso 1: Comprobar la dirección de correo electrónico

> [!NOTE]
> Si el autoservicio está habilitado en su cuenta, los usuarios pueden suscribirse a servicios gratuitos, como Power BI, por su cuenta. Estos servicios se usan específicamente en casos en los que una suscripción de usuario de autoservicio haya creado la cuenta no administrada que desea asumir como administrador. En el paso 1, se crea una cuenta de usuario para el dominio que desea quitar mediante Power BI para iniciar el asistente para la toma de posesión de administrador para que pueda convertirse en el administrador de la cuenta de dominio no administrada.

1. Para registrarse en Power BI, vaya al sitio [Power BI](https://powerbi.com) y seleccione **Iniciar prueba gratuita de FreeStart** >  (en Compartir con Power BI Pro). 

2. Registrarse con una cuenta de usuario que use el nombre de dominio de su organización (como `powerbiadmin@contoso.com`). Si tu cuenta ya está en uso, inicia sesión con la contraseña actual.

3. Compruebe el código de verificación **del** correo electrónico y escriba el código para validar la dirección de correo electrónico.

## <a name="step-2-create-a-new-account-for-admin-access"></a>Paso 2: Crear una nueva cuenta para el acceso de administrador

1. Cuando escriba el código de verificación, se le mostrará a una página donde puede crear una nueva cuenta.

2. Rellene los campos de nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, siga los pasos para crear la cuenta.

## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Paso 3: Comprobar la propiedad del dominio y convertirse en administrador

1. Después de completar el paso 2, seleccione el icono del Centro de administración en el panel de navegación izquierdo (como alternativa, vaya a un explorador y escriba ).`https://admin.microsoft.com`

    Se le redirigirá al Asistente para la toma de posesión de administrador.

2. Seleccione **Siguiente** y compruebe que es el propietario del dominio que desea asumir agregando un registro TXT al registrador de dominios.

    El asistente le proporcionará el registro TXT que desea agregar, así como un vínculo al sitio web del registrador y un vínculo a instrucciones paso a paso.

3. En la **página Ya eres administrador** , selecciona **Ir al Centro de administración**.

    Tiene los privilegios de administrador necesarios para administrar la cuenta en el Centro de administración. Por ejemplo, puede administrar usuarios y grupos de cuentas, comprar nuevas suscripciones, realizar asignaciones de usuarios y administrar los dominios de cuenta.

    Si quieres quitar el dominio de esta cuenta para poder agregarlo a otra cuenta, consulta [Quitar un dominio de otra cuenta](remove-a-domain-from-another-account.md).
  
## <a name="related-content"></a>Contenido relacionado

YouTube: [tres pasos para realizar una](https://www.youtube.com/watch?v=xt5EsrQBZZk) toma de administración de TI para Power BI y Microsoft 365 (vídeo)\
[Toma de administración en Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (artículo)\
[Uso del registro de autoservicio en la organización](self-service-sign-up.md) (artículo)\
[Descripción de la Power BI de administrador del servicio de mantenimiento](/power-bi/service-admin-role) (artículo)