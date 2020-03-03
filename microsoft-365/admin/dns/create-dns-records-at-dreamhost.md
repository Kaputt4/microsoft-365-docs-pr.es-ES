---
title: Crear registros DNS en Dreamhost para Office 365
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
ms.assetid: 9c0812e0-908b-4b41-a64b-77f0dbd3db7a
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Dreamhost para Office 365.
ms.openlocfilehash: 201452bc68f82138c08e2054452747a900ed0e6b
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42349491"
---
# <a name="create-dns-records-at-dreamhost-for-office-365"></a>Crear registros DNS en Dreamhost para Office 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si DreamHost es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync, etc.
 
Después de agregar estos registros a DreamHost, su dominio estará configurado para trabajar con los servicios de Office 365.
  
Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/). Se le pedirá que inicie sesión.
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. En la página **Panel** , seleccione **dominios**y, a continuación, **administrar dominios**.
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar. 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. In the **Add a custom DNS record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**Valor**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |(Este campo es opcional).  <br/> |
   
   ![Dreamhost-BP-Verify-1-1](../../media/ed4a7d43-eeeb-4ec8-849c-37f81315dc69.png)
  
5. Seleccione **Agregar registro ahora.**
    
    ![Dreamhost-BP-Verify-1-2](../../media/5b89c89b-3a8e-4624-895a-86f3cc4638f6.png)
  
6. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.
  
Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
    
  
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
    
  
4. En la página**verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365
<a name="BKMK_add_MX"> </a>

Siga estos pasos.
  
1. Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/). Se le pedirá que inicie sesión.
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. En la página **Panel** , seleccione **correo**y, a continuación, **Custom mx**.
    
    ![Dreamhost-BP-configure-2-1](../../media/58478679-4018-49cc-9d83-371dc5fa4a22.png)
  
3. En la sección **administrar la entrega de correo** , en la columna **acciones** , seleccione **Editar** en el dominio que quiera editar. 
    
    ![Dreamhost-BP-configure-2-2](../../media/6eed0be2-6477-4f49-9f90-39e190499a53.png)
  
4. En la sección **registro MX personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores siguientes de la tabla siguiente. 
    
    (You may have to scroll down.)
    
    (Si hay otros registros MX, marque los registros que se van a eliminar).
    
    |**Registro MX (obligatorio)**|
    |:-----|
    |0  *\<clave-de-dominio\>*  .mail.protection.outlook.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> El 0 es el valor de prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  <br/> **Nota:** Obtenga la * \<clave\> de dominio* de su cuenta de Office 365.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Dreamhost-BP-configure-2-3](../../media/90da1816-e186-4016-ab22-7962f8b86add.png)
  
5. Seleccione **cambiar este dominio para usar registros MX personalizados ahora.**
    
    ![Dreamhost-BP-configure-2-4](../../media/3221c767-83d3-4f30-9d08-dc998772d2a3.png)
  
6. Si hay otros registros MX, elimine cada uno de ellos seleccionando la entrada y, después, presionando la tecla **suprimir** en el teclado. 
    
    ![Dreamhost-BP-configure-2-5](../../media/1827733c-3609-4b0f-bba1-531ab090da91.png)
  
7. Si ha eliminado algún registro, seleccione **actualizar los registros MX personalizados ahora.**
    
    ![Dreamhost-BP-configure-2-6](../../media/177462be-0686-47b7-a389-025dfc8d6526.png)

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Agregar los seis registros CNAME necesarios para Office 365
<a name="BKMK_add_CNAME"> </a>

Siga estos pasos.
  
1. Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/). Se le pedirá que inicie sesión.
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. En la página **Panel** , seleccione **dominios**y, a continuación, **administrar dominios**.
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar. 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**Valor**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |(Este campo es opcional).  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |(Este campo es opcional).  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |(Este campo es opcional).  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |(Este campo es opcional).  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |(Este campo es opcional).  <br/> |
   
    ![Dreamhost-BP-configure-3-1](../../media/0c4cc587-ea24-47f2-8dc6-a35735b250e6.png)
  
5. Seleccione **Agregar registro ahora.**
    
    ![Dreamhost-BP-configure-3-2](../../media/b5d4f939-de6d-4d1f-a20a-4eb5fe715281.png)
  
6. Con los dos pasos anteriores y los valores de las otras cinco filas de la tabla, agregue cada uno de los otros cinco registros CNAME.

  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores.
  
Siga estos pasos.
  
1. Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/). Se le pedirá que inicie sesión.
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. En la página **Panel** , seleccione **dominios**y, a continuación, **administrar dominios**.
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar. 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**Valor**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |(Este campo es opcional).  <br/> |
   
   ![Dreamhost-BP-configure-4-1](../../media/cbc4bbca-bdbc-4dc9-b1b7-b55491eb1e53.png)
  
5. Seleccione **Agregar registro ahora.**
    
    ![Dreamhost-BP-configure-4-2](../../media/2bd7cae8-1fbc-4407-8dfa-06ce37c586c0.png)
  
6. Con los dos pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.
    
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Agregar los dos registros SRV necesarios para Office 365
<a name="BKMK_add_SRV"> </a>

Siga estos pasos.
  
1. Para empezar, vaya a su página de dominios en DreamHost a través de [este vínculo](https://panel.dreamhost.com/). Se le pedirá que inicie sesión.
    
    ![Dreamhost-BP-configure-1-1](../../media/1919b810-b6ba-4e29-a774-de1e7c67d078.png)
  
2. En la página **Panel** , seleccione **dominios**y, a continuación, **administrar dominios**.
    
    ![Dreamhost-BP-configure-1-2](../../media/ab05c16a-79f6-491f-ad07-9a2e6674671d.png)
  
3. En la página **administrar dominios** , en la sección **dominio** , seleccione **DNS** para el dominio que quiera editar. 
    
    ![Dreamhost-BP-configure-1-3](../../media/1a8723a0-54bc-40ff-bc30-5fc3e8cd219b.png)
  
4. En la sección **Agregar un registro DNS personalizado** , en los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila en la tabla siguiente. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**Valor**|**Comment**|
    |:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |SRV  <br/> |100 1 443  <br/> sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |(Este campo es opcional).  <br/> |
    |_sipfederationtls. _tcp  <br/> |SRV  <br/> |100 1 5061  <br/> sipfed.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |(Este campo es opcional).  <br/> |
   
    ![Dreamhost-BP-configure-5-1](../../media/934eb79f-3617-4b72-802c-c42c7d165283.png)
  
5. Seleccione **Agregar registro ahora**.
    
    ![Dreamhost-BP-configure-5-2](../../media/015bc73c-8f88-49ce-87f9-e5a6ea3e10a8.png)
  
6. Con los dos pasos anteriores y los valores de la segunda fila de la tabla, agregue el otro registro SRV.
    
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
