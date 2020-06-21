---
title: Crear registros DNS en Register.com para Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Register.com para Microsoft.
ms.openlocfilehash: 7a11fa248f2602eb02fe1242234d26584bd33fd2
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780330"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>Crear registros DNS en Register.com para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si Register.com es su proveedor de host DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.
  
Estos son los registros principales que agregar. Siga los pasos siguientes o [vea el vídeo](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
- [Agregar un registro TXT en Register.com para comprobar que es el propietario del dominio](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Agregar los registros CNAME necesarios para Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [Agregar los dos registros SRV necesarios para Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Después de agregar estos registros a Register.com, su dominio estará configurado para funcionar con los servicios de Microsoft.
  

  
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Agregar un registro TXT en Register.com para comprobar que es el propietario del dominio
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Siga los pasos siguientes o [vea el vídeo (empieza en 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.
    
2. Seleccione **Dominios**.
    
3. Seleccione **administrar**.
    
4. Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.
    
5. Desplácese hacia abajo hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros txt (SPF)**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Seleccione **continuar**.
    
8. En la página siguiente, seleccione **continuar** de nuevo para confirmar los cambios. 
    
9. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
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

Siga los pasos siguientes o [vea el vídeo (empieza en 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.
    
2. Seleccione **Dominios**.
    
3. Seleccione **administrar**.
    
4. Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.
    
5. Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros de intercambio de correo**.
    
    ![Seleccionar Editar registros de intercambio de correo](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.
    
    (Elija el valor **prioridad** de la lista desplegable). 
    
    |****Nombre de host****|****Prioridad****|****Servidor de correo****|
    |:-----|:-----|:-----|
    |@  <br/> |Máximo  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*. mail.protection.outlook.com  <br/>  <br/>**Nota:** Obtén tu \<*domain-key*\> cuenta de Microsoft. <br> [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copie y pegue el valor de la tabla](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. Si se muestran otros registros MX en la lista, seleccione todos los registros que quiera eliminar.
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. Seleccione **continuar**.
    
    ![Seleccione continuar.](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios. 
    
    ![Seleccione continuar.](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Agregar los registros CNAME necesarios para Microsoft
<a name="BKMK_add_CNAME"> </a>

Siga los pasos siguientes o [vea el vídeo (empieza en 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.
    
2. Seleccione **Dominios**.
    
3. Seleccione **administrar**.
    
4. Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.
    
5. Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros de alias de dominio**.
    
    ![Seleccione Editar registros de alias de dominio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. Seleccione **Agregar más alias de dominio**.
    
    ![Seleccione Agregar alias de dominios](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. Agregar los registros CNAME necesarios.
    
    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    |****Primer campo (sin etiqueta)****|****Señala a****|
    |:-----|:-----|
    |autodescubrir  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |EnterpriseEnrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![Copiar y pegar los valores DNS de la tabla](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. Una vez que haya agregado todos los registros CNAME que necesita, seleccione **continuar**.
    
    ![Seleccione continuar.](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios. 
    
    ![Seleccione continuar.](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En vez de eso, agregue los valores necesarios de Microsoft para el registro actual, de modo que solo tenga un único registro de SPF que incluya ambos conjuntos de valores.  
  
Siga los pasos siguientes o [vea el vídeo (empieza en 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. Para empezar, vaya a su página de dominios en Register.com a través de [este vínculo](https://www.register.com/myaccount/). Se le pedirá que inicie sesión en primer lugar.
    
2. Seleccione **Dominios**.
    
3. Seleccione **administrar**.
    
4. Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.
    
5. Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros txt (SPF)**.
    
    ![Seleccionar Editar registros TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.
    
    |****Nombre de host****|****Registro TXT****|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.  |
   
     ![Copiar y pegar los valores de la tabla](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. Seleccione **continuar**.
    
    ![Seleccione continuar.](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios. 
    
    ![Seleccione continuar.](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="BKMK_add_SRV"> </a>

Siga los pasos siguientes o [vea el vídeo (empieza en 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).
  
1. To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.
    
2. Seleccione **Dominios**.
    
3. Seleccione **administrar**.
    
4. Busque la fila que contiene el nombre del dominio que desea modificar; y, a continuación, en esa fila, seleccione **administrar**.
    
5. Desplácese hasta la sección **configuración técnica avanzada** y, a continuación, seleccione **Editar registros SRV**.
    
    ![Seleccionar Editar registros SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. Agregue el primero de los dos registros SRV:
    
    En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.
    
    (Elija el valor **prioridad** de la lista desplegable). 
    
    |****Servicio****|****Puerto****|****Nombre****|****Prioridad****|****Grosor****|****Puerto****|****Destino****|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |Máximo  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |Máximo  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![Copiar y pegar los valores de la tabla](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. Seleccione **Agregar más registros SRV**.
    
    ![Seleccione Agregar más registros SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. Agregue el segundo registro SRV:
    
    Copie y pegue los valores de la segunda fila de la tabla anterior en los cuadros para el segundo registro.
    
9. Una vez que haya agregado los dos registros SRV, seleccione **continuar**.
    
    ![Seleccione continuar.](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. En la página siguiente, seleccione **continuar** de nuevo para confirmar y guardar los cambios. 
    
    ![Seleccione continuar.](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
