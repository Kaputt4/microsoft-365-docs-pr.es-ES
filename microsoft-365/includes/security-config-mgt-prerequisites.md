---
title: archivo include
description: archivo include
author: mjcaparas
ms.service: microsoft-365-enterprise
ms.author: macapara
ms.openlocfilehash: 31008df3e43c99f3a97dad3dce037b96e3b0c4b5
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66116292"
---
## <a name="prerequisites"></a>Requisitos previos

Revise las secciones siguientes para conocer los requisitos de Security Management para Microsoft Defender para punto de conexión Escenario:

### <a name="environment"></a>Entorno

Cuando un dispositivo se incorpora a Microsoft Defender para punto de conexión:


- El dispositivo se realiza una encuesta en busca de una presencia de Endpoint Manager existente, que es una inscripción de administración de dispositivos móviles (MDM) para Intune
- Los dispositivos sin una presencia Endpoint Manager habilitarán la característica administración de seguridad
- Se crea una confianza con Azure Active Directory si aún no existe una.
- La confianza de Azure Active Directory se usa para comunicarse con Endpoint Manager (Intune) y recuperar directivas
- La recuperación de directivas de Endpoint Manager se aplica en el dispositivo mediante Microsoft Defender para punto de conexión

### <a name="active-directory-requirements"></a>Requisitos de Active Directory

Cuando un dispositivo unido a un dominio crea una confianza con Azure Active Directory, este escenario se conoce como escenario híbrido de *unión a Azure Active Directory* . Security Management for Microsoft Defender para punto de conexión admite completamente este escenario con los siguientes requisitos:

- Azure Active Directory Connect (AAD Connect) debe sincronizarse con el inquilino que se usa desde Microsoft Defender para punto de conexión
- La unión a Azure Active Directory híbrida debe configurarse en el entorno (ya sea mediante federación o AAD Connect Sync)
- AAD Connect Sync debe incluir los objetos de dispositivo *en el ámbito* para la sincronización con Azure Active Directory (cuando sea necesario para la unión)
- Las reglas de AAD Connect para la sincronización [deben modificarse para Server 2012 R2](/microsoft-365/security/defender-endpoint/troubleshoot-security-config-mgt?view=o365-worldwide#instructions-for-applying-computer-join-rule-in-aad-connect) (cuando se necesita compatibilidad con Server 2012 R2)
- Todos los dispositivos deben registrarse en Azure Active Directory del inquilino que hospeda Microsoft Defender para punto de conexión. No se admiten escenarios entre inquilinos. 

### <a name="connectivity-requirements"></a>Requisitos de conectividad

Los dispositivos deben tener acceso a los siguientes puntos de conexión:

- `enterpriseregistration.windows.net` : para el registro de Azure AD.
- `login.microsoftonline.com` : para el registro de Azure AD.
- `*.dm.microsoft.com` - El uso de un carácter comodín admite los puntos de conexión de servicio en la nube que se usan para la inscripción, la protección y los informes, y que pueden cambiar a medida que el servicio se escala.

> [!Note]
> Si los usuarios de la organización inspeccionan capa de sockets seguros (SSL), los puntos de conexión deben excluirse de la inspección.

### <a name="supported-platforms"></a>Plataformas compatibles

Las directivas para la administración de seguridad de Microsoft Defender para punto de conexión son compatibles con las siguientes plataformas de dispositivos:

- Windows 10 Professional/Enterprise (con [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541))
- Windows 11 Professional/Enterprise
- Windows Server 2012 R2 con [Microsoft Defender para dispositivos Down-Level](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2016 con [Microsoft Defender para dispositivos Down-Level](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2019 (con [KB5006744](https://support.microsoft.com/topic/october-19-2021-kb5006744-os-build-17763-2268-preview-e043a8a3-901b-4190-bb6b-f5a4137411c0))
- Windows Server 2022 (con [KB5006745](https://support.microsoft.com/topic/october-26-2021-kb5006745-os-build-20348-320-preview-8ff9319a-19e7-40c7-bbd1-cd70fcca066c))

### <a name="licensing-and-subscriptions"></a>Licencias y suscripciones

Para usar la administración de seguridad para Microsoft Defender para punto de conexión, necesita:

- Una suscripción que concede licencias para Microsoft Defender para punto de conexión, como Microsoft 365, o una licencia independiente solo para Microsoft Defender para punto de conexión. Una suscripción que concede licencias de Microsoft Defender para punto de conexión también concede a su inquilino acceso al nodo Seguridad del punto de conexión del Centro de administración de Microsoft Endpoint Manager.

  > [!NOTE]  
  > **Excepción**: si tiene acceso a Microsoft Defender para punto de conexión como parte de una licencia solo de Microsoft Defender for Cloud (anteriormente Azure Security Center), la Administración de seguridad para Microsoft Defender para punto de conexión funcionalidad no está disponible.

El nodo Seguridad del punto de conexión es donde configurará e implementará directivas para administrar Microsoft Defender para punto de conexión de los dispositivos y supervisar el estado del dispositivo.

Para obtener información actual sobre las opciones, consulte [Requisitos mínimos para Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/minimum-requirements?view=o365-worldwide&preserve-view=true).



## <a name="architecture"></a>Arquitectura

El diagrama siguiente es una representación conceptual de la solución de administración de configuración de seguridad Microsoft Defender para punto de conexión.

:::image type="content" alt-text="Representación conceptual de la solución de administración de configuración de seguridad Microsoft Defender para punto de conexión" source="../security/defender-endpoint/images/mde-architecture.png":::

1. Dispositivos incorporados a Microsoft Defender para punto de conexión.

2. Se establece una confianza entre cada dispositivo y Azure AD. Cuando un dispositivo tiene una confianza existente, se usa. Cuando los dispositivos no se han registrado, se crea una nueva confianza.

3. Los dispositivos usan su identidad de Azure AD para comunicarse con Endpoint Manager. Esta identidad permite a Microsoft Endpoint Manager distribuir directivas destinadas a los dispositivos cuando se registran.

4. Defender para punto de conexión notifica el estado de la directiva a Endpoint Manager.

## <a name="which-solution-should-i-use"></a>¿Qué solución debo usar?

Microsoft Endpoint Manager incluye varios métodos y tipos de directiva para administrar la configuración de Defender para punto de conexión en dispositivos.

Cuando las necesidades de protección de dispositivos se extiendan más allá de la administración de Defender para punto de conexión, consulte [Información general sobre protección](/mem/intune/protect/device-protect) de dispositivos para obtener información sobre las funcionalidades adicionales proporcionadas por Microsoft Endpoint Manager para ayudar a proteger los dispositivos, como *el cumplimiento de* dispositivos, *las aplicaciones administradas*, *las directivas de protección* de aplicaciones y la integración con asociados de cumplimiento de terceros y *de defensa contra amenazas móviles*.

La tabla siguiente puede ayudarle a comprender qué directivas que pueden configurar la configuración de MDE son compatibles con los dispositivos administrados por los distintos escenarios. Al implementar una directiva compatible con la configuración de seguridad de *MDE* y *Microsoft Endpoint Manager*, los dispositivos que solo ejecutan Microsoft Defender para punto de conexión y los dispositivos administrados por Intune o Configuration Manager.

| Microsoft Endpoint Manager  | Carga de trabajo |Policy| Configuración de seguridad de MDE  |  Microsoft Endpoint Manager |
|----------------|----------------|-------------------|------------|
| Seguridad de punto de conexión    | Antivirus   |     Antivirus           | ![Compatible](../media/green-check.png)  | ![Compatible](../media/green-check.png)  |
|                      | Antivirus   |   Exclusiones de antivirus   | ![Compatible](../media/green-check.png)  | ![Compatible](../media/green-check.png)  |
|                      | Antivirus   | Experiencia de Seguridad de Windows |                        | ![Compatible](../media/green-check.png)  |
|                      | Cifrado de disco   |     Todo |      | ![Compatible](../media/green-check.png)  |
|                      | Firewall   | Firewall              | ![Compatible](../media/green-check.png) | ![Compatible](../media/green-check.png)  |
|                      | Firewall | Reglas de firewall                | ![Compatible](../media/green-check.png) | ![Compatible](../media/green-check.png)  |
|                      | Detección y respuesta de puntos de conexión   | Detección y respuesta de puntos de conexión | ![Compatible](../media/green-check.png) | ![Compatible](../media/green-check.png)  |
|                      | Reducción de la superficie expuesta a ataques    |   Todo |          | ![Compatible](../media/green-check.png)  |
|                      | Protección de cuentas       |    Todo |     | ![Compatible](../media/green-check.png)  |
|                      | Cumplimiento de dispositivos     |   Todo |  | ![Compatible](../media/green-check.png)  |
|                      | Acceso condicional    |   Todo |  | ![Compatible](../media/green-check.png)  |
|                      | Líneas base de seguridad      |  Todo |   | ![Compatible](../media/green-check.png)  |

**Las directivas de seguridad de puntos de conexión** son grupos discretos de configuraciones diseñadas para su uso por los administradores de seguridad que se centran en la protección de dispositivos de su organización.

- **Las** directivas antivirus administran las configuraciones de seguridad que se encuentran en Microsoft Defender para punto de conexión. Consulte  [la directiva antivirus](/mem/intune/protect/endpoint-security-antivirus-policy) para la seguridad de los puntos de conexión.
- Las directivas de **reducción de superficie** expuesta a ataques se centran en minimizar los lugares donde la organización es vulnerable a ciberataques y ataques. Para obtener más información, consulte [Introducción a la reducción de la superficie expuesta a ataques](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction) en la documentación de Protección contra amenazas de Windows y Directiva de [reducción de la superficie expuesta a ataques](/mem/intune/protect/endpoint-security-asr-policy) para la seguridad de los puntos de conexión.
- Las directivas **de detección y respuesta de puntos de conexión** (EDR) administran las funcionalidades de Defender para punto de conexión que proporcionan detecciones avanzadas de ataques casi en tiempo real y accionables. En función de las configuraciones de EDR, los analistas de seguridad pueden priorizar las alertas de forma eficaz, obtener visibilidad sobre el ámbito completo de una infracción y realizar acciones de respuesta para corregir amenazas. Consulte [la directiva de detección y respuesta de puntos de conexión](/mem/intune/protect/endpoint-security-edr-policy) para obtener información sobre la seguridad de los puntos de conexión.
- **Las** directivas de firewall se centran en el firewall de Defender en los dispositivos. Consulte [directiva de firewall](/mem/intune/protect/endpoint-security-firewall-policy) para obtener información sobre la seguridad de los puntos de conexión.
- **Las reglas de firewall** configuran reglas granulares para firewalls, incluidos puertos, protocolos, aplicaciones y redes específicos. Consulte [directiva de firewall](/mem/intune/protect/endpoint-security-firewall-policy) para obtener información sobre la seguridad de los puntos de conexión.
- **Las líneas base de seguridad** incluyen opciones de seguridad preconfiguradas que definen la posición de seguridad recomendada por Microsoft para diferentes productos como Defender, Edge o Windows. Las recomendaciones predeterminadas proceden de los equipos de productos pertinentes y permiten implementar rápidamente esa configuración segura recomendada en los dispositivos. Aunque la configuración está preconfigurada en cada línea base, puede crear instancias personalizadas de ellas para establecer las expectativas de seguridad de su organización. Consulte [las líneas base de seguridad](/mem/intune/protect/security-baselines) para Intune.

## <a name="configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management"></a>Configuración del inquilino para admitir Microsoft Defender para punto de conexión Security Configuration Management

Para admitir Microsoft Defender para punto de conexión administración de configuración de seguridad a través del Centro de administración de Microsoft Endpoint Manager, debe habilitar la comunicación entre ellos desde cada consola.

1. Inicie sesión en [Microsoft 365 Defender portal](https://security.microsoft.com/) y vaya a Configuración **Endpoints** >  Configuration Management **Enforcement Scope (Ámbito de cumplimiento** **de administración de** >  configuración de puntos de conexión **de configuración)** >  y habilite las plataformas para la administración de la configuración de seguridad:

   :::image type="content" source="../media/security-settings-mgt.png" alt-text="Habilite la administración de la configuración de Microsoft Defender para punto de conexión en la consola de Defender.":::
    
1. Configure el modo piloto y Configuration Manager las opciones de autoridad para satisfacer las necesidades de su organización:

   :::image type="content" source="../media/pilot-CMAuthority-mde-settings-management-defender.png" alt-text="Configure el modo piloto para la administración de la configuración del punto de conexión en el portal de Microsoft 365 Defender.":::
   
  > [!TIP]
  > Use el modo piloto y las etiquetas de dispositivo adecuadas para probar y validar el lanzamiento en un pequeño número de dispositivos. Sin usar el modo piloto, cualquier dispositivo que entre en el ámbito configurado se inscribirá automáticamente.

1. Asegúrese de que los usuarios pertinentes tengan permisos para administrar la configuración de seguridad del punto de conexión en Microsoft Endpoint Manager o conceda esos permisos mediante la configuración de un rol en el portal de Defender. Vaya a **Roles** >  **de configuración** > **Agregar elemento**:

   :::image type="content" source="../media/add-role-in-mde.png" alt-text="Cree un nuevo rol en el portal de Defender.":::

   > [!TIP]
   > Puede modificar los roles existentes y agregar los permisos necesarios en lugar de crear roles adicionales en Microsoft Defender para punto de conexión

1. Al configurar el rol, agregue usuarios y asegúrese de seleccionar **Administrar la configuración de seguridad del punto de conexión en Microsoft Endpoint Manager**:

   :::image type="content" source="../media/add-role.png" alt-text="Conceda a los usuarios permisos para administrar la configuración.":::

1. Inicie sesión en el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

1. Seleccione **Seguridad** >  de punto de conexión **Microsoft Defender para punto de conexión** y establezca **Permitir Microsoft Defender para punto de conexión para aplicar configuraciones de seguridad de punto de conexión (versión preliminar)** en **Activado**.

   :::image type="content" source="../media/enable-mde-settings-management-mem.png" alt-text="Habilite la administración de la configuración de Microsoft Defender para punto de conexión en el Centro de administración de Microsoft Endpoint Manager.":::

   Al establecer esta opción en *Activado*, todos los dispositivos del ámbito de la plataforma de Microsoft Defender para punto de conexión que no estén administrados por Microsoft Endpoint Manager podrán incorporarse a Microsoft Defender para punto de conexión.

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Incorporar dispositivos a Microsoft Defender para punto de conexión

Microsoft Defender para punto de conexión admite varias opciones para incorporar dispositivos. Para obtener instrucciones actuales, consulte [Incorporación de herramientas y métodos para dispositivos Windows](/microsoft-365/security/defender-endpoint/security-config-management) en la documentación de Defender para punto de conexión.



## <a name="co-existence-with-microsoft-endpoint-configuration-manager"></a>Coexistencia con el punto de conexión de Microsoft Configuration Manager
En algunos entornos, es posible que desee usar la administración de seguridad para Microsoft Defender para punto de conexión con [Configuration Manager asociación de inquilinos](/mem/configmgr/tenant-attach/endpoint-security-get-started). Si usa ambos, tendrá que controlar la directiva a través de un único canal, ya que el uso de más de un canal crea la oportunidad de conflictos y resultados no deseados.

Para admitir esto, configure los *valores de Administración de seguridad mediante Configuration Manager* cambie a *Desactivado*.  Inicie sesión en el [portal de Microsoft 365 Defender](https://security.microsoft.com/) y vaya a Configuración **Endpoints** Configuration Management **Enforcement Scope (Ámbito de cumplimiento** **de administración de configuración de** puntos  >  de  >  conexión **de configuración** > ):

:::image type="content" source="../media/manage-security-settings-cfg-mgr.png" alt-text="Administrar la configuración de seguridad mediante Configuration Manager configuración.":::

>[!NOTE]
>Cuando se usa Security Management para Microsoft Defender para punto de conexión con Configuration Manager, la directiva de seguridad de punto de conexión debe aislarse en un plano de control único. Controlar la directiva a través de ambos canales puede provocar conflictos y resultados no deseados.


## <a name="create-azure-ad-groups"></a>Creación de grupos de Azure AD

Una vez que los dispositivos se incorporen a Defender para punto de conexión, deberá crear grupos de dispositivos para admitir la implementación de directivas para Microsoft Defender para punto de conexión.

Para identificar los dispositivos que se han inscrito con Microsoft Defender para punto de conexión pero no están administrados por Intune o Configuration Manager:

1. Inicie sesión en [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vaya a **Dispositivos** > **Todos los dispositivos** y, a continuación, seleccione la columna **Administrado por** para ordenar la vista de dispositivos.

   Los dispositivos que se incorporan a Microsoft Defender para punto de conexión y se han registrado pero no se administran mediante Intune muestran **Microsoft Defender para punto de conexión** en la columna *Administrado por*. Estos son los dispositivos que pueden recibir directivas de administración de seguridad para Microsoft Defender para punto de conexión.

   También encontrará dos etiquetas para los dispositivos que usan la administración de seguridad para Microsoft Defender para punto de conexión:

   - **MDEJoined: se** agrega a los dispositivos que están unidos al directorio como parte de este escenario.
   - **MDEManaged: se** agrega a los dispositivos que usan activamente el escenario de administración de seguridad. Esta etiqueta se quita del dispositivo si Defender para punto de conexión deja de administrar la configuración de seguridad.

Puede crear grupos para estos dispositivos [en Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) o [desde el Centro de administración de Microsoft Endpoint Manager](/mem/intune/fundamentals/groups-add).

## <a name="deploy-policy"></a>Implementar directiva

Después de crear uno o varios grupos de Azure AD que contienen dispositivos administrados por Microsoft Defender para punto de conexión, puede crear e implementar las siguientes directivas para Security Management para Microsoft Defender para punto de conexión en esos grupos:

- Antivirus
- Firewall
- Reglas de firewall
- Detección y respuesta de puntos de conexión

> [!TIP]
> Evite implementar varias directivas que administren la misma configuración en un dispositivo.
>
> Microsoft Endpoint Manager admite la implementación de varias instancias de cada tipo de directiva de seguridad de punto de conexión en el mismo dispositivo, y cada instancia de directiva la recibe el dispositivo por separado. Por lo tanto, un dispositivo podría recibir configuraciones independientes para la misma configuración de directivas diferentes, lo que da lugar a un conflicto. Algunas opciones de configuración (como Exclusiones antivirus) se combinarán en el cliente y se aplicarán correctamente.

1. Inicie sesión en el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vaya a **Seguridad del punto de conexión** y, a continuación, seleccione el tipo de directiva que desea configurar, antivirus o firewall y, a continuación, seleccione **Crear directiva**.

3. Escriba las propiedades siguientes o el tipo de directiva que seleccionó:

   - En Directiva antivirus, seleccione:
     - Plataforma: **Windows 10, Windows 11 y Windows Server (versión preliminar)**
     - Perfil: **Antivirus de Microsoft Defender (versión preliminar)**

   - En Directiva de firewall, seleccione:
     - Plataforma: **Windows 10, Windows 11 y Windows Server (versión preliminar)**
     - Perfil: **Firewall de Microsoft Defender (versión preliminar)**

   - En Directiva de reglas de firewall, seleccione:
     - Plataforma: **Windows 10, Windows 11 y Windows Server (versión preliminar)**
     - Perfil: **Reglas de firewall de Microsoft Defender (versión preliminar)**

   - En Endpoint Detection and Response policy (Directiva de detección y respuesta de puntos de conexión), seleccione:
     - Plataforma: **Windows 10, Windows 11 y Windows Server (versión preliminar)**
     - Perfil: **Detección y respuesta de puntos de conexión (versión preliminar)**

   >[!Note]
   > Estos perfiles se aplican a ambos dispositivos que se comunican a través de Mobile Administración de dispositivos (MDM) con Microsoft Intune, así como a los dispositivos que se comunican mediante el cliente Microsoft Defender para punto de conexión.
   >
   > Asegúrese de revisar el destino y los grupos según sea necesario.

4. Seleccione **Crear**.

5. En la página **Datos básicos**, escriba un nombre y una descripción para el perfil y, después, elija **Siguiente**.

6. En la página **Configuración** , seleccione la configuración que desea administrar con este perfil. Para obtener más información sobre una configuración, expanda su cuadro de diálogo de información y seleccione el vínculo *Más información* para ver la información de CSP de la configuración en la documentación en línea.

   Cuando haya finalizado la configuración, seleccione **Siguiente**.

7. En la página **Asignaciones** , seleccione los grupos de Azure AD que recibirán este perfil. Para obtener más información sobre la asignación de perfiles, vea [Asignación de perfiles de usuario y dispositivo](/mem/intune/configuration/device-profile-assign).

   Seleccione **Siguiente** para continuar.

   > [!TIP]
   >
   > - Los filtros de asignación no se admiten para los perfiles de Administración de configuración de seguridad.
   > - Solo *los objetos de dispositivo* son aplicables para la administración de Microsoft Defender para punto de conexión. No se admite la segmentación de usuarios.
   > - Las directivas configuradas se aplicarán a los clientes Microsoft Intune y Microsoft Defender para punto de conexión

8. Complete el proceso de creación de directivas y, a continuación, en la página **Revisar y crear** , seleccione **Crear**. El nuevo perfil se muestra en la lista cuando se selecciona el tipo de directiva del perfil creado.

9. Espere a que se asigne la directiva y vea una indicación correcta de que se aplicó la directiva.

10. Puede validar que la configuración se ha aplicado localmente en el cliente mediante la utilidad de [comandos Get-MpPreference](/powershell/module/defender/get-mppreference#examples) .
