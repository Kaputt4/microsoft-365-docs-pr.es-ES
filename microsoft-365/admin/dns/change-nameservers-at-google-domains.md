---
title: Cambiar los servidores DNS para configurar Microsoft con Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Obtenga información sobre cómo configurar Microsoft para que administre los registros DNS de su dominio personalizado en Google Domains.
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658445"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a>Cambiar los servidores DNS para configurar Microsoft con Google Domains

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca. 
  
Siga estas instrucciones si desea que Microsoft administre los registros DNS por usted. (Si lo prefiere, puede [administrar todos los registros DNS en Google Domains](create-dns-records-at-google-domains.md)).
  
    
## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.
  
> [!NOTE]
>  Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea. 
  
1. Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. Seleccione **Iniciar sesión**.
    
2. Escriba sus credenciales de inicio de sesión y vuelva a seleccionar **iniciar sesión**.
    
2. En la página **Dominios**, en la sección **Dominio**, seleccione **Configurar DNS** para el dominio que quiera editar. 
    
3. En la sección **Registros de recursos personalizados**, en los cuadros para el nuevo registro, escriba o copie y pegue los valores que aparecen en la tabla siguiente. 
    
    (Es posible que tenga que desplazarse hacia abajo).
    
    (Elija el valor **Tipo** de la lista desplegable). 
    
|||||
|:-----|:-----|:-----|:-----|
|**Nombre** <br/> |**Tipo** <br/> |**TTL** <br/> |**Datos** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX* <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. Elija **Agregar**.
    
5. Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.
    
Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro.
  
Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
1. En el centro de administración de Microsoft, diríjase a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Dominios</a>.

    
2. En la página **Dominios**, elija el dominio que está verificando. 
    
3. En la página de **Configuración**, elija **Iniciar configuración**.
    
4. En la página **Verificar dominio**, elija **Verificar**.
    
> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

Para completar la configuración de su dominio con Microsoft, debe cambiar los registros NS de su dominio en su registrador de dominios para que apunten a los servidores de nombres principal y secundario de Microsoft. Esto configura a Microsoft para que actualice los registros DNS del dominio por usted. Agregaremos todos los registros para que el correo electrónico, Skype Empresarial Online y su sitio web público funcionen con su dominio, y ya lo tendrá todo preparado.
  
> [!CAUTION]
> Al cambiar los registros NS de su dominio para que apunten a los servidores de nombres de Microsoft, se ven afectados todos los servicios que están actualmente asociados a su dominio. Por ejemplo, todo el correo electrónico enviado a su dominio (como rob@ *your_domain.*  com) empezará a llegar a Microsoft después de realizar este cambio. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > cuando haya completado los pasos de esta sección, los únicos servidores DNS que se deben enumerar son estos cuatro: 
  
1. Para empezar, vaya a su página de dominios en Google Domains a través de [este vínculo](https://domains.google.com/registrar). Se le pedirá que inicie sesión. Para ello:
    
1. Seleccione **Iniciar sesión**.
    
2. Escriba sus credenciales de inicio de sesión y vuelva a seleccionar **Iniciar sesión**.
    
2. En la página **Dominios**, en la sección **Dominio**, seleccione **Configurar DNS** para el dominio que quiera editar. 
    
3. En la página **Dominios**, en la sección **Servidores de nombres**, seleccione **Use servidores de nombres personalizados**.
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. Dependiendo de si ya existen o no servidores de nombres enumerados en la página que se muestra ahora, continúe con uno de los dos procedimientos siguientes:
    
  - Si aún **NO** se muestran servidores DNS en la lista, [Si aún NO se muestran servidores DNS en la lista](#if-there-are-no-nameservers-already-listed).
    
  - Si **YA** se muestran servidores DNS en la lista, [Si ya existen servidores de nombres enumerados](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Si aún NO se muestran servidores DNS en la lista

1. Agregue el primer servidor de nombres.
    
    En la sección **Servidores de nombres**, en el cuadro **SERVIDOR DE NOMBRES**, escriba o copie y pegue el primer valor de la tabla siguiente. 
    
|||
|:-----|:-----|
|**Primer servidor de nombres** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Segundo servidor de nombres** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Tercer servidor de nombres** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Cuarto servidor de nombres** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-BP-redelegate-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. Seleccione el control **+ (agregar)** para crear una fila vacía. 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. Agregue los otros tres registros del servidor de nombres.
    
    En la sección **servidores de nombres personalizados** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, a continuación, seleccione el control **+ (agregar)** para agregar otra fila. 
    
    Repita este proceso hasta que haya creado los cuatro registros de servidor de nombres.
    
4. Seleccione **Guardar**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Si ya existen servidores de nombres enumerados

1. Si en la lista se muestran otros servidores DNS, seleccione **Editar**.
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (Es decir, elimine solo los servidores DNS actuales que  *no*  tengan el nombre **ns1.BDM.microsoftonline.com**, **NS2.BDM.microsoftonline.com**, **NS3.BDM.microsoftonline.com** o **NS4.BDM.microsoftonline.com**). 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. Elimine cada uno seleccionándolo y, después, presione la tecla **Eliminar** en el teclado. 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. Aún en la sección **Servidores de nombres**, en las filas **Servidor de nombres**, escriba o copie y pegue los valores de la tabla siguiente. 
    
|||
|:-----|:-----|
|**Primer servidor de nombres** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Segundo servidor de nombres** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Tercer servidor de nombres** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Cuarto servidor de nombres** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-BP-redelegate-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. Seleccione el control **+ (agregar)** para crear una fila vacía. 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. Agregue los otros dos registros del servidor de nombres.
    
    En la sección **servidores de nombres personalizados** , cree un registro (para hacerlo, use los valores de la siguiente fila de la tabla y, a continuación, seleccione el control **+ (agregar)** para agregar otra fila. 
    
    Repita este proceso hasta que haya creado los cuatro registros de servidor de nombres.
    
6. Seleccione **Guardar**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> Las actualizaciones de los registros de los servidores de nombres pueden tardar varias horas en propagarse por el sistema DNS de Internet. El correo electrónico y otros servicios de Microsoft estarán todos establecidos para funcionar con su dominio. 
  
