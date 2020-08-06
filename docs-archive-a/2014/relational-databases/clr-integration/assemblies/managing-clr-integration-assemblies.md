---
title: Administrar ensamblados de integración CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- database objects [CLR integration], assemblies
- common language runtime [SQL Server], assemblies
- assemblies [CLR integration], managing
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
author: rothja
ms.author: jroth
ms.openlocfilehash: 191ccd73ca42ef4c26291e6de88f5f2b0cf565ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747620"
---
# <a name="managing-clr-integration-assemblies"></a><span data-ttu-id="a5766-102">Administrar ensamblados de integración CLR</span><span class="sxs-lookup"><span data-stu-id="a5766-102">Managing CLR Integration Assemblies</span></span>
  <span data-ttu-id="a5766-103">El código administrado se compila y, a continuación, se implementa en unidades denominadas ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5766-103">Managed code is compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="a5766-104">Un ensamblado se empaqueta como un archivo DLL o ejecutable (.exe).</span><span class="sxs-lookup"><span data-stu-id="a5766-104">An assembly is packaged as a DLL or executable (.exe) file.</span></span> <span data-ttu-id="a5766-105">Aunque un archivo ejecutable se puede ejecutar solo, una DLL se debe hospedar en una aplicación existente.</span><span class="sxs-lookup"><span data-stu-id="a5766-105">While an executable file can run on its own, a DLL must be hosted in an existing application.</span></span> <span data-ttu-id="a5766-106">Los ensamblados DLL administrados pueden cargarse y hospedarse en [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5766-106">Managed DLL assemblies can be loaded into and hosted by [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="a5766-107">base de datos que usa la instrucción CREATE ASSEMBLy, antes de que se pueda cargar en el proceso y utilizar.</span><span class="sxs-lookup"><span data-stu-id="a5766-107">database using the CREATE ASSEMBLY statement, before it can be loaded in the process and used.</span></span> <span data-ttu-id="a5766-108">Los ensamblados también pueden actualizarse a partir de una versión más reciente mediante la instrucción ALTER ASSEMBLY o quitarse de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la instrucción DROP ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="a5766-108">Assemblies can also be updated from a more recent version using the ALTER ASSEMBLY statement, or removed from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the DROP ASSEMBLY statement.</span></span>  
  
 <span data-ttu-id="a5766-109">La información del ensamblado se almacena en la tabla `sys.assembly_files` de la base de datos en la que se ha instalado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5766-109">Assembly information is stored in the `sys.assembly_files` table in the database where the assembly has been installed.</span></span> <span data-ttu-id="a5766-110">La tabla `sys.assembly_files` contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a5766-110">The `sys.assembly_files` table contains the following columns.</span></span>  
  
|<span data-ttu-id="a5766-111">Columna</span><span class="sxs-lookup"><span data-stu-id="a5766-111">Column</span></span>|<span data-ttu-id="a5766-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5766-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a5766-113">assembly_id</span><span class="sxs-lookup"><span data-stu-id="a5766-113">assembly_id</span></span>|<span data-ttu-id="a5766-114">Identificador definido para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5766-114">The identifier defined for the assembly.</span></span> <span data-ttu-id="a5766-115">Este número se asigna a todos los objetos relacionados con el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5766-115">This number is assigned to all objects relating to the same assembly.</span></span>|  
|<span data-ttu-id="a5766-116">name</span><span class="sxs-lookup"><span data-stu-id="a5766-116">name</span></span>|<span data-ttu-id="a5766-117">El nombre del objeto.</span><span class="sxs-lookup"><span data-stu-id="a5766-117">The name of the object.</span></span>|  
|<span data-ttu-id="a5766-118">file_id</span><span class="sxs-lookup"><span data-stu-id="a5766-118">file_id</span></span>|<span data-ttu-id="a5766-119">Un número que identifica cada objeto, siendo 1 el valor del primer objeto asociado a un `assembly_id` determinado.</span><span class="sxs-lookup"><span data-stu-id="a5766-119">A number identifying each object, with the first object associated with a given `assembly_id` being given the value of 1.</span></span> <span data-ttu-id="a5766-120">Si varios objetos están asociados al mismo `assembly_id`, 1 incrementa a continuación cada valor `file_id` subsiguiente.</span><span class="sxs-lookup"><span data-stu-id="a5766-120">If multiple objects are associated with the same `assembly_id`, then each subsequent `file_id` value is incremented by 1.</span></span>|  
|<span data-ttu-id="a5766-121">contenido</span><span class="sxs-lookup"><span data-stu-id="a5766-121">content</span></span>|<span data-ttu-id="a5766-122">Representación hexadecimal del ensamblado o archivo.</span><span class="sxs-lookup"><span data-stu-id="a5766-122">The hexadecimal representation of the assembly or file.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="a5766-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a5766-123">In This Section</span></span>  
 [<span data-ttu-id="a5766-124">Crear un ensamblado</span><span class="sxs-lookup"><span data-stu-id="a5766-124">Creating an Assembly</span></span>](creating-an-assembly.md)  
 <span data-ttu-id="a5766-125">Describe la creación de los ensamblados SAFE, EXTERNAL_ACCESS y UNSAFE CLR en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5766-125">Discusses creating SAFE, EXTERNAL_ACCESS, and UNSAFE CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a5766-126">Modificar un ensamblado</span><span class="sxs-lookup"><span data-stu-id="a5766-126">Altering an Assembly</span></span>](altering-an-assembly.md)  
 <span data-ttu-id="a5766-127">Describe la actualización de los ensamblados CLR en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5766-127">Describes updating CLR assemblies in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a5766-128">Quitar un ensamblado</span><span class="sxs-lookup"><span data-stu-id="a5766-128">Dropping an Assembly</span></span>](dropping-an-assembly.md)  
 <span data-ttu-id="a5766-129">Describe cómo quitar los ensamblados CLR de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5766-129">Discusses dropping CLR assemblies from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5766-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5766-130">See Also</span></span>  
 <span data-ttu-id="a5766-131">[Seguridad de la integración CLR](../security/clr-integration-security.md) </span><span class="sxs-lookup"><span data-stu-id="a5766-131">[CLR Integration Security](../security/clr-integration-security.md) </span></span>  
 [<span data-ttu-id="a5766-132">Seguridad de acceso del código de integración CLR</span><span class="sxs-lookup"><span data-stu-id="a5766-132">CLR Integration Code Access Security</span></span>](../security/clr-integration-code-access-security.md)  
  
  
