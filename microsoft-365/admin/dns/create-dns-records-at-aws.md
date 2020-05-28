---
title: Crear registros DNS en Amazon Web Services (AWS) para Microsoft
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
ms.assetid: 7a2efd75-0771-4897-ba7b-082fe5bfa9da
description: Aprenda a comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype empresarial online y otros servicios en Amazon Web Services (AWS) para Microsoft.
ms.openlocfilehash: fcc4da3a5841e9df2f6edabd540363fe70bb73ad
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400574"
---
# <a name="create-dns-records-at-amazon-web-services-aws-for-microsoft"></a>Crear registros DNS en Amazon Web Services (AWS) para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si AWS es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype online para empresas, etc.
  
Después de agregar estos registros a AWS, el dominio estará configurado para funcionar con los servicios de Microsoft.
  

  
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.
    
2. En la página **recursos** , seleccione **zonas hospedadas**.
    
3. En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar. 
    
4. Seleccione **crear conjunto de registros**.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
    |||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Type** <br/> |**Alias** <br/> |**TTL (segundos)** <br/> |**Valor** <br/> |**Directiva de enrutamiento** <br/> |
    |(Leave this field empty.)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX*  <br/>**Nota:** esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |Simple  <br/> |
   
6. Seleccione **Crear**.
    
7. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
4. En la página**Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>Agregar un registro MX para que el correo electrónico del dominio llegue a Microsoft 365
<a name="BKMK_add_MX"> </a>

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.
    
2. En la página **recursos** , seleccione **zonas hospedadas**.
    
3. En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar. 
    
4. Seleccione **crear conjunto de registros**.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    |**Name**|**Type**|**Alias**|**TTL (segundos)**|**Valor**|**Directiva de enrutamiento**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |(Deje este campo en blanco).  <br/> |MX - Registro de intercambio de correo  <br/> |No  <br/> |300  <br/> |0 *\<domain-key\>* . mail.Protection.Outlook.com.  <br/> El 0 es el valor de prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  <br/> **Este valor DEBE terminar en punto (.).** <br/> **Nota:** Obtenga su \<*domain-key*\> cuenta de Microsoft 365. [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          |Simple  <br/> |
       
    ![AWS-BP-configure-2-1](../../media/94a71ce7-1b3b-4b1a-9ad3-9592db133075.png)
  
6. Seleccione **Crear**.
    
    ![AWS-BP-Configure-2-2](../../media/1c050c72-c04f-48d5-a8e9-44cd83ddd33e.png)
  
7. Si hay otros registros MX, quítelos.
    
    > [!IMPORTANT]
    > AWS almacena registros MX como un conjunto que puede contener varios registros. **No** seleccione **eliminar conjunto de registros**, ya que se eliminarán todos los registros MX, incluido el que acaba de agregar. Use las siguientes instrucciones en su lugar. 
  
    En primer lugar, seleccione el conjunto de registros MX.
    
    ![AWS-BP-Configure-2-3](../../media/9d9388cb-e2d0-43b7-928c-e1d07e519c6f.png)
  
    A continuación, en el área **Editar conjunto de registros**, elimine cada registro MX obsoleto seleccionando la entrada en el cuadro **Valor** y, a continuación, pulse la tecla **Eliminar** de su teclado. 
    
    ![AWS-BP-Configure-2-4](../../media/c3b0c1bc-21ab-44cc-84b7-f504725c5540.png)
  
8. Seleccione **Guardar conjunto de registros**.
    
    ![AWS-BP-Configure-2-5](../../media/86f0998d-f5d4-4750-a93d-ac13b318c40b.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft-365"></a>Agregue los cinco registros CNAME necesarios para Microsoft 365
<a name="BKMK_add_CNAME"> </a>

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.
    
2. En la página **recursos** , seleccione **zonas hospedadas**.
    
3. En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar. 
    
4. Seleccione **crear conjunto de registros**.
    
5. Agregue el primer registro CNAME.
    
    En el área **Agregar conjunto de registros**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores a partir de la primera fila de la tabla siguiente. 
    
    (Seleccione los valores **Tipo** y **Directiva de enrutamiento** que aparecen en las listas desplegables). 
    
    |**Name**|**Type**|**Alias**|**TTL (segundos)**|**Valor**|**Directiva de enrutamiento**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME - nombre canónico  <br/> |No  <br/> |300  <br/> |autodiscover.outlook.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |Simple  <br/> |
    |sip  <br/> |CNAME - nombre canónico  <br/> |No  <br/> |300  <br/> |sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |Simple  <br/> |
    |lyncdiscover  <br/> |CNAME - nombre canónico  <br/> |No  <br/> |300  <br/> |webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |Simple  <br/> |
    |enterpriseregistration  <br/> |CNAME - nombre canónico  <br/> |No  <br/> |300  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |Simple  <br/> |
    |EnterpriseEnrollment  <br/> |CNAME - nombre canónico  <br/> |No  <br/> |300  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |Simple  <br/> |
   
    ![AWS-BP-configure-3-1](../../media/895c71bd-0e3a-425e-9681-98c1c67e714b.png)
  
6. Seleccione **Crear**.
    
    ![AWS-BP-Configure-3-2](../../media/33964846-5282-44a4-b241-62ce02b96735.png)
  
7. Agregue los otros cuatro registros CNAME.
    
    En la página **zonas hospedadas** , seleccione **crear conjunto de registros**, cree un registro con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **crear** para completar ese registro. 
    
    Repita este proceso hasta que haya creado los cinco registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores necesarios de Microsoft al registro activo para que tenga un *único* registro de SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records). Para validar el registro de SPF, puede usar una de estas[herramientas de validación de SPF](../setup/domains-faq.md). 
  
1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.
    
2. En la página **recursos** , seleccione **zonas hospedadas**.
    
3. En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar. 
    
4. Seleccione el conjunto de registros **txt** . 
    
    ![AWS-BP-Configure-4-1](../../media/0310fa66-c016-4987-80df-930f1c8f3c39.png)
  
5. En el área **Editar conjunto de registros**, al final de la entrada actual del cuadro **Valor:** del registro existente, presione ENTRAR en el teclado para crear una línea; luego, en esa línea (en el valor existente), escriba o copie y pegue el valor de la tabla siguiente (puede ver un ejemplo en la ilustración que aparece debajo de la tabla). 
    
    |**Valor:**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> (Las comillas necesarias por las instrucciones en pantalla aparecen automáticamente. No es necesario escribirlas manualmente).  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |
   
    ![AWS-BP-configure-4-2](../../media/beb3c086-eaf8-4245-9860-18512a3ff72e.png)
  
6. Seleccione **Guardar conjunto de registros**.
    
    ![AWS-BP-Configure-4-3](../../media/94b9306c-bdc9-4f84-ad6f-6d12edbfde90.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft-365"></a>Agregue los dos registros SRV necesarios para Microsoft 365
<a name="BKMK_add_SRV"> </a>

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.
    
2. En la página **recursos** , seleccione **zonas hospedadas**.
    
3. En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar. 
    
4. Seleccione **crear conjunto de registros**.
    
5. Agregue el primer registro SRV.
    
    En el área **Agregar conjunto de registros**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores a partir de la primera fila de la tabla siguiente. 
    
    (Seleccione los valores **Tipo** y **Directiva de enrutamiento** que aparecen en las listas desplegables). 
    
    |**Name**|**Type**|**Alias**|**TTL (segundos)**|**Valor**|**Directiva de enrutamiento**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls|SRV - Localizador de servicio|No|300|100 1 443 sipdir.online.lync.com. **Este valor debe terminar con un punto (.).**><br> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |Simple|
    |_sipfederationtls. _tcp|SRV - Localizador de servicio|No|300|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**<br> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           |Simple|
   
    ![AWS-BP-configure-5-1](../../media/c3f841d3-6076-428f-bb04-e71cc5f392fa.png)
  
6. Seleccione **Crear**.
    
    ![AWS-BP-Configure-5-2](../../media/1bf5dc58-a46b-47a5-bd69-7c2147dd4e50.png)
  
7. Para agregar el otro registro SRV:
    
    En la página **zonas hospedadas** , seleccione **crear conjunto de registros**, cree un registro con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **crear** para completar ese registro. 
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
