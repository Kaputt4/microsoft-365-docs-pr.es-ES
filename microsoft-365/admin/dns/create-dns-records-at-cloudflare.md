---
title: Conectar los registros DNS en Cloudflare para Microsoft 365
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea y otros servicios en Cloudflare para Microsoft.
ms.openlocfilehash: 164a681cccac3385d2ca963ac58706c8e743bc1e
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780377"
---
# <a name="connect-your-dns-records-at-cloudflare-to-microsoft-365"></a>Conectar los registros DNS en Cloudflare para Microsoft 365

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si Cloudflare es el proveedor de hospedaje DNS, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial En línea, etc.

## <a name="before-you-begin"></a>Antes de empezar

Tiene dos opciones para configurar registros DNS para el dominio:

- [**Use Dominio Conectar**](#use-domain-connect-to-verify-and-set-up-your-domain) Si no ha configurado el dominio con otro proveedor de servicios de correo electrónico, use los pasos de Conectar dominio para comprobar y configurar automáticamente el nuevo dominio para usarlo con Microsoft 365.

    OR

- [**Siga los pasos manuales.**](#create-dns-records-with-manual-setup) Compruebe el dominio siguiendo los pasos manuales que se indican a continuación y elija cuándo y qué registros se van a agregar al registrador de dominios. Esto le permite configurar nuevos registros MX (correo), por ejemplo, a su conveniencia.

## <a name="use-domain-connect-to-verify-and-set-up-your-domain"></a>Uso de Conectar de dominio para comprobar y configurar el dominio

Siga estos pasos para comprobar y configurar automáticamente el dominio de Cloudflare con Microsoft 365:

1. En el Centro de administración de Microsoft 365, seleccione **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**Dominios**</a> y seleccione el dominio que desea configurar.

1. Seleccione los tres puntos (más acciones) \> y elija **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. En ¿Cómo desea conectar el dominio? página, seleccione **Continuar**.

1. En la página Agregar registros DNS, seleccione **Agregar registros DNS**.

1. En la página de inicio de sesión de Cloudflare, inicie sesión en su cuenta y seleccione **Autorizar**.

    Esto completa la configuración del dominio para Microsoft 365.

## <a name="create-dns-records-with-manual-setup"></a>Creación de registros DNS con configuración manual

Después de agregar estos registros en Cloudflare, el dominio se configurará para trabajar con Microsoft 365 servicios.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="change-your-domains-nameserver-ns-records"></a>Cambiar los registros del servidor de nombres (o NS) de su dominio

> [!IMPORTANT]
> Debe realizar este procedimiento en el registrador de dominios en el que compró y registró su dominio.

Cuando se registró en Cloudflare, agregó un dominio mediante el proceso de instalación de Cloudflare.

El dominio que agregó se compró en Cloudflare o en un registrador de dominios independiente. Para comprobar y crear registros DNS para el dominio en Microsoft 365, primero debe cambiar los servidores de nombres en el registrador de dominios para que usen los servidores de nombres de Cloudflare.

Para cambiar los servidores DNS del dominio en el sitio web del registrador de dominios usted mismo, haga lo siguiente:

1. En el sitio web del registrador de dominios, busque el área donde poder modificar los servidores DNS del dominio.

2. Cree dos registros de servidor de nombres mediante los valores de la tabla siguiente o edite los registros de nameserver existentes para que coincidan con estos valores.

    |Tipo|Valor|
    |---|---|
    |Primer servidor de nombres|Use el valor nameserver proporcionado por Cloudflare.|
    |Segundo servidor de nombres|Use el valor nameserver proporcionado por Cloudflare.|

    > [!TIP]
    > You should use at least two name server records. Si aparece algún otro servidor de nombres, debe eliminarlos.

3. Guarde los cambios.

> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. A continuación, el correo electrónico de Microsoft y otros servicios estarán configurados para que funcionen con su dominio.

### <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de utilizar el dominio con Microsoft, tenemos que asegurarnos de que sea el propietario. Si puede iniciar sesión en la cuenta en el registrador de dominio y crear el registro DNS, Microsoft sabrá que es el propietario del dominio.

> [!NOTE]
> Este registro se usa exclusivamente para verificar si se es el propietario de un dominio; no afecta a nada más. Puede eliminarlo más adelante, si lo desea.

1. Para empezar, vaya a la página de dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .

1. En la página Inicio, seleccione el dominio que desea actualizar.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::

1. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

1. En la página Administración de DNS, seleccione **+Agregar registro**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione el tipo TXT de la lista desplegable y escriba o copie y pegue los valores de esta tabla.

    |Tipo|Nombre|TTL|Contenido|
    |---|---|---|:----|
    |TXT|@|30 minutos|MS=*msXXXXXXXX* <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-TXT-save.png" alt-text="Seleccione Agregar registro.":::

   Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

Ahora que ha agregado el registro en el sitio del registrador de dominios, volverá a Microsoft y buscará el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.

Para comprobar el registro en Microsoft 365:

1. En el centro de administración, vaya a dominios **de Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**.**</a>

1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. Seleccione **Continuar**.

1. En la página **verificar dominio**, seleccione **verificar**.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a la página de dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .

1. En la página Inicio, seleccione el dominio que desea actualizar.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::

1. En la página Información general del dominio, seleccione **DNS**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

1. En la página Administración de DNS, seleccione **+Agregar registro**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione el tipo MX en la lista desplegable y escriba o copie y pegue los valores de esta tabla.

   |Tipo|Nombre|Servidor de correo|TTL|Prioridad|
   |---|---|---|---|---|
   |MX|@|*\<domain-key\>*.mail.protection.outlook.com <br/> **Nota:** Obtenga su *\<domain-key\>* de su cuenta de Microsoft 365. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|30 minutos|1 <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml) <br/>|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-mx-save.png" alt-text="Seleccione Agregar registro.":::

1. Si hay otros registros MX enumerados en la sección **Registros MX** , elimínelos seleccionando **Editar** y, a continuación, seleccione **Eliminar**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-mx-delete.png" alt-text="Seleccione Eliminar.":::

1. En el cuadro de diálogo de confirmación, seleccione **Eliminar** para confirmar los cambios.

### <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página de dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .

1. En la página Inicio, seleccione el dominio que desea actualizar.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::

1. En la página Información general del dominio, seleccione **DNS**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

1. En la página **Administración de DNS**, seleccione **+Agregar registro**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione el tipo CNAME en la lista desplegable y escriba o copie y pegue los valores de esta tabla.

    |Tipo|Nombre|Target|TTL|
    |---|---|---|---|
    |CNAME|autodescubrir|autodiscover.outlook.com|Automático|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="Seleccione Guardar.":::

### <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365. En su lugar, agregue los valores de Microsoft 365 necesarios al registro actual para que tenga un *único* registro SPF que incluya ambos conjuntos de valores.

1. Para empezar, vaya a la página de dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .

1. En la página Inicio, seleccione el dominio que desea actualizar.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::

1. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

1. En la página Administración de DNS, seleccione **+Agregar registro**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione el tipo TXT de la lista desplegable y escriba o copie y pegue los valores de esta tabla.

    |Tipo|Nombre|TTL|Contenido|
    |---|---|---|---|
    |TXT|@|30 minutos|v=spf1 include:spf.protection.outlook.com -all <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-TXT-save.png" alt-text="Seleccione Guardar.":::

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea, como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita 4 registros: 2 registros SRV para la comunicación de usuario a usuario y 2 registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

> [!IMPORTANT]
> Tenga en cuenta que Cloudflare es responsable de que esta funcionalidad esté disponible. En caso de que vea discrepancias entre los pasos siguientes y la GUI de Cloudflare actual (interfaz gráfica de usuario), aproveche el [Community de Cloudflare](https://community.cloudflare.com/).

1. Para empezar, vaya a la página de dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .

1. En la página Inicio, seleccione el dominio que desea actualizar.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::

1. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

1. En la página Administración de DNS, seleccione **+Agregar registro**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione el tipo SRV en la lista desplegable y escriba o copie y pegue los valores de esta tabla.

    |Tipo|Nombre|Servicio|Protocolo|TTL|Prioridad|Peso|Puerto|Target|
    |---|---|---|---|---|---|---|---|---|
    |SRV|Use su *domain_name*; por ejemplo, contoso.com|_sip|TLS|30 minutos|100|1|443|sipfed.online.lync.com|
    |SRV|_sipfederationtls|TCP|Use su *domain_name*; por ejemplo, contoso.com|30 minutos|100|1|5061|sipfed.online.lync.com|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-srv-save.png" alt-text="Seleccione Guardar.":::

1. Agregue el otro registro SRV copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Agregue los dos registros CNAME necesarios para Skype Empresarial

1. Para empezar, vaya a la página de dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .

1. En la página Inicio, seleccione el dominio que desea actualizar.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::

1. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

1. En la página Administración de DNS, seleccione **+Agregar registro**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione el tipo CNAME en la lista desplegable y escriba o copie y pegue los valores de esta tabla.

    |Tipo|Nombre|Target|TTL|
    |---|---|---|---|
    |CNAME|sip|sipdir.online.lync.com. <br/> **Este valor DEBE terminar en punto (.)**|1 hora|
    |CNAME|lyncdiscover|webdir.online.lync.com. <br/> **Este valor DEBE terminar en punto (.)**|1 Hour|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="Seleccione Guardar.":::

1. Agregue el otro registro CNAME copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota los dispositivos móviles que se conectan a su dominio. Mobile Administración de dispositivos necesita 2 registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Agregue los dos registros CNAME necesarios para Mobile Administración de dispositivos

1. Para empezar, vaya a la página de dominios de Cloudflare mediante [este vínculo](https://www.cloudflare.com/a/login). Se le pedirá que inicie sesión primero .

1. En la página Inicio, seleccione el dominio que desea actualizar.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-1.png" alt-text="Seleccione el dominio que desea actualizar.":::

1. En la página Información general del dominio, seleccione **DNS**.

    :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-2.png" alt-text="Seleccione DNS.":::

1. En la página Administración de DNS, seleccione **+Agregar registro**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-add-record.png" alt-text="Seleccione Agregar registro.":::

1. Seleccione el tipo CNAME en la lista desplegable y escriba o copie y pegue los valores de esta tabla.

    |Tipo|Nombre|Target|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net. <br/> **Este valor DEBE terminar en punto (.)**|1 hora|
    |CNAME|enterpriseenrollment|enterpriseenrollment-s.manage.microsoft.com. <br/> **Este valor DEBE terminar en punto (.).**|1 Hour|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-cloudflare/cloudflare-domains-cname-save.png" alt-text="Seleccione Guardar.":::

1. Agregue el otro registro CNAME copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
