---
title: Bibliotecas de .NET Framework compatibles | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], .NET Framework libraries
- .NET Framework [CLR Integration]
ms.assetid: 417544ff-c25c-496e-add4-2f278f8a4911
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f92e3eadccc869452cf35534f786724c8e259a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662095"
---
# <a name="supported-net-framework-libraries"></a><span data-ttu-id="83ca1-102">Bibliotecas de .NET Framework admitidas</span><span class="sxs-lookup"><span data-stu-id="83ca1-102">Supported .NET Framework Libraries</span></span>
  <span data-ttu-id="83ca1-103">Con Common Language Runtime (CLR) hospedado en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], puede crear procedimientos almacenados, desencadenadores, funciones definidas por el usuario, tipos definidos por el usuario y agregados definidos por el usuario en código administrado.</span><span class="sxs-lookup"><span data-stu-id="83ca1-103">With the common language runtime (CLR) hosted in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="83ca1-104">Con la funcionalidad de las bibliotecas de clases de.NET Framework, tiene acceso a clases pregeneradas que proporcionan funcionalidad para la manipulación de cadenas, operaciones matemáticas avanzadas, acceso a archivos, criptografía, etc.</span><span class="sxs-lookup"><span data-stu-id="83ca1-104">With the functionality found in the .NET Framework class libraries, you have access to pre-built classes that provide functionality for string manipulation, advanced math operations, file access, cryptography, and more.</span></span> <span data-ttu-id="83ca1-105">Se puede tener acceso a estas clases desde cualquier procedimiento almacenado administrado, tipo definido por el usuario, desencadenador, función definida por el usuario o agregado definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="83ca1-105">These classes can be accessed from any managed stored procedure, user-defined type, trigger, user-defined function, or user-defined aggregate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83ca1-106">Si el servicio o actualiza los ensamblados no compatibles en la caché de ensamblados global (GAC), el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="83ca1-106">If you service or upgrade unsupported assemblies in the global assembly cache (GAC), your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="83ca1-107">Si un ensamblado existe en una [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] integración CLR.</span><span class="sxs-lookup"><span data-stu-id="83ca1-107">If an assembly exists both in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span> <span data-ttu-id="83ca1-108">Si mantiene o actualiza cualquier ensamblado en la GAC que también esté registrado en la base de datos, incluidos los ensamblados de .NET Framework no compatibles, asegúrese de que también mantiene o actualiza la copia del ensamblado en las bases de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con la instrucción `ALTER ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="83ca1-108">If you service or upgrade any assemblies in the GAC that are also registered in the database, including unsupported .NET Framework assemblies, make sure to also service or upgrade the copy of the assembly inside your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases with the `ALTER ASSEMBLY` statement.</span></span> <span data-ttu-id="83ca1-109">Para obtener más información, vea el [artículo 949080 de Knowledge Base](https://support.microsoft.com/kb/949080).</span><span class="sxs-lookup"><span data-stu-id="83ca1-109">For more information, see [Knowledge Base article 949080](https://support.microsoft.com/kb/949080).</span></span>  
  
## <a name="supported-libraries"></a><span data-ttu-id="83ca1-110">Bibliotecas compatibles</span><span class="sxs-lookup"><span data-stu-id="83ca1-110">Supported Libraries</span></span>  
 <span data-ttu-id="83ca1-111">A partir de [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] tiene una lista de bibliotecas de .NET Framework compatibles, que se han probado para garantizar que cumplen con los estándares de seguridad y confiabilidad para la interacción con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] las carga directamente desde la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="83ca1-111">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] has a list of supported .NET Framework libraries, which have been tested to ensure that they meet reliability and security standards for interaction with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] loads them directly from the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="83ca1-112">Las bibliotecas/espacios de nombres que admite la integración CLR en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] son:</span><span class="sxs-lookup"><span data-stu-id="83ca1-112">The libraries/namespaces supported by CLR integration in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are:</span></span>  
  
-   <span data-ttu-id="83ca1-113">CustomMarshalers</span><span class="sxs-lookup"><span data-stu-id="83ca1-113">CustomMarshalers</span></span>  
  
-   <span data-ttu-id="83ca1-114">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="83ca1-114">Microsoft.VisualBasic</span></span>  
  
-   <span data-ttu-id="83ca1-115">Microsoft.VisualC</span><span class="sxs-lookup"><span data-stu-id="83ca1-115">Microsoft.VisualC</span></span>  
  
-   <span data-ttu-id="83ca1-116">mscorlib</span><span class="sxs-lookup"><span data-stu-id="83ca1-116">mscorlib</span></span>  
  
-   <span data-ttu-id="83ca1-117">Sistema</span><span class="sxs-lookup"><span data-stu-id="83ca1-117">System</span></span>  
  
-   <span data-ttu-id="83ca1-118">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="83ca1-118">System.Configuration</span></span>  
  
-   <span data-ttu-id="83ca1-119">System.Data</span><span class="sxs-lookup"><span data-stu-id="83ca1-119">System.Data</span></span>  
  
-   <span data-ttu-id="83ca1-120">System.Data.OracleClient</span><span class="sxs-lookup"><span data-stu-id="83ca1-120">System.Data.OracleClient</span></span>  
  
-   <span data-ttu-id="83ca1-121">System.Data.SqlXml</span><span class="sxs-lookup"><span data-stu-id="83ca1-121">System.Data.SqlXml</span></span>  
  
-   <span data-ttu-id="83ca1-122">System.Deployment</span><span class="sxs-lookup"><span data-stu-id="83ca1-122">System.Deployment</span></span>  
  
-   <span data-ttu-id="83ca1-123">System.Security</span><span class="sxs-lookup"><span data-stu-id="83ca1-123">System.Security</span></span>  
  
-   <span data-ttu-id="83ca1-124">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="83ca1-124">System.Transactions</span></span>  
  
-   <span data-ttu-id="83ca1-125">System.Web.Services</span><span class="sxs-lookup"><span data-stu-id="83ca1-125">System.Web.Services</span></span>  
  
-   <span data-ttu-id="83ca1-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="83ca1-126">System.Xml</span></span>  
  
-   <span data-ttu-id="83ca1-127">System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="83ca1-127">System.Core.dll</span></span>  
  
-   <span data-ttu-id="83ca1-128">System.Xml.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="83ca1-128">System.Xml.Linq.dll</span></span>  
  
## <a name="unsupported-libraries"></a><span data-ttu-id="83ca1-129">Bibliotecas no compatibles</span><span class="sxs-lookup"><span data-stu-id="83ca1-129">Unsupported Libraries</span></span>  
 <span data-ttu-id="83ca1-130">También se puede llamar a bibliotecas no compatibles desde los procedimientos almacenados administrados, desencadenadores, funciones definidas por el usuario, tipos definidos por el usuario y agregados definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="83ca1-130">Unsupported libraries can still be called from your managed stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates.</span></span> <span data-ttu-id="83ca1-131">La biblioteca no compatible se debe registrar previamente en la base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], mediante la instrucción `CREATE ASSEMBLY`, antes de utilizarla en el código.</span><span class="sxs-lookup"><span data-stu-id="83ca1-131">The unsupported library must first be registered in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, using the `CREATE ASSEMBLY` statement, before it can be used in your code.</span></span> <span data-ttu-id="83ca1-132">Las bibliotecas no compatibles que se registren y se ejecuten en el servidor se deben revisar y probar para garantizar la seguridad y la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="83ca1-132">Any unsupported library that is registered and run on the server should be reviewed and tested for security and reliability.</span></span>  
  
 <span data-ttu-id="83ca1-133">Por ejemplo, el espacio de nombres `System.DirectoryServices` no se admite.</span><span class="sxs-lookup"><span data-stu-id="83ca1-133">For example, the `System.DirectoryServices` namespace is not supported.</span></span> <span data-ttu-id="83ca1-134">Debe registrar el ensamblado System.DirectoryServices.dll con permisos `UNSAFE` antes de llamarlo desde el código.</span><span class="sxs-lookup"><span data-stu-id="83ca1-134">You must register the System.DirectoryServices.dll assembly with `UNSAFE` permissions before you can call it from your code.</span></span> <span data-ttu-id="83ca1-135">El permiso `UNSAFE` es necesario porque las clases del espacio de nombres `System.DirectoryServices` no cumplen los requisitos de `SAFE` ni `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="83ca1-135">The `UNSAFE` permission is necessary because classes in the `System.DirectoryServices` namespace do not meet the requirements for `SAFE` or `EXTERNAL_ACCESS`.</span></span> <span data-ttu-id="83ca1-136">Para obtener más información, vea restricciones del modelo de programación de la [integración CLR](clr-integration-programming-model-restrictions.md) y [seguridad de acceso del código de integración CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="83ca1-136">For more information, see [CLR Integration Programming Model Restrictions](clr-integration-programming-model-restrictions.md) and [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ca1-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83ca1-137">See Also</span></span>  
 <span data-ttu-id="83ca1-138">[Crear un ensamblado](../assemblies/creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="83ca1-138">[Creating an Assembly](../assemblies/creating-an-assembly.md) </span></span>  
 <span data-ttu-id="83ca1-139">[Seguridad de acceso del código de integración CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="83ca1-139">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 [<span data-ttu-id="83ca1-140">Restricciones del modelo de programación de la integración CLR</span><span class="sxs-lookup"><span data-stu-id="83ca1-140">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
  
  
