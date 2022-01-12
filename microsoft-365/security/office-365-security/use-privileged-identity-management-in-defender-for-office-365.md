---
title: Usar Azure Privileged Identity Management (PIM) en Microsoft Defender para Office 365 para limitar el acceso del administrador a las herramientas de ciberseguridad.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/03/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Aprenda a integrar Azure PIM para conceder acceso Just-In-Time limitado a los usuarios para que realicen tareas con privilegios elevados en Microsoft Defender para Office 365 y reducir así el riesgo para los datos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3be90ff1113e25ea418aaf1a25b12574b3bbbe1f
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61939482"
---
<!--A-->
# <a name="privileged-identity-management-pim-and-why-to-use-it-with-microsoft-defender-for-office-365"></a>Privileged Identity Management (PIM) y por qué usarlo con Microsoft Defender para Office 365

Privileged Identity Management (PIM) es una característica de Azure que, una vez configurada, proporciona a los usuarios acceso a los datos durante un período de tiempo limitado (a veces denominado período de tiempo con cuadro de tiempo) para que se pueda realizar una tarea específica. A este acceso se le da "just-in-time" (o el tiempo suficiente) para realizar la acción necesaria y, a continuación, se revoca. PIM limita el acceso y el tiempo que el usuario tiene a los datos confidenciales, lo que reduce el riesgo de exposición en comparación con las cuentas de administración con privilegios que tienen acceso a largo plazo a datos y otras configuraciones. Entonces, ¿cómo podemos usar esta característica (PIM) junto con Microsoft Defender para Office 365?

> [!TIP]
> El acceso a PIM se limita al nivel de rol e identidad y permite la finalización de varias tareas. No debe confundirse con Privileged Access Management (PAM), que tiene como ámbito un nivel de tarea.

## <a name="steps-to-use-pim-to-grant-just-in-time-access-to-defender-for-office-365-related-tasks"></a>Pasos para usar PIM para conceder acceso just-In-Time a las tareas relacionadas con Defender para Office 365

Al configurar PIM para que funcione con Defender para Office 365, los administradores crean un proceso para que un usuario solicite acceso para realizar las acciones que necesita. El usuario debe *justificar* la necesidad de la elevación de sus privilegios.

En este ejemplo, configuraremos a “Alex”, un miembro de nuestro equipo de seguridad que no tendrá acceso permanente en Office 365, pero que puede elevarse a un rol necesario para las operaciones cotidianas normales (como la [búsqueda de amenazas](threat-hunting-in-threat-explorer.md)) y, a continuación, a un mayor nivel de privilegios cuando se requieran operaciones menos frecuentes pero confidenciales, como la [corrección de correo electrónico malintencionado](remediate-malicious-email-delivered-office-365.md).

> [!NOTE]
> Esto le llevará a través de los pasos necesarios para configurar PIM para un analista de seguridad que requiere la capacidad de purgar correos electrónicos con el Explorador de amenazas en Microsoft Defender para Office 365, pero se pueden usar los mismos pasos para otros roles RBAC dentro del portal de seguridad y cumplimiento. Por ejemplo, este proceso podría usarse para un trabajador de la información que necesita acceso diario en eDiscovery para realizar búsquedas y casos de trabajo, pero solo en ocasiones necesita el derecho elevado para exportar datos desde el inquilino.

***Paso 1***. En la consola de Azure PIM de la suscripción, agregue al usuario (Alex) al rol lector de seguridad de Azure y configure las opciones de seguridad relacionadas con la activación.

1. Inicie sesión en el [Centro de administración de Azure AD](https://aad.portal.azure.com/) y seleccione **Azure Active Directory** > **Roles y administradores**.
2. Seleccione **Lector de seguridad** en la lista de roles y, a continuación,**Editar**  > **Configuración**
3. Establezca la "**duración máxima de activación (horas)**" a un día laborable normal y "Al activar" para requerir **Azure MFA**.
4. Como este es el nivel de privilegios normal de Alex para las operaciones diarias, desactivaremos **Requerir justificación en la activación**' > **Actualizar**.
5. Seleccione **Agregar asignaciones** > **No hay ningún miembro seleccionado** > seleccione o escriba el nombre para buscar al miembro correcto.
6. Haga clic en el botón **Seleccionar** para elegir el miembro que necesita agregar para privilegios de PIM > haga clic en **Siguiente** > no realice ningún cambio en la página Agregar asignación (tanto el tipo de asignación *Apta* como la duración *Permanentemente apta* serán valores predeterminados) y **Asignar**.

El nombre de su usuario (aquí "Alex") aparecerá en Asignaciones Aptas en la página siguiente, lo que significa que puede usar PIM en el rol con las opciones configuradas anteriormente.

> [!NOTE]
> Para una revisión rápida de Privileged Identity Management vea [este vídeo](https://www.youtube.com/watch?v=VQMAg0sa_lE).

:::image type="content" source="../../media/pim-mdo-role-setting-details-for-security-reader-show-8-hr-duration.png" alt-text="Asegúrese de examinar la configuración del rol Lector de seguridad en Privileged Access Management. Aquí verá que la duración máxima de la activación de PIM es de 8 horas.":::

***Paso 2***. Cree el segundo grupo de permisos necesario (con privilegios elevados) para tareas adicionales y asigne elegibilidad.

Con los [Grupos de acceso con privilegios](/azure/active-directory/privileged-identity-management/groups-features), ya se pueden crear grupos personalizados y combinar permisos o aumentar la granularidad cuando sea necesario para satisfacer las prácticas y necesidades de la organización.

### <a name="create-a-role-group-requiring-the-permissions-we-need"></a>Cree un grupo de roles que requiera los permisos que necesitamos

En el portal Microsoft 365 Defender, cree un grupo de roles personalizado que contenga los permisos que desee.

1. En el portal Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Permisos y roles** y, a continuación, seleccione **Roles** en **Correo electrónico y colaboración**. Para ir directamente a la página **Permisos**, use <https://security.microsoft.com/emailandcollabpermissions>.
2. En la página **Permisos**, haga clic en ![Crear icono.](../../media/m365-cc-sc-create-icon.png) **Create**.
3. Asigne un nombre al grupo para que refleje su propósito, como "Buscar y purgar PIM".
4. No agregue miembros, simplemente guarde el grupo y pase a la siguiente parte.

### <a name="create-the-security-group-in-azure-ad-for-elevated-permissions"></a>Creación del grupo de seguridad en Azure AD para permisos elevados

1. Vuelva al [Centro de administración de Azure AD](https://aad.portal.azure.com/) y vaya a **Grupos** > **Azure AD** > **Nuevo grupo**.
2. Asigne un nombre a su grupo Azure AD para reflejar su propósito, **no se requiere ningún propietario o miembro** en este momento.
3. Los roles Turn **Azure AD se pueden asignar al grupo** a **Sí**.
4. No agregue ningún rol, miembros o propietarios, cree el grupo.
5. Vuelva al grupo que acaba de crear y seleccione **Acceso con privilegios** > **Habilitar acceso con privilegios**.
6. En el grupo, seleccione **Asignaciones aptas** > **Agregar asignaciones** > Agregar el usuario que necesita Buscar y purgar como rol de **miembro**.
7. Configure la **Configuración** en el panel Acceso con privilegios del grupo. Elija **Editar** la configuración del rol de **miembro**.
8. Cambie el tiempo de activación para adaptarlo a su organización. En este ejemplo, se requiere *justificación de*, *Azure MFA,* e *información de vales* antes de seleccionar **Actualizar**.

### <a name="nest-the-newly-created-security-group-into-the-role-group"></a>Anide el grupo de seguridad recién creado en el grupo de roles

1. [Conéctese al Centro de seguridad y cumplimiento PowerShell](/powershell/exchange/connect-to-scc-powershell) y ejecute el siguiente comando:

   ```powershell
   Add-RoleGroupMember "<<Role Group Name>>" -Member "<<Azure Security Group>>"`
   ```

## <a name="test-your-configuration-of-pim-with-defender-for-office-365"></a>Probar la configuración de PIM con Defender para Office 365

1. Inicie sesión con el usuario de prueba (Alex), que no debería tener acceso administrativo en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center) en este momento.
2. Vaya a PIM, donde el usuario puede activar su rol de lector de seguridad diario.
3. Si intenta purgar un correo electrónico mediante el Explorador de amenazas, recibirá un error que indica que necesita permisos adicionales.
4. Utilice PIM una segunda vez en el rol más elevado. Tras un breve retraso, ahora debería poder purgar los correos electrónicos sin problemas.

   :::image type="content" source="../../media/pim-mdo-add-the-search-and-purge-role-assignment-to-this-pim-role.PNG" alt-text="Si el usuario que agregamos (Alex) a través del rol PIM lector de seguridad intenta eliminar un correo electrónico sospechoso, recibirá un mensaje que dice &quot;Necesita el rol de Búsqueda y purga para realizar acciones en este correo electrónico. Póngase en contacto con el administrador para obtener la asignación de roles o agregue el correo electrónico a un incidente.":::

La asignación permanente de roles administrativos y permisos, como el rol de búsqueda y purga, no se mantiene con la iniciativa de seguridad Confianza cero, pero, como puede ver, PIM se puede usar para conceder acceso, solo cuando sea necesario, al conjunto de herramientas necesario.

*Expresamos nuestros agradecimientos al ingeniero de clientes Ben Harris por el acceso a la entrada de blog y a los recursos usados para este contenido.*

<!--A-->