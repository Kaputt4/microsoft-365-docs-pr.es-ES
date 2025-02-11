---
title: Conexión de los registros DNS en GoDaddy a Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea y otros servicios en GoDaddy para Microsoft.
ms.openlocfilehash: ce9d26d5ecf2bb91ac267e6ab0305e1d50eb4095
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68729509"
---
# <a name="connect-your-dns-records-at-godaddy-to-microsoft-365"></a>Conexión de los registros DNS en GoDaddy a Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si GoDaddy es su proveedor de hosting DNS, siga los pasos de este artículo para comprobar su dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial Online, etc.

## <a name="before-you-begin"></a>Antes de empezar

Tiene dos opciones para configurar registros DNS para el dominio:

- [**Uso de Domain Connect**](#use-domain-connect-to-verify-and-set-up-your-domain) Si no ha configurado el dominio con otro proveedor de servicios de correo electrónico, use los pasos de Domain Connect para comprobar y configurar automáticamente el nuevo dominio para usarlo con Microsoft 365.

   O

- [**Siga los pasos manuales.**](#create-dns-records-with-manual-setup) Compruebe el dominio siguiendo los pasos manuales que se indican a continuación y elija cuándo y qué registros se van a agregar al registrador de dominios. Esto le permite configurar nuevos registros MX (correo), por ejemplo, a su conveniencia.

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>Uso de Domain Connect para comprobar y configurar el dominio

Siga estos pasos para comprobar y configurar automáticamente el dominio de GoDaddy con Microsoft 365:

1. En el Centro de administración de Microsoft 365, seleccione **Dominios de configuración** >  y seleccione el dominio que desea configurar.<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

1. Seleccione los tres puntos (más acciones) > elija **Iniciar configuración**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. En ¿Cómo desea conectar el dominio? página, seleccione **Continuar**.

1. En la página Agregar registros DNS, seleccione **Agregar registros DNS**.

1. En la página de inicio de sesión de GoDaddy, inicie sesión en su cuenta y seleccione **Autorizar**.

   Esto completa la configuración del dominio para Microsoft 365.

## <a name="create-dns-records-with-manual-setup"></a>Creación de registros DNS con configuración manual

Después de agregar estos registros en GoDaddy, el dominio se configurará para trabajar con servicios de Microsoft.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.

> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled).

   Si se le pide que inicie sesión, use sus credenciales de inicio de sesión, seleccione el nombre de inicio de sesión en la esquina superior derecha y, a continuación, seleccione **Mis productos**.

1. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Registros**, seleccione **AGREGAR** (es posible que tenga que desplazarse hacia abajo).

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

1. Elija **TXT** en la lista desplegable.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="Seleccione TXT en la lista desplegable Tipo.":::

1. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla.

   |Tipo|Host|TXT Value|TTL|
   |---|---|---|---|
   |TXT|@|MS=ms *XXXXXXXX*<br>**Nota**: Este es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|1 hora  <br>|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXT-values.png" alt-text="Rellene los valores de la tabla para el registro TXT.":::

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXTSave.png" alt-text="Seleccione Guardar.":::

   Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.
  
Para comprobar el registro en Microsoft 365:
  
1. En el centro de administración, vaya a **Dominios de configuración**\>.<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"></a>

1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar configuración**.

   :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. Seleccione **Continuar**.
  
1. En la página **Verificar dominio**, elija **Verificar**.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled).

   Si se le pide que inicie sesión, use sus credenciales de inicio de sesión, seleccione el nombre de inicio de sesión en la esquina superior derecha y, a continuación, seleccione **Mis productos**.

2. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

3. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

4. Elija **MX** en la lista desplegable.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="Seleccione MX en la lista desplegable Tipo.":::

5. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

   (Elija los valores **Type** y **TTL** de la lista desplegable).

   |Tipo|Host|Points to |Prioridad|TTL|
   |---|---|---|---|---|
   |MX|@| *\<domain-key\>*.mail.protection.outlook.com  <br/> **Nota:** Obtenga su *\<domain-key\>* de su cuenta Microsoft. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|10  <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)|1 hora|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="Rellene los valores de la tabla para el registro MX.":::

6. Seleccione **Guardar**.

### <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled).

   Si se le pide que inicie sesión, use sus credenciales de inicio de sesión, seleccione el nombre de inicio de sesión en la esquina superior derecha y, a continuación, seleccione **Mis productos**.

2. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

3. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

4. Elija **CNAME** en la lista desplegable.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="Seleccione CNAME en la lista desplegable Tipo.":::

5. Cree el registro CNAME.

   En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.

   (Elija el valor **de TTL** en la lista desplegable).

   |Tipo|Host|Points to |TTL|
   |---|---|---|---|
   |CNAME|autodiscover|autodiscover.outlook.com|1 hora|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="Rellene los valores de la tabla para el registro CNAME.":::

6. Seleccione **Guardar**.

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un  *único*  registro SPF que incluya ambos conjuntos de valores.

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled).

   Si se le pide que inicie sesión, use sus credenciales de inicio de sesión, seleccione el nombre de inicio de sesión en la esquina superior derecha y, a continuación, seleccione **Mis productos**.

2. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

3. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

4. Elija **TXT** en la lista desplegable.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="Seleccione TXT en la lista desplegable Tipo.":::

5. In the boxes for the new record, type or copy and paste the following values.

   (Elija el valor **de TTL** en las listas desplegables).

   |Tipo|Host|TXT Value|TTL|
   |---|---|---|---|
   |TXT|@|v=spf1 include:spf.protection.outlook.com -all  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|1 hora|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-TXT-values.png" alt-text="Rellene los valores de la tabla para el registro TXT.":::

6. Seleccione **Guardar**.

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea, como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled).

   Si se le pide que inicie sesión, use sus credenciales de inicio de sesión, seleccione el nombre de inicio de sesión en la esquina superior derecha y, a continuación, seleccione **Mis productos**.

1. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

1. Elija **SRV** en la lista desplegable.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="Seleccione SRV en la lista desplegable Tipo.":::

1. Cree el primer registro SRV.

   En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.

   (Elija los valores **Type** y **TTL** de las listas desplegables).

   |Tipo|Servicio|Protocolo|Nombre|Target|Prioridad|Peso|Puerto|TTL|
   |---|---|---|---|---|---|---|---|---|
   |SRV|_sip|_tls|@|sipdir.online.lync.com|100| 1|443|1 hora|
   |SRV|_sipfederationtls|_tcp|@| sipfed.online.lync.com| 100|1|5061|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-SRV-values.png" alt-text="Rellene los valores de la tabla para el registro SRV.":::

1. Seleccione **Guardar**.

1. Agregue el otro registro SRV eligiendo los valores de la segunda fila de la tabla.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Agregue los dos registros CNAME necesarios para Skype Empresarial
  
1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled).

   Si se le pide que inicie sesión, use sus credenciales de inicio de sesión, seleccione el nombre de inicio de sesión en la esquina superior derecha y, a continuación, seleccione **Mis productos**.

1. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

1. Elija **CNAME** en la lista desplegable.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="Seleccione CNAME en la lista desplegable Tipo.":::

1. En los cuadros vacíos de los nuevos registros, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.

   |Tipo|Host|Points to |TTL|
   |---|---|---|---|
   |CNAME|sip|sipdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)**|1 Hour|
   |CNAME|lyncdiscover|webdir.online.lync.com.  <br/> **Este valor DEBE terminar en punto (.)**|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="Rellene los valores de la tabla para el registro CNAME.":::
  
1. Seleccione **Guardar**.
  
1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota los dispositivos móviles que se conectan a su dominio. Mobile Administración de dispositivos necesita 2 registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records-mobile-device-management"></a>Agregue los dos registros CNAME necesarios mobile Administración de dispositivos

1. Para empezar, vaya a su página de dominios en GoDaddy a través de [este vínculo](https://account.godaddy.com/products/?go_redirect=disabled).

   Si se le pide que inicie sesión, use sus credenciales de inicio de sesión, seleccione el nombre de inicio de sesión en la esquina superior derecha y, a continuación, seleccione **Mis productos**.

1. En **Dominios**, seleccione los tres puntos junto al dominio que desea comprobar y, a continuación, seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-1.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Registros**, seleccione **AGREGAR**.

   :::image type="content" source="../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png" alt-text="Seleccione AGREGAR.":::

1. Elija **CNAME** en la lista desplegable.

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-Type.png" alt-text="Seleccione CNAME en la lista desplegable Tipo.":::

1. En los cuadros vacíos de los nuevos registros, escriba o copie y pegue los valores de la primera fila de la tabla siguiente.

   |Tipo|Host|Points to |TTL|
   |---|---|---|---|
   |CNAME|enterpriseregistration|enterpriseregistration.windows.net.  <br/> **Este valor DEBE terminar en punto (.)**|1 Hour|
   |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor DEBE terminar en punto (.).**|1 Hour|

   :::image type="content" source="../../media/dns-godaddy/godaddy-domains-CNAME-values.png" alt-text="Rellene los valores de la tabla para el registro CNAME.":::
  
1. Seleccione **Guardar**.
  
1. Agregue el otro registro CNAME eligiendo los valores de la segunda fila de la tabla.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).
