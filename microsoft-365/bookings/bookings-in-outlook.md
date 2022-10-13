---
title: Bookings conmigo
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.collection:
- scotvorg
ROBOTS: NO INDEX, NO FOLLOW
description: Use Bookings conmigo para permitir que otros usuarios programe reuniones con usted en Outlook.
ms.openlocfilehash: 7eea946472e94fb6d4e2ae144a1127a6b8e09c72
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2022
ms.locfileid: "68565496"
---
# <a name="bookings-with-me"></a>Bookings conmigo

**Bookings with me** in Outlook es una página de programación personal basada en web que se integra con la información de disponibilidad de su calendario de Outlook. Bookings with me permite a las personas programar una reunión o cita con usted. Puede crear tipos de reunión personalizados para compartirlos con otros usuarios para que puedan programar fácilmente tiempo con usted en función de su disponibilidad y preferencias. Ambos reciben una confirmación por correo electrónico y los asistentes pueden actualizar o cancelar reuniones programadas con usted desde la página Reservas conmigo.

Bookings with me tiene dos vistas diferentes:

- [Reservas conmigo: configuración y uso compartido](https://support.microsoft.com/office/bookings-with-me-setup-and-sharing-ad2e28c4-4abd-45c7-9439-27a789d254a2) Una página de reserva personal donde puede crear tipos de reunión que otros usuarios pueden reservar con usted. Los tipos de reunión personalizados le ofrecen la capacidad de personalizar cuándo desea reunirse y cómo se comparte ese tipo de reunión con otros usuarios. Puede controlar si cada tipo de reunión es público en la página de programación o si es privado y solo puede acceder a él un grupo de personas seleccionado. También puede elegir agregar una reunión de Teams a todas las reuniones reservadas a través de la página Reservas conmigo. Puedes acceder a tu página de Bookings with me a través de Outlook en la Web. Después de configurar la página y publicarla, puede compartirla con otros usuarios. Por ejemplo, puede agregarlo a la firma de Outlook.

- [Vista de asistentes](https://support.microsoft.com/office/select-a-meeting-time-in-bookings-with-me-8f3bbe5b-4bc6-4073-bf61-57383c00b43a) Cuando compartas tu página de Bookings conmigo con otros usuarios, verán la vista de asistentes. Si el organizador ha compartido su vínculo de página Reservas conmigo contigo, podrás ver todos sus tipos de reuniones públicas. Si el organizador ha compartido un vínculo de reunión, solo podrá ver esa reunión.
  - Las reuniones públicas pueden ser vistas y programadas por cualquier persona que tenga el vínculo de la página Reservas conmigo. Tiene el control de con quién comparte ese vínculo. Todos los tipos de reuniones públicas serán visibles para cualquier persona que tenga el vínculo de la página Bookings with me .
  - Las reuniones privadas solo las pueden ver las personas que tienen el vínculo para ese tipo de reunión. La diferencia entre las reuniones públicas y las privadas es que las reuniones privadas pueden tener vínculos diferentes y los vínculos expiran después de 90 días. También puede establecer vínculos privados para que expiren después de una reserva única. Al acceder a la vista de programación de una reunión privada, solo estará visible ese tipo de reunión.

## <a name="when-to-use-bookings-with-me"></a>Cuándo usar Bookings conmigo

Bookings with me es una solución ideal para empresas, pequeñas empresas y usuarios en educación para programar reuniones 1:1 con aquellos que están fuera y dentro de sus organizaciones. A continuación se muestran algunos ejemplos de cómo puede usar Bookings conmigo.

- Programar entrevistas con candidatos externos
- Configuración de reuniones de clientes y clientes
- Programación del soporte técnico
- Configuración del horario de oficina
- Configurar horas de mentoría
- 1:1 reuniones con informes directos
- Pausas para el almuerzo y el café

## <a name="before-you-begin"></a>Antes de empezar

Las reservas conmigo se pueden activar o desactivar para toda la organización o para usuarios específicos. Al activar Bookings para los usuarios, pueden crear una página de Bookings, compartir su página con otros usuarios y permitir que otras personas reserven tiempo con ellos. Este artículo está destinado a propietarios y administradores que administran Bookings conmigo para sus organizaciones.

Reservas conmigo está disponible en las siguientes suscripciones:

- Office 365: A3, A5, E1, E3, E5, F1, F3
- Microsoft 365: A3, A5, E1, E3, E5, F1, F3, Business Basic, Business Standard, Business Premium

Las reservas conmigo están activadas de forma predeterminada para los usuarios con estas suscripciones.

Bookings with me necesita el **Microsoft Bookings App (plan de servicio)** asignado a los usuarios para que puedan acceder a Bookings. Los administradores de inquilinos pueden habilitar o deshabilitar este plan de servicio. Por lo tanto, si no se les asigna **Microsoft Bookings**, el acceso a Bookings se denegará a los usuarios incluso si se encuentran en una de las SKU enumeradas anteriormente.

Para obtener más información, consulte el [artículo Bookings with me Microsoft 365 Roadmap (Bookings with me Microsoft 365 Roadmap).](https://go.microsoft.com/fwlink/?linkid=328648)

### <a name="prerequisites-for-using-bookings-with-me"></a>Requisitos previos para usar Bookings conmigo

1. Bookings conmigo y Bookings comparten el mismo modelo de licencia. Sin embargo, Bookings no tiene que estar activado para la organización mediante la configuración del inquilino para que los usuarios accedan a Bookings conmigo. La aplicación Bookings debe estar habilitada para que los usuarios tengan acceso a Bookings conmigo.

   Para activar Bookings with me sin acceso a Bookings, bloquee el acceso a Microsoft Bookings mediante el [comando de PowerShell de la directiva de buzón de correo de OWA](/powershell/module/exchange/set-owamailboxpolicy) o siga las instrucciones que aparecen aquí: [Activar o desactivar Microsoft Bookings](turn-bookings-on-or-off.md).

2. El uso compartido anónimo de Calendar FreeBusy debe estar habilitado para usar Bookings conmigo. Esto permite que la página Bookings tenga acceso a la información de disponibilidad en el calendario de Outlook. Use PowerShell para comprobar el estado.

   ```PowerShell
     Get-SharingPolicy -Identity "Default Sharing Policy" | fl Domains 
   ```

    Anonymous:SharingPolicyAction debe ser uno de los dominios de la respuesta. El valor sharingPolicyAction puede ser CalendarSharingFreeBusySimple, CalendarSharingFreeBusyDetail o CalendarSharingFreeBusyReviewer (valor predeterminado).

   Para habilitar el uso compartido anónimo, use el siguiente comando.

   ```PowerShell
     Set-SharingPolicy "Default Sharing Policy" -Domains @{Add="Anonymous:CalendarSharingFreeBusySimple"}
   ```
3.  Para los buzones a los que se les asigna una propiedad SharingPolicy personalizada, la directiva debe tener Anonymous:SharingPolicyActio como uno de los dominios.

   ```Powershell:
      get-mailbox adam@contoso.com | Format-List SharingPolicy
   ```

   Si el comando devuelve:

   `SharingPolicy        : "contoso.onmicrosoft.com\Default Sharing (CONTOSO)"`

   Debe actualizar la directiva con uno de los dominios necesarios:

   ```Powershell
   Set-SharingPolicy "Default Sharing (CONTOSO)" -Domains @{Add="Anonymous:CalendarSharingFreeBusySimple"}
   ```

Para obtener más información, vea [Set-SharingPolicy](/powershell/module/exchange/set-sharingpolicy).

## <a name="turn-bookings-with-me-on-or-off"></a>Activar o desactivar Bookings with me

Las reservas conmigo se pueden activar o desactivar para toda la organización o usuarios específicos. Cuando Bookings with me está activado, los usuarios pueden crear una página bookings with me y compartir vínculos con otros usuarios dentro o fuera de su organización.

### <a name="turn-bookings-with-me-on-or-off-for-your-organization-using-powershell"></a>Activar o desactivar Bookings with me para su organización mediante PowerShell

Tendrá que ejecutar los siguientes comandos mediante Exchange Online PowerShell. Para obtener más información sobre cómo ejecutar cmdlets de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Para activar o desactivar Bookings with me para su organización mediante el cmdlet de PowerShell [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecute los siguientes comandos.

Use los comandos **Get-OrganizationConfig** y **Set-OrganizationConfig** para averiguar el estado y activar o desactivar Bookings with me para su organización.

> [!NOTE]
> Normalmente, los comandos de Set-OrganizationConfig tardan entre 30 y 60 minutos en surtir efecto para los usuarios.

1. Compruebe el acceso de control de EWS mediante la ejecución del siguiente comando.

   ```PowerShell
   Get-OrganizationConfig | Format-List EwsEnabled
   ```

    Si el comando devuelve "EwsEnabled: **$true**", continúe con el paso 2.

    Si el comando devuelve "EwsEnabled:" (vacío es el valor predeterminado), habilite, pero solo si necesita bloquear "Bookings with" y continúe con el paso 2.
    De lo contrario, los valores predeterminados de EwsEnabled son suficientes para dejar "Bookings with me" habilitado, no se necesitan más cambios.

   ```PowerShell
   Set-OrganizationConfig -EwsEnabled: $true
   ```

2. Para comprobar el valor de EwsApplicationAccessPolicy, ejecute el siguiente comando:

   ```PowerShell
   Get-OrganizationConfig | Format-List EwsApplicationAccessPolicy,Ews*List
   ```

    **A**. Si el valor de **EwsApplicationAccessPolicy** es **EnforceAllowList**, solo las aplicaciones especificadas en **EwsAllowList** pueden acceder a EWS y REST.

    - Para desactivar Bookings with me para su organización, quite **MicrosoftOWSPersonalBookings**, si está presente, de **EwsAllowList** mediante la ejecución del siguiente comando:  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - Para activar Bookings conmigo para su organización, agregue **MicrosoftOWSPersonalBookings** a **EwsAllowList** ejecutando el siguiente comando:  

   ```PowerShell
   Set-OrganizationConfig -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. Si el valor de **EwsApplicationAccessPolicy** es **EnforceBlockList**, todas las aplicaciones pueden acceder a EWS y REST, excepto los especificados en **EwsBlockList**.

    - Para desactivar Bookings conmigo para su organización, agregue **MicrosoftOWSPersonalBookings** ejecutando el siguiente comando:

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - Para activar Bookings conmigo si está bloqueado, quite **MicrosoftOWSPersonalBookings** ejecutando el siguiente comando:

   ```PowerShell
   Set-OrganizationConfig -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. Si el valor de **EwsApplicationAccessPolicy** está vacío, todas las aplicaciones pueden acceder a EWS y REST.

    - Para desactivar Bookings conmigo para su organización, establezca la directiva **EnforceBlockList** y agregue **MicrosoftOWSPersonalBookings** a la lista de bloques mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-OrganizationConfig -EwsApplicationAccessPolicy EnforceBlockList -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```
   
  > [!NOTE]
  > El parámetro EwsApplicationAccessPolicy define qué aplicaciones distintas de Entourage, Outlook y Outlook para Mac pueden acceder a EWS.

### <a name="turn-bookings-with-me-off-or-on-for-individual-users"></a>Desactivar o activar Bookings with me para usuarios individuales

Use los comandos **Get-CASMailbox** y **Set-CASMailbox** para comprobar el estado del usuario y activar o desactivar Bookings with me para usuarios individuales de su organización.

1. Compruebe el acceso de control de EWS de la persona mediante la ejecución del siguiente comando:

   ```PowerShell
   Get-CASMailbox -Identity adam@contoso.com | Format-List EwsEnabled
   ```

    **A**. Si el comando devuelve "**EwsEnabled: $true**", continúe con el paso 2.

2. Compruebe el **valor de EwsApplicationAccessPolicy** de la persona ejecutando el siguiente comando:

   ```PowerShell
   Get-CASMailbox -Identity adam@contoso.com | Format-List EwsApplicationAccessPolicy,Ews*List
   ```

    **A**. Si el valor de **EwsApplicationAccessPolicy** es **EnforceAllowList**, solo las aplicaciones especificadas en EwsAllowList pueden acceder a EWS y REST.

    - Para desactivar Bookings with me para este usuario, quite **MicrosoftOWSPersonalBookings**, si está presente en **EwsAllowList** mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    - Active Bookings with me para este usuario, agregue **MicrosoftOWSPersonalBookings** a **EwsAllowList** ejecutando el siguiente comando:

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsAllowList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    **B**. Si el valor de **EwsApplicationAccessPolicy** es **EnforceBlockList**, todas las aplicaciones pueden acceder a EWS y REST, excepto los especificados en **EwsBlockList**.  

    - Para desactivar Bookings with me para este usuario, agregue **MicrosoftOWSPersonalBookings** a **EnforceBlockList** mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

    - Para activar Bookings conmigo para este usuario, quite **MicrosoftOWSPersonalBookings**, si está presente en EnforceBlockList mediante la ejecución del siguiente comando:

   ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsBlockList @{Remove="MicrosoftOWSPersonalBookings"}
   ```

    **C**. Si el valor de EwsApplicationAccessPolicy está vacío, todas las aplicaciones pueden acceder a EWS y REST.

    - Para desactivar Bookings with me para este usuario, establezca la directiva **EnforceBlockList** y agregue **MicrosoftOWSPersonalBookings** a EWSBlockList mediante la ejecución del siguiente comando:

    ```PowerShell
   Set-CASMailbox -Identity adam@contoso.com -EwsApplicationAccessPolicy EnforceBlockList -EWSBlockList @{Add="MicrosoftOWSPersonalBookings"}
   ```

### <a name="create-bookings-with-me"></a>Creación de Bookings conmigo

1. Abra [Outlook en la Web](https://go.microsoft.com/fwlink/p/?LinkID=402333).
2. Seleccione **Calendario**.
3. Seleccione el vínculo **crear reservas** que aparece en el calendario para crear Bookings conmigo.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="what-is-the-difference-between-bookings-and-bookings-with-me"></a>¿Cuál es la diferencia entre Bookings y Bookings conmigo?

Bookings with me se integra con su calendario de Outlook y solo se puede usar para reuniones 1:1. Bookings with me está pensado para programar horarios de reunión con usuarios individuales. Bookings está pensado para administrar la programación de un grupo de personas.

Además, Bookings with me no creará un nuevo buzón para cada página bookings with me.

### <a name="why-is-bookings-with-me-in-preview"></a>¿Por qué Bookings conmigo está en versión preliminar?

Bookings with me está en versión preliminar para todos los usuarios empresariales de todo el mundo. Estamos recopilando comentarios y haciendo mejoras mientras se integran en las experiencias de programación en Bookings y Outlook.  

### <a name="who-can-access-my-public-bookings-page"></a>¿Quién puede acceder a mi página pública de Bookings?

Cualquier persona que tenga su dirección de página de Bookings conmigo puede acceder a los tipos de reunión públicos. Usted decide con quién comparte sus Reservas con mi dirección de página. Para obtener más información, consulte [Seleccionar una hora de reunión en Bookings with me](https://support.microsoft.com/office/select-a-meeting-time-in-bookings-with-me-8f3bbe5b-4bc6-4073-bf61-57383c00b43a).

### <a name="what-is-the-difference-between-public-and-private-meeting-types"></a>¿Cuál es la diferencia entre los tipos de reunión públicos y privados?

Los tipos de reunión pueden ser públicos o privados. Los tipos de reunión públicos están disponibles para cualquier persona con la que comparta el vínculo de la página de Bookings. Los tipos de reunión privados solo están disponibles para las personas con las que comparte el tipo de reunión privado individual.  

Los tipos de reunión privados también pueden generar vínculos de uso único. Los vínculos de uso único expiran después de su primera reserva. Para obtener más información, consulte [configuración de bookings with me meeting types](https://support.microsoft.com/office/bookings-with-me-setup-and-sharing-ad2e28c4-4abd-45c7-9439-27a789d254a2).

### <a name="do-people-need-to-have-a-microsoft-account-or-bookings-license-to-schedule-time-with-me"></a>¿Las personas necesitan tener una cuenta Microsoft o una licencia de Bookings para programar la hora conmigo?

No. Cualquier persona puede programar la hora con usted mediante su página Reservas conmigo, incluso si no tiene una cuenta microsoft. Necesita una licencia de Bookings para crear una página de Bookings with me.

## <a name="privacy"></a>Privacidad

### <a name="where-is-bookings-with-me-data-stored"></a>¿Dónde se almacenan los datos de Bookings with me?

Bookings with me es una característica de Outlook con tecnología de Bookings. Todos los datos se almacenan en la plataforma Microsoft 365 y en Exchange. Bookings with me sigue las directivas de almacenamiento de datos establecidas por Microsoft, que son las mismas directivas que siguen todas las aplicaciones de Office. Todos los datos de clientes (incluida la información proporcionada por los asistentes al reservar) se capturan en Bookings y se almacenan en Exchange. Para obtener más información, consulte [Privacidad: Todo se trata de usted](https://www.microsoft.com/en-us/trust-center/privacy).
