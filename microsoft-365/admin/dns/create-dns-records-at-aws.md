---
title: Conectar los registros DNS en Amazon Web Services (AWS) para Microsoft 365
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
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
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial Online y otros servicios en Amazon Web Services (AWS) para Microsoft.
ms.openlocfilehash: b07ee3d44c3c36115a3ce35d4517e834f212689f
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568049"
---
# <a name="connect-your-dns-records-at-amazon-web-services-aws-to-microsoft-365"></a>Conectar los registros DNS en Amazon Web Services (AWS) para Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si AWS es su proveedor de hospedaje DNS, siga los pasos de este artículo para comprobar su dominio y configurar registros DNS para correo electrónico, Skype Online para empresas, y así sucesivamente.

Después de agregar estos registros en AWS, el dominio se configurará para que funcione con servicios Microsoft.

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.

> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.

1. En la página de aterrizaje, en **Dominios**, seleccione **Dominios registrados**.

1. En **Nombre de** dominio, seleccione el dominio que desea configurar en Microsoft 365.

    **Nota**: Si no ha creado una zona hospedada para su dominio, seleccione Crear zona  hospedada y complete los pasos antes de pasar al paso siguiente.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Seleccione el nombre del dominio que desea comprobar.":::

1. Seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Nombre de dominio**, seleccione el nombre de dominio para la versión de zona hospedada del dominio que desea comprobar.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Seleccione el nombre del dominio que desea comprobar.":::

1. Seleccione **Crear registro**.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Seleccione Crear registro.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Elija los **valores de directiva de** tipo **y enrutamiento de** las listas desplegables).

    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.

    |Nombre del registro|Tipo de registro|Valor|TTL (Seconds)|Directiva de enrutamiento|
    |:-----|:-----|:-----|:-----|:-----|
    |(Leave this field empty.)|TXT: se usa para comprobar remitentes de correo electrónico|MS=*msXXXXXXXX* <br/> **Nota:** esto es un ejemplo. Use su valor **Dirección de destino** específico aquí, de la tabla de Microsoft 365. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|300|Simple|

1. Seleccione **Crear registros**.

   :::image type="content" source="../../media/dns-aws/aws-domains-txt-create-records.png" alt-text="Seleccione Crear registros.":::

   Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y solicitará una búsqueda para el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.

Para comprobar el registro en Microsoft 365:

1. En el Centro de administración, vaya a **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**dominios**</a>.

1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar instalación.":::

1. Seleccione **Continuar**.

1. En la página **Verificar dominio**, elija **Verificar**.

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft-365"></a>Agregue un registro MX para que el correo electrónico de su dominio se envíe a Microsoft 365

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.

1. En la página de aterrizaje, en **Dominios**, seleccione **Dominios registrados**.

1. En **Nombre de** dominio, seleccione el dominio que desea configurar en Microsoft 365.

    **Nota**: Si no ha creado una zona hospedada para su dominio, seleccione Crear zona  hospedada y complete los pasos antes de pasar al paso siguiente.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Nombre de dominio**, seleccione el nombre de dominio para la versión de zona hospedada del dominio que desea comprobar.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Crear registro**.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Seleccione Crear registro.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Elija los **valores de directiva de** tipo **y enrutamiento de** las listas desplegables).

    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.

    |Nombre del registro|Tipo de registro|Valor|TTL (Seconds)|Directiva de enrutamiento|
    |:-----|:-----|:-----|:-----|:-----|
    |(Leave this field empty.)|MX: especifica servidores de correo|0 *\<domain-key\>*.mail.protection.outlook.com. <br/> El 0 es el valor de prioridad MX. Agréguelo al principio del valor MX, separado del resto del valor por un espacio.  <br/> **Este valor DEBE terminar en punto (.).** <br/> **Nota:** Obtenga el de \<*domain-key*\> su cuenta Microsoft 365 usuario. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|300|Enrutamiento simple|

1. Seleccione **Crear registros**.

   :::image type="content" source="../../media/dns-aws/aws-domains-mx-create-records.png" alt-text="Seleccione Crear registros.":::

1. Si hay otros registros MX, elimínelos seleccionando el registro y seleccionando **Eliminar**.

## <a name="add-the-cname-record-required-for-microsoft-365"></a>Agregue el registro CNAME necesario para Microsoft 365

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.

1. En la página de aterrizaje, en **Dominios**, seleccione **Dominios registrados**.

1. En **Nombre de** dominio, seleccione el dominio que desea configurar en Microsoft 365.

    **Nota**: Si no ha creado una zona hospedada para su dominio, seleccione Crear zona  hospedada y complete los pasos antes de pasar al paso siguiente.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Nombre de dominio**, seleccione el nombre de dominio para la versión de zona hospedada del dominio que desea comprobar.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Crear registro**.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Seleccione Crear registro.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Elija los **valores de directiva de** tipo **y enrutamiento de** las listas desplegables).

    |Nombre del registro|Tipo de registro|Valor|TTL|Directiva de enrutamiento|
    |:-----|:-----|:-----|:-----|:-----|
    |autodescubrir|CNAME: enruta el tráfico a otro nombre de dominio|autodiscover.outlook.com. <br/> **Este valor DEBE terminar en punto (.)**|300|Simple|

1. Seleccione **Crear registros**.

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="Seleccione Crear registros.":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga  un único registro SPF que incluya ambos conjuntos de valores. ¿Necesita ejemplos? Consulte los [Registros externos del sistema de nombres de dominio para Microsoft](../../enterprise/external-domain-name-system-records.md). Para validar el registro SPF, puede usar una de estas [herramientas de validación deSPF](../setup/domains-faq.yml).

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.

1. En la página de aterrizaje, en **Dominios**, seleccione **Dominios registrados**.

1. En **Nombre de** dominio, seleccione el dominio que desea configurar en Microsoft 365.

    **Nota**: Si no ha creado una zona hospedada para su dominio, seleccione Crear zona  hospedada y complete los pasos antes de pasar al paso siguiente.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Nombre de dominio**, seleccione el nombre de dominio para la versión de zona hospedada del dominio que desea comprobar.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Crear registro**.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Seleccione Crear registro.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Elija el **valor Type** de las listas desplegables).

    |Tipo de registro|Valor|
    |:-----|:-----|
    |TXT: se usa para comprobar remitentes de correo electrónico y para valores específicos de la aplicación|v=spf1 include:spf.protection.outlook.com -all <br/> (Las comillas necesarias por las instrucciones en pantalla aparecen automáticamente. No es necesario escribirlas manualmente).  <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|

1. Seleccione **Crear registros**.

   :::image type="content" source="../../media/dns-aws/aws-domains-txt-create-records.png" alt-text="Seleccione Crear registros.":::

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.

1. En la página de aterrizaje, en **Dominios**, seleccione **Dominios registrados**.

1. En **Nombre de** dominio, seleccione el dominio que desea configurar en Microsoft 365.

    **Nota**: Si no ha creado una zona hospedada para su dominio, seleccione Crear zona  hospedada y complete los pasos antes de pasar al paso siguiente.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Nombre de dominio**, seleccione el nombre de dominio para la versión de zona hospedada del dominio que desea comprobar.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Crear registro**.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Seleccione Crear registro.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Choose the **Type** and **Routing Policy** values from the drop-down lists.)

    |Nombre del registro|Tipo de registro|Valor|TTL (Seconds)|Directiva de enrutamiento|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls|SRV: valores específicos de la aplicación que id servers|100 1 443 sipdir.online.lync.com. **Este valor DEBE terminar con un punto (.)**> <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|300|Simple|
    |_sipfederationtls._tcp|SRV: valores específicos de la aplicación que id servers|100 1 5061 sipfed.online.lync.com. **Este valor DEBE terminar en punto (.)** <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|300|Simple|

1. Para agregar el otro registro SRV, seleccione Agregar otro **registro, cree** un registro con los valores de la siguiente fila de la tabla y, a continuación, vuelva a seleccionar **Crear registros**.

   :::image type="content" source="../../media/dns-aws/aws-domians-srv-create-records.png" alt-text="Seleccione Crear registros.":::

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records"></a>Agregar los dos registros CNAME necesarios

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.

1. En la página de aterrizaje, en **Dominios**, seleccione **Dominios registrados**.

1. En **Nombre de** dominio, seleccione el dominio que desea configurar en Microsoft 365.

    **Nota**: Si no ha creado una zona hospedada para su dominio, seleccione Crear zona  hospedada y complete los pasos antes de pasar al paso siguiente.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Nombre de dominio**, seleccione el nombre de dominio para la versión de zona hospedada del dominio que desea comprobar.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Crear registro**.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Seleccione Crear registro.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Elija los **valores de directiva de** tipo **y enrutamiento de** las listas desplegables).

    |Nombre del registro|Tipo de registro|Valor|TTL|Directiva de enrutamiento|
    |:-----|:-----|:-----|:-----|:-----|
    |sip|CNAME - nombre canónico|sipdir.online.lync.com. <br/> **Este valor DEBE terminar en punto (.)**|300|Simple|
    |lyncdiscover|CNAME - nombre canónico|webdir.online.lync.com. <br/> **Este valor DEBE terminar en punto (.)**|300|Simple|

1. Para agregar el otro registro CNAME, seleccione **Agregar otro** registro, cree un registro con los valores de la siguiente fila de la tabla.

1. Seleccione **Crear registros**.

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="Seleccione Crear registros.":::

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y Mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota dispositivos móviles que se conectan a su dominio. La Administración de dispositivos móvil necesita dos registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Agregue los dos registros CNAME necesarios para mobile Administración de dispositivos

1. Para empezar, vaya a su página de dominios en AWS a través de [este vínculo](https://console.aws.amazon.com/route53/home). Se le pedirá que inicie sesión primero.

1. En la página de aterrizaje, en **Dominios**, seleccione **Dominios registrados**.

1. En **Nombre de** dominio, seleccione el dominio que desea configurar en Microsoft 365.

    **Nota**: Si no ha creado una zona hospedada para su dominio, seleccione Crear zona  hospedada y complete los pasos antes de pasar al paso siguiente.

   :::image type="content" source="../../media/dns-aws/aws-domains-1.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Administrar DNS**.

   :::image type="content" source="../../media/dns-aws/aws-domains-2.png" alt-text="Seleccione Administrar DNS en la lista desplegable.":::

1. En **Nombre de dominio**, seleccione el nombre de dominio para la versión de zona hospedada del dominio que desea comprobar.

   :::image type="content" source="../../media/dns-aws/aws-domains-3.png" alt-text="Seleccione el nombre del dominio.":::

1. Seleccione **Crear registro**.

   :::image type="content" source="../../media/dns-aws/aws-domains-create-record.png" alt-text="Seleccione Crear registro.":::

1. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.

    (Elija los **valores de directiva de** tipo **y enrutamiento de** las listas desplegables).

    |Nombre del registro|Tipo de registro|Valor|TTL|Directiva de enrutamiento|
    |:-----|:-----|:-----|:-----|:-----|
    |enterpriseregistration|CNAME - nombre canónico|enterpriseregistration.windows.net. <br/> **Este valor DEBE terminar en punto (.)**|300|Simple|
    |EnterpriseEnrollment|CNAME - nombre canónico|enterpriseenrollment-s.manage.microsoft.com. <br/> **Este valor DEBE terminar en punto (.).**|300|Simple|

1. Para agregar el otro registro CNAME, seleccione **Agregar otro** registro, cree un registro con los valores de la siguiente fila de la tabla.

1. Seleccione **Crear registros**.

   :::image type="content" source="../../media/dns-aws/aws-domains-cname-create-records.png" alt-text="Seleccione Crear registros.":::

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
