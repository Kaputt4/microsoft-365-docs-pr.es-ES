---
title: Administrar permite y bloquea en la lista de permitidos o bloqueados de inquilinos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Obtenga información sobre cómo administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dc32e6827e9751dc72d28b8eff79d1966f43f646
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2022
ms.locfileid: "66159963"
---
# <a name="manage-your-allows-and-blocks-in-the-tenant-allowblock-list"></a>Administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones de correo en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, es posible que no esté de acuerdo con el veredicto de filtrado de EOP. Por ejemplo, un buen mensaje podría marcarse como incorrecto (un falso positivo) o un mensaje incorrecto podría permitirse a través de (un falso negativo).

La lista de permitidos o bloqueados de inquilinos del portal de Microsoft 365 Defender proporciona una manera de invalidar manualmente los veredictos de filtrado de Microsoft 365. La lista de permitidos o bloqueados de inquilinos se usa durante el flujo de correo para los mensajes entrantes (no se aplica a los mensajes dentro de la organización) y en el momento en que el usuario hace clic. Puede especificar los siguientes tipos de invalidaciones:

- Direcciones URL que se van a bloquear.
- Archivos que se van a bloquear.
- Correos electrónicos o dominios del remitente que se van a bloquear.
- Remitentes suplantados para permitir o bloquear. Si invalida el veredicto de permitir o bloquear en la [información de inteligencia](learn-about-spoof-intelligence.md) sobre suplantación de identidad, el remitente suplantado se convierte en una entrada de bloqueo o permiso manual que solo aparece en la pestaña **Suplantación** de identidad de la lista de permitidos o bloqueados de inquilinos. También puede crear manualmente entradas de permitir o bloquear para remitentes suplantados aquí antes de que se detecten mediante inteligencia de suplantación de identidad.
- Direcciones URL que se van a permitir.
- Archivos que se van a permitir.
- Dominios o correos electrónicos del remitente que se van a permitir.

En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin Exchange Online buzones).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

- Los archivos se especifican mediante el valor hash SHA256 del archivo. Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`. No se admiten los valores de hash perceptual (pHash).

- En el caso de remitentes, direcciones URL y hashes de archivos, la lista de permitidos y bloques de inquilinos permite 500 entradas cada una para los bloques y permite, lo que lo convierte en un total de 1000 entradas. Para la suplantación de identidad (remitentes suplantados), el número total de entradas permitidas es 1024.

- El número máximo de caracteres para cada entrada es:
  - Hash de archivo = 64
  - URL = 250

- Una entrada debe estar activa en un plazo de 30 minutos.

- De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días. Puede especificar una fecha o establecerla para que nunca expire (para el tipo de bloque de entradas).

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).

- Debe tener permisos asignados en Exchange Online antes de poder realizar los procedimientos de este artículo:
  - Para agregar y quitar valores de la lista de permitidos o bloqueados de inquilinos, debe ser miembro de
    - **Grupo de roles Administración de la organización** o **Administrador de seguridad** (**rol administrador de seguridad**)
    - **Grupo de roles Operador de seguridad** (**Administrador de listas de permitidos de inquilinos**).
  - Para obtener acceso de solo lectura a la lista de permitidos o bloqueados de inquilinos, debe ser miembro de
    - **Grupo de roles lector global**
    - **Grupo de roles lector de seguridad**
    - **Grupo de roles de configuración de solo vista**

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios *y* los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="configure-the-tenant-allowblock-list"></a>Configuración de la lista de permitidos o bloqueados de inquilinos

### <a name="use-the-microsoft-365-defender-portal"></a>Uso del portal de Microsoft 365 Defender

En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas Listas **de inquilinos permitidos o bloqueados** en la sección **Reglas**. Para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell"></a>Uso Exchange Online PowerShell o PowerShell de EOP independiente

Para permitir o bloquear correos electrónicos, consulte [Permitir o bloquear correos electrónicos mediante la Lista de permitidos o bloqueados de inquilinos](allow-block-email-spoof.md).

Para permitir o bloquear archivos, consulte [Permitir o bloquear archivos mediante la Lista de inquilinos permitidos o bloqueados](allow-block-files.md).

Para permitir o bloquear direcciones URL, consulte [Permitir o bloquear direcciones URL mediante la Lista de permitidos o bloqueados de inquilinos](allow-block-urls.md).

### <a name="what-to-expect-after-you-add-an-allow-or-block-entry"></a>Qué esperar después de agregar una entrada de permitir o bloquear

Después de agregar una entrada de permitir a través del portal envíos o una entrada de bloque en la lista de permitidos o bloqueados de inquilinos, la entrada debería empezar a funcionar inmediatamente.

Se recomienda permitir que las entradas expiren automáticamente después de 30 días para ver si el sistema ha obtenido información sobre el permiso o el bloque. Si no es así, debe realizar otra entrada para dar al sistema otros 30 días para aprender.

## <a name="view-entries-in-the-tenant-allowblock-list"></a>Visualización de entradas en la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas Listas **de inquilinos permitidos o bloqueados** en la sección **Reglas**. O bien, para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña que desee. Las columnas que están disponibles dependen de la pestaña seleccionada:

   - **Remitentes**:
     - **Valor**: dominio o dirección de correo electrónico del remitente.
     - **Acción**: el valor **Permitir** o **Bloquear**.
     - **Modificado por**
     - **Actualizado por última vez**
     - **Quitar activado**
     - **Notas**
   - **Spoofing**
     - **Usuario con identidad suplantada**
     - **Infraestructura de envío**
     - **Tipo de suplantación:** el valor **Interno** o **Externo**.
     - **Acción**: el valor **Bloquear** o **Permitir**.
   - **Direcciones URL**:
     - **Valor**: la dirección URL.
     - **Acción**: el valor **Permitir** o **Bloquear**.
     - **Modificado por**
     - **Actualizado por última vez**
     - **Quitar activado**
     - **Notas**
   - **Files**
     - **Valor**: el hash de archivo.
     - **Acción**: el valor **Permitir** o **Bloquear**.
     - **Modificado por**
     - **Actualizado por última vez**
     - **Quitar activado**
     - **Notas**

   Puede hacer clic en un encabezado de columna para ordenar en orden ascendente o descendente.

   Puede hacer clic en **Agrupar** para agrupar los resultados. Los valores que están disponibles dependen de la pestaña seleccionada:

   - **Remitentes**: puede agrupar los resultados por **acción**.
   - **Suplantación de identidad**: puede agrupar los resultados por **tipo de acción** o **suplantación de identidad**.
   - **Direcciones URL**: puede agrupar los resultados por **acción**.
   - **Archivos**: puede agrupar los resultados por **acción**.

   Haga clic en **Buscar**, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico. Cuando haya terminado, haga clic en ![el icono Borrar búsqueda.](../../media/m365-cc-sc-close-icon.png) **Borrar búsqueda**.

   Haga clic en **Filtrar** para filtrar los resultados. Los valores que están disponibles en el control flotante **Filtro** que aparece dependen de la pestaña seleccionada:

   - **Remitentes**
     - **Action**
     - **Nunca expirar**
     - **Fecha de última actualización**
     - **Quitar activado**
   - **Spoofing**
     - **Action**
     - **Tipo de suplantación de identidad**
   - **Url**
     - **Action**
     - **Nunca expirar**
     - **Fecha de última actualización**
     - **Quitar activado**
   - **Files**
     - **Action**
     - **Nunca expirar**
     - **Actualizado por última vez**
     - **Quitar activado**

   Cuando haya terminado, haga clic en **Aplicar**. Para borrar los filtros existentes, haga clic en **Filtrar** y, en el control flotante **Filtro** que aparece, haga clic en **Borrar filtros**.

## <a name="modify-entries-in-the-tenant-allowblock-list"></a>Modificar entradas en la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña que contiene el tipo de entrada que desea modificar:
   - **Remitentes**
   - **Spoofing**
   - **Url**
   - **Files**

3. Seleccione la entrada que desea modificar y, a continuación, haga clic en ![el icono Editar.](../../media/m365-cc-sc-edit-icon.png) **Edición**. Los valores que puede modificar en el control flotante que aparece dependen de la pestaña seleccionada en el paso anterior:
   - **Remitentes**
     - **Nunca expire** ni la fecha de expiración.
     - **Nota opcional**
   - **Spoofing**
     - **Acción**: puede cambiar el valor a **Permitir** o **Bloquear**.
   - **Url**
     - **Nunca expire** ni la fecha de expiración.
     - **Nota opcional**
   - **Files**
     - **Nunca expire** ni la fecha de expiración.
     - **Nota opcional**

    Tenga en cuenta que los valores de los remitentes, las direcciones URL y los archivos nunca expiran solo para las entradas bloqueadas. 

4. Cuando haya terminado, haga clic en **Guardar**.

> [!NOTE]
> Solo puede ampliar los plazos durante un máximo de 30 días después de la fecha de creación. Los bloques se pueden extender hasta 90 días, pero a diferencia de lo que permite, también se pueden establecer en Nunca expirar.

## <a name="remove-entries-from-the-tenant-allowblock-list"></a>Eliminación de entradas de la lista de permitidos o bloqueados de inquilinos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. Seleccione la pestaña que contiene el tipo de entrada que desea quitar:
   - **Remitentes**
   - **Spoofing**
   - **Url**
   - **Files**

3. Seleccione la entrada que desea quitar y, a continuación, haga clic en ![el icono Eliminar.](../../media/m365-cc-sc-delete-icon.png) **Delete**.

4. En el cuadro de diálogo de advertencia que aparece, haga clic en **Eliminar**.

## <a name="related-articles"></a>Artículos relacionados

- [Permitir o bloquear archivos en la lista de inquilinos permitidos o bloqueados](allow-block-files.md)
- [Permitir o bloquear correos electrónicos en la lista de permitidos o bloqueados de inquilinos](allow-block-email-spoof.md)
- [Permitir o bloquear direcciones URL en la lista de permitidos o bloqueados de inquilinos](allow-block-urls.md)