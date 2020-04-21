---
title: Realizar un relevo interno del administrador
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Obtenga información sobre cómo comprobar que el correo electrónico y la propiedad del dominio se tomen en un inquilino no administrado en Microsoft 365
ms.openlocfilehash: 1772ba9929433c87603d4b9d7027419063fd2fca
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627949"
---
# <a name="perform-an-internal-admin-takeover"></a>Realizar un relevo interno del administrador

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 

Si es administrador y desea tomar el control de un inquilino no administrado creado por un registro de usuario de autoservicio, puede hacerlo con una adquisición de administrador interna.

> [!NOTE]
> Una inscripción de autoservicio para cualquier servicio en la nube que use Azure AD agregará el usuario a un directorio de Azure AD no administrado o "instantánea" y creará un inquilino no administrado. Un inquilino no administrado es un directorio sin administrador global. Para determinar si un inquilino está administrado o no administrado, consulte determinar el [tipo de inquilino](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Paso 1: comprobar su dirección de correo electrónico

> [!NOTE]
> Si el autoservicio está habilitado en el espacio empresarial, los usuarios pueden suscribirse a servicios gratuitos, como Power BI, por su cuenta. En estos pasos se da por hecho que una suscripción de usuario de autoservicio ha creado el inquilino no administrado que desea tomar como administrador. En el primer paso, se crea un contexto de usuario en el inquilino no administrado, que usa Power BI para ilustrar la ruta de acceso de adquisición de administración.

1. Para registrarse en Power BI, vaya al sitio de [Power BI](https://powerbi.com) y seleccione **iniciar** > **versión de prueba** gratuita de inicio libre (en compartir con Power Bi Pro Box). 

2. Regístrese con una cuenta de usuario que use el nombre de dominio de su organización ( `powerbiadmin@contoso.com`como). Si su cuenta ya está en uso, inicie sesión con su contraseña actual.

3. Busque en su correo electrónico el **código de verificación** y escriba el código para validar su dirección de correo electrónico.
    
## <a name="step-2-create-a-new-account"></a>Paso 2: crear una cuenta nueva

1. Cuando escriba el código de verificación, se le enviará a una página en la que puede crear una nueva cuenta. 
    
2. Rellene los campos nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, seleccione **iniciar**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Paso 3: comprobar la propiedad del dominio y convertirse en el administrador

1. Se **convierte en el Asistente de administración que** se abrirá. Si el asistente no se inicia, busque el icono **Administrador** y selecciónelo. 

2. Seleccione **sí, quiero ser el administrador**.

3. Para comprobar que es el propietario del dominio que desea asumir, agregue un registro TXT a su registrador de dominios. El asistente le proporcionará el registro TXT para agregar, así como proporcionar un vínculo al sitio web de su registrador y un vínculo a las instrucciones paso a paso.
    
4. Una vez que haya agregado el registro TXT a su sitio de registrador, regrese al asistente y seleccione **Aceptar, he agregado el registro**.
    
> [!NOTE]
> La toma del inquilino de instantánea no afectará a la información o los servicios existentes. Sin embargo, si algún usuario del dominio se ha registrado para obtener servicios que requieren una licencia, se le pedirá que compre licencias para ellos como parte de la toma del rol de administrador. Puede Agregar o quitar licencias una vez que el proceso de configuración de administración haya finalizado. 
  
## <a name="related-articles"></a>Artículos relacionados

YouTube: [3 pasos para realizar una adquisición del administrador de TI para Power BI y Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Adquisición de administradores en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Obtener ayuda con los dominios](../get-help-with-domains/get-help-with-domains.md)

[Uso del registro de autoservicio en su organización](self-service-sign-up.md)
  
[Descripción del rol de administrador del servicio de Power BI](https://docs.microsoft.com/power-bi/service-admin-role)

