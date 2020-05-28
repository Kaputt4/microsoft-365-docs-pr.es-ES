---
title: Crear registros DNS en dominios locos para Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Aprenda a comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en dominios locos para Microsoft.
ms.openlocfilehash: af154db43f486f71443497180fe64cff89e11b5f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400538"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a>Crear registros DNS en dominios locos para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si Crazy Domains es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
  
Después de agregar estos registros a otros dominios, el dominio estará configurado para trabajar con los servicios de Microsoft.
  

  
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. En la sección **mi cuenta** , seleccione **dominios**.
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar. 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. En la sección **configuración DNS** , seleccione el icono de la lista desplegable. 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Seleccione **Agregar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Elija **Registro TXT** en la lista desplegable **Agregar registro**. 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. Elija **Agregar**.
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.
    
    |**Subdominio**|**Registro de texto**|
    |:-----|:-----|
    |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. Seleccione **Actualizar**.
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
    
  
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
    
  
4. En la página**verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="BKMK_add_MX"> </a>

1. Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. En la sección **mi cuenta** , seleccione **dominios**.
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar. 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. En la sección **configuración DNS** , seleccione el icono de la lista desplegable. 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Seleccione **Agregar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Elija **Registro MX** en la lista desplegable **Agregar registro:**. 
    
    ![CrazyDomains-BP-configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. Elija **Agregar**.
    
    ![CrazyDomains-BP-configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.
    
    (Elija el valor **prioridad** de la lista desplegable). 
    
    |**Correo por zona**|**Prioridad**|**Asignado a un servidor**|
    |:-----|:-----|:-----|
    |(Deje este campo en blanco).  <br/> |1   <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/> **Nota:** Obtén tu *\<domain-key\>* cuenta de Microsoft.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. Seleccione **Actualizar**.
    
    ![CrazyDomains-BP-configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. Si hay otros registros MX enumerados en la sección **registro MX** , seleccione **modificar** para uno de esos registros. 
    
    ![CrazyDomains-BP-configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. Seleccione **Eliminar**.
    
    ![CrazyDomains-BP-configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. Seleccione **Actualizar** para confirmar la eliminación. 
    
    ![CrazyDomains-BP-configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. Use el mismo proceso para quitar cualquier otro registro MX de la lista, hasta que solo quede el que ha agregado anteriormente en este procedimiento.
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Agregar los seis registros CNAME necesarios para Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. En la sección **mi cuenta** , seleccione **dominios**.
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar. 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. En la sección **configuración DNS** , seleccione el icono de la lista desplegable. 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Seleccione **Agregar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Elija **Registro CNAME** en la lista desplegable **Agregar registro:**. 
    
    ![CrazyDomains-BP-configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. Elija **Agregar**.
    
    ![CrazyDomains-BP-configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. Agregue el primero de los seis registros CNAME.
    
    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |**Subdominio**|**Alias para**|
    |:-----|:-----|
    |autodescubrir  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |EnterpriseEnrollment-s.manage.microsoft.com  <br/> |
   
    ![CrazyDomains-BP-configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. Seleccione **Agregar registro CNAME**.
    
    ![CrazyDomains-BP-configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. Agregue el segundo registro CNAME.
    
    En los cuadros para el nuevo registro, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar registro CNAME**.
    
    Repita este proceso hasta crear los seis registros CNAME.
    
11. Seleccione **Actualizar** para guardar los cambios. 
    
    ![CrazyDomains-BP-configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores. 
  
1. Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. En la sección **mi cuenta** , seleccione **dominios**.
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar. 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. En la sección **configuración DNS** , seleccione el icono de la lista desplegable. 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Seleccione **Agregar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Elija **Registro TXT** en la lista desplegable **Agregar registro:**. 
    
    ![CrazyDomains-BP-configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. Elija **Agregar**.
    
    ![CrazyDomains-BP-configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. En los cuadros para el nuevo registro, escriba o pegue los valores de la tabla siguiente.
    
    |**Subdominio**|**Registro de texto**|
    |:-----|:-----|
    |(Deje este campo en blanco).  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
   
    ![CrazyDomains-BP-configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. Seleccione **Actualizar**.
    
    ![CrazyDomains-BP-configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para comenzar, vaya a la página de dominios de Crazy Domains a través de [este vínculo](https://manage.crazydomains.com/members/domains/). Se le pedirá que primero inicie sesión.
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. En la sección **mi cuenta** , seleccione **dominios**.
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. En la página **nombres de dominio** , en la sección **dominio** , seleccione el nombre del dominio que quiera actualizar. 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. En la sección **configuración DNS** , seleccione el icono de la lista desplegable. 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Seleccione **Agregar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Elija **Registro SRV** en la lista desplegable **Agregar registro:**. 
    
    ![CrazyDomains-BP-configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. Elija **Agregar**.
    
    ![CrazyDomains-BP-configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. Agregue el primero de los dos registros SRV.
    
    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |**Tipo de registro**|**Subdominio**|**Prioridad**|**Grosor**|**Puerto**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |Registro SRV  <br/> |_sip. _tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |Registro SRV  <br/> |_sipfederationtls. _tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![CrazyDomains-BP-configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. Seleccione **Agregar registro SRV**.
    
    ![CrazyDomains-BP-configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. Agregue el otro registro SRV.
    
    En los cuadros del nuevo registro, use los valores de la segunda fila de la tabla.
    
11. Seleccione **Actualizar** para guardar los cambios. 
    
    ![CrazyDomains-BP-configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
