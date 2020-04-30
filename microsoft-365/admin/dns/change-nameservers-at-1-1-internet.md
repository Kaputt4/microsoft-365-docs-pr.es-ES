---
title: Cambiar los servidores DNS para configurar Microsoft con 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Obtenga información sobre cómo configurar Office 365 operado por 21Vianet para administrar los registros DNS, cuando 1&1 Internet es el proveedor de host DNS.
ms.openlocfilehash: 99ac40472d0afa0cb734b0e86a0f10d7904133e1
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939417"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-11-ionos"></a>Cambiar los servidores DNS para configurar Microsoft 365 con 1&1 IONOS

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Siga estas instrucciones si desea que Microsoft 365 administre los registros DNS de Microsoft 365 por usted. (Si lo prefiere, puede [administrar todos los registros DNS de Microsoft 365 en 1&1 IONOS](create-dns-records-at-1-1-internet.md)). 
  

    
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación


Antes de utilizar el dominio con Microsoft 365, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft 365 sabrá que es el propietario del dominio.
  
> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
Siga los pasos siguientes o [vea el vídeo (empieza en 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). You'll be prompted to log in. 
    
2. En **mis dominios**, seleccione **administrar dominios**.
    
3. En la página **centro de dominios** , busque el dominio que desea actualizar; a continuación, seleccione el control **Panel** ( **v**) para ese dominio.
    
4. En el área **configuración del dominio** , seleccione **Editar configuración DNS**.
    
5. En la sección **registros txt y SRV** , seleccione **Agregar registro**.
    
    (You may have to scroll down.) 
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Tipo** <br/> |**Prefijo** <br/> |**Valor de nombre** <br/> |
|TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX* <br/> **Nota**: este es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. Seleccione **Guardar**y vuelva a **Guardar** . 
    
8. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.
    
9. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio de su registrador de dominios, volverá a Microsoft 365 y solicitará que busque el registro.
  
Cuando Microsoft 365 encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración, diríjase a la página **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">dominios</a>.
    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija ** Iniciar configuración**.
    
4. En la página**Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Buscar y corregir problemas después de agregar el dominio o los registros DNS en Microsoft 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

Para completar la configuración de su dominio con Microsoft 365, debe cambiar los registros NS de su dominio en su registrador de dominios para que apunten a los servidores de nombres principal y secundario de Microsoft 365. Esto configura Microsoft 365 para que actualice los registros DNS del dominio por usted. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.
  
> [!CAUTION]
> Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft 365, se ven afectados todos los servicios que están actualmente asociados a su dominio. Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ *your_domain* . com) empezará a llegar a Microsoft 365 después de realizar este cambio. 
  
¿Está preparado para cambiar los registros NS para que Microsoft 365 pueda configurar su dominio? Siga los pasos siguientes o [vea el vídeo (empieza en 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!IMPORTANT]
>  El siguiente procedimiento le mostrará cómo eliminar cualquier otro de los servidores de nombres no deseados de la lista, y también cómo agregar los servidores de nombres correctos si aún no aparecen. > cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son los cuatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Para empezar, vaya a su página de dominios en 1&1 IONOS a través de [este vínculo](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F). You'll be prompted to log in. 
    
2. En **mis dominios**, seleccione **administrar dominios**.
    
3. En la página **centro de dominios** , busque el dominio que desea actualizar y, a continuación, seleccione el control **Panel** ( **v**) para ese dominio.
    
4. En el área **configuración del dominio** , seleccione **Editar configuración DNS**.
    
5. En la sección **Configuración de servidor DNS**, seleccione **Otros servidores DNS**.
    
    (Es posible que tenga que desplazarse hacia abajo).
    
6. Dependiendo de si ya existen o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes:
    
  - Si aún **NO** se muestran servidores DNS en la lista, [Si aún NO se muestran servidores DNS en la lista](#if-there-are-no-nameservers-already-listed).
    
  - Si **YA** se muestran servidores DNS en la lista, [Si ya existen servidores de nombres enumerados](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Si aún NO se muestran servidores DNS en la lista

1. En el cuadro **Servidor DNS 1**, escriba (o copie y pegue) el valor de la tabla siguiente. 
    
|||
|:-----|:-----|
|**Servidor DNS 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
   
   ![Especificación de un valor en el cuadro servidor DNS 1](../../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. En la lista desplegable **Servidores DNS adicionales**, elija **Mis servidores DNS secundarios**.
    
    ![Choosing My secondary name servers in the list](../../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. En los cuadros **Servidor DNS 2, 3 y 4**, escriba (o copie y pegue) el valor de la tabla siguiente. 
    
|||
|:-----|:-----|
|**Servidor DNS 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
![Introducción de los valores del servidor de nombres](../../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. Haga clic en **Guardar**.
    
    ![Seleccione Guardar en la página Configuración del servidor de nombres](../../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.
    
    ![Selección de la opción Guardar en el cuadro de diálogo Editar configuración DNS](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Si ya existen servidores de nombres enumerados

> [!CAUTION]
> Siga estos pasos  *solo*  si tiene servidores de nombres distintos de los cuatro servidores de nombres  *correctos*  . (Es decir, elimine  *solo*  los servidores de nombres actuales que  *no*  sean **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** o **ns4.bdm.microsoftonline.com** ). 
  
1. Si ya se muestran servidores DNS en los cuadros de **Servidor DNS**, elimínelos (para hacerlo, selecciónelos de uno en uno y, después, presione la tecla **Suprimir** en el teclado). 
    
    ![Deleting name servers](../../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. En los cuadros **Servidor DNS 1, 2, 3 y 4**, escriba (o copie y pegue) los valores de la tabla siguiente. 
    
|||
|:-----|:-----|
|**Servidor DNS 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor DNS 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Introducción de los valores del servidor de nombres](../../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. Haga clic en **Guardar**.
    
    ![Seleccione Guardar en la página Configuración del servidor de nombres](../../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. En el cuadro de diálogo **Editar configuración DNS** , seleccione **sí**.
    
    ![Selección de la opción Guardar en el cuadro de diálogo Editar configuración DNS](../../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio. 
  


