---
title: Atributos personalizados para las rutinas CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- SqlFacet attribute
- SqlTrigger attribute
- SqlProcedure attribute
- custom attributes [CLR integration]
- SqlUserDefinedAggregate attribute
- attributes [CLR integration]
- SqlMethod attribute
- SqlFunction attribute
- common language runtime [SQL Server], attributes
- SqlUserDefinedTypeAttribute attribute
ms.assetid: 95069d22-b05d-4670-b053-15ee2a664e33
author: rothja
ms.author: jroth
ms.openlocfilehash: 058bbec7f0f1f63fbd96258a0abe7a6c3d543d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662101"
---
# <a name="custom-attributes-for-clr-routines"></a><span data-ttu-id="e76a3-102">Atributos personalizados para las rutinas de CLR</span><span class="sxs-lookup"><span data-stu-id="e76a3-102">Custom Attributes for CLR Routines</span></span>
  <span data-ttu-id="e76a3-103">Los atributos enumerados se pueden aplicar a rutinas Common Language Runtime (CLR), tipos definidos por el usuario y agregados definidos por el usuario que estén registrados en [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e76a3-103">The attributes listed can be applied to common language runtime (CLR) routines, user-defined types, and user-defined aggregates that are registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e76a3-104">Si no se aplica el atributo, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] asume el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e76a3-104">If the attribute is not applied, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assumes the default value.</span></span> <span data-ttu-id="e76a3-105">Los atributos que se enumeran se definen en el espacio de nombres `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="e76a3-105">The attributes listed are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="the-sqluserdefinedaggregate-attribute"></a><span data-ttu-id="e76a3-106">Atributo SqlUserDefinedAggregate</span><span class="sxs-lookup"><span data-stu-id="e76a3-106">The SqlUserDefinedAggregate Attribute</span></span>  
 <span data-ttu-id="e76a3-107">El atributo `SqlUserDefinedAggregate` indica que el método debe registrarse como un agregado definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e76a3-107">The `SqlUserDefinedAggregate` attribute indicates that the method should be registered as a user-defined aggregate.</span></span> <span data-ttu-id="e76a3-108">Los agregados definidos por el usuario deben anotarse con este atributo.</span><span class="sxs-lookup"><span data-stu-id="e76a3-108">Every user-defined aggregate must be annotated with this attribute.</span></span>  
  
 <span data-ttu-id="e76a3-109">Para obtener más información, vea [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span><span class="sxs-lookup"><span data-stu-id="e76a3-109">For more information, see [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span></span>  
  
## <a name="the-sqlfunction-attribute"></a><span data-ttu-id="e76a3-110">Atributo SqlFunction</span><span class="sxs-lookup"><span data-stu-id="e76a3-110">The SqlFunction Attribute</span></span>  
 <span data-ttu-id="e76a3-111">El atributo `SqlFunction` indica que el método debe registrarse como una función, con el conjunto de atributos de función correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e76a3-111">The `SqlFunction` attribute indicates the method should be registered as a function, with the appropriate function attributes set.</span></span>  
  
 <span data-ttu-id="e76a3-112">Para obtener más información, vea [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span><span class="sxs-lookup"><span data-stu-id="e76a3-112">For more information, see [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span></span>  
  
## <a name="the-sqlfacet-attribute"></a><span data-ttu-id="e76a3-113">Atributo SqlFacet</span><span class="sxs-lookup"><span data-stu-id="e76a3-113">The SqlFacet Attribute</span></span>  
 <span data-ttu-id="e76a3-114">El atributo `SqlFacet` se usa para devolver información acerca del tipo de valor devuelto por una expresión de tipos definidos por el usuario (UDT).</span><span class="sxs-lookup"><span data-stu-id="e76a3-114">The `SqlFacet` attribute is used to return information about the return type of a user-defined type (UDT) expression.</span></span>  
  
 <span data-ttu-id="e76a3-115">Para obtener más información, vea [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span><span class="sxs-lookup"><span data-stu-id="e76a3-115">For more information, see [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span></span>  
  
## <a name="the-sqlprocedure-attribute"></a><span data-ttu-id="e76a3-116">Atributo SqlProcedure</span><span class="sxs-lookup"><span data-stu-id="e76a3-116">The SqlProcedure Attribute</span></span>  
 <span data-ttu-id="e76a3-117">El atributo `SqlProcedure` indica que el método debe registrarse como un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="e76a3-117">The `SqlProcedure` attribute indicates the method should be registered as a stored procedure.</span></span> <span data-ttu-id="e76a3-118">Solamente Visual Studio usa este atributo para registrar automáticamente el método especificado como un procedimiento almacenado; [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no lo usa.</span><span class="sxs-lookup"><span data-stu-id="e76a3-118">This attribute is used only by Visual Studio to register the specified method as a stored procedure automatically; it is not used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e76a3-119">Para obtener más información, vea [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span><span class="sxs-lookup"><span data-stu-id="e76a3-119">For more information, see [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span></span>  
  
## <a name="the-sqltrigger-attribute"></a><span data-ttu-id="e76a3-120">Atributo SqlTrigger</span><span class="sxs-lookup"><span data-stu-id="e76a3-120">The SqlTrigger Attribute</span></span>  
 <span data-ttu-id="e76a3-121">El atributo `SqlTrigger` indica que el método debe registrarse como un desencadenador.</span><span class="sxs-lookup"><span data-stu-id="e76a3-121">The `SqlTrigger` attribute indicates the method should be registered as a trigger.</span></span>  
  
 <span data-ttu-id="e76a3-122">Para obtener más información, vea [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) y [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span><span class="sxs-lookup"><span data-stu-id="e76a3-122">For more information, see [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) and [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span></span>  
  
## <a name="the-sqluserdefinedtypeattribute"></a><span data-ttu-id="e76a3-123">Atributo SqlUserDefinedTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="e76a3-123">The SqlUserDefinedTypeAttribute</span></span>  
 <span data-ttu-id="e76a3-124">Puede aplicar el atributo SqlUserDefinedTypeAttribute a una definición de clase en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e76a3-124">You can apply the SqlUserDefinedTypeAttribute to a class definition in the assembly.</span></span> <span data-ttu-id="e76a3-125">Esto hace que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cree un tipo definido por el usuario que se enlaza a la definición de clase que tiene este atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="e76a3-125">It causes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to create a user-defined type that is bound to the class definition which has this custom attribute.</span></span>  
  
 <span data-ttu-id="e76a3-126">Para obtener más información, vea [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span><span class="sxs-lookup"><span data-stu-id="e76a3-126">For more information, see [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span></span>  
  
## <a name="the-sqlmethod-attribute"></a><span data-ttu-id="e76a3-127">Atributo SqlMethod</span><span class="sxs-lookup"><span data-stu-id="e76a3-127">The SqlMethod Attribute</span></span>  
 <span data-ttu-id="e76a3-128">El atributo `SqlMethod` se usa para indicar el determinismo y las propiedades de acceso a datos de un método o una propiedad en un UDT.</span><span class="sxs-lookup"><span data-stu-id="e76a3-128">The `SqlMethod` attribute is used to indicate the determinism and data access properties of a method or a property on a UDT.</span></span>  
  
 <span data-ttu-id="e76a3-129">Para obtener más información, vea [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span><span class="sxs-lookup"><span data-stu-id="e76a3-129">For more information, see [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e76a3-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e76a3-130">See Also</span></span>  
 <span data-ttu-id="e76a3-131">[Agregados definidos por el usuario CLR](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span><span class="sxs-lookup"><span data-stu-id="e76a3-131">[CLR User-Defined Aggregates](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span></span>  
 <span data-ttu-id="e76a3-132">[Funciones definidas por el usuario de CLR](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="e76a3-132">[CLR User-Defined Functions](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="e76a3-133">[Tipos definidos por el usuario CLR](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="e76a3-133">[CLR User-Defined Types](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 <span data-ttu-id="e76a3-134">[Procedimientos almacenados CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="e76a3-134">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="e76a3-135">Desencadenadores de CLR</span><span class="sxs-lookup"><span data-stu-id="e76a3-135">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
  
  
