---
title: Crear registros DNS en Bluehost para Office 365
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Bluehost para Office 365.
ms.openlocfilehash: 9a5cad6778cb66958539a324befee43ddb2dd8b9
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247217"
---
# <a name="create-dns-records-at-bluehost-for-office-365"></a>Crear registros DNS en Bluehost para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si Bluehost es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
  
Después de agregar estos registros a Bluehost, el dominio estará configurado para funcionar con los servicios de Office 365.
  
Para obtener información sobre hospedaje web y DNS para sitios web con Office 365, vea [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm). You'll be prompted to log in first.
    
2. En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio. 
    
    (Es posible que tenga que desplazarse hacia abajo).
    
3. En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.
    
4. En la página * * editor de la zona DNS * *, en el área **Agregar registro DNS** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Host Record** <br/> |**TTL** <br/> |**Tipo** <br/> |**TXT Value** <br/> |
    |@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** Este es un ejemplo. Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365. [¿Cómo puedo encontrarlo?](../get-help-with-domains/information-for-dns-records.md)          |
   
5. Seleccione **Agregar registro**.
    
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

1. Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm). You'll be prompted to log in first.
    
2. En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio. 
    
    (Es posible que tenga que desplazarse hacia abajo).
    
3. En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Tipo**|**Apunta a**|**Prioridad**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |MX  <br/> | *\< clave-de-dominio \>*  . mail.protection.outlook.com      <br/>**Nota:** Obtenga la \< *clave* \> de dominio de su cuenta de Office 365. [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |comprendi  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![Elija tipo en la lista desplegable](../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. Seleccione **Agregar registro**.
    
    ![Seleccione Agregar registro](../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. Si hay otros registros MX en la sección **MX (agente de intercambio de correo)**, elimínelos. 
    
    Para uno de los demás registros MX, seleccione **eliminar.**
    
    ![Seleccione Eliminar para cada registro MX adicional](../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. En el cuadro de diálogo de confirmación, seleccione **Aceptar**.
    
    ![Seleccione Aceptar.](../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. Siga el mismo procedimiento para eliminar el resto de los registros MX que se muestren.
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Agregar los seis registros CNAME necesarios para Office 365
<a name="BKMK_add_CNAME"> </a>

1. Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm). You'll be prompted to log in first.
    
2. En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio. 
    
    (Es posible que tenga que desplazarse hacia abajo).
    
3. En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.
    
4. En la sección registros de **A (host)** , busque la fila del registro de **detección automática** y, a continuación, seleccione **eliminar** para esa fila. 
    
    > [!IMPORTANT]
    > Tiene que eliminar el registro **autodiscover** existente  *antes*  de agregar el registro **autodiscover** necesario para Office 365. Bluehost no le permite mantener de forma simultánea dos registros **autodiscover**. 
  
    ![Seleccione eliminar.](../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. Seleccione **Aceptar**.
    
    ![Seleccione Aceptar.](../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. Cree el primero de los seis registros CNAME.
    
    En la página **Editor de zona DNS**, en el área **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Tipo**|**Apunta a**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |14400  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |14400  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |14400  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |14400  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |14400  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Crear el primer registro CNAME](../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. Seleccione **Agregar registro**.
    
    ![Seleccione Agregar registro](../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. Agregue los otros cinco registros CNAME.
    
    En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro). 
    
    Repita este proceso hasta crear los seis registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte estos [registros del sistema de nombres de dominio externo para Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md). 
  
1. Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm). You'll be prompted to log in first.
    
2. En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio. 
    
    (Es posible que tenga que desplazarse hacia abajo).
    
3. En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
        
    |**Host Record**|**TTL**|**Tipo**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.           |
   
    ![Copiar el valor TXT](../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. Seleccione **Agregar registro**.
    
    ![Seleccione Agregar registro](../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Agregar los dos registros SRV necesarios para Office 365
<a name="BKMK_add_SRV"> </a>

1. Para empezar, vaya a su página de dominios en Bluehost a través de [este vínculo](https://my.bluehost.com/cgi/dm). You'll be prompted to log in first.
    
2. En la página **dominios**, en el área **dominio**, encuentre la fila del dominio que quiere cambiar y, a continuación, seleccione la casilla que corresponde a ese dominio. 
    
    (Es posible que tenga que desplazarse hacia abajo).
    
3. En el área ***domain_name*** , en la fila editor de la **zona DNS** , seleccione **administrar registros DNS**.
    
4. Cree el primero de los dos registros SRV.
    
    En la página **Editor de zona DNS**, en el área **Agregar registro DNS**, en los cuadros del nuevo registro, escriba (o copie y pegue) los valores de la primera fila de la tabla siguiente. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Servicio**|**Protocolo**|**Host**|**TTL**|**Tipo**|**Prioridad**|**Peso**|**Puerto**|**Apunta a**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Copiar el valor del nuevo registro](../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. Seleccione **Agregar registro**.
    
    ![Seleccione Agregar registro](../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. Agregue el otro registro SRV.
    
    En la sección **Agregar registro DNS** , cree un registro (para hacerlo, use los valores de la otra fila de la tabla y, después, vuelva a seleccionar **Agregar registro** para completar ese registro). 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

