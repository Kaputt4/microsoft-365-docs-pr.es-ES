---
title: Crear registros DNS en Google Domains para Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Obtenga información sobre cómo comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync y otros servicios en Google Domains para Microsoft.
ms.openlocfilehash: 399482374f87d864edbc01feb4896b168d157f7f
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919753"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Crear registros DNS en Google Domains para Microsoft

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Si Google Domains es su proveedor de host DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Lync, etc.
  
Después de agregar estos registros a Google Domains, el dominio estará configurado para funcionar con los servicios de Microsoft.
  
Para obtener información acerca del hospedaje web y de DNS para sitios web con Microsoft, vea [Usar un sitio web público con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación
<a name="BKMK_verify"> </a>

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:
    
1. Seleccione **iniciar sesión**.
    
2. Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.
    
2. En la página **mis dominios** , busque el dominio que desea usar con Microsoft y seleccione el vínculo **administrar** junto a él. En el panel de navegación izquierdo, seleccione **DNS**.
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Type** <br/> |**TTL** <br/> |**Datos** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Elija **Agregar**.
    
5. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
4. En la página**Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft
<a name="BKMK_add_MX"> </a>

1. Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:
    
2. Seleccione **iniciar sesión**.
    
3. Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.
4. En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar.
    
    > [!IMPORTANT]
    > Si tiene una cuenta de correo electrónico de G Suite, primero deberá eliminar los registros MX asociados a esa cuenta. Los registros MX de G Suite le impiden agregar otros registros MX, incluidos los necesarios para Microsoft. Tenga en cuenta que eliminar los registros de G Suite no elimina su cuenta de G Suite. Para eliminar sus registros MX de G Suite, siga los pasos que se muestran a continuación. 
  
5. En la sección **registros sintéticos** , en el área **G Suite** , seleccione **eliminar**.
    
    (You may have to scroll down.)
    
    ![Seleccione eliminar en la sección registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. Seleccione **Eliminar**.
    
    ![Seleccione eliminar.](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**TTL**|**Datos**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<clave-de-dominio\>*  .mail.protection.outlook.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> El valor de **0** se corresponde con la prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  <br/> **Nota:** Obtenga la \<*clave-de-dominio*\> desde su cuenta de Microsoft.  [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)          Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. Seleccione **Agregar**.
    
    ![Seleccione Agregar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. Si hay otros registros MX personalizados, quítelos:
    
1. Seleccione **Editar** en la fila del registro MX. 
    
    ![Seleccione Editar en la fila del registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. Para cada uno de los demás registros MX personalizados, seleccione la entrada en el cuadro **datos** y, después, presione la tecla **suprimir** en el teclado para eliminar ese registro. 
    
    Continúe hasta haber eliminado la entrada **Datos** de cada uno de los demás registros MX. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. Cuando haya eliminado la entrada de **datos** de cada uno de los demás registros MX, seleccione **Guardar** para guardar los cambios. 
    
    ![Seleccione Guardar](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Agregar los cinco registros CNAME necesarios para Microsoft

1. Para empezar, vaya a su página de [Google Domains]https://domains.google.com/registrar) (e inicie sesión.
    
2. En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar. 
    
3. Agregue el primer registro CNAME.
    
    En la sección **Registros de recursos personalizados**, en los cuadros del nuevo registro, escriba o copie y pegue los valores que aparecen en la primera fila de la tabla siguiente. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**TTL**|**Datos**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. Seleccione **Agregar**.
    
    ![Seleccione Agregar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. Agregue los otros cuatro registros CNAME.
    
    En la sección **registros de recursos personalizados** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro). 
    
    Repita este proceso hasta que haya creado todos los registros CNAME necesarios.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En vez de eso, agregue los valores necesarios de Microsoft para el registro actual, de modo que solo tenga un único registro de SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:
    
1. Seleccione **iniciar sesión**.
    
2. Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.
    
3. En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar. 
    
4. En la sección **registros de recursos personalizados** , en la fila registro TXT, seleccione **Editar**. 
    
    > [!IMPORTANT]
    > Google Domains almacena los registros TXT como un conjunto que puede contener varios registros. Cuando tenga como mínimo otro registro TXT (como el registro TXT que usó para comprobar el dominio), necesitará agregar los nuevos registros TXT a ese conjunto de registros. Si intenta agregar otros registros TXT como entradas separadas, se mostrará el mensaje de error **Registro duplicado**. 
  
    ![Seleccione Editar en la fila de registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. Seleccione el control **(+)** . 
    
    ![Seleccionar el control más](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.
    
    (Es posible que tenga que desplazarse hacia abajo).
    
    |**Datos**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > Recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.           
   
   ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. Haga clic en **Guardar**.
    
    ![Seleccione Guardar](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Agregar los dos registros SRV necesarios para Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:
    
2. Seleccione **iniciar sesión**.
    
3. Escriba sus credenciales de inicio de sesión y, después, seleccione **iniciar sesión de**nuevo.
    
4. En la página **dominios** , en la sección **dominio** , seleccione **configurar DNS** para el dominio que desea editar. 
    
5. Agregue el primer registro SRV.
    
    In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Name**|**Type**|**TTL**|**Datos**|
    |:-----|:-----|:-----|:-----|
    |_sip. _tls|SRV|1H|100 1 443 sipdir.online.lync.com. **Este valor debe terminar con un punto (.).** **Nota:** Se recomienda copiar y pegar esta entrada para que todo el espaciado sea correcto.           |
    |_sipfederationtls. _tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**

    Recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.       
   
    ![Escribir o pegar valores en la sección registros de recursos personalizados](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. Seleccione **Agregar**.
    
    ![Seleccione Agregar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. Agregue el otro registro SRV.
    
    En la sección **registros de recursos personalizados** , cree un registro (para hacerlo, use los valores de la segunda fila de la tabla y, después, vuelva a seleccionar **Agregar** para completar ese registro). 
    
    > [!NOTE]
    > Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
