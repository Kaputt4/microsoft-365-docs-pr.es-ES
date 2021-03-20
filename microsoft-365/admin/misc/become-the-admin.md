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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Obtenga información sobre cómo comprobar la propiedad del dominio y el correo electrónico para asumir un inquilino no administrado en Microsoft 365
ms.openlocfilehash: 72278fd0e373848a79f9823e186b19bc1cb47770
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914851"
---
# <a name="perform-an-internal-admin-takeover"></a>Realizar una toma de administración interna

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 

Si es un administrador y desea asumir un inquilino no administrado creado por un registro de usuario de autoservicio, puede hacerlo con una toma de posesión de un administrador interno.

> [!NOTE]
> Un registro de autoservicio para cualquier servicio en la nube que use Azure AD agregará al usuario a un directorio de Azure AD no administrado o "de sombra" y creará un inquilino no administrado. Un inquilino no administrado es un directorio sin un administrador global. Para determinar si un inquilino está administrado o no administrado, consulte [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type). 
  
## <a name="step-1-verify-your-email-address"></a>Paso 1: Comprobar la dirección de correo electrónico

> [!NOTE]
> Si el autoservicio está habilitado en el inquilino, los usuarios pueden suscribirse a servicios gratuitos, como Power BI, por su cuenta. Estos pasos suponen que una suscripción de usuario de autoservicio ha creado el inquilino no administrado que desea asumir como administrador. En el primer paso se crea un contexto de usuario en el inquilino no administrado, con Power BI para ilustrar la ruta de acceso de adquisición de administrador.

1. Para registrarse en Power BI, vaya al sitio de [Power BI](https://powerbi.com) y seleccione **Iniciar** prueba gratuita de inicio gratuito (en Cuadro Compartir con Power  >   BI Pro). 

2. Registrarse con una cuenta de usuario que use el nombre de dominio de su organización (como `powerbiadmin@contoso.com` ). Si tu cuenta ya está en uso, inicia sesión con la contraseña actual.

3. Compruebe el código de verificación **del** correo electrónico y escriba el código para validar la dirección de correo electrónico.
    
## <a name="step-2-create-a-new-account"></a>Paso 2: Crear una nueva cuenta

1. Cuando escriba el código de verificación, se le mostrará a una página donde puede crear una nueva cuenta. 
    
2. Rellene los campos de nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, **seleccione Iniciar**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Paso 3: Comprobar la propiedad del dominio y convertirse en administrador

1. Se **abrirá el Asistente para** convertirse en administrador. Si el asistente no se inicia, busque el icono **Administrador** y selecciónelo. 

2. Seleccione **Sí, quiero ser el administrador**.

3. Compruebe que es el propietario del dominio que desea asumir agregando un registro TXT al registrador de dominios. El asistente le proporcionará el registro TXT que desea agregar, así como un vínculo al sitio web del registrador y un vínculo a instrucciones paso a paso.
    
4. Una vez que haya agregado el registro TXT al sitio de registrador, vuelva al asistente y seleccione **Correcto,** he agregado el registro .
    
> [!NOTE]
> La toma del espacio empresarial de instantáneas no afectará a ninguna información o servicios existentes. Sin embargo, si algún usuario del dominio se ha registrado en los servicios que requieren una licencia, se le pedirá que compre licencias para ellos como parte de la toma del rol de administrador. Puede comprar o quitar licencias una vez finalizado el proceso de configuración de administración.
  
## <a name="related-articles"></a>Artículos relacionados

YouTube: 3 pasos para realizar una toma de administración de [TI para Power BI y Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Toma de posesión de administradores en Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Uso del registro de autoservicio en su organización](self-service-sign-up.md)
  
[Descripción del rol de administrador de servicio de Power BI](/power-bi/service-admin-role)