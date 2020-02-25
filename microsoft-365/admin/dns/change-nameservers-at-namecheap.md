---
title: Cambiar los servidores de nombres para configurar Office 365 con namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Aprenda a configurar su dominio personalizado de Office 365 con namecheap si quiere que Office 365 administre sus registros DNS. '
ms.openlocfilehash: caf0a484b82ecf10f2835ae8fd5dea98c16e61c3
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246604"
---
# <a name="change-nameservers-to-set-up-office-365-with-namecheap"></a>Cambiar los servidores de nombres para configurar Office 365 con namecheap

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.
  
Siga estas instrucciones si quiere que Office 365 administre automáticamente los registros DNS de Office 365. (Si lo prefiere, puede [administrar todos los registros DNS de Office 365 en namecheap](create-dns-records-at-namecheap.md)).
  
    
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

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
|TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota**: este es un ejemplo. Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.           [¿Cómo puedo encontrarlo?](../get-help-with-domains/information-for-dns-records.md)          |30 minutos  <br/> |
   
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
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

Para completar la configuración del dominio con Office 365, debe cambiar los registros NS del dominio en su registrador de dominios para que apunten a los servidores DNS primario y secundario de Office 365. Esto configura Office 365 para actualizar los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.
  
> [!CAUTION]
> Si cambia los registros NS del dominio para que apunten a los servidores DNS de Office 365, esto afectará a todos los servicios que estén asociados actualmente con su dominio. Por ejemplo, todos los correos que se envíen a su dominio (como, por ejemplo, rob@ *su_dominio*  .com) comenzarán a llegar a Office 365 después de realizar este cambio. 
  
> [!IMPORTANT]
>  Cuando haya completado los pasos descritos en esta sección, los  *únicos*  servidores DNS que deben aparecer son estos cuatro: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  En el procedimiento siguiente se muestra cómo eliminar cualquier otro servidor de nombres que no desee de la lista y también cómo agregar estos cuatro servidores DNS  *correctos*  , si aún no están en la lista. 
  
1. Para empezar, vaya a su página de dominios en namecheap a través de [este vínculo](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Se le pedirá que inicie sesión y continúe.
    
    ![Namecheap-BP-configure-1-1](../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. En la página de **aterrizaje** , en **cuenta**, elija **lista de dominios** en la lista desplegable. 
    
    ![Namecheap-BP-configure-1-2](../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. En la página **lista de dominios** , busque el nombre del dominio que desea editar y, a continuación, seleccione **administrar**.
    
    ![Namecheap-BP-configure-1-3](../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Seleccione **dominio**.
    
    ![Namecheap-BP-redelegate-1-1](../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. Busque la sección **servidores de nombres** y seleccione **personalizada** en la lista desplegable **namecheap predeterminada** . 
    
    ![Namecheap-BP-redelegate-1-2](../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. Dependiendo de si ya hay o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes.
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Si aún NO se muestran servidores DNS en la lista
<a name="BKMK_ProcedureWithOUT"> </a>

1. Seleccione **Agregar NAMESERVER** dos veces para agregar dos filas nuevas.
    
    ![Namecheap-BP-redelegate-1-3-1](../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. En los cuadros **servidor de nombres** , escriba (o copie y pegue) los valores de la tabla siguiente.
    
|||
|:-----|:-----|
|**Servidor DNS 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor de nombres 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-redelegate-1-3-2](../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. Seleccione el control **Guardar** (marca de verificación). 
    
    ![Namecheap-BP-redelegate-1-5](../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Si ya existen servidores de nombres enumerados

> [!CAUTION]
> Siga estos pasos  *solo*  si tiene servidores de nombres distintos de los cuatro servidores de nombres  *correctos*  . (Es decir, elimine  *solo*  los servidores de nombres actuales que  *no*  sean **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com** ). 
  
1. Si en los cuadros **servidor de nombres** aparecen otros servidores DNS, elimínelos (para hacerlo, selecciónelos y, después, presione la tecla **suprimir** en el teclado). 
    
    ![Namecheap-BP-redelegate-1-4](../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. Seleccione **Agregar NAMESERVER** dos veces para agregar dos filas nuevas. 
    
    ![Namecheap-BP-redelegate-1-3-1](../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. En los cuadros **servidor de nombres** , escriba (o copie y pegue) los valores de la tabla siguiente.
 
    
|||
|:-----|:-----|
|**Servidor DNS 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-redelegate-1-3-2](../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. Seleccione el control **Guardar** (marca de verificación). 
    
    ![Namecheap-BP-redelegate-1-5](../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.