---
title: Cambiar los servidores DNS para configurar Office 365 con Amazon Web Services (AWS)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Descubra cómo puede configurar Office 365 para administrar los registros DNS en Amazon Web Services (AWS). '
ms.openlocfilehash: 9500522478c22277c57772ef64b4d0a4b87e8c44
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352491"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a>Cambiar los servidores DNS para configurar Office 365 con Amazon Web Services (AWS)

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Siga estas instrucciones si quiere que Office 365 administre los registros DNS de Office 365 automáticamente. (Si lo prefiere, puede [administrar todos los registros DNS de Office 365 en AWS](create-dns-records-at-aws.md)).
  
    
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
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
|(Deje este campo en blanco)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **Nota:** esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Simple <br/> |
   
6. Seleccione **Crear**.
    
7. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Office 365 y solicitará que Office 365 lo busque.
  
Cuando Office 365 encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
4. En la página**Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Encontrar y solucionar problemas después de agregar el dominio o registros DNS en Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

Para completar la configuración del dominio con Office 365, debe cambiar los registros NS del dominio en su registrador de dominios para que apunten a los servidores DNS primario y secundario de Office 365. Esto configura Office 365 para actualizar los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.
  
> [!CAUTION]
> Si cambia los registros NS del dominio para que apunten a los servidores DNS de Office 365, esto afectará a todos los servicios que estén asociados actualmente con su dominio. Por ejemplo, todos los correos que se envíen a su dominio (como, por ejemplo, rob@ *su_dominio*  .com) comenzarán a llegar a Office 365 después de realizar este cambio. 
  
> [!IMPORTANT]
>  El siguiente procedimiento le mostrará cómo eliminar cualquier otro de los servidores de nombres no deseados de la lista, y también cómo agregar los servidores de nombres correctos si aún no aparecen. > cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son los cuatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.
    
2. En la página **recursos** , seleccione **zonas hospedadas**.
    
3. En la página **zonas hospedadas** , en la columna **nombre de dominio** , seleccione el nombre del dominio que desea editar. 
    
4. Seleccione el conjunto de registros **Servidor DNS**. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. En el conjunto de registros **NS: servidor de nombres de dominio** del cuadro **Valor**, elimine todos los servidores de nombres al seleccionarlos todos y después presionar la tecla **Supr** en el teclado. 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (Es decir, elimine solo los servidores DNS actuales que *no* tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**). 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. En el área **TTL (segundos):** , seleccione **1H** (1 hora). 
    
    ![Seleccionar 1H para una hora](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. Aún en el conjunto de registros **NS: servidor de nombres**, en el cuadro **Valor**, escriba o copie y pegue el valor **Primera línea** de la tabla siguiente y después presione la tecla **Entrar** en el teclado y escriba o copie y pegue el siguiente valor **línea**. 
    
    > [!IMPORTANT]
    > Cada valor de servidor DNS  *debe*  estar en su propia línea dentro del cuadro **Valor**, como se muestra en la siguiente ilustración. 
  
|||
|:-----|:-----|
|**Primera línea** <br/> |ns1.bdm.microsoftonline.com.  <br/> **This value MUST end with a period (.)** <br/> |
|**Segunda línea** <br/> |ns2.bdm.microsoftonline.com.  <br/> **This value MUST end with a period (.)** <br/> |
|**Tercera línea** <br/> |ns3.bdm.microsoftonline.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |
|**Cuarta línea** <br/> |ns4.bdm.microsoftonline.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |
   
   ![Escriba o pegue el valor de la primera línea en el cuadro valor](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. Seleccione **Guardar conjunto de registros**.
    
    ![Seleccione Guardar conjunto de registros.](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio. 
