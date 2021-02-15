---
title: Cambiar los servidores de nombres para configurar Microsoft con Hostgator
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
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Obtenga información sobre cómo configurar Microsoft para administrar los registros DNS de su dominio personalizado en Hostgator.
ms.openlocfilehash: 34e7bbe3abc084185f72f4fef004ad891492ef3c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658025"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>Cambiar los servidores de nombres para configurar Microsoft 365 con Hostgator

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.
  
Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted. (Si lo prefiere, puede administrar todos los registros DNS de [Microsoft en Hostgator).](create-dns-records-at-hostgator.md)
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Apunte el dominio a su cuenta de hospedaje.

> [!IMPORTANT]
> Necesita realizar este procedimiento antes de realizar el procedimiento de la sección siguiente ( **Agregar un registro TXT para comprobación** ).
  
Siga estos pasos para asociar el dominio y las cuentas de hospedaje.
  
1. Para empezar, vaya a la página de su portal de clientes en Hostgator con [este vínculo](https://portal.hostgator.com/domain/manage). Se le pedirá que inicie sesión.
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Seleccione la **pestaña** Dominios.
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. En la **página Administrar dominios,** en el área **Mis dominios,** seleccione el dominio que desea actualizar.
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. En la **página Información general de** dominios, en el área Servidores **dns,** seleccione **Cambiar**.
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. En la **página Servidores** dns de  su dominio, en la  lista desplegable Seleccionar cuenta de hospedaje, elija la cuenta de hospedaje asociada a su dominio.
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Seleccione **Guardar servidores dns.**
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

> [!IMPORTANT]
> Antes de llevar a cabo este procedimiento, primero debe realizar el procedimiento de la primera sección de este artículo, Apuntar el dominio [a la cuenta de hospedaje.](#point-your-domain-to-your-hosting-account).
  
Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.
  
1. Para empezar, vaya a la página cPanel en Hostgator. Se le pedirá que inicie sesión primero.
    
    (Cada cuenta alojada en Hostgator se le asigna una única dirección CPanel. La dirección cPanel debe tener un aspecto parecido a este: https://YourSiteAddress:secure-port-number. La suscripción de correo electrónico que ha recibido de Hostgator especificará esa dirección de correo electrónico).
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft. 
  
2. En la **página Panel de control,** en el área **Dominios,** seleccione **Editor de zona DNS avanzado.**
    
    (Es posible que tenga que desplazarse hacia abajo). 
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Elija el valor **Tipo** de la lista desplegable). 
    
|||||
|:-----|:-----|:-----|:-----|
|**Nombre** <br/> |**TTL** <br/> |**Tipo** <br/> |**Datos TXT** <br/> |
|Use su  *nombre_de_dominio*  . (por ejemplo, fourthcoffee.com.)  <br/> **Este valor DEBE terminar en punto (.).** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Seleccione **Agregar registro.**
    
5. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.

    
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
> El siguiente procedimiento le mostrará cómo eliminar cualquier otro servidor de nombres no deseado de la lista y también cómo agregar los servidores de nombres correctos si aún no aparecen en la lista. Cuando haya completado los pasos de esta sección, los únicos servidores de nombres que deben aparecer son los cuatro siguientes:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** y **ns4.bdm.microsoftonline.com**.
  
1. Para empezar, vaya a la página de su portal de clientes en Hostgator con [este vínculo](https://portal.hostgator.com/domain/manage). Se le pedirá que inicie sesión.
    
    ![Hostgator-BP-Redelegate-1-0](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Seleccione la **pestaña** Dominios. 
    
    ![Hostgator-BP-Redelegate-1-1](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. En la **página Administrar dominios,** en el área **Mis dominios,** seleccione el dominio que desea actualizar. 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. En la **página Información general del** dominio, en el área Servidores **dns,** seleccione **Cambiar**.
    
    ![Hostgator-BP-Redelegate-1-3](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. En la **página Servidores** dns de  su dominio, en la  lista desplegable Seleccionar cuenta de hospedaje, elija la cuenta de hospedaje asociada a su dominio. 
    
    ![Hostgator-BP-Redelegate-1-4](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Seleccione **Establecer manualmente mis servidores de nombres.**
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **PRECAUCIÓN:** Siga estos pasos solo si tiene servidores de nombres existentes distintos de los cuatro servidores de nombres correctos. (Es decir, elimine solo los servidores  de nombres actuales que no se denominan **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com**.)
  
        En la página **Servidores DNS** del dominio, en la lista de servidores DNS, elimine todos los servidores DNS de la lista (para hacerlo, seleccione los servidores DNS en la lista y, después, presione la tecla **Suprimir** en el teclado). 
    
   ![Hostgator-BP-Redelegate-1-6](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. En la lista de servidores DNS, escriba (o copie y pegue) los dos primeros valores de la tabla siguiente.
    
|||
|:-----|:-----|
|**Servidor DNS 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 2:** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator-BP-Redelegate-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Agregue los demás valores de servidor de nombres.
    
    Seleccione **(+)** agregar y, a continuación, escriba o copie y pegue el valor de la siguiente fila de la tabla en el cuadro del registro. 
    
    Repita este proceso hasta que haya creado los cuatro registros de servidor de nombres.
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Seleccione **Guardar servidores dns.**
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio.
