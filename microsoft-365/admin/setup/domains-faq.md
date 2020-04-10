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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Obtenga más información acerca de los dominios en Office 365 buscando respuestas a sus preguntas en preguntas más frecuentes.
ms.custom: okr_smb
ms.openlocfilehash: 5579cacaa789ca91d68616ffb89e37586f6a062f
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212202"
---
# <a name="domains-faq"></a>Preguntas más frecuentes de dominios

Este artículo contiene respuestas a las preguntas más frecuentes acerca de los dominios en Office 365.

Si no encuentra una respuesta a su pregunta, infórmenos de ello dejando un comentario y lo agregaremos a la lista.
    
## <a name="what-is-mx-priority"></a>¿Qué es una prioridad de MX?

El correo se entrega al servidor de intercambio de correo con el número de preferencia más bajo (prioridad más alta), por lo que el registro MX que use para el enrutamiento de correo debe tener el número de preferencia más bajo, normalmente 0 o *alta* prioridad. 
  
- Al crear un registro MX, la mayoría de los proveedores de hospedaje DNS requieren que establezca el número de preferencia.
    
- Algunas etiquetas son la *preferencia* de cuadro y alguna de ellas tiene *prioridad* . 
    
- Algunos requieren un número y algunos le piden que seleccione *bajo* , *medio* o *alto* . 
    
- Si solo tiene un registro MX, cualquier valor es correcto para prioridad o preferencia.
    
- Si tiene más de uno, asegúrese de que el registro MX para el enrutamiento de correo tiene una prioridad mayor que la usada para validar que es el propietario del dominio.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>¿Cómo puedo validar los registros de SPF para mi dominio?

Es importante que tenga o cree **un solo registro TXT para SPF**. Si ya tiene un registro de SPF, debe anexar a él los nuevos valores de Office 365, en lugar de crear uno nuevo. Una vez que haya agregado o actualizado el registro de SPF para el correo electrónico de Office 365, debe asegurarse de que la sintaxis es correcta con una de estas herramientas: 
  
- [Herramientas de prueba de registros de SPF](http://www.kitterman.com/spf/validate.html)
    
- [Surveyor de SPF](https://dmarcian.com/spf-survey/)
    
- [Preparar la interfaz web](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>¿Cómo administra Office 365 los registros DNS?

Hay dos opciones para la administración de DNS con Office 365:
  
1. Puede cambiar los registros del servidor de nombres (NS) y, a continuación, Office 365 se ocupa de todos los registros específicos del servicio, como la configuración de su registro MX para el correo electrónico. **Recomenda**
    
2. Agregue los registros DNS para el correo electrónico y otros servicios de Office 365 en su host DNS. **(Solo expertos)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>Office 365 crea y hospeda los registros DNS 
**Ventajas** 
- No tiene que preocuparse por cometer errores en los valores que escribió para los registros DNS para los servicios de Office 365.  
- Tiene más flexibilidad en la elección del registrador de dominios y el host DNS. 
- Cualquier proveedor que le permita cambiar los registros del servidor de nombres funcionará, incluso si el proveedor no admite todos los tipos de registros necesarios.   
- Cuando Office 365 agrega nuevos registros DNS, no es necesario realizar actualizaciones.  

#### <a name="disadvantages"></a>Desventajas 
- No puede cambiar los registros DNS para hospedar correo electrónico fuera de Office 365. 
- Si ya usa un sitio web público con su dominio para su dirección, como www.fourthcoffee.com, debe redirigir a los usuarios a esa dirección desde Office 365. 
- La configuración de la redirección requiere una dirección IP estática, que no siempre está disponible fácilmente para los sitios web públicos. -Si su registrador de dominios actual no le permite cambiar los registros del servidor de nombres de su dominio, tiene que cambiar a otro registrador para usar esta opción de administración de DNS.  

 ### <a name="you-manage-the-dns-records-yourself"></a>Los registros DNS se administran personalmente 
 #### <a name="advantages"></a>Ventajas
- Puede controlar los registros DNS para los servicios de Office 365.   
- Si tiene un sitio web público con su dominio para su dirección, como www.fourthcoffee.com, no tiene que preocuparse por usar el redireccionamiento para asegurarse de que los usuarios aún puedan acceder a su sitio web después de configurar su dominio en Office 365.    
- Tiene la flexibilidad para hospedar correo electrónico en otro lugar, como con un servidor de Exchange local.  
 
#### <a name="disadvantages"></a>Desventajas
Debe configurar los registros DNS para los servicios de Office 365 personalmente (a menos que tenga un dominio de GoDaddy). 
-  Si su host DNS actual no admite todos los tipos de registro necesarios para Office 365, algunas características de Office 365 no estarán disponibles y es posible que deba cambiar a un host DNS diferente. 
- Cuando Office 365 cambia los requisitos para los registros DNS o agrega nuevos servicios, debe realizar las actualizaciones personalmente en el host DNS. 
   
## <a name="what-is-a-domain-name"></a>¿Qué es un nombre de dominio?


Un dominio es un nombre único que aparece después del signo **@** en las direcciones de correo electrónico y después de **www.** en las direcciones web. Normalmente, toma la forma del nombre de la organización y un sufijo de Internet estándar, como *yourbusiness.com* o *StateUniversity.edu.* 
  
Usar un dominio personalizado como "**rob\@contoso.com**" con Office 365 puede ayudarle a crear credibilidad y un reconocimiento para su marca. 
  
Puede [comprar un dominio en Office 365 y configurarlo automáticamente](../get-help-with-domains/buy-a-domain-name.md), o puede comprar o traer uno que ya es propietario de un registrador de dominios.
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>¿Puedo transferir un dominio que he comprado de Microsoft a otro proveedor?

Sí, pero no puede transferir un dominio de Office 365 a otro registrador hasta 60 días después de que lo haya comprado con Office 365.

Tenga en cuenta que una consulta *Whois* mostrará un registrador de dominios de Office 365 comprado como dominios silvestres de Westn LLC. Sin embargo, solo debe ponerse en contacto con Office 365 en relación con el dominio adquirido de Office 365.
  
Siga los pasos siguientes para obtener el código en Office 365 y, a continuación, vaya al sitio web del otro registrador de dominios para configurar la transferencia de su nombre de dominio a dicho registrador.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
    Si está usando Office 365 Germany, vaya a esta página de <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a> . 
    
    Si está usando Office 365 operado por 21Vianet, vaya a esta página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a> .
    
2. En la página **dominios** , seleccione el dominio de Office 365 que desea transferir a otro registrador de dominios y, a continuación, seleccione **transferencia** > de dominio**Habilitar transferencia de dominio**.
       
4. Siga los pasos para preparar la transferencia del dominio.
    
5. Una vez que obtenga el código, vaya al sitio web del registrador de dominios donde desea administrar su nombre de dominio hacia delante y siga sus instrucciones para transferir un dominio (busque ayuda en su sitio web).
    
6. Si necesita volver a ver el código, en la página **configuración del dominio** en Office 365, seleccione **Ver código de autorización para la transferencia del dominio**.
    
7. Una vez completada la transferencia, renovará su dominio en el nuevo registrador de dominios.
    
8. Para finalizar el proceso, vuelva a la página **dominios** del centro de administración y seleccione **transferencia de dominio completa**. 

*Nota: tenga en cuenta que los dominios comprados de Office 365 no son válidos para los cambios en el servidor de nombres o la transferencia del dominio entre los inquilinos de Office 365.  Si alguno de ellos es necesario, el registro de dominio deberá transferirse a otro registrador.*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>¿Cómo puedo cambiar el modo en que mis registros DNS se administran en Office 365?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>Cambiar la administración de DNS a un host DNS fuera de Office 365
   
1. Inicie sesión en el registrador de dominios de su dominio.
    
2. Busque el área en el sitio web del registrador en la que se actualizan los registros del servidor de nombres y actualice los servidores de nombres para que apunten al host DNS de su dominio. (El host DNS suele ser el registrador de dominios).
    
3. Siga un vínculo para ir al Asistente para la configuración de dominios:
    
4. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
    Si está usando Office 365 Germany, vaya a esta página de <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a> . 
    
    Si está usando Office 365 operado por 21Vianet, vaya a esta página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a> .
    
5. En la página **dominios** , seleccione el dominio que quiere cambiar y seleccione **Administración de DNS**.
    
6. En el Asistente para la configuración de dominios, en la página **configurar los servicios en línea** , seleccione **Administraré mis propios registros DNS**y, a continuación, seleccione **siguiente**.
    
7. Agregue los registros DNS sugeridos por el asistente en la página **Actualizar configuración DNS** al sitio web del registrador. 
    
8. Una vez que haya agregado los registros, vuelva a Office 365 y seleccione **comprobar**.
    

### <a name="change-dns-management-to-office-365"></a>Cambiar la administración de DNS a Office 365
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
    Si está usando Office 365 Germany, vaya a esta página de <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a> . 
    
    Si está usando Office 365 operado por 21Vianet, vaya a esta página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a> .
    
2. En la página **dominios** , seleccione el dominio que quiere cambiar y seleccione **Administración de DNS**.
    
3. En el Asistente para la configuración de dominios, en la página **configurar los servicios en línea** , seleccione **configurar mis servicios en línea para mí. (Recomendado)** y, a continuación, seleccione **siguiente**.
    
4. Si aún no ha comprobado el dominio, siga los pasos para hacerlo primero.
    
5. En la página **Actualizar configuración DNS** , se enumeran los servidores de nombres para Office 365. Vaya al registrador de dominios de su dominio y actualice los servidores de nombres a los servidores de nombres de Office 365. 
    
4. Una vez que haya actualizado los servidores de nombres, **espere al menos una hora**. A continuación, en el Asistente de Office 365, seleccione **comprobar**.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>¿Qué sucede si mi proveedor de DNS no es compatible con determinados tipos de registros?

Si administra sus propios registros DNS y su host DNS no admite todos los registros DNS que necesita Office 365, algunas características de Office 365 no funcionarán. Le recomendamos que transfiera su dominio a un registrador que admita todos los registros DNS necesarios.
  
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
    
 **Si no se admiten los registros SRV**, no estarán disponibles las siguientes características de Office 365: 
  
- Integración de presencia y mensajería instantánea de Skype empresarial online con Outlook Web App
    
- Comunicación externa (Federación) con usuarios de Skype empresarial online en otras organizaciones.
    
- Conectividad pública a Internet (PIC) con usuarios de Skype empresarial online que han iniciado sesión con una cuenta de Microsoft (anteriormente conocida como Windows Live ID).
    
 **Si no se admiten varios registros CNAME,** tiene que elegir entre las siguientes características de Skype empresarial online: 
  
- Los clientes de escritorio de correo electrónico y los clientes móviles pueden usar la detección automática para buscar automáticamente el servicio de Exchange Online para que los usuarios puedan iniciar sesión sin tener que escribir el nombre de un servidor.
    
- Los clientes de escritorio de Skype empresarial online pueden usar la detección automática para buscar automáticamente el servicio de Skype empresarial online para que los usuarios puedan iniciar sesión sin tener que escribir el nombre de un servidor.
    
- Los clientes móviles de Skype empresarial online pueden usar la detección automática para buscar automáticamente el servicio de Skype empresarial online para que los usuarios puedan iniciar sesión sin tener que escribir el nombre de un servidor.
    
 **Si no se admiten los registros SPF/txt**, es posible que otras personas puedan usar su dominio para enviar correo no deseado u otro correo electrónico malintencionado. Los registros de SPF funcionan mediante la identificación de los servidores autorizados para enviar correo electrónico desde su dominio. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>¿Cómo se configura o se cambia el dominio predeterminado en Office 365?

Debe tener al menos un dominio personalizado que haya agregado a Office 365 para poder elegir un dominio predeterminado.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
    Si está usando Office 365 Germany, vaya a esta página de <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">dominios</a> . 
    
    Si está usando Office 365 operado por 21Vianet, vaya a esta página de <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">dominios</a> .
    
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

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>¿Puedo agregar subdominios personalizados o varios dominios a Office 365?

::: moniker range="o365-worldwide"

Afirma! Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador. Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.

::: moniker-end

::: moniker range="o365-germany"

Afirma! Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador. Si va a permitir que Microsoft administre la configuración de DNS con registros NS o si compró el dominio de Microsoft, no puede agregar subdominios.

::: moniker-end

::: moniker range="o365-21vianet"

Afirma! Para agregar subdominios, debe administrar su propia configuración DNS en el sitio web del registrador. Si permite que 21Vianet administre la configuración DNS con registros NS, no puede agregar subdominios.

::: moniker-end

Normalmente, puede Agregar hasta 900 dominios a su suscripción de Office 365.
  
Por ejemplo, puede Agregar los dominios contoso.com y contosomarketing.com y, a continuación, agregar los subdominios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, etc.
  
Cuando se agrega un subdominio, se comprueba automáticamente según el dominio primario que se está comprobando.
  
Cuando se agregan varios dominios a Office 365, puede hospedar cualquiera de los servicios (como correo electrónico) en cualquiera de los dominios que haya agregado.  *Al cambiar el correo electrónico a Office 365, al actualizar el registro MX de un dominio, todo el correo electrónico enviado a ese dominio empezará a llegar a Office 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Si ya ha agregado un dominio contoso.com a un inquilino de Office 365, también puede Agregar el subdominio xyz.contoso.com a otro inquilino de Office 365. Al agregar el subdominio, se le pedirá que agregue un registro TXT en el proveedor de host DNS.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>¿Por qué tengo un dominio "onmicrosoft.com"?

Office 365 crea un dominio para usted, como _contoso.onmicrosoft.com_, cuando se registra en el servicio. El identificador de usuario que crea al registrarse incluye el dominio, como _alan\@contoso.onmicrosoft.com_. 
  
 __Si quiere que su correo sea similar a _Alan\@contoso.com_:__ [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos que se indican en [Agregar usuarios y dominios a Office 365](add-domain.md) si es el propietario ya. 
  
- **No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.** Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.com, no puede cambiarlo a fabrikam.onmicrosoft.com. Para usar un dominio onmicrosoft.com diferente, debe iniciar una nueva suscripción con Office 365. 
    
- **No puede cambiar el nombre de la dirección URL del sitio de grupo.** La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.com. Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo. 
    
- **No puede quitar el dominio de Microsoft.** Office 365 debe mantenerlo ahí porque se usa en segundo plano para la suscripción. Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado. 
    
Puede seguir usando el dominio de onmicrosoft.com inicial incluso después de agregar el dominio. Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.
  
::: moniker-end

::: moniker range="o365-germany"

## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>¿Por qué tengo un dominio "onmicrosoft.de"?

Office 365 crea un dominio para usted, como *contoso.onmicrosoft.de*, cuando se registra en el servicio. El identificador de usuario que crea al registrarse incluye el dominio, como "alan@contoso.onmicrosoft.de". 
  
Si desea que el correo electrónico tenga un aspecto similar a "alan@contoso.de": [compre el dominio](../get-help-with-domains/buy-a-domain-name.md) o simplemente siga los pasos descritos en [Agregar usuarios y dominios a Office 365](add-domain.md) si es el propietario ya 
  
- **No puede cambiar el nombre del dominio de mi Microsoft después de suscribirse.** Por ejemplo, si el dominio inicial elegido era fourthcoffee.onmicrosoft.de, no puede cambiarlo a fabrikam.onmicrosoft.de. Para usar un dominio onmicrosoft.de diferente, debe iniciar una nueva suscripción con Office 365. 
    
- **No puede cambiar el nombre de la dirección URL del sitio de grupo.** La dirección URL del sitio de grupo se basa en el nombre de dominio onmicrosoft.de. Por desgracia, debido a la forma en que funciona la arquitectura de SharePoint Online, no puede cambiar el nombre del sitio de grupo. 
    
- **No puede quitar el dominio de Microsoft.** Office 365 debe mantenerlo ahí porque se usa en segundo plano para la suscripción. Pero no es necesario usar el dominio usted mismo una vez que haya agregado un dominio personalizado. 
    
Puede seguir usando el dominio de onmicrosoft.de inicial incluso después de agregar el dominio. Sigue funcionando para el correo electrónico y otros servicios, por lo que es su elección.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>¿Cómo puedo comprobar mi estado para ONG o educación?

1. Seleccione **configurar** en el [centro de administración](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791.aspx) para iniciar el asistente. (Asegúrese de iniciar sesión en Office 365 en primer lugar). 
    
2. Para convertirse en el administrador de su centro educativo, seleccione la opción **convertirse en Administrador** en Office 365. 
    
3. Se le pedirá que agregue un registro DNS TXT en el sitio web del host DNS de su dominio. ¿Por qué? Debido a que iniciando sesión en el host DNS y agrega un registro para su dominio, usted prueba a Office 365 que es el propietario del nombre de dominio.
    
4. Después de agregar el registro, volverá al portal de Office 365 y confirmará que lo ha agregado, por lo que Office 365 puede comprobarlo.
    
¿Tiene una ONG y desea obtener Office 365? Asegúrese de [que su organización sea cualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) y, a continuación, Regístrese para obtener el servicio. 
  
¿Quiere saber más sobre cómo convertirse en el administrador de su centro educativo? [Obtenga información sobre ti](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>¿Puedo realizar una prueba de Office 365 con unas pocas direcciones de correo electrónico de mi dominio personalizado?

Puede, pero hay limitaciones:
  
- Su proveedor de correo electrónico actual debe proporcionar el reenvío de correo electrónico.
    
- Debe administrar los registros DNS relacionados con Office 365 en su proveedor de host DNS, en lugar de que Office 365 administre estos registros. Para obtener más información, consulte Agregar un dominio a Office 365 cuando quiera administrar sus propios registros DNS.
    
- Algunas características de Office 365 no estarán disponibles:
- Los usuarios no podrán ver la información de disponibilidad de los usuarios que están en el otro proveedor de correo electrónico.
- Los administradores no podrán administrar las cuentas de todos los usuarios desde un solo punto.
- Es posible que los usuarios no puedan usar el filtrado de correo no deseado de Office 365

### <a name="how-to-set-up-an-office-365-pilot"></a>Cómo configurar un piloto de Office 365
    
1. Inicie sesión en el centro de administración de Microsoft 365
    
    1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
        
    2. Vaya a **Settings** \> **dominios**de configuración. 
    
2. Comprobar que es el propietario del dominio que desea usar
    
    1. En la página **dominios** , seleccione **Agregar dominio**. 
        
    2. En el panel, escriba el dominio, en este ejemplo cohowinery.com y, a continuación, seleccione **siguiente**. 
        
    3. En la página **comprobar** dominio, siga las instrucciones paso a paso. 
        
    4. En la lista desplegable, seleccione su proveedor de host DNS y siga las instrucciones para mostrar que es el propietario del dominio.
        
    5. Seleccione **comprobar**. Tarda entre unos minutos y 72 horas para que los cambios en el DNS surtan efecto. 
        
    6. Cuando la comprobación se realice correctamente, se le pedirá que modifique los registros DNS.
    
3. Marcar el dominio como compartido en Exchange Online
    
    1. Vaya al **centro de administración de Exchange** (EAC). 
        
    2. En la sección **flujo de correo** , seleccione **dominios aceptados**. 
        
    3. Haga doble clic en el dominio que desee modificar.
        
    4. En la ventana que se abre, seleccione **retransmisión interna**. 
        
    5. Seleccione **Guardar**. Esta configuración puede tardar unos minutos en surtir efecto. 
    
4. Opcionalmente, desbloquear el servidor de correo electrónico existente
    
    1. Office 365 usa Exchange Online Protection (EOP) para la protección contra correo no deseado. Si EOP detecta un gran volumen de correo no deseado que ha reenviado su servidor de correo actual, puede bloquearlo, lo que impediría el reenvío en funcionamiento. Si está seguro de que la protección contra correo no deseado de su proveedor de correo electrónico es la que usa, puede usar la lista blanca del servidor en Office 365. Sin embargo, esto también permitirá que el correo no deseado que llegue a través del servidor original pase a los buzones de Office 365 y no podrá evaluar cómo Office 365 impide el correo no deseado.
    
    2. Vaya al centro de administración de Exchange (EAC).
        
    3. En EAC, seleccione **protección**y, a continuación, seleccione **filtro de conexión**. 
        
    4. En la lista de direcciones IP **permitidas**, seleccione **+** y agregue la dirección IP del servidor de correo que puede obtener de su proveedor de correo electrónico actual. 
    
5. Crear cuentas de usuario y establecer la dirección principal (responder a)
    
    1. Vaya al Centro de administración de Microsoft 365.
        
    2. En la barra de navegación izquierda, **Seleccione** \> usuarios **activos**. 
        
    3. Cree las cuentas de usuario.
        
    4. Seleccione **+ (nuevo)** para cada cuenta y rellene la información necesaria. 
        
    5. Para que el correo electrónico del usuario sea el mismo que el que está actualmente, el campo **nombre de usuario** debe ser exactamente igual a la dirección de correo electrónico existente del usuario. 
        
    6. Junto a nombre de usuario, seleccione su nombre de dominio personalizado en la lista desplegable.
        
    7. Seleccione **crear** \> **cierre**. 
        
6. Actualizar registros DNS en su proveedor de host DNS
    
    1. Inicie sesión en el sitio web de su proveedor de host DNS y siga los [pasos de crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). **Realice las siguientes excepciones:**
    
        1. No cree un nuevo registro MX ni cambie el registro MX existente.
            
        2. Si ya tiene un registro de marco de directivas de remitente (SPF) para su proveedor de correo electrónico anterior, en lugar de crear un nuevo registro de SPF (TXT) para Exchange Online, solo tiene que agregar "include include SPF. Protection. Outlook. com" al registro TXT actual. Por ejemplo, "v = spf1 mx include:adatum. com include include SPF. Protection. Outlook. com ~ All".
            
        3. Si aún no tiene un registro de SPF, modifique el que se recomienda en Office 365 para incluir el dominio de su proveedor de correo electrónico actual, además de spf.protection.outlook.com. Esto autoriza los mensajes salientes desde ambos sistemas de correo electrónico.
            
7. Configurar el reenvío de correo electrónico en su proveedor actual
    
    1. En su proveedor de correo electrónico actual, configure el reenvío de las cuentas de correo electrónico de los usuarios a su dominio onmicrosoft.com:
        
    2. El buzón del usuario A debe reenviar a usera@yourcompany.onmicrosoft.com
        
    3. El buzón del usuario B debe reenviar a userb@yourcompany.onmicrosoft.com
        
    4. Cuando haya completado este paso:
        
    5. Todo el correo enviado a usera@yourcompany.com y userb@yourcompany.com estará disponible en Office 365.
    
    6. Notas:
        
        - Póngase en contacto con su proveedor de correo electrónico actual para conocer los pasos exactos para configurar el reenvío.
            
        - No es necesario que conserve una copia de los mensajes en el proveedor de correo electrónico actual.
            
        - La mayoría de los proveedores reenvía correo electrónico que deja intacta la dirección de respuesta del remitente, de modo que las respuestas se envían al remitente original.
    
8. Prueba del flujo de correo
    
    1. Inicie sesión en Outlook Web App con las credenciales del usuario A.
        
    2. Realice las siguientes pruebas:
        
    3. Pruebe el correo electrónico de Office 365 local. Por ejemplo, envíe un correo electrónico al usuario B. Este correo electrónico debe entregarse inmediatamente. En este escenario, el mensaje no se redirigirá al buzón del usuario B en el servidor original, ya que Office 365 Ve el buzón como local.
        
    4. Pruebe el correo electrónico para alguien que se encuentra en el otro sistema de correo electrónico. Por ejemplo, envíe un correo electrónico al usuario C. Este correo electrónico debe entregarse al buzón del usuario C en su servidor de correo original.
        
    5. Desde una cuenta externa o de la cuenta de correo electrónico de un empleado en el otro sistema de correo electrónico, compruebe que el reenvío está configurado correctamente en el otro sistema de correo electrónico. Por ejemplo, en la cuenta de servidor original del usuario C o en una cuenta de hotmail, envíe al usuario un correo electrónico y compruebe que llegue al buzón de Office 365 del usuario A.
        
9. Mover el contenido del buzón
    
    1. Como solo hay dos usuarios que mover, y como el usuario A y el usuario B ya usan Outlook, el correo electrónico se puede mover abriendo el antiguo. PST en el nuevo perfil de Outlook y copiar los mensajes, los elementos del calendario, los contactos, etc. como se muestra en importar elementos de Outlook desde un archivo de datos de Outlook (. pst). Una vez organizadas en las ubicaciones adecuadas en el buzón de Office 365, se puede tener acceso a los elementos desde cualquier dispositivo en cualquier lugar.
        
    2. Cuando hay más buzones de correo implicados o si los empleados todavía no usan Outlook, puede usar las herramientas de migración disponibles en el centro de administración de Exchange. Para empezar, vaya al centro de administración de Exchange y siga las instrucciones que se indican en migrar correo electrónico desde un servidor IMAP a buzones de Exchange Online.
    
