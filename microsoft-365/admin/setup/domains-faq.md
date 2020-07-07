---
title: Preguntas más frecuentes de dominios
f1.keywords:
- NOCSH
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Obtenga más información acerca de los dominios buscando respuestas a las preguntas más frecuentes.
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049741"
---
# <a name="domains-faq"></a>Preguntas más frecuentes de dominios

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Este artículo contiene respuestas a las preguntas más frecuentes acerca de los dominios de Microsoft 365.

Si no encuentra una respuesta a su pregunta, infórmenos de ello dejando un comentario y lo agregaremos a la lista.

En este artículo

[¿Qué es la prioridad mx?](#what-is-mx-priority) 
 [¿Cómo puedo validar los registros de SPF para mi dominio?](#how-can-i-validate-spf-records-for-my-domain) 
 [¿Qué es un nombre de dominio?](#what-is-a-domain-name) 
 [¿Qué sucede si mi proveedor de DNS no es compatible con determinados tipos de registros?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
 [¿Cómo se configura o se cambia el dominio predeterminado en Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
 [¿Puedo agregar subdominios personalizados o varios dominios a Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
 [¿Por qué tengo un dominio "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain) 
 [¿Por qué tengo un dominio "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain) 
 [¿Cómo puedo comprobar mi estado para ONG o educación?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>¿Qué es una prioridad de MX?

El correo se entrega al servidor de intercambio de correo con el número de preferencia más bajo (prioridad más alta), por lo que el registro MX que use para el enrutamiento de correo debe tener el número de preferencia más bajo, normalmente 0 o *alta* prioridad. 
  
- Al crear un registro MX, la mayoría de los proveedores de hospedaje DNS requieren que establezca el número de preferencia.
    
- Algunas etiquetas son la *preferencia* de cuadro y alguna de ellas tiene *prioridad* . 
    
- Algunos requieren un número y algunos le piden que seleccione *bajo* , *medio* o *alto* . 
    
- Si solo tiene un registro MX, cualquier valor es correcto para prioridad o preferencia.
    
- Si tiene más de uno, asegúrese de que el registro MX para el enrutamiento de correo tiene una prioridad mayor que la usada para validar que es el propietario del dominio.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>¿Cómo puedo validar los registros de SPF para mi dominio?

Es importante que tenga o cree **un solo registro TXT para SPF**. Si ya tiene un registro de SPF, debe anexar a él los nuevos valores de Microsoft 365, en lugar de crear uno nuevo. Una vez que haya agregado o actualizado el registro de SPF para el correo electrónico de Microsoft, debe asegurarse de que la sintaxis es correcta con una de estas herramientas: 
  
- [Herramientas de prueba de registros de SPF](http://www.kitterman.com/spf/validate.html)
    
- [Surveyor de SPF](https://dmarcian.com/spf-survey/)
    
- [Preparar la interfaz web](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>¿Qué es un nombre de dominio?

Un dominio es un nombre único que aparece después del signo **@** en las direcciones de correo electrónico y después de **www.** en las direcciones web. Normalmente, toma la forma del nombre de la organización y un sufijo de Internet estándar, como *yourbusiness.com* o *StateUniversity.edu.* 
  
Usar un dominio personalizado como "**rob \@ contoso.com**" con Microsoft 365 puede ayudarle a crear credibilidad y un reconocimiento para su marca. 
  
Puede [comprar un dominio en Microsoft 365 y configurarlo automáticamente](../get-help-with-domains/buy-a-domain-name.md), o puede comprar o traer uno que ya es propietario de un registrador de dominios.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>¿Qué sucede si mi proveedor de DNS no es compatible con determinados tipos de registros?

Si administra sus propios registros DNS y su host DNS no admite todos los registros DNS que Microsoft 365 necesita, algunas características de Microsoft 365 no funcionarán. Le recomendamos que transfiera su dominio a un registrador que admita todos los registros DNS necesarios.
  
Proveedores que admiten todos los registros DNS necesarios:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Coloque
    
- MyHosting.com
    
- Name.com
    
- Voz casi gratuita
    
- Nettica
    
- Centro de información de redes (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>¿Cómo se configura o se cambia el dominio predeterminado en Microsoft 365?

Debe tener al menos un dominio personalizado que haya agregado a Microsoft 365 para poder elegir un dominio predeterminado.

::: moniker range="o365-worldwide"

1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, diríjase a la página **configuración** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a>.

::: moniker-end
    
2. En la página **dominios** , seleccione el dominio que desea establecer como predeterminado para las nuevas direcciones de correo electrónico. 
    
3. Seleccione **Establecer como predeterminado**.
    
::: moniker range="o365-worldwide"

No puede cambiar el nombre del dominio inicial *. onmicrosoft.com* . 

::: moniker-end

::: moniker range="o365-germany"

No puede cambiar el nombre del dominio inicial *. onmicrosoft.de* . 

::: moniker-end

::: moniker range="o365-21vianet"

No puede cambiar el nombre del dominio inicial *. Partner.onmschina.cn* . 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>¿Puedo agregar subdominios personalizados o varios dominios a Microsoft 365?

::: moniker range="o365-worldwide"

Sí. Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador. Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.

::: moniker-end

::: moniker range="o365-germany"

Afirma! Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador. Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.

::: moniker-end

::: moniker range="o365-21vianet"

Afirma! Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador. Si permite que 21Vianet administre la configuración DNS con registros NS, no puede agregar subdominios.

::: moniker-end

Normalmente, puede Agregar hasta 900 dominios a su suscripción de Microsoft 365.
  
Por ejemplo, puede Agregar los dominios contoso.com y contosomarketing.com y, a continuación, agregar los subdominios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, etc.
  
Cuando se agrega un subdominio, se comprueba automáticamente según el dominio primario que se está comprobando.
  
Cuando se agregan varios dominios a Microsoft 365, puede hospedar cualquiera de los servicios (como correo electrónico) en cualquiera de los dominios que haya agregado.  *Al cambiar el correo electrónico a Microsoft 365, al actualizar el registro MX de un dominio, todo el correo electrónico enviado a ese dominio empezará a ser de Microsoft 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Si agregó un dominio contoso.com a una suscripción de Microsoft 365, también puede Agregar el subdominio xyz.contoso.com a otra organización 365 de Microsoft. Al agregar el subdominio, se le pedirá que agregue un registro TXT en el proveedor de host DNS.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>¿Por qué tengo un dominio "onmicrosoft.com"?

Microsoft 365 crea un dominio para usted, como *contoso.onmicrosoft.com*, cuando se registra en el servicio. El identificador de usuario que crea al registrarse incluye el dominio, como *Alan@contoso.onmicrosoft.com*. 
  
 **Si quiere que su correo sea similar a *Alan \@ contoso.com*:** [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos que se indican en [Agregar usuarios y dominios a Microsoft 365](add-domain.md) si es el propietario ya. 
  
- **No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.** Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.com, no puede cambiarlo a fabrikam.onmicrosoft.com. Para usar un dominio de onmicrosoft.com diferente, debe iniciar una nueva suscripción con Microsoft 365. 
    
- **No puede cambiar el nombre de la dirección URL del sitio de grupo.** La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.com. Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo. 
    
- **No puede quitar el dominio de Microsoft.** Microsoft 365 necesita mantenerlo bien porque se usa en segundo plano para la suscripción. Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado. 
    
Puede seguir usando el dominio de onmicrosoft.com inicial incluso después de agregar el dominio. Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>¿Por qué tengo un dominio "onmicrosoft.de"?

Microsoft 365 crea un dominio para usted, como *contoso.onmicrosoft.de*, cuando se registra en el servicio. El identificador de usuario que crea al registrarse incluye el dominio, como *Alan@contoso.onmicrosoft.de*. 
  
 **Si quiere que su correo sea similar a *Alan@contoso.de*:** [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos descritos en [Agregar los usuarios y el dominio a Microsoft 365](add-domain.md) si ya es el propietario. 
  
- **No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.** Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.de, no puede cambiarlo a fabrikam.onmicrosoft.de. Para usar un dominio de onmicrosoft.de diferente, debe iniciar una nueva suscripción con Microsoft 365. 
    
- **No puede cambiar el nombre de la dirección URL del sitio de grupo.** La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.de. Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo. 
    
- **No puede quitar el dominio de Microsoft.** Microsoft 365 necesita mantenerlo bien porque se usa en segundo plano para la suscripción. Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado. 
    
Puede seguir usando el dominio de onmicrosoft.de inicial incluso después de agregar el dominio. Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>¿Cómo puedo comprobar mi estado para ONG o educación?

1. Seleccione **configurar** en el [centro de administración](https://docs.microsoft.com/microsoft-365/admin/admin-home) para iniciar el asistente. (Asegúrese de iniciar sesión primero en Microsoft 365). 
    
2. Para convertirse en el administrador de su centro educativo, seleccione la opción **convertirse en Administrador** en Microsoft 365. 
    
3. Se le pedirá que agregue un registro DNS TXT en el sitio web del host DNS de su dominio. ¿Por qué? Debido a que inicia sesión en el host DNS y agrega un registro para su dominio, usted prueba a Microsoft 365 que es el propietario del nombre de dominio.
    
4. Después de agregar el registro, volverá al portal de 365 de Microsoft y confirmará que lo ha agregado, por lo que Microsoft 365 puede comprobar.
    
¿Tiene una ONG y desea obtener Microsoft 365? Asegúrese de [que su organización sea cualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) y, a continuación, Regístrese para obtener el servicio. 
  
¿Quiere saber más sobre cómo convertirse en el administrador de su centro educativo? [Obtenga información sobre ti](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).