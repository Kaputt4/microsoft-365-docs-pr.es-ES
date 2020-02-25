---
title: Crear registros DNS en namecheap para Office 365
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en namecheap para Office 365.
ms.openlocfilehash: a913aa5f2d88be5bed246e813bebd590f401c07f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246549"
---
# <a name="create-dns-records-at-namecheap-for-office-365"></a>Crear registros DNS en namecheap para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si namecheap es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc.
  
Después de agregar estos registros a namecheap, su dominio estará configurado para trabajar con los servicios de Office 365.
  
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
Siga estos pasos.
  
1. Para empezar, vaya a su página de dominios en namecheap a través de [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.
    
    ![Namecheap-BP-configure-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. En la página de **aterrizaje** , en **cuenta**, elija **lista de dominios** en la lista desplegable. 
    
    ![Namecheap-BP-configure-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. En la página **lista de dominios** , busque el nombre del dominio que desea editar y, a continuación, seleccione **administrar**.
    
    ![Namecheap-BP-configure-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Seleccione **DNS avanzado**.
    
    ![Namecheap-BP-configure-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. En la sección **registros de host** , seleccione **Agregar nuevo registro**.
    
    ![Namecheap-BP-configure-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. En la lista desplegable **tipo** , seleccione **registro TXT**.
    
    > [!NOTE]
    > La lista desplegable **tipo** aparece automáticamente cuando se selecciona **Agregar nuevo registro**. 
  
    ![Namecheap-BP-Verify-1-1](../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. In the boxes for the new record, type or copy and paste the values from the following table.
    
    (Elija el valor **TTL** de la lista desplegable). 
    
    |**Tipo**|**Host**|**Valor**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/>**Nota:** Este es un ejemplo. Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.  [¿Cómo puedo encontrarlo?](../get-help-with-domains/information-for-dns-records.md)          |30 minutos  <br/> |
       
    ![Namecheap-BP-Verify-1-2](../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. Seleccione el control **Guardar cambios** (marca de verificación). 
    
    ![Namecheap-BP-Verify-1-3](../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .
    
2. En la página **dominios** , seleccione el dominio que desea comprobar. 
    
    
  
3. En la página **configuración** , seleccione **Iniciar configuración**.
    
    
  
4. En la página **comprobar dominio** , seleccione **comprobar**.
    
    
  
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365
<a name="BKMK_add_MX"> </a>

Siga estos pasos.
  
1. Para empezar, vaya a su página de dominios en namecheap a través de [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.
    
    ![Namecheap-BP-configure-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. En la página de **aterrizaje** , en **cuenta**, elija **lista de dominios** en la lista desplegable. 
    
    ![Namecheap-BP-configure-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. En la página **lista de dominios** , busque el nombre del dominio que desea editar y, a continuación, seleccione **administrar**.
    
    ![Namecheap-BP-configure-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Seleccione **DNS avanzado**.
    
    ![Namecheap-BP-configure-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. En la sección **configuración de correo** , seleccione **mx personalizado** en la lista desplegable **reenvío de correo electrónico** . 
    
    (You may have to scroll down.)
    
    ![Namecheap-BP-configure-2-1](../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png)
  
6. Seleccione **Agregar nuevo registro**.
    
    ![Namecheap-BP-configure-2-2-1](../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png)
  
7. En los cuadros para el nuevo registro, escriba (o copie y pegue) los valores de la tabla siguiente.
    
    (El cuadro **prioridad** es el cuadro sin nombre a la derecha del cuadro **valor** . Elija el valor **TTL** de la lista desplegable). 
    
    |**Tipo**|**Host**|**Valor**|**Prioridad**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |Registro MX  <br/> |@  <br/> |\<*Domain-Key*\>. mail.Protection.Outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Nota:** Obtenga la * \<clave\> de dominio* de su cuenta de Office 365.  [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |comprendi  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |30 minutos  <br/> |
       
    ![Namecheap-BP-configure-2-2-2](../media/f3b76d62-5022-48c1-901b-8615a8571309.png)
  
8. Seleccione el control **Guardar cambios** (marca de verificación). 
    
    ![Namecheap-BP-configure-2-3](../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png)
  
9. Si existen otros registros MX, quite cada uno de ellos usando el procedimiento de dos pasos siguiente:
    
    En primer lugar, seleccione el **icono de eliminación** (papelera) para el registro que desea quitar. 
    
    ![Namecheap-BP-configure-2-4](../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png)
  
    En segundo lugar, seleccione **sí** para confirmar la eliminación. 
    
    ![Namecheap-BP-configure-2-5](../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png)
  
    Quite todos los registros MX excepto el que ha agregado anteriormente en este procedimiento.

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Agregar los seis registros CNAME necesarios para Office 365
<a name="BKMK_add_CNAME"> </a>

Siga estos pasos.
  
1. Para empezar, vaya a su página de dominios en namecheap a través de [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.
    
    ![Namecheap-BP-configure-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. En la página de **aterrizaje** , en **cuenta**, elija **lista de dominios** en la lista desplegable. 
    
    ![Namecheap-BP-configure-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. En la página **lista de dominios** , busque el nombre del dominio que desea editar y, a continuación, seleccione **administrar**.
    
    ![Namecheap-BP-configure-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Seleccione **DNS avanzado**.
    
    ![Namecheap-BP-configure-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. En la sección **registros de host** , seleccione **Agregar nuevo registro**.
    
    ![Namecheap-BP-configure-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. En la lista desplegable **tipo** , seleccione **registro CNAME**.
    
    > [!NOTE]
    > La lista desplegable **tipo** aparece automáticamente cuando se selecciona **Agregar nuevo registro**. 
  
    ![Namecheap-BP-configure-3-1](../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png)
  
7. En los cuadros vacíos para el nuevo registro, seleccione **CNAME** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |**Tipo**|**Host**|**Valor**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |3600  <br/> |
       
    ![Namecheap-BP-configure-3-2](../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png)
  
8. Seleccione el control **Guardar cambios** (marca de verificación). 
    
    ![Namecheap-BP-configure-3-3](../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png)
  
9. Con los cuatro pasos anteriores y los valores de las otras cinco filas de la tabla, agregue cada uno de los otros cinco registros CNAME.

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. 

Siga estos pasos.
  
1. Para empezar, vaya a su página de dominios en namecheap a través de [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.
    
2. En la página de **aterrizaje** , en **cuenta**, elija **lista de dominios** en la lista desplegable. 
    
    ![Namecheap-BP-configure-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. En la página **lista de dominios** , busque el nombre del dominio que desea editar y, a continuación, seleccione **administrar**.
    
    ![Namecheap-BP-configure-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Seleccione **DNS avanzado**.
    
    ![Namecheap-BP-configure-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. En la sección **registros de host** , seleccione **Agregar nuevo registro**.
    
    ![Namecheap-BP-configure-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. En la lista desplegable **tipo** , seleccione **registro TXT**.
    
    > [!NOTE]
    > La lista desplegable **tipo** aparece automáticamente cuando se selecciona **Agregar nuevo registro**. 
  
    ![Namecheap-BP-configure-4-1](../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png)
  
7. En los cuadros para el nuevo registro, escriba o copie y pegue los valores siguientes de la tabla siguiente.
    
    (Elija el valor **TTL** de la lista desplegable). 
    
    |**Tipo**|**Host**|**Valor**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.           |30 minutos  <br/> |
       
    ![Namecheap-BP-configure-4-2](../media/ea0829f1-990b-424b-b26e-9859468318dd.png)
  
8. Seleccione el control **Guardar cambios** (marca de verificación). 
    
    ![Namecheap-BP-configure-4-3](../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Agregar los dos registros SRV necesarios para Office 365
<a name="BKMK_add_SRV"> </a>

1. Para empezar, vaya a su página de dominios en namecheap a través de [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). You'll be prompted to sign in.
    
    ![Namecheap-BP-configure-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. En la página de **aterrizaje** , en **cuenta**, elija **lista de dominios** en la lista desplegable. 
    
    ![Namecheap-BP-configure-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. En la página **lista de dominios** , busque el nombre del dominio que desea editar y, a continuación, seleccione **administrar**.
    
    ![Namecheap-BP-configure-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Seleccione **DNS avanzado**.
    
    ![Namecheap-BP-configure-1-4](../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. En la sección **registros de host** , seleccione **Agregar nuevo registro**.
    
    ![Namecheap-BP-configure-1-5](../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. En la lista desplegable **tipo** , seleccione **registro SRV**.
    
    > [!NOTE]
    > La lista desplegable **tipo** aparece automáticamente cuando se selecciona **Agregar nuevo registro**. 
  
    ![Namecheap-BP-configure-5-1](../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png)
  
7. En los cuadros vacíos para los nuevos registros, escriba (o copie y pegue) los valores de la primera fila en la tabla siguiente.
    
    |**Servicio**|**Protocolo**|**Prioridad**|**Peso**|**Puerto**|**Destino**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |30 minutos  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |30 minutos  <br/> |
       
    ![Namecheap-BP-configure-5-2](../media/ff9566ea-0096-4b7f-873c-027080a23b56.png)
  
8. Seleccione el control **Guardar cambios** (marca de verificación). 
    
    ![Namecheap-BP-configure-5-3](../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png)
  
9. Con los cuatro pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

  
