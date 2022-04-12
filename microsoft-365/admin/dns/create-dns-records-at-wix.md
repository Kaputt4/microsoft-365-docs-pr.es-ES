---
title: Conectar los registros DNS en Wix para Microsoft 365
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Obtenga información sobre cómo comprobar su dominio y configurar registros DNS para correo electrónico, Skype Empresarial En línea y otros servicios en Wix para Microsoft.
ms.openlocfilehash: 58d7819e006183a35272811ed791d3236f9fc742
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780332"
---
# <a name="connect-your-dns-records-at-wix-to-microsoft-365"></a>Conectar los registros DNS en Wix para Microsoft 365

**[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.yml)** si no encuentra lo que busca.

Si Wix es el proveedor de hospedaje dns, siga los pasos de este artículo para comprobar el dominio y configurar los registros DNS para el correo electrónico, Skype Empresarial en línea, etc.

Después de agregar estos registros en Wix, el dominio se configurará para trabajar con servicios Microsoft.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Agregar un registro TXT para verificación

Antes de usar su dominio con Microsoft, debemos asegurarnos de que lo posee. La capacidad de iniciar sesión en su cuenta en el registrador de dominios y crear el registro DNS demuestra a Microsoft que es el propietario del dominio.

> [!NOTE]
> Este registro solo se utiliza para comprobar que usted es el propietario del dominio; no afecta a nada más. Puede eliminarlo más adelante si lo desea.

> [!NOTE]
> WIX no admite entradas DNS para subdominios.

1. Para empezar, vaya a la página de dominios en Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .

2. Seleccione **Dominios** \> **...** y, a continuación, seleccione **Administrar registros DNS** en la lista desplegable.

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

3. Seleccione **+ Agregar registro** en la fila **TXT (texto)** del editor DNS.

   :::image type="content" source="../../media/dns-wix/wix-domains-TXT-add-record.png" alt-text="Seleccione Agregar registro.":::

4. In the boxes for the new record, type or copy and paste the values from the following table.

   |Nombre de host|TXT Value|TTL|
   |---|---|---|
   |Rellenado automáticamente (deje en blanco)|MS=*msXXXXXXXX* <br/> **Nota:** esto es un ejemplo. Utilice aquí su valor de **Dirección de destino**, desde la tabla. [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)|1 hora|

5. **SeleccioneGuardar**.

   :::image type="content" source="../../media/dns-wix/wix-domains-txt-save.png" alt-text="Seleccione Guardar.":::

   Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.


Ahora que ha agregado el registro en el sitio de su registrador de dominios, deberá volver a Microsoft y solicitar el registro. Cuando Microsoft encuentre el registro TXT correcto, se comprobará su dominio.

Para comprobar el registro en Microsoft 365:

1. En el centro de administración, vaya a dominios **de Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**.**</a>

1. En la página Dominios, seleccione el dominio que está comprobando y seleccione **Iniciar configuración**.

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="Seleccione Iniciar configuración.":::

1. Seleccione **Continuar**.

1. En la página **verificar dominio**, seleccione **verificar**.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

1. Para empezar, vaya a la página de dominios en Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .

1. Seleccione **Dominios** \> **...** y, a continuación, seleccione **Administrar registros DNS** en la lista desplegable.

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

1. En **MX (Intercambio de correo),** seleccione **Editar registros MX**.

   :::image type="content" source="../../media/dns-wix/wix-domains-edit-mx-records.png" alt-text="Seleccione Editar registros MX.":::

1. Elija **Otro** en la lista desplegable y seleccione **+ Agregar registro**.

   :::image type="content" source="../../media/dns-wix/wix-domains-other.png" alt-text="Seleccione Otro en la lista desplegable.":::

1. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:

   |Nombre de host|Points to |Prioridad|TTL|
   |---|---|---|---|
   |Rellenado automáticamente|*\<domain-key\>*.mail.protection.outlook.com <br/> **Nota:** Obtenga su *\<domain-key\>* de su cuenta Microsoft.  [¿Cómo puedo encontrarla?](../get-help-with-domains/information-for-dns-records.md)|0 <br/> Para obtener más información sobre la prioridad, consulte [¿Qué es una prioridad de MX?](../setup/domains-faq.yml)|1 hora|

1. Si aparece algún otro registro MX, elimine cada uno de ellos.

  :::image type="content" source="../../media/dns-wix/wix-domains-mx-delete.png" alt-text="Seleccione Eliminar.":::

1. Seleccione **Guardar**.

## <a name="add-the-cname-record-required-for-microsoft"></a>Agregar el registro CNAME necesario para Microsoft

1. Para empezar, vaya a la página de dominios en Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .

2. Seleccione **Dominios** \> **...** y, a continuación, seleccione **Administrar registros DNS** en la lista desplegable.

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

3. Seleccione **+ Agregar registro** en la fila **CNAME (alias)** del editor DNS para el registro CNAME.

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-add-record.png" alt-text="Seleccione + Agregar registro.":::

4. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:

   |Nombre de host|Valor|TTL|
   |---|---|---|
   |autodescubrir|autodiscover.outlook.com|1 hora|

5. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="Seleccione Guardar.":::

   Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Agregar un registro TXT para SPF para ayudar a prevenir el spam de correo electrónico

> [!IMPORTANT]
> No puede tener más de un registro TXT para el SPF de un dominio. Si su dominio tiene más de un registro de SPF, obtendrá errores de correo, así como problemas de clasificación de entrega y de correo no deseado. Si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft. En su lugar, agregue los valores de Microsoft necesarios al registro actual para que tenga un *único* registro SPF que incluya ambos conjuntos de valores.

1. Para empezar, vaya a la página de dominios en Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .

2. Seleccione **Dominios** \> **...** y, a continuación, seleccione **Administrar registros DNS** en la lista desplegable.

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

3. Seleccione **+ Agregar registro** en la fila **TXT (texto)** del editor DNS.

   :::image type="content" source="../../media/dns-wix/wix-domains-TXT-add-record.png" alt-text="Seleccione + Agregar registro.":::

   **Nota**: Wix proporciona una fila SPF en el editor DNS. Omita esa fila y use la fila **TXT (Texto)** para escribir los valores de SPF siguientes.

4. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la tabla siguiente:

   |Nombre de host|Valor|TTL|
   |---|---|---|
   |[deje esto en blanco]|v=spf1 include:spf.protection.outlook.com -all <br/> **Nota:** recomendamos copiar y pegar esta entrada, para que todo el espacio sea correcto.|1 Hour|

5. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-wix/wix-domains-txt-save.png" alt-text="Seleccione Guardar.":::

   Espere unos minutos antes de continuar para que el registro que acaba de crear pueda actualizarse en Internet.

## <a name="advanced-option-skype-for-business"></a>Opción avanzada: Skype Empresarial

Solo seleccione esta opción si su organización usa Skype Empresarial para servicios de comunicación en línea, como chat, llamadas de conferencia y videollamadas, además de Microsoft Teams. Skype necesita cuatro registros: dos registros SRV para la comunicación de usuario a usuario y dos registros CNAME para iniciar sesión y conectar usuarios al servicio.

### <a name="add-the-two-required-srv-records"></a>Agregar los dos registros SRV necesarios

1. Para empezar, vaya a la página de dominios en Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .

1. Seleccione **Dominios** \> **...** y, a continuación, seleccione **Administrar registros DNS** en la lista desplegable.

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

1. Seleccione **+ Agregar registro** en la fila **SRV** del editor DNS.

   :::image type="content" source="../../media/dns-wix/wix-domains-srv-add-record.png" alt-text="Seleccione + Agregar registro.":::

1. En los cuadros del nuevo registro, escriba o copie y pegue los valores de la primera fila de la tabla:

   |Servicio|Protocolo|Nombre de host|Peso|Puerto|Target|Prioridad|TTL|
   |---|---|---|---|---|---|---|---|
   |sip|tls|Rellenado automáticamente|1|443|sipdir.online.lync.com|100|1 Hour|
   |sipfed|tcp|Rellenado automáticamente|1|5061|sipfed.online.lync.com|100|1 Hour|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-wix/wix-domains-srv-save.png" alt-text="Seleccione Guardar.":::

1. Agregue el otro registro SRV copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Normalmente, se necesitan unos 15 minutos para que los cambios de DNS surtan efecto. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, vea [Encontrar y solucionar problemas después de agregar el dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

### <a name="add-the-two-required-cname-records-for-skype-for-business"></a>Agregue los dos registros CNAME necesarios para Skype Empresarial

1. Seleccione **+ Agregar otro** en la fila **CNAME (alias)** del editor DNS y escriba los valores de la primera fila de la tabla siguiente.

   |Tipo|Host|Valor|TTL|
   |---|---|---|---|
   |CNAME|sip|sipdir.online.lync.com. <br/> **Este valor DEBE terminar en punto (.)**|1 hora|
   |CNAME|lyncdiscover|webdir.online.lync.com. <br/> **Este valor DEBE terminar en punto (.)**|1 Hour|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="Seleccione Guardar.":::

1. Agregue el otro registro CNAME copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>Opción avanzada: Intune y mobile Administración de dispositivos para Microsoft 365

Este servicio le ayuda a proteger y administrar de forma remota los dispositivos móviles que se conectan a su dominio. Mobile Administración de dispositivos necesita dos registros CNAME para que los usuarios puedan inscribir dispositivos en el servicio.

### <a name="add-the-two-required-cname-records-for-mobile-device-management"></a>Agregue los dos registros CNAME necesarios para Mobile Administración de dispositivos

1. Para empezar, vaya a la página de dominios en Wix mediante [este vínculo](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Se le pedirá que inicie sesión primero .

1. Seleccione **Dominios** \> **...** y, a continuación, seleccione **Administrar registros DNS** en la lista desplegable.

   :::image type="content" source="../../media/dns-wix/wix-domains-1.png" alt-text="Seleccione Administrar registros DNS en la lista desplegable.":::

1. Seleccione **+ Agregar registro** en la fila **CNAME (alias)** del editor DNS para el registro CNAME.

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-add-record.png" alt-text="Seleccione + Agregar registro.":::

1. Escriba los valores de la primera fila de la tabla siguiente.

    |Tipo|Host|Valor|TTL|
    |---|---|---|---|
    |CNAME|enterpriseregistration|enterpriseregistration.windows.net. <br/> **Este valor DEBE terminar en punto (.)**|1 hora|
    |CNAME|enterpriseenrollment|enterpriseenrollment.manage.microsoft.com. <br/> **Este valor DEBE terminar en punto (.).**|1 Hour|

1. Seleccione **Guardar**.

   :::image type="content" source="../../media/dns-wix/wix-domains-cname-save.png" alt-text="Seleccione Guardar.":::

1. Agregue el otro registro CNAME copiando los valores de la segunda fila de la tabla.

> [!NOTE]
> Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md).
