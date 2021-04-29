---
title: Recomendaciones de directiva de contraseñas
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Obtenga información acerca de cómo hacer que su organización sea más segura frente a ataques a contraseñas y por qué debe prohibir contraseñas comunes y habilitar la autenticación multifactor basada en riesgos.
ms.openlocfilehash: d3f86a6e85ab2f8e469a57ea98a661e4cc453673
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073870"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="ef064-103">Recomendaciones de directiva de contraseñas</span><span class="sxs-lookup"><span data-stu-id="ef064-103">Password policy recommendations</span></span>

<span data-ttu-id="ef064-104">Como administrador de una organización, usted es el responsable de configurar la directiva de contraseñas para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="ef064-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="ef064-105">El establecimiento de la Directiva de contraseñas puede resultar complicado y confuso, y en este artículo se proporcionan recomendaciones para que la organización sea más segura frente a ataques de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ef064-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="ef064-106">Para determinar con qué frecuencia expiran las contraseñas de Microsoft 365 en la organización, vea [Establecer la directiva de expiración de contraseñas para Microsoft 365](../manage/set-password-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="ef064-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="ef064-107">Para obtener más información acerca de las contraseñas de Microsoft 365, vea:</span><span class="sxs-lookup"><span data-stu-id="ef064-107">For more information about Microsoft 365 passwords, see:</span></span>

<span data-ttu-id="ef064-108">[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ef064-108">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>

<span data-ttu-id="ef064-109">[Configurar la contraseña de un usuario individual para que nunca expire](../add-users/set-password-to-never-expire.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ef064-109">[Set an individual user's password to never expire](../add-users/set-password-to-never-expire.md) (artice)</span></span>

<span data-ttu-id="ef064-110">[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ef064-110">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="ef064-111">[Volver a enviar la contraseña de un usuario: ayuda para administradores](../add-users/resend-user-password.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ef064-111">[Resend a user's password - Admin Help](../add-users/resend-user-password.md) (article)</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="ef064-112">Comprender las recomendaciones de contraseña</span><span class="sxs-lookup"><span data-stu-id="ef064-112">Understanding password recommendations</span></span>

<span data-ttu-id="ef064-113">Los procedimientos recomendados para las contraseñas se dividen en algunas amplias categorías:</span><span class="sxs-lookup"><span data-stu-id="ef064-113">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="ef064-114">**Resisten los ataques comunes** esto implica la elección del lugar donde los usuarios introducen las contraseñas (dispositivos conocidos y de confianza con una detección de malware, sitios validados) y la elección de la contraseña que debe elegir (longitud y unicidad).</span><span class="sxs-lookup"><span data-stu-id="ef064-114">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="ef064-115">**Refrenan ataques exitosos** el contener ataques de hackers satisfactoriamente consiste en limitar la exposición a un servicio específico, o bien evitar que se produzcan daños, en caso de que se robe la contraseña de un usuario.</span><span class="sxs-lookup"><span data-stu-id="ef064-115">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="ef064-116">Por ejemplo, si se asegura de que una infracción de las credenciales de la red social no haga que su cuenta bancaria sea vulnerable, o no permita que una cuenta guardada mal protegida acepte vínculos de restablecimiento de una cuenta importante.</span><span class="sxs-lookup"><span data-stu-id="ef064-116">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="ef064-117">**Entender la naturaleza humana** muchos de los procedimientos válidos de contraseñas no se encuentran en el comportamiento humano natural.</span><span class="sxs-lookup"><span data-stu-id="ef064-117">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="ef064-118">Entender la naturaleza humana es fundamental, ya que la investigación muestra que casi todas las reglas que se imponen a los usuarios tendrán como resultado debilitar la calidad de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="ef064-118">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="ef064-119">Los requisitos de longitud, los requisitos de caracteres especiales y los requisitos de cambio de contraseña todos provocan la normalización de las contraseñas, lo que hace que resulte más fácil averiguar o descifrar contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ef064-119">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="ef064-120">Instrucciones de contraseña para administradores</span><span class="sxs-lookup"><span data-stu-id="ef064-120">Password guidelines for administrators</span></span>

<span data-ttu-id="ef064-121">El principal objetivo de un sistema de contraseña más seguro es la diversidad de las contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ef064-121">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="ef064-122">Desea que la Directiva de contraseñas contenga una gran cantidad de contraseñas distintas y difíciles de adivinar.</span><span class="sxs-lookup"><span data-stu-id="ef064-122">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="ef064-123">Estas son algunas recomendaciones para mantener su organización lo más segura posible.</span><span class="sxs-lookup"><span data-stu-id="ef064-123">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="ef064-124">Mantenga como requisito el que la longitud mínima sea de 8 caracteres (una contraseña más larga no siempre es mejor)</span><span class="sxs-lookup"><span data-stu-id="ef064-124">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="ef064-125">No solicite requisitos de composición de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ef064-125">Don't require character composition requirements.</span></span> <span data-ttu-id="ef064-126">Por ejemplo, \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="ef064-126">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="ef064-127">No requiera una configuración de contraseña periódica obligatoria para cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="ef064-127">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="ef064-128">Prohíba las contraseñas comunes para evitar el uso de las contraseñas más vulnerables en el sistema. </span><span class="sxs-lookup"><span data-stu-id="ef064-128">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="ef064-129">Instruya a los usuarios para que no vuelvan a usar las contraseñas de la organización para propósitos no relacionados con el trabajo</span><span class="sxs-lookup"><span data-stu-id="ef064-129">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="ef064-130">Exija el registro para la [autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="ef064-130">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="ef064-131">Permitir desafíos de autenticación multifactor basada en riesgos</span><span class="sxs-lookup"><span data-stu-id="ef064-131">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="ef064-132">Guía de contraseñas para los usuarios</span><span class="sxs-lookup"><span data-stu-id="ef064-132">Password guidance for your users</span></span>

<span data-ttu-id="ef064-133">Esta es una guía de contraseñas para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="ef064-133">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="ef064-134">Asegúrese de que los usuarios sepan estas recomendaciones y apliquen las directivas de contraseñas recomendadas en el nivel de organización.</span><span class="sxs-lookup"><span data-stu-id="ef064-134">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="ef064-135">No use una contraseña igual o similar a una que use en otros sitios web</span><span class="sxs-lookup"><span data-stu-id="ef064-135">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="ef064-136">No use solo una palabra, por ejemplo, **contraseña**, ni una frase que use habitualmente, como **ILOVEYOU.**</span><span class="sxs-lookup"><span data-stu-id="ef064-136">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="ef064-137">Haga que las contraseñas sean difíciles de adivinar, incluso las personas que sepan mucho sobre usted, como el nombre y el cumpleaños de sus amigos y familiares, sus bandas favoritas y las frases que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="ef064-137">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="ef064-138">Algunos métodos comunes y sus repercusiones negativas</span><span class="sxs-lookup"><span data-stu-id="ef064-138">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="ef064-139">Éstas son algunas de las prácticas de administración de contraseñas más usadas, pero la búsqueda nos avisa sobre las consecuencias negativas que tienen.</span><span class="sxs-lookup"><span data-stu-id="ef064-139">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="ef064-140">Requisitos de expiración de contraseña para usuarios</span><span class="sxs-lookup"><span data-stu-id="ef064-140">Password expiration requirements for users</span></span>

<span data-ttu-id="ef064-141">Los requisitos de expiración de contraseñas son más dañinos que los que hacen que los usuarios seleccionen contraseñas predecibles, formadas por palabras secuenciales y números estrechamente relacionados entre sí.</span><span class="sxs-lookup"><span data-stu-id="ef064-141">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="ef064-142">En estos casos, la contraseña siguiente puede predecirse en función de la contraseña anterior.</span><span class="sxs-lookup"><span data-stu-id="ef064-142">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="ef064-143">Los requisitos de expiración de contraseñas no proporcionan ventajas de contención ya que los ciberdelincuentes casi siempre usan credenciales tan pronto como los comprometen.</span><span class="sxs-lookup"><span data-stu-id="ef064-143">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span> <span data-ttu-id="ef064-144">Consulte [Momento para reconsiderar los cambios en la contraseña obligatoria](https://go.microsoft.com/fwlink/p/?linkid=861018) para más información.</span><span class="sxs-lookup"><span data-stu-id="ef064-144">Check out [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) for more info.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="ef064-145">Requerir contraseñas largas</span><span class="sxs-lookup"><span data-stu-id="ef064-145">Requiring long passwords</span></span>

<span data-ttu-id="ef064-146">Los requisitos de longitud de contraseña (con un tamaño superior a 10 caracteres) pueden dar lugar a un comportamiento de usuario predecible e indeseable.</span><span class="sxs-lookup"><span data-stu-id="ef064-146">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="ef064-147">Por ejemplo, es posible que los usuarios que tengan que disponer de una contraseña de 16 caracteres elijan patrones de repetición como **fourfourfourfour** o **passwordpassword** que cumplan con los requisitos de longitud de caracteres y no sean difíciles de adivinar.</span><span class="sxs-lookup"><span data-stu-id="ef064-147">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="ef064-148">Además, los requisitos de longitud aumentan las posibilidades de que los usuarios adopten otras prácticas que no sean seguras, como escribir su contraseña, volver a usarlas o almacenarlas sin cifrar en sus documentos.</span><span class="sxs-lookup"><span data-stu-id="ef064-148">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="ef064-149">Para animar a los usuarios a considerar una contraseña única, le recomendamos que mantenga un requisito de longitud mínima de 8 caracteres.</span><span class="sxs-lookup"><span data-stu-id="ef064-149">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span>
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="ef064-150">Requerir el uso de varios juegos de caracteres</span><span class="sxs-lookup"><span data-stu-id="ef064-150">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="ef064-151">Los requisitos de complejidad de las contraseñas reducen el espacio clave y provocan que los usuarios actúen de formas predecibles, que hacen más daño que bien.</span><span class="sxs-lookup"><span data-stu-id="ef064-151">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="ef064-152">La mayoría de los sistemas aplican algunos niveles de complejidad de contraseña.</span><span class="sxs-lookup"><span data-stu-id="ef064-152">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="ef064-153">Por ejemplo, las contraseñas necesitan caracteres de las tres categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="ef064-153">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="ef064-154">Caracteres en mayúsculas </span><span class="sxs-lookup"><span data-stu-id="ef064-154">uppercase characters</span></span>

- <span data-ttu-id="ef064-155">Caracteres en minúsculas</span><span class="sxs-lookup"><span data-stu-id="ef064-155">lowercase characters</span></span>

- <span data-ttu-id="ef064-156">Caracteres no alfanuméricos</span><span class="sxs-lookup"><span data-stu-id="ef064-156">non-alphanumeric characters</span></span>

<span data-ttu-id="ef064-157">La mayoría de los usuarios usa patrones similares, por ejemplo, una letra mayúscula en la primera posición, un símbolo en la última y un número las últimas 2.</span><span class="sxs-lookup"><span data-stu-id="ef064-157">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="ef064-158">Los ciberdelincuentes lo saben, por lo que ejecutan sus ataques de diccionario utilizando las sustituciones más comunes, "$" para "s", "@" para "a", "1" para "l".</span><span class="sxs-lookup"><span data-stu-id="ef064-158">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="ef064-159">Obligar a sus usuarios a elegir una combinación de letras en mayúsculas, minúsculas, dígitos y caracteres especiales tiene un efecto negativo.</span><span class="sxs-lookup"><span data-stu-id="ef064-159">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="ef064-160">Algunos requisitos de complejidad incluso evitan que los usuarios usen contraseñas seguras y fáciles de recordar, y obligan a que se encuentren con contraseñas menos seguras y menos fáciles de recordar.</span><span class="sxs-lookup"><span data-stu-id="ef064-160">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="ef064-161">Patrones correctos</span><span class="sxs-lookup"><span data-stu-id="ef064-161">Successful Patterns</span></span>

<span data-ttu-id="ef064-162">En cambio, estas son algunas recomendaciones para favorecer la diversidad de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ef064-162">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="ef064-163">Prohibir contraseñas comunes</span><span class="sxs-lookup"><span data-stu-id="ef064-163">Ban common passwords</span></span>

<span data-ttu-id="ef064-164">El requisito de contraseña más importante que debe aplicar a los usuarios al crear contraseñas es vetar el uso de contraseñas comunes para reducir la susceptibilidad de la organización a ataques violentos de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ef064-164">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="ef064-165">Las contraseñas de usuario comunes son, por ejemplo, **abcdefg**, **contraseña**, **mono**.</span><span class="sxs-lookup"><span data-stu-id="ef064-165">Common user passwords include, **abcdefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="ef064-166">Instruya a los usuarios para no volver a usar contraseñas de la organización en otro lugar</span><span class="sxs-lookup"><span data-stu-id="ef064-166">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="ef064-167">Uno de los mensajes más importantes para tener acceso a los usuarios de su organización es no volver a usar la contraseña de su organización en ningún otro lugar.</span><span class="sxs-lookup"><span data-stu-id="ef064-167">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="ef064-168">El uso de las contraseñas de organización en sitios web externos aumenta considerablemente la probabilidad de que los ciberdelincuentes puedan comprometer estas contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ef064-168">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="ef064-169">Exigir registro de Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="ef064-169">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="ef064-170">Asegúrese de que los usuarios actualizan la información de contacto y seguridad, como una dirección de correo electrónico alternativa, un número de teléfono o un dispositivo registrado para las notificaciones de inserción, de modo que pueden responder a los desafíos de seguridad y recibir notificaciones de eventos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ef064-170">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="ef064-171">La información actualizada de contacto y seguridad ayuda a los usuarios a verificar su identidad si alguna vez olvidan su contraseña o si alguien más intenta hacerse cargo de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="ef064-171">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="ef064-172">También proporciona un canal de notificación fuera de banda en caso de eventos de seguridad como intentos de inicio de sesión o cambio de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ef064-172">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="ef064-173">Para obtener más información, consulte [configurar la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="ef064-173">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="ef064-174">Habilitar la autenticación multifactor basada en riesgos</span><span class="sxs-lookup"><span data-stu-id="ef064-174">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="ef064-175">La autenticación multifactor basada en riesgos garantiza que, cuando nuestro sistema detecta actividad sospechosa, puede poner a prueba al usuario para asegurarse de que es el propietario legítimo de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="ef064-175">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="ef064-176">¿Desea obtener más información?</span><span class="sxs-lookup"><span data-stu-id="ef064-176">Want to know more?</span></span> <span data-ttu-id="ef064-177">Lectura recomendada</span><span class="sxs-lookup"><span data-stu-id="ef064-177">Recommended reading</span></span>

- [<span data-ttu-id="ef064-178">¿Las contraseñas de web seguras realizan alguna acción?</span><span class="sxs-lookup"><span data-stu-id="ef064-178">Do Strong Web Passwords Accomplish Anything?</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [<span data-ttu-id="ef064-179">Carteras de contraseñas y el usuario de esfuerzo finito</span><span class="sxs-lookup"><span data-stu-id="ef064-179">Password Portfolios and the Finite-Effort User</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [<span data-ttu-id="ef064-180">Prevenir contraseñas vulnerables leyendo las mentes de los usuarios</span><span class="sxs-lookup"><span data-stu-id="ef064-180">Preventing Weak Passwords by Reading Users' Minds</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [<span data-ttu-id="ef064-181">Elegir contraseñas seguras</span><span class="sxs-lookup"><span data-stu-id="ef064-181">Choosing Secure Passwords</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [<span data-ttu-id="ef064-182">Tiempo para reconsiderar los cambios en la contraseña obligatoria</span><span class="sxs-lookup"><span data-stu-id="ef064-182">Time to rethink mandatory password changes</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [<span data-ttu-id="ef064-183">Las peores contraseñas de 2015</span><span class="sxs-lookup"><span data-stu-id="ef064-183">Worst Passwords of 2015</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-content"></a><span data-ttu-id="ef064-184">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="ef064-184">Related content</span></span>

<span data-ttu-id="ef064-185">[Restablecer contraseñas](../add-users/reset-passwords.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ef064-185">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>

<span data-ttu-id="ef064-186">[Establecer la contraseña de un usuario individual para que nunca expire](../add-users/set-password-to-never-expire.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ef064-186">[Set an individual user's password to never expire](../add-users/set-password-to-never-expire.md) (article)</span></span>

<span data-ttu-id="ef064-187">[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ef064-187">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="ef064-188">[Volver a enviar la contraseña de un usuario: ayuda para administradores](../add-users/resend-user-password.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="ef064-188">[Resend a user's password - Admin Help](../add-users/resend-user-password.md) (article)</span></span>