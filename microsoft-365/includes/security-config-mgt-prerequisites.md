---
title: incluir archivo
description: incluir archivo
author: mjcaparas
ms.service: microsoft-365-enterprise
ms.author: macapara
ms.openlocfilehash: e8d19f8ab5423ccc0441d29efab2ecdb3eb27a04
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677198"
---
## <a name="prerequisites"></a>Requisitos previos

Revise las siguientes secciones para ver los requisitos de security management for Microsoft Defender for Endpoint Scenario:

### <a name="environment"></a>Entorno

Cuando un dispositivo se incorpora a Microsoft Defender para endpoint:

- El dispositivo se busca una presencia de Endpoint Manager existente, Ya sea Configuration Manager o Intune
- Los dispositivos sin Endpoint Manager presencia habilitan la característica administración de seguridad
- Se crea una confianza con Azure Active Directory si aún no existe una
- Azure Active Directory confianza se usa para comunicarse con Endpoint Manager (Intune) y recuperar directivas
- La recuperación de directivas Endpoint Manager se aplica en el dispositivo mediante Microsoft Defender para endpoint

### <a name="active-directory-requirements"></a>Requisitos de Active Directory

Cuando un dispositivo unido a un dominio crea una confianza con Azure Active Directory, este escenario se conoce como un escenario de *unión* Azure Active Directory híbrido. La Administración de seguridad para Microsoft Defender para endpoint admite completamente este escenario con los siguientes requisitos:

- Azure Active Directory Conectar (AAD Conectar) debe sincronizarse con el inquilino que se usa desde Microsoft Defender para endpoint
- La Azure Active Directory híbrida debe configurarse en el entorno (ya sea a través de federación o AAD Conectar sincronización)
- AAD Conectar Sync debe incluir los objetos de *dispositivo* en el ámbito de sincronización con Azure Active Directory (cuando sea necesario para la unión)
- AAD Conectar las reglas de sincronización deben modificarse para Server 2012 R2 (cuando se necesite compatibilidad con Server 2012 R2)

### <a name="connectivity-requirements"></a>Requisitos de conectividad

Los dispositivos deben tener acceso a los siguientes puntos de conexión:

- `enterpriseregistration.windows.net`- Para Azure AD registro.
- `login.microsoftonline.com`- Para Azure AD registro.
- `*.dm.microsoft.com` - El uso de un comodín admite los puntos de conexión de servicio en la nube que se usan para la inscripción, la protección y los informes, y que pueden cambiar a medida que se escala el servicio.

### <a name="supported-platforms"></a>Plataformas compatibles

Las directivas de Microsoft Defender para la administración de seguridad de puntos de conexión son compatibles con las siguientes plataformas de dispositivos:

- Windows 10 Professional/Enterprise (con [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541))
- Windows Server 2012 R2 con [Microsoft Defender para Down-Level dispositivos](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2016 con [Microsoft Defender para Down-Level dispositivos](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2019 (con [KB5006744](https://support.microsoft.com/topic/october-19-2021-kb5006744-os-build-17763-2268-preview-e043a8a3-901b-4190-bb6b-f5a4137411c0))
- Windows Server 2022


### <a name="licensing-and-subscriptions"></a>Licencias y suscripciones

Para usar la administración de seguridad para Microsoft Defender para Endpoint, necesita:

- Una suscripción que concede licencias para Microsoft Defender para Endpoint, como Microsoft 365, o una licencia independiente solo para Microsoft Defender para Endpoint. Para obtener información actual acerca de las opciones, vea [Requisitos mínimos de Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/minimum-requirements).

  *Cualquier suscripción* que conceda licencias de Punto de conexión de Microsoft Defender también concede a su inquilino acceso al nodo de seguridad endpoint del centro de administración de Microsoft Endpoint Manager cliente. El nodo de seguridad de extremo es donde configurarás e implementarás directivas para administrar Microsoft Defender para Endpoint para tus dispositivos y supervisar el estado del dispositivo.

## <a name="architecture"></a>Arquitectura

El siguiente diagrama es una representación conceptual de la solución de administración de configuración de seguridad de Microsoft Defender para endpoints.


:::image type="content" alt-text="Representación conceptual de la solución de administración de configuración de seguridad de Microsoft Defender para endpoints" source="../security/defender-endpoint/images/mde-architecture.png":::


1. Dispositivos incorporados a Microsoft Defender para endpoint.

2. Se establece una confianza entre cada dispositivo y Azure AD. Cuando un dispositivo tiene una confianza existente, se usa. Cuando los dispositivos no se han registrado, se crea una nueva confianza.


3. Los dispositivos usan su Azure AD identity para comunicarse con Endpoint Manager. Esta identidad permite Microsoft Endpoint Manager distribuir directivas dirigidas a los dispositivos cuando se desensa.

4. Defender for Endpoint notifica el estado de la directiva de nuevo a Endpoint Manager.

## <a name="configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management"></a>Configurar el espacio empresarial para admitir Microsoft Defender para la administración de configuración de endpoint security

Para admitir Microsoft Defender para la administración de la configuración de seguridad de puntos de conexión a través del centro de administración de Microsoft Endpoint Manager, debe habilitar la comunicación entre ellos desde cada consola.

1. Inicie sesión en [Microsoft 365 Defender portal](https://security.microsoft.com/) y vaya **a Configuración** Endpoints Configuration Management Enforcement Scope y habilite las plataformas para la  >    >    >   administración de la configuración de seguridad:

   :::image type="content" source="../media/enable-mde-settings-management-defender.png" alt-text="Habilita Microsoft Defender para la administración de la configuración de puntos de conexión en la consola de Defender.":::

2. Asegúrese de que los usuarios relevantes tienen permisos para administrar la configuración de seguridad de puntos de conexión en Microsoft Endpoint Manager o conceder dichos permisos mediante la configuración de un rol en el portal de Defender. Vaya a **Configuración**  >  **Roles Agregar**  >  **elemento**:

   :::image type="content" source="../media/add-role-in-mde.png" alt-text="Cree un nuevo rol en el portal de Defender.":::

   > [!TIP]
   > Puede modificar roles existentes y agregar los permisos necesarios frente a la creación de roles adicionales en Microsoft Defender para endpoint

3. Al configurar el rol, agregue usuarios y asegúrese de seleccionar Administrar la configuración de seguridad del punto de conexión **en Microsoft Endpoint Manager**:

   :::image type="content" source="../media/add-role.png" alt-text="Conceder permisos a los usuarios para administrar la configuración.":::

4. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

5. Seleccione **Endpoint security** Microsoft Defender for  >  **Endpoint** y establezca Allow Microsoft Defender for Endpoint to enforce Endpoint Security **Configurations (Preview)** en **On**.

   :::image type="content" source="../media/enable-mde-settings-management-mem.png" alt-text="Habilite Microsoft Defender para la administración de la configuración de puntos de conexión en el Microsoft Endpoint Manager de administración.":::

   Al establecer esta opción en *On*, todos los dispositivos del ámbito de plataforma de Microsoft Defender para endpoint que no están administrados por Microsoft Endpoint Manager podrán incorporarse a Microsoft Defender para Endpoint.

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Incorporar dispositivos a Microsoft Defender para punto de conexión

Microsoft Defender para endpoint admite varias opciones para incorporar dispositivos. Para obtener instrucciones actuales, consulta Herramientas de incorporación y métodos [para Windows dispositivos en](/microsoft-365/security/defender-endpoint/security-config-management) la documentación de Defender para endpoints.

Los dispositivos que administras con Intune o Configuration Manager no son compatibles con este escenario.

## <a name="create-azure-ad-groups"></a>Crear Azure AD grupos

Después de que los dispositivos se incorpore a Defender for Endpoint, tendrás que crear grupos de dispositivos para admitir la implementación de directivas para Microsoft Defender para Endpoint.

Para identificar los dispositivos que se han inscrito en Microsoft Defender para Endpoint pero que no están administrados por Intune o Configuration Manager:

1. Inicie sesión en [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vaya a  >  **Dispositivos Todos los** dispositivos y, a continuación, seleccione la columna Administrado **por** para ordenar la vista de dispositivos.

   Los dispositivos que se incorpore a Microsoft Defender para Endpoint y que se han registrado pero no están administrados por Intune o Configuration Manager muestran **Microsoft Defender** para endpoint en la columna *Administrado por.* Estos son los dispositivos que pueden recibir directivas de administración de seguridad para Microsoft Defender para endpoint.

Puede crear grupos para estos dispositivos [en Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) o desde el centro de [administración Microsoft Endpoint Manager.](/mem/intune/fundamentals/groups-add)

## <a name="deploy-policy"></a>Implementar directiva

Después de crear uno o más grupos de Azure AD que contienen dispositivos administrados por Microsoft Defender para endpoint, puede crear e implementar las siguientes directivas de administración de seguridad para Microsoft Defender para endpoint en esos grupos:

- Antivirus
- Firewall
- Reglas de firewall
- Detección y respuesta de extremos

> [!TIP]
> Evite implementar varias directivas que administren la misma configuración en un dispositivo.
>
> Microsoft Endpoint Manager permite implementar varias instancias de cada tipo de directiva de seguridad de extremo en el mismo dispositivo, con cada instancia de directiva que recibe el dispositivo por separado. Por lo tanto, un dispositivo puede recibir configuraciones independientes para la misma configuración de diferentes directivas, lo que da como resultado un conflicto. Algunas opciones de configuración (como exclusiones de antivirus) se combinarán en el cliente y se aplicarán correctamente.

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vaya a **Seguridad de extremo** y, a continuación, seleccione el tipo de directiva que desea configurar, ya sea Antivirus o Firewall y, a continuación, seleccione Crear **directiva**.

3. Escriba las siguientes propiedades o el tipo de directiva que ha seleccionado:

   - Para la directiva antivirus, seleccione:
     - Plataforma: **Windows 10, Windows 11 y Windows server (versión preliminar)**
     - Perfil: **Antivirus de Microsoft Defender (versión preliminar)**

   - Para directiva de firewall, seleccione:
     - Plataforma: **Windows 10, Windows 11 y Windows server (versión preliminar)**
     - Perfil: **Firewall de Microsoft Defender (versión preliminar)**

   - En Directiva de reglas de firewall, seleccione:
     - Plataforma: **Windows 10, Windows 11 y Windows server (versión preliminar)**
     - Perfil: **Reglas de firewall de Microsoft Defender (versión preliminar)**

   - Para la directiva de detección y respuesta de puntos de conexión, seleccione:
     - Plataforma: **Windows 10, Windows 11 y Windows server (versión preliminar)**
     - Perfil: **detección y respuesta de extremos (versión preliminar)**

4. Seleccione **Crear**.

5. En la **página Conceptos básicos,** escriba un nombre y una descripción para el perfil y, a continuación, elija **Siguiente**.

6. En la **página Configuración,** seleccione la configuración que desea administrar con este perfil. Para obtener más información sobre una configuración,  expanda su cuadro de diálogo de información y seleccione el vínculo Más información para ver la información de CSP para la configuración en la documentación en línea.

   Cuando haya terminado de configurar la configuración, seleccione **Siguiente**.

7. En la **página Asignaciones,** seleccione los Azure AD que recibirán este perfil. Para obtener más información sobre la asignación de perfiles, vea [Asignar perfiles de usuario y dispositivo.](/mem/intune/configuration/device-profile-assign)

   Seleccione **Siguiente** para continuar.

   > [!TIP]
   >
   > - Los filtros de asignación no son compatibles con los perfiles de administración de configuración de seguridad.
   > - Solo *los objetos device* son aplicables a Microsoft Defender para la administración de puntos de conexión. No se admite la segmentación de usuarios.
   > - Las directivas configuradas se aplicarán tanto a Microsoft Intune como a Microsoft Defender para clientes de punto de conexión

8. Complete el proceso de creación de directivas y, a continuación, en la **página Revisar +** **crear,** seleccione Crear . El nuevo perfil se muestra en la lista al seleccionar el tipo de directiva para el perfil que creó.

9. Espere a que se asigne la directiva y vea una indicación correcta de que se aplicó la directiva.

10. Puede validar que la configuración se aplica localmente en el cliente mediante la utilidad de comandos [Get-MpPreference.](/powershell/module/defender/get-mppreference#examples)

