---
title: Solucionar Windows problemas de configuración de 365 Business Cloud PC
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
description: Obtenga información sobre cómo solucionar problemas de configuración Windows equipos de 365 Business Cloud.
ms.date: 08/13/2021
ms.openlocfilehash: 5602df4eaf140fec86a28252bb88763bd6417f50
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58532936"
---
# <a name="troubleshoot-windows-365-business-cloud-pc-setup-issues"></a>Solucionar Windows problemas de configuración de 365 Business Cloud PC

Si los usuarios obtienen el error "Error de instalación" o si el programa de instalación tarda más de 90 minutos después de asignarles una licencia, siga los pasos descritos en este artículo para resolver el problema.

> [!IMPORTANT]
> Debe ser un administrador global para realizar la mayoría de las tareas descritas en este artículo. Si se pueden usar otros roles de administrador para un procedimiento específico, se observan antes del procedimiento. Si no tiene permiso para iniciar sesión o acceder a partes de Azure Portal, póngase en contacto con el administrador de TI. Para obtener más información acerca de las reglas de Azure, vea [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference). Para obtener más información sobre Azure Portal, vea [Introducción a Azure Portal](/azure/azure-portal/azure-portal-overview).

## <a name="step-1-verify-azure-ad-device-settings"></a>Paso 1. Comprobar la configuración del dispositivo de Azure AD

Asegúrese de **que los usuarios pueden unir dispositivos a Azure AD** está establecido en **Todos**.

1. Inicie sesión en el portal Microsoft Azure en [https://portal.azure.com/](https://go.microsoft.com/fwlink/p/?linkid=516942) .
2. En **Administrar Azure Active Directory**, seleccione **Ver**.
3. En el panel de navegación izquierdo, en **Administrar**, seleccione **Dispositivos** y, a continuación, **seleccione Configuración del dispositivo**.
4. Si **los usuarios pueden unir dispositivos** a Azure AD no está establecido en **Todos**, seleccione Todo **y,** a continuación, **seleccione Guardar**.
5. Vaya al [paso 2. Compruebe que la cuenta Windows 365 BPRT Permanent User system está activa.](#step-2-verify-that-the-windows-365-bprt-permanent-user-system-account-is-active)

## <a name="step-2-verify-that-the-windows-365-bprt-permanent-user-system-account-is-active"></a>Paso 2. Comprobar que la cuenta Windows 365 BPRT Permanent User system está activa

La primera vez que se asigna una licencia Windows 365 en la organización, se crea automáticamente en Azure AD una cuenta del sistema denominada **Windows 365 usuario permanente de BPRT.** No elimine esta cuenta ni realice ningún cambio en ella (como cambiar el nombre o UPN). Si se elimina la cuenta del sistema, se producirá un error en la configuración. Esta cuenta del sistema garantiza un proceso de configuración sin problemas y no tiene ninguna capacidad de escritura ni acceso a su organización más allá de las capacidades de servicio de ámbito de Windows 365 Empresa. Si elimina esta cuenta del sistema, debe abrir una nueva solicitud de soporte técnico para que se restaure.

Para asegurarse de que Windows cuenta del sistema de usuario permanente de 365 BPRT está activa en Azure AD, siga estos pasos.

1. En Azure Portal, vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">página Azure Active Directory información general.</a>
2. En la navegación izquierda, en **Administrar**, seleccione **Usuarios**.
3. En el cuadro de búsqueda, **escriba Windows 365 BPRT Permanent User** y, a continuación, presione **ENTRAR**.
4. Si la Windows del sistema de usuario permanente de 365 BPRT está presente, vaya al [paso 3. Compruebe que MFA basada en dispositivos está desactivada.](#step-3-verify-that-device-based-mfa-is-turned-off)
5. Si falta Windows cuenta del sistema de usuario permanente de 365  BPRT, en la navegación izquierda, seleccione Nueva solicitud de soporte técnico para abrir un vale de soporte técnico. Después de cerrar el vale de soporte técnico, vaya directamente al [paso 6. Restablecer los equipos en la nube](#step-6-reset-your-cloud-pcs).

## <a name="step-3-verify-that-device-based-mfa-is-turned-off"></a>Paso 3. Comprobar que MFA basada en dispositivos está desactivada

Es posible que la organización esté configurada para que la autenticación multifactor (MFA) sea necesaria para unir dispositivos con Azure AD. Si es así, debe desactivar esta configuración. Para asegurarse de que **Requerir autenticación multifactor para** registrar o unir dispositivos con Azure AD está establecido en **No**, siga estos pasos.

1. En Azure Portal, vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">página Azure Active Directory información general.</a>
2. En el panel de navegación izquierdo, en **Administrar**, seleccione **Dispositivos** y, a continuación, **seleccione Configuración del dispositivo**.
3. Si **Requerir autenticación multifactor para registrar** o unir dispositivos con Azure AD está establecido en **Sí**, seleccione **No** y, a continuación, **seleccione Guardar**.
4. Vaya al [paso 4. Asegúrese de que MFA no bloquee el programa de instalación](#step-4-make-sure-that-mfa-doesnt-block-setup).

## <a name="step-4-make-sure-that-mfa-doesnt-block-setup"></a>Paso 4. Asegúrese de que MFA no bloquea la instalación

Si no tiene una licencia de Azure AD Premium P1 que incluya el acceso condicional, vaya al [paso 5. Asegúrate de que la configuración de la entidad de MDM esté configurada correctamente.](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly) Si no sabes si la suscripción incluye Azure AD Premium P1, consulta [¿Qué suscripción tengo?](../admin-overview/what-subscription-do-i-have.md)

Si tiene una licencia de Azure AD Premium P1 que incluye acceso condicional, seleccione un usuario para que sea el primer usuario que inicie sesión en la página principal de Windows 365 después de completar los pasos restantes de este [https://windows365.microsoft.com](https://windows365.microsoft.com) artículo. Asegúrese de que no hay directivas de acceso condicional de MFA para ese primer usuario. MFA debe permanecer desactivado durante los intentos de instalación. Después de que todos los equipos en la nube se configuren correctamente en toda la organización, puede activar MFA para este usuario. Para obtener más información acerca de las directivas de acceso condicional, vea ¿Qué es el acceso [condicional en Azure Active Directory?](/azure/active-directory/conditional-access/overview).

Para comprobar si hay directivas de acceso condicional, siga estos pasos.

1. En Azure Portal, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=2169290" target="_blank">Directivas de acceso</a> condicional.
2. Si no hay directivas enumeradas, continúe con [el paso 5. Asegúrate de que la configuración de la entidad de MDM esté configurada correctamente.](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)
3. Si hay alguna directiva en la página, seleccione un nombre de directiva.
4. En la **sección Controles de Acceso,** en **Conceder**, si indica "0 controles seleccionados", vuelva a la lista directivas y seleccione la siguiente directiva. De lo contrario, continúe con el paso 5.
5. En la **sección Controles de acceso,** en **Conceder**, si indica que hay más de un control seleccionado, seleccione el **_vínculo n_ controles seleccionados.**
6. En el panel derecho, si está seleccionado Requerir autenticación **multifactor,** desactive la casilla y, a continuación, seleccione el **botón** Seleccionar.
   > [!TIP]
   > Como alternativa, puede excluir al primer usuario de la directiva. Para obtener información sobre cómo hacerlo, vea Administrar usuarios [excluidos de las directivas de acceso condicional.](/azure/active-directory/governance/conditional-access-exclusion)
7. Repita los pasos del 3 al 6 hasta que haya quitado MFA para todas las directivas de acceso condicional.
8. Vaya al [paso 5. Asegúrate de que la configuración de la entidad de MDM esté configurada correctamente.](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)

## <a name="step-5-make-sure-mdm-authority-configuration-is-set-up-correctly"></a>Paso 5. Asegúrese de que la configuración de la entidad MDM esté configurada correctamente

Si realizó cambios en función de los pasos 1 a 4 anteriores de este artículo, es posible que la causa raíz se resuelva ahora. Para comprobar que el problema está corregido, vaya al [paso 6. Restablecer los equipos en la nube](#step-6-reset-your-cloud-pcs).

Si no has realizado ningún cambio en los pasos 1-4, es posible que el error de configuración se deba a la configuración de la entidad de MDM en el entorno. Si es así, tiene dos rutas de acceso a seguir, dependiendo de si tiene previsto usar Microsoft Intune para administrar los equipos en la nube.

- Si usas o planeas usar Microsoft Intune para los equipos en la nube, sigue los pasos descritos en Ruta A: Asegúrate de que la configuración de Movilidad (MDM y MAM) esté configurada [correctamente.](#path-a-use-microsoft-intune-to-manage-your-cloud-pcs)
- Si no tienes previsto usar Microsoft Intune para administrar los equipos en la nube, sigue los pasos descritos en [Path B: Turn off automatic MDM enrollment](#path-b-turn-off-automatic-mdm-enrollment).

### <a name="path-a-use-microsoft-intune-to-manage-your-cloud-pcs"></a>Ruta A. Use Microsoft Intune para administrar los equipos en la nube

Si ya usas Microsoft Intune, o planeas usarlo para administrar los equipos en la nube de Windows 365, asegúrate de que la configuración de Movilidad (MDM y **MAM)** en Azure AD esté configurada correctamente.

1. En Azure Portal, vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">página Azure Active Directory información general.</a>
2. En la navegación izquierda, en **Administrar**, seleccione **Movilidad (MDM y MAM)** y, a continuación, **seleccione Microsoft Intune**.
3. En la **página Configurar,** junto al ámbito **de usuario MDM,** seleccione **Algunos** o **Todos** y, a continuación, **seleccione Guardar**.
4. En la navegación izquierda, en **Administrar**, seleccione **Movilidad (MDM y MAM),** seleccione **Microsoft Intune Inscripción** y, a continuación, repita el paso 3.

Los usuarios a los que se les asigna un equipo en la nube deben tener asignada una licencia de Intune. No es necesario asignar una licencia de Intune a la cuenta del sistema CloudPCBPRT.

> [!IMPORTANT]
> Para asignar licencias, debe ser administrador global o de licencias o tener un rol con permisos de licencia.

1. En el [centro Microsoft Endpoint Manager de administración,](https://go.microsoft.com/fwlink/p/?linkid=2169290)seleccione **Usuarios** Todos  >  **los usuarios**.
2. En la **lista Todos los** usuarios, seleccione un usuario.
3. En la página **Perfil de** usuario, seleccione **Licencias**.
4. En la **página Licencias,** seleccione **Asignaciones**.
5. Busque **Intune**, active la casilla y, a continuación, **seleccione Guardar**. La cuenta de usuario ahora tiene los permisos necesarios para usar el servicio e inscribir dispositivos.
6. Vaya al [paso 6. Restablecer los equipos en la nube](#step-6-reset-your-cloud-pcs).

### <a name="path-b-turn-off-automatic-mdm-enrollment"></a>Ruta B. Desactivar la inscripción automática de MDM

Si no tienes previsto usar Microsoft Intune para la administración del equipo en la nube, debes desactivar la inscripción automática de MDM.

> [!IMPORTANT]
> Si no eres el administrador de MDM, no use ninguno de los siguientes procedimientos sin consultar primero con el administrador de TI. Solo siga estos procedimientos si no se están configurando equipos en la nube. Cualquier cambio en la configuración podría afectar al entorno de administración. Si necesita ayuda, póngase [en contacto con el soporte técnico de Intune](/mem/get-support).

#### <a name="option-1-use-the-azure-ad-portal-to-turn-off-automatic-intune-enrollment"></a>Opción 1. Usar Azure AD Portal para desactivar la inscripción automática de Intune

1. En Azure Portal, vaya a la <a href="https://go.microsoft.com/fwlink/p/?linkid=516942" target="_blank">página Azure Active Directory información general.</a>
2. En la navegación izquierda, en **Administrar**, seleccione **Movilidad (MDM y MAM)** y, a continuación, **seleccione Microsoft Intune**.
3. En la **página Configurar,** junto al ámbito de usuario MDM, selecciona **Ninguno** y, a continuación, **selecciona Guardar**.
4. En la navegación izquierda, en **Administrar**, seleccione **Movilidad (MDM y MAM),** seleccione **Microsoft Intune Inscripción** y, a continuación, repita el paso 3.
5. Vaya al [paso 6. Restablecer los equipos en la nube](#step-6-reset-your-cloud-pcs).

#### <a name="option-2-use-microsoft-graph-to-turn-off-automatic-intune-enrollment"></a>Opción 2: Usar Microsoft Graph desactivar la inscripción automática de Intune

Si no puedes usar el portal de administración Microsoft Azure para configurar **Mobility (MDM y MAM)** como se indica en [la opción 1. Use Azure AD Portal para](#option-1-use-the-azure-ad-portal-to-turn-off-automatic-intune-enrollment)desactivar la inscripción automática de Intune, verá una advertencia que dice: "La inscripción automática de MDM solo está disponible para Azure AD Premium suscriptores". En este caso, debes usar Microsoft Graph desactivar las directivas MDM en tu entorno.

1. Vaya a Graph Explorer en <a href="https://go.microsoft.com/fwlink/p/?linkid=2170005">https://developer.microsoft.com/graph/graph-explorer</a> .
2. En **Graph,** seleccione **Iniciar sesión en Graph Explorer** e inicie sesión con su cuenta de administrador global.
3. Si ve el cuadro **de diálogo Permisos solicitados,** seleccione **Aceptar**.
4. Junto al nombre de la cuenta, seleccione el **botón Más** acciones (los tres puntos) y, a continuación, seleccione **Seleccionar permisos**.
5. En el **panel Permisos,** expanda **Directiva**, seleccione **Directiva.Read.All** y **Policy.ReadWrite.MobilityManagement** y, a continuación, **seleccione Consentimiento**.
6. Si ve el cuadro **de diálogo Permisos solicitados,** active la casilla Consentimiento en **nombre** de su organización y, a continuación, **seleccione Aceptar**.
7. Vuelva **a expandir** Directiva, compruebe que la columna Estado de **Policy.Read.All** y **Policy.ReadWrite.MobilityManagement** diga **Consented** y, a continuación, cierre el **panel Permisos.** 
8. En la primera lista desplegable, seleccione **GET**.
9. En el cuadro de texto, escriba la siguiente cadena y, a continuación, **seleccione Ejecutar consulta**:  
    `https://graph.microsoft.com/beta/policies/mobileDeviceManagementPolicies`  
    Esta consulta recupera la lista de directivas de administración de dispositivos de la organización.
   Los resultados del panel **vista previa** de respuesta deben ser similares al siguiente fragmento de código:

    ```
    {
        "@odata.context": "https://graph.microsoft.com/beta/$metadata#mobilityManagementPolicies",
        "value": [
            {
                "id": "0000000a-0000-0000-c000-000000000000",
                "appliesTo": "all",
                "complianceUrl": null,
                "description": "Device Management Policy for Microsoft Intune",
                "discoveryUrl": null,
                "displayName": "Microsoft Intune",
                "isValid": true,
                "termsOfUseUrl": null
            },
            {
                "id": "d4ebce55-015a-49b5-a083-c84d1797ae8c",
                "appliesTo": "none",
                "complianceUrl": "https://portal.manage.microsoft.com/?portalAction",
                "description": "Device Management Policy for Microsoft Intune Enrollment",
                "discoveryUrl": "https://enrollment.manage.microsoft.com/enrollmentserver/discovery.svc",
                "displayName": "Microsoft Intune Enrollment",
                "isValid": true,
                "termsOfUseUrl": "https://portal.manage.microsoft.com/TermsofUse.aspx"
            }
        ]
    }
    ```
10. Si el `"appliesTo"` valor no es ninguno **para** todas las directivas enumeradas, vaya al [paso 6. Restablecer los equipos en la nube](#step-6-reset-your-cloud-pcs). De lo contrario, continúe con el paso 11.
11. En la primera lista desplegable, seleccione **PATCH**.
12. En el cuadro de texto, escriba la siguiente cadena:  
    `https://graph.microsoft.com/beta/policies/mobileDeviceManagementPolicies/0000000a-0000-0000-c000-000000000000`
13. En la **sección Cuerpo de** solicitud, escriba el siguiente fragmento de código y, a continuación, seleccione Ejecutar **consulta**:
    ```
    {
        "appliesTo": "none"
    }
    ```
14. En el cuadro de texto, escriba la siguiente cadena:  
    `https://graph.microsoft.com/beta/policies/mobileDeviceManagementPolicies/d4ebce55-015a-49b5-a083-c84d1797ae8c`
15. En la **sección Cuerpo de** la solicitud, deje el fragmento de código que escribió en el paso 13 y, a continuación, seleccione Ejecutar **consulta**.
16. En la primera lista desplegable, seleccione **GET**.
17. Borra cualquier texto de la **sección Cuerpo de la** solicitud.
18. En el cuadro de texto, escriba la siguiente cadena y, a continuación, **seleccione Ejecutar consulta**:  
    `https://graph.microsoft.com/beta/policies/mobileDeviceManagementPolicies`

    Los resultados del panel **de vista Respuesta** deben ser similares al siguiente fragmento de código.
    ```
    {
        "@odata.context": "https://graph.microsoft.com/beta/$metadata#mobilityManagementPolicies",
        "value": [
            {
                "id": "0000000a-0000-0000-c000-000000000000",
                "appliesTo": "none",
                "complianceUrl": "https://portal.manage.microsoft.com/?portalAction=Compliance",
                "description": "Device Management Policy for Microsoft Intune",
                "discoveryUrl": "https://enrollment.manage.microsoft.com/enrollmentserver/discovery.svc”,
                "displayName": "Microsoft Intune",
                "isValid": true,
                "termsOfUseUrl": "https://portal.manage.microsoft.com/TermsofUse.aspx"
            },
            {
                "id": "d4ebce55-015a-49b5-a083-c84d1797ae8c",
                "appliesTo": "none",
                "complianceUrl": "https://portal.manage.microsoft.com/?portalAction",
                "description": "Device Management Policy for Microsoft Intune Enrollment",
                "discoveryUrl": "https://enrollment.manage.microsoft.com/enrollmentserver/discovery.svc",
                "displayName": "Microsoft Intune Enrollment",
                "isValid": true,
                "termsOfUseUrl": "https://portal.manage.microsoft.com/TermsofUse.aspx"
            }
        ]
    } 
    ```

    Los `"appliesTo"` valores de todas las directivas ahora se establecen en **ninguno**. Esta consulta comprueba que el ámbito ha cambiado correctamente para las directivas de administración de dispositivos de la organización.
19. Vaya al [paso 6. Restablecer los equipos en la nube](#step-6-reset-your-cloud-pcs).

## <a name="step-6-reset-your-cloud-pcs"></a>Paso 6. Restablecer los equipos en la nube

Después de completar los pasos de solución de problemas de este artículo, los usuarios deben reiniciar la configuración del equipo en la nube. 

Si acaba de completar [el paso 3. Compruebe que MFA basada en dispositivos esté](#step-3-verify-that-device-based-mfa-is-turned-off)desactivada, espere al menos diez minutos para que los cambios entren en vigor antes de continuar. Asegúrese de que el usuario que excluyó de MFA sea el primer usuario que inicie sesión en la página principal de [Windows 365](https://windows365.microsoft.com).

Diga a todos los usuarios de PC en la nube que vieron el error "Error de instalación" que usen los siguientes pasos para restablecer sus equipos en la nube.

1. En la [Windows principal de 365](https://windows365.microsoft.com), seleccione el icono de engranaje para cualquier equipo en la nube que tenga el estado "Error de instalación" y, a continuación, **seleccione Restablecer**. Esta acción reinicia el proceso de instalación.
2. Después del restablecimiento, si se muestra el error "Error de instalación" y omitió [el paso 5. Asegúrate de que la](#step-5-make-sure-mdm-authority-configuration-is-set-up-correctly)configuración de la entidad mdm esté configurada correctamente, completa ese paso y vuelve a restablecer cloudPC. De lo contrario, en la navegación izquierda, seleccione **Nueva solicitud de soporte técnico** para abrir un vale de soporte técnico.
