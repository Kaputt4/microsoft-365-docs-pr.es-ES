---
title: Cambiar los servidores DNS para configurar Office 365 con Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Obtenga información acerca de cómo puede configurar Office 365 para administrar los registros DNS de su dominio personalizado en Hostgator.
ms.openlocfilehash: 95131e258482fdb0ff9aa7f00b3339e1c6f9509d
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351851"
---
# <a name="change-nameservers-to-set-up-office-365-with-hostgator"></a>Cambiar los servidores DNS para configurar Office 365 con Hostgator

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca.
  
Siga estas instrucciones si quiere que Office 365 administre automáticamente los registros DNS de Office 365. (Si lo prefiere, puede [administrar todos los registros DNS de Office 365 en Hostgator](create-dns-records-at-hostgator.md)).
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Apunte el dominio a su cuenta de hospedaje.

> [!IMPORTANT]
> Necesita realizar este procedimiento antes de realizar el procedimiento de la sección siguiente ( **Agregar un registro TXT para comprobación** ).
  
Siga estos pasos para asociar el dominio y las cuentas de hospedaje.
  
1. Para empezar, vaya a la página de su portal de clientes en Hostgator con [este vínculo](https://portal.hostgator.com/domain/manage). Se le pedirá que inicie sesión.
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Seleccione la pestaña **dominios** .
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. En la página **administrar dominios** , en el área **mis dominios** , seleccione el dominio que desea actualizar.
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. En la página **información general de dominios** , en el área **servidores DNS** , seleccione **cambiar**.
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. En la página **servidores de nombres** de su dominio, en la lista desplegable **seleccionar cuenta de hospedaje** , elija la cuenta de **hospedaje** que está asociada a su dominio.
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Seleccione **Guardar servidores de nombres**.
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

> [!IMPORTANT]
> Antes de llevar a cabo este procedimiento, primero debe realizar el procedimiento de la primera sección de este artículo, [apuntar el dominio a su cuenta de hospedaje.](#point-your-domain-to-your-hosting-account)
  
Para que pueda usar el dominio con Office 365, tenemos que asegurarnos de que es de su propiedad. Si puede iniciar sesión en la cuenta en su registrador de dominios y crear el registro DNS, Office 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.
  
1. Para empezar, vaya a la página cPanel en Hostgator. Se le pedirá que inicie sesión primero.
    
    (Cada cuenta alojada en Hostgator se le asigna una única dirección CPanel. La dirección cPanel debe tener un aspecto parecido a este: https://YourSiteAddress:secure-port-number. La suscripción de correo electrónico que ha recibido de Hostgator especificará esa dirección de correo electrónico).
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para empezar a trabajar con Office 365, puede comprar una cuenta de hospedaje desde Hostgator o [cambiar los registros del servidor de nombres (NS) de su dominio](#change-your-domains-nameserver-ns-records) para que apunten a Office 365. 
  
2. En la página **Panel de control** , en el área **dominios** , seleccione **Editor de zonas DNS avanzado**.
    
    (You may have to scroll down.) 
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Elija el valor **Tipo** de la lista desplegable). 
    
|||||
|:-----|:-----|:-----|:-----|
|**Nombre** <br/> |**TTL** <br/> |**Tipo** <br/> |**Datos TXT** <br/> |
|Use su  *nombre_de_dominio*  . (por ejemplo, fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Office 365. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Seleccione **Agregar registro**.
    
5. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
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
> El siguiente procedimiento le mostrará cómo eliminar cualquier otro de los servidores de nombres no deseados de la lista, y también cómo agregar los servidores de nombres correctos si aún no aparecen. Cuando haya completado los pasos de esta sección, los únicos servidores de nombres que se deben enumerar son los cuatro siguientes: **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**y **NS4.BDM.microsoftonline.com**.
  
1. Para empezar, vaya a la página de su portal de clientes en Hostgator con [este vínculo](https://portal.hostgator.com/domain/manage). Se le pedirá que inicie sesión.
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Seleccione la pestaña **dominios** . 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. En la página **administrar dominios** , en el área **mis dominios** , seleccione el dominio que desea actualizar. 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. En la página **información general del dominio** , en el área **servidores DNS** , seleccione **cambiar**.
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. En la página **servidores de nombres** de su dominio, en la lista desplegable **seleccionar cuenta de hospedaje** , elija la cuenta de **hospedaje** que está asociada a su dominio. 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Seleccione **establecer manualmente mis servidores de nombres**.
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **PRECAUCIÓN**: siga estos pasos solo si tiene servidores de nombres distintos de los cuatro servidores de nombres correctos. (Es decir, elimine solo los servidores DNS actuales que *no* tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com**o **NS4.BDM.microsoftonline.com**).
  
        En la página **Servidores DNS** del dominio, en la lista de servidores DNS, elimine todos los servidores DNS de la lista (para hacerlo, seleccione los servidores DNS en la lista y, después, presione la tecla **Suprimir** en el teclado). 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. En la lista de servidores DNS, escriba (o copie y pegue) los dos primeros valores de la tabla siguiente.
    
|||
|:-----|:-----|
|**Servidor DNS 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 2:** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator-BP-redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Agregue los demás valores de servidor de nombres.
    
    Seleccione **(+)** agregar y, a continuación, escriba (o copie y pegue) el valor de la siguiente fila de la tabla en el cuadro para el registro. 
    
    Repita este proceso hasta que haya creado los cuatro registros de servidor de nombres.
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Seleccione **Guardar servidores de nombres**.
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, su correo electrónico y otros servicios de Office 365 estarán listos para funcionar con su dominio.
