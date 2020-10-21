---
title: Crear registros DNS en Hostgator para Microsoft
f1.keywords:
- NOCSH
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Hostgator para Microsoft.
ms.openlocfilehash: f8cfc417a7ff9821fd40b33c8dfe9932dd454d18
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646000"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>Crear registros DNS en Hostgator para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si Hostgator es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
  
> [!IMPORTANT]
> Debe realizar la primera procedurebelow, [apuntar su dominio a su cuenta de hospedaje](#point-your-domain-to-your-hosting-account), antes de agregar los registros DNS mediante cualquiera de los otros procedimientos de este artículo. 

Después de realizar todos estos cambios en Hostgator, su dominio estará configurado para funcionar con los servicios de Microsoft.
  

  
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Apuntar el dominio a su cuenta de hospedaje
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> Necesita realizar este procedimiento antes de realizar cualquier otro procedimiento de este artículo. 
  
Siga estos pasos para asociar el dominio y las cuentas de hospedaje.
  
1. Para empezar, vaya a su página de administración de dominios en Hostgator con [este vínculo](https://portal.hostgator.com/). Se le pedirá que inicie sesión.
    
2. Seleccione **dominios** en el lado izquierdo.
  
3. En la página **administrar dominios** , seleccione el dominio que desea actualizar. 
  
4. En el menú emergente de la izquierda, seleccione servidores de **nombres**.
  
5. En la página **servidores DNS** del dominio, en la lista desplegable **apuntar automáticamente este dominio a mi cuenta de hospedaje** , elija la cuenta de hospedaje asociada con el dominio. 
  
6. Seleccione **Guardar servidores de nombres**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Antes de realizar este procedimiento, primero necesita realizar el procedimiento de la primera sección de este artículo, [Apuntar el dominio a su cuenta de hospedaje](#point-your-domain-to-your-hosting-account). 
  
Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a la página cPanel en Hostgator. Se le pedirá que inicie sesión primero.
    
    (Cada cuenta alojada en Hostgator se le asigna una única dirección CPanel. La dirección cPanel debe tener un aspecto parecido a este: https://YourSiteAddress:secure-port-number. El correo electrónico de suscripción que ha recibido de Hostgator especificará esa dirección y un vínculo de cPanel también está disponible en la página de **hospedaje** ).
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para empezar a trabajar con Microsoft, puede comprar una cuenta de hospedaje en Hostgator o volver a [delegar los servidores de nombres para que apunten a Microsoft](change-nameservers-at-hostgator.md). 
  
2. En la página **Panel de control** , en el área **dominios** , seleccione **Advanced Zone editor**.
    
3. En la página **Editor de zonas avanzadas** , en el área **Agregar un registro** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. 
    
    (Elija el valor **Tipo** de la lista desplegable). 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Nombre** <br/> |**TTL** <br/> |**Tipo** <br/> |**Datos TXT** <br/> |
    |Use su  *domain_name*. (por ejemplo, fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Seleccione **Agregar registro**.
    
5. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
4. En la página**Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Antes de realizar este procedimiento, primero necesita realizar el procedimiento de la primera sección de este artículo, [Apuntar el dominio a su cuenta de hospedaje](#point-your-domain-to-your-hosting-account). 
  
1. Para empezar, vaya a la página cPanel en Hostgator. Se le pedirá que inicie sesión primero.
    
    (Cada cuenta alojada en Hostgator se le asigna una única dirección CPanel. La dirección cPanel debe tener un aspecto parecido a este: https://YourSiteAddress:secure-port-number. El correo electrónico de suscripción que ha recibido de Hostgator especificará esa dirección y un vínculo de cPanel también está disponible en la página de **hospedaje** ).
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para empezar a trabajar con Microsoft, puede comprar una cuenta de hospedaje en Hostgator o volver a [delegar los servidores de nombres para que apunten a Microsoft](change-nameservers-at-hostgator.md). 
  
2. En la página **Panel de control** , en el área **correo electrónico** , seleccione **entrada MX**.
    
 
3. En el área **Enrutamiento de correo electrónico**, seleccione **Agente de intercambio de correo remoto**.

4. Seleccione **Cambiar**.
  
5. En el área **Agregar un nuevo registro** , en los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente. 
    
    |**Prioridad**|**Destino**|
    |:-----|:-----|
    |comprendi  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Nota: **Obtenga la \< *domain-key*  \> desde su cuenta de Microsoft.  [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Seleccione **Agregar nuevo registro**.
   
 
7. Si hay otros registros MX en la sección **registros MX** , quítelos. 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Agregar los seis registros CNAME necesarios para Microsoft
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Antes de realizar este procedimiento, primero necesita realizar el procedimiento de la primera sección de este artículo, [Apuntar el dominio a su cuenta de hospedaje](#point-your-domain-to-your-hosting-account). 
  
1. Para empezar, vaya a la página cPanel en Hostgator. Se le pedirá que inicie sesión primero.
    
    (Cada cuenta alojada en Hostgator se le asigna una única dirección CPanel. La dirección cPanel debe tener un aspecto parecido a este: https://YourSiteAddress:secure-port-number. El correo electrónico de suscripción que ha recibido de Hostgator especificará esa dirección y un vínculo de cPanel también está disponible en la página de **hospedaje** ).
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para empezar a trabajar con Microsoft, puede comprar una cuenta de hospedaje en Hostgator o volver a [delegar los servidores de nombres para que apunten a Microsoft](change-nameservers-at-hostgator.md). 
  
2. En la página **Panel de control** , en el área **dominios** , seleccione **Advanced Zone editor**.
    
3. Agregue el primero de los seis registros CNAME.
    
    En la página **Editor de zonas avanzadas** , en el área **Agregar un registro** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente. 
    
    (Elija el valor **Tipo** de la lista desplegable). 
    
    |**Nombre**|**TTL**|**Tipo**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (por ejemplo, autodiscover.fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (por ejemplo, sip.fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (por ejemplo, lyncdiscover.fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (por ejemplo, enterpriseregistration.fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (por ejemplo, enterpriseregistration.fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Seleccione **Agregar registro**.

5. Agregue los otros cinco registros CNAME.
    
    En la sección **Agregar un registro** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro). 
    
    Repita este proceso hasta crear los seis registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En vez de eso, agregue los valores necesarios de Microsoft para el registro actual, de modo que solo tenga un único registro de SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> Antes de realizar este procedimiento, primero necesita realizar el procedimiento de la primera sección de este artículo, [Apuntar el dominio a su cuenta de hospedaje](#point-your-domain-to-your-hosting-account). 
  
1. Para empezar, vaya a la página cPanel en Hostgator. Se le pedirá que inicie sesión primero.
    
    (Cada cuenta alojada en Hostgator se le asigna una única dirección CPanel. La dirección cPanel debe tener un aspecto parecido a este: https://YourSiteAddress:secure-port-number. El correo electrónico de suscripción que ha recibido de Hostgator especificará esa dirección y un vínculo de cPanel también está disponible en la página de **hospedaje** ).
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para empezar a trabajar con Microsoft, puede comprar una cuenta de hospedaje en Hostgator o volver a [delegar los servidores de nombres para que apunten a Microsoft](change-nameservers-at-hostgator.md). 
  
2. En la página **Panel de control** , en el área **dominios** , seleccione **Advanced Zone editor**.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Elija el valor **Tipo** de la lista desplegable). 
    
    |**Nombre**|**TTL**|**Tipo**|**Datos TXT**|
    |:-----|:-----|:-----|:-----|
    |Use su  *domain_name*. (por ejemplo, fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
  
4. Seleccione **Agregar registro**.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Antes de realizar este procedimiento, primero necesita realizar el procedimiento de la primera sección de este artículo, [Apuntar el dominio a su cuenta de hospedaje](#point-your-domain-to-your-hosting-account). 
  
1. Para empezar, vaya a la página cPanel en Hostgator. Se le pedirá que inicie sesión primero.
    
    (Cada cuenta alojada en Hostgator se le asigna una única dirección CPanel. La dirección cPanel debe tener un aspecto parecido a este: https://YourSiteAddress:secure-port-number. El correo electrónico de suscripción que ha recibido de Hostgator especificará esa dirección y un vínculo de cPanel también está disponible en la página de **hospedaje** ).
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para empezar a trabajar con Microsoft, puede comprar una cuenta de hospedaje en Hostgator o volver a [delegar los servidores de nombres para que apunten a Microsoft](change-nameservers-at-hostgator.md). 
  
2. En la página **Panel de control** , en el área **dominios** , seleccione **Advanced Zone editor**.

    
3. Agregue el primero de los dos registros SRV.
    
    En la página **Editor avanzado de zona DNS**, en el área **Agregar registro**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente. 
    
    (Elija el valor **Tipo** de la lista desplegable). 
    
    |**Nombre**|**TTL**|**Tipo**|**Prioridad**|**Grosor**|**Puerto**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _sip._tls. *domain_name*. (por ejemplo, _sip._tls.fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _sipfederationtls._tcp. *domain_name*. (por ejemplo, _sipfederationtls._tcp.fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Seleccione **Agregar registro**.

  
5. Agregue el otro registro SRV.
    
    En la sección **Agregar un registro** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro). 
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
