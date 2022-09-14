---
title: Agregar usuarios y asignar licencias en Microsoft 365
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- highpri
- M365-subscription-management
- Adm_O365_Setup
- Adm_TOC
ms.custom:
- VSBFY23
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
- adminvideo
- business_assist
search.appverid:
- MET150
description: Obtenga más información sobre cómo proporcionar a cada miembro del equipo una cuenta de usuario para que pueda tener licencias de Microsoft 365, credenciales de inicio de sesión y buzones de Microsoft 365.
ms.date: 07/01/2020
ms.openlocfilehash: 4f96fb483ab38cc2ea20d80ba5e64592bf5c4c20
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "67662077"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Agregar usuarios y asignar licencias al mismo tiempo

Consulte [Microsoft 365 ayuda de pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

Todos los usuarios de su equipo necesitan una cuenta de usuario para poder iniciar sesión y acceder a [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/business). La forma más sencilla de agregar cuentas de usuario es hacerlo de una en una en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Después de realizar este paso, los usuarios tendrán licencias de Microsoft 365, credenciales de inicio de sesión y buzones de Microsoft 365.

> [!TIP]
> Si necesita ayuda con los pasos descritos en este tema, considere la posibilidad de [trabajar con un especialista de Microsoft Small Business](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser un administrador global, de licencia o de usuario para agregar usuarios y asignar licencias. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-dashboard-view"></a>Ver: Agregar usuarios en la vista del panel

Vea este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198205).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Los pasos usados en el vídeo muestran un punto de partida diferente para agregar usuarios, pero los pasos restantes son los mismos que en el procedimiento siguiente.

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a>Agregar usuarios uno a uno en la vista del panel

:::image type="content" source="../../media/classic-admin-center.png" alt-text="Captura de pantalla: Vista del panel del Centro de administración":::

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <https://admin.microsoft.com>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Vaya a **Usuarios**  >  **Usuarios activos** y seleccione **Agregar un usuario**.
3. En el **Configurar los conceptos básicos** panel, rellene la información básica del usuario y, a continuación, seleccione **Siguiente**.
    - **Nombre** Rellene el nombre y los apellidos, el nombre para mostrar y el nombre de usuario.
    - **Dominio** Elija el dominio para la cuenta del usuario. Por ejemplo, si el nombre de usuario es Pedro y el dominio es contoso.com, iniciarán sesión con pedro@contoso.com.
    - **Configuración de contraseñas** Elija si quiere usar la contraseña autogenerada o crear su propia contraseña segura para el usuario.
    - El usuario deberá cambiar su contraseña después de 90 días. También puede elegir la opción **Requerir que este usuario cambie su contraseña la primera vez que inicie sesión**.
    - Elija si desea enviar la contraseña por correo electrónico cuando se agrega el usuario.
4. En el panel **Asignar licencias de productos**, seleccione la ubicación y la licencia correspondiente para el usuario. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales. Expanda **Aplicaciones**, y active o desactive la selección de aplicaciones para limitar las aplicaciones para las que el usuario tiene licencia. Seleccione **Siguiente**.
5. En el panel **Configuración opcional**, expanda **Roles** para convertir a este usuario en administrador. Expanda **Información del perfil** agregar información adicional sobre el usuario.
6. Seleccione **Siguiente**, revise la configuración del nuevo usuario, realice los cambios que desee y a continuación seleccione **Terminar de agregar** y después **Cerrar**.

## <a name="add-a-user-in-the-admin-simplified-view"></a>Agregar un usuario en la vista simplificada de administración

Si ve esta página en el Centro de administración, se encuentra en la **vista simplificada de administrador**. Siga los pasos siguientes para agregar un usuario.

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="Captura de pantalla: Vista simplificada del Centro de administración":::

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <https://admin.microsoft.com>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Seleccione **Crear una cuenta para otra persona**.
3. En la página **Agregar una cuenta de usuario**, rellene el nombre y los apellidos, el nombre para mostrar y el nombre de usuario que usarán para iniciar sesión.
4. Agregue la dirección de correo electrónico del usuario en el cuadro de texto **Hasta 5 direcciones de correo...**. Esto garantizará que el nuevo usuario obtiene la información que necesita para iniciar sesión en los servicios de Microsoft 365.
5. Seleccione **Agregar usuario** y **Descargar información de inicio de sesión** si quiere guardar esta información.

## <a name="add-multiple-users-at-the-same-time"></a>Agregar varios usuarios al mismo tiempo

Puede usar cualquiera de los siguientes métodos para agregar varios usuarios al mismo tiempo:

- **Use una hoja de cálculo para agregar usuarios en masa.** Consulte [Agregar varios usuarios al mismo tiempo](../../enterprise/add-several-users-at-the-same-time.md).
- **Automatice la adición de cuentas y la asignación de licencias.** Vea [Crear cuentas de usuarios con Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Seleccione este método si ya está familiarizado con el uso de cmdlets de Windows PowerShell.
- **¿Usa Active Directory?** [Configurar la sincronización de directorios para Microsoft 365](../../enterprise/set-up-directory-synchronization.md). Use la herramienta Azure AD Connect para replicar cuentas de usuario de Active Directory (y otros objetos de Active Directory) en Microsoft 365. La sincronización solo agrega las cuentas de usuario. Deberá asignar licencias a los usuarios sincronizados para que puedan usar el correo electrónico y otras aplicaciones de Office.
- **¿Está migrando desde Exchange?** Consulte [Formas de migrar varias cuentas de correo electrónico a Office 365](/Exchange/mailbox-migration/mailbox-migration) Al migrar varios buzones de correo a Microsoft 365 mediante traslado, por etapas o un método de Exchange híbrido, podrá agregar usuarios automáticamente como parte de la migración. La migración solo agrega las cuentas de usuario. Deberá asignar licencias a los usuarios para que puedan usar el correo electrónico y otras aplicaciones de Office. Si no asigna una licencia a un usuario, su buzón se deshabilitará después de un período de gracia de 30 días. Obtenga información sobre cómo [asignar licencias a usuarios](../manage/assign-licenses-to-users.md) en el Centro de administración de Microsoft 365.

## <a name="create-edit-or-delete-custom-user-views"></a>Creación, edición o eliminación de vistas de usuario personalizadas

Si es administrador global o de administración de usuarios de una suscripción de Microsoft 365 para empresas, puede crear hasta 50 vistas de usuario personalizadas para ver subconjuntos de usuarios. Estas vistas se suman al conjunto estándar de vistas. Puede crear, editar o eliminar vistas de usuario personalizadas, y las vistas personalizadas que cree están disponibles para todos los administradores.

Al crear, editar o eliminar una vista de usuario personalizada, los cambios se muestran en la lista **Filtro** que todos los administradores de la empresa ven cuando van a la página **Usuarios** .

> [!TIP]
> Las vistas de usuario estándar se muestran de forma predeterminada en la lista desplegable **Filtros** . Los filtros estándar incluyen **Todos los usuarios**, **Usuarios con licencia**, **Usuarios invitados**,  **Inicio de sesión permitido**, **Inicio de sesión bloqueado**, **Usuarios sin licencia**, **Usuarios con errores**, **Administradores de facturación**, **Administradores globales**, **Administradores del departamento de soporte** técnico, **Administradores de servicio** y **Administradores de administración de usuarios**. No se pueden editar ni eliminar vistas estándar. 

Algunas cosas a tener en cuenta sobre las vistas estándar: 

- Algunas vistas estándar muestran una lista no ordenada si hay más de 2000 usuarios en la lista. Para buscar usuarios específicos en esta lista, use el cuadro de búsqueda. 
- Si no ha comprado Microsoft 365 de Microsoft, **los administradores de facturación** no aparecen en la lista de vistas estándar. Para más información, vea [Asignar roles de administrador](assign-admin-roles.md). 
  
### <a name="choose-the-filters-for-your-custom-user-view"></a>Elija los filtros para la vista de usuario personalizada.

Puede crear y editar las vistas personalizadas en el panel **Filtro personalizado** . Si selecciona varias opciones de filtro, obtendrá resultados que contengan usuarios que coincidan con todos los criterios seleccionados. En el ejemplo siguiente se muestra cómo crear una vista personalizada denominada "Usuarios canadienses" que muestra todos los usuarios de un dominio específico que se encuentran en Canadá. 

 **A: dominio** Si tiene varios dominios para su organización, puede elegir entre una lista desplegable de dominios disponibles. 
  
 **B: estado de inicio de sesión** Elija los usuarios permitidos o bloqueados. 
  
 **C : ubicación** Elija una ubicación en una lista desplegable de países. 
  
 **D: licencia de producto asignada** Elija entre una lista desplegable de licencias disponibles en su organización. Use este filtro para mostrar a los usuarios que tienen asignada la licencia que seleccionó. Los usuarios también pueden tener licencias adicionales. 
  
También puede filtrar por detalles adicionales del perfil de usuario que se usan en su organización, como el departamento, la ciudad, el estado o la provincia, el país o la región o el puesto de trabajo.
  
 **Otras condiciones:**
  
- **Solo usuarios sincronizados** Seleccione este cuadro para mostrar todos los usuarios que se han sincronizado con la instancia local de Active Directory, independientemente de si los usuarios se han activado o no. 

- **Usuarios con errores** Seleccione este cuadro para mostrar los usuarios que pueden tener errores de aprovisionamiento. 

- **Usuarios sin licencia** Seleccione este cuadro para buscar todos los usuarios a los que no se les ha asignado una licencia. Los resultados de esta vista también pueden incluir usuarios que tienen un buzón de Exchange pero no tienen una licencia. Para realizar un seguimiento específico de esos usuarios, use el filtro **Usuarios sin licencia con buzones o archivos de Exchange**. Los resultados de esta vista también pueden incluir usuarios que tienen un archivo de Exchange, pero que no tienen una licencia.

- **Usuarios sin licencia con buzones o archivos de Exchange** Seleccione este cuadro para mostrar las cuentas de usuario que se crearon en Exchange Online y tienen un buzón de Exchange, pero no se les asignó una licencia de Microsoft 365. Los resultados de este filtro incluyen usuarios que tienen o a los que se les asignó un archivo de Exchange. 

> [!NOTE]
> El filtro **Usuarios sin licencia con buzones de Exchange** funciona cuando:

1. El buzón se ha convertido recientemente de **compartido** a **usuario** y no tiene licencia.
2. El buzón de correo se ha migrado recientemente a Microsoft 365, pero no se ha asignado una licencia.
3. El buzón de correo se ha creado mediante PowerShell y no se ha asignado una licencia.
4. Se aprovisiona un nuevo buzón que se ha creado localmente con un cmdlet New-RemoteMailbox para el usuario.

> [!TIP]
> Si crea una vista personalizada que devuelve más de 2000 usuarios, la lista de usuarios resultante no se ordena. En este caso, use el cuadro de búsqueda para buscar usuarios o editar la vista personalizada para refinar la búsqueda. 
  
### <a name="create-a-custom-user-view"></a>Creación de una vista de usuario personalizada

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos</a>.
  
::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">activos</a>.  

::: moniker-end
    
2. En la página **Usuarios activos** , seleccione **Filtros** y seleccione **Nuevo filtro**.
  
3. En la página **Filtro personalizado** , escriba el nombre del filtro, elija las condiciones del filtro personalizado y, a continuación, seleccione **Agregar**. La vista personalizada ahora se incluye en la lista desplegable de filtros.

### <a name="edit-or-delete-a-custom-user-view"></a>Edición o eliminación de una vista de usuario personalizada

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">activos</a>. 

::: moniker-end 
    
2. En la página **Usuarios activos** , seleccione **Filtrar**, seleccione el filtro que desea cambiar y, a continuación, seleccione **Editar filtro**. 
    
    > [!TIP]
    > Solo puede editar vistas personalizadas. 
  
3. En la página **Filtro personalizado** , edite la información según sea necesario y, a continuación, seleccione **Guardar**. O bien, para eliminar el filtro, en la parte inferior de la página, seleccione **Eliminar**.

## <a name="next-steps"></a>Siguientes pasos

Después de agregar un usuario, recibirá un correo electrónico de Microsoft. El correo electrónico contendrá el identificador y la contraseña del usuario para que puedan iniciar sesión en Microsoft 365. Use el proceso habitual para comunicar nuevas contraseñas. Comparta la [Guía de inicio rápido de los empleados](../setup/employee-quick-setup.md) con los nuevos usuarios para configurar opciones como [cómo descargar e instalar aplicaciones de Office en un equipo PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y cómo [configurar el correo electrónico y las aplicaciones de Office en un dispositivo móvil](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenido relacionado

[Agregar un nuevo empleado a Microsoft 365](add-new-employee.md) (artículo)\
[Agregar varios usuarios al mismo tiempo a Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (artículo)\
[Restaurar un usuario en Microsoft 365](restore-user.md) (artículo)\
[Asignar licencias a los usuarios](../manage/assign-licenses-to-users.md) (artículo)\
[Elimine un usuario de su organización](delete-a-user.md) (artículo)
