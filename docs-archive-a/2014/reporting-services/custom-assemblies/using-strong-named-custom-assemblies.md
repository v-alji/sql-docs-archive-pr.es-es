---
title: Usar ensamblados personalizados con nombre seguro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- AllowPartiallyTrustedCallersAttribute attribute
- strong-named custom assemblies [Reporting Services]
- strong names [Reporting Services]
- assemblies [Reporting Services], strong names
- custom assemblies [Reporting Services], strong-named
ms.assetid: ca9f19d7-6e86-46f2-b9ad-9bf807eaa52e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e685ecda39e0487eb4b469920820fa6e4a10daa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662676"
---
# <a name="using-strong-named-custom-assemblies"></a><span data-ttu-id="719b6-102">Usar ensamblados personalizados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="719b6-102">Using Strong-Named Custom Assemblies</span></span>
  <span data-ttu-id="719b6-103">Un nombre seguro identifica un ensamblado e incluye un nombre para el mismo, un número de versión de cuatro partes, información de la referencia cultural (si se proporciona), una clave pública y una firma digital almacenadas en el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="719b6-103">A strong name identifies an assembly and includes the assembly's text name, four-part version number, culture information (if provided), a public key, and a digital signature stored in the assembly's manifest.</span></span> <span data-ttu-id="719b6-104">Un nombre seguro identifica de forma única un ensamblado para Common Language Runtime (CLR) y se asegura de la integridad binaria.</span><span class="sxs-lookup"><span data-stu-id="719b6-104">A strong name uniquely identifies an assembly to the common language runtime (CLR) and ensures binary integrity.</span></span>  
  
## <a name="using-allowpartiallytrustedcallersattribute"></a><span data-ttu-id="719b6-105">Usar AllowPartiallyTrustedCallersAttribute</span><span class="sxs-lookup"><span data-stu-id="719b6-105">Using AllowPartiallyTrustedCallersAttribute</span></span>  
 <span data-ttu-id="719b6-106">Para usar ensamblados con nombre seguro con los informes, debe permitir que el código de confianza parcial llame al ensamblado con nombre seguro con el atributo **AllowPartiallyTrustedCallers** del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="719b6-106">To use strong-named assemblies with reports, you must allow your strong-named assembly to be called by partially trusted code using the assembly's **AllowPartiallyTrustedCallers** attribute.</span></span> <span data-ttu-id="719b6-107">Puede usar **AllowPartiallyTrustedCallersAttribute** para permitir que el Diseñador de informes o el servidor de informes llamen a los ensamblados con nombre seguro en las expresiones de informe.</span><span class="sxs-lookup"><span data-stu-id="719b6-107">You can use **AllowPartiallyTrustedCallersAttribute** to allow strong-named assemblies to be called by Report Designer or the report server in report expressions.</span></span> <span data-ttu-id="719b6-108">Para permitir que el código con confianza parcial llame a los ensamblados con nombre seguro, agregue el siguiente atributo de nivel de ensamblado al archivo de atributos de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="719b6-108">To allow partially trusted code to call strong-named assemblies, add the following assembly-level attribute to your assembly attribute file.</span></span>  
  
```vb  
<assembly:AllowPartiallyTrustedCallers>  
```  
  
```csharp  
[assembly:AllowPartiallyTrustedCallers]  
```  
  
 <span data-ttu-id="719b6-109">**AllowPartiallyTrustedCallersAttribute** solo es eficaz cuando lo aplica un ensamblado con nombre seguro en el nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="719b6-109">**AllowPartiallyTrustedCallersAttribute** is effective only when applied by a strong-named assembly at the assembly level.</span></span> <span data-ttu-id="719b6-110">Para obtener más información sobre cómo aplicar atributos en el nivel de ensamblado, vea "aplicar atributos" en la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentación del SDK.</span><span class="sxs-lookup"><span data-stu-id="719b6-110">For more information about applying attributes at the assembly level, see "Applying Attributes" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="719b6-111">Cuando **AllowPartiallyTrustedCallersAttribute** está presente, se evitan las comprobaciones de seguridad **FullTrustLinkDemand** predeterminadas, con lo que el ensamblado se puede llamar desde cualquier otro ensamblado con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="719b6-111">When **AllowPartiallyTrustedCallersAttribute** is present, the default **FullTrustLinkDemand** security checks are prevented, making the assembly callable from any other partially trusted assembly.</span></span> <span data-ttu-id="719b6-112">Todas las comprobaciones de seguridad, incluidos los atributos de seguridad declarativos de nivel de clase o de método, se deben indicar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="719b6-112">All security checks, including class-level or method-level declarative security attributes, must be explicitly stated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="719b6-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="719b6-113">See Also</span></span>  
 [<span data-ttu-id="719b6-114">Usar ensamblados personalizados con informes</span><span class="sxs-lookup"><span data-stu-id="719b6-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
