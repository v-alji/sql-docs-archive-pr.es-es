---
title: Trabajar con tipos de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DataType object
- SQL Server Management Objects, data types
- data types [SMO]
- SMO [SQL Server], data types
ms.assetid: 1e0e736a-c709-4d89-aeb2-b32dcfd641fa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbffc1c59eb12fa0f448a7fcb26157d5e18dba3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669551"
---
# <a name="working-with-data-types"></a><span data-ttu-id="f476f-102">Trabajar con tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f476f-102">Working with Data Types</span></span>
  <span data-ttu-id="f476f-103">Los datos se presentan en diversos tipos y tamaños como, por ejemplo, una cadena con una longitud definida, un número con una precisión específica o un tipo de datos definido por el usuario que es otro objeto que tiene su propio conjunto de reglas.</span><span class="sxs-lookup"><span data-stu-id="f476f-103">Data comes in many types and sizes, such as a string that has a defined length, a number that has specific accuracy, or a user-defined data type that is another object that has its own set of rules.</span></span> <span data-ttu-id="f476f-104">El <xref:Microsoft.SqlServer.Management.Smo.DataType> objeto clasifica el tipo de datos para que pueda controlarse correctamente mediante [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f476f-104">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object classifies the type of data so that it can be handled correctly by [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f476f-105">El objeto <xref:Microsoft.SqlServer.Management.Smo.DataType> está asociada a objetos que aceptan datos.</span><span class="sxs-lookup"><span data-stu-id="f476f-105">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object is associated with objects that accept data.</span></span> <span data-ttu-id="f476f-106">Los siguientes objetos SMO (objetos de administración de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]) aceptan datos que deben definirse mediante una propiedad de objeto <xref:Microsoft.SqlServer.Management.Smo.DataType>:</span><span class="sxs-lookup"><span data-stu-id="f476f-106">The following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects accept data that must be defined by a <xref:Microsoft.SqlServer.Management.Smo.DataType> object property:</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Column>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedAggregateParameter>  
  
 <span data-ttu-id="f476f-107">La propiedad `DataType` de los objetos que aceptan los datos puede establecerse de varias formas.</span><span class="sxs-lookup"><span data-stu-id="f476f-107">The `DataType` property for objects that accept data can be set in several ways.</span></span>  
  
-   <span data-ttu-id="f476f-108">Use el constructor predeterminado y especifique las propiedades de objeto <xref:Microsoft.SqlServer.Management.Smo.DataType> de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="f476f-108">Use the default constructor and specify <xref:Microsoft.SqlServer.Management.Smo.DataType> object properties explicitly</span></span>  
  
-   <span data-ttu-id="f476f-109">Use un constructor sobrecargado y especifique las propiedades <xref:Microsoft.SqlServer.Management.Smo.DataType> como parámetros.</span><span class="sxs-lookup"><span data-stu-id="f476f-109">Use an overloaded constructor and specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> properties as parameters.</span></span>  
  
-   <span data-ttu-id="f476f-110">Especifique el objeto <xref:Microsoft.SqlServer.Management.Smo.DataType> insertado en el constructor de objeto.</span><span class="sxs-lookup"><span data-stu-id="f476f-110">Specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> inline in the object constructor.</span></span>  
  
-   <span data-ttu-id="f476f-111">Use uno de los miembros estáticos de la clase <xref:Microsoft.SqlServer.Management.Smo.DataType> como, por ejemplo, `Int`.</span><span class="sxs-lookup"><span data-stu-id="f476f-111">Use one of the static members of the <xref:Microsoft.SqlServer.Management.Smo.DataType> class, for example `Int`.</span></span> <span data-ttu-id="f476f-112">De esta forma, se devolverá una instancia de un objeto <xref:Microsoft.SqlServer.Management.Smo.DataType>.</span><span class="sxs-lookup"><span data-stu-id="f476f-112">This will in fact return an instance of a <xref:Microsoft.SqlServer.Management.Smo.DataType> object.</span></span>  
  
 <span data-ttu-id="f476f-113">El objeto <xref:Microsoft.SqlServer.Management.Smo.DataType> tiene varias propiedades que definen el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f476f-113">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object has several properties that define the type of data.</span></span> <span data-ttu-id="f476f-114">Por ejemplo, la propiedad <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> especifica el tipo de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f476f-114">For example, the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> property specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.</span></span> <span data-ttu-id="f476f-115">Los valores constantes que representan los tipos de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se relacionan en la enumeración <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="f476f-115">The constant values that represent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types are listed in the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="f476f-116">Se trata de tipos de datos como `varchar`, `nchar`, `currency`, `integer`, `float` y `datetime`.</span><span class="sxs-lookup"><span data-stu-id="f476f-116">This refers to data types such as `varchar`, `nchar`, `currency`, `integer`, `float`, and `datetime`.</span></span>  
  
 <span data-ttu-id="f476f-117">Al establecer el tipo de datos, deben establecerse propiedades concretas para los datos.</span><span class="sxs-lookup"><span data-stu-id="f476f-117">When the data type is established, specific properties must be set for the data.</span></span> <span data-ttu-id="f476f-118">Por ejemplo, si es un tipo `nchar`, la longitud de los datos de cadena debe establecerse en la propiedad `Length`.</span><span class="sxs-lookup"><span data-stu-id="f476f-118">For example, if it is an `nchar` type, the length of the string data must be set in the `Length` property.</span></span> <span data-ttu-id="f476f-119">Esto mismo se aplica a los valores numéricos, en los que debe especificarse una precisión y una escala.</span><span class="sxs-lookup"><span data-stu-id="f476f-119">The same applies for numeric values, where you would have to specify precision and scale.</span></span>  
  
 <span data-ttu-id="f476f-120">Los tipos de datos <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> y <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> hacen referencia a objetos que contienen la definición del tipo de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f476f-120"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> data types refer to objects that contain the definition of the type of data defined by the user.</span></span> <span data-ttu-id="f476f-121"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> se basa en los tipos de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de la enumeración <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="f476f-121">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> is based on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types from the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="f476f-122"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>Se basa en los [!INCLUDE[msCoName](../../../includes/msconame-md.md)] tipos de datos de .net.</span><span class="sxs-lookup"><span data-stu-id="f476f-122">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> is based on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET data types.</span></span> <span data-ttu-id="f476f-123">Normalmente, representarían datos de un tipo específico que la base de datos reutiliza con frecuencia debido a las reglas de negocios definidas por la organización.</span><span class="sxs-lookup"><span data-stu-id="f476f-123">Typically, these would represent data of a specific type that is frequently reused by the database because of business rules defined by the organization.</span></span> <span data-ttu-id="f476f-124">Por ejemplo, un tipo de datos que almacena una cantidad de dinero y un denominador de divisa resultarían de gran utilidad en una compañía que trabaje con distintas divisas.</span><span class="sxs-lookup"><span data-stu-id="f476f-124">For example, a data type that stores an amount of money and a currency denominator would be helpful in a company that deals in multiple currencies.</span></span>  
  
 <span data-ttu-id="f476f-125">La enumeración <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> contiene una lista de todos los tipos de datos compatibles con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f476f-125">The <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration contains a list of all the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-supported data types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f476f-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f476f-126">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-basic"></a><span data-ttu-id="f476f-127">Construir un objeto DataType con la especificación del constructor de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f476f-127">Constructing a DataType Object with the Specification in the Constructor in Visual Basic</span></span>  
 <span data-ttu-id="f476f-128">En este ejemplo de código se muestra cómo utilizar el constructor para crear instancias de tipos de datos basadas en tipos de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] diferentes.</span><span class="sxs-lookup"><span data-stu-id="f476f-128">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f476f-129">Los tipos <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> y XML exigen, todos ellos, un valor de nombre que identifique el objeto.</span><span class="sxs-lookup"><span data-stu-id="f476f-129">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes1](SMO How to#SMO_VBDataTypes1)]  -->  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-c"></a><span data-ttu-id="f476f-130">Construir un objeto DataType con la especificación del constructor de Visual Basic C#</span><span class="sxs-lookup"><span data-stu-id="f476f-130">Constructing a DataType Object with the Specification in the Constructor in Visual C#</span></span>  
 <span data-ttu-id="f476f-131">En este ejemplo de código se muestra cómo utilizar el constructor para crear instancias de tipos de datos basadas en tipos de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] diferentes.</span><span class="sxs-lookup"><span data-stu-id="f476f-131">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f476f-132">Los tipos <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> y XML exigen, todos ellos, un valor de nombre que identifique el objeto.</span><span class="sxs-lookup"><span data-stu-id="f476f-132">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare a DataType object variable and define the data type in the constructor.   
DataType dt;   
//For the decimal data type the following two arguments specify precision, and scale.   
dt = new DataType(SqlDataType.Decimal, 10, 2);   
}  
```  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-basic"></a><span data-ttu-id="f476f-133">Construir un objeto DataType utilizando el constructor predeterminado de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f476f-133">Constructing a DataType Object by Using the Default Constructor in Visual Basic</span></span>  
 <span data-ttu-id="f476f-134">En este ejemplo de código se muestra cómo utilizar el constructor predeterminado para crear instancias de tipos de datos basadas en tipos de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] diferentes.</span><span class="sxs-lookup"><span data-stu-id="f476f-134">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="f476f-135">Después, las propiedades se utilizan para especificar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f476f-135">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="f476f-136">**Nota:** Los <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> tipos de XML, y requieren un valor de nombre para identificar el objeto.</span><span class="sxs-lookup"><span data-stu-id="f476f-136">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes2](SMO How to#SMO_VBDataTypes2)]  -->  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-c"></a><span data-ttu-id="f476f-137">Construir un objeto DataType utilizando el constructor predeterminado de Visual C#</span><span class="sxs-lookup"><span data-stu-id="f476f-137">Constructing a DataType Object by Using the Default Constructor in Visual C#</span></span>  
 <span data-ttu-id="f476f-138">En este ejemplo de código se muestra cómo utilizar el constructor predeterminado para crear instancias de tipos de datos basadas en tipos de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] diferentes.</span><span class="sxs-lookup"><span data-stu-id="f476f-138">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="f476f-139">Después, las propiedades se utilizan para especificar el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="f476f-139">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="f476f-140">**Nota:** Los <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> tipos de XML, y requieren un valor de nombre para identificar el objeto.</span><span class="sxs-lookup"><span data-stu-id="f476f-140">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare and create a DataType object variable.   
DataType dt;   
dt = new DataType();   
//Define the data type by setting the SqlDataType property.   
dt.SqlDataType = SqlDataType.VarChar;   
//The VarChar data type requires a value for the MaximumLength property.   
dt.MaximumLength = 100;   
}  
```  
  
  
