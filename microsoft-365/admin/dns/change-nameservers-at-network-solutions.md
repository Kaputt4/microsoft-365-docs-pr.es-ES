---
title: Cambiar los servidores de nombres para configurar Microsoft con soluciones de red
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Aprenda a configurar su dominio personalizado de Microsoft con Soluciones de red si desea que Microsoft administre los registros DNS. '
ms.openlocfilehash: 04817ca24b13b4c138986df3875b6d397100fffd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658433"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a>Cambiar los servidores de nombres para configurar Microsoft con soluciones de red

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.
  
Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted. (Si lo prefiere, puede administrar todos los registros DNS de [Microsoft en Network Solutions).](create-dns-records-at-network-solutions.md)
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a>Agregar un registro TXT en Network Solutions para comprobar que es el propietario del dominio

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
Siga los pasos siguientes o [vea el vídeo (empieza en 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).
  
1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
    
    > [!IMPORTANT]
    > Antes de seleccionar el botón **Iniciar** sesión, elija Primero **Administrar** mis nombres de dominio en la lista desplegable Iniciar sesión **para:**
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Seleccione la casilla situada al lado del nombre del dominio que desea modificar.
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Seleccione **Editar DNS**.
    
    ![Seleccionar Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Seleccione **Administrar registros DNS avanzados.**
    
    (Es posible que tenga que desplazarse hacia abajo).
    
    ![Seleccionar Administrar registros DNS avanzados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Desplácese hacia abajo hasta **la sección Texto (registros TXT)** y, a continuación, **seleccione Editar registros TXT**.
    
    ![Seleccionar Editar registros TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.
    
|**Host**|**TTL**|**Texto**|
|:-----|:-----|:-----|
|@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Nota:** Este es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365.           [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Escribir o pegar valores en los cuadros para el nuevo registro](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Seleccione **Continuar**.
    
    ![Seleccionar Continuar](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Seleccione **Guardar cambios.**
    
    ![Seleccionar Guardar cambios](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
    
  
3. En la página de **Configuración**, elija **Iniciar configuración**.
    
    
  
4. En la página **verificar dominio**, seleccione **verificar**.
    
    
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

Para completar la configuración de su dominio con Microsoft, cambie los registros NS de su dominio en el registrador de dominios para que apunten a los servidores de nombres principales y secundarios de Microsoft. Esto configura Microsoft para que actualice automáticamente los registros DNS del dominio. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.
  
> [!CAUTION]
> Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft, se verán afectados todos los servicios asociados actualmente a su dominio. Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ your_domain .com) empezará a llegar *a*  Microsoft después de realizar este cambio.
  
¿Está listo para cambiar los registros NS para que Microsoft pueda configurar su dominio? Siga los pasos siguientes o [vea el vídeo (empieza en 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).
  
> [!IMPORTANT]
>  Cuando haya completado los pasos de  esta sección, los únicos servidores de nombres que deben aparecer son los cuatro siguientes: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** y **ns4.bdm.microsoftonline.com**. En el procedimiento siguiente se muestra cómo eliminar cualquier otro servidor de nombres que no desee de la lista y también cómo agregar estos cuatro servidores DNS  *correctos*  , si aún no están en la lista. 
  
1. Para empezar, vaya a la página de dominios en Network Solutions mediante [este vínculo](https://www.networksolutions.com/manage-it). Se le pedirá que inicie sesión.
    
    > [!IMPORTANT]
    > Antes de seleccionar el botón **Iniciar** sesión, elija Primero **Administrar** mis nombres de dominio en la lista desplegable Iniciar sesión **para:** 
  
    ![Elija Administrar mis nombres de dominio e inicie sesión en Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Seleccione la casilla situada al lado del nombre del dominio que desea modificar.
    
    ![Seleccione la casilla del dominio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Seleccione **Editar DNS**.
    
    ![Seleccionar Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Seleccione **Mover DNS**.
    
    ![NetworkSolutionsBP-Redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. Dependiendo de si ya existen o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes:
    
  - Si aún **NO** se muestran servidores DNS en la lista, [Si aún NO se muestran servidores DNS en la lista](#if-there-are-no-nameservers-already-listed).
    
  - Si **YA** se muestran servidores DNS en la lista, [Si ya existen servidores de nombres enumerados](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Si aún NO se muestran servidores DNS en la lista

1. En la **página Dominios,** en la sección Especificar servidores de nombres **de dominio,** seleccione **Agregar más servidores dns.**
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. En la página **Nombres de dominio**, escriba (o copie y pegue) los valores de servidores DNS de la tabla siguiente. 
    
|||
|:-----|:-----|
|**Servidor DNS 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 2** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 2** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. Seleccione **Mover DNS**.
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. Seleccione **Guardar cambios.**
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Si ya existen servidores de nombres enumerados

> [!CAUTION]
> Siga estos pasos  *solo*  si tiene servidores de nombres distintos de los cuatro servidores de nombres  *correctos*  . (Es decir, elimine  *solo*  los servidores de nombres actuales que  *no*  sean **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com** ).
  
1. Si la lista contiene otros servidores DNS, elimínelos (para hacerlo, selecciónelos y, después, presione la tecla **Suprimir** en el teclado).
    
    ![NetworkSolutions-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. Seleccione **Agregar más servidores dns.**
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. En la página **Nombres de dominio**, escriba (o copie y pegue) los valores de servidores DNS de la tabla siguiente. 
    
|||
|:-----|:-----|
|**Servidor DNS 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor de nombres 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor de nombres 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. Seleccione **Mover DNS**.
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. Seleccione **Guardar cambios.**
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para funcionar con su dominio.
