---
title: Cambiar los servidores de nombres para configurar Microsoft con Amazon Web Services (AWS)
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Obtenga información sobre cómo configurar Microsoft para administrar los registros DNS en Amazon Web Services (AWS). '
ms.openlocfilehash: 4700557c40973ab051cced81c129197a826964ab
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658457"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a>Cambiar los servidores de nombres para configurar Microsoft con Amazon Web Services (AWS)

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted. (Si lo prefiere, puede administrar todos los registros DNS de [Microsoft en AWS).](create-dns-records-at-aws.md)
  
    
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.
    
2. En la **página Recursos,** seleccione **Zonas hospedadas.**
    
3. En la **página Zonas hospedadas,** en la columna **Nombre** de dominio, seleccione el nombre del dominio que desea editar. 
    
4. Seleccione **Crear conjunto de registros.**
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Nombre** <br/> |**Tipo** <br/> |**Alias** <br/> |**TTL (segundos)** <br/> |**Valor** <br/> |**Directiva de enrutamiento** <br/> |
|(Deje este campo vacío)  <br/> |TXT - Text  <br/> |No  <br/> |300  <br/> |MS=ms *XXXXXXXX* <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Simple <br/> |
   
6. Seleccione **Crear**.
    
7. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija **Iniciar configuración**.
    
4. En la página **Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

Para completar la configuración de su dominio con Microsoft, cambie los registros NS de su dominio en el registrador de dominios para que apunten a los servidores de nombres principales y secundarios de Microsoft. Esto configura Microsoft para que actualice automáticamente los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.
  
> [!CAUTION]
> Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft, se verán afectados todos los servicios asociados actualmente a su dominio. Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ your_domain .com) empezará a llegar *a*  Microsoft después de realizar este cambio. 
  
> [!IMPORTANT]
>  El siguiente procedimiento le mostrará cómo eliminar cualquier otro servidor de nombres no deseado de la lista y también cómo agregar los servidores de nombres correctos si aún no aparecen en la lista. > una vez completados los pasos de esta sección, los únicos servidores de nombres que deben aparecer son los cuatro siguientes: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.
    
2. En la **página Recursos,** seleccione **Zonas hospedadas.**
    
3. En la **página Zonas hospedadas,** en la columna **Nombre** de dominio, seleccione el nombre del dominio que desea editar. 
    
4. Seleccione el conjunto de registros **Servidor DNS**. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. En el conjunto de registros **NS: servidor de nombres de dominio** del cuadro **Valor**, elimine todos los servidores de nombres al seleccionarlos todos y después presionar la tecla **Supr** en el teclado. 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (Es decir, elimine solo los servidores  de nombres actuales que no se denominan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**.) 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. En el **área TTL (segundos),** seleccione **1h** (1 hora). 
    
    ![Seleccionar 1H durante una hora](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. Aún en el conjunto de registros **NS: servidor de nombres**, en el cuadro **Valor**, escriba o copie y pegue el valor **Primera línea** de la tabla siguiente y después presione la tecla **Entrar** en el teclado y escriba o copie y pegue el siguiente valor **línea**. 
    
    > [!IMPORTANT]
    > Cada valor de servidor DNS  *debe*  estar en su propia línea dentro del cuadro **Valor**, como se muestra en la siguiente ilustración. 
  
|||
|:-----|:-----|
|**Primera línea** <br/> |ns1.bdm.microsoftonline.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |
|**Segunda línea** <br/> |ns2.bdm.microsoftonline.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |
|**Tercera línea** <br/> |ns3.bdm.microsoftonline.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |
|**Cuarta línea** <br/> |ns4.bdm.microsoftonline.com.  <br/> **Este valor DEBE terminar en punto (.).** <br/> |
   
   ![Escriba o pegue el valor de la primera línea en el cuadro Valor](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. Seleccione **Guardar conjunto de registros.**
    
    ![Seleccionar guardar conjunto de registros](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio. 
