---
title: Configurar el cifrado de mensajes de Microsoft Purview
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/16/2022
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Obtenga información sobre el cifrado de mensajes de Microsoft Purview que permite la comunicación de correo electrónico protegida con personas dentro y fuera de su organización.
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
ms.openlocfilehash: 828588491c3efbc696994f6073ca4ce849a64be5
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66622137"
---
# <a name="set-up-message-encryption"></a>Configurar el cifrado de mensajes

El cifrado de mensajes de Microsoft Purview permite a las organizaciones compartir correos electrónicos protegidos con cualquier persona en cualquier dispositivo. Los usuarios pueden intercambiar mensajes protegidos con otras organizaciones de Microsoft 365, así como con terceros mediante Outlook.com, Gmail y otros servicios de correo electrónico.

Siga los pasos que se indican a continuación para asegurarse de que el cifrado de mensajes de Microsoft Purview está disponible en su organización.

## <a name="verify-that-azure-rights-management-is-active"></a>Verificar que Azure Rights Management está habilitada

Cifrado de mensajes de Microsoft Purview aprovecha las características de protección de [Azure Rights Management Services (Azure RMS),](/azure/information-protection/what-is-information-protection)la tecnología que usa [Azure Information Protection](/azure/information-protection/what-is-azure-rms) para proteger correos electrónicos y documentos mediante controles de cifrado y acceso.

El único requisito previo para usar el cifrado de mensajes de Microsoft Purview es que [Azure Rights Management](/azure/information-protection/what-is-azure-rms) debe activarse en el inquilino de su organización. Si es así, Microsoft 365 activa automáticamente el cifrado de mensajes y no es necesario hacer nada.

Azure RMS también se activa automáticamente para la mayoría de los planes aptos, por lo que probablemente tampoco tenga que hacer nada al respecto. Consulte [activación de Azure Rights Management](/azure/information-protection/activate-service) para obtener más información.

> [!IMPORTANT]
> Si usa el servicio Active Directory Rights Management (AD RMS) con Exchange Online, debe [migrar a Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) antes de poder usar el cifrado de mensajes. El cifrado de mensajes de Microsoft Purview no es compatible con AD RMS.

Para más información, vea:

- [Preguntas más frecuentes sobre el cifrado de mensajes](ome-faq.yml) para comprobar si el plan de suscripción incluye Azure Information Protection (que incluye la funcionalidad de Azure RMS).
- [Azure Information Protection](https://azure.microsoft.com/services/information-protection/) para obtener información sobre cómo comprar una suscripción apta.

### <a name="manually-activating-azure-rights-management"></a>Activar Azure Rights Management manualmente

Si deshabilitó Azure RMS, o si no se activó automáticamente por algún motivo, puede activarlo manualmente en:

- **El Centro de administración de Microsoft 365**: vea [Cómo activar Azure Rights Management desde el centro de administración](/azure/information-protection/activate-office365) para obtener instrucciones.
- **Azure Portal**: vea [Cómo activar Azure Rights Management desde Azure Portal](/azure/information-protection/activate-azure) para obtener instrucciones.

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Configurar la administración del espacio empresarial de Azure Information Protection

Este paso es opcional. Permitir que Microsoft administre la clave raíz de Azure Information Protection es la configuración predeterminada y el procedimiento recomendado para la mayoría de organizaciones. Si este es el caso, no es necesario que realice ninguna acción.

Hay muchos motivos, por ejemplo, los requisitos de cumplimiento, que pueden requerir la creación y administración de su propia clave raíz (también conocido como Bring your own key (BYOK)). Si este es el caso, se recomienda completar los pasos necesarios antes de configurar el cifrado de mensajes de Microsoft Purview. Vea [Planificar e implementar la clave de espacio empresarial de Azure Information Protection](/information-protection/plan-design/plan-implement-tenant-key) para obtener más información.

## <a name="verify-microsoft-purview-message-encryption-configuration-in-exchange-online-powershell"></a>Comprobar la configuración del cifrado de mensajes de Microsoft Purview en Exchange Online PowerShell

Puede comprobar que el inquilino de Microsoft 365 está configurado correctamente para usar el cifrado de mensajes de Microsoft Purview en [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).

1. [Conectarse a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) usando una cuenta con permisos de administrador global en su espacio empresarial de Microsoft 365.

2. Ejecute el cmdlet Get-IRMConfiguration.

     Debería ver un valor de $True para el parámetro AzureRMSLicensingEnabled, que indica que el cifrado de mensajes de Microsoft Purview está configurado en su inquilino. Si no es así, use Set-IRMConfiguration para establecer el valor de AzureRMSLicensingEnabled en $True para habilitar el cifrado de mensajes de Microsoft Purview.

3. Ejecute el cmdlet test-IRMConfiguration usando la siguiente sintaxis:

   ```powershell
   Test-IRMConfiguration [-Sender <email address> -Recipient <email address>]
   ```

   **Ejemplo**:

   ```powershell
   Test-IRMConfiguration -Sender securityadmin@contoso.com -Recipient securityadmin@contoso.com
   ```

   - Para el remitente y el destinatario, use la dirección de correo electrónico de cualquier usuario de su espacio empresarial de Microsoft 365.

     Sus resultados deben ser similares a estos:

     ```console
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - El nombre de su organización reemplazará a *Contoso*.

   - Los nombres de las plantillas predeterminadas pueden diferir de los que se muestran arriba. Vea [Configurar y administrar plantillas para Azure Information Protection](/azure/information-protection/configure-policy-templates) para obtener más información.

4. Si se produce un error en la prueba con un mensaje de error **Error al adquirir las plantillas de RMS**, ejecute los siguientes comandos y ejecute el cmdlet Test-IRMConfiguration para comprobar que funciona.

   ```powershell
   $RMSConfig = Get-AadrmConfiguration
   $LicenseUri = $RMSConfig.LicensingIntranetDistributionPointUrl
   Set-IRMConfiguration -LicensingLocation $LicenseUri
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```
5. Ejecute el cmdlet Remove-PSSession para desconectarse del servicio Rights Management.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-microsoft-purview-message-encryption"></a>Pasos siguientes: definir reglas de flujo de correo para usar el cifrado de mensajes de Microsoft Purview

Si hay reglas de flujo de correo configuradas previamente para cifrar el correo electrónico en su organización, debe actualizar las reglas existentes para usar el cifrado de mensajes de Microsoft Purview. Para las nuevas implementaciones, debe crear nuevas reglas de flujo de correo.

> [!IMPORTANT]
> Si no actualiza las reglas de flujo de correo existentes, los usuarios seguirán recibiendo correo cifrado con el formato de archivo adjunto HTML anterior, en lugar de la nueva experiencia sin fisuras.

Las reglas de flujo de correo determinan bajo qué condiciones se deben cifrar los mensajes de correo electrónico, así como las condiciones para quitar ese cifrado. Al establecer una acción para una regla, todos los mensajes que coinciden con las condiciones de la regla se cifran al enviarse.

Para conocer los pasos para crear el cifrado de mensajes de reglas de flujo de correo, consulte [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).

Para actualizar las reglas existentes para usar el cifrado de mensajes de Microsoft Purview:

1. En el Centro de administración de Microsoft 365, vaya a **Centros de administración**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">**Exchange**</a>.
2. En el centro de administración de Exchange, vaya a **Flujo de correo > Reglas**.
3. Para cada regla, en **Hacer lo siguiente**:
    - Seleccione **Modificar la seguridad de los mensajes**.
    - Seleccione **Aplicar el cifrado de mensajes de Office 365 y la protección de derechos**.
    - Seleccione una plantilla RMS de la lista.
    - Seleccione **Guardar**.
    - Seleccione **Aceptar**.
