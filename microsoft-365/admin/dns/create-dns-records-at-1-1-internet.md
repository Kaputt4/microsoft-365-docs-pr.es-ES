---
title: Crear registros DNS en 1&1 IONOS para Microsoft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en 1&1 IONOS para Microsoft.
ms.openlocfilehash: 1c32e15be8bfdf9ea29647af511d0f8ff0ac0b57
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049148"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Crear registros DNS en 1&1 IONOS para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
> [!CAUTION]
> Tenga en cuenta que 1&1 IONOS no permite que un dominio tenga un registro MX y un registro CNAME de detección automática de nivel superior. Esto limita las formas en que puede configurar Exchange Online para Microsoft. Hay una solución alternativa, pero le recomendamos que la emplee **solo** si ya tiene experiencia con la creación de subdominios en 1&1 IONOS. > si, a pesar de esta [limitación del servicio](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) , elige administrar sus propios registros DNS de Microsoft en 1&1 IONOS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online, etc. 
  
Después de agregar estos registros a la 1&1 IONOS, su dominio estará configurado para trabajar con los servicios de Microsoft.
  
  
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
Siga los pasos siguientes o [vea el vídeo (empieza en 0:42)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
1. Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/). You'll be prompted to log in.
    
2. Seleccione **administrar dominios**.
    
3. En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.
    
4. En el área **configuración del dominio** , seleccione **Editar configuración DNS**.
    
5. En la sección **registros txt y SRV** , seleccione **Agregar registro**.
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Tipo** <br/> |**Prefijo** <br/> |**Valor de nombre** <br/> |
    |TXT  <br/> |(Deje este campo en blanco)  <br/> |MS=ms *XXXXXXXX*  <br/> Nota: este es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Haga clic en **Guardar**.
    
8. Vuelva a seleccionar **Guardar** . 
    
9. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.
    
10. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
4. En la página**Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="BKMK_add_MX"> </a>

Siga los pasos siguientes o [vea el vídeo (empieza en 3:22)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/). You'll be prompted to log in.
    
2. Seleccione **administrar dominios**.
    
3. En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.
    
4. En el área **configuración del dominio** , seleccione **Editar configuración DNS**.
    
5. En la sección **registros MX** , en el área **intercambiador de correo (registro MX)** , seleccione **otro servidor de correo**.<br/>(You may have to scroll down.)<br/>![1&amp;1-BP-configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. Si ya aparecen registros MX en la lista, elimínelos seleccionando el registro y, después, presionando la tecla **Eliminar** del teclado.<br/>(Si no hay ningún registro MX en la lista, continúe con el paso siguiente).<br/>![1&amp;1-BP-configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. En los cuadros para el registro **MX 1**, escriba o copie y pegue los valores de la tabla siguiente. 
    
    |**MX 1**|**Prioridad**|
    |:-----|:-----|
    | *\< clave-de-dominio \>*  . mail.protection.outlook.com      <br/>  Nota: Obtén la \<clave\> de dominio de tu cuenta de Microsoft. [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | 
    
    ![1 y 1-configurar 2 y 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. Haga clic en **Guardar**.<br/>(You may have to scroll down.)<br/>![1&amp;1-BP-configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.<br/>![Selección de sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Agregar los seis registros CNAME necesarios para Microsoft
<a name="BKMK_add_CNAME"> </a>

1&1 IONOS requiere una solución alternativa para que pueda usar un registro MX junto con los registros CNAME necesarios para los servicios de correo electrónico de Microsoft. Para solucionar este problema, es necesario crear un conjunto de subdominios en 1&1 IONOS y asignarlos a registros CNAME.
  
> [!IMPORTANT]
> Asegúrese de que tiene al menos dos subdominios disponibles antes de iniciar este procedimiento. Le recomendamos esta solución solo si ya tiene experiencia con la creación de subdominios en 1&1 IONOS. 
  
### <a name="basic-cname-records"></a>Registros CNAME básicos

Siga los pasos siguientes o [vea el vídeo (empieza en 3:57)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/). You'll be prompted to log in.
    
2. Seleccione **administrar dominios**.
    
3. En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione **administrar subdominios**.<br/>![1&amp;1-BP-configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>Ahora podrá crear dos subdominios y establecer un valor **Alias** para cada uno.<br/>(Esto es necesario porque 1&1 IONOS admite solo un registro CNAME de nivel superior, pero Microsoft requiere varios registros CNAME).<br/>En primer lugar, debe crear el subdominio Autodiscover.
    
4. En la sección **información general de subdominio** , seleccione **crear subdominio**.
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).

    |**Crear subdominio**|**Alias**|
    |:-----|:-----|
    |autodescubrir  <br/> |autodiscover.outlook.com   | 

    ![1&amp;1-BP-configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. Seleccione **crear subdominio**.<br/>![1&amp;1-BP-configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. En la sección **información general de subdominio** , localice el subdominio **Autodiscover** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio. <br/>![1&amp;1-BP-configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. En el área **configuración de subdominio** , seleccione **Editar configuración DNS**. <br/>![1&amp;1-BP-configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. En la sección **registros A/AAAA (direcciones IP)** , en el área **dirección IP (registro A)** , seleccione **CNAME**.<br/>![1&amp;1-BP-configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente.<br/> 
    
    |**Crear subdominio**|**Alias**|
    |:-----|:-----|
    |autodescubrir  <br/> |autodiscover.outlook.com   |

    ![1&amp;1-BP-configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. Active la casilla del aviso de declinación de responsabilidades **Soy consciente**.<br/>![1&amp;1-BP-configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. Haga clic en **Guardar**.<br/>![1&amp;1-BP-configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>Registros CNAME adicionales

Los registros CNAME adicionales creados con el procedimiento siguiente habilitan servicios Skype Empresarial Online. Repetirá los mismos pasos que siguió para crear los dos registros anteriores CNAME.
  
1. Cree el tercer subdominio (Lyncdiscover).<br/>En la sección **información general de subdominio** , seleccione **crear subdominio**.
    
2. En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).<br/> 
    
    |**Crear subdominio**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. Seleccione **crear subdominio**.
    
4. En la página **centro de dominios** , seleccione **administrar subdominios**.
    
5. En la sección **información general de subdominio** , busque el subdominio **lyncdiscover** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio. <br/>En el área **configuración de subdominio** , seleccione **Editar configuración DNS**.
    
6. En la sección **registros A/AAAA (direcciones IP)** , en el área **dirección IP (registro A)** , seleccione **CNAME**.
    
7. En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente. <br/>
    
    |**Crear subdominio**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. Active la casilla de verificación **I-Aware** declinación de responsabilidades y, después, seleccione **Guardar**.
    
9. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.
    
10. Crear el cuarto subdominio (SIP): <br/>En la sección **información general de subdominio** , seleccione **crear subdominio**.
    
11. En el cuadro **Crear subdominio** del nuevo subdominio, escriba o copie y pegue solo el valor **Crear subdominio** de la tabla siguiente. (Agregará el valor **Alias** en un paso posterior).<br/>
    
    |**Crear subdominio**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. Seleccione **crear subdominio**.
    
13. En la página **centro de dominios** , seleccione **administrar subdominios**.
    
14. En la sección **información general de subdominio** , busque el subdominio **SIP** que acaba de crear y, a continuación, seleccione el control **Panel (v)** para ese subdominio. <br/>En el área **configuración de subdominio** , seleccione **Editar configuración DNS**.
    
15. En la sección **registros A/AAAA (direcciones IP)** , en el área **dirección IP (registro A)** , seleccione **CNAME**.
    
16. En el cuadro de diálogo **Alias:**, escriba o copie y pegue solo el valor **Alias** de la tabla siguiente. 
    
    |**Crear subdominio**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. Active la casilla de verificación **I-Aware** declinación de responsabilidades y, después, seleccione **Guardar**.
    
18. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.
    
### <a name="cname-records-needed-for-mdm"></a>Registros CNAME necesarios para MDM

> [!IMPORTANT]
> Siga el procedimiento que ha usado para los otros cuatro registros CNAME, pero proporcione los valores de la tabla siguiente. 
  
|**Crear subdominio**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a evitar el correo no deseado

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records). Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md). 
  
Siga los pasos siguientes o [vea el vídeo (empieza en 5:09)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/). You'll be prompted to log in.
    
2. Seleccione **administrar dominios**.
    
3. En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** (**v**) para ese dominio.
    
4. En el área **configuración del dominio** , seleccione **Editar configuración DNS**.
    
5. En la sección **registros txt y SRV** , seleccione **Agregar registro**. <br/>(You may have to scroll down.)
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. <br/>(Choose the **Type** value from the drop-down list.) <br/>
    
    |**Type**|**Prefijo**|**Valor de nombre**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           | 
    
    ![Registro TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. Haga clic en **Guardar**.<br/>![Agregar registro](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. Haga clic en **Guardar**.<br/>![Guardar registro](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.<br/>![Selección de sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft

Siga los pasos siguientes o [vea el vídeo (empieza en 5:51)](https://docs.microsoft.com/microsoft-365/admin/dns/create-dns-records-at-1-1-internet).
  
> [!NOTE]
> Si se ha registrado con 1und1.de, [inicie sesión aquí](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://my.1and1.com/). You'll be prompted to log in.
    
2. Seleccione **administrar dominios**.
    
3. En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.
    
4. En el área **configuración del dominio** , seleccione **Editar configuración DNS**.
    
5. En la sección **registros txt y SRV** , seleccione **Agregar registro**.
    
6. Agregue el primero de los dos registros SRV.<br/>En el área **Agregar registro**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores que aparecen en la primera fila de la tabla siguiente. <br/>(Seleccione los valores **tipo** y **TTL** que se muestran en la lista desplegable). 
    
    |**Tipo**|**Servicio**|**Protocolo**|**Nombre**|**Host**|**Prioridad**|**Grosor**|**Puerto**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |_tls  <br/> |(Leave this field empty.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (1 h)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(Deje este campo en blanco).  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (1 h)  <br/> |  
    
    ![1&amp;1-BP-configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. Haga clic en **Guardar**. <br/>![1&amp;1-BP-configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. Haga clic en **Guardar**. <br/>![1&amp;1-BP-configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**. <br/>![Selección de sí en el cuadro de diálogo Editar configuración DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. Agregue el otro registro SRV. <br/>En la sección **registros txt y SRV** , seleccione **Agregar registro**. <br/>En el área **Agregar registro** , cree un registro con los valores de la otra fila de la tabla y, a continuación, vuelva a seleccionar **Agregar**, **Guardar**y **sí** para completar el registro. 
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
