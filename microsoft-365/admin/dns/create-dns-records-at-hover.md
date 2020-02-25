---
title: Crear registros DNS en Hover para Office 365
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Aprenda a comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios al pasar el mouse para Office 365.
ms.openlocfilehash: 54ff58963dcd66f692507f1d778fb9a8d24f82fa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249273"
---
# <a name="create-dns-records-at-hover-for-office-365"></a>Crear registros DNS en Hover para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si Hover es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
     
Después de agregar estos registros a Hover, su dominio estará configurado para trabajar con los servicios de Office 365.
  
Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.
    
    ![Iniciar sesión](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. En **administre sus dominios**, seleccione el nombre del dominio que desea editar.
    
    ![Seleccionar un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Seleccione la pestaña **DNS** . 
    
    ![Seleccione la pestaña DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Seleccione **Agregar nuevo**.
    
    ![Seleccione Agregar nuevo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    ||||
    |:-----|:-----|:-----|
    |Nombre de host  <br/> |Tipo de registro  <br/> |Valor  <br/> |
    |@  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** Este es un ejemplo. Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.           [¿Cómo puedo encontrarlo?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Escriba (o copie y pegue) los valores DNS](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. Seleccione **Guardar**.
    
    ![Seleccione Guardar](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .
    
2. En la página **dominios** , seleccione el dominio que desea comprobar. 
    
    
  
3. En la página **configuración** , seleccione **Iniciar configuración**.
    
    
  
4. En la página **comprobar dominio** , seleccione **comprobar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365
<a name="BKMK_add_MX"> </a>

Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.
    
    ![Iniciar sesión](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. En **administre sus dominios**, seleccione el nombre del dominio que desea editar.
    
    ![Seleccionar un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Seleccione la pestaña **DNS** . 
    
    ![Seleccione la pestaña DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Seleccione **Agregar nuevo**.
    
    ![Seleccione Agregar nuevo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. En los cuadros para el nuevo registro, seleccione **MX** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la tabla siguiente.
    
    |**Nombre de host**|**Tipo de registro**|**Prioridad**|**Nombre de host**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |comprendi  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\< clave-de-dominio \>*  . mail.protection.outlook.com      <br/> **Nota:** Obtenga la * \<clave\> de dominio* de su cuenta de Office 365.           [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Escriba (o copie y pegue) los valores DNS](../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. Seleccione **Guardar**.
    
    ![Seleccione Guardar](../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. Si existen otros registros MX, quite cada uno de ellos usando el procedimiento de dos pasos siguiente:
    
    En primer lugar, mueva sobre un registro que quiera quitar, seleccione **eliminar**.
    
    ![Pase el mouse y seleccione eliminar](../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    En segundo lugar, seleccione **sí** para confirmar cada eliminación. 
    
    ![Seleccione Sí para confirmar la eliminación.](../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    Repita este proceso hasta que haya eliminado todos los registros MX excepto el que haya agregado anteriormente en este procedimiento.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Agregar los registros CNAME necesarios para Office 365
<a name="BKMK_add_CNAME"> </a>

Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.
    
    ![Iniciar sesión](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. En **administre sus dominios**, seleccione el nombre del dominio que desea editar.
    
    ![Seleccionar un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Seleccione la pestaña **DNS** . 
    
    ![Seleccione la pestaña DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Agregue el primero de los seis registros CNAME.
    
    Seleccione **Agregar nuevo**.
    
    ![Seleccione Agregar nuevo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. En los cuadros vacíos para el nuevo registro, seleccione **CNAME** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |**Nombre de host**|**Tipo de registro**|**Host de destino**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Escriba (o copie y pegue) los valores DNS](../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. Seleccione **Guardar**.
    
    ![Seleccione Guardar](../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. Con los tres pasos anteriores y con los valores de las otras cinco filas de la tabla, agregue cada uno de los otros cinco registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. 
  
Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.
    
    ![Iniciar sesión](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. En **administre sus dominios**, seleccione el nombre del dominio que desea editar.
    
    ![Seleccionar un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Seleccione la pestaña **DNS** . 
    
    ![Seleccione la pestaña DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Seleccione **Agregar nuevo**.
    
    ![Seleccione Agregar nuevo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    |**Nombre de host**|**Tipo de registro**|**Valor**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.           |
   
    ![Escriba (o copie y pegue) los valores DNS](../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. Seleccione **Guardar**.
    
    ![Seleccione Guardar](../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Agregar los dos registros SRV necesarios para Office 365
<a name="BKMK_add_SRV"> </a>

Siga los pasos siguientes o [vea el vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para empezar, vaya a la página dominios en Hover mediante [este vínculo](https://www.hover.com/domains). Se le pedirá que inicie sesión.
    
    ![Iniciar sesión](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. En **administre sus dominios**, seleccione el nombre del dominio que desea editar.
    
    ![Seleccionar un dominio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Seleccione la pestaña **DNS** . 
    
    ![Seleccione la pestaña DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Agregue el primero de los dos registros SRV.
    
    Seleccione **Agregar nuevo**.
    
    ![Seleccione Agregar nuevo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. En los cuadros vacíos para el nuevo registro, seleccione **SRV** para el **Tipo de registro** y, a continuación, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |**Nombre de host**|**Tipo de registro**|**Prioridad**|**Peso**|**Puerto**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Escriba (o copie y pegue) los valores DNS](../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. Seleccione **Guardar**.
    
    ![Seleccione Guardar](../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. Con los tres pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.
    
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
