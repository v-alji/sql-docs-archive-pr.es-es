---
title: Cambio del separador de palabras usado para el inglés de Estados Unidos y el del Reino Unido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 6b5d2177-db98-47f5-b32e-4b80a2f74ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3b759b90ec834dcb666f7862bfba3857f2fea0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673614"
---
# <a name="change-the-word-breaker-used-for-us-english-and-uk-english"></a><span data-ttu-id="e6b54-102">Cambiar el separador de palabras usado para el inglés de Estados Unidos y el del Reino Unido</span><span class="sxs-lookup"><span data-stu-id="e6b54-102">Change the Word Breaker Used for US English and UK English</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="e6b54-103">instala una nueva versión (versión 14.0.4999.1038) del separador de palabras y del lematizador para el idioma inglés, reemplazando la versión anterior de estos componentes (versión 12.0.6828.0).</span><span class="sxs-lookup"><span data-stu-id="e6b54-103">installs a new version (version 14.0.4999.1038) of the word breaker and stemmer for the English language, replacing the previous version of these components (version 12.0.6828.0).</span></span> <span data-ttu-id="e6b54-104">Para obtener más información sobre el comportamiento modificado de los nuevos componentes, vea [Cambios de comportamiento en la búsqueda de texto completo](full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="e6b54-104">For information about the changed behavior of the new components, see [Behavior Changes to Full-Text Search](full-text-search.md).</span></span> <span data-ttu-id="e6b54-105">En este tema se describe cómo pasar de la nueva versión de estos componentes a la versión previa o viceversa.</span><span class="sxs-lookup"><span data-stu-id="e6b54-105">This topic describes how to switch from the new version of these components to the previous version, or to switch back from the previous version to the new version.</span></span> <span data-ttu-id="e6b54-106">Para las instalaciones de clúster, estos cambios deben realizarse en todos los nodos principales y pasivos.</span><span class="sxs-lookup"><span data-stu-id="e6b54-106">For cluster installations, these changes should be made on all the primary and passive nodes.</span></span>  
  
 <span data-ttu-id="e6b54-107">Las versiones previas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizaban separadores de palabras distintos representados por CLSID diferentes para el inglés de Estados Unidos (LCID 1033) y el inglés del Reino Unido (LCID 2057).</span><span class="sxs-lookup"><span data-stu-id="e6b54-107">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] used different word breakers represented by different CLSIDs for US English (LCID 1033) and UK English (LCID 2057).</span></span> <span data-ttu-id="e6b54-108">En esta versión, ambos LCID usan los mismos componentes con los mismos CLSID, como se muestra en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="e6b54-108">In this release, both LCIDs use the same components with the same CLSIDs, as shown in the following table:</span></span>  
  
|<span data-ttu-id="e6b54-109">LCID</span><span class="sxs-lookup"><span data-stu-id="e6b54-109">LCID</span></span>|<span data-ttu-id="e6b54-110">Separador de palabras instalado por versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="e6b54-110">Word breaker installed by previous versions</span></span><br /><br /> <span data-ttu-id="e6b54-111">versión 12.0.6828.0</span><span class="sxs-lookup"><span data-stu-id="e6b54-111">version 12.0.6828.0</span></span>|<span data-ttu-id="e6b54-112">Lematizador instalado por versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="e6b54-112">Stemmer installed by previous versions</span></span>|<span data-ttu-id="e6b54-113">Separador de palabras instalado por esta versión</span><span class="sxs-lookup"><span data-stu-id="e6b54-113">Word breaker installed by this version</span></span><br /><br /> <span data-ttu-id="e6b54-114">versión 14.0.4999.1038</span><span class="sxs-lookup"><span data-stu-id="e6b54-114">version 14.0.4999.1038</span></span>|<span data-ttu-id="e6b54-115">Lematizador instalado por esta versión</span><span class="sxs-lookup"><span data-stu-id="e6b54-115">Stemmer installed by this version</span></span>|  
|----------|-------------------------------------------------------------------------|--------------------------------------------|-----------------------------------------------------------------------|---------------------------------------|  
|<span data-ttu-id="e6b54-116">3082</span><span class="sxs-lookup"><span data-stu-id="e6b54-116">1033</span></span><br /><span data-ttu-id="e6b54-117">(inglés de Estados Unidos)</span><span class="sxs-lookup"><span data-stu-id="e6b54-117">(US English)</span></span>|<span data-ttu-id="e6b54-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span><span class="sxs-lookup"><span data-stu-id="e6b54-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span></span>|<span data-ttu-id="e6b54-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="e6b54-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="e6b54-120">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="e6b54-120">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="e6b54-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="e6b54-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
|<span data-ttu-id="e6b54-122">2057</span><span class="sxs-lookup"><span data-stu-id="e6b54-122">2057</span></span><br /><span data-ttu-id="e6b54-123">(inglés del Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="e6b54-123">(UK English)</span></span>|<span data-ttu-id="e6b54-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span><span class="sxs-lookup"><span data-stu-id="e6b54-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span></span>|<span data-ttu-id="e6b54-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="e6b54-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="e6b54-126">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="e6b54-126">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="e6b54-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="e6b54-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
  
 <span data-ttu-id="e6b54-128">Los componentes descritos en este tema son archivos DLL instalados en la carpeta `MSSQL\Binn` para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6b54-128">The components described in this topic are DLL files that are installed in the `MSSQL\Binn` folder for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="e6b54-129">La ruta de acceso completa es normalmente `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span><span class="sxs-lookup"><span data-stu-id="e6b54-129">The full path is typically `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span></span>  
  
 <span data-ttu-id="e6b54-130">Para obtener más información sobre los separadores de palabras y los lematizadores, vea [Configurar y administrar separadores de palabras y lematizadores para la búsqueda](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="e6b54-130">For more information about word breakers and stemmers, see [Configure and Manage Word Breakers and Stemmers for Search](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="switching-from-the-current-english-word-breaker-to-the-previous-english-word-breakers"></a><span data-ttu-id="e6b54-131">Pasar del separador de palabras de inglés actual a los separadores de palabras anteriores de inglés</span><span class="sxs-lookup"><span data-stu-id="e6b54-131">Switching from the current English word breaker to the previous English word breakers</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-us-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="e6b54-132">Para pasar de la versión actual del separador de palabras de inglés de Estados Unidos a la versión anterior</span><span class="sxs-lookup"><span data-stu-id="e6b54-132">To switch from the current version of the US English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="e6b54-133">En el Registro, navegue al siguiente nodo: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<raízDeInstancia\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-133">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="e6b54-134">Siga estos pasos para agregar nuevas claves a los COM ClassID de las interfaces en inglés de Estados Unidos de separadores de palabras y lematizadores del LCID 1033:</span><span class="sxs-lookup"><span data-stu-id="e6b54-134">Use the following steps to add new keyS for the COM ClassIDs for the previous US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="e6b54-135">Agregue una nueva clave con el valor **{188D6CC5-CB03-4C01-912E-47D21295D77E}** para el separador de palabras anterior.</span><span class="sxs-lookup"><span data-stu-id="e6b54-135">Add a new key with the value **{188D6CC5-CB03-4C01-912E-47D21295D77E}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="e6b54-136">Actualice los datos (predeterminados) de ese valor de clave a **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-136">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="e6b54-137">Agregue una nueva clave con el valor **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** para el lematizador anterior.</span><span class="sxs-lookup"><span data-stu-id="e6b54-137">Add a new key with the value **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="e6b54-138">Actualice los datos (predeterminados) de ese valor de clave a **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-138">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="e6b54-139">En el Registro, vaya al siguiente nodo: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\enu**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-139">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\enu**.</span></span>  
  
4.  <span data-ttu-id="e6b54-140">Actualice el valor de clave **WBreakerClass** a **{188D6CC5-CB03-4C01-912E-47D21295D77E}** .</span><span class="sxs-lookup"><span data-stu-id="e6b54-140">Update the **WBreakerClass** key value to **{188D6CC5-CB03-4C01-912E-47D21295D77E}**.</span></span>  
  
5.  <span data-ttu-id="e6b54-141">Actualice el valor de clave **StemmerClass** a **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="e6b54-141">Update the **StemmerClass** key value to **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="e6b54-142">Reinicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b54-142">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-uk-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="e6b54-143">Para pasar de la versión actual del separador de palabras de inglés del Reino Unido a la versión anterior</span><span class="sxs-lookup"><span data-stu-id="e6b54-143">To switch from the current version of the UK English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="e6b54-144">En el Registro, navegue al siguiente nodo: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<raízDeInstancia\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-144">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="e6b54-145">Siga estos pasos para agregar una nueva clave para los ClassID COM de las interfaces inglesas del Reino Unido de separadores de palabras y lematizadores del LCID 2057:</span><span class="sxs-lookup"><span data-stu-id="e6b54-145">Use the following steps to add a new key for the COM ClassIDs for the previous UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="e6b54-146">Agregue una nueva clave con el valor **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** para el separador de palabras anterior.</span><span class="sxs-lookup"><span data-stu-id="e6b54-146">Add a new key with the value **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="e6b54-147">Actualice los datos (predeterminados) de ese valor de clave a **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-147">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="e6b54-148">Agregue una nueva clave con el valor **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** para el lematizador anterior.</span><span class="sxs-lookup"><span data-stu-id="e6b54-148">Add a new key with the value **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="e6b54-149">Actualice los datos (predeterminados) de ese valor de clave a **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-149">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="e6b54-150">En el Registro, vaya al siguiente nodo: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-150">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="e6b54-151">Actualice el valor de clave **WBreakerClass** a **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** .</span><span class="sxs-lookup"><span data-stu-id="e6b54-151">Update the **WBreakerClass** key value to **{173C97E2-AEBE-437C-9445-01B237ABF2F6}**.</span></span>  
  
5.  <span data-ttu-id="e6b54-152">Actualice el valor de clave **StemmerClass** a **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="e6b54-152">Update the **StemmerClass** key value to **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="e6b54-153">Reinicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b54-153">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="switching-back-from-the-previous-english-word-breakers-to-the-current-english-word-breaker"></a><span data-ttu-id="e6b54-154">Pasar de los separadores de palabras de inglés anteriores al separador de palabras de inglés actual</span><span class="sxs-lookup"><span data-stu-id="e6b54-154">Switching back from the previous English word breakers to the current English word breaker</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-us-english-word-breaker-to-the-current-version"></a><span data-ttu-id="e6b54-155">Para volver a la versión anterior del separador de palabras de inglés de Estados Unidos a la versión actual</span><span class="sxs-lookup"><span data-stu-id="e6b54-155">To switch back from the previous version of the US English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="e6b54-156">En el Registro, navegue al siguiente nodo: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<raízDeInstancia\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-156">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="e6b54-157">Si las siguientes claves no existen, siga los siguientes pasos para agregar una nueva clave para los ClassID COM de las interfaces inglesas de Estados Unidos de separadores de palabras y lematizadores actuales del LCID 1033:</span><span class="sxs-lookup"><span data-stu-id="e6b54-157">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="e6b54-158">Agregue una nueva clave con el valor **{9faed859-0b30-4434-ae65-412e14a16fb8}** para el separador de palabras actual.</span><span class="sxs-lookup"><span data-stu-id="e6b54-158">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="e6b54-159">Actualice los datos (predeterminados) de ese valor de clave a **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-159">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="e6b54-160">Agregue una nueva clave con el valor **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** para el lematizador actual.</span><span class="sxs-lookup"><span data-stu-id="e6b54-160">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="e6b54-161">Actualice los datos (predeterminados) de ese valor de clave a **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-161">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="e6b54-162">En el Registro, vaya al siguiente nodo: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-162">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="e6b54-163">Actualice el valor de clave **WBreakerClass** a **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="e6b54-163">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="e6b54-164">Actualice el valor de clave **StemmerClass** a **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="e6b54-164">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="e6b54-165">Reinicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b54-165">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-uk-english-word-breaker-to-the-current-version"></a><span data-ttu-id="e6b54-166">Para volver a la versión anterior del separador de palabras de inglés del Reino Unido a la versión actual</span><span class="sxs-lookup"><span data-stu-id="e6b54-166">To switch back from the previous version of the UK English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="e6b54-167">En el Registro, navegue al siguiente nodo: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<raízDeInstancia\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-167">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="e6b54-168">Si las siguientes claves no existen, siga estos pasos para agregar una nueva clave para los ClassID COM de las interfaces inglesas del Reino Unido de separadores de palabras y lematizadores actuales del LCID 2057:</span><span class="sxs-lookup"><span data-stu-id="e6b54-168">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="e6b54-169">Agregue una nueva clave con el valor **{9faed859-0b30-4434-ae65-412e14a16fb8}** para el separador de palabras actual.</span><span class="sxs-lookup"><span data-stu-id="e6b54-169">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="e6b54-170">Actualice los datos (predeterminados) de ese valor de clave a **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-170">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="e6b54-171">Agregue una nueva clave con el valor **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** para el lematizador actual.</span><span class="sxs-lookup"><span data-stu-id="e6b54-171">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="e6b54-172">Actualice los datos (predeterminados) de ese valor de clave a **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-172">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="e6b54-173">En el Registro, vaya al siguiente nodo: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="e6b54-173">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="e6b54-174">Actualice el valor de clave **WBreakerClass** a **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="e6b54-174">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="e6b54-175">Actualice el valor de clave **StemmerClass** a **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="e6b54-175">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="e6b54-176">Reinicie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6b54-176">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b54-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6b54-177">See Also</span></span>  
 <span data-ttu-id="e6b54-178">[Revertir los separadores de palabras usados por las búsquedas a la versión anterior](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span><span class="sxs-lookup"><span data-stu-id="e6b54-178">[Revert the Word Breakers Used by Search to the Previous Version](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span></span>  
 [<span data-ttu-id="e6b54-179">Cambios de comportamiento en la búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="e6b54-179">Behavior Changes to Full-Text Search</span></span>](full-text-search.md)  
  
  
