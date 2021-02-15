---
title: Realizar una toma de posesión de un administrador interno
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
ms.openlocfilehash: 28359908576260218459d13b8c1c1b662b9a2c8f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658068"
---
# <a name="perform-an-internal-admin-takeover"></a>Realizar una toma de posesión de un administrador interno

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 

Si es un administrador y quiere asumir un inquilino no administrado creado por un registro de usuario de autoservicio, puede hacerlo con una toma de posesión de administrador interno.

> [!NOTE]
> Un registro de autoservicio para cualquier servicio en la nube que use Azure AD agregará al usuario a un directorio de Azure AD no administrado o "sombreado" y creará un inquilino no administrado. Un inquilino no administrado es un directorio sin un administrador global. Para determinar si un inquilino está administrado o no administrado, consulte [Determinación del tipo de inquilino.](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type) 
  
## <a name="step-1-verify-your-email-address"></a>Paso 1: Comprobar la dirección de correo electrónico

> [!NOTE]
> Si el autoservicio está habilitado en el espacio empresarial, los usuarios pueden suscribirse a servicios gratuitos, como Power BI, por sí mismos. En estos pasos se supone que una suscripción de usuario de autoservicio ha creado el inquilino no administrado que desea asumir como administrador. En el primer paso se crea un contexto de usuario en el inquilino no administrado, con Power BI para ilustrar la ruta de acceso de toma de control del administrador.

1. Para registrarse en Power BI, vaya al sitio de [Power BI](https://powerbi.com) y seleccione Iniciar prueba gratuita de Inicio gratuito (en el cuadro Compartir con Power  >   BI Pro). 

2. Registrarse con una cuenta de usuario que use el nombre de dominio de su organización (como `powerbiadmin@contoso.com` ). Si su cuenta ya está en uso, inicie sesión con su contraseña actual.

3. Compruebe el código de **verificación** en el correo electrónico y escriba el código para validar la dirección de correo electrónico.
    
## <a name="step-2-create-a-new-account"></a>Paso 2: Crear una nueva cuenta

1. Cuando escriba el código de verificación, se le mostrará a una página donde puede crear una nueva cuenta. 
    
2. Rellene los campos de nombre de usuario y contraseña con la cuenta que desea usar y, a continuación, seleccione **Iniciar**. 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>Paso 3: Comprobar la propiedad del dominio y convertirse en el administrador

1. Se **abrirá el Asistente** para convertirse en administrador. Si el asistente no se inicia, busca **el** icono Administrador y selecciónelo. 

2. Seleccione **Sí, quiero ser el administrador.**

3. Compruebe que es el propietario del dominio que desea asumir agregando un registro TXT al registrador de dominios. El asistente le proporcionará el registro TXT para agregar, así como un vínculo al sitio web de su registrador y un vínculo a instrucciones paso a paso.
    
4. Una vez que haya agregado el registro TXT al sitio de registrador, vuelva al asistente y seleccione Bien, he **agregado el registro.**
    
> [!NOTE]
> La toma de control del inquilino de instantánea no afectará a la información o los servicios existentes. Sin embargo, si algún usuario del dominio se ha suscrito a los servicios que requieren una licencia, se le pedirá que compre licencias para ellos como parte de la toma del rol de administrador. Puede comprar o quitar licencias una vez finalizado el proceso de configuración del administrador.
  
## <a name="related-articles"></a>Artículos relacionados

YouTube: 3 pasos para realizar una toma de posesión de administrador [de TI para Power BI y Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Toma de posesión de administradores en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[Uso del registro de autoservicio en su organización](self-service-sign-up.md)
  
[Descripción del rol de administrador del servicio Power BI](https://docs.microsoft.com/power-bi/service-admin-role)

