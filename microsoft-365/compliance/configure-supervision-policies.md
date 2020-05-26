---
title: Configurar directivas de supervisión
description: Configure las directivas de supervisión de comunicaciones en Office 365 para capturar las comunicaciones de los empleados a fin de examinarlas por revisores externos o internos.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 54ff4012767b156bc72289473e289fa4d93d1a2c
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352163"
---
# <a name="configure-supervision-policies-in-office-365"></a>Configurar directivas de supervisión en Office 365

>[!IMPORTANT]
>Tras la publicación del cumplimiento de la comunicación en el cumplimiento de Microsoft 365 en febrero de 2020, se está retirando la supervisión en Office 365. Las directivas de supervisión ya no estarán disponibles para su creación, y las directivas se quitarán después de un período prolongado de acceso de solo lectura.
>
>Si usa la supervisión, tenga en cuenta que:
>
>- A partir del 15 de junio de 2020, los inquilinos no tendrán la capacidad de crear nuevas directivas de supervisión.
>- A partir del 31 de agosto de 2020, las directivas existentes dejarán de capturar mensajes nuevos.
>- A partir del 26 de octubre de 2020, las directivas existentes se eliminarán.
>
>Alentamos activamente a los clientes que actualmente están explorando o usando la supervisión en Office 365 para usar la nueva solución de cumplimiento de la [comunicación](communication-compliance.md) a fin de satisfacer los requisitos normativos o de supervisión de comunicaciones con un conjunto mucho más rico de capacidades inteligentes.

Usar directivas de supervisión para capturar las comunicaciones de los empleados para que las examinen los revisores externos o internos. Para obtener más información sobre cómo las directivas de supervisión pueden ayudarle a supervisar las comunicaciones en su organización, consulte [directivas de supervisión en Office 365](supervision-policies.md).

>[!NOTE]
>Los usuarios supervisados por directivas de supervisión deben tener una licencia de cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento de cumplimiento avanzado o estar incluidas en una suscripción a Office 365 Enterprise E5 o estar incluidas en una suscripción a Microsoft 365 E5.
>Si no tiene un plan existente de Enterprise E5 y desea intentar la supervisión, puede [registrarse para obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).
  
Siga estos pasos para configurar y usar la supervisión en su organización:
  
- **Paso 1 (opcional)**: [configurar grupos para supervisión](#step-1-set-up-groups-for-supervision-optional)

    Antes de empezar a usar directivas de supervisión, determine quién necesita las comunicaciones revisadas y quién realiza las revisiones. Si quiere empezar solo con unos pocos usuarios para ver cómo funciona la supervisión, puede omitir la configuración de grupos por ahora.

- **Paso 2 (obligatorio)**: [hacer que la supervisión esté disponible en su organización](#step-2-make-supervision-available-in-your-organization-required)

    Se agrega al grupo de funciones de revisión de supervisión para que pueda configurar directivas. Cualquier persona a la que se le haya asignado este rol puede tener acceso a la página **supervisión** del centro de seguridad & cumplimiento. Si el correo electrónico que se puede rever está hospedado en Exchange Online, cada revisor debe tener [acceso remoto de PowerShell a Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- **Paso 3 (opcional)**: [crear tipos personalizados de información confidencial y diccionarios de palabras clave personalizados](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    Si necesita un tipo de información confidencial personalizado o un diccionario de palabras clave personalizado para la Directiva de supervisión, debe crearlo antes de iniciar el Asistente para la supervisión.

- **Paso 4 (obligatorio)**: [configurar una directiva de supervisión](#step-4-set-up-a-supervision-policy-required)

    Las directivas de supervisión se crean en el centro de seguridad & cumplimiento. Estas directivas definen qué comunicaciones están sujetas a revisión en su organización y especifica quién realiza las revisiones. Las comunicaciones incluyen el correo electrónico y las comunicaciones de Microsoft Teams y las comunicaciones de la plataforma de terceros (como Facebook, Twitter, etc.). Las directivas de supervisión creadas en organizaciones no son compatibles con la supervisión de la comunicación en las suscripciones de Microsoft 365.

- **Paso 5 (opcional)**: [probar la Directiva de supervisión de la comunicación](#step-5-test-your-supervision-policy-optional)

    Pruebe la Directiva de supervisión para asegurarse de que funciona según lo deseado. Es importante asegurarse de que la estrategia de cumplimiento cumple los estándares.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>Paso 1: configurar grupos para supervisión (opcional)

 Cuando se crea una directiva de supervisión, se define quién tiene las comunicaciones examinadas y quién realiza las revisiones. En la Directiva, usará direcciones de correo electrónico para identificar personas o grupos de personas. Para simplificar la configuración, puede crear grupos para los usuarios que tengan su comunicación examinada y grupos para las personas que revisen dichas comunicaciones. Si está usando grupos, es posible que necesite varios. Por ejemplo, desea supervisar las comunicaciones entre dos grupos de personas distintas o si desea especificar un grupo que no se va a supervisar.

Use el siguiente gráfico para ayudarle a configurar los grupos de su organización para las directivas de supervisión de comunicación:

| **Miembro de la Directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios no supervisados | Grupos de distribución <br> Grupos de Microsoft 365 | Grupos de distribución dinámicos |
| Reviewers | Grupos de seguridad habilitados para correo  | Grupos de distribución <br> Grupos de distribución dinámicos |
  
Al seleccionar un grupo de 365 de Microsoft para los usuarios supervisados, la Directiva supervisa el contenido del buzón compartido y los canales de Microsoft Teams asociados con el grupo. Al seleccionar una lista de distribución, la Directiva supervisa los buzones de usuario individuales.

Para administrar usuarios supervisados en grandes organizaciones empresariales, es posible que necesite supervisar a todos los usuarios en grupos grandes. Puede usar PowerShell para configurar un grupo de distribución para una directiva de supervisión global para el grupo asignado. Esto le permite supervisar miles de usuarios con una sola directiva y mantener la Directiva de supervisión actualizada a medida que los empleados nuevos se unen a su organización.

1. Cree un [grupo de distribución](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup?view=exchange-ps) dedicado para la Directiva de supervisión global con las siguientes propiedades: Asegúrese de que este grupo de distribución no se use para otros fines u otros servicios de Office 365.

    - **MemberDepartRestriction = cerrado**. Garantiza que los usuarios no puedan quitar a sí mismos del grupo de distribución.
    - **MemberJoinRestriction = cerrado**. Garantiza que los usuarios no pueden agregarse a sí mismos al grupo de distribución.
    - **ModerationEnabled = true**. Garantiza que todos los mensajes enviados a este grupo están sujetos a aprobación y que el grupo no se está usando para comunicarse fuera de la configuración de la Directiva de supervisión.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Seleccione un [atributo personalizado de Exchange](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) sin usar para realizar un seguimiento de los usuarios agregados a la Directiva de supervisión de su organización.

3. Ejecute el siguiente script de PowerShell en una programación recurrente para agregar usuarios a la Directiva de supervisión:

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Para obtener más información acerca de la configuración de grupos, vea:

- [Crear y administrar grupos de distribución](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Administrar grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Información general de los grupos de 365 de Microsoft](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>Paso 2: hacer que la supervisión esté disponible en su organización (obligatorio)

Para que la **supervisión** esté disponible como una opción de menú en el centro de seguridad & cumplimiento, debe tener asignado el rol de administrador de revisión de supervisión.
  
Para ello, puede agregarse como miembro del grupo de funciones de revisión de supervisión, o bien puede crear un grupo de roles.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Adición de miembros al grupo de roles de revisión de supervisión

1. Inicie sesión [https://protection.office.com](https://protection.office.com) con las credenciales de una cuenta de administrador en la organización.

2. En el centro de seguridad & cumplimiento, vaya a **permisos**.

3. Seleccione el grupo de roles **revisión de supervisión** y, a continuación, haga clic en el icono Editar.

4. En la sección **miembros** , agregue a las personas que desea que administren la supervisión de la comunicación de su organización.

### <a name="create-a-new-role-group"></a>Crear un nuevo grupo de roles

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador en la organización.

2. En el centro de seguridad & cumplimiento, vaya a **permisos** y, después, haga clic en Agregar ( **+** ).

3. En la sección **roles** , haga clic en Agregar ( **+** ) y desplácese hacia abajo hasta **Administrador de revisión de supervisión**. Agregue este rol al grupo de roles.

4. En la sección **miembros** , agregue a las personas que desea que administren la supervisión de la comunicación de su organización.

Para obtener más información acerca de los grupos de roles y los permisos, consulte [Permissions in the Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Habilitar el acceso remoto de PowerShell para revisores (si el correo electrónico se hospeda en Exchange Online)

1. Siga las instrucciones de [habilitar o deshabilitar el acceso a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>Paso 3: crear tipos personalizados de información confidencial y diccionarios de palabras clave personalizados (opcional)

Para elegir entre los tipos de información confidencial personalizados existentes o los diccionarios de palabras clave personalizados en el Asistente para directivas de supervisión, primero debe crear estos elementos si es necesario.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>Crear Diccionario o léxico personalizado de palabra clave (opcional)

Use un editor de texto (como el Bloc de notas) para crear un archivo que incluya los términos de palabra clave que desea supervisar en una directiva de supervisión. Asegúrese de que cada término está en una línea independiente y guarde el archivo en formato **Unicode/UTF-16 (Little endian)** .

### <a name="create-custom-sensitive-information-types"></a>Crear tipos personalizados de información confidencial

1. Cree un nuevo tipo de información confidencial y agregue el diccionario personalizado en el centro de seguridad & cumplimiento. Navegue hasta **Classifications** \> **tipos de información confidencial** de clasificaciones y siga los pasos del **Asistente para nuevos tipos de información confidencial**. Aquí podrá:

    - Definir un nombre y una descripción para el tipo de información confidencial
    - Definir los elementos de proximidad, nivel de confianza y patrón principal
    - Importe el diccionario personalizado como requisito para el elemento correspondiente
    - Revisar las selecciones y crear el tipo de información confidencial

    Para obtener información más detallada, consulte [crear un tipo personalizado de información confidencial](create-a-custom-sensitive-information-type.md) y [crear un diccionario de palabras clave](create-a-keyword-dictionary.md)

    Una vez creado el diccionario o léxico personalizado, puede ver las palabras clave configuradas con el cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/get-dlpkeyworddictionary) o agregar y quitar términos con el cmdlet [set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/set-dlpkeyworddictionary) .

## <a name="step-4-set-up-a-supervision-policy-required"></a>Paso 4: configurar una directiva de supervisión (obligatorio)
  
1. Inicie sesión [https://protection.office.com](https://protection.office.com) con las credenciales de una cuenta de administrador en la organización.

2. En el centro de seguridad & cumplimiento, seleccione **supervisión**.
  
3. Seleccione **crear** y siga el Asistente para establecer la configuración de la Directiva. Con el asistente, podrá:

    - Asigne un nombre y una descripción a la Directiva.
    - Elija los usuarios o grupos que desea supervisar, incluida la elección de los usuarios o grupos que quiera excluir.
    - Definir las [condiciones](supervision-policies.md#ConditionalSettings)de la Directiva de supervisión. Puede elegir entre la dirección del mensaje, la palabra clave, los tipos de archivo y las condiciones de coincidencia de tamaño.
    - Elija si le gustaría incluir tipos de información confidencial. Aquí puede seleccionar los tipos de información confidencial predeterminada y personalizado.
    - Elija si quiere habilitar el modelo de lenguaje ofensivo. Esto detecta un idioma no apropiado enviado o recibido en el cuerpo de los mensajes de correo electrónico.
    - Definir el porcentaje de comunicaciones que se van a revisar.
    - Elija los revisores para la Directiva. Los revisores pueden ser usuarios individuales o [grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group). Todos los revisores deben tener buzones hospedados en Exchange Online.
    - Revise las selecciones de la Directiva y cree la Directiva.

## <a name="step-5-test-your-supervision-policy-optional"></a>Paso 5: probar la Directiva de supervisión (opcional)

Después de crear una directiva de supervisión de la comunicación, es aconsejable probarla para asegurarse de que la Directiva aplica correctamente las condiciones definidas. Es posible que también desee [probar sus directivas de prevención de pérdida de datos (DLP)](create-test-tune-dlp-policy.md) si las directivas de supervisión incluyen tipos de información confidencial. Siga estos pasos para probar la Directiva de supervisión:

1. Abra un cliente de correo electrónico o Microsoft teams que haya iniciado sesión como usuario supervisado definido en la Directiva que desea probar.
2. Envíe un correo electrónico o un chat de Microsoft teams que cumpla los criterios que haya definido en la Directiva de supervisión. Puede ser una palabra clave, el tamaño de los datos adjuntos, el dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la Directiva es demasiado restrictiva o demasiado flexible.

    >[!NOTE]
    >Los correos electrónicos sujetos a directivas definidas se procesan casi en tiempo real y se pueden probar inmediatamente una vez configurada la Directiva. Los chats de Microsoft Teams pueden tardar hasta 24 horas en procesarse por completo en una directiva. 

3. Inicie sesión en Microsoft 365 como revisor designado en la Directiva de supervisión de la comunicación. Navegue hasta la **supervisión**de la  >  *directiva personalizada*  >  **abierta** para ver el informe de la Directiva.

