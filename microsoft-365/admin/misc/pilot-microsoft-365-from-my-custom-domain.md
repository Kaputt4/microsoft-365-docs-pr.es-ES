---
title: Prueba piloto de Microsoft 365 desde mi dominio personalizado
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información acerca de cómo probar la funcionalidad de correo electrónico de mi dominio personalizado en un buzón de Microsoft 365 usando solo dos cuentas de prueba.
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186052"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>Prueba piloto de Microsoft 365 desde mi dominio personalizado

Puede realizar pruebas piloto de Microsoft 365 con estos requisitos y limitaciones:

- Su proveedor de correo electrónico actual debe proporcionar el reenvío de correo electrónico.

- Debe administrar los registros DNS de Microsoft 365 en su proveedor de host DNS, en lugar de hacer que Microsoft 365 administre estos registros por usted.

    Para obtener más información, vea [Agregar registros DNS para conectar su dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

- La información de disponibilidad de los usuarios en el otro servidor de correo electrónico no está disponible.

- Los administradores no pueden administrar todas las cuentas de usuario desde una sola ubicación.

- Es posible que los usuarios no puedan usar el filtrado de correo no deseado de Microsoft 365.

## <a name="set-up-a-microsoft-365-pilot"></a>Configurar una prueba piloto de Microsoft 365

Siga estos pasos para configurar una prueba piloto de Microsoft 365:

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>Paso 1: iniciar sesión en el Centro de administración de Microsoft 365

1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con su cuenta profesional o educativa.

2. Seleccione **Configuración** > **Dominios** en el panel de navegación izquierdo.

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>Paso 2: comprobar que es el propietario del dominio que quiere usar

1. En la página **Dominios**, seleccione **Agregar dominio**.

2. Escriba el nombre del dominio en el cuadro, seleccione **Usar este dominio** y, a continuación, seleccione **Continuar**.

3. Seleccione los servicios que desee probar con su dominio, como el correo electrónico y la mensajería instantánea.

5. En la página **Comprobar** dominio, siga las instrucciones paso a paso y, a continuación, haga clic en y **Comprobar**.

    Se tarda entre unos minutos y 72 horas en que los cambios en el DNS surtan efecto.

    Cuando la comprobación se realice correctamente, se le pedirá que modifique los registros de DNS.

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>Paso 3: marcar el dominio como compartido en Exchange Online

1. En el Centro de administración de Exchange, en la sección **Flujo de correo**, seleccione **Dominios aceptados** y, a continuación, seleccione el dominio que desea modificar.

2. Haga doble clic para abrir la ventana y, a continuación, seleccione **retransmisión interna**. 

3. Seleccione **Guardar**.

    Esta configuración puede tardar unos minutos en surtir efecto.

### <a name="step-4-unblock-the-existing-email-server-optional"></a>Paso 4: desbloquear el servidor de correo electrónico existente (opcional)

Microsoft 365 usa Exchange Online Protection (EOP) para la protección contra correo electrónico no deseado. EOP podría bloquear el servidor de correo existente si detecta un alto volumen de spam que el servidor de correo actual reenviará. Si confía en la protección contra correo no deseado para su proveedor de correo electrónico, puede desbloquear el servidor de Microsoft 365.

> [!NOTE]
> Desbloquear el servidor de correo electrónico existente permite que el spam que llega a través del servidor original llegue a los buzones de Microsoft 365, por lo que no se puede evaluar la eficacia de Microsoft 365 para evitar el spam.

1. En el panel de navegación del Centro de administración de Exchange, seleccione **Protección**y, a continuación, seleccione **Filtro de conexión**.

2. En la **Lista de direcciones IP permitidas**, seleccione **+**, y agregue la dirección IP para el servidor de correo electrónico a su proveedor de correo electrónico actual. 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>Paso 5: crear cuentas de usuario y configurar la dirección de respuesta principal

1. En el Centro de administración de Microsoft 365 panel de navegación izquierdo, seleccione **Usuarios** > **Usuarios activos**.

2. Para crear dos cuentas de prueba, agregue dos usuarios existentes.

    Para cada cuenta, seleccione **+ Agregar un usuario**, y rellene la información necesaria, incluyendo el método de contraseña que quiere probar.

    Para asegurarse de que el correo electrónico de un usuario siga siendo el mismo, el campo **Nombre de usuario** tiene que coincidir con la dirección de correo electrónico actual del usuario.

3. Elija la licencia adecuada, haga clic en **Siguiente**y, después, haga clic en **Finalizar la agregación**. 

4. Junto a **Nombre de usuario**, seleccione su nombre de dominio personalizado de la lista desplegable. 

5. Seleccione **Crear** > **Cerrar**.

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a>Paso 6: actualizar los registros DNS en su proveedor de host DNS

Inicie sesión en el sitio web de su proveedor de host DNS y siga las instrucciones que encontrará en [Agregar registros DNS para conectar su dominio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

**Realice las dos siguientes excepciones:**

- No cree un nuevo registro MX ni cambie su registro MX existente.

- Si ya tiene un registro de Marco de Directivas de Remitente (SPF) para su anterior proveedor de correo electrónico, en lugar de crear un nuevo registro SPF (TXT) para Exchange Online, agregue "include:spf.protection.outlook.com" al registro TXT actual.

    Por ejemplo, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".

    Si no tiene un registro de SPF, modifique el recomendado por Microsoft 365 para incluir el dominio de su proveedor de correo electrónico actual y agregue spf.protection.outlook.com. Esto autoriza los mensajes salientes de ambos sistemas de correo electrónico.

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a>Paso 7: configurar el reenvío de correo electrónico en su proveedor actual

En su proveedor de correo electrónico actual, configure el reenvío de las cuentas de correo electrónico de los usuarios a su dominio onmicrosoft.com:

- Reenviar un buzón de correo del usuario A a usera@yourcompany.onmicrosoft.com

- Reenviar el buzón de correo del usuario B a userb@yourcompany.onmicrosoft.com

Cuando finalice este paso, todo el correo electrónico enviado a usera@yourcompany.com y userb@yourcompany.com estará disponible en Microsoft 365.

> [!NOTE]
> Póngase en contacto con su proveedor de correo electrónico actual para ver los pasos detallados para configurar el reenvío de correo electrónico.<br/>
> No es necesario mantener una copia de los mensajes en el proveedor de correo electrónico actual.<br/>
> La mayoría de los proveedores reenvían el correo electrónico dejando la dirección de respuesta del remitente intacta para que las respuestas pasen al remitente original.

### <a name="step-8-test-mail-flow"></a>Paso 8: comprobar el flujo de correo

1. Inicie sesión en Outlook Web App con las credenciales del usuario A.

2. Realice estas pruebas:

    - Pruebe el correo electrónico local de Microsoft enviando un correo electrónico, por ejemplo, al usuario B. El correo electrónico se entrega inmediatamente. En este escenario, el mensaje no se enruta al buzón del usuario B en su servidor original porque el buzón de Microsoft 365 es local.

    - Pruebe el correo electrónico para un usuario en el sistema de correo electrónico existente enviando un correo electrónico, por ejemplo, al usuario C. El correo electrónico se entrega en el buzón del usuario C en su servidor de correo original.

    - Compruebe que el reenvío se configuró correctamente desde una cuenta externa o desde una cuenta de correo electrónico del empleado en el sistema de correo electrónico existente. Por ejemplo, desde la cuenta de servidor original del usuario C o de una cuenta de hotmail, envíe un correo electrónico al usuario A y compruebe que llega al buzón de Microsoft 365 para el usuario A.

### <a name="step-9-move-mailbox-contents"></a>Paso 9: mover contenido del buzón de correo

Como va a mover solo dos usuarios de prueba, y el usuario A y el usuario B usan Outlook, puede mover el correo electrónico abriendo el archivo .PST antiguo en el nuevo perfil de Outlook y copie los mensajes, los elementos de calendario, los contactos, etc. Para obtener más información, vea [Importar correo electrónico, contactos y calendario desde un archivo .pst de Outlook](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).

Una vez que se importan a las ubicaciones adecuadas en el buzón de correo de Microsoft 365, se puede acceder a ellos desde cualquier dispositivo y en cualquier lugar.

Cuando haya más buzones involucrados, o si los empleados no están usando Outlook, puede usar las herramientas de migración disponibles en el Centro de administración de Exchange. Para empezar, vaya al Centro de administración de Exchange y siga las instrucciones que encontrará en [migrar el correo electrónico desde un servidor IMAP a los buzones de correo de Exchange Online: necesitamos un nuevo recurso de artículo].