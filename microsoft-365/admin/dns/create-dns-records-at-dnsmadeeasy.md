---
title: Crear registros DNS en DNSMadeEasy para Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en DNSMadeEasy para Office 365.
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248825"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a>Crear registros DNS en DNSMadeEasy para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si DNSMadeEasy es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
  
Después de agregar estos registros a DNSMadeEasy, el dominio estará configurado para funcionar con los servicios de Office 365.
  
Para obtener información sobre hospedaje web y DNS para sitios web con Office 365, vea [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
> [!IMPORTANT]
> Para las cuentas de DNSMadeEasy, el dominio que agregó se compró de un registrador de dominios separado. DNSMadeEasy no ofrece servicios de registro de dominios. Su capacidad para iniciar sesión en DNSMadeEasy y crear el registro DNS es una prueba suficiente de que es el propietario. 
  
1. Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.
    
2. En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar. 
    
3. En la página **DNS administrados** , en el área **registros txt** , seleccione el **+** control () ( **Agregar nuevo**).
    
    (You may have to scroll down.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**Name** <br/> |**Valor** <br/> |**TTL** <br/> |
    |(Deje este campo en blanco).  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** Este es un ejemplo. Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365. [¿Cómo puedo encontrarlo?](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. Seleccione **Enviar**.
    
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .

    
2. En la página **dominios** , seleccione el dominio que desea comprobar. 
    
3. En la página **configuración** , seleccione **Iniciar configuración**.
    
4. En la página **comprobar dominio** , seleccione **comprobar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365
<a name="BKMK_add_MX"> </a>

1. Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.
    
2. En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar. 
    
    En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar. 
    
    ![DNSMadeEasy-BP-configure-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. En la página **DNS administrados** , en el área **registros MX** , seleccione el control **(+)** ( **Agregar nuevo**).
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-BP-configure-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. En el área **Agregar registros MX**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente. 
    
    (Es posible que tenga que desplazarse hacia abajo).
    
    |**Name**|**Servidor**|**Nivel de MX**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(Deje este campo en blanco).  <br/> | *\< clave-de-dominio \>*  . mail.protection.outlook.com      <br/> **This value MUST end with a period (.)** <br/> **Nota:** Obtenga la \< *clave* \> de dominio de su cuenta de Office 365. [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. Seleccione **Enviar**.
    
    ![DNSMadeEasy-BP-configure-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. Si en la sección **Registros MX** se muestran otros registros MX, selecciónelos para eliminarlos. 
    
    ![DNSMadeEasy-BP-configure-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. Una vez seleccionados todos los registros, seleccione **eliminar seleccionados**.
    
    ![DNSMadeEasy-BP-configure-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. En el cuadro de diálogo **eliminar registros MX** , seleccione **eliminar** para confirmar los cambios. 
    
    ![DNSMadeEasy-BP-configure-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Agregue los cinco registros CNAME necesarios para Office 365
<a name="BKMK_add_CNAME"> </a>

1. Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.
    
2. En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar. 
    
3. En la página **DNS administrados** , en el área **registros CNAME** , seleccione el control **(+)** ( **Agregar nuevo**).
    
    (Es posible que tenga que desplazarse hacia abajo).
    
    ![DNSMadeEasy-BP-configure-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. Agregue el primero de los cinco registros CNAME.
    
    En el área **Agregar registros CNAME**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente. 
    
    |**Nombre**|**Alias para**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. Seleccione **Enviar**.
    
    ![DNSMadeEasy-BP-configure-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. Agregue cada uno de los otros cuatro registros CNAME.
    
    En la sección **registros CNAME** , seleccione el control **(+)** ( **Agregar nuevo**), cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, seleccione **Enviar** para completar ese registro). 
    
    Repita este proceso hasta que haya creado los cinco registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte estos [registros del sistema de nombres de dominio externo para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md). 
  
1. Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.
    
2. En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar. 
    
3. En la página **DNS administrados** , en el área **registros txt** , seleccione el control **(+)** ( **Agregar nuevo**).
    
    (Es posible que tenga que desplazarse hacia abajo).
    
    ![DNSMadeEasy-BP-configure-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Name**|**Valor**|**TTL**|
    |:-----|:-----|:-----|
    |(Deje este campo en blanco).  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.           |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. Seleccione **Enviar**.
    
    ![DNSMadeEasy-BP-configure-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Agregar los dos registros SRV necesarios para Office 365
<a name="BKMK_add_SRV"> </a>

1. Para empezar, vaya a su página de dominios en DNSMadeEasy a través de [este vínculo](https://cp.dnsmadeeasy.com/). Se le pedirá que inicie sesión primero.
    
2. En la página **consola de administración** , en el área **dominios actualizados recientemente** , seleccione el dominio que desea actualizar. 
    
3. En la página **DNS administrados** , en el área **registros SRV** , seleccione el control **(+)** ( **Agregar nuevo**).
    
    (Puede que tenga que desplazarse hacia abajo).
    
    ![DNSMadeEasy-BP-configure-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. Agregue el primero de los dos registros SRV.
    
    En el área **Agregar registros SRV**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente. 
    
    |**Nombre**|**Prioridad**|**Peso**|**Puerto**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1800  <br/> |
    |_sipfederationtls. _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. Seleccione **Enviar**.
    
    ![DNSMadeEasy-BP-configure-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. Agregue el otro registro SRV.
    
    En la sección **registros SRV** , seleccione el control **(+)** ( **Agregar nuevo**), cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, seleccione **Enviar** para completar ese registro). 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

