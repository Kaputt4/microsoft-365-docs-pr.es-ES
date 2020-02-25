---
title: Crear registros DNS en Freenom para Office 365
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Freenom para Office 365.
ms.openlocfilehash: a1396964c7dc9c279589a6020e0c741fd0cb29d5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248972"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a>Crear registros DNS en Freenom para Office 365

[Consulte preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md) si no encuentra lo que está buscando. 
  
> [!CAUTION]
> El sitio web de Freenom no admite los registros SRV, lo que significa que no funcionarán varias características de Skype empresarial online y Outlook Web App. Independientemente del plan de Office 365 que use, hay importantes limitaciones de servicio y es posible que quiera cambiar a un proveedor de host DNS diferente. 
  
Si a pesar de las limitaciones del servicio, elige administrar sus propios registros DNS de Office 365 en Freenom, siga los pasos descritos en este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico y otros servicios.
  
Para obtener información acerca del hospedaje web y de DNS para sitios web con Office 365, consulte [Usar un sitio web público con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="bkmk_txt"> </a>

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en Freenom a través de [este vínculo](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Inicio de sesión de Freenom](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Seleccione **servicios**y, a continuación, seleccione **mis dominios**.
    
    ![Freenom seleccionar servicios y mis dominios](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. En el dominio que quiera editar, seleccione **administrar dominio**.
    
    ![Freenom seleccione administrar dominio](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Seleccione **administrar DNS de Freenom**.
    
    ![Freenom administrar Freenom DNS](../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. En **Agregar registro**, en la columna **tipo** , elija **txt** en el menú. 
    
    ![Freenom agregar tipo de registro TXT](../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. In the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Name**|**Type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(se deja en blanco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |MS = msXXXXXXXX  <br/> **Nota:** Este es un ejemplo. Utilice aquí su valor de **Dirección o puntos de destino**, de la tabla de Office 365.           [¿Cómo puedo encontrarlo?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Valores de Freenom TXT para verificación](../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Seleccione **Guardar cambios**.
    
    ![Registro TXT Freenom guardar cambios](../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a> .

    
2. En la página **dominios** , seleccione el dominio que desea comprobar. 
    
    
  
3. En la página **configuración** , seleccione **Iniciar configuración**.
    
    
  
4. En la página **comprobar dominio** , seleccione **comprobar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Office 365
<a name="bkmk_mx"> </a>

1. Para empezar, vaya a su página de dominios en Freenom a través de [este vínculo](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Inicio de sesión de Freenom](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Seleccione **servicios**y, a continuación, seleccione **mis dominios**.
    
    ![Freenom seleccionar servicios y mis dominios](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. En el dominio que quiera editar, seleccione **administrar dominio**.
    
    ![Freenom seleccione administrar dominio](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Establezca el nombre para el dominio en los servidores de nombres Freenom predeterminados. Seleccione **herramientas de administración**y, a continuación, seleccione **servidores de nombres**.
    
    ![Configuración de los servidores de nombres Freenom](../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Asegúrese de que la opción **usar servidores de nombres predeterminados** está seleccionada y, después, seleccione **Cambiar servidores de nombres**.
    
    ![Cambiar los servidores de nombres de Freenom](../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Seleccione **administrar DNS de Freenom**.
    
    ![Freenom seleccionar administrar Freenom DNS](../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. En **Agregar registro**, en la columna **tipo** , elija **mx** en el menú. 
    
    ![Freenom agregar tipo de registro MX](../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. 
    
    |**Name**|**Type**|**TTL**|**Target**|**Prioridad**|
    |:-----|:-----|:-----|:-----|:-----|
    |(se deja en blanco)  <br/> |MX (intercambiador de correo)  <br/> |3600 (segundos)  <br/> |\<Domain-Key\>. mail.Protection.Outlook.com  <br/> **Nota:** Obtenga la * \<clave\> de dominio* de su cuenta de Office 365.   [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9) <br/> |
   
   ![Registro MX de Freenom](../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Seleccione **Guardar cambios**.
    
    ![Guardar cambios del registro MX de Freenom](../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Si hay otros registros MX, elimínelos todos. Para cada registro, seleccione **eliminar**. Si el mensaje **realmente desea quitar esta entrada** , seleccione **Aceptar**.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Agregar los registros CNAME necesarios para Office 365
<a name="bkmk_cname"> </a>

1. Para empezar, vaya a su página de dominios en Freenom a través de [este vínculo](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Inicio de sesión de Freenom](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Seleccione **servicios**y, a continuación, seleccione **mis dominios**.
    
    ![Freenom seleccionar servicios y mis dominios](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. En el dominio que quiera editar, seleccione **administrar dominio**.
    
    ![Freenom seleccione administrar dominio](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Seleccione **administrar DNS de Freenom**.
    
    ![Freenom seleccionar administrar Freenom DNS](../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. En **Agregar registro**, en la columna **tipo** , elija **CNAME** en el menú. 
    
    ![Freenom agregar tipo de registro CNAME](../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Cree el primer registro CNAME. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente. 
    
    |**Nombre**|**Tipo de registro**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Valores CNAME de Freenom](../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Seleccione **Guardar cambios**.
    
    ![Guardar los cambios de Freenom CNAME](../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Repita los pasos anteriores para crear los otros cinco registros CNAME. 
    
    Para cada registro, escriba (o copie y pegue) los valores de la siguiente fila de la tabla anterior en los cuadros para ese registro.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. En vez de eso, agregue los valores necesarios de Office 365 para el registro actual, de modo que solo tenga un  *único*  registro de SPF que incluya ambos conjuntos de valores. 

1. Para empezar, vaya a su página de dominios en Freenom a través de [este vínculo](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Inicio de sesión de Freenom](../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Seleccione **servicios**y, a continuación, seleccione **mis dominios**.
    
    ![Freenom seleccionar servicios y mis dominios](../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. En el dominio que quiera editar, seleccione **administrar dominio**.
    
    ![Freenom seleccione administrar dominio](../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Seleccione **administrar DNS de Freenom**.
    
    ![Freenom seleccionar administrar Freenom DNS](../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. En **Agregar registro**, en la columna **tipo** , elija **txt** en el menú. 
    
    ![Freenom agregar tipo de registro TXT](../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**Nombre**|**Tipo de registro**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(se deja en blanco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.           |
   
    ![Valores de Freenom TXT para SPF](../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Seleccione **Guardar cambios**.
    
    ![Freenom registro TXT para cambios de guardado de SPF](../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

