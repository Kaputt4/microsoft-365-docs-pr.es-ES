---
title: Crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: Aprenda a verificar su dominio y a crear registros DNS en cualquier proveedor de hospedaje de DNS para Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 2d3c726f70ffb4588f7ae2fc8b53bf8f0c60e258
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255160"
---
# <a name="create-dns-records-at-any-dns-hosting-provider-for-office-365"></a>Crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Consulte nuestra lista de [instrucciones específicas del host](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) para buscar su host y siga los pasos para agregar todos los registros que necesite. 
  
Si no conoce el proveedor de host DNS o el registrador de dominios de su dominio, vea [Encuentre su registrador de dominios o proveedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
  
Si va a configurar los registros usted mismo, estos son los registros que deberá agregar. Tenga en cuenta que el registro de verificación y el registro MX son únicos para su dominio. Para configurarlos, tendrá que obtener un "token" específico para su dominio. En los pasos siguientes se explica cómo realizar esta acción.
  
> [!IMPORTANT]
> El nombre exacto de los cuadros o  *campos*  en los que escribe o pega información para crear cada tipo de registro DNS es distinto en cada host DNS. Su host DNS podría ofrecer ayuda en su sitio web para que pueda hacer corresponder las instrucciones que ofrecemos aquí con los campos de su sitio web. No olvide comprobar si existen instrucciones paso a paso para su host de DNS en [Crear registros DNS para Office 365](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx)> Algunos hosts DNS no le permiten crear todos los tipos de registros necesarios, lo que causa [limitaciones de servicio](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) en Office 365. Si su proveedor no admite registros SRV, TXT o CNAME, le recomendamos que [transfiera su dominio](../get-help-with-domains/buy-a-domain-name.md) a un proveedor que admita todos los tipos de registros necesarios. Para realizar una instalación de Office 365 rápida y automatizada, le recomendamos que transfiera su dominio a GoDaddy. 
  
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos cuantos minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>Agregar un registro TXT o MX para su verificación
<a name="BKMK_verify"> </a>

> [!NOTE]
> Sólo debe crear uno de los dos registros. TXT es el tipo de registro preferido, pero algunos proveedores de host DNS no lo admiten. De ser así, puede crear un registro MX. 
  
Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
 **Busque el área del sitio web de su proveedor de host DNS en la que puede crear un registro.**
  
1. Inicie sesión en el sitio web del proveedor de host DNS.
    
2. Elija su dominio.
    
3. Busque la página donde puede modificar los registros DNS para su dominio.
    
 **Cree el registro.**
  
1. En función de si se está creando un registro TXT o un registro MX, siga uno de los procedimientos siguientes:
    
  - **Si crea un registro TXT, utilice estos valores:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro**|**Alias** o **Nombre de host**|**Valor**|**TTL**|
|TXT|Realice una de las siguientes acciones: escriba **@**, deje el campo vacío o escriba el nombre de dominio.    <br/> **Nota:** Los diferentes anfitriones de DNS tienen diferentes requerimientos para este campo. |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.  <br/>        [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc.  |
   
  - **Si crea un registro MX, utilice estos valores:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Tipo de registro**|**Alias** o **Nombre de host**|**Valor**|**Prioridad**|**TTL**|
|MX|Escriba **@** o el nombre del dominio. |MS=ms *XXXXXXXX* <br/> **Nota:** esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.    <br/>       [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Para**Prioridad**, para evitar conflictos con el registro MX usado para el flujo de correo, use una prioridad más baja que la prioridad de cualquier registro MX existente. <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |Configure este valor como **1 hora** o el equivalente en minutos ( **60** ), segundos ( **3600** ), etc. |
   
2. Guarde el registro.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.
  
Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página**configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
2. En la página **dominios**, seleccione el dominio que está verificando. 
  
3. En la página de **configuración**, seleccione ** Iniciar configuración**.
       
4. En la página**verificar dominio**, seleccione **verificar**.   
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-mx-record-to-route-email"></a>Agregar un registro MX para enrutar correo
<a name="BKMK_add_MX"> </a>

Agregue un registro MX para que el correo electrónico del dominio vaya a Office 365.  *Cuando actualice el registro MX de su dominio, todo el correo electrónico nuevo de cualquiera que use tu dominio pasará a Office 365*. Cualquier correo electrónico que ya tengas permanecerá en tu actual servidor de correo electrónico, a menos que decidas [migrar el correo electrónico y los contactos de Office 365](../setup/migrate-email-and-contacts-admin.md) a Office 365. 
  
  
 **Tarea**
  
Buscar la página donde puede crear los registros para su dominio.
  
1. Inicie sesión en la página web de su host DNS.
    
2. Elija su dominio.
    
3. Busque la página donde puede modificar los registros DNS para su dominio.
    
::: moniker range="o365-worldwide"

El registro MX que agregará incluye un valor ( **Dirección de destino**) que tiene un aspecto como el siguiente: \<MX token\>.mail.protection.outlook.com, donde \<MX token\> es un valor como MSxxxxxxx. 

::: moniker-end

::: moniker range="o365-germany"

El registro MX que agregará incluye un valor ( **Dirección de destino**) que tiene un aspecto como el siguiente: \<MX token\>.mail.protection.outlook.de, donde \<MX token\> es un valor como MSxxxxxxx.   

::: moniker-end

1. En el sitio web de tu servidor DNS, añade un nuevo registro MX.
    
    Ahora [obtendrá la información para el registro MX](../get-help-with-domains/information-for-dns-records.md) de Office 365. 
    
2. Para el registro MX del paso anterior, copie el valor de **Dirección de destino**. 
    
    Deberá usar este valor en el registro que está creando en su host DNS del sitio, como se describe en el siguiente paso.
    
3. En el nuevo registro MX del sitio del host DNS, asegúrese de que los campos se configuran exactamente con los valores siguientes:
    
  - **Tipo de registro**: **MX**
    
  - **Prioridad**: defina la prioridad del registro MX con el valor más alto posible, que suele ser **0**.
    
    Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)
    
  - **Nombre de host**:**@**
    
  - **Dirección de destino**: pegue aquí el valor de**dirección de destino** que acaba de copiar de Office 365. 
    
  - **TTL**: configure este valor en**1 hora** o el equivalente en minutos (**60**), segundos (**3600**), etc. 
    
4. Guarde el registro.
    
Quite los demás registros MX.
  
Si tiene algún registro MX para este dominio que envíe correo electrónico a un lugar distinto de Office 365, elimínelo.
  
## <a name="add-three-cname-records"></a>Agregar tres registros CNAME
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Agregue los tres registros CNAME necesarios para Office 365. Si en Office 365 se muestran más registros CNAME, agréguelos siguiendo los pasos generales indicados aquí.
  
En el sitio web de su anfitrión DNS, creará tres nuevos registros CNAME, normalmente uno a la vez.
  
1. En el cuadro para cada nuevo registro, escriba o copie y pegue los valores siguientes. Después de agregar los primeros tres registros nuevos, elija crear otro registro CNAME.
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Host** <br/> |**Señala a** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hora  <br/> |
|CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 hora  <br/> |
|CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 hora  <br/> |
   
   > [!NOTE]
   > Por **TTL**: Configure este valor en**1 hora** o a el equivalente en minutos (**60**), segundos (**3600**), etc. > estos registros no se aplican a Exchange, Lync o Skype Empresarial para implementaciones híbridas. 
  
2. Cuando haya terminado, guarde los registros.
    
::: moniker-end
::: moniker range="o365-germany"

Agregue los tres registros CNAME necesarios para Office 365. Si en Office 365 se muestran más registros CNAME, agréguelos siguiendo los pasos generales indicados aquí.
  
En el sitio web de su anfitrión DNS, creará tres nuevos registros CNAME, normalmente uno a la vez.
  
1. En el cuadro para cada nuevo registro, escriba o copie y pegue los valores siguientes. Después de agregar los primeros tres registros nuevos, elija crear otro registro CNAME.
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Host** <br/> |**Señala a** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 hora  <br/> |
|CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 hora  <br/> |
|CNAME (alias)  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 hora  <br/> |
   
   > [!NOTE]
   > Por **TTL**: Configure este valor en**1 hora** o a el equivalente en minutos (**60**), segundos (**3600**), etc. > estos registros no se aplican a Exchange, Lync o Skype Empresarial para implementaciones híbridas. 
  
2. Cuando haya terminado, guarde los registros.
    
::: moniker-end

::: moniker range="o365-21vianet"

Agregue los tres registros CNAME necesarios para Office 365. Si en Office 365 se muestran más registros CNAME, agréguelos siguiendo los pasos generales indicados aquí.
  
En el sitio web de su anfitrión DNS, creará tres nuevos registros CNAME, normalmente uno a la vez.
  
1. En el cuadro para cada nuevo registro, escriba o copie y pegue los valores siguientes. Después de agregar los primeros tres registros nuevos, elija crear otro registro CNAME.
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Host** <br/> |**Señala a** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |autodescubrir  <br/> |autodiscover.partner.outlook.cn  <br/> |1 hora  <br/> |
|CNAME (alias)  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 hora  <br/> |
|CNAME (alias)  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 hora  <br/> |
   
   > [!NOTE]
   > Por **TTL**: Configure este valor en**1 hora** o a el equivalente en minutos (**60**), segundos (**3600**), etc. > estos registros no se aplican a Exchange, Lync o Skype Empresarial para implementaciones híbridas. 
  
2. Cuando haya terminado, guarde los registros.
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Añadir dos registros CNAME para la Gestión de Dispositivos Móviles (MDM) para Office 365
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Si tiene Mobile Device Management (MDM) para Office 365, entonces debe crear dos registros CNAME adicionales. Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla. > (Si no tienes MDM, puedes saltarte este paso.) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Host** <br/> |**Señala a** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hora  <br/> |
|CNAME (alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 hora  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Si tiene Mobile Device Management (MDM) para Office 365, entonces debe crear dos registros CNAME adicionales. Siga el procedimiento que utilizó para los otros cuatro registros CNAME, pero suministre los valores de la siguiente tabla. > (Si no tienes MDM, puedes saltarte este paso.) 
  
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Host** <br/> |**Señala a** <br/> |**TTL** <br/> |
|CNAME (alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 hora  <br/> |
|CNAME (alias)  <br/> |enterpriseenrollment  <br/> |EnterpriseEnrollment-s.manage.microsoft.com  <br/> |1 hora  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.
  
En el sitio web de su host DNS, edite el registro SPF existente o cree un nuevo registro TXT para SPF.
  
> [!IMPORTANT]
> SPF está diseñado para ayudar a evitar la suplantación de identidad, pero hay técnicas de suplantación de identidad contra las que SPF no puede proteger. Para protegerse de estos, una vez que haya configurado el SPF, también debe configurar DKIM y DMARC para Office 365. Para comenzar, vea [Usar DKIM para validar el correo electrónico saliente enviado desde el dominio en Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). A continuación, consulte [Usar DMARC para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. En los cuadros para el nuevo registro, escriba o copie y pegue el conjunto de valores siguientes que se aplican a su situación.
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Host** <br/> |**Valor TXT** <br/> |**TTL** <br/> |
|TXT (texto)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |1 hora  <br/> |
   
   Para **TTL**: configure este valor en **1 hora** o el equivalente en minutos (**60**), segundos (**3600**), etc. 
    
2. Cuando haya terminado, guarde el registro.
    
3. Para validar su registro de SPF, use una de estas[herramientas de validación SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. 
  
En el sitio web de su host DNS, edite el registro SPF existente o cree un nuevo registro TXT para SPF.
  
> [!IMPORTANT]
> SPF está diseñado para ayudar a evitar la suplantación de identidad, pero hay técnicas de suplantación de identidad contra las que SPF no puede proteger. Para protegerse de estos, una vez que haya configurado el SPF, también debe configurar DKIM y DMARC para Office 365. Para comenzar, vea [Usar DKIM para validar el correo electrónico saliente enviado desde el dominio en Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). A continuación, consulte [Usar DMARC para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. En los cuadros para el nuevo registro, escriba o copie y pegue el conjunto de valores siguientes que se aplican a su situación.
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro**|**Host**|**Valor TXT**|**TTL**|
|TXT (texto)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  Recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |1 hora|
   
   Para **TTL**: configure este valor en **1 hora** o el equivalente en minutos (**60**), segundos (**3600**), etc. 
    
2. Cuando haya terminado, guarde el registro.
    
3. Para validar su registro de SPF, use una de estas[herramientas de validación SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. 
  
En el sitio web de su host DNS, edite el registro SPF existente o cree un nuevo registro TXT para SPF.
  
> [!IMPORTANT]
> SPF está diseñado para ayudar a evitar la suplantación de identidad, pero hay técnicas de suplantación de identidad contra las que SPF no puede proteger. Para protegerse de estos, una vez que haya configurado el SPF, también debe configurar DKIM y DMARC para Office 365. Para comenzar, vea [Usar DKIM para validar el correo electrónico saliente enviado desde el dominio en Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). A continuación, consulte [Usar DMARC para validar el correo electrónico en Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. En los cuadros para el nuevo registro, escriba o copie y pegue el conjunto de valores siguientes que se aplican a su situación.
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro**|**Host**|**Valor TXT**|**TTL**|
|TXT (texto)|@|v=spf1 include:spf.protection.partner.outlook.cn -all>[!NOTE] > Recomendamos copiar y pegar esta entrada, para que todo el espaciado sea correcto.           |1 hora|
   
   Para **TTL**: configure este valor en **1 hora** o el equivalente en minutos (**60**), segundos (**3600**), etc. 
    
2. Cuando haya terminado, guarde el registro.
    
3. Para validar su registro de SPF, use una de estas[herramientas de validación SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).
    
::: moniker-end

## <a name="add-two-srv-records"></a>Agregar dos registros SRV
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

En el sitio web del host DNS, debe crear dos nuevos registros SRV, normalmente de uno en uno. Es decir, una vez que agregue el primer registro SRV en el sitio web, elija crear otro registro SRV.
  
1. En el cuadro para cada nuevo registro, escriba o copie y pegue los valores siguientes. **(Consulte las notas siguientes para crear registros SRV cuando el host DNS no tiene todos estos como campos independientes).**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Nombre** <br/> |**Destino** <br/> |**Protocolo** <br/> |**Servicio** <br/> |**Prioridad** <br/> |**Grosor** <br/> |**Puerto** <br/> |**TTL** <br/> |
|SRV (servicio)  <br/> |@  <br/> (O déjelo en blanco, si @ no está permitido)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hora  <br/> |
|SRV (servicio)  <br/> |@  <br/> (O déjelo en blanco, si @ no está permitido)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hora  <br/> |
   
  > [!NOTE]
  >  Para **nombre**: si su host DNS no permite la configuración para **@**, déjelo en blanco. Use este enfoque *solo* cuando el host DNS tiene campos separados para los valores de servicio y protocolo. De lo contrario, consulte las notas de servicio y protocolo a continuación. 

>  Para **servicio** y **protocolo**: si el host DNS no proporciona estos campos para registros SRV, debe especificar los valores de **servicio** y **protocolo** como el **nombre** del valor del registro. (Nota: dependiendo de su host DNS, el campo del **nombre** puede llamarse de otra forma, como: **host**, **nombre del host**o **subdominio**). Para establecer el valor combinado, se crea una sola cadena, separando los valores con un punto.  Por ejemplo: **Nombre**: _sip._tls 

>  Para **prioridad**, el**peso**y el**puerto**: si el host DNS no proporciona estos campos para registros SRV, debe especificarlos como el valor del **destino** del registro. (Nota: dependiendo de su host DNS, el campo del **destino** puede llamarse de otra forma, como: **contenido**, **dirección de IP**o **nombre de host de destino**). Para establecer el valor combinado, se crea una sola cadena, separando los valores con espacios y terminando con un punto. Los valores deben ser incluidos en este orden: prioridad, peso, puerto, y destino. Por ejemplo: **Destino**: 100 1 443 sipdir.online.lync.com. 

>  Variación para**prioridad**, **peso**y el **puerto**: algunos hosts DNS proporcionan algunos, pero no todos, de los campos obligatorios por separado. Para estos sitios de host de DNS, especifique los valores que no se muestran por separado como una cadena combinada, en orden, para el valor de **destino** del registro. (Nota: dependiendo de su host DNS, el campo del **destino** puede llamarse de otra forma, como: **contenido**, **dirección de IP**o **nombre de host de destino**). Para configurar el valor combinado, se crea una sola cadena para los campos que no se muestran individualmente, separando los valores con espacios. Los valores deben ser incluidos *en orden*,  dejando fuera los valores que tienen campos separados disponibles: prioridad, peso, puerto, y destino. Por ejemplo, cuando prioridad tiene un campo independiente, concatene solamente los valores peso, puerto y destino: **Destino**: 1 443 sipdir.online.lync.com 

> Para **TTL**: configure este valor en **1 hora** o el equivalente en minutos (**60**), segundos (**3600**), etc. 
  
2. Cuando haya terminado, guarde los registros.
    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-germany"

En el sitio web del host DNS, debe crear dos nuevos registros SRV, normalmente de uno en uno. Es decir, una vez que agregue el primer registro SRV en el sitio web, elija crear otro registro SRV.
  
1. En el cuadro para cada nuevo registro, escriba o copie y pegue los valores siguientes. **(Consulte las notas siguientes para crear registros SRV cuando el host DNS no tiene todos estos como campos independientes).**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Nombre** <br/> |**Destino** <br/> |**Protocolo** <br/> |**Servicio** <br/> |**Prioridad** <br/> |**Grosor** <br/> |**Puerto** <br/> |**TTL** <br/> |
|SRV (servicio)  <br/> |@  <br/> (O déjelo en blanco, si @ no está permitido)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hora  <br/> |
|SRV (servicio)  <br/> |@  <br/> (O déjelo en blanco, si @ no está permitido)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hora  <br/> |
   
 > [!NOTE]
 >  Para **nombre**: si su host DNS no permite la configuración para **@**, déjelo en blanco. Use este enfoque *solo* cuando el host DNS tiene campos separados para los valores de servicio y protocolo. De lo contrario, consulte las notas de servicio y protocolo a continuación. 

>  Para **servicio** y **protocolo**: si el host DNS no proporciona estos campos para registros SRV, debe especificar los valores de **servicio** y **protocolo** como el **nombre** del valor del registro. (Nota: dependiendo de su host DNS, el campo del **nombre** puede llamarse de otra forma, como: **host**, **nombre del host**o **subdominio**). Para establecer el valor combinado, se crea una sola cadena, separando los valores con un punto. > Por ejemplo: **nombre**: _sip._tls 

>  Para **prioridad**, el**peso**y el**puerto**: si el host DNS no proporciona estos campos para registros SRV, debe especificarlos como el valor del **destino** del registro. (Nota: dependiendo de su host DNS, el campo del **destino** puede llamarse de otra forma, como: **contenido**, **dirección de IP**o **nombre de host de destino**). Para establecer el valor combinado, se crea una sola cadena, separando los valores con espacios y terminando con un punto. Los valores deben ser incluidos en este orden: prioridad, peso, puerto, y destino. > Por ejemplo: **destino**: 100 1 443 sipdir.online.lync.de. 

>  Variación para**prioridad**, **peso**y el **puerto**: algunos hosts DNS proporcionan algunos, pero no todos, de los campos obligatorios por separado. Para estos sitios de host de DNS, especifique los valores que no se muestran por separado como una cadena combinada, en orden, para el valor de **destino** del registro. (Nota: dependiendo de su host DNS, el campo del **destino** puede llamarse de otra forma, como: **contenido**, **dirección de IP**o **nombre de host de destino**). Para configurar el valor combinado, se crea una sola cadena para los campos que no se muestran individualmente, separando los valores con espacios. Los valores deben ser incluidos *en orden*,  dejando fuera los valores que tienen campos separados disponibles: prioridad, peso, puerto, y destino. > Por ejemplo, cuando Priority tiene un campo independiente, concatene solo los valores peso, puerto y destino: **destino**: 1 443 sipdir.online.lync.de 

>  Para **TTL**: configure este valor en **1 hora** o el equivalente en minutos (**60**), segundos (**3600**), etc. 
  
2. Cuando haya terminado, guarde los registros.
    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-21vianet"

En el sitio web del host DNS, debe crear dos nuevos registros SRV, normalmente de uno en uno. Es decir, una vez que agregue el primer registro SRV en el sitio web, elija crear otro registro SRV.
  
1. En el cuadro para cada nuevo registro, escriba o copie y pegue los valores siguientes. **(Consulte las notas siguientes para crear registros SRV cuando el host DNS no tiene todos estos como campos independientes).**
    
||||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Nombre** <br/> |**Destino** <br/> |**Protocolo** <br/> |**Servicio** <br/> |**Prioridad** <br/> |**Grosor** <br/> |**Puerto** <br/> |**TTL** <br/> |
|SRV (servicio)  <br/> |@  <br/> (O déjelo en blanco, si @ no está permitido)  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hora  <br/> |
|SRV (servicio)  <br/> |@  <br/> (O déjelo en blanco, si @ no está permitido)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hora  <br/> |
   
 > [!NOTE]
 >  Para **nombre**: si su host DNS no permite la configuración para **@**, déjelo en blanco. Use este enfoque *solo* cuando el host DNS tiene campos separados para los valores de servicio y protocolo. De lo contrario, consulte las notas de servicio y protocolo a continuación. 

>  Para **servicio** y **protocolo**: si el host DNS no proporciona estos campos para registros SRV, debe especificar los valores de **servicio** y **protocolo** como el **nombre** del valor del registro. (Nota: dependiendo de su host DNS, el campo del **nombre** puede llamarse de otra forma, como: **host**, **nombre del host**o **subdominio**). Para establecer el valor combinado, se crea una sola cadena, separando los valores con un punto. > Por ejemplo: **nombre**: _sip._tls 

>  Para **prioridad**, el**peso**y el**puerto**: si el host DNS no proporciona estos campos para registros SRV, debe especificarlos como el valor del **destino** del registro. (Nota: dependiendo de su host DNS, el campo del **destino** puede llamarse de otra forma, como: **contenido**, **dirección de IP**o **nombre de host de destino**). Para establecer el valor combinado, se crea una sola cadena, separando los valores con espacios y terminando con un punto. Los valores deben ser incluidos en este orden: prioridad, peso, puerto, y destino. > Por ejemplo: **destino**: 100 1 443 sipdir.online.partner.lync.cn. 

>  Variación para**prioridad**, **peso**y el **puerto**: algunos hosts DNS proporcionan algunos, pero no todos, de los campos obligatorios por separado. Para estos sitios de host de DNS, especifique los valores que no se muestran por separado como una cadena combinada, en orden, para el valor de **destino** del registro. (Nota: dependiendo de su host DNS, el campo del **destino** puede llamarse de otra forma, como: **contenido**, **dirección de IP**o **nombre de host de destino**). Para configurar el valor combinado, se crea una sola cadena para los campos que no se muestran individualmente, separando los valores con espacios. Los valores deben ser incluidos *en orden*,  dejando fuera los valores que tienen campos separados disponibles: prioridad, peso, puerto, y destino. > Por ejemplo, cuando Priority tiene un campo independiente, concatene solamente los valores peso, puerto y valores del destino: **destino**: 1 443 sipdir.online.partner.lync.cn 

>  Para **TTL**: configure este valor en **1 hora** o el equivalente en minutos (**60**), segundos (**3600**), etc. 
  
2. Cuando haya terminado, guarde los registros.
    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>Más sobre la actualización de los registros DNS
<a name="BKMK_MoreAbout"> </a>

 **Si sabe cómo actualizar registros DNS en el host DNS del dominio**, use los valores de DNS Office 365 para editar los registros del host DNS del dominio, por ejemplo, para configurar un registro MX o SPF. Busque los valores específicos que debe usar realizando los [siguientes pasos](../get-help-with-domains/information-for-dns-records.md). También puede verlos en el asistente para configuración de dominios al avanzar por él.
  
 **Si necesita ayuda para saber cómo agregar los registros DNS requeridos**consulte[ configurar su dominio (instrucciones específicas para el host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide), primero [reunir la información necesaria para crear los registros DNS de Office 365](../get-help-with-domains/information-for-dns-records.md). Después, siga los pasos generales que se indican en este tema para configurar sus registros DNS del dominio y así poder usar su dominio con los servicios de Office 365, como el correo electrónico.
  
 **Si no tiene un sitio web que usa con el dominio personalizado**, puede hacer que Office 365 configure y administre los registros DNS de su dominio en lugar de realizar toda la configuración usted mismo. Obtenga información sobre las [dos opciones para configurar y administrar registros DNS de un dominio personalizado](https://support.office.com/article/5980474a-097f-4f21-a864-21245314957f.aspx) en Office 365. 
  

