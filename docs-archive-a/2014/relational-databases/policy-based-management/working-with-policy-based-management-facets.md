---
title: Trabajar con facetas de administración basadas en directivas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- viewing Policy-Based Management facets
- facets [Policy-Based Management], copying
- facets [Policy-Based Management], viewing
- copying Policy-Based Management facets
ms.assetid: 88d025c4-07c2-4e4d-8634-204249a8c82c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5a356550796cc682b2292defffd6565b7fea0783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670969"
---
# <a name="working-with-policy-based-management-facets"></a><span data-ttu-id="54bf3-102">Trabajar con facetas de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="54bf3-102">Working with Policy-Based Management Facets</span></span>
  <span data-ttu-id="54bf3-103">Una faceta de administración basada en directivas es un conjunto de propiedades lógicas que se relacionan con una área de interés de administración.</span><span class="sxs-lookup"><span data-stu-id="54bf3-103">A Policy-Based Management facet is a set of logical properties that are related to an area of management interest.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="54bf3-104">incluye varias facetas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="54bf3-104">includes several predefined facets.</span></span> <span data-ttu-id="54bf3-105">Por ejemplo, la faceta Configuración de área expuesta define, como propiedades, las características que están desactivadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="54bf3-105">For example, the Surface Area Configuration facet defines, as properties, the features that are off by default.</span></span>  
  
 <span data-ttu-id="54bf3-106">Al administrar varios entornos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] similares, puede configurar una faceta en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copiar el estado de la faceta en un archivo y, a continuación, importar ese archivo en otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como una directiva.</span><span class="sxs-lookup"><span data-stu-id="54bf3-106">When you manage many similar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environments, you can configure a facet in one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copy the state of the facet to a file, and then import that file into another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a policy.</span></span> <span data-ttu-id="54bf3-107">Cuando el estado se ha convertido en una directiva, la directiva se puede aplicar a otras instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], objetos de instancia, bases de datos u objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="54bf3-107">When the state has been converted to a policy, the policy can be applied to other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance objects, databases, or database objects.</span></span>  
  
 <span data-ttu-id="54bf3-108">En este tema se describe cómo copiar el estado de una faceta en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="54bf3-108">This topic describes how to copy the state of a facet to an XML file.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="54bf3-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="54bf3-109">Permissions</span></span>  
 <span data-ttu-id="54bf3-110">Los procedimientos descritos en este tema requieren la pertenencia al rol PolicyAdministratorRole de la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="54bf3-110">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
## <a name="viewing-and-copying-facet-states"></a><span data-ttu-id="54bf3-111">Ver y copiar los estados de la faceta</span><span class="sxs-lookup"><span data-stu-id="54bf3-111">Viewing and Copying Facet States</span></span>  
 [<span data-ttu-id="54bf3-112">Ver las facetas de administración basada en directivas en un objeto de SQL Server</span><span class="sxs-lookup"><span data-stu-id="54bf3-112">View the Policy-Based Management Facets on a SQL Server Object</span></span>](view-the-policy-based-management-facets-on-a-sql-server-object.md)  
  
 [<span data-ttu-id="54bf3-113">Copiar en un archivo XML un estado de faceta de administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="54bf3-113">Copy a Policy-Based Management Facet State to an XML File</span></span>](copy-a-policy-based-management-facet-state-to-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="54bf3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54bf3-114">See Also</span></span>  
 [<span data-ttu-id="54bf3-115">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="54bf3-115">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
