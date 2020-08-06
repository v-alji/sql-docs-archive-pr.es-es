---
title: Tipos definidos por el usuario CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- validation [CLR integration]
- types [CLR integration]
- UserDefined serialization format [CLR integration]
- null values [CLR integration]
- serialization
- Native serialization format [CLR integration]
- databases [CLR integration]
- building database objects [CLR integration], user-defined types
- user-defined types [CLR integration]
- common language runtime [SQL Server], user-defined types
- UDTs [CLR integration]
- database objects [CLR integration], user-defined types
- turning on CLR functionality
- customizing UDT expression return types [CLR integration]
- UDTs [CLR integration], about UDTs
- comparing UDT values
- annotations [CLR integration]
- user-defined types [CLR integration], about UDTs
- variables [CLR integration]
- invoking UDT methods
- indexes [CLR integration]
ms.assetid: 27c4889b-c543-47a8-a630-ad06804f92df
author: rothja
ms.author: jroth
ms.openlocfilehash: e4e19323eeac9e0a1148924543f71aa7de5619b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677701"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="ac10b-102">Tipos CLR definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="ac10b-102">CLR User-Defined Types</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ac10b-103">ofrece la posibilidad de crear objetos de base de datos programados en un ensamblado creado en Common Language Runtime (CLR) de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac10b-103">gives you the ability to create database objects that are programmed against an assembly created in the.NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="ac10b-104">Los objetos de base de datos que pueden aprovechar el complejo modelo de programación que proporciona CLR incluyen desencadenadores, procedimientos almacenados, funciones, funciones de agregado y tipos.</span><span class="sxs-lookup"><span data-stu-id="ac10b-104">Database objects that can take advantage of the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac10b-105">La capacidad para ejecutar el código CLR se encuentra desactivada (OFF) de manera predeterminada en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac10b-105">The ability to execute CLR code is set to OFF by default in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ac10b-106">El CLR se puede habilitar mediante el **sp_configure** procedimiento almacenado del sistema.</span><span class="sxs-lookup"><span data-stu-id="ac10b-106">The CLR can be enabled by using the **sp_configure** system stored procedure.</span></span>  
  
 <span data-ttu-id="ac10b-107">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , puede utilizar tipos definidos por el usuario (UDT) para extender el sistema de tipos escalares del servidor, lo que permite el almacenamiento de objetos CLR en una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac10b-107">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can use user-defined types (UDTs) to extend the scalar type system of the server, enabling storage of CLR objects in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="ac10b-108">Los UDT pueden contener varios elementos y presentar varios comportamientos, diferenciándose de los tipos de datos de alias adicionales que constan de un tipo de datos del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] único.</span><span class="sxs-lookup"><span data-stu-id="ac10b-108">UDTs can contain multiple elements and can have behaviors, differentiating them from the traditional alias data types which consist of a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system data type.</span></span>  
  
 <span data-ttu-id="ac10b-109">Dado que el sistema tiene acceso a los UDT como un conjunto, su uso para los tipos de datos complejos puede causar un impacto negativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ac10b-109">Because UDTs are accessed by the system as a whole, their use for complex data types may negatively impact performance.</span></span> <span data-ttu-id="ac10b-110">Normalmente, los datos complejos se modelan mejor mediante filas tradicionales y tablas.</span><span class="sxs-lookup"><span data-stu-id="ac10b-110">Complex data is generally best modeled using traditional rows and tables.</span></span> <span data-ttu-id="ac10b-111">Los UDT en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se adaptan perfectamente a:</span><span class="sxs-lookup"><span data-stu-id="ac10b-111">UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are well suited to the following:</span></span>  
  
-   <span data-ttu-id="ac10b-112">Fecha, tiempo, moneda y tipos numéricos extendidos</span><span class="sxs-lookup"><span data-stu-id="ac10b-112">Date, time, currency, and extended numeric types</span></span>  
  
-   <span data-ttu-id="ac10b-113">Aplicaciones geoespaciales</span><span class="sxs-lookup"><span data-stu-id="ac10b-113">Geospatial applications</span></span>  
  
-   <span data-ttu-id="ac10b-114">Datos codificados o cifrados</span><span class="sxs-lookup"><span data-stu-id="ac10b-114">Encoded or encrypted data</span></span>  
  
 <span data-ttu-id="ac10b-115">El proceso para desarrollar los UDT en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consta de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac10b-115">The process of developing UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="ac10b-116">**Codificar y generar el ensamblado que define los UDT.**</span><span class="sxs-lookup"><span data-stu-id="ac10b-116">**Code and build the assembly that defines the UDT.**</span></span> <span data-ttu-id="ac10b-117">Los UDT se definen mediante cualquiera de los lenguajes admitidos en Common Language Runtime (CLR) de .NET Framework que generan código comprobable.</span><span class="sxs-lookup"><span data-stu-id="ac10b-117">UDTs are defined using any of the languages supported by the.NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="ac10b-118">Esto incluye Visual C# y Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="ac10b-118">This includes Visual C# and Visual Basic .NET.</span></span> <span data-ttu-id="ac10b-119">Los datos se exponen como los campos y propiedades de una clase o estructura de .NET Framework, y los métodos de la clase o estructura definen los comportamientos.</span><span class="sxs-lookup"><span data-stu-id="ac10b-119">The data is exposed as fields and properties of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span>  
  
2.  <span data-ttu-id="ac10b-120">**Registrar el ensamblado.**</span><span class="sxs-lookup"><span data-stu-id="ac10b-120">**Register the assembly.**</span></span> <span data-ttu-id="ac10b-121">Los UDT pueden implementarse a través de la interfaz de usuario de Visual Studio en un proyecto de base de datos o mediante la instrucción CREATE ASSEMBLY de [!INCLUDE[tsql](../../includes/tsql-md.md)], que copia el ensamblado que contiene la clase o estructura en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac10b-121">UDTs can be deployed through the Visual Studio user interface in a database project, or by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY statement, which copies the assembly containing the class or structure into a database.</span></span>  
  
3.  <span data-ttu-id="ac10b-122">**Crear un UDT en SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="ac10b-122">**Create the UDT in SQL Server.**</span></span> <span data-ttu-id="ac10b-123">Una vez que un ensamblado se carga en una base de datos host, use la instrucción CREATE TYPE de [!INCLUDE[tsql](../../includes/tsql-md.md)] para crear un UDT y exponer los miembros de la clase o estructura como miembros del UDT.</span><span class="sxs-lookup"><span data-stu-id="ac10b-123">Once an assembly is loaded into a host database, you use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE statement to create a UDT and expose the members of the class or structure as members of the UDT.</span></span> <span data-ttu-id="ac10b-124">Los UDT únicamente existen en el contexto de una base de datos única y, una vez registrados, no dependen de ninguno de los archivos externos a partir de los que se crearon.</span><span class="sxs-lookup"><span data-stu-id="ac10b-124">UDTs exist only in the context of a single database, and, once registered, have no dependencies on the external files from which they were created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ac10b-125">Antes de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], no se admitían los UDT creados a partir de los ensamblados de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac10b-125">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], UDTs created from .NET Framework assemblies were not supported.</span></span> <span data-ttu-id="ac10b-126">Sin embargo, todavía puede usar los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos de alias mediante **sp_addtype**.</span><span class="sxs-lookup"><span data-stu-id="ac10b-126">However, you can still use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alias data types by using **sp_addtype**.</span></span> <span data-ttu-id="ac10b-127">La sintaxis CREATE TYPE se puede usar para crear los tipos de datos definidos por el usuario nativos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y los UDT.</span><span class="sxs-lookup"><span data-stu-id="ac10b-127">The CREATE TYPE syntax can be used for creating both native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined data types and UDTs.</span></span>  
  
4.  <span data-ttu-id="ac10b-128">**Crear tablas, variables o parámetros con el UDT** A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , un tipo definido por el usuario se puede utilizar como la definición de columna de una tabla, como una variable de un [!INCLUDE[tsql](../../includes/tsql-md.md)] lote o como un argumento de una [!INCLUDE[tsql](../../includes/tsql-md.md)] función o un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="ac10b-128">**Create tables, variables, or parameters using the UDT** Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user-defined type can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac10b-129">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ac10b-129">In This Section</span></span>  
 [<span data-ttu-id="ac10b-130">Crear un tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="ac10b-130">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
 <span data-ttu-id="ac10b-131">Describe cómo crear los UDT.</span><span class="sxs-lookup"><span data-stu-id="ac10b-131">Describes how to create UDTs.</span></span>  
  
 [<span data-ttu-id="ac10b-132">Registrar tipos definidos por el usuario en SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac10b-132">Registering User-Defined Types in SQL Server</span></span>](registering-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="ac10b-133">Describe cómo registrar y administrar los UDT en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac10b-133">Describes how to register and manage UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ac10b-134">Trabajar con tipos definidos por el usuario en SQL Server</span><span class="sxs-lookup"><span data-stu-id="ac10b-134">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="ac10b-135">Describe cómo crear consultas mediante los UDT.</span><span class="sxs-lookup"><span data-stu-id="ac10b-135">Describes how to create queries using UDTs.</span></span>  
  
 [<span data-ttu-id="ac10b-136">Acceso a tipos definidos por el usuario en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ac10b-136">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
 <span data-ttu-id="ac10b-137">Describe cómo trabajar con los UDT mediante el proveedor de datos de .NET Framework para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="ac10b-137">Describes how to work with UDTs using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ADO.NET.</span></span>  
  
  
